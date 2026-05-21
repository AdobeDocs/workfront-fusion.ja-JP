---
title: JSONata モジュール
description: Adobe Workfront Fusion JSONata コネクタには、Adobe Workfront Fusionがデータコンテンツをさらに処理できるように、JSON形式でデータを処理するモジュールが用意されています。
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
TQID: https://experienceleague.adobe.com/luvZBccaWY5-8muR71o8C82qVROYJvcuAqt3Ol2LZac
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 30%

---

# [!UICONTROL JSONata] モジュール

Adobe Workfront Fusion [!UICONTROL JSONata] コネクタを使用すると、JSON オブジェクトをクエリできます。 このモジュールは接続を必要としません。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++



## JSONata モジュールとそのフィールド

### 評価

このアクションモジュールは、JSON オブジェクトをクエリし、配列を返します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expression]</td> 
   <td>JSON オブジェクトの評価に使用する式を入力します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data] </td> 
   <td> 評価するJSON オブジェクトを入力します。  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stringify出力] </td> 
   <td> 出力を文字列に変換するには、このオプションを有効にします。  </td> 
  </tr> 
  </tbody>
  </table>

>[!BEGINSHADEBOX]

**例**：

目標は、次のJSON オブジェクトから名前の配列を返すことです。

```JSON
{
  "people": [
    { "name": "Alice", "age": 30 },
    { "name": "Bob", "age": 25 },
    { "name": "Charlie", "age": 35 }
  ]
}
```

1. 式フィールドに`people.name`と入力します。
1. 「データ」フィールドにJSON オブジェクトを入力します。

このモジュールは、JSON オブジェクトから取得した名前の配列を返します。

>[!ENDSHADEBOX]



### JSONata MCP

このアクションモジュールは、指定された入出力スキーマを分析してJSONata式を生成します。 スキーマを指定します。このスキーマは、モデル コンテキスト プロトコル（MCP）が使用して、入力を出力に変換する式を生成します。




<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールで使用する大規模言語モデル（LLM）への接続に使用する接続を選択します。</p> <p>現時点では、Anthropic API キーのみがサポートされています。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 入力スキーマ &#x200B;]</td> 
   <td> <p>この式に使用する入力スキーマを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 出力スキーマ &#x200B;]</td> 
   <td> <p>この式に使用する出力スキーマを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
