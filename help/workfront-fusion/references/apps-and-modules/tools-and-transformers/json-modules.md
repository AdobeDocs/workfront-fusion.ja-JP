---
title: JSON モジュール
description: Adobe Workfront Fusion JSON アプリは、Adobe Workfront Fusion がデータコンテンツとより深く連携したり、新しい JSON コンテンツを作成したりできるように、JSON 形式のデータを処理するモジュールを提供します。
author: Becky
feature: Workfront Fusion
exl-id: f8b281c5-bb63-4412-98c5-d82f45f8eafc
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 82%

---

# [!UICONTROL JSON] モジュール

Adobe Workfront Fusion [!UICONTROL JSON] アプリには、Adobe Workfront Fusion がデータコンテンツをさらに操作したり、新しい JSON コンテンツを作成したりできるように、データを JSON 形式で処理するモジュールが用意されています。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++



## JSON 解析時の考慮事項

* [データ構造](#data-structure)
* [コレクションと配列](#collection-vs-array)

### データ構造

データ構造は、JSON データの編成方法を記述し、個々の JSON 項目をシナリオ内の他のモジュールにマッピングできるようにします。データ構造を指定しない場合は、モジュールを手動で実行すると、Workfront Fusion は指定された JSON から構造を構築します。

1. [!UICONTROL JSON を解析]モジュールをシナリオに追加します。
1. 「**[!UICONTROL JSON 文字列]**」フィールドで、データ構造を作成する JSON を入力します。
1. 他のモジュールを [!UICONTROL JSON を解析]モジュールにはまだ結びつけません。Workfront Fusion は JSON データの構造をまだ把握していないので、「JSON を解析 [!UICONTROL  モジュールのデータを、シナリオ内の他のモジュールにマッピングすることはでき ] せん。
1. シナリオを手動で実行します。これにより、[!UICONTROL JSON を解析]モジュールが、指定した JSON から JSON 構造を識別できるようになります。
1. 次のモジュールを接続できるようになりました。JSON を解析モジュールの項目をマッピングに使用できるようになりました。

詳しくは、[[!UICONTROL Adobe Workfront Fusion のデータ構造]](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)を参照してください。

### コレクションと配列

「JSON 文字列」フィールドにコレクション `{ ... }` が含まれている場合、出力はコレクションの項目を含む単一のバンドルです。

>[!BEGINSHADEBOX]

**例：**

```
{
    "name" : "Peter",

    "ID" : 1>}
```


![JSON コレクション ](/help/workfront-fusion/references/apps-and-modules/assets/json-collection.png)

>[!ENDSHADEBOX]

JSON 文字列フィールドに配列 `[ ... ]` が含まれている場合、出力は一連のバンドルになります。各バンドルには、配列の 1 つの要素が含まれます。

>[!BEGINSHADEBOX]

**例：**

```
[
  {
    "name" : "Peter",
    "ID" : 1
  },

  {
    "name" : "Mike",
    "ID" : 2
  }
]
```

![JSON 配列 ](/help/workfront-fusion/references/apps-and-modules/assets/json-array.png)

>[!ENDSHADEBOX]

## [!UICONTROL JSON] モジュールとそのフィールド

[!DNL JSON] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらに加えて、アプリやサービスでのアクセスレベルなどの要因に応じて、追加の JSON フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [JSON を XML に変換](#convert-json-to-xml)
* [JSON を解析](#parse-json)
* [JSON を作成](#create-json)
* [JSON を変換](#transform-json)

### アグリゲーター

#### [!UICONTROL JSON に集計]

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

#### [!UICONTROL JSON を XML に変換]

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

#### [!UICONTROL JSON を作成]

このアクションモジュールは、データ構造から JSON を作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">データ構造</td> 
   <td> <p>JSON の作成に使用するデータ構造を選択します。詳しくは、この記事の<a href="#data-structure" class="MCXref xref">データ構造</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">インデント</td> 
   <td> <p>この JSON に使用するインデントを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL JSON を解析]

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

#### [!UICONTROL JSON を変換]

このアクションモジュールは、オブジェクトを json 文字列に変換します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">インデント</td> 
   <td> <p>この JSON に使用するインデントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object]</td> 
   <td> <p>JSON に変換するオブジェクトを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

## データレコードを JSON に変換中

>[!BEGINSHADEBOX]

**例：**&#x200B;次の例は、データレコードを [!DNL Google Sheets] から JSON 形式に変換する方法を示しています。

1. データを取得するには、シナリオに [!DNL Google Sheets]／[!UICONTROL 行を選択]モジュールを配置します。[!DNL Google] スプレッドシートから行を取得するモジュールを設定します。「**[!UICONTROL 返される行の最大数]**」を小さい数に設定しますが、テスト用に 1 より大きい値（例：3）に設定します。[!DNL Google Sheets] モジュールを右クリックし、「**[!UICONTROL このモジュールのみを実行]**」を選択して実行します。モジュールの出力を確認します。

1. [!DNL Google Sheets] モジュールの後に、[!UICONTROL 配列アグリゲーター]モジュールを接続します。モジュール設定で、「**[!UICONTROL ソースノード]**」フィールドから [!DNL Google Sheets] モジュール を選択します。その他のフィールドは、現時点ではそのままにしておきます。

1. [!UICONTROL 配列アグリゲーター]モジュールの後に [!UICONTROL JSON]／[!UICONTROL JSON を作成]モジュールを接続します。モジュールの設定には、JSON 形式を記述したデータ構造が必要です。「**[!UICONTROL 追加]**」をクリックして、データ構造の設定を開きます。このデータ構造を作成する最も簡単な方法は、JSON サンプルから自動的に生成することです。「**[!UICONTROL ジェネレーター]**」をクリックし、JSON サンプルを「**[!UICONTROL サンプルデータ]**」フィールドに貼り付けます。

   **例：**

   ```
   {
   "books": [
   {
   "id": "ID",
   "title": "Title",
   "author": "Author"
   }
   ]
   }
   ```

1. 「**[!UICONTROL 保存]**」をクリックします。これで、データ構造の「[!UICONTROL 仕様]」フィールドに、生成された構造が含まれます。
1. データ構造の名前をより具体的なものに変更し、「**[!UICONTROL 保存]**」をクリックします。ルート配列属性に対応するフィールドは、JSON モジュールの設定で、マッピング可能なフィールドとして表示されます。

1. フィールドの横にある「**[!UICONTROL マップ]**」ボタンをクリックし、Array aggregator から出力された `Array[]` 項目をマッピングします。

1. 「**[!UICONTROL OK]**」をクリックして、[!UICONTROL JSON] モジュールの設定を閉じます。

1. [!UICONTROL Array Aggregator] モジュールの設定を開きます。**[!UICONTROL ターゲット構造]**&#x200B;を[!UICONTROL カスタム]から、ルート配列属性に対応する [!UICONTROL JSON] モジュールのフィールドに変更します。[!DNL Google Sheets] モジュールの項目を適切なフィールドにマッピングします。

1. 「**[!UICONTROL OK]**」をクリックして、[!UICONTROL Array Aggregator] モジュールの設定を閉じます。

1. シナリオを実行します。

   [!UICONTROL JSON] モジュールは正しい JSON 形式を出力します。

1. [!DNL Google Sheets] モジュールの設定を開き、「[!UICONTROL 返される行の最大数]」の数値を増やしてスプレッドシートの行数よりも大きくなるようにし、すべてのデータを処理できるようにします。

>[!ENDSHADEBOX]

## トラブルシューティング

### [!UICONTROL JSON を解析]モジュールからデータをマッピングできません

JSON コンテンツが [!UICONTROL JSON を解析]モジュールに適切にマッピングされ、データ構造が正しく定義されていることを確認します。詳しくは、この記事の[データレコードを JSON に変換](#transforming-data-records-to-json)を参照してください。

### JSON で条件ステートメントを使用するとモジュールが失敗する

`if` などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。

>[!BEGINSHADEBOX]

**例：**

![JSON の引用符 ](/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png)

>[!ENDSHADEBOX]
