---
title: API トークン認証を使用する web サービスに Adobe Workfront Fusion を接続
description: 一部のサービスでは、Adobe Workfront Fusion などの統合ソリューションを使用して、シナリオで簡単に使用できるアプリを作成できません。
author: Becky
feature: Workfront Fusion
exl-id: 4a8ac816-52de-41e8-96d7-1c8cde2ebe32
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 42%

---

# API トークン認証を使用する web サービスに Adobe Workfront Fusion を接続

一部のサービスでは、Adobe Workfront Fusion などの統合ソリューションを使用して、シナリオで簡単に使用できるアプリを作成できません。

この状況の回避策は、HTTP / リクエストを行うモジュールを使用して、目的のサービス（アプリ）をWorkfront Fusion に接続することです。

この記事では、API キー/API トークンを使用して、ほぼすべての web サービスをWorkfront Fusion に接続する方法について説明します。

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
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
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

## API トークンを使用する web サービスへの接続

API トークンを介してサービスに接続する手順は、ほとんどの web サービスで同様です。

1. Web サービスの web サイト上にアプリケーションを作成します。詳しくは、この記事の[新しいアプリケーションを作成して API トークンを取得](#create-a-new-application-and-obtain-the-api-token)を参照してください。
1. API キーまたは API トークンを取得します。
1. シナリオにWorkfront Fusion の HTTP / リクエストを行うモジュールを追加します。
1. この記事の [HTTP モジュールの設定 ](#set-up-the-http-module) の節で説明されているように、web サービスの API ドキュメントに従ってモジュールを設定し、シナリオを実行します。

>[!NOTE]
>
>次の使用例は、Pushhover 通知サービスに接続します。

## 新しいアプリケーションを作成して API トークンを取得

>[!NOTE]
>
>Web サービスで API キーまたは API トークンを作成および配布するには、多くの異なる方法があります。目的の web サービスの API キーとトークンの取得手順については、サービスの web サイトにアクセスし、「API キー」または「API トークン」を検索してください。
>
>Pushover API キーを取得する手順は、検索対象の例として記載しているだけです。

1. Pushhover アカウントにログインします。
1. ページの下部にある「**Create an Application/API Token**」をクリックします。
1. アプリケーション情報を入力し、「**Create an Application**」をクリックします。
1. 提供された API トークンを安全な場所に保存します。目的の web サービスに接続するには、Workfront Fusion HTTP / リクエストを行うモジュール（この場合は Pushhover）が必要です。

## HTTP モジュールの設定

Web サービスをWorkfront Fusion シナリオに接続するには、シナリオで HTTP/リクエストを行うモジュールを使用し、web サービスの API ドキュメントに従ってモジュールを設定する必要があります。

1. シナリオに HTTP / リクエストを行うモジュールを追加します。
1. Workfront Fusion を使用してメッセージをプッシュするには、HTTP モジュールを次のように設定します。

   >[!NOTE]
   >
   >これらのモジュール設定は、Pushhover web サービス API ドキュメントに対応しています。 他の web サービスでは設定が異なる場合があります。例えば、API トークンは Body フィールドではなく Header に挿入できます。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> URL</td> 
      <td> <p><code>https://api.pushover.net/1/messages.json</code> </p> <p>URL フィールドには、web サービスの API ドキュメントで確認できるエンドポイントが含まれます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> メソッド</td> 
      <td> <p><code>POST</code> </p> <p>使用されるメソッドは、対応するエンドポイントによって異なります。メッセージをプッシュするための Pushover エンドポイントでは、POST メソッドを使用します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> ヘッダー</p> </td> 
      <td> <p>一部の web サービスでは、ヘッダーを使用して API トークン認証や他のパラメーターを指定します。メッセージをプッシュする際、Pushover エンドポイントはすべてのリクエストタイプで本文を使用するので、この例ではそうではありません（以下を参照）。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> クエリ文字列</p> </td> 
      <td> <p>一部の web サービスでは、クエリ文字列を使用して他のパラメーターを指定します。Pushhover web サービスは、すべてのリクエストタイプに対して Body （以下を参照）を使用するので、この例では該当しません。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> 本文タイプ</p> </td> 
      <td> <p><code>Raw</code> </p> <p>この設定を使用すると、下の「コンテンツタイプ」フィールドで JSON コンテンツタイプを選択できます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> コンテンツタイプ</p> </td> 
      <td> <p><code>JSON (application/json)</code> </p> <p>JSON は、Pushover アプリで必要なコンテンツタイプです。 これは、他の web サービスとは異なる場合があります。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> コンテンツをリクエスト</p> </td> 
      <td> <p>Body リクエストのコンテンツを JSON 形式で入力します。 この記事の <a href="#map-the-json-body-using-the-json--create-json-module" class="MCXref xref">JSON を使用した JSON 本文のマッピング/JSON モジュールの作成 </a> で説明しているように、JSON/JSON モジュールを作成を使用できます。 または、この記事の <a href="#enter-the-json-body-manually" class="MCXref xref">JSON 本文の手動入力 </a> で説明しているように、JSON コンテンツを手動で入力できます。</p> <p>その web サービスに必要なパラメーターについて詳しくは、web サービスの API ドキュメントを参照してください。</p> </td>

   </tr> 
    </tbody> 
   </table>

## JSON 本文を手動で入力

パラメーターと値を JSON 形式で指定します。

>[!BEGINSHADEBOX]

**例：**

```
{"user":"12345c2ecu1hq42ypqzhswbyam34",
"token":"123459evz8aepwtxydndydgyumbfx",
"message":"Hello World!",
"title":"The Push Notification"}
```

>[!ENDSHADEBOX]

この例には、次の情報が含まれます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p> ユーザー</p> </td> 
   <td> <p>USER_KEY。これは、Pushhover ダッシュボードにあります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> トークン </td> 
   <td> <p>生成された API トークン/API キーは、Pushover アプリを作成したものです。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> メッセージ </td> 
   <td> <p>デバイスに送信されるプッシュ通知のテキストコンテンツ。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> タイトル </td> 
   <td> <p>（オプション）メッセージのタイトル。値を入力しない場合は、アプリの名前が使用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## JSON/JSON を作成モジュールを使用して JSON 本文をマッピングします

この JSON を作成モジュールを使用すると、JSON の指定が容易になります。 また、値を動的に定義することもできます。

JSON モジュールについて詳しくは、[JSON モジュール](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/json-modules.md)を参照してください。

1. JSON を作成する元となる値を入力またはマッピングします。

   ![JSON 値 ](/help/workfront-fusion/create-scenarios/connect-to-apps/assets/json-values-350x288.png)

1. JSON/JSON を作成モジュールを HTTP/ リクエストを行うモジュールに接続します。
1. JSON を作成モジュールの JSON 文字列を「HTTP / リクエストを行う」モジュールの「リクエストコンテンツ」フィールドにマッピングします。

シナリオを実行すると、プッシュ通知は Pushhover アカウントに登録されているデバイスに送信されます。
