---
title: Google Forms モジュール
description: ' [!DNL Adobe Workfront Fusion Google Forms]  モジュールを使用すると、Google Forms で応答を監視、選択、追加、更新または削除できます。'
author: Becky
feature: Workfront Fusion
exl-id: dc017957-c0f8-4206-916f-21ccda346fb9
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1415'
ht-degree: 74%

---

# [!DNL Google Forms] モジュール

Adobe Workfront Fusion [!DNL Google Forms] モジュールを使用すると、[!DNL Google Forms] ージ上の応答を監視、選択、追加、更新、削除できます。

Adobe Workfront Fusion で [!DNL Google Docs] を使用するには、[!DNL Google] アカウントが必要です。 [!DNL Google] アカウントをまだお持ちでない場合は、[!DNL Google] アカウントのヘルプページで作成できます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <p>現在：Workfront Fusion ライセンス要件なし</p>
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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

[!DNL Google Forms] モジュールを使用するには、[!DNL Google] アカウントが必要です。

## Google Forms API の情報

Google Forms コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>2.0.10</td> 
  </tr>
 </tbody> 
 </table>

## フォームからスプレッドシートの作成

フォームの応答を操作するには、まず応答スプレッドシートを作成する必要があります。

1. フォームを開きます。
1. 「**[!UICONTROL 応答]**」タブに移動します。
1. **[!UICONTROL スプレッドシートを作成]** アイコン ![ スプレッドシートアイコン ](/help/workfront-fusion/references/apps-and-modules/assets/spreadsheet-icon.png) をクリックします。

1. 新規スプレッドシートを作成するか、既存スプレッドシートを作成するかを選択します
1. 「**[!UICONTROL 作成]**」をクリックします。

## [!DNL Google Forms] モジュールとそのフィールド

[!DNL Google Forms] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Google Forms]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

#### [!UICONTROL 応答の監視]

フォームで新しい応答を監視します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>新しい応答を監視するフォームの応答を含むスプレッドシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> フォームの応答を含むシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Row with headers]</td> 
   <td>テーブルのヘッダー行を指定します。デフォルトの行は <code>A1:Z1</code> です。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value Render Option]</td> 
   <td> <p>出力で値をレンダリングする方法を指定します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Formatted value]</strong> </p> <p>値はセルの書式設定に従って計算され、返信で書式設定されます。書式設定は、リクエスト元のユーザーのロケールではなく、スプレッドシートのロケールに基づいて行われます。例えば、<code>A1</code> が <code>1. 23</code>、<code>A2 </code> が <code>=A1</code> で通貨の形式に設定されている場合、<code>A2</code> は <code>$1. 23</code> を返します。</p> </li> 
     <li> <p><strong>[!UICONTROL Unformatted value]</strong> </p> <p>値は計算されますが、返信では書式設定されません。例えば、<code>A1</code> が <code>1. 23</code>、<code>A2 </code> が <code>=A1</code> で通貨の形式に設定されている場合、<code>A2</code> は数値 <code>1. 23</code> を返します。</p> </li> 
     <li> <p><strong>[!UICONTROL Formula]</strong> </p> <p>値は計算されません。返信には数式が含まれます。例えば、<code>A1</code> が <code>1. 23</code>、<code>A2 </code> が <code>=A1</code> で通貨の形式に設定されている場合、<code>A2</code> は <code>=A1</code> を返します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Date and time render option]</td> 
   <td>日付、時間および期間を出力に表示する方法を選択します。[!UICONTROL Value Render Option] が [!UICONTROL Formatted Value] に設定されている場合、このフィールドは無視されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p> Workfront Fusion が 1 つのサイクルで処理する応答の最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL 応答の追加]](#add-a-response)
* [[!UICONTROL 応答の削除]](#delete-a-response)
* [[!UICONTROL 応答の更新]](#update-a-response)

#### [!UICONTROL 応答の追加]

このモジュールは、フォームのスプレッドシートの下部に新しい応答を追加します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>応答を追加するシートが含まれているスプレッドシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> フォームの応答を含むシートを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>シートの列に目的の値を入力します。 列は、シートに基づいて使用できます。</p> <p>[!UICONTROL Timestamp] 列には、次の値を使用します。</p><pre>formatDate(now;DD/MM/YYYY HH:mm;UTC)</pre> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> ユーザーが入力した値は解析されず、そのまま保存されます。 </p> </li> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>値は、ユーザーが UI に入力したかのように解析されます。数値は数値のまま保持されますが、文字列の場合は [!DNL Google Sheets] UI を経由してセルにテキストを入力する時に適用されるルールと同じルールに従って数値、日付、もしくは他の形式に変換される可能性があります。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Insert data option]</td> 
   <td> <p>新しいデータが入力されるときの既存のデータの変更方法を指定します。 </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Overwrite]</strong> </p> <p>新しいデータは、書き込まれたエリアの既存のデータを上書きします。シートの末尾にデータを追加すると、新しい行または列が挿入され、データを書き込むことができます。</p> </li> 
     <li> <p><strong>[!UICONTROL Insert rows]</strong></p> <p>行が新しいデータ用に挿入されます。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 応答の削除]

このモジュールは、選択した応答を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>応答を削除するシートを含むスプレッドシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> フォームの応答を含むシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Row number]</p> </td> 
   <td> <p>削除する行の数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 応答の更新]

このモジュールは、選択された応答を更新します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>応答を更新するシートが含まれているスプレッドシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> フォームの応答を含むシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Row number]</p> </td> 
   <td> <p>更新する行の数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>目的の列に新しい値を入力します。 列は、シートに基づいて使用できます。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> ユーザーが入力した値は解析されず、そのまま保存されます。 </p> </li> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>値は、ユーザーが UI に入力したかのように解析されます。数値は数値のまま保持されますが、文字列の場合は [!DNL Google Sheets] UI を経由してセルにテキストを入力する時に適用されるルールと同じルールに従って数値、日付、もしくは他の形式に変換される可能性があります。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL 応答の検索]](#search-responses)
* [[!UICONTROL 応答の検索（詳細]）](#search-responses-advanced)

#### [!UICONTROL 応答の検索]

このモジュールは、指定された条件に一致する応答を返します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
    <td>接続</td>
   <td> <p>[!DNL Google] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Spreadsheet]</td>
   <td> <p>検索するフォームを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Sheet] </td>
   <td> <p>フォームの応答を含むシートを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Column range]</td>
   <td> <p> 検索する列の範囲を選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>応答の検索に使用するフィルターを定義します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Sort Order] </td>
   <td> <p>返された応答を昇順または降順で並べ替えるかどうかを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Order By]</td>
   <td> <p> 返された応答を並べ替える列を選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value Render Option]</td> 
   <td> <p>出力で値をレンダリングする方法を指定します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Formatted value]</strong></p> <p>値はセルの書式設定に従って計算され、返信で書式設定されます。書式設定は、リクエスト元のユーザーのロケールではなく、スプレッドシートのロケールに基づいて行われます。例えば、<code>A1</code> が <code>1. 23</code>、<code>A2 </code> が <code>=A1</code> で通貨の形式に設定されている場合、<code>A2</code> は <code>$1. 23</code> を返します。</p> </li> 
     <li> <p><strong>[!UICONTROL Unformatted value]</strong> </p> <p>値は計算されますが、返信では書式設定されません。例えば、<code>A1</code> が <code>1. 23</code>、<code>A2 </code> が <code>=A1</code> で通貨の形式に設定されている場合、<code>A2</code> は数値 <code>1. 23</code> を返します。</p> </li> 
     <li> <p><strong>[!UICONTROL Formula]</strong> </p> <p>値は計算されません。返信には数式が含まれます。例えば、<code>A1</code> が <code>1. 23</code>、<code>A2 </code> が <code>=A1</code> で通貨の形式に設定されている場合、<code>A2</code> は <code>=A1</code> を返します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Date and time render option]</td>
    <td>日付、時間および期間を出力に表示する方法を選択します。「[!UICONTROL Value Render]」オプションが「Formatted Value」に設定されている場合、このフィールドは無視されます。 </td>
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Maximum number of returned responses]</td>
   <td> <p> Workfront Fusion が 1 つのサイクルで返す応答の最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 応答の検索（詳細）]

このモジュールは、[[!DNL Google Charts Query Language]](https://developers.google.com/chart/interactive/docs/querylanguage?hl=ja) を使用して検索を実行します。このモジュールは行番号を返しません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
   <td> <p>[!DNL Google] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Spreadsheet]</td>
   <td> <p>検索するシートが含まれているスプレッドシートを選択します。</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Sheet]</td>
   <td> <p> フォームの応答を含むシートを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p><a href="https://developers.google.com/chart/interactive/docs/querylanguage?hl=ja">[!DNL Google Charts Query Language]</a> を使用して検索クエリを定義します。</p> <p>例：<code>select * where C = "John"</code> は、C 列が「John」である行のすべての値を取得します。</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Maximum number of returned rows]</td>
   <td> <p> Workfront Fusion が 1 つのサイクルで返す応答の最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>
