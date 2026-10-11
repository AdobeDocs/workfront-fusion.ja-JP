---
title: HTTP > JWT リクエストモジュールを作成
description: Adobe Workfront Fusion HTTP > Make a JWT リクエストモジュールは、HTTP （S） リクエストをURLに送信し、Fusionが自動的に署名するJSON Web トークンで認証します。
author: Becky
feature: Workfront Fusion
exl-id: 2f8c0b0d-085a-4b49-b350-4fd4cca1d0a7
TQID: 'https://experienceleague.adobe.com/'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5e6403abee4e5767da9134529b9e88070bad5f44
workflow-type: tm+mt
source-wordcount: '1437'
ht-degree: 20%
---
# [!UICONTROL HTTP] > [!UICONTROL JWT リクエストを作成] モジュール

Adobe Workfront Fusion [!UICONTROL HTTP] > [!UICONTROL JWT リクエストを作成] モジュールは、HTTP （S） リクエストをURLに送信し、すべての呼び出しでモジュールが署名するJSON Web Token （JWT）を使用して認証します。 その後、応答は、標準の[!UICONTROL HTTP] > [!UICONTROL &#x200B; リクエストを作成] モジュールと同じように処理されます。

このモジュールは、標準の[!UICONTROL &#x200B; リクエストを作成] モジュールと同様に動作します。主な違いは、提供したクレームからJWTに自動的に署名し、デフォルトで`Authorization: Bearer <token>`としてリクエストに追加することです。

このモジュールを使用すると、別の手順でトークンを作成することなく、共有秘密（HMAC）または秘密鍵（RSA/ECDSA）で署名された短期間有効なベアラートークンを必要とするサービスなど、認証のために署名されたJWTを必要とするAPIを呼び出すことができます。

APIでOAuth 2.0、基本認証、API キー、またはクライアント証明書を使用する場合は、代わりに一致する専用のHTTP モジュールを使用します。

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
   <p>オペレーションベース：オペレーションベースのライセンスを持つ組織で使用できます</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## JWT接続の作成

モジュールにはJWT接続が必要です。 接続は、署名マテリアルを保存して、シークレット キーまたは秘密キーがシナリオに表示されないようにします。

### FusionでのJWT接続の作成

1. シナリオに[!UICONTROL HTTP] > [!UICONTROL JWT リクエスト &#x200B;] モジュールを追加します。
1. 「**[!UICONTROL 接続]**」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 接続フィールドを設定します。

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader"><p>接続名</p></td>
      <td><p>接続に名前を入力します。</p></td>
     </tr>
     <tr>
      <td role="rowheader"><p>アルゴリズム</p></td>
      <td>
       <p>接続の署名アルゴリズムを選択します。</p>
       <ul>
        <li><code>HS256</code></li>
        <li><code>HS384</code></li>
        <li><code>HS512</code></li>
        <li><code>RS256</code></li>
        <li><code>RS384</code></li>
        <li><code>RS512</code></li>
        <li><code>PS256</code></li>
        <li><code>PS384</code></li>
        <li><code>PS512</code></li>
        <li><code>ES256</code></li>
        <li><code>ES384</code></li>
        <li><code>ES512</code></li>
       </ul>
      </td>
     </tr>
     <tr>
      <td role="rowheader"><p>秘密鍵</p></td>
      <td>
       <p>署名キーを入力します。</p>
       <ul>
        <li><code>HS*</code> アルゴリズムの場合は、共有秘密文字列を使用します。</li>
        <li><code>RS*</code>、<code>PS*</code>および<code>ES*</code> アルゴリズムの場合は、PEM エンコードされた秘密鍵を使用します。</li>
       </ul>
      </td>
     </tr>
    </tbody>
   </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を作成し、モジュールに戻ります。

>[!IMPORTANT]
>
>JWT接続は、1つのアルゴリズムのみで署名します。 シナリオで複数の署名アルゴリズムが必要な場合は、各アルゴリズムに個別の接続を作成します。 これは、既存のスタンドアロン JWT アプリの動作と一致します。

## [!UICONTROL HTTP] > [!UICONTROL JWT リクエスト &#x200B;] モジュールとそのフィールドを作成する

[!UICONTROL HTTP] > [!UICONTROL JWT リクエスト &#x200B;] モジュールを設定すると、Adobe Workfront Fusionは、モジュール UIに表示されるのと同じ順序で、以下に示すフィールドを表示します。 モジュール内の太字のタイトルは、必須フィールドを示します。 詳細設定としてマークされたフィールドは、**[!UICONTROL 詳細設定を表示]**&#x200B;を選択しない限り非表示になります。

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Connection]</p></td>
   <td><p>既存のJWT接続を選択するか、新しいJWT接続を作成します。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL URL]</p></td>
   <td><p>リクエストのターゲット URL。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Method]</p></td>
   <td><p>GET、POST、PUT、PATCH、DELETEなどのHTTP メソッド。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Headers]</p></td>
   <td><p>キー/値形式のカスタムリクエストヘッダー。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Query String]</p></td>
   <td><p>キー/値形式のクエリ文字列パラメーター。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Body type]</p></td>
   <td><p>リクエスト本文のエンコード方法。 オプションには、Raw、application/x-www-form-urlencoded、multipart/form-dataなどがあります。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Parse response]</p></td>
   <td><p>有効にすると、Fusionは応答コンテンツタイプに基づいて応答本文を解析します。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL JWT ペイロード （クレーム） &#x200B;]</p></td>
   <td><p>JWT ペイロードにクレームとして含まれるキー/値のペア。 予約された要求<code>exp</code>、<code>iat</code>および<code>nbf</code>は、NumericDate （Unixのエポックからの秒数）である必要があります。 要求の値はJSON タイプを保持するので、数値は数値のままになり、ブール値はブール値のままになります。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL タイムアウト &#x200B;] （詳細）</p></td>
   <td><p>リクエストのタイムアウトを秒単位で指定します（1～300）。 デフォルトは 40 秒です。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 再試行回数] （詳細）</p></td>
   <td><p>再試行可能なエラーが原因でリクエストが失敗した場合に、リクエストを再試行する回数を指定します。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Additional Retry Status Codes] （advanced）</p></td>
   <td><p>再試行可能として扱うHTTP ステータスコードを追加で指定します。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Share cookie with other HTTP modules] （advanced）</p></td>
   <td><p>このオプションを有効にすると、シナリオ内のすべての HTTP モジュールとサーバーから Cookie を共有できます。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 自己署名証明書] （詳細）</p></td>
   <td><p>自己署名証明書を使用してTLSを使用する場合は、証明書をアップロードします。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Reject connections that are using unverified （self-signed） certificates] （advanced）</p></td>
   <td><p>このオプションを有効にすると、未検証の TLS 証明書を使用している接続を拒否できます。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Follow redirect] （advanced）</p></td>
   <td><p>このオプションを有効にすると、3xx 応答で URL リダイレクトに従います。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 複数の同じクエリ文字列キーのシリアル化を配列として無効にする] （詳細）</p></td>
   <td><p>デフォルトでは、Workfront Fusionは、同じURL クエリ文字列パラメーターキーの複数の値を配列として処理します。 例えば、<code>www.test.com?foo=bar&amp;foo=baz</code> が <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code> に変換されます。 このオプションをアクティブ化すると、この機能は無効になります。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Request compressed content] （advanced）</p></td>
   <td><p>このオプションを有効にすると、web サイトの圧縮バージョンを要求できます。 圧縮コンテンツをリクエストするヘッダーに、<code>[!UICONTROL Accept-Encoding]</code> を追加します。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Use Mutual TLS] （advanced）</p></td>
   <td><p>このオプションを有効にすると、HTTP リクエストで相互 TLS を使用できます。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL Sign Options] （詳細）</p></td>
   <td><p>リクエストに追加する各サインオプションについて、<b>項目を追加</b>をクリックし、パラメーターの名前と値を入力します。</p><p>JWT署名者に渡された追加オプション（<code>expiresIn</code>、<code>issuer</code>、<code>audience</code>、<code>subject</code>、<code>keyid</code>など）。 <code>expiresIn</code>などの期間の値は、<code>jsonwebtoken</code> ライブラリによって解釈されます。 プレーン数はミリ秒単位で扱われるので、<code>"1h"</code>や<code>"3600s"</code>などの単位文字列を使用して明示的に指定します。 アルゴリズムは接続から取得され、ここで上書きすることはできません。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL ヘッダー名] （詳細）</p></td>
   <td><p>署名済みJWTを受け取るリクエストヘッダーの名前を入力またはマッピングします。 デフォルト：<code>Authorization</code>。 ヘッダー名にドット （<code>.</code>）を含めることはできません。これは、点線の名前が拒否され、リクエストログでマスクできないためです。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL トークンタイプ &#x200B;] （詳細）</p></td>
   <td><p>トークンの前に配置された認証スキーム（<code>Bearer</code>など）を入力するか、マッピングします。 接頭辞なしで生のトークンを送信するには、この空白のままにします。</p></td>
  </tr>
 </tbody>
</table>

## トークンの構築方法

1. モジュールは、[!UICONTROL JWT ペイロード （要求） &#x200B;] フィールドで要求を収集します。
1. <code>expなどの予約済み要求</code>, <code>iat</code>、および<code>nbf</code> NumericDate値に変換されます。
1. モジュールは[!UICONTROL 署名オプション &#x200B;]を適用し、接続のアルゴリズムを使用してトークンに署名します。
1. 署名済みトークンは、[!UICONTROL &#x200B; ヘッダー名]によって定義されたリクエストヘッダーに配置されます。
1. [!UICONTROL &#x200B; トークンタイプ &#x200B;]が設定されている場合、モジュールはトークンの前にプレフィックスを追加します。 例えば、<code>Bearer eyJ...</code>.
1. リクエストが送信され、応答は標準の[!UICONTROL HTTP] > [!UICONTROL &#x200B; リクエストを作成] モジュールと同じように処理されます。

署名されたトークンは、デバッグログとエラーログで自動的にマスクされるので、公開されることはありません。

## 例

### 接続

- アルゴリズム：`HS256`
- 秘密鍵：`my-shared-secret`

### モジュール設定

- URL：`https://api.example.com/v1/orders`
- メソッド：`GET`
- JWT ペイロード（クレーム）:
  - `sub` = `service-account-42`
  - `iss` = `make-integration`
- 署名オプション：
  - `expiresIn` = `1h`
- ヘッダー名：`Authorization`
- トークンタイプ：`Bearer`

### 結果

モジュールは、次のようなヘッダーでリクエストを送信します。

```text
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

## FAQ/gotchas

### トークンの有効期限が短いのはなぜですか？

`3600`など、`expiresIn`の番号を入力した可能性があります。 `jsonwebtoken` ライブラリは、平易な数値をミリ秒単位で解釈します。 代わりに、`"1h"`や`"3600s"`などの単位文字列を使用してください。

### トークンはいつ作成されますか？

モジュールは、接続の作成時ではなく、モジュールが実行されるたびに新しいJWTに署名します。 接続には署名マテリアルとアルゴリズムのみが保存されるため、`iat`や`exp`などのクレームは、そのモジュール実行の瞬間を反映しています。

リクエストが同じモジュール実行内で再試行された場合、Fusionは、各試行に対して新しいトークンに署名するのではなく、それらの再試行に対して同じ署名済みトークンを再利用します。 このため、非常に短い`expiresIn`値は、再試行が発生する前に期限切れになり、既に期限切れのトークンを再試行して送信する可能性があります。 これを回避するには、`"1h"`や`"3600s"`などの明確な単位文字列を使用し、トークンの有効期間が短くなりすぎないようにします。

### リクエストごとにアルゴリズムを変更できますか？

いいえ。 アルゴリズムは接続によって固定されます。 別のアルゴリズムが必要な場合は、別のJWT接続を作成します。

### カスタムヘッダーでトークンを送信できますか？

はい。 [!UICONTROL &#x200B; ヘッダー名] フィールドをカスタム名に設定しますが、ドット （`.`）を含めることはできません。

### `Bearer`なしで生のトークンを送信できますか？

はい。 [!UICONTROL &#x200B; トークンタイプ &#x200B;]を空のままにします。

### トークンはログに表示されますか？

いいえ。 署名されたトークンは、デバッグログとエラーログで自動的にマスクされます。


>[!NOTE]
>
>テクニカルノート：署名は`jsonwebtoken` ライブラリを使用し、スタンドアロン JWT アプリの署名動作を反映するため、同じ入力でスタンドアロン JWT アプリと同じトークンが生成されます。
