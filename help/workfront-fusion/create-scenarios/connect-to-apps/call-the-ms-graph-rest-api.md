---
title: MS Graph REST API の呼び出し
description: Adobe Workfront Fusion HTTP &> Make an OAuth 2.0 リクエストモジュールを使用してMS Graph REST APIを呼び出します
author: Becky
feature: Workfront Fusion
exl-id: f411c807-955d-44fe-98b1-3ebba3fe0861
TQID: https://experienceleague.adobe.com/EhrbH3ohTVdBxnrbfVI8Uwqq7j8BfCrdWvEn7Y0pe4A
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 719
ht-degree: 36%

---

# MS Graph REST API の呼び出し

多くのMicrosoft web サービスには、Microsoft Graph APIを介してアクセスします。 Microsoft Graph APIへの接続は、Workfront Fusion HTTP/OAuth 2.0 リクエストモジュールを使用して作成できます。

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

## Microsoft Application Registration PortalへのWorkfront Fusionの登録

Microsoft Graph REST APIへの接続を作成するには、まずAdobe Workfront Fusionを登録する必要があります。

1. 新しいアプリケーションの登録を開始します（[Microsoft ID プラットフォームへのアプリケーションの登録](https://docs.microsoft.com/en-us/graph/auth-register-app-v2)）。詳しくは、Microsoft ドキュメントを参照してください。

   Microsoftを導入する際は、次の情報が必要です。

   <table style="table-layout:auto">
      <tr>
        <td>アプリケーション名</td>
        <td>「My Workfront Fusion application」など、アプリケーションの名前を入力します。</td>
      </tr>
      <tr>
        <td>リダイレクト URL</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/oauth2</code></td>
      </tr>
    </table>

1. アプリの登録が完了したら、アプリケーション IDをメモします。

   >[!IMPORTANT]
   >
   >Workfront Fusionで接続を設定するには、アプリケーション IDが必要です。

1. クライアントシークレットを生成します。 このシークレットをメモしておいてください。

   手順については、Microsoft ドキュメントの「[Microsoft ID プラットフォームにアプリケーションを登録する](https://docs.microsoft.com/en-us/graph/auth-register-app-v2)」を参照してください。

   >[!IMPORTANT]
   >
   >Workfront Fusionで接続を設定するには、クライアントシークレットが必要です。

1. アプリケーションの権限を設定します。

   これらのフィールドの検索と設定について詳しくは、[Microsoft ドキュメントの「Microsoft Graphに対する権限の設定」セクション「ユーザーなしでアクセスする](https://docs.microsoft.com/en-us/graph/auth-v2-service)」を参照してください。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">アプリケーションにはどのような種類の権限が必要ですか？</td> 
      <td>「<code>Delegated permissions</code>」を選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">権限の選択</td> 
      <td> <p>次の権限を選択します。</p> 
       <ul> 
        <li> <p><code>offline_access</code> </p> </li> 
        <li> <p><code>openid</code> </p> </li> 
        <li> <p>統合に必要なその他の権限（例：<code>User.Read</code>）</p> </li> 
       </ul> <p><b>重要</b>: Workfront Fusionで接続を設定するには、選択した権限が必要です。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 引き続き[Workfront FusionでMS Graph API接続を設定](#configure-your-ms-graph-api-connection-in-workfront-fusion)します。

## Workfront FusionでのMS Graph API接続の設定

「[Workfront Application Registration PortalへのWorkfront Fusionの登録](#register-workfront-fusion-in-the-microsoft-application-registration-portal)」で説明されているようにMicrosoft Fusionを登録した後、HTTP/Oauth 2.0 リクエストモジュールを作成で接続を設定できます。

1. HTTP/OAuth 2.0 コールモジュールをシナリオに追加します。
1. 接続フィールドの横にある「**追加**」をクリックします。
1. 接続フィールドを次のように設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">接続名</td> 
      <td>接続に名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">環境</p> </td> 
      <td>実稼動用アカウントと非実稼動用アカウントのどちらに接続するかを選択します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">タイプ</p> </td> 
      <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">フロータイプ</p> </td> 
      <td>「<code>Authorization Code</code>」を選択します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">URIを認証</td> 
      <td><code>https://login.microsoftonline.com/common/oauth2/v2.0/authorize</code>と入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">トークン URI</td> 
      <td><code>https://login.microsoftonline.com/common/oauth2/v2.0/token</code>と入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">範囲</td> 
      <td> <p><a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Microsoft Application Registration PortalへのWorkfront Fusionの登録</a>で説明されているように、登録時に選択した権限を入力します。</p> <p>各スコープについて、<b>Add</b>をクリックし、権限を入力します。</p> <p>例：<code>offline_access</code>。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">スコープ区切り記号</td> 
      <td>「<code>SPACE</code>」を選択します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">クライアント ID</td> 
      <td><a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Microsoft Application Registration PortalへのWorkfront Fusionの登録</a>の手順2のアプリケーション IDを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">クライアントシークレット</td> 
      <td><a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Microsoft Application Registration PortalへのWorkfront Fusionの登録</a>の手順3で生成したクライアント秘密鍵を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">パラメーターを承認</td> 
      <td> <p>次の認証パラメーターを追加します。 追加する各パラメーターについて、「<b>項目を追加</b>」をクリックし、次の項目を入力します。 </p> 
       <ul> 
        <li> <p>キー：<code> response_mode</code>値： <code>query</code></p> </li> 
        <li> <p>キー：<code>prompt </code>値： <code>consent</code></p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">アクセストークン パラメーター</td> 
      <td>このフィールドには何も入力する必要はありません。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">トークンパラメーターの更新</td> 
      <td> 
       <ol> 
        <li value="1"> <p>「<b>項目を追加</b>」をクリックします。</p> </li> 
        <li value="2"> <p>「<b> キー</b>」フィールドに「<code>scope</code>」と入力します。</p> </li> 
        <li value="3"> <p>「<b>値</b>」フィールドに、スコープフィールドに入力したすべてのスコープをスペースで区切って入力します。</p> <p>例： <code>offline_access openid User.Read</code></p> </li> 
       </ol> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">カスタムヘッダー</td> 
      <td>このフィールドには何も入力する必要はありません。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">トークンの配置</td> 
      <td><code>In the header</code> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**続行**」をクリックします。
1. 表示されるウィンドウで、「**確定**」をクリックして接続を完了し、モジュールに戻ります。
