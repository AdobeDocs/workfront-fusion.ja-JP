---
title: データストアモジュール
description: データベースやシンプルなテーブルと同様に、 [!DNL Adobe Workfront Fusion]  データストアではシナリオのデータを保存して、個々のシナリオやシナリオ実行の間でデータを転送することができます。データストアを使用すると、同期中に様々なシステムから新しいデータを保存できます。
author: Becky
feature: Workfront Fusion
exl-id: 0338b822-b345-429e-850d-3978b692231d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 90%

---

# [!UICONTROL Data store] モジュール

データベースやシンプルなテーブルと同様に、[!DNL Adobe Workfront Fusion] データストアではシナリオのデータを保存して、個々のシナリオやシナリオ実行の間でデータを転送することができます。データストアを使用すると、同期中に様々なシステムから新しいデータを保存できます。

データストアモジュールを使用すると、[!DNL Adobe Workfront Fusion] データストアでレコードの追加、置換、更新、取得、削除、検索、カウントを行えるようになります。

<!--For information on creating, editing, and troubleshooting data stores, see [Data Stores in [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/)-->

Workfront Fusion のデータストアの紹介ビデオについては、以下を参照してください。

* [データストア](https://video.tv.adobe.com/v/3427029/){target=_blank}

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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## 前提条件

[!UICONTROL Data Store] モジュールを使用するには、まずデータストアを作成する必要があります。

<!--For information on creating data stores, see [Data Stores in [!UICONTROL Adobe Workfront Fusion]]()-->

## [!UICONTROL Data Store] モジュールとそのフィールド

データストアモジュールを設定する際、[!DNL Workfront Fusion] には以下のフィールドが表示されます。これらのほか、アプリやサービスでのアクセスレベルなどの要因に応じて、追加のデータストアフィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

[!UICONTROL Data Store] のモジュールはすべてアクションタイプのモジュールです。

* [レコードの追加 / 置換](#addreplace-a-record)
* [レコードの更新](#update-a-record)
* [レコードを取得](#get-a-record)
* [レコードの有無の確認](#check-the-existence-of-a-record)
* [レコードの削除](#delete-a-record)
* [すべてのレコードの削除](#delete-all-records)
* [レコードの検索](#search-records)
* [レコードのカウント](#count-records)

### [!UICONTROL Add/Replace a Record]

このアクションモジュールは、レコードを追加または置き換えます。

データストアとレコードのキーを指定します。

このモジュールは、レコードの ID および関連するフィールドと共に、接続を介してアクセスされるカスタムフィールドとその値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

>[!NOTE]
>
>既に同じ名前のデータストアにあるレコードを追加しようとして、[!UICONTROL Overwrite an existing record] オプションが無効になると、モジュールがエラーをスローする。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> レコードを作成するデータストアを選択または追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>モジュールで追加または置換するレコードの一意のキーを入力します。このキーは、後でレコードを取得するために使用できます。このフィールドを空白のままにすると、キーが自動的に生成されます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing record] </td> 
   <td> <p>レコードを上書きする場合は、このオプションを有効にします。上書きするレコードは、上記の「キー」フィールドで指定する必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record] </td> 
   <td> <p>レコードのフィールドに目的の値を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update a Record]

このアクションモジュールは、レコードを更新します。

データストアとレコードのキーを指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> レコードを作成するデータストアを選択または追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>モジュールで更新するレコードの一意のキーを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Insert missing record] </td> 
   <td> <p>このオプションを有効にすると、指定したキーを持つレコードがまだ存在しない場合、新しいレコードが作成されます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record]</td> 
   <td> <p> レコードの更新対象フィールドに、目的の値を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Get a Record]

このアクションモジュールは、レコードを取得します。

データストアとレコードのキーを指定します。

このモジュールは、レコードの ID および関連するフィールドと共に、接続を介してアクセスされるカスタムフィールドとその値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> レコードを取得するデータストアを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>モジュールで取得するレコードの一意のキーを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Check the Existence of a Record]

このアクションモジュールは、特定のレコードが存在するかどうかを指定します。

データストアとレコードのキーを指定します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>レコードの存在を確認するデータストアを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>存在するかどうかをモジュールで確認するレコードの一意のキーを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete a Record]

このアクションモジュールは、レコードを削除します。

データストアとレコードのキーを指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>レコードの存在を確認するデータストアを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>モジュールで削除するレコードの一意のキーを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete All Records]

このアクションモジュールは、特定のデータストアからすべてのレコードを削除します。

データストアを指定します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>すべてのレコードを削除するデータストアを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Search Records]

この検索モジュールは、指定した検索クエリに一致する、データストア内のオブジェクト内のレコードを検索します。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> 検索するデータストアを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>検索のフィルターを設定します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Sort]</p> </td> 
   <td> <p style="font-weight: normal;">並べ替えの基準となる各フィールドに対して、次のフィールドに入力します。</p> <p style="font-weight: bold;">[!UICONTROL Key]</p> <p>結果の並べ替えに使用する列名を選択します。</p> <p style="font-weight: bold;">[!UICONTROL Order]</p> <p>昇順または降順のどちらで結果を並べ替えるかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p> 1 回の実行サイクル中に、[!DNL Workfront Fusion] が返す検索結果の最大数を設定します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> 有効にした場合、このモジュールが結果を返さなくても、このモジュールが処理の一部となるルートが処理を続行します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Count Records]

このアクションモジュールは、データストア内のレコードに番号を付けます。

データストアを指定します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>カウントするレコードを含むデータストアを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>
