---
title: Adobe PDF サービス
description: Adobe PDF サービス
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: e6fbbc20-4315-4668-9e11-af7cfa82ae66
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: ht
source-wordcount: '4151'
ht-degree: 100%

---

# [!DNL Adobe PDF Services]

Adobe Workfront Fusion [!DNL Adobe PDF Services] を使用すると、PDF ファイルからデータを抽出したり、指定したデータから新しい PDF ファイルを生成したりできます。さらに、様々なファイルタイプを PDF に変換したり、PDF を他のファイルタイプに変換したりできます。PDF サービスでは、PDF ファイルの組み合わせ、圧縮、メタデータの読み取りを行うことや、ファイルのパスワード保護を制御することもできます。

シナリオの作成手順について詳しくは、[シナリオの作成：記事のインデックス](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

モジュールについて詳しくは、[モジュール：記事インデックス](/help/workfront-fusion/references/modules/modules-toc.md)の記事を参照してください。

PDF サービスに使用される API については、[Adobe Document Generation API](https://www.adobe.io/apis/documentcloud/dcsdk/doc-generation.html) を参照してください。

## [!DNL Adobe PDF Services] を使用する際のセキュリティに関する考慮事項

[!DNL Adobe PDF Services] はファイルの読み取り、変換、変更はできますが、[!DNL Adobe] も Workfront Fusion もファイルやデータを保存しません。つまり、次のようになります。

* ユーザーは、ファイルのセキュリティを含め、ファイルの制御を維持する
* PDF サービスを使用するのに[!UICONTROL アドビ]ストレージやクラウドストレージアカウントは必要ありません。

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

OAuth サーバー間接続を作成するには、Adobe Developers Console に Adobe PDF サービス API を追加する必要があります。API を追加する場合は、OAuth サーバー間オプションを選択します。

手順について詳しくは、アドビの開発者向けドキュメントで [OAuth ユーザー認証資格証明を使用したプロジェクトへの API の追加](https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication)を参照してください。

## Adobe PDF サービス API 情報

Adobe PDF サービスコネクターは、次を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://pdf-services-stage.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v2.1.4</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Adobe PDF Services] への接続の作成

[!DNL Adobe PDF Services] モジュールへの接続を作成するには、以下を実行します。

1. 任意の [!DNL Adobe PDF Services] モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection type]</td>
          <td>
            <p>サーバー間接続と JWT 接続のどちらを作成するかを選択します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>この接続の名前を入力します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]</td>
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の検索手順については、アドビデベロッパー向けドキュメントで<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >資格情報</a>を参照してください。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の検索手順については、アドビデベロッパー向けドキュメントで<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >資格情報</a>を参照してください。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Technical account ID]（JWT のみ）</td>
          <td>[!DNL Adobe] [!UICONTROL Technical account ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の検索手順については、アドビデベロッパー向けドキュメントで<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >資格情報</a>を参照してください。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Organization ID]（JWT のみ）</td>
          <td>[!DNL Adobe] [!UICONTROL Organization ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の検索手順については、アドビデベロッパー向けドキュメントで<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >資格情報</a>を参照してください。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Meta scopes]（JWT のみ）</td>
          <td>
            接続に必要なメタスコープを入力します。
          </td>
        </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>JWT 接続を選択した場合は、資格情報が [!DNL Adobe Developer Console] で作成されたときに生成された秘密鍵を入力します。 </p>
          <p>秘密鍵または証明書を抽出するには：</p>
          <ol>
            <li value="1">
              <p><b>[!UICONTROL Extract]</b> をクリックします。</p>
            </li>
            <li value="2">
              <p>抽出するファイルのタイプを選択します。</p>
            </li>
            <li value="3">
              <p>秘密鍵または証明書を含むファイルを選択します。</p>
            </li>
            <li value="4">
              <p>ファイルのパスワードを入力します。</p>
            </li>
            <li value="5">
              <p><b>[!UICONTROL Save]</b> をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
      </tr>
       </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。


## [!DNL Adobe PDF Services] モジュールとそのフィールド

[!DNL PDF Services] を設定すると、Workfront Fusion には以下のフィールドが表示されます。これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加のフィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL PDF ファイルの結合]](#combine-pdf-files)
* [[!UICONTROL PDF ファイルの圧縮]](#compress-pdf-files)
* [[!UICONTROL PDF ファイルへのドキュメントの変換]](#convert-document-to-pdf-file)
* [[!UICONTROL PDF ファイルへの HTML の変換]](#convert-html-to-pdf-file)
* [[!UICONTROL PDF ファイルへの画像の変換]](#convert-image-to-pdf-file)
* [[!UICONTROL ドキュメントへの PDF の変換]](#convert-pdf-to-document)
* [[!UICONTROL 画像への PDF の変換]](#convert-pdf-to-image)
* [[!UICONTROL テキスト／テーブルの抽出]](#extract-text--table)
* [[!UICONTROL ドキュメントの生成]](#generate-document)
* [[!UICONTROL PDF ファイルのリニアライズ]](#linearize-a-pdf-file)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [[!UICONTROL PDF ファイルの OCR]](#ocr-for-pdf-file)
* [[!UICONTROL ページ操作]](#page-manipulation)
* [[!UICONTROL PDF アクセシビリティの自動タグ付け]](#pdf-accessibility-auto-tag)
* [[!UICONTROL PDF ファイルのプロパティ]](#pdf-file-properties)
* [[!UICONTROL PDF ファイルの保護]](#protect-pdf-file)
* [[!UICONTROL PDF ファイルの保護の解除]](#remove-protection-of-a-pdf-file)
* [PDF ファイルの分割](#split-a-pdf-file)

### [!UICONTROL PDF ファイルの結合]

このアクションモジュールは、複数の PDF ファイルを取得し、それらを 1 つの PDF ファイルに結合します。例えばこのモジュールは、[!UICONTROL Workfront] プロジェクトのすべてのドキュメントを、プロジェクトの完了時に 1 つの PDF に結合します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する方法については、この記事内の <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents]</td> 
   <td> <p>集約モジュールを使用して、ドキュメントを収集して PDF に組み合わせることも、手動でドキュメントを追加することもできます。 </p> <p>[!UICONTROL Array Aggregator] モジュールを使用して、以前のモジュールの出力を集計することをお勧めします。集約を使用すると、結合するファイルの名前、場所、数を把握する必要がなくなります。したがって、集約を使用すると、結合するドキュメントを手動で入力するよりも、高い柔軟性と拡張性が得られます。</p> <p>[!UICONTROL Combine PDF] モジュールを集約と共に使用するには、[!UICONTROL Documents] フィールドでマッピングを有効にする必要があります。 </p> <p>この例では、[!UICONTROL Read Related Records] モジュールはプロジェクトに関連付けられたドキュメントを識別し、[!UICONTROL Download Documents] モジュールは各ドキュメントをダウンロードします。すべての PDF は配列に集計され、[!UICONTROL Combine PDF] ファイルモジュールに渡されます。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/combine-example-350x104.png" style="width: 350;height: 104;"> </p> <p>手動でドキュメントを入力することもできます。</p> <p>結合 PDF に含めるドキュメントごとに、次の手順を実行します。</p> 
    <ol> 
     <li value="1"> <p>「[!UICONTROL Add a Document]」をクリックします。</p> </li> 
     <li value="2"> <p>「[!UICONTROL Source file]」フィールドで、含めるドキュメントを出力するモジュールを選択するか、ソースファイルの名前とデータをマッピングします。 </p> </li> 
     <li value="3"> <p>（オプション）ソースファイルの特定のページのみを含める場合は、追加するページ範囲ごとに、「[!UICONTROL Pages]」フィールドの「<strong>[!UICONTROL Add item]</strong>」をクリックし、含めるページ範囲の最初と最後のページを入力し、「<strong>[!UICONTROL Add]</strong>」をクリックします。1 つのドキュメントから複数のページ範囲を含めることができます。</p> </li> 
     <li value="4"> <p>「<strong>[!UICONTROL Add]</strong>」をクリックします。 </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF ファイルを圧縮]

このアクションモジュールは PDF ファイルを取得し、圧縮します。これは、帯域幅やメモリの節約に役立ちます。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは PDF 形式である必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Compression level]</td> 
   <td>使用する圧縮レベルを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL ドキュメントを PDF ファイルに変換]

このツールは、ドキュメントを PDF ファイルに変換します。ソースファイルは、次のいずれかのドキュメント形式である必要があります。

* DOC
* XLS
* PPT
* TXT
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは、次のいずれかの形式で指定する必要があります。</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>XLS</p> </li> 
     <li> <p>PPT</p> </li> 
     <li> <p>TXT</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>ソースドキュメントのデフォルト言語を選択します。これにより、ソースファイルにフォントが含まれていない場合、モジュールは適切なフォントを選択できるようになります。</p> <p>次の言語から選択します。</p> 
    <ul> 
     <li> <p>en-US（デフォルト）：英語（米国）</p> </li> 
     <li> <p>ca-ES：カタロニア語（スペイン）</p> </li> 
     <li> <p>cs-CZ：チェコ語（チェコ共和国）</p> </li> 
     <li> <p>da-DK：デンマーク語（デンマーク）</p> </li> 
     <li> <p>de-DE：ドイツ語（ドイツ）</p> </li> 
     <li> <p>en-AE：英語（アラブ首長国連邦）</p> </li> 
     <li> <p>en-GB：英語（英国）</p> </li> 
     <li> <p>en-IL：英語（イスラエル）</p> </li> 
     <li> <p>en-US：英語（米国）</p> </li> 
     <li> <p>es-ES：スペイン語（スペイン）</p> </li> 
     <li> <p>es-MX：スペイン語（メキシコ）</p> </li> 
     <li> <p>eu-ES：バスク語（スペイン）</p> </li> 
     <li> <p>fi-FI：フィンランド語（フィンランド）</p> </li> 
     <li> <p>fr-CA：フランス語（カナダ）</p> </li> 
     <li> <p>fr-FR：フランス語（フランス）</p> </li> 
     <li> <p>fr-MA：フランス語（モロッコ）</p> </li> 
     <li> <p>hr-HR：クロアチア語（クロアチア）</p> </li> 
     <li> <p>hu-HU：ハンガリー語（ハンガリー）</p> </li> 
     <li> <p>it-IT：イタリア語（イタリア）</p> </li> 
     <li> <p>ja-JP：日本語（日本）</p> </li> 
     <li> <p>kr-KR：韓国語（韓国）</p> </li> 
     <li> <p>nb-NO：ノルウェー語（ブークモール）（ノルウェー）</p> </li> 
     <li> <p>nl-NL：オランダ語（オランダ）</p> </li> 
     <li> <p>pl-PL：ポーランド語（ポーランド）</p> </li> 
     <li> <p>pt-BR：ポルトガル語（ブラジル）</p> </li> 
     <li> <p>pt-PT：ポルトガル語（ポルトガル）</p> </li> 
     <li> <p>ro-RO：ルーマニア語（ルーマニア）</p> </li> 
     <li> <p>ru-RU：ロシア語（ロシア）</p> </li> 
     <li> <p>sk-SK：スロバキア語（スロバキア）</p> </li> 
     <li> <p>sl-SI：スロベニア語（スロベニア）</p> </li> 
     <li> <p>sv-SE：スウェーデン語（スウェーデン）</p> </li> 
     <li> <p>tr-TR：トルコ語（トルコ）</p> </li> 
     <li> <p>uk-UA：ウクライナ語（ウクライナ）</p> </li> 
     <li> <p>zh-CN：中国語（中国本土）</p> </li> 
     <li> <p>zh-TW：中国語（台湾）</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL HTML を PDF ファイルに変換]

このツールは、HTML ファイルを PDF ファイルに変換します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>重要：ソースファイルは HTML 形式または ZIP 形式である必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON]</td> 
   <td> <p>HTML で JavaScript 変数を参照する場合、これらの変数を含めることができます。 </p> <p>変数ごとに、「<strong>[!UICONTROL Add item]</strong>」をクリックし、変数のキーと値を含めます。</p> <p>メモ：   
     <ul> 
      <li> <p>ZIP ファイルから PDF を作成する場合、ソースの付随事項には <code> &lt;script src='./json.js' type='text/javascript'&gt;&lt;/script&gt;</code> のようなスクリプト要素が含まれている必要があります。 </p> </li> 
      <li> <p>URL から PDF を作成する場合、ページがレンダリングされる前に、この JSON オブジェクトのコンテンツがブラウザー VM に挿入されます。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include header and footer]</td> 
   <td> <p>このオプションを有効にすると、PDF ドキュメントのヘッダーとフッターが作成されます。</p> 
    <ul> 
     <li> <p>ヘッダーには、日付とドキュメントタイトルが含まれます。</p> </li> 
     <li> <p>フッターには、ファイル名とページ番号が含まれます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page width]</td> 
   <td>用紙の幅をインチ単位で入力します。モジュールはこの情報を使用して、作成された PDF ファイル内のページを書式設定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page height]</td> 
   <td>用紙の高さをインチ単位で入力します。モジュールはこの情報を使用して、作成された PDF ファイル内のページを書式設定します。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 画像を PDF ファイルに変換]

このツールは、画像を PDF ファイルに変換します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>前のモジュールからソースファイルを選択するか、ソースファイル名と画像ファイルをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF を文書に変換]

このツールは、PDF ファイルをドキュメントに変換します。出力ファイルには、次のいずれかの形式を選択できます。

* DOC
* DOCX
* PPTX
* XLSX
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは PDF 形式である必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>ファイルを出力する形式を次の中から選択します。</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>DOCX</p> </li> 
     <li> <p>PPTX</p> </li> 
     <li> <p>XLSX</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>ソースドキュメントのデフォルト言語を選択します。これにより、ソースファイルにフォントが含まれていない場合、モジュールは適切なフォントを選択できるようになります。</p> <p>次の言語から選択します。</p> 
    <ul> 
     <li> <p>en-US（デフォルト）：英語（米国）</p> </li> 
     <li> <p>ca-ES：カタロニア語（スペイン）</p> </li> 
     <li> <p>cs-CZ：チェコ語（チェコ共和国）</p> </li> 
     <li> <p>da-DK：デンマーク語（デンマーク）</p> </li> 
     <li> <p>de-DE：ドイツ語（ドイツ）</p> </li> 
     <li> <p>en-AE：英語（アラブ首長国連邦）</p> </li> 
     <li> <p>en-GB：英語（英国）</p> </li> 
     <li> <p>en-IL：英語（イスラエル）</p> </li> 
     <li> <p>en-US：英語（米国）</p> </li> 
     <li> <p>es-ES：スペイン語（スペイン）</p> </li> 
     <li> <p>es-MX：スペイン語（メキシコ）</p> </li> 
     <li> <p>eu-ES：バスク語（スペイン）</p> </li> 
     <li> <p>fi-FI：フィンランド語（フィンランド）</p> </li> 
     <li> <p>fr-CA：フランス語（カナダ）</p> </li> 
     <li> <p>fr-FR：フランス語（フランス）</p> </li> 
     <li> <p>fr-MA：フランス語（モロッコ）</p> </li> 
     <li> <p>hr-HR：クロアチア語（クロアチア）</p> </li> 
     <li> <p>hu-HU：ハンガリー語（ハンガリー）</p> </li> 
     <li> <p>it-IT：イタリア語（イタリア）</p> </li> 
     <li> <p>ja-JP：日本語（日本）</p> </li> 
     <li> <p>kr-KR：韓国語（韓国）</p> </li> 
     <li> <p>nb-NO：ノルウェー語（ブークモール）（ノルウェー）</p> </li> 
     <li> <p>nl-NL：オランダ語（オランダ）</p> </li> 
     <li> <p>pl-PL：ポーランド語（ポーランド）</p> </li> 
     <li> <p>pt-BR：ポルトガル語（ブラジル）</p> </li> 
     <li> <p>pt-PT：ポルトガル語（ポルトガル）</p> </li> 
     <li> <p>ro-RO：ルーマニア語（ルーマニア）</p> </li> 
     <li> <p>ru-RU：ロシア語（ロシア）</p> </li> 
     <li> <p>sk-SK：スロバキア語（スロバキア）</p> </li> 
     <li> <p>sl-SI：スロベニア語（スロベニア）</p> </li> 
     <li> <p>sv-SE：スウェーデン語（スウェーデン）</p> </li> 
     <li> <p>tr-TR：トルコ語（トルコ）</p> </li> 
     <li> <p>uk-UA：ウクライナ語（ウクライナ）</p> </li> 
     <li> <p>zh-CN：中国語（中国本土）</p> </li> 
     <li> <p>zh-TW：中国語（台湾）</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF を画像に変換]

このツールは、PDF を PNG または JPEG 形式の画像に変換し、リストとして出力するか ZIP に結合します。

ZIP として出力されると、PDF は 1 ページにつき 1 つの画像に変換され、各画像の末尾がページ番号が付けられます。その後、画像ファイルは ZIP ファイルに結合されます。

例えば、8 ページの「TestFile」という名前のファイルでは、「TestFile_1」から「TestFile_8」までの 8 つの画像が生成されます。このモジュールの出力は、8 つの画像を含む ZIP ファイルです。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは PDF 形式である必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>ファイルを出力する形式を次の中から選択します。</p> 
    <ul> 
     <li>PNG</li> 
     <li>JPEG</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output type]</td> 
   <td> <p>ファイルをファイルのリストとして出力するか、ZIP ファイルとして出力するかを選択します。</td> 
  </tr> 
  <tr> 
 </tbody> 
</table>

### [!UICONTROL テキスト／テーブルの抽出]

このアクションモジュールを使用すると、データを PDF ファイルから抽出できます。このモジュールは、段落やテーブルの単一セル内のテキストなど、個々のテキスト要素を出力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Elements that should be extracted as JSON]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Text]</p> </li> 
     <li> <p>[!UICONTROL Tables]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Extract Bounding boxes?]</td> 
   <td>テキストのバウンディングボックスに関するデータを抽出するには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include styling information for output?]</td> 
   <td>出力 JSON にスタイル情報を追加するには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL ドキュメントの生成]

[!UICONTROL ドキュメントの生成]モジュールは、選択したデータを含む PDF を作成する強力な方法です。[!DNL Microsoft Word] テンプレートを使用するか、JSON 形式でデータを指定することで、形式設定できます。

[!UICONTROL [!DNL Adobe PDF Services]ドキュメントの生成]機能について詳しくは、[!DNL Adobe Document Services] ドキュメントの[ドキュメント生成の概要](https://www.adobe.io/apis/documentcloud/dcsdk/docs.html)を参照してください。

* [ [!DNL Microsoft Word]  テンプレートで[!UICONTROL ドキュメントの生成]モジュールの使用](#use-the-generate-document-module-with-a-microsoft-word-template)
* [JSON で[!UICONTROL ドキュメントの生成]モジュールの使用](#use-the-generate-document-module-with-json)

#### [!DNL Microsoft Word] テンプレートで[!UICONTROL ドキュメントの生成]モジュールの使用


>[!NOTE]
>
>Microsoft Word テンプレートのディスカッションについて詳しくは、[Microsoft Word テンプレートモジュール](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-word-templates-modules.md)を参照してください。
>
>PDF Services Generate ドキュメントモジュールで Microsoft Word テンプレートを使用する場合、Microsoft Word テンプレートモジュールを使用する必要はありません。


[!UICONTROL Microsoft Word] テンプレートで[!UICONTROL ドキュメントの生成]モジュールを使用するには、まずテンプレートを作成する必要があります。手順については、[!DNL Microsoft Office] ドキュメントで「テンプレートの作成」を検索してください。

[!UICONTROL ドキュメントの生成]モジュールのフィールドに次のように入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>このソースファイルは、モジュールが新しい PDF の生成に使用する [!DNL Microsoft Word] テンプレートです。</p> <p>Workfront Fusion で使用する [!DNL Microsoft Word] テンプレート用に Workfront にプロジェクトを作成することをお勧めします。その後、Workfront／[!UICONTROL Download document] モジュールを使用して、適切なテンプレートをシナリオに取り込みます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>生成するドキュメントの形式を選択します。</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>テキストに置き換えるテンプレートの値タグごとに、次のように入力します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Key]</p> <p>キーを入力します。テンプレートでは、キーは値タグに表示されるテキストです。例えば、値タグ <code>&#123;&#123;name&#125;&#125;</code> にテキストを配置する場合は、キーフィールドに <code>name </code> と入力します。</p> </li> 
     <li> <p>値のタイプ</p> <p>値フィールド内のデータを、値、オブジェクトまたはオブジェクトの配列のどれにするかを選択します。</p> </li> 
     <li> <p>[!UICONTROL Value]</p> <p>生成されたドキュメントに、値タグの代わりに表示するテキストを入力またはマッピングします。</p> </li> 
    </ul> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/generate-with-template-350x241.png" style="width: 350;height: 241;"> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### JSON で[!UICONTROL ドキュメントの生成]モジュールの使用

JSON で[!UICONTROL ドキュメントの生成]モジュールを使用するには、次のようにフィールドに入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>生成するドキュメントの形式を選択します。</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>このモジュールで JSON を使用するには、このフィールドでマッピングを有効にする必要があります。</p> <p>ドキュメントを生成する JSON を入力またはマッピングします。 </p> <p>このフィールドに JSON を直接入力するか、JSON モジュールから JSON 出力をマッピングできます。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF ファイルのリニアライズ]

このツールは、PDF ドキュメントをリニアライズして、web 用に最適化された PDF ドキュメントを作成します。リニアライズド PDF ドキュメントは、ドキュメント全体をダウンロードする必要なく、ページごとに表示できます。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

## カスタム API 呼び出しの実行

このアクションモジュールは、PDF サービス API へのカスタム HTTP リクエストです。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> 相対パスまたは URL を入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>API 呼び出しに追加するフィールドごとに、「<b>項目を追加</b>」をクリックして、フィールドのキーとオプション値を入力します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


### [!UICONTROL PDF ファイルの OCR]

このツールは、ファイルに対して光学式文字認識（OCR）を実行し、PDF を生成します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>このドキュメントの言語を選択します。<p>言語オプションについて詳しくは、この記事の<a href="#convert-document-to-pdf-file" class="MCXref xref" >ドキュメントを PDF ファイルに変換</a>を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL OCR type]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Modified original image] タイプでは、テキストが検索可能および選択可能であることが保証されますが、クリーンアッププロセス中に元の画像が変更されてから（例えば、傾き補正など）、非表示のテキストレイヤーがその上に配置されます。このタイプでは、不要なアーティファクトが削除され、シナリオによっては文書がより読みやすくなる可能性があります。 </p> </li> 
     <li> <p>[!UICONTROL Unchangedoriginal image] タイプでも、元の画像の上に検索可能なテキストレイヤーがオーバーレイされますが、この場合、元の画像は変更されません。このタイプでは、元の画像に最大限の忠実度が得られます。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL ページ操作]

このモジュールを使用すると、PDF ドキュメント内のページを選択的に回転または削除できます。例えば、縦表示を横表示に変更したり、PDF ドキュメントから特定のページを削除したりできます。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td> <p>ファイルに対して実行するアクションを選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Delete]</b> </p> <p>ドキュメントからページを削除するには、このオプションを選択します。</p><p>削除する各ページ範囲で、「<strong>[!UICONTROL Add]</strong>」をクリックし、ページ範囲の最初と最後のページを入力します。 </p> <p>メモ：   
     <ul> 
      <li> <p>負の数を使用して、ドキュメントの最後から前方向に数えることができます。ドキュメントの最後のページは -1、最後から 2 番目のページは -2 というふうになります。</p> </li> 
      <li> <p>単一ページを削除するには、範囲の開始と終了の両方に同じページ番号を設定します。</p></ul> </li> 
     <li> <p><b>[!UICONTROL Rotate]</b> </p> <p>ページを回転するには、このオプションを選択し、開始時の方向を基準にドキュメントページを回転する角度を時計回りの角度で入力します。</p> <p>ページを縦から横にまたはその逆に回転するには、ページを 90°または 270°回転します。</p> <p>ページが上下逆の場合は、180°回転します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pages]</td> 
   <td> <p>削除する各ページ範囲で、「<strong>[!UICONTROL Add]</strong>」をクリックし、ページ範囲の最初と最後のページを入力します。 </p> <p>メモ：   
     <ul> 
      <li> <p>負の数を使用して、ドキュメントの最後から前方向に数えることができます。ドキュメントの最後のページは -1、最後から 2 番目のページは -2 というふうになります。</p> </li> 
      <li> <p>単一ページを削除するには、範囲の開始と終了の両方に同じページ番号を設定します。</p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF アクセシビリティの自動タグ付け]

このアクションモジュールは、アクセシビリティのユースケースにタグ付けされた PDF を作成します。また、問題をリストアップし修正を提案する、オプションの Microsoft Excel レポートも作成します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shift Headings]</td> 
   <td> <p>文書の見出しを移動するには、このオプションを有効にします。</p> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generate Report]</td> 
   <td> <p>PDF のアクセシビリティの問題とその場所を記載したレポートを生成し、これらの問題の修正方法に関する提案を出すには、このオプションを有効にします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF ファイルのプロパティ]

このツールは、次のようなドキュメントに関する基本情報を抽出します。

* ページ数
* PDF のバージョン
* ファイルが暗号化されているかどうか
* ファイルが線形化されているかどうか
* ファイルに埋め込みファイルが含まれているかどうか

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF ファイルの保護]

このツールは、ユーザーまたは所有者のパスワードを使用して PDF ドキュメントを保護します。また、PDF ドキュメントにおける印刷、編集、コピーなど、特定の機能に対する制限も設定します。暗号化するコンテンツのタイプと暗号化アルゴリズムを選択します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは PDF 形式である必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password Protection Type]</td> 
   <td> <p>パスワードを使用して入力 PDF ドキュメントを暗号化するには、このオプションを有効にします。このオプションを有効にする場合、次のいずれかまたは両方の値を指定して入力する必要があります。 </p> 
    <ul> 
     <li> <p>[!UICONTROL User Password]</p> </li> 
     <li> <p>[!UICONTROL Owner Password] </p> </li> 
    </ul> <p>各パスワードは最大 128 文字までです。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encryption Algorithm]</td> 
   <td> <p>暗号化アルゴリズムを選択します。 </p> 
    <ul> 
     <li> <p>[!UICONTROL AES-128 encryption]</p> <p>パスワードは LATIN-I 文字のみをサポートします。 </p> </li> 
     <li> <p>[!UICONTROL AES-256 encryption]</p> <p>パスワードは Unicode 文字セットをサポートしています</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content to Encrypt]</td> 
   <td> <p>暗号化するコンテンツのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL All content]</p> </li> 
     <li> <p>[!UICONTROL All content except metadata]</p> </li> 
     <li> <p>[!UICONTROL Only embedded data] </p> </li> 
    </ul> <p>「[!UICONTROL Only embedded data]」を選択すると、指定されたアクセス権限が無効になります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permissions]</td> 
   <td> <p>印刷、編集、コンテンツのコピーを許可する権限を選択します。</p> <p>権限設定は、「[!UICONTROL Password Protection Type]」フィールドで [!UICONTROL Owner Password] が設定されている場合にのみ使用されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF ファイルの保護を解除]

このツールは、PDF ドキュメントからセキュリティ（パスワード保護）を削除します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは PDF 形式である必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password]</td> 
   <td>現在ファイルを保護しているパスワードを入力します。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF ファイルの分割]

このアクションモジュールは、PDF ドキュメントを複数の小さなドキュメントに分割します。ファイル数、ファイルあたりのページ数、ページ範囲のどちらで分割するかを指定します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用する接続を選択します。</p> [!DNL Adobe PDF Services] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >[!DNL Adobe PDF Services]</a> への接続の作成を参照してください。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p>ソースファイルは PDF 形式である必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split option]</td> 
   <td>ファイルの分割方法を選択します。 
   <ul>
   <li><p><b>ページ範囲</b></p><p>別のドキュメントに分割する各ページ範囲で、「<b>追加</b>」をクリックし、開始ページと終了ページを入力します。</p></li>
   <li><p><b>ページ数</b></p><p>新規ドキュメントに含めるページ数を入力します。</p></li>
   <li><p><b>ファイル数</b></p><p>ドキュメントを分割する均等サイズのファイルの数を入力します。</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

