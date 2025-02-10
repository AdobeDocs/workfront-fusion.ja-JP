---
title: HTTP／API キー認証リクエストを作成
description: この  [!DNL Adobe Workfront Fusion]  アクションモジュールは、API キー認証を必要とする指定された URL に HTTPS リクエストを送信し、応答を処理します。
author: Becky
feature: Workfront Fusion
exl-id: 362b80b5-42f4-4b82-b06c-39c7c5a1eb1a
source-git-commit: 1a42567e93b4fae67c92720b7642186919e4c93d
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 72%

---

# HTTP > [!UICONTROL Make an API Key Authorization request]

この [!DNL Adobe Workfront Fusion] アクションモジュールは、API キー認証を必要とする指定された URL に HTTPS リクエストを送信し、応答を処理します。

>[!NOTE]
>
>現在専用コネクタがないAdobe製品に接続する場合は、Adobe Authenticator モジュールを使用することをお勧めします。
>
>詳しくは、[Adobe Authenticator モジュール](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md)を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## [!UICONTROL HTTP]/[!UICONTROL Make an API Key Authorization request] モジュール設定

[!UICONTROL HTTP]/[!UICONTROL Make an API Key Authorization request] モジュールを設定すると、以下に示 [!DNL Adobe Workfront Fusion] フィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) でモジュールから別のモジュールに情報をマッピングを参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Credentials]</td> 
   <td> <p>API キー認証資格情報を含むキーを選択します。新しいキーを追加するには、「<strong>[!UICONTROL Add]</strong>」をクリックして次の情報を設定します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key name]</strong></p> <p>この API 資格情報セットの名前を入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>API キーを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL API Key placement]</strong> </p> <p>API キーをヘッダーに配置するか、API 呼び出しのクエリに配置するかを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL API Key parameter name]</strong> </p> <p>API 呼び出しで API キーを識別する名前（「apiKey」や「X-API-Key」など）を入力します。この情報は、モジュールが接続する web サービスのドキュメントに記載されています。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx)] </td> 
   <td> <p>エラー処理を設定するには、このオプションを使用します。</p> <p>詳しくは、「<a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref"> エラー処理 </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>API エンドポイント、ウェブサイトなど、リクエストの送信先 URL を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例： <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> 目的のクエリのキーと値のペアを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Body type]</p> </td> 
   <td> <p>HTTP 本文は、使用するヘッダーがある場合、そのヘッダーの直後に HTTP トランザクションメッセージで送信されるデータバイトです。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p>Raw 本文タイプは、開発者向けドキュメントで送信するデータが指定されていない場合でも、通常、ほとんどの HTTP 本文リクエストに適しています。</p> <p>[!UICONTROL Content type] フィールドでデータ解析の形式を指定します。</p> <p>選択したコンテンツタイプにもかかわらず、モジュールは開発者ドキュメントで規定されているか必要とされている任意の形式でデータを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Application/x-www-form-urlencoded]</strong> </p> <p>このボディタイプは、<code>application/x-www-form-urlencoded</code> を使用してデータを [!UICONTROL POST] します。</p> <p><code>[!UICONTROL application/x-www-form-urlencoded]</code> の場合、サーバーに送信される HTTP メッセージの本文は基本的に 1 つのクエリ文字列になります。キーと値は、<code>&amp;</code> で区切られ、キーと値の間に <code>=</code> を持つキーと値のペアでエンコードされています。 </p> <p>バイナリデータの場合は、代わりに <code>[!UICONTROL multipart/form-data]</code> を使用します。</p> 
      <div class="example" data-mc-autonum="<b>Example: </b>">
       <span class="autonumber"><span><b>例：</b></span></span> 
       <p>結果の HTTP リクエスト形式の例は、次のようになります。</p> 
       <p><code>field1=value1&amp;field2=value2</code> </p> 
      </div> </li> 
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>[!UICONTROL Multipart/form-data] は、ファイルおよびデータの送信に使用される HTTP マルチパートリクエストです。 通常、ファイルをサーバーにアップロードする際に使用されます。</p> <p>リクエストで送信するフィールドを追加します。各フィールドには、キーと値のペアが含まれている必要があります。</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>リクエスト本文内で送信するキーと値を入力します。</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>キーを入力し、リクエスト本文で送信するソースファイルを指定します。</p> <p>以前のモジュール（[!UICONTROL HTTP] &gt;[!UICONTROL Get a File] や [!UICONTROL Google Drive] &gt; など）からアップロードするファイルをマッピングするか、ファイル名とファイルデータを手動で入力 [!UICONTROL Download a File)] ます。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>このオプションを有効にすると、応答を自動的に解析し、JSON および XML 応答を変換するので、[!UICONTROL JSON]/[!UICONTROL Parse JSON] または [!UICONTROL XML]/[!UICONTROL Parse XML] モジュールを使用する必要がなくなります。</p> <p>解析された JSON または XML コンテンツを使用する前に、モジュールを手動で 1 回実行して、モジュールが応答コンテンツを認識し、後続のモジュールにマッピングできるようにします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>リクエストのタイムアウトを秒単位で指定します（1～300）。デフォルトは 40 秒です。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> このオプションを有効にすると、シナリオ内のすべての HTTP モジュールとサーバーから Cookie を共有できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p>自己署名証明書を追加するには：</p>
          <ol>
            <li value="1">
              <p><b>[!UICONTROL Extract]</b> をクリックします。</p>
            </li>
            <li value="2">
              <p>抽出するファイルのタイプを選択します。</p>
            </li>
            <li value="3">
              <p>または証明書を含むファイルを選択します。</p>
            </li>
            <li value="4">
              <p>ファイルのパスワードを入力します。</p>
            </li>
            <li value="5">
              <p>「<b>[!UICONTROL Save]</b>」をクリックしてファイルを抽出し、モジュール設定に戻ります。</p>
            </li>
          </ol>
</p> </td> 
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
   <td> <p>デフォルトでは、[!DNL Workfront Fusion] は、配列と同じ URL クエリ文字列パラメーターキーに対する複数の値を処理します。例えば、<code>www.test.com?foo=bar&amp;foo=baz</code> が <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code> に変換されます。このオプションをアクティブ化すると、この機能は無効になります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request compressed content]</td> 
   <td> <p> このオプションを有効にすると、web サイトの圧縮バージョンを要求できます。</p> <p>圧縮コンテンツをリクエストするヘッダーに、<code>[!UICONTROL Accept-Encoding]</code> を追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>このオプションを有効にすると、HTTP リクエストで相互 TLS を使用できます。</p> <p>相互 TLS について詳しくは、<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> の HTTP モジュールで相互 TLS を使用を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>
