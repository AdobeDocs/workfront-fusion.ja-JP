---
title: AWS S3 モジュール
description: ' [!DNL Adobe Workfront Fusion AWS]  S3 モジュールを使用すると、S3 バケットに対して操作を実行できます。'
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
source-git-commit: 8d78f1b0e9ba020c6d63ac8f5b1f21500d1ada35
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 79%

---

# AWS S3 モジュール

[!DNL Adobe Workfront Fusion AWS] S3 モジュールを使用すると、S3 バケットに対して操作を実行できます。

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

[!UICONTROL AWS S3] モジュールを使用するには [!DNL Amazon Web Service] アカウントが必要です。

## AWS S3 APIについて

AWS S3 コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td><pre><code>https://s3.&#123;&#123;parameters.region&#125;&#125;.amazonaws.com</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL AWS] を Workfront Fusion に接続 {#connect-aws-to-workfront-fusion}

[!DNL AWS S3]をWorkfront Fusionに接続するには、[!DNL AWS] アカウントをWorkfront Fusionに接続する必要があります。 これを行うには、まず [!DNL AWS] [!UICONTROL IAM] で API ユーザーを作成します。

1. [!DNL AWS] [!UICONTROL IAM] アカウントにログインします。
1. **[!UICONTROL ID とアクセスの管理]**／**[!UICONTROL アクセス管理]**／**[!UICONTROL ユーザー]**&#x200B;に移動します。

1. 「**[!UICONTROL ユーザーを追加]**」をクリックします。
1. 新しいユーザーの名前を入力し、「[!UICONTROL アクセスタイプ]」セクションで「**[!UICONTROL プログラムアクセス]**」オプションを選択します。
1. 「**[!UICONTROL 既存のポリシーを直接添付]**」をクリックして、検索バーで **[!UICONTROL AmazonS3FullAccess]** を検索します。 それが表示されたら選択して「**[!UICONTROL 次へ]**」をクリックします。

1. 他のダイアログ画面を進み、「**[!UICONTROL ユーザーを作成]**」をクリックします。
1. 提供された&#x200B;**[!UICONTROL アクセスキー ID]** および&#x200B;**[!UICONTROL 秘密アクセスキー]**&#x200B;をコピーします。

1. Workfront Fusionに移動し、[!DNL AWS S3] モジュールの&#x200B;**[!UICONTROL 接続を作成]** ダイアログを開きます。
1. 手順7の「[!UICONTROL アクセスキー ID]」および「[!UICONTROL 秘密アクセスキー]」をそれぞれのフィールドに入力し、「**[!UICONTROL 続行]**」をクリックして接続を確立します。

接続が確立されました。 モジュールの設定に進むことができます。

## [!DNL AWS S3] モジュールとそのフィールド

[!DNL AWS S3] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL AWS S3]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [検索](#searches)

### アクション

* [[!UICONTROL バケットを作成]](#create-bucket)
* [[!UICONTROL ファイルを取得]](#get-file)
* [[!UICONTROL API 呼び出しの実行]](#make-an-api-call)
* [[!UICONTROL ファイルをアップロード]](#upload-file)

#### [!UICONTROL バケットを作成]

このアクションモジュールは、AWSでバケットを作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL AWS] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">[!DNL AWS] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>新しいバケットの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>地域のエンドポイントを選択します。 詳しくは、AWS ドキュメントの<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">地域エンドポイント </a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを取得]

このアクションモジュールは、バケットからファイルをダウンロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL AWS] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">[!DNL AWS] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>地域のエンドポイントを選択します。 詳しくは、[!DNL AWS] ドキュメントの<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">地域エンドポイント </a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>ファイルのダウンロード元のバケットを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Path]</p> </td> 
   <td> <p>ファイルにパスを入力します。 例：<code>/photos/2019/February/image023.jpg</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL API 呼び出しの実行]

このアクションモジュールは、AWS S3 APIをカスタム呼び出します。

[!DNL Amazon S3] APIの詳細については、[[!DNL Amazon S3] [!UICONTROL REST] APIの概要](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html)を参照してください。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL AWS] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">[!DNL AWS] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Region] </td> 
   <td> <p>地域のエンドポイントを選択します。 詳しくは、[!DNL AWS] ドキュメントの<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">地域エンドポイント </a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>ホスト URLを入力します。 パスは <code> https://s3.&lt;selected-region>.amazonaws.com/</code> を基準として指定する必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しを設定する必要がある [!UICONTROL HTTP] リクエストメソッドを選択します。 詳しくは、Adobe Workfront Fusion</a>の<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!UICONTROL HTTP] リクエストメソッドを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>リクエストヘッダーを追加します。 追加する各ヘッダーについて、<b>項目を追加</b>をクリックし、ヘッダーを入力します。 次の共通のリクエストヘッダーを使用できます。 リクエストヘッダーについて詳細は、<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonRequestHeaders.html">[!DNL AWS S3]API ドキュメント</a>を参照してください。</p> <p>Workfront Fusion は認証ヘッダーを自動的に追加します。</p> 
    <table style="table-layout:auto">
     <col> 
     <col> 
     <thead> 
      <tr> 
       <th>ヘッダー名</th> 
       <th> <p> 説明</p> </th> 
      </tr> 
     </thead> 
     <tbody> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Length]</p> </td> 
       <td> <p>RFC 2616 に従ったメッセージの長さ（ヘッダーなし）。 このヘッダーは、[!UICONTROL PUT] や、XML を読み込む操作（ログや ACL など）に必要です。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Type]</p> </td> 
       <td> <p>リソースのコンテンツタイプ（リクエストコンテンツが本文にある場合）。 例：<code>text/plain</code>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-MD5]</p> </td> 
       <td> <p>RFC 1864 に従って、base64 エンコードされた 128 ビットの MD5 ダイジェスト（ヘッダーなし）。 このヘッダーをメッセージの整合性チェックとして使用し、データが最初に送信されたのと同じデータであることを検証できます。 これはオプションですが、[!UICONTROL Content-MD5] メカニズムをエンドツーエンドの整合性チェックとして使用することをお勧めします。 [!UICONTROL REST]認証リクエストについて詳しくは、AWS ドキュメントの「<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html?r=1821">REST リクエストの署名と認証</a>」を参照してください。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Date]</p> </td> 
       <td> <p>リクエスターに応じた現在の日時。 例：<code>Wed, 01 Mar 2006 12:00:00 GMT</code>。 <code>Authorization </code> ヘッダーを指定する場合は、<code>x-amz-date</code> ヘッダーまたは <code>Date </code> ヘッダーを指定する必要があります。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Expect]</p> </td> 
       <td> <p>アプリケーションで [!UICONTROL 100-continue] を使用する場合、確認を受け取るまでリクエスト本文は送信されません。 ヘッダーに基づいてメッセージを拒否した場合、メッセージの本文は送信されません。 このヘッダーは、本文を送信する場合にのみ使用できます。</p> <p>有効な値：[!UICONTROL 100-continue]</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
       <td> <p>パススタイルのリクエストの場合、値は <code>s3.amazonaws.com</code> です。 仮想スタイルのリクエストの場合、値は <code>BucketName.s3.amazonaws.com</code> です。 詳しくは、AWS ドキュメントの<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html"> バーチャルホスティング </a>を参照してください。</p> <p>このヘッダーは HTTP 1.1 に必要であり、ほとんどのツールキットで自動的に追加されます。HTTP/1.0 リクエストの場合はオプションです。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-content-sha256]</p> </td> 
       <td> <p>署名バージョン 4 を使用してリクエストを認証する場合は、このヘッダーによってリクエストペイロードのハッシュが提供されます。 オブジェクトをチャンク単位でアップロードする場合は、値を <code>STREAMING-AWS4-HMAC-SHA256-PAYLOAD</code> に設定して、署名がヘッダーのみを対象とし、ペイロードがないことを示します。 詳しくは、AWS ドキュメントの「<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-streaming.html">Signature Calculations for the Authorization Header</a>」を参照してください。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-date]</p> </td> 
       <td> <p>リクエスターに応じた現在の日時。 例：<code>Wed, 01 Mar 2006 12:00:00 GMT</code>。 <code>Authorization </code> ヘッダーを指定する場合は、<code>x-amz-date</code> ヘッダーまたは <code>Date </code> ヘッダーを指定する必要があります。 両方を指定した場合は、<code>x-amz-date</code> ヘッダーの値が優先されます。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-security-token]</p> </td> 
       <td> <p>このヘッダーは、次のシナリオで使用できます。</p> 
        <ul> 
         <li>[!DNL Amazon DevPay]操作のためにセキュリティトークンを提供します。 [!DNL Amazon DevPay]を使用する各リクエストには、製品トークン用とユーザートークン用の 2 つの<code>x-amz-security-token</code>ヘッダーが必要です。 [!DNL Amazon S3] が認証済みリクエストを受け取ると、計算済みの署名と提供された署名を比較します。 署名の計算に使用されている複数値ヘッダーの形式が適切でない場合、認証の問題が発生する可能性があります。</li> 
         <li>一時的なセキュリティ資格情報を使用する場合は、セキュリティトークンを提供します。 IAM から取得した一時的なセキュリティ認証情報を使用してリクエストを行う際には、このヘッダーを使用してセキュリティトークンを提供する必要があります。 一時的なセキュリティ認証情報の詳細については、「リクエストの実行」を参照してください。</li> 
        </ul> <p>このヘッダーは、[!DNL Amazon DevPay] を使用するリクエストおよび一時的なセキュリティ認証情報を使用して署名されたリクエストに必要です。</p> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>パラメーターやフォームフィールドなど、必要なクエリ文字列を追加します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：   <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをアップロード]

このアクションモジュールは、ファイルをAWS S3 バケットにアップロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL AWS] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">[!DNL AWS] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>地域のエンドポイントを選択します。 詳しくは、[!DNL AWS] ドキュメントの<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">地域エンドポイント </a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Folder] </p> </td> 
   <td> <p>ファイルのアップロード先であるターゲットフォルダーを指定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers]（オプション）</p> </td> 
   <td> <p> 追加する各ヘッダーについて、<b>項目を追加</b>をクリックし、ヘッダーのキーと値を入力します。</p><p> 使用可能なヘッダーについては、AWS ドキュメントの<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutObject.html">PutObject</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL ファイルをリストする]](#list-files)
* [[!UICONTROL フォルダーをリストする]](#list-folders)

#### [!UICONTROL ファイルをリストする]

指定された場所からファイルのリストを返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL AWS] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">[!DNL AWS] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>地域のエンドポイントを選択します。 詳しくは、[!DNL AWS] ドキュメントの<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">地域エンドポイント </a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>ファイルを検索する [!DNL Amazon S3] バケットを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix]</p> </td> 
   <td> <p> でファイルを検索するフォルダーへのパスを入力します。例： <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーをリストする]

指定された場所からフォルダーのリストを返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL AWS] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-aws-to-workfront-fusion" class="MCXref xref">[!DNL AWS] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>地域のエンドポイントを選択します。 詳しくは、[!DNL AWS] ドキュメントの<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">地域エンドポイント </a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>フォルダーを検索する [!DNL Amazon S3] バケットを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix]（オプション）</p> </td> 
   <td> <p> フォルダーを検索するフォルダーへのパス（例：） <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>
