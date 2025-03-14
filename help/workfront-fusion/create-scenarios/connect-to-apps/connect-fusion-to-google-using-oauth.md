---
title: カスタム OAuth クライアントを使用して Google Services に Adobe Workfront Fusion を接続
description: Adobe Workfront Fusion を使用して、カスタム OAuth クライアントを使用してGoogle サービスに接続できます。 この手順を実行するには、既存のGoogle アカウントが必要です。
author: Becky
feature: Workfront Fusion
exl-id: 2f0bc289-4ecf-4a31-9d7b-641bbca6fc95
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 26%

---

# カスタム OAuth クライアントを使用して Google Services に Adobe Workfront Fusion を接続

Adobe Workfront Fusion を使用して、カスタム OAuth クライアントを使用してGoogle サービスに接続できます。 この手順を実行するには、既存のGoogle アカウントが必要です。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront プランを選択する：組織がAdobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

この接続を行うには、既存のGoogle アカウントが必要です。

## カスタム OAuth クライアントを使用して Fusion をGoogle サービスに接続する

この連携を作成するには、Google Cloud Platform でプロジェクトを作成して設定し、そのプロジェクトに基づいて Fusion で連携を設定する必要があります。

>[!NOTE]
>
>この手順の目的は次のとおりです。
>
>* 個人用（`@gmail.com` および `@googlemail.com` ユーザー）
>* 内部使用（カスタム OAuth クライアントの使用を希望するGoogle Workspace ユーザー）

* [Google Cloud Platform でのプロジェクトの作成](#create-a-project-on-google-cloud-platform)
* [OAuth 同意設定の指定 ](#configure-oauth-consent-settings)
* [OAuth 認証情報の作成](#create-oauth-credentials)
* [Workfront Fusion でGoogleに接続する](#connect-to-google-in-workfront-fusion)

### Google Cloud Platform でのプロジェクトの作成

Google Cloud Platform でプロジェクトを作成するには：

1. Google Cloud Platform でプロジェクトの作成を開始します。

   手順については、Google ドキュメントの [Google Cloud プロジェクトの作成 ](https://developers.google.com/workspace/guides/create-project) を参照してください。
1. API を有効にする場合は、Google Drive API と、使用するすべてのGoogle アプリの API （Google Sheets API など）を有効にする必要があります。
1. プロジェクトの作成を完了します。
1. この記事にある [OAuth の同意設定を指定](#configure-oauth-consent-settings)の節に進みます。

### OAuth 同意設定の指定

1. プロジェクトの OAuth 設定の開始

   手順については、Google ドキュメントの [OAuth 同意画面の設定と範囲の選択 ](https://developers.google.com/workspace/guides/configure-oauth-consent) を参照してください。
1. **外部**&#x200B;を選択し、続いて「**作成**」をクリックします。

   >[!NOTE]
   >
   >このオプションを選択すると、課金されなくなります。詳しくは、検証要件の例外に関するGoogleの情報を参照してください。

1. 必須フィールドに次のように入力します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>アプリ名</p> </td> 
      <td> <p>同意を要求するアプリの名前を入力します。</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b> 例：</b></span></span>Adobe Workfront Fusion </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">ユーザーサポートメール</td> 
      <td>ユーザーがこのアプリに接続する際の同意に関する質問を連絡するためのメールアドレスを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">メールアドレス</td> 
      <td>Google がプロジェクトに対する変更を通知する際に使用できるメールアドレスを 1 つ以上入力します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「承認済みのドメイン」で、「**ドメインを追加**」をクリックし、`workfrontfusion.com` と入力します。
1. 次の範囲を追加します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>サービス／API</th> 
      <th>必須スコープ</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td> <p>Gmail</p> </td> 
      <td> <p>https://mail.google.com/</p> <p>https://www.googleapis.com/auth/gmail.labels</p> <p>https://www.googleapis.com/auth/gmail.send</p> <p>https://www.googleapis.com/auth/gmail.readonly</p> <p>https://www.googleapis.com/auth/gmail.compose</p> <p>https://www.googleapis.com/auth/gmail.insert</p> <p>https://www.googleapis.com/auth/gmail.modify</p> <p>https://www.googleapis.com/auth/gmail.metadata</p> </td> 
     </tr> 
     <tr> 
      <td> <p>Google ドライブ</p> </td> 
      <td> <p>https://www.googleapis.com/auth/drive</p> <p>https://www.googleapis.com/auth/drive.readonly</p> </td> 
     </tr> 
    </tbody> 
   </table>

   リストを展開するか、リストの次のページに移動して、すべてを表示する必要が生じる場合があります。

1. （オプション）テストユーザーをプロジェクトに追加します。
1. 情報の正確性を確認し、「**ダッシュボードに戻る**」をクリックします。

   >[!NOTE]
   >
   >Googleによる確認のために、同意画面と申請書を送信する必要はありません。

1. [OAuth 資格情報を作成](#create-oauth-credentials)に進みます。

### OAuth 資格情報を作成

1. OAuth クライアント ID 資格情報の作成を開始します。

   手順については、Google ドキュメントの [ アクセス資格情報の作成 ](https://developers.google.com/workspace/guides/create-credentials) を参照してください。

   >[!NOTE]
   >
   >これが最初に有効にした API またはサービス（Gmail またはGoogle ドライブ）でない場合は、新しい資格情報を作成する必要はありません。

1. 必須フィールドに次のように入力します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">アプリケーションタイプ</td> 
      <td> <p> Web アプリケーション</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">名前</td> 
      <td>Workfront Fusion </td> 
     </tr> 
    </tbody> 
   </table>

1. [ 承認済みのリダイレクト URI] で、次の **いずれか** を入力します。

   * Gmail またはGoogle ドライブの場合：`https://app.workfrontfusion.com/oauth/cb/google-restricted`

   * その他のGoogle アプリの場合：`https://app.workfrontfusion.com/oauth/cb/google`

1. 「**作成**」をクリックします。

   クライアント ID とクライアント秘密鍵が表示されます。

1. クライアント ID とクライアント秘密鍵を安全な場所にコピーします。 これらを使用して、Workfront Fusion に接続します。
1. [Workfront Fusion でGoogleに接続 ](#connect-to-google-in-workfront-fusion) を続けます。

### Workfront Fusion でGoogleに接続する

Googleへの接続を作成するプロセスは、Google サービスのモジュール（Google Sheets やGoogle Docsなど）を使用しているか、HTTP >Make an OAuth2.0 request module を介してGoogleに接続しているかによって異なります。

* [Google サービスでのGoogleへの接続](#connect-to-google-in-a-google-service)
* [HTTP / OAuth2.0 リクエストを行うモジュールで、Googleに接続します。](#connect-to-google-in-the-http--make-an-oauth20-request-module)

#### Google サービスでのGoogleへの接続

1. Workfront Fusion で、接続を作成する必要があるGoogle モジュールを見つけます。
1. 「**接続を作成**」をクリックしてから、「**詳細設定を表示**」をクリックします。
1. 必要に応じて、「接続名」、「環境」、「タイプ」の各フィールドに入力します。
1. 取得したクライアント ID とクライアントシークレットを [OAuth 認証情報を作成 ](#create-oauth-credentials) の各フィールドに入力し、「**続行**」をクリックします。

1. Google アカウントでログインします。

   **このアプリは検証されていません**&#x200B;ウィンドウが表示されます。ウィンドウのタイトルに表示される「アプリ」は、前述で作成した OAuth クライアントです。

1. **詳細** をクリックし、**Workfront Fusion に移動（安全でない）** をクリックして、カスタム OAuth クライアントを使用したアクセスを許可します。

1. 「**許可**」をクリックして、Workfront Fusion の権限を付与します。
1. 表示されるウィンドウで、「**許可**」を再度クリックして、選択内容を確認します。

   カスタム OAuth クライアントを使用した目的のGoogle サービスへの接続が確立されます。

#### HTTP / OAuth2.0 リクエストを行うモジュールで、Googleに接続します。 {#connect-to-google-in-the-http--make-an-oauth20-request-module}

HTTP/ OAuth2.0 リクエストモジュールでGoogleに接続する手順については、HTTP/ OAuth 2.0 リクエストモジュールを作成するでの [Googleへの接続の作成手順 ](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module) を参照してください。

## 次のエラーメッセージが表示されます：[403 アクセスが設定されていません ]

`403 Access Not Configured` エラーメッセージが表示された場合は、Google Cloud Platform で対応する API を有効にする必要があります。 この API を有効にするには、この記事の [Google Cloud Platform でプロジェクトを作成する ](#create-a-project-on-google-cloud-platform) の節の手順に従ってください。
