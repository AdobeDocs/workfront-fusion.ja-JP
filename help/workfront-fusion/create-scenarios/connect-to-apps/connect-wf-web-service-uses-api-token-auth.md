---
title: API トークン認証を使用する web サービスに Adobe Workfront Fusion を接続
description: 一部のサービスでは、Adobe Workfront Fusionなどの統合ソリューションでは、シナリオで簡単に使用できるアプリを作成できません。
author: Becky
feature: Workfront Fusion
exl-id: 4a8ac816-52de-41e8-96d7-1c8cde2ebe32
TQID: https://experienceleague.adobe.com/y1H-y57MvK4LScn9Z6sUYuua3kr3iqyY-ElYkmCgxrI
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 985
ht-degree: 49%

---

# API トークン認証を使用する web サービスに Adobe Workfront Fusion を接続

一部のサービスでは、Adobe Workfront Fusionなどの統合ソリューションでは、シナリオで簡単に使用できるアプリを作成できません。

この状況に対する回避策は、HTTP/リクエストモジュールを使用して、目的のサービス（アプリ）をWorkfront Fusionに接続することです。

この記事では、API キー/API トークンを使用して、ほぼすべてのweb サービスをWorkfront Fusionに接続する方法について説明します。

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
   <p>コネクターベース（レガシー）: Workfront以外のアプリケーションに接続するには、作業の自動化と統合用のWorkfront Fusionが必要です </p>
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

## API トークンを使用する web サービスへの接続

API トークンを介してサービスに接続する手順は、ほとんどの web サービスで同様です。

1. Web サービスの web サイト上にアプリケーションを作成します。詳しくは、この記事の[新しいアプリケーションを作成して API トークンを取得](#create-a-new-application-and-obtain-the-api-token)を参照してください。
1. API キーまたは API トークンを取得します。
1. Workfront FusionのHTTP/リクエストモジュールをシナリオに追加します。
1. この記事の「[HTTP モジュールの設定](#set-up-the-http-module)」の節で説明しているように、web サービスのAPI ドキュメントに従ってモジュールを設定し、シナリオを実行します。

>[!NOTE]
>
>次の使用例は、プッシュオーバー通知サービスに接続します。

## 新しいアプリケーションを作成して API トークンを取得

>[!NOTE]
>
>Web サービスで API キーまたは API トークンを作成および配布するには、多くの異なる方法があります。 目的の web サービスの API キーとトークンの取得手順については、サービスの web サイトにアクセスし、「API キー」または「API トークン」を検索してください。
>
>Pushover API キーを取得する手順は、検索対象の例として記載しているだけです。

1. プッシュオーバーアカウントにログインします。
1. ページの下部にある「**Create an Application/API Token**」をクリックします。
1. アプリケーション情報を入力し、「**Create an Application**」をクリックします。
1. 提供された API トークンを安全な場所に保存します。 Workfront Fusion HTTP/リクエストモジュールを作成して、目的のweb サービス（この場合はプッシュオーバー）に接続する必要があります。

## HTTP モジュールの設定

web サービスをWorkfront Fusion シナリオに接続するには、シナリオでHTTP/リクエストモジュールを使用し、web サービスのAPI ドキュメントに従ってモジュールを設定する必要があります。

1. HTTP/リクエストモジュールをシナリオに追加します。
1. Workfront Fusionを使用してメッセージをプッシュするには、HTTP モジュールを次のように設定します。

   >[!NOTE]
   >
   >これらのモジュール設定は、Pushover web サービス API ドキュメントに対応しています。 他の web サービスでは設定が異なる場合があります。 例えば、API トークンは、Body フィールドではなくHeaderに挿入できます。

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
      <td> <p><code>POST</code> </p> <p>使用されるメソッドは、対応するエンドポイントによって異なります。 メッセージをプッシュするための Pushover エンドポイントでは、POST メソッドを使用します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> ヘッダー</p> </td> 
      <td> <p>一部の web サービスでは、ヘッダーを使用して API トークン認証や他のパラメーターを指定します。 メッセージをプッシュする際、Pushover エンドポイントはすべてのリクエストタイプで本文を使用するので、この例ではそうではありません（以下を参照）。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> クエリ文字列</p> </td> 
      <td> <p>一部の web サービスでは、クエリ文字列を使用して他のパラメーターを指定します。 この例では、Pushover web サービスがすべてのリクエストタイプにBody （以下を参照）を使用するため、この例では当てはまりません。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Body Type</p> </td> 
      <td> <p><code>Raw</code> </p> <p>この設定を使用すると、以下の「コンテンツタイプ」フィールドでJSON コンテンツタイプを選択できます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> コンテンツタイプ</p> </td> 
      <td> <p><code>JSON (application/json)</code> </p> <p>JSONは、プッシュオーバーアプリで必要なコンテンツタイプです。 これは、他の web サービスとは異なる場合があります。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> コンテンツを依頼</p> </td> 
      <td> <p>JSON形式でBody リクエストコンテンツを入力します。 JSON/JSONを作成モジュールを使用できます。詳しくは、<a href="#map-the-json-body-using-the-json--create-json-module" class="MCXref xref">JSON/JSONを作成モジュールを使用してJSON本文をマッピングする</a>を参照してください。 または、<a href="#enter-the-json-body-manually" class="MCXref xref">この記事の「JSON本文を手動で入力する</a>」で説明しているように、JSON コンテンツを手動で入力することもできます。</p> <p>その web サービスに必要なパラメーターについて詳しくは、web サービスの API ドキュメントを参照してください。</p> </td>

   </tr> 
    </tbody> 
   </table>

## JSON本文を手動で入力する

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

この例には、次の情報が含まれています。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p> ユーザー</p> </td> 
   <td> <p>USER_KEY。 これは、プッシュオーバーダッシュボードにあります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> トークン </td> 
   <td> <p>プッシュオーバーアプリを作成した際に生成されたAPI トークン/API キー。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> message </td> 
   <td> <p>デバイスに送信されるプッシュ通知のテキストコンテンツ。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> タイトル </td> 
   <td> <p>（オプション）メッセージのタイトル。 値を入力しない場合は、アプリの名前が使用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## JSON/JSONを作成モジュールを使用してJSON本文をマッピングします

JSONを作成モジュールを使用すると、JSONの指定が簡単になります。 また、値を動的に定義することもできます。

JSON モジュールについて詳しくは、[JSON モジュール](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/json-modules.md)を参照してください。

1. JSON を作成する元となる値を入力またはマッピングします。

   ![JSON値](/help/workfront-fusion/create-scenarios/connect-to-apps/assets/json-values-350x288.png)

1. JSON/JSON モジュールをHTTP/リクエストモジュールに接続します。
1. JSONを作成モジュールのJSON文字列を、HTTP/リクエストモジュールを作成のリクエストコンテンツフィールドにマッピングします。

シナリオを実行すると、プッシュ通知はプッシュオーバーアカウントに登録されているデバイスに送信されます。
