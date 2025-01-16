---
title: ' [!DNL Adobe Workfront Fusion] のデータストア'
description: データストアは、データベースやシンプルなテーブルと同様に、シナリオのデータを保存できるので、個々のシナリオ間やシナリオ実行間でデータを転送できるようになります。データストアを使用すると、同期中に様々なシステムから新しいデータを保存できます。
author: Becky
feature: Workfront Fusion
exl-id: 8bfa3201-45db-49d7-985d-9c324acd56b6
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 61%

---

# データストアの作成と管理

データストアは、データベースやシンプルなテーブルと同様に、シナリオのデータを保存できるので、個々のシナリオ間やシナリオ実行間でデータを転送できるようになります。データストアを使用すると、同期中に様々なシステムから新しいデータを保存できます。

データストアモジュールを使用すると、[!DNL Adobe Workfront Fusion] データストア内のレコードに対して次のアクションを実行できます。

* 追加
* 置き換え
* アップデート
* 取得
* 削除
* 検索
* カウント

データストアモジュールの使用について詳しくは、[[!UICONTROL Data store] モジュール ](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/data-store-modules.md) を参照してください。

Workfront Fusion のデータストアの紹介ビデオについては、以下を参照してください。

* [データストア](https://video.tv.adobe.com/v/3427029/){target=_blank}

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

## 使用可能なデータ容量

組織が新しいWorkfront プランモデル（Select、Prime、Ultimateの各パッケージ）を使用している場合、組織のプランは Fusion インスタンスで使用可能なデータストアのサイズと数に影響します。

### Ultimateプラン

Ultimate パッケージ上の Fusion インスタンスは、次を受け取ります。

* 100 MB の容量
* 50 個のデータストア

### プランとPrimeプランの選択

Select パッケージまたはPrime パッケージの Fusion インスタンスは、以下を受け取ります。—>

* 最初の 500,000 件の処理には 100 MB。

* 10 万回の追加操作ごとに 10 MB。

  例えば、600,000 件の操作を行う組織は 110 MB を受け取ります。

組織は、最大 50 個のデータストアを持つことができます。 これらのデータストアの合計サイズは、組織のデータストアの合計サイズを超えることはできません。

## [!DNL Workfront Fusion] でのデータストアの作成

* [データストアの設定](#set-up-the-data-store)
* [データ構造の設定](#set-up-the-data-structure)

### データストアの設定

モジュールでデータストアを使用するには、まず [!DNL Workfront Fusion] でデータストアを作成する必要があります。

>[!NOTE]
>
>組織で使用可能なデータストアの数には制限があります。作成するデータストアの数が作成できるデータストアの数を超えると、[!DNL Workfront] は [!UICONTROL Maximum stores reached] エラーを返します。
>
>詳しくは、この記事の[「ストアの最大数に達しました」エラー](#maximum-stores-reached-error)を参照してください。

1. [!DNL Workfront Fusion] アカウントにログインします。
1. 左側のナビゲーションパネルで「**[!UICONTROL Data stores]**」をクリックします。
1. 画面の右上隅にある「**[!UICONTROL Add data store]**」をクリックします。
1. 新規データストアの設定を入力します。

   [!DNL Workfront Fusion] モジュールでフィールドのタイトルが太字になっている場合は、必須の設定であることを示します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Data store name] </td> 
      <td> <p>データストアの名前を入力します。 </p> </td> 
     </tr> 
     <tr> 
      <td> <p>[!UICONTROL Data Structure]</p> </td> 
      <td> <p>データ構造はテーブルの列のリストです。このリストは列名とデータタイプを示します。</p> <p>次のいずれかの操作を行います。</p> 
       <ul> 
        <li><b>作成済みのデータ構造を選択する</b></li> 
        <li><b> 新しいデータ構造の追加 </b> <p>「<strong>[!UICONTROL Add]</strong>」をクリックして、新しいデータ構造を作成します。</p> <p>詳しくは、この記事で<a href="#set-up-the-data-structure" class="MCXref xref">データ構造の設定</a>の節を参照してください。</p> </li> 
        <li style="font-weight: bold;"> <p>フィールドを空のままにする</p> <p style="font-weight: normal;">データ構造を選択または追加しない場合、データベースにはプライマリキーのみが含まれます。このようなデータベースタイプが役に立つのは、キーのみを保存する必要があり、特定のキーがデータベースに存在するかどうかにのみ関心がある場合です。</p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td>データストレージのサイズ （MB 単位）</td> 
      <td> <p>内部データストレージの合計から、データストアのサイズを割り当てます。</p> <p> デフォルト値は 10 MB です。95 MB の割り当てのうち、未割り当てのデータストア容量が 10 MB 未満の場合、デフォルトのサイズは未割り当てのストレージの容量になります。  <p>メモ：予約容量はいつでも変更できます。</p>  </td> 
     </tr> 
    </tbody> 
   </table>

### データ構造の設定

1. データストアを作成または編集する際に、「**[!UICONTROL Add]**」をクリックします。
1. 表示される **[!UICONTROL Add data structure]** ボックスで、次のフィールドを設定します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Data structure name]</td> 
      <td> <p> 新しいデータ構造の名前を入力します。</p> </td> 
     </tr> 
     <tr> 
      <td> <p>[!UICONTROL Specification]</p> </td> 
      <td> <p>データストアの列を設定するには、次のいずれかの操作を行います。</p> 
       <ul> 
        <li> <p>「<strong>[!UICONTROL Add item]</strong>」をクリックして、1 つの列のプロパティを手動で指定します。</p> <p>データストア列の <strong>[!UICONTROL Name]</strong> と <strong>[!UICONTROL Type]</strong> を入力し、対応するプロパティを定義します。</p> </li> 
        <li> <p>「<strong>[!UICONTROL Generator]</strong>」をクリックして、指定したサンプルデータから列を決定します。</p> 
         <div class="example" data-mc-autonum="<b>Example: </b>">
          <span class="autonumber"><span><b>例：</b></span></span> 
          <p>例えば、次の JSON サンプルデータは、「name」、「age」、「phone number」の 3 つの列を作成します。「phone number」は、携帯電話と固定電話の電話番号をまとめたものです。</p> 
          <p><code>&lbrace;</code> </p> 
          <p><code>"name":"John",</code> </p> 
          <p><code>"age":30,</code> </p> 
          <p><code>"phone number": &lbrace;</code> </p> 
          <p><code>"mobile":"987654321",</code> </p> 
          <p><code>"landline":"123456789"</code> </p> 
          <p><code>&rbrace;</code> </p> 
          <p><code>&rbrace;</code> </p> 
          <p>データストアビューでは空の列は次のように表示されます。</p> 
          <p> <img src="assets/empty-columns-350x132.png" style="width: 350;height: 132;"> </p> 
          <p>データストアへの値の追加は、手動で行うことも、[!DNL Workfront Fusion] のデータストアモジュールを使用して行うこともできます。</p> 
         </div> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Strict] </td> 
      <td> <p>このオプションを有効にすると、ペイロードをデータ構造に確実に一致させることができます。データ構造で規定されていない追加の項目を含んだペイロードは却下されます。</p> </td> 
     </tr> 
    </tbody> 
   </table>

## 既存のデータストアの編集

[!DNL Workfront Fusion] の [!UICONTROL Data stores] 領域にある既存のデータストアのプロパティとコンテンツを編集できます。

* [データストアのプロパティの編集](#edit-the-properties-of-a-data-store)
* [データストアの内容の編集](#edit-the-contents-of-a-data-store)

### データストアのプロパティの編集

データストアのプロパティには、データストアで使用されているデータ構造と、データストアのサイズが含まれます。

1. 左側 **[!UICONTROL Data stores]** ナビゲーションパネルで ![](assets/data-store-icon.png) をクリックして、[!UICONTROL Data stores] 領域を開きます。
1. 編集 **[!UICONTROL Edit]** るデータストアの横にある「![](assets/data-store-edit.png)」をクリックします。
1. （オプション）このデータストアで使用されるデータ構造を別の既存のデータ構造に変更する場合は、「**[!UICONTROL Data structure]**」ドロップダウンから選択します。

   または

   （オプション）このデータストアで使用するデータ構造をまったく新しいデータ構造に変更する場合は、この記事の[データ構造の設定](#set-up-the-data-structure)を参照してください。

1. （オプション）データストアのサイズを変更するには、「**[!UICONTROL Data storage size in MB]**」フィールドに新しいサイズを入力します。
1. **[!UICONTROL Save]** をクリックします。

### データストアの内容の編集

1. 左側のナビゲーションパネルにある「**[!UICONTROL Data Store]**」アイコン ![](assets/data-store-icon.png) をクリックして、[!UICONTROL Data Store] 領域を開きます。
1. 編集するデータストアの横にある「**[!UICONTROL Browse]**」をクリックします。
1. （オプション）列を目的の場所にドラッグして並べ替えます。
1. （任意） 1 つのセルを [!UICONTROL Edit] すには、そのセルの **[!UICONTROL Edit]** アイコンをクリックして目的の値を入力します。
1. （オプション）「**[!UICONTROL Add]**」をクリックして、新しい項目の情報を入力することにより、新しい項目をデータストアに追加します。
1. **[!UICONTROL Save]** をクリックします。

## トラブルシューティング

* [失われたデータをデータストアから復元](#restoring-lost-data-from-a-data-store)
* [「容量不足」エラー](#out-of-space-error)
* [「ストアの最大数に達しました」エラー](#maximum-stores-reached-error)

### 失われたデータをデータストアから復元

現在、失われたデータの復元を自動化できるツールはありません。

#### 回避策

1. 項目がデータストアに挿入されたシナリオのすべての実行ログを調べます。

   実行ログの確認について詳しくは、[ シナリオの実行履歴の表示 ](/help/workfront-fusion/manage-scenarios/view-scenario-execution-history.md) を参照してください。

1. データをコピーします。
1. データをデータストアに再度挿入します。

   データストアにデータの挿入する方法については、[データストアのコンテンツの編集](#edit-the-contents-of-a-data-store)を参照してください。

### [!UICONTROL Out of space] エラー

以前に作成したデータストアが既に割り当て済みのデータストアストレージであるため、[!UICONTROL Out of Space] エラーが発生します。

#### 回避策

1. 既存のデータストアのいずれかを編集して、使用するスペースを減らします。これにより、新しいデータストア用の空き容量ができます。

   詳しくは、[データストアのプロパティの編集](#edit-the-properties-of-a-data-store)を参照してください。

>[!NOTE]
>
>追加のデータストアが不要であることが確実でない限り、すべてのスペースを 1 つのデータストアに割り当てることがないようにすることをお勧めします。

### [!UICONTROL Maximum stores reached] エラー

組織が使用可能なすべてのデータストアを使用したので、[!UICONTROL Maximum stores reached] エラーが発生します。

#### 回避策

既存のデータストアの数を減らすには、次のいずれかの操作を検討します。

* 既存のデータストアを結合する
* 未使用のデータストアを削除する
