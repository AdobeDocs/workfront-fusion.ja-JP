---
title: JSONata モジュール
description: Adobe Workfront Fusion JSONata コネクタは、Adobe Workfront Fusion がデータコンテンツをさらに操作できるように、データを JSON 形式で処理するモジュールを提供します。
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 5%

---

# [!UICONTROL JSONata] モジュール

Adobe Workfront Fusion [!UICONTROL JSONata] コネクタを使用すると、JSON オブジェクトをクエリできます。 このモジュールには接続は必要ありません。

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



## JSONata モジュールとそのフィールド

### 評価

このアクションモジュールは JSON オブジェクトをクエリし、配列を返します。

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
   <td> 評価する JSON オブジェクトを入力します。  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stringify 出力 ] </td> 
   <td> 出力を文字列に変換するには、このオプションを有効にします。  </td> 
  </tr> 
  </tbody>
  </table>

>[!BEGINSHADEBOX]

**例**：

目的は、次の JSON オブジェクトから名前の配列を返すことです。

```JSON
{
  "people": [
    { "name": "Alice", "age": 30 },
    { "name": "Bob", "age": 25 },
    { "name": "Charlie", "age": 35 }
  ]
}
```

1. 「式」フィールドに「`people.name`」と入力します。
1. データフィールドに、JSON オブジェクトを入力します。

モジュールは、JSON オブジェクトから取得した名前の配列を返します。

>[!ENDSHADEBOX]



### JSONata MCP

このアクションモジュールは、指定された入出力スキーマを分析して JSONata 式を生成します。 入力を出力に変換する式の生成に Model Context Protocol （MCP）で使用されるスキーマを指定します。




<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>このモジュールに使用するラージ言語モデル （LLM）への接続に使用する接続を選択します。</p> <p>現在は、Anthropic API キーのみがサポートされています。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 入力スキーマ ]</td> 
   <td> <p>この式に使用する入力スキーマを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 出力スキーマ ]</td> 
   <td> <p>この式に使用する出力スキーマを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
