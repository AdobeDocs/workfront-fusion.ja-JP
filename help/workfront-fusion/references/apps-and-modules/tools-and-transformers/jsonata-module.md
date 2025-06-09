---
title: JSONata モジュール
description: Adobe Workfront Fusion JSONata コネクタは、Adobe Workfront Fusion がデータコンテンツをさらに操作できるように、データを JSON 形式で処理するモジュールを提供します。
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: da3bf98f8254228598372fed8c06d6318718721f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 13%

---

# [!UICONTROL JSONata] モジュール

[!DNL Adobe Workfront Fusion] [!UICONTROL JSONata] コネクタを使用すると、JSON オブジェクトをクエリできます。 このモジュールには接続は必要ありません。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規：[!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：[!DNL Adobe Workfront Fusion] を購入してください。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

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
   <td role="rowheader">[!UICONTROL Stringify 出力 &#x200B;] </td> 
   <td> 出力を文字列に変換するには、このオプションを有効にします。  </td> 
  </tr> 
  </tbody>
  </table>

>[!BEGINSHADEBOX]

**例**:

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
   <td role="rowheader">[!UICONTROL 入力スキーマ &#x200B;]</td> 
   <td> <p>この式に使用する入力スキーマを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 出力スキーマ &#x200B;]</td> 
   <td> <p>この式に使用する出力スキーマを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
