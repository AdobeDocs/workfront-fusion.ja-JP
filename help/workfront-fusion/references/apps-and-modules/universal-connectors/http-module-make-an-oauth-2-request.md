---
title: HTTP／OAuth 2.0 リクエストを作成モジュール
description: OAuth 2.0認証を必要とするサーバーにAdobe Workfront Fusion HTTP （S）リクエストを行うには、まずOAuth接続を作成する必要があります。 Adobe Workfront Fusionを使用すると、この接続で行われたすべての呼び出しに適切な認証ヘッダーが設定され、必要に応じて関連するトークンが自動的に更新されます。
author: Becky
feature: Workfront Fusion
exl-id: a302a1d4-fddf-4a71-adda-6b87ff7dba4b
TQID: https://experienceleague.adobe.com/ylQwzctWz1sE03eGhHWxjf48mKxHiuZVy-HN07Mtmh0
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 2371
ht-degree: 74%

---

# [!UICONTROL HTTP]／[!UICONTROL OAuth 2.0 リクエストを実行]モジュール

>[!NOTE]
>
>Adobe Workfront Fusion を使用するには、Adobe Workfront ライセンスに加えて、Adobe Workfront Fusion ライセンスが必要です。

OAuth 2.0認証を必要とするサーバーにAdobe Workfront Fusion HTTP （S）リクエストを行うには、まずOAuth接続を作成する必要があります。 Adobe Workfront Fusionを使用すると、この接続で行われたすべての呼び出しに適切な認証ヘッダーが設定され、必要に応じて関連するトークンが自動的に更新されます。

Workfront Fusionは、次のOAuth 2.0認証フローをサポートしています。

* 認証コードフロー
* 暗黙フロー

リソース所有者パスワード資格情報フローやクライアント資格情報フローなど、その他のフローは、このモジュールを通じて自動的にはサポートされません。

OAuth 2.0 認証について詳しくは、[OAuth 2.0 承認フレームワーク](https://tools.ietf.org/html/rfc6749)を参照してください。

>[!NOTE]
>
>現在、専用コネクタがないAdobe製品に接続する場合は、Adobe Authenticator モジュールを使用することをお勧めします。
>
>詳しくは、[Adobe Authenticator モジュール](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md)を参照してください。

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

## [!DNL OAuth] リクエストの接続を作成

* [HTTPで接続を作成するための一般的な手順／OAuth 2.0 リクエスト作成モジュール](#general-instructions-for-creating-a-connection-in-the-http--make-an-oauth-20-request-module)
* [http > [!UICONTROL Make] an OAuth 2.0 リクエストモジュールでGoogleへの接続を作成する手順](#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module)
* [HTTP 経由で Microsoft Graph API への接続を作成するための手順／OAuth 2.0 リクエスト作成モジュール](#instructions-for-connecting-to-microsoft-graph-api-via-the-http--make-an-oauth-20-request-module)

### [!UICONTROL HTTP] で接続を作成するための一般的な手順／[!UICONTROL OAuth 2.0 リクエスト作成]モジュール

1. Adobe Workfront Fusionと通信する[!DNL target] サービスでOAuth クライアントを作成します。 このオプションは、所定のサービスの[!UICONTROL 開発者]セクションに含まれていることが多いです。

   1. クライアントを作成する際に、適切な URL を `[!UICONTROL Redirect URL]` または `[!UICONTROL Callback URL]` フィールドに入力します：

      | 南北アメリカ／APAC | `https://app.workfrontfusion.com/oauth/cb/oauth2` |
      |---|---|
      | **EMEA** | `https://app-eu.workfrontfusion.com/oauth/cb/oauth2` |

   1. クライアントを作成すると、指定されたサービスは次の 2 つのキー（`[!UICONTROL Client ID]` と `[!UICONTROL Client Secret]`）が表示されます。 一部のサービスでは、これらを`[!UICONTROL App Key]`および`[!UICONTROL App Secret]`と呼んでいます。 キーと秘密鍵を安全な場所に保存して、Workfront Fusion で接続を作成する際に指定できるようにします。

1. `[!UICONTROL Authorize URI]` および `[!UICONTROL Token URI]` を特定のサービスの API ドキュメント内で探します。 これらは、Workfront Fusionが[!DNL target] サービスと通信するURL アドレスです。 アドレスは OAuth 認証に使用されます。

   >[!NOTE]
   >
   >サービスで暗黙的なフローを使用する場合、`[!UICONTROL Authorize URI]` のみが必要です。

1. （条件付き）ターゲットサービスでスコープ（アクセス権）を使用する場合、サービスで個々のスコープがどのように区切られるかを確認し、それに応じて詳細設定で区切り記号を設定してください。 区切り記号が正しく設定されていない場合、Workfront Fusionは接続の作成に失敗し、無効なスコープエラーが表示されます。
1. 上記の手順を完了したら、Workfront FusionでOAuth接続の作成を開始できます。 HTTP/OAuth 2 リクエストモジュールをシナリオに追加します。
1. モジュールの「接続」フィールドで、「**[!UICONTROL 追加]**」をクリックします。

1. 次のフィールドに入力して、接続を作成します。

   <table style="table-layout:auto">  
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name] </td> 
      <td> <p>接続の名前を入力します。</p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Environment] </td> 
      <td> <p>実稼動環境と非実稼動環境のどちらを使用するかを選択します。</p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Type] </td> 
      <td> <p>サービスアカウントと個人アカウントのどちらを使用しているかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Flow type]</p> </td> 
      <td> <p>トークンを取得するフローを選択します。</p> 
       <ul> 
        <li><strong>[!UICONTROL Authorization Code]</strong>：サービスの API ドキュメントにある <code>[!UICONTROL Authorize URI]</code> と <code>[!UICONTROL Token URI]</code> を入力します。</li> 
        <li><strong>[!UICONTROL Implicit]</strong>：サービスの API ドキュメントにある <code>[!UICONTROL Authorize URI]</code> を入力してください。</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope] </td> 
      <td> <p>個々のスコープを追加します。 この情報は、特定のサービスの開発者向けドキュメント（API）に記載されています。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope separator] </td> 
      <td> <p>上記で入力したスコープを区切る範囲を選択します。 この情報は、特定のサービスの開発者向けドキュメント（API）に記載されています。</p> <p>警告：区切り記号が正しく設定されていない場合、Workfront Fusionは接続の作成に失敗し、無効なスコープエラーが表示されます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client ID] </td> 
      <td> <p>クライアント ID を入力します。 クライアント ID は、接続するサービスで OAuth クライアントを作成したときに取得されました。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td> <p> クライアントの秘密鍵を入力します。 接続するサービスで OAuth クライアントを作成したときに、クライアントシークレットを取得しました。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Authorize parameters]</p> </td> 
      <td> <p>認証呼び出しに含めるパラメーターを追加します。 次の標準パラメーターは常に自動的に含まれるため、追加する必要はありません。</p> <p>標準パラメーター：</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL response_type]</strong> </p> <p> [!UICONTROL Authorization Code flow] 用の <code>code </code> および [!UICONTROL Implicit flow] 用の <code>token </code> の場合</p> </li> 
        <li> <p><strong>[!UICONTROL redirect_uri]</strong> </p> 
         <table style="table-layout:auto">  
          <col> 
          <col> 
          <tbody> 
           <tr> 
            <td role="rowheader">南北アメリカ／APAC</td> 
            <td>https://app.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
           <tr> 
            <td role="rowheader">EMEA </td> 
            <td>https://app-eu.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
          </tbody> 
         </table> </li> 
        <li> <p><strong>[!UICONTROL client_id]</strong> </p> <p> アカウントの作成時に受け取ったクライアント ID</p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Access token parameters]</p> </td> 
      <td> <p>トークン呼び出しに含めるパラメーターを追加します。 次の標準パラメーターは常に自動的に含まれるため、追加する必要はありません。</p> <p>標準パラメーター：</p> 
       <ul> 
        <li><strong>[!UICONTROL grant_type]</strong>： <code>authorization_code</code></li> 
        <li> <p><strong>[!UICONTROL redirect_uri]：</strong> </p> 
         <table style="table-layout:auto">  
          <col> 
          <col> 
          <tbody> 
           <tr> 
            <td role="rowheader">南北アメリカ／APAC</td> 
            <td>https://app.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
           <tr> 
            <td role="rowheader">EMEA </td> 
            <td>https://app-eu.workfrontfusion.com/oauth/cb/oauth2</td> 
           </tr> 
          </tbody> 
         </table> </li> 
        <li><strong>[!UICONTROL client_id]</strong>：アカウントの作成時に受け取ったクライアント ID は、リクエスト本文に自動的に含まれます</li> 
        <li><strong>client_secret</strong>：アカウントの作成時に受け取ったクライアントシークレットが、リクエスト本文に自動的に含まれます</li> 
        <li><strong>コード</strong>：認証リクエストによって返されるコード</li> 
       </ul> <p>メモ：  <p>OAuth 2.0 標準は、この手順で少なくとも 2 つのクライアント認証方法（<code>[!UICONTROL client_secret_basic]</code> および <code>[!UICONTROL client_secret_post]</code>）をサポートします。 Workfront Fusionは、指定されたクライアント IDとシークレットを<code>[!UICONTROL client_secret_post]</code> メソッドを通じて自動的に送信します。 したがって、これらのパラメーターは、トークンのリクエスト本文に自動的に含まれます。 </p> <p>OAuth 2.0 認証について詳しくは、<a href="https://tools.ietf.org/html/rfc6749">OAuth 2.0 承認フレームワーク</a>を参照してください。</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Refresh token parameters]</p> </td> 
      <td> <p>トークン呼び出しに含めるパラメーターを追加します。 次の標準パラメーターは常に自動的に含まれるため、追加する必要はありません。</p> <p>標準パラメーター：</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL grant_type]</strong>： <code>refresh_token</code></p> </li> 
        <li> <p><strong>[!UICONTROL refresh_token]</strong>：接続しているサービスで取得された最新の更新トークン。</p> </li> 
        <li> <p><strong>[!UICONTROL client_id]</strong>：アカウントの作成時に受け取ったクライアント ID は、リクエスト本文に自動的に含まれます</p> </li> 
        <li> <p><strong>[!UICONTROL client_secret]</strong>：アカウントの作成時に受け取ったクライアント秘密鍵は、リクエスト本文に自動的に含まれます</p> </li> 
       </ul> <p>メモ：  <p>OAuth 2.0 標準は、この手順で少なくとも 2 つのクライアント認証方法（<code>[!UICONTROL client_secret_basic]</code> および <code>[!UICONTROL client_secret_post]</code>）をサポートします。 Workfront Fusionは、指定されたクライアント IDとシークレットを<code>[!UICONTROL client_secret_post]</code> メソッドを通じて自動的に送信します。 したがって、これらのパラメーターは、トークンのリクエスト本文に自動的に含まれます。 </p> <p>OAuth 2.0 認証について詳しくは、<a href="https://tools.ietf.org/html/rfc6749">OAuth 2.0 承認フレームワーク</a>を参照してください。</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Custom Headers]</p> </td> 
      <td> <p>[!UICONTROL Token] および R[!UICONTROL efresh Token] の手順のヘッダーに含める追加のキーと値を指定します。</p> <p>メモ：  <p>OAuth 2.0 標準は、この手順で少なくとも 2 つのクライアント認証方法（<code>[!UICONTROL client_secret_basic]</code> および <code>[!UICONTROL client_secret_post]</code>）をサポートします。 Workfront Fusionは、<code>[!UICONTROL client_secret_basic]</code> メソッドを自動的にサポートしません。 接続しているサービスで、クライアント ID とクライアント秘密鍵が 1 つの文字列に結合され、Authorization ヘッダーに base64 がエンコードされると想定される場合は、そのヘッダーとキーの値をここに追加する必要があります。</p> <p> OAuth 2.0 認証について詳しくは、<a href="https://tools.ietf.org/html/rfc6749">OAuth 2.0 認証フレームワーク</a>を参照してください。</p> </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Token placement]</p> </td> 
      <td> <p>指定した URL に接続する際に、[!UICONTROL header]、[!UICONTROL query string]、またはその両方でトークンを送信するかどうかを選択します。</p> <p>トークンは、最も一般的にリクエストヘッダーで送信されます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Header token name] </td> 
      <td> <p>ヘッダーに認証トークンの名前を入力します。 デフォルト：<code>[!UICONTROL Bearer]</code>。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Query string parameter name] </td> 
      <td> <p>クエリ文字列に認証トークンの名前を入力します。 デフォルト：<code>[!UICONTROL access_token]</code>。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。
1. 引き続き[OAuth 2.0 リクエストモジュールの作成](#configure-the-make-an-oauth-20-request-module)を設定します。

### [!UICONTROL HTTP] > [!UICONTROL で[!DNL Google]への接続を作成するための手順OAuth 2.0 リクエストモジュールを作成する]

次の例は、[!UICONTROL HTTP]／[!UICONTROL OAuth 2.0 実行]リクエストモジュールを使用して [!DNL Google] に接続する方法を示しています。

1. カスタム OAuth クライアント ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)を使用してAdobe Workfront Fusionを [!DNL Google Services] に接続する[の記事に記載されているように、プロジェクトを作成し、OAuth設定を設定し、資格情報を生成していることを確認します。
1. [!UICONTROL HTTP] > [!UICONTROL OAuth 2.0 リクエスト ] モジュールを開きます。
1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。
1. 次の値を入力します。

   <table style="table-layout:auto">  
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name] </td> 
      <td> <p>接続に名前を入力します。</p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Environment] </td> 
      <td> <p>実稼動環境と非実稼動環境のどちらを使用するかを選択します。</p> </td> 
     </tr> 
      <tr> 
      <td role="rowheader">[!UICONTROL Type] </td> 
      <td> <p>サービスアカウントと個人アカウントのどちらを使用しているかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Flow type]</p> </td> 
      <td> <p>[!UICONTROL Authorization Code]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Authorize URI]</td> 
      <td><code>https://accounts.google.com/o/oauth2/v2/auth</code> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Token URI]</td> 
      <td><code>https://www.googleapis.com/oauth2/v4/token</code> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope] </td> 
      <td> <p>個々のスコープを追加します。 スコープについて詳しくは、[!DNL Google] ドキュメントにある<a href="https://developers.google.com/identity/protocols/oauth2/scopes"> [!DNL Google] API</a>向け OAuth 2.0 スコープを参照してください。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Scope separator] </td> 
      <td> <p>[!UICONTROL SPACE]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client ID] </td> 
      <td> <p>[!DNL Google] クライアント ID を入力します。 </p> <p>クライアント IDを作成するには、カスタム OAuth クライアント </a>を使用して記事[!DNL Connect Adobe Workfront Fusion]から[!DNL Google Services]の「<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md#create-oauth-credentials" class="MCXref xref">OAuth資格情報を作成</a>」を参照してください。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td> <p>[!DNL Google] クライアント秘密鍵を入力します。 </p> <p>クライアント秘密鍵を作成するには、カスタム OAuth クライアント </a>を使用して記事[!DNL Connect Adobe Workfront Fusion]から[!DNL Google] サービスの<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md#create-oauth-credentials" class="MCXref xref">OAuth資格情報を作成</a>を参照してください。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Authorize parameters]</p> </td> 
      <td> <p><code>[!UICONTROL access_type]</code> - <code>[!UICONTROL offline] </code> キーと値のペアを追加します。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/google-authentication-http.png"> </p> <p>メモ：トークンの更新など、認証に関する問題が発生した場合は、<code>[!UICONTROL prompt] </code>- <code>[!UICONTROL consent] </code> キーと値のペアを試してください。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続設定を保存します。
1. 引き続き[OAuth 2.0 リクエストモジュールの作成](#configure-the-make-an-oauth-20-request-module)を設定します。

## OAuth 2.0 リクエストモジュールの設定

OAuth 2.0接続を確立したら、必要に応じてモジュールの設定を続行します。 すべての認証トークンは、このリクエストと、同じ接続を使用する他のリクエストに自動的に含まれます。

[!UICONTROL HTTP] > [!UICONTROL OAuth 2.0 リクエストを作成] モジュールを設定すると、Workfront Fusionに次のフィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[Adobe Workfront Fusion でのモジュール間の情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto">  
 <col> 
 <col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>接続の設定について詳しくは、この記事の「<a href="#create-a-connection-for-an-oauth-request" class="MCXref xref">OAuth リクエストの接続を作成する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx)] </td> 
   <td> <p>エラー処理を設定するには、このオプションを使用します。</p> <p>詳しくは、<a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref"> エラー処理</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>API エンドポイント、ウェブサイトなど、リクエストの送信先 URL を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。 例： <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> 目的のクエリのキーと値のペアを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Body type]</p> </td> 
   <td> <p>HTTP 本文は、使用するヘッダーがある場合、そのヘッダーの直後に HTTP トランザクションメッセージで送信されるデータバイトです。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p>Raw 本文タイプは、開発者向けドキュメントで送信するデータが指定されていない場合でも、通常、ほとんどの HTTP 本文リクエストに適しています。</p> <p>データを解析する形式を [!UICONTROL Content type] フィールドに指定します。</p> <p>選択したコンテンツタイプに関係なく、データは開発者ドキュメントで規定または必須されている形式で入力されます。</p> </li> 
     <li> <p><strong>[!UICONTROL Application/x-www-form-urlencoded]</strong> </p> <p>この本文タイプは、<code>[!UICONTROL application/x-www-form-urlencoded]</code> を使用したデータの投稿です。</p> <p><code>[!UICONTROL application/x-www-form-urlencoded]</code> の場合、サーバーに送信される HTTP メッセージの本文は基本的に 1 つのクエリ文字列になります。 キーと値はキーと値のペアでエンコードされます。ペア同士は <code>&amp;</code> で区切られ、各ペアのキーと値の間には <code>=</code> が入ります。 </p> <p>バイナリデータの場合は、代わりに <code>use [!UICONTROL multipart/form-data]</code>。</p> 
      <div class="example" data-mc-autonum="<b>Example: </b>">
       <span class="autonumber"><span><b>例：</b></span></span> 
       <p>結果の HTTP リクエスト形式の例は、次のようになります。</p> 
       <p><code>field1=value1&amp;field2=value2</code> </p> 
      </div> </li> 
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>[!UICONTROL Multipart/form-data] は、ファイルとデータの送信に使用される HTTP マルチパートリクエストです。 通常、ファイルをサーバーにアップロードする際に使用されます。</p> <p>リクエストで送信するフィールドを追加します。 各フィールドには、キーと値のペアが含まれている必要があります。</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>リクエスト本文内で送信するキーと値を入力します。</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>キーを入力し、リクエスト本文で送信するソースファイルを指定します。</p> <p>前のモジュール（[!UICONTROL HTTP] &gt; [!UICONTROL Get a File]など）からアップロードするファイルをマッピングするか、ファイル名とファイルデータを手動で入力します。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>このオプションを有効にすると、応答を自動的に解析し、JSON および XML 応答を変換するので、[!UICONTROL JSON]／[!UICONTROL Parse JSON] または [!UICONTROL XML]／[!UICONTROL Parse XML] モジュールを使用する必要がなくなります。</p> <p>解析された JSON または XML コンテンツを使用する前に、モジュールを手動で 1 回実行して、モジュールが応答コンテンツを認識し、後続のモジュールにマッピングできるようにします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>リクエストのタイムアウトを秒単位で入力します（1～300）。 デフォルトは 40 秒です。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> このオプションを有効にすると、シナリオ内のすべての HTTP モジュールとサーバーから Cookie を共有できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p>自己署名証明書または秘密鍵をTLSに使用するには、<b>Extract</b>をクリックし、証明書または秘密鍵のファイルとパスワードを指定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reject connections that are using unverified (self-signed) certificates] </td> 
   <td> <p>このオプションを有効にすると、未検証の TLS 証明書を使用している接続を拒否できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow redirect]</td> 
   <td> <p> このオプションを有効にすると、3xx 応答で URL リダイレクトに従います。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow all redirects] </td> 
   <td> <p>このオプションを有効にすると、すべての応答コードで URL リダイレクトに従います。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Disable serialization of multiple same query string keys as arrays]</p> </td> 
   <td> <p>デフォルトでは、Workfront Fusionは、同じURL クエリ文字列パラメーターキーの複数の値を配列として処理します。 例えば、<code>www.test.com?foo=bar&amp;foo=baz</code> が <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code> に変換されます。 このオプションをアクティブ化すると、この機能は無効になります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request compressed content]</td> 
   <td> <p> このオプションを有効にすると、web サイトの圧縮バージョンを要求できます。</p> <p>これにより、圧縮コンテンツを要求する <code>[!UICONTROL Accept-Encoding]</code> ヘッダーが追加されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>このオプションを有効にすると、HTTP リクエストで相互 TLS を使用できます。</p> <p>相互TLSについて詳しくは、<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">Adobe Workfront FusionでのHTTP モジュールでの相互TLSの使用</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>
