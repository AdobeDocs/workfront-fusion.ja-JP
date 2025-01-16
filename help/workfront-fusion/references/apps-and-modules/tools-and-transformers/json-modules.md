---
title: JSON モジュール
description: Adobe Workfront Fusion JSON アプリは、Adobe Workfront Fusion がデータコンテンツとより深く連携したり、新しい JSON コンテンツを作成したりできるように、JSON 形式のデータを処理するモジュールを提供します。
author: Becky
feature: Workfront Fusion
exl-id: f8b281c5-bb63-4412-98c5-d82f45f8eafc
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 67%

---

# [!UICONTROL JSON] モジュール

[!DNL Adobe Workfront Fusion] [!UICONTROL JSON] アプリは、データを JSON 形式で処理するモジュールを提供し、[!DNL Adobe Workfront Fusion] ーザーがデータコンテンツをさらに操作したり、新しい JSON コンテンツを作成したりできます。

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
   <p>レガシーライセンス要件：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration], [!UICONTROL [!DNL Workfront Fusion] for Work Automation]</p>
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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

## JSON を解析

* [データ構造](#data-structure)
* [コレクションと配列](#collection-vs-array)

### データ構造

データ構造は、JSON データの編成方法を記述し、個々の JSON 項目をシナリオ内の他のモジュールにマッピングできるようにします。データ構造を指定しない場合、モジュールを手動で実行すると、[!DNL Workfront Fusion] が指定された JSON から構造を作成します。

1. [!UICONTROL Parse JSON] モジュールをシナリオに追加します。
1. 「**[!UICONTROL JSON String]**」フィールドに、データ構造を構築する JSON を入力します。
1. その他のモジュールはまだ [!UICONTROL Parse JSON] モジュールに接続しないでください。 [!DNL Workfront Fusion] は JSON データの構造をまだ知らないので、[!UICONTROL Parse JSON] モジュールのデータをシナリオ内の他のモジュールにマッピングすることはまだできません。
1. シナリオを手動で実行します。これにより、指定した JSON から [!UICONTROL Parse JSON] モジュールが JSON 構造を識別できるようになります。
1. 次のモジュールを接続できるようになりました。JSON を解析モジュールの項目をマッピングに使用できるようになりました。

詳しくは、[[!UICONTROL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md) のデータ構造を参照してください。

### コレクションと配列

「JSON 文字列」フィールドにコレクション `{ ... }` が含まれている場合、出力はコレクションの項目を含む単一のバンドルです。

>[!INFO]
>
>**例：**
>
>```
>{
>    "name" : "Peter",
>
>    "ID" : 1
>}
>```
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/json-collection.png)

JSON 文字列フィールドに配列 `[ ... ]` が含まれている場合、出力は一連のバンドルになります。各バンドルには、配列の 1 つの要素が含まれます。

>[!INFO]
>
>**例：**
>
>```
>[
>  {
>    "name" : "Peter",
>    "ID" : 1
>  },
>
>  {
>    "name" : "Mike",
>    "ID" : 2
>  }
>]
>```
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/json-array.png)

## [!UICONTROL JSON] モジュールとそのフィールド

[!DNL JSON] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリやサービスでのアクセスレベルなどの要因に応じて、追加の JSON フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [JSON を XML に変換](#convert-json-to-xml)
* [JSON を解析](#parse-json)
* [JSON を作成](#create-json)
* [JSON を変換](#transform-json)

### アグリゲーター

#### [!UICONTROL Aggregate to JSON]

この集約モジュールは、以前のモジュールからの出力を JSON に集計します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module] </td> 
   <td> <p>JSON に集計するデータを出力するモジュールを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>JSON の作成に使用するデータ構造を選択します。データ構造は、このモジュールで使用できる他のフィールドを決定します。詳しくは、記事内の<a href="#data-structure" class="MCXref xref">データ構造</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Indentation]</td> 
   <td> <p> タブ、2 つのスペース、4 つのスペースのどれを使用して JSON のインデントを設定するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by]</td> 
   <td>集約出力をグループ化する式を定義します。この式には、1 つ以上のマッピングされた項目を含めることができます。集計されたデータは、この式の値を使用してグループに分割されます。各グループは、キー（評価された式）と値（集約されたテキスト）を持つ個別のバンドルとして出力されます。キーを後続のモジュールのフィルターとして使用できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>結果がない場合にシナリオを停止するには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

### 変換サービス

* [JSON を XML に変換](#convert-json-to-xml)
* [JSON を作成](#create-json)
* [JSON を解析](#parse-json)
* [JSON を変換](#transform-json)

#### [!UICONTROL Convert JSON to XML]

このアクションモジュールは、JSON 文字列を XML に変換します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>XML に変換する JSON を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create JSON]

このアクションモジュールは、データ構造から JSON を作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">データ構造</td> 
   <td> <p>JSON の作成に使用するデータ構造を選択します。詳しくは、この記事の<a href="#data-structure" class="MCXref xref">データ構造</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Parse JSON]

このアクションモジュールは、JSON 文字列を解析してデータ構造にし、JSON 文字列内のデータにアクセスできるようにします。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>JSON の作成に使用するデータ構造を選択します。詳しくは、この記事の<a href="#data-structure" class="MCXref xref">データ構造</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>解析する JSON を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Transform JSON]

このアクションモジュールは、オブジェクトを json 文字列に変換します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object]</td> 
   <td> <p>JSON に変換するオブジェクトを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

## データレコードを JSON に変換中

>[!INFO]
>
>**例：**&#x200B;次の例は、データレコードを [!DNL Google Sheets] から JSON 形式に変換する方法を示しています。
>
>1. [!DNL Google Sheets]/[!UICONTROL Select rows] モジュールをシナリオに配置して、データを取得します。 [!DNL Google] スプレッドシートから行を取得するモジュールを設定します。テスト目的で&#x200B;**[!UICONTROL Maximum number of returned rows]** を小さい数に、1 より大きい数に設定します（例：3）。 [!DNL Google Sheets] モジュールを右クリックして「**[!UICONTROL Run this module only]**」を選択し、実行します。 モジュールの出力を確認します。
>
>1. [!UICONTROL Array Aggregator] モジュールを [!DNL Google Sheets] モジュールの後に接続します。 モジュールの設定で、「**[!UICONTROL Source node]**」フィールドの [!DNL Google Sheets] モジュールを選択します。 その他のフィールドは、現時点ではそのままにしておきます。
>
>1. [!UICONTROL JSON]/[!UICONTROL Create JSON] モジュールを [!UICONTROL Array Aggregator] モジュールの後に接続します。 モジュールの設定には、JSON 形式を記述したデータ構造が必要です。「**[!UICONTROL Add]**」をクリックして、データ構造の設定を開きます。 このデータ構造を作成する最も簡単な方法は、JSON サンプルから自動的に生成することです。「**[!UICONTROL Generator]**」をクリックし、JSON サンプルを「**[!UICONTROL Sample data]**」フィールドに貼り付けます。
>
>     **例：**
>
>     ```
>     {
>     
>     "books": [
>     
>     {
>     
>     "id": "ID",
>     
>     "title": "Title",
>     
>     "author": "Author"
>     
>     }
>     
>     ]
>     
>     }
>     
>     ```
>
>1. 「**[!UICONTROL Save]**」をクリックします。 生成された構造がデータ構造内の [!UICONTROL Specification] フィールドに含まれるようになりました。
>1. データ構造の名前をより具体的な名前に変更し、「**[!UICONTROL Save]**」をクリックします。 ルート配列属性に対応するフィールドは、JSON モジュールの設定で、マッピング可能なフィールドとして表示されます。
>
>1. フィールドの横にある「**[!UICONTROL Map]**」ボタンをクリックし、配列アグリゲータ出力から `Array[]` の項目をフィールドにマップします。
>
>1. 「**[!UICONTROL OK]**」をクリックして、[!UICONTROL JSON] モジュールの設定を閉じます。
>
>1. [!UICONTROL Array Aggregator] モジュールの設定を開きます。 **[!UICONTROL Target structure]** を [!UICONTROL Custom] から、ルート配列属性に対応する [!UICONTROL JSON] モジュールのフィールドに変更します。 [!DNL Google Sheets] モジュールの項目を適切なフィールドにマッピングします。
>
>1. 「**[!UICONTROL OK]**」をクリックして、[!UICONTROL Array Aggregator] モジュールの設定を閉じます。
>
>1. シナリオを実行します。
>
>[!UICONTROL JSON] モジュールは、正しい JSON 形式を出力します。
>
>1. [!DNL Google Sheets] モジュールの設定を開き、[!UICONTROL Maximum number of returned rows] 数をスプレッドシートの行数より大きくして、すべてのデータを処理します。

## トラブルシューティング

### [!UICONTROL Parse JSON] モジュールからデータをマッピングできません

JSON コンテンツが [!UICONTROL Parse JSON] モジュールに正しくマッピングされ、データ構造が正しく定義されていることを確認します。 詳しくは、この記事の[データレコードを JSON に変換](#transforming-data-records-to-json)を参照してください。

### JSON で条件ステートメントを使用するとモジュールが失敗する

`if` などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。

>[!INFO]
>
>**例：**
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png)
