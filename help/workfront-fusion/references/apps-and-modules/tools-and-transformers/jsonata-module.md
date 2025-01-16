---
title: JSONata モジュール
description: Adobe Workfront Fusion JSONata コネクタは、Adobe Workfront Fusion がデータコンテンツをさらに操作できるように、データを JSON 形式で処理するモジュールを提供します。
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: 2ba6ca5f5a82aea4979ff8f273bdeef1a8d22a06
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---

# [!UICONTROL JSONata] モジュール

[!DNL Adobe Workfront Fusion] [!UICONTROL JSONata] コネクタを使用すると、JSON オブジェクトに対してクエリを実行できます。 このモジュールには接続は必要ありません。

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
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
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
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
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
   <td role="rowheader">[!UICONTROL Stringify output] </td> 
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
