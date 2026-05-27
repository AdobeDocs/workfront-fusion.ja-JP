---
title: カスタム OAuth クライアントを使用して Google Services に Adobe Workfront Fusion を接続
description: Adobe Workfront Fusionを使用して、カスタム OAuth クライアントを使用してGoogle サービスに接続できます。 この手順を実行するには、既存のGoogle アカウントが必要です。
author: Becky
feature: Workfront Fusion
exl-id: 2f0bc289-4ecf-4a31-9d7b-641bbca6fc95
TQID: https://experienceleague.adobe.com/Y-cRr-lDvYKc83iwzPoB2Rs9gKD9LCZQFfiBgefal7I
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1022
ht-degree: 37%

---

# カスタム OAuth クライアントを使用して Google Services に Adobe Workfront Fusion を接続

Adobe Workfront Fusionを使用して、カスタム OAuth クライアントを使用してGoogle サービスに接続できます。 この手順を実行するには、既存のGoogle アカウントが必要です。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意の Adobe Workfront Workflow パッケージと任意の Adobe Workfront Automation および Integration パッケージ</p><p>Workfront Ultimate</p><p>Workfront Fusion を追加購入した Workfront Prime および Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>Work またはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

この接続を行うには、既存のGoogle アカウントが必要です。

## カスタム OAuth クライアントを使用してFusionをGoogle サービスに接続する

この接続を作成するには、Google Cloud Platformでプロジェクトを作成して設定し、そのプロジェクトに基づいてFusionで接続を設定する必要があります。

>[!NOTE]
>
>この手順の目的は次のとおりです。
>
>* 個人用（`@gmail.com` および `@googlemail.com` ユーザー）
>* 内部使用（カスタム OAuth クライアントの使用を希望するGoogle Workspace ユーザー）

* [Google Cloud Platformでのプロジェクトの作成](#create-a-project-on-google-cloud-platform)
* [OAuth同意設定の設定](#configure-oauth-consent-settings)
* [OAuth資格情報の作成](#create-oauth-credentials)
* [Workfront FusionでGoogleに接続する](#connect-to-google-in-workfront-fusion)

### Google Cloud Platformでのプロジェクトの作成

Google Cloud Platformでプロジェクトを作成するには：

1. Google Cloud Platformでプロジェクトの作成を開始します。

   手順については、Google ドキュメントの「[Google Cloud プロジェクトを作成する](https://developers.google.com/workspace/guides/create-project)」を参照してください。
1. APIを有効にする場合は、Google Drive APIと、使用するすべてのGoogle アプリケーション（Google Sheets APIなど）のAPIを有効にする必要があります。
1. プロジェクトの作成を完了します。
1. この記事にある [OAuth の同意設定を指定](#configure-oauth-consent-settings)の節に進みます。

### OAuth同意設定の設定

1. プロジェクトのOAuthの設定を開始します

   手順については、[OAuth同意画面の設定を参照し、Google ドキュメントのスコープ ](https://developers.google.com/workspace/guides/configure-oauth-consent)を選択してください。
1. **外部**&#x200B;を選択し、続いて「**作成**」をクリックします。

   >[!NOTE]
   >
   >このオプションを選択すると、課金されなくなります。 詳しくは、Googleの検証要件の例外に関する情報を参照してください。

1. 必須フィールドに次のように入力します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>アプリ名</p> </td> 
      <td> <p>同意を要求するアプリの名前を入力します。</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span>Adobe Workfront Fusion </p> </td> 
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

1. 「承認済みドメイン」で、「**ドメインを追加**」をクリックし、「`workfrontfusion.com`」と入力します。
1. 次のスコープを追加します。

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
   >Googleによる認証のために、同意画面と申請を送信する必要はありません。

1. [OAuth 資格情報を作成](#create-oauth-credentials)に進みます。

### OAuth 資格情報を作成

1. OAuth クライアント ID資格情報の作成を開始します。

   手順については、Google ドキュメントの「[ アクセス資格情報を作成する](https://developers.google.com/workspace/guides/create-credentials)」を参照してください。

   >[!NOTE]
   >
   >これが最初のAPIまたはサービス（GmailまたはGoogle ドライブ）ではない場合は、新しい資格情報を作成する必要はありません。

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

1. 「承認済みリダイレクト URI」で、次のうち&#x200B;**one**&#x200B;を入力します。

   * GmailまたはGoogle ドライブの場合：`https://app.workfrontfusion.com/oauth/cb/google-restricted`

   * その他のGoogle アプリの場合：`https://app.workfrontfusion.com/oauth/cb/google`

1. 「**作成**」をクリックします。

   Client IDとClient Secretが表示されます。

1. クライアント IDとクライアントシークレットを安全な場所にコピーします。 Workfront Fusionでのつながりを構築するために使用します。
1. 引き続き[Workfront FusionでGoogleに接続](#connect-to-google-in-workfront-fusion)します。

### Workfront FusionでGoogleに接続する

Googleへの接続を作成するプロセスは、Google サービス（Google SheetsやGoogle Docsなど）のモジュールを使用しているか、HTTP >OAuth2.0 リクエストモジュールを作成してGoogleに接続しているかによって異なります。

* [Google サービスでGoogleに接続する](#connect-to-google-in-a-google-service)
* [HTTP/OAuth2.0 リクエストモジュールを作成でGoogleに接続します](#connect-to-google-in-the-http--make-an-oauth20-request-module)

#### Google サービスでGoogleに接続する

1. Workfront Fusionで、接続を作成する必要があるGoogle モジュールを見つけます。
1. 「**接続を作成**」をクリックしてから、「**詳細設定を表示**」をクリックします。
1. 必要に応じて、「接続名」、「環境」および「タイプ」フィールドに入力します。
1. 「[OAuth資格情報を作成](#create-oauth-credentials)」で取得したクライアント IDとクライアント秘密鍵を各フィールドに入力し、**続行**&#x200B;をクリックします。

1. Google アカウントでログインします。

   **このアプリは検証されていません**&#x200B;ウィンドウが表示されます。 ウィンドウのタイトルに表示される「アプリ」は、前述で作成した OAuth クライアントです。

1. 「**Advanced**」をクリックし、**Workfront Fusion （安全でない）**&#x200B;に移動して、カスタム OAuth クライアントを使用してアクセスを許可します。

1. 「**許可**」をクリックして、Workfront Fusion権限を付与します。
1. 表示されるウィンドウで、「**許可**」を再度クリックして、選択内容を確認します。

   カスタム OAuth クライアントを使用して、目的のGoogle サービスへの接続が確立されます。

#### HTTP/OAuth2.0 リクエストモジュールを作成でGoogleに接続します {#connect-to-google-in-the-http--make-an-oauth20-request-module}

HTTP/OAuth2.0 リクエストモジュールを作成するHTTPでGoogleに接続する手順については、「[HTTP/OAuth 2.0 リクエストモジュールを作成する](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module)」のHTTP/OAuth 2.0 リクエストモジュールを作成する手順を参照してください。

## 考えられるエラーメッセージ：[403 アクセスが構成されていません]

`403 Access Not Configured` エラーメッセージが表示される場合は、Google Cloud Platformで対応するAPIを有効にする必要があります。 APIを有効にするには、この記事の「[Google Cloud Platformでプロジェクトを作成する](#create-a-project-on-google-cloud-platform)」の節の手順に従います。
