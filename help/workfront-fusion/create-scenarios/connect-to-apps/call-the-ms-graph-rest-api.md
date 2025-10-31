---
title: Ms Graph REST API の呼び出し
description: Adobe Workfront Fusion HTTP を介した MS Graph REST API の呼び出し&> OAuth 2.0 リクエストモジュールの作成
author: Becky
feature: Workfront Fusion
exl-id: f411c807-955d-44fe-98b1-3ebba3fe0861
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 17%

---

# Ms Graph REST API の呼び出し

多くのMicrosoft web サービスには、Microsoft Graph API を使用してアクセスします。 「Workfront Fusion HTTP」、「OAuth 2.0 リクエストを行う」モジュールを使用して、Microsoft Graph API への接続を作成できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Workfront Fusion をMicrosoft アプリケーション登録ポータルに登録します。

Adobe Workfront Graph REST API への接続を作成するには、まずMicrosoft Fusion を登録する必要があります。

1. Microsoft ドキュメントの [Microsoft ID プラットフォームへのアプリケーションの登録 &#x200B;](https://docs.microsoft.com/en-us/graph/auth-register-app-v2) の説明に従って、新しいアプリケーションの登録を開始します。

   登録の一環として、Microsoftでは次の情報が必要です。

   <table style="table-layout:auto">
      <tr>
        <td>アプリケーション名</td>
        <td>「My Workfront Fusion application」のように、アプリケーションの名前を入力します。</td>
      </tr>
      <tr>
        <td>リダイレクト URL</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/oauth2</code></td>
      </tr>
    </table>

1. アプリの登録が完了したら、アプリケーション ID をメモします。

   >[!IMPORTANT]
   >
   >Workfront Fusion で接続を設定するには、アプリケーション ID が必要です。

1. クライアントシークレットを生成します。 このシークレットをメモしておいてください。

   手順については、Microsoft ドキュメントの [Microsoft ID プラットフォームへのアプリケーションの登録 &#x200B;](https://docs.microsoft.com/en-us/graph/auth-register-app-v2) を参照してください。

   >[!IMPORTANT]
   >
   >Workfront Fusion で接続を設定するには、クライアントシークレットが必要です。

1. アプリケーションの権限を設定します。

   これらのフィールドの検索と設定について詳しくは、Microsoft ドキュメントの [&#x200B; ユーザーなしでアクセスする &#x200B;](https://docs.microsoft.com/en-us/graph/auth-v2-service) の「Microsoft グラフの権限の設定」の節を参照してください。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">アプリケーションで必要な権限のタイプは何ですか？</td> 
      <td>「<code>Delegated permissions</code>」を選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">権限を選択</td> 
      <td> <p>次の権限を選択します。</p> 
       <ul> 
        <li> <p><code>offline_access</code> </p> </li> 
        <li> <p><code>openid</code> </p> </li> 
        <li> <p>統合に必要なその他の権限（例：<code>User.Read</code>）</p> </li> 
       </ul> <p><b> 重要 </b>:Workfront Fusion で接続を設定するには、選択した権限が必要です。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 続けて [Workfront Fusion での MS Graph API 接続の設定 &#x200B;](#configure-your-ms-graph-api-connection-in-workfront-fusion) を行います。

## Workfront Fusion での MS Graph API 接続の設定

[Workfront Application Registration Portal でのWorkfront Fusion の登録 &#x200B;](#register-workfront-fusion-in-the-microsoft-application-registration-portal) の説明に従ってMicrosoft Fusion を登録したら、HTTP / Make an Oauth 2.0 request モジュールで接続を設定できます。

1. HTTP を追加し、シナリオに OAuth 2.0 呼び出しを行うモジュールを作成します。
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
      <td>実稼動アカウントに接続するか、実稼動以外のアカウントに接続するかを選択します。 </td> 
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
      <td role="rowheader">URI を許可</td> 
      <td><code>https://login.microsoftonline.com/common/oauth2/v2.0/authorize</code> と入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">トークン URI</td> 
      <td><code>https://login.microsoftonline.com/common/oauth2/v2.0/token</code> と入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">範囲</td> 
      <td> <p><a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Microsoft Application Registration Portal でのWorkfront Fusion の登録 </a> の説明に従って、登録時に選択した権限を入力します。</p> <p>各範囲について、「<b> 追加 </b>」をクリックし、権限を入力します。</p> <p>例：<code>offline_access</code>。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">スコープ区切り記号</td> 
      <td>「<code>SPACE</code>」を選択します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">クライアント ID</td> 
      <td><a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Microsoft Application Registration Portal でのWorkfront Fusion の登録 </a> の手順 2 で示したアプリケーション ID を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">クライアントシークレット</td> 
      <td><a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Microsoft Application Registration Portal でのWorkfront Fusion の登録 </a> の手順 3 で生成したクライアント秘密鍵を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">パラメーターを許可</td> 
      <td> <p>次の認証パラメーターを追加します。 追加するパラメーターごとに、「<b> 項目を追加 </b>」をクリックして以下を入力します。 </p> 
       <ul> 
        <li> <p>キー：<code> response_mode</code> 値： <code>query</code></p> </li> 
        <li> <p>キー：<code>prompt </code> 値： <code>consent</code></p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">アクセストークンのパラメーター</td> 
      <td>このフィールドには何も入力する必要はありません。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">更新トークンパラメーター</td> 
      <td> 
       <ol> 
        <li value="1"> <p><b> 項目を追加 </b> をクリックします。</p> </li> 
        <li value="2"> <p>「<b> キー </b>」フィールドに「<code>scope</code>」と入力します。</p> </li> 
        <li value="3"> <p>「<b> 値 </b>」フィールドに、範囲フィールドに入力したすべての範囲をスペースで区切って入力します。</p> <p>例： <code>offline_access openid User.Read</code></p> </li> 
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
