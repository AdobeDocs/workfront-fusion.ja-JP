---
title: テキストパーサー
description: テキストパーサーツールを使用すると、他の [!DNL Adobe Workfront Fusion] シナリオモジュールで使用できるようにテキストを解析できます。テキストパーサーには接続は必要ありません。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 885d714e-fc09-41a2-89dc-ebe29a355e43
source-git-commit: 4fa892b7875af2fcabaf26b375925af7a8cad2a0
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 78%

---

# [!UICONTROL Text parser]

[!UICONTROL Text parser tool] を使用して、他の [!DNL Adobe Workfront Fusion] シナリオモジュールで使用するテキストを解析できます。 [!UICONTROL Text parser] には接続は必要ありません。

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
   <p>Workfront Fusion のライセンス要件はありません。</p>
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

## テキストパーサー API 情報

テキストパーサーコネクターでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v2</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Text parser] モジュールとそのフィールド

[!UICONTROL Text parser] モジュールを設定する際、[!DNL Adobe Workfront Fusion] に以下のフィールドが表示されます。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 変換サービス

* [[!UICONTROL Get Elements from HTML]](#get-elements-from-html)
* [[!UICONTROL Get Elements from text]](#get-elements-from-text)
* [[!UICONTROL HTML to Text]](#html-to-text)
* [[!UICONTROL Match Pattern]](#match-pattern)
* [[!UICONTROL Replace]](#replace)

#### [!UICONTROL Get Elements from HTML]

必要な要素を HTML コードから取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module finds no matches]</td> 
   <td> <p>結果が返されない場合にモジュールがシナリオを停止しないようにするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Element type]</td> 
   <td> <p> HTML コードから取得する要素のタイプを選択します。 </p> 
    <ul> 
     <li>[!UICONTROL Image]</li> 
     <li>[!UICONTROL Link]</li> 
     <li>[!UICONTROL iFrame element(s)]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL HTML] </td> 
   <td> <p>指定した要素タイプを取得する HTML コードを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Elements from text]

指定されたパターンに基づいてテキストから要素を解析します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Input text]</td> 
   <td> <p>解析するテキストを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Pattern]</td> 
   <td> <p>テキストから解析する要素を反映するパターンを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Ignore Duplicate Occurrences]</td> 
   <td> <p>テキスト要素の重複発生を無視する場合は、このチェックボックスをオンにします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL HTML to Text]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL HTML] </td> 
   <td> <p>プレーンテキストに変換する HTML コードを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Line break] </td> 
   <td> <p>新規行（改行）のタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Uppercase headings]</p> </td> 
   <td> <p>見出しタグ（&lt;h2&gt; &lt;/h2&gt; など）で囲まれたテキストを大文字テキストに変換する場合は、このオプションを有効にします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Match Pattern]

[!UICONTROL Match pattern] モジュールを使用すると、指定されたテキストから検索パターンに一致する文字列要素を見つけて抽出できます。 このモジュールは正規表現（regex または regexp と表記される場合もあります）を使用します。

正規表現とは、各文字が特別な意味を持つメタ文字、またはリテラルの意味を持つ正規文字のいずれかである文字のシーケンスです。これらの文字とメタ文字は、テキストの検索に使用できるパターンを識別します。例えば、名前を検索する場合、大文字で始まる 2 つの連続した単語で構成されるパターンを検索する正規表現を設定できます。正規表現は、テキストを検索および操作するための強力なツールです。

正規表現についての詳しい説明は、この記事の範囲外です。次のリソースをお勧めします。

* メタ文字の完全なリストについては、MDN web ドキュメントの[正規表現](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)を参照してください。
* 正規表現の作成方法を説明するチュートリアルについては、[RegexOne](https://regexone.com/) をお勧めします。
* 正規表現を試したい方には、[正規表現 101](https://regex101.com/) web サイトをお勧めします。左パネルで ECMAScript（JavaScript）FLAVOR を選択します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Pattern] </td> 
   <td> <p>正規表現のパターンを入力します。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span><code>[+-]?(\d+(\.\d+)?|\.\d+)([eE][+-]?\d+)?</code> で指定されたテキスト内のすべての数字を抽出します。</p> <p>メモ：  <p>パターンでは、少なくとも 1 つのキャプチャグループが括弧内に含まれている必要があります<code>()</code>。パターンにキャプチャグループが含まれていない場合、出力バンドルは空になります。</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Global match]</td> 
   <td> <p>テキスト内のすべての一致を取得するには、このオプションを有効にします。一致はそれぞれ、個別のバンドルに出力されます。このオプションが無効になっている場合、モジュールは最初のエントリのみを取得します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Case sensitive]</td> 
   <td> <p> このモジュールでテキストの大文字と小文字を区別して扱うには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Multiline] </td> 
   <td> <p>このオプションを有効にすると、開始メタ文字と終了メタ文字（<code>^</code> および <code>$</code>）が、入力文字列全体の先頭または末尾だけでなく、各行の先頭または末尾と一致するようになります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Singleline]</td> 
   <td>このオプションを有効にすると、ピリオド （.）が改行文字（<code>\n</code>）と一致します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p>結果が返されない場合にモジュールがシナリオを停止しないようにするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text] </td> 
   <td> <p>パターンと一致させるテキストを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace]

指定した値または正規表現について入力したテキストを検索し、結果を新しい値に置き換えます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Pattern] </td> 
   <td> <p>検索語句を入力します。また、正規表現を使用することもできます。正規表現について詳しくは、<a href="#match-pattern" class="MCXref xref">[!UICONTROL Match Pattern]</a> モジュールを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New value]</td> 
   <td> <p> 検索語句を置き換える値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Global match]</td> 
   <td> <p>テキスト内のすべての一致を取得するには、このオプションを有効にします。一致はそれぞれ、個別のバンドルに出力されます。このオプションが無効になっている場合、モジュールは最初のエントリのみを取得します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Case sensitive]</td> 
   <td> <p> このモジュールでテキストの大文字と小文字を区別して扱うには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Multiline] </td> 
   <td> <p>このオプションを有効にすると、開始メタ文字と終了メタ文字（<code>^</code> および <code>$</code>）が、入力文字列全体の先頭または末尾だけでなく、各行の先頭または末尾と一致するようになります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Singleline]</td> 
   <td>このオプションを有効にすると、ピリオド （.）が改行文字（<code>\n</code>）と一致します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text] </td> 
   <td> <p>検索するテキストを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### データスクレーピング

データスクレーピング（web スクレーピング、データ抽出、web 収集とも呼ばれます）とは、web サイトからデータを収集し、ローカルのデータベースまたはスプレッドシートに保存するプロセスです。Web サイトからデータを削除する場合で、かつ正規表現に慣れていない場合は、データスクレーピングツールを使用できます。

データ収集ツールが REST API を提供する場合は、アドビのユニバーサルエクスペリ [[!UICONTROL HTTP] ンスモジュールおよび [Webhook](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md) モジュールを使用して ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors) このツールに接続できます。

## テキストパーサーのトラブルシューティング

出力するテキストパーサーを取得できない場合は、この情報を使用します。

>[!BEGINSHADEBOX]

例：

ファイルのファイル形式「filename.docx」をパースする必要があり、ファイル名の拡張子は DOCX から CSV までPDFによって異なります。

この場合に使用できる式は [!DNL \..+] です。

この正規表現は通常、完全一致を返します。

ただし、テキストパーサーにこの式を実装しても、一致しません。

![](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-you-dont-get-a-match-350x365.png)

この理由は、「i」が一致あたりの一致数のみを示すので、この場合は 2 回一致があるので、「i」の後に数値「1」と「2」が続きます。このユースケースの場合、2 番目に一致した値のみをフィルターで照合または渡す必要がある場合は、数値で表される値を指定できます。

![](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-matches-350x355.png)

解析する部分に括弧を追加する必要のある一致値を取得するには（例えば、「filename.docx」から「docx」のみを抽出する）、このケースシナリオで使用する正規表現式に従って、括弧を \ に適用する必要があります。(.+)

これにより、DOCX が取り込まれ、グループに配置され、「.」が残ります。それ以外

![](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-get-matches-350x592.png)

次の図に示す出力では、キャプチャするグループは任意の文字（行末文字を除く）に一致します。

![](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-output-350x389.png)

正規表現も組み込んだもう 1 つの回避策は、replace 関数を使用することです

`{{replace("abcdefghijklmno pqr stuvw xyz.docx"; "/.\./"; ".")}}`

次に、`abcdefghijklmno pqr stuvw xyz.docx` を実際のファイル名変数に置き換えます。

>[!ENDSHADEBOX]
