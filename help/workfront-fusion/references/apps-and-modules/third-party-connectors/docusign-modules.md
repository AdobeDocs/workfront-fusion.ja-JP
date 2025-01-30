---
title: DocuSign モジュール
description: ' [!DNL Adobe Workfront Fusion DocuSign] モジュールを使用すると、エンベロープのステータスを監視および取得したり、エンベロープを検索および取得したり、ドキュメントをダウンロードして送信し、 [!DNL DocuSign] アカウントにログインしたりできます。'
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1637'
ht-degree: 84%

---

# DocuSign モジュール

[!DNL Adobe Workfront Fusion] [!DNL DocuSign]モジュールを使用すると、エンベロープのステータスを監視および取得したり、エンベロープを検索および取得したり、ドキュメントをダウンロードして送信し、[!DNL DocuSign]アカウントにログインしたりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## 前提条件

[!DNL DocuSign] モジュールを使用するには、[!DNL DocuSign] アカウントが必要です。

## DocuSign API 情報

DocuSign コネクタは以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>1.18.11</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL DocuSign] を [!DNL Workfront Fusion] に接続 {#connect-docusign-to-workfront-fusion}

[!DNL DocuSign] モジュールへの接続を作成するには、以下を実行します。

1. 最初の [!DNL DocuSign] モジュールの設定を開始する際は、[!UICONTROL Connection] ボックスの横にある **[!UICONTROL Add]** をクリックします。
1. 以下の情報を入力します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>新しい [!DNL DocuSign] 接続の名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>接続するアカウントが実稼動アカウントかデモアカウントかを選択します。</td> 
     </tr> 
    </tbody> 
   </table>

1. [ [!DNL Adobe Workfront Fusion]  への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md#connect)の手順に従って続けます。

## [!DNL DocuSign] モジュールとそのフィールド

[!DNL DocuSign] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL DocuSign] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)

### トリガー

#### [!UICONTROL Watch envelopes]

このトリガーモジュールは、エンベロープが送信、配信、署名、完了または拒否されたときにシナリオを開始します。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>監視するレコードを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p> 監視するイベントのタイプを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Document completed]</li> 
     <li>[!UICONTROL Document declined]</li> 
     <li>[!UICONTROL Document sent]</li> 
     <li>[!UICONTROL Document signed]</li> 
     <li>[!UICONTROL New document in Inbox]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Output fields]</p> </td> 
   <td> <p>モジュールの出力に含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが操作するレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Download a document]](#download-a-document)
* [[!UICONTROL Read an envelope]](#read-an-envelope)
* [[!UICONTROL Upload a file to an envelope]](#upload-a-file-to-an-envelope)
* [[!UICONTROL Create a new envelope]](#create-a-new-envelope)
* [[!UICONTROL Add Recipient to Envelope]](#add-recipient-to-envelope)
* [[!UICONTROL Add custom field]](#add-custom-field)
* [[!UICONTROL Modify custom field]](#modify-custom-field)
* [[!UICONTROL Send envelope]](#send-envelope)

#### [!UICONTROL Custom API Call]

このアクションモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Account]</td> 
   <td>[!DNL DocuSign] API アクセスに使用するアカウントを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>モジュールとやり取りする web サーバー上のアドレスを入力します。</p> <p>相対 URL を入力できます。つまり、<code>http://</code> などのプロトコルを最初に含める必要はありません。これは、web サーバー上でやり取りが発生していることを示しています。</p> <p>例： <code>[!DNL /api/conversations].create</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> {"Content-type":"application/json"}</code></p> <p>メモ：エラーが表示され、エラーの発生元を特定するのが困難な場合は、[!DNL Workfront] ドキュメントに基づいてヘッダーの変更を考慮してください。カスタム API 呼び出しで 422 HTTP リクエストエラーが返される場合は、"Content-Type":"text/plain"ヘッダーを使用してみてください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>1 回の実行サイクルで処理する結果の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**例**：エンベロープのリスト
>
>次の API 呼び出しは、[!DNL DocuSign] アカウントの指定された日付からのエンベロープを返します。
>
>**URL**：`/v2.1/accounts/{accountId}/envelopes/`
>
>**メソッド**：`GET`
>
>**クエリ文字列**：
>
>* **キー**：`from_date`
>
>* **値**：`YYYY-MM-DD`
>
>リクエストがアカウント内のエンベロープのステータス変更のチェックを開始する時期を指定します。
>
>![Docusign 設定の例 ](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)
>
>結果は、モジュールの出力（バンドル／本文／エンベロープの下）にあります。
>
>この例では、6 個のエンベロープが返されました。
>
>![docusign 出力の例 ](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

#### [!UICONTROL Download a document]

このアクションモジュールは、1 つのドキュメントをダウンロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>ダウンロードするドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> ダウンロードするエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Document ID]</p> </td> 
   <td> <p>ダウンロードするドキュメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Certificate]</td> 
   <td>ダウンロードにエンベロープ署名証明書を含める場合は、[<strong>[!UICONTROL Yes]</strong>] を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents by User ID]</td> 
   <td>受信者がユーザー ID でドキュメントを取得できるようにする場合は、「<strong>[!UICONTROL Yes]</strong>」を選択します。 例えば、ユーザーが異なる表示の 2 つの異なるルーティングオーダーに含まれている場合、このオプションを使用すると、両方のルーティングのすべてのドキュメントが戻されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encrypt]</td> 
   <td>[!DNL DocuSign] アカウントに設定されているすべてのキーマネージャーに対して、応答で返されるPDFのバイト数を暗号化する場合は、「<strong>[!UICONTROL Yes]</strong>」を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>言語を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Changes]</td> 
   <td><strong>[!UICONTROL Yes]</strong> に設定すると、返されるPDFの変更されたフィールドは黄色でハイライト表示され、オプションのシグネチャやイニシャルは赤で囲まれます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watermark]</td> 
   <td> <p>「<strong>[!UICONTROL No]</strong>」を選択すると、PDFドキュメントから透かしを削除できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read an envelope]

このアクションモジュールは、エンベロープ ID を使用して、[!DNL DocuSign] にあるエンベロープに関する情報を読み取ります。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>情報を読み取るドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 情報を読み取るドキュメントを含む ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に表示するプロパティを選択します。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file to an envelope]

このモジュールは、指定されたファイルを DocuSign の既存のエンベロープにアップロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>ファイルをアップロードするエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> ファイルをアップロードするエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>前のモジュールからソースファイルを選択するか、ソースファイルの名前とデータを入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a new envelope]

このアクションモジュールは、テンプレートから新規エンベロープを作成します。新規エンベロープの ID と、新規エンベロープのステータスを返します。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td>

<td> <p>DocuSign アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> の記事を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Account] </td>
   <td> <p>ファイルをアップロードするエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template]</td>
   <td> <p> 新規エンベロープを作成するテンプレートを選択します。テンプレートは、選択した [!UICONTROL Account] に基づいて使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL After creation]
   </td> 
   <td> <p>エンベロープをドラフトとして保存するか、署名用に送信するかを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template recipients]</td>
    <td>このエンベロープの受信者を選択します。</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Recipient to Envelope]

このアクションモジュールは、1 人以上の受信者を既存のエンベロープに追加します。エンベロープが既に送信されている場合は、受信者にメールが送信されます。このモジュールは、既に完了しているエンベロープに対しては無効です。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>DocuSign アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Account] </td>
   <td> <p>受信者を追加するエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Envelope ID]</td>
    <td>受信者を追加するエンベロープの ID を選択またはマッピングします。</td>
  </tr> 
  <tr data-mc-conditions="">
    <td role="rowheader">[!UICONTROL Recipient type]</td>
   <td> <p> エンベロープに追加する受信者のタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Agent]</p> </li> 
     <li> <p>[!UICONTROL Carbon copy]</p> </li> 
     <li> <p>[!UICONTROL Certified delivery]</p> </li> 
     <li> <p>[!UICONTROL In-person signer]</p> </li> 
     <li> <p>[!UICONTROL Intermediary]</p> </li> 
     <li> <p>[!UICONTROL Signer]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Email]</td>
   <td> <p>エンベロープに追加する受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Name]</td>
   <td>エンベロープに追加する受信者の名前を入力またはマッピングします。</td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Routing order]</td>
   <td> <p>受信者のルーティング番号を入力またはマッピングします。ルーティング番号は、受信者がドキュメントを受け取り署名する順序を指定するものです。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Email body]</td>
   <td>受信者に送信するメールの本文（コンテンツ）を入力またはマッピングします。</td> 
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Email subject]</td>
   <td>受信者に送信するメールの件名を入力またはマッピングします。</td> 
  </tr> 
    <td role="rowheader">[!UICONTROL Private message]</td>
   <td> <li> <p>選択した受信者にのみ、一般メッセージと共にプライベートメッセージも表示されます。プライベートメッセージの長さは 1000 文字までです。</p> </li> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Authentication]</td> 
   <td> <p>受信者の ID の確認に使用する認証メソッドを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL None]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Access code]</strong> </p> <p>アクセスコードを入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Phone]</strong> </p> <p>電話番号の入力またはマッピング</p> </li> 
     <li> <p><strong>[!UICONTROL SMS]</strong> </p> <p>電話番号の入力またはマッピング</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add custom field]

このアクションモジュールは、カスタムフィールドをドキュメントに追加します

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>カスタムフィールドを追加するドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> カスタムフィールドを追加するドキュメントが含まれるエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>追加する新しいフィールドの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>追加したフィールドを必須フィールドにする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>フィールドを表示する場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>追加したフィールドの値（コンテンツ）を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modify custom field]

このアクションモジュールは、フィールド名を使用してカスタムフィールドを変更します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>カスタムフィールドを変更するドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> カスタムフィールドを変更するドキュメントが含まれるエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field ID]</td> 
   <td>変更するフィールドの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>変更するフィールドの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>変更したフィールドを必須フィールドにする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>フィールドを表示する場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>変更したフィールドの値（コンテンツ）を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send envelope]

このアクションモジュールは、受信者に下書きエンベロープを送信します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">[!DNL DocuSign] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>受信者に送信する下書きエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 受信者に送信する下書きエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
