---
title: Adobe Workfront Fusion のデータストア
description: データストアは、データベースやシンプルなテーブルと同様に、シナリオのデータを保存できるので、個々のシナリオ間やシナリオ実行間でデータを転送できるようになります。データストアを使用すると、同期中に様々なシステムから新しいデータを保存できます。
author: Becky
feature: Workfront Fusion
exl-id: 8bfa3201-45db-49d7-985d-9c324acd56b6
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 69%

---

# データストアの作成と管理

データストアは、データベースやシンプルなテーブルと同様に、シナリオのデータを保存できるので、個々のシナリオ間やシナリオ実行間でデータを転送できるようになります。データストアを使用すると、同期中に様々なシステムから新しいデータを保存できます。

データストアモジュールを使用すると、Adobe Workfront Fusion データストア内のレコードに対して次のアクションを実行できます。

* 追加
* 置き換え
* アップデート
* 取得
* 削除
* 検索
* カウント

データストアモジュールの使用については、[[!UICONTROL データストア]モジュール](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/data-store-modules.md)を参照してください。

Workfront Fusion のデータストアの紹介ビデオについては、以下を参照してください。

* [データストア](https://video.tv.adobe.com/v/3427029/){target=_blank}

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++

## 使用可能なデータ容量

組織が新しいWorkfront プランモデル（Select、Prime、Ultimateの各パッケージ）を使用している場合、組織のプランは Fusion インスタンスで使用可能なデータストアのサイズと数に影響します。

### Ultimateプラン

Ultimate パッケージ上の Fusion インスタンスは、次を受け取ります。

* 100 MB の容量
* 50 個のデータストア

### プランとPrimeプランの選択

「選択」または「Prime」パッケージの Fusion インスタンスを次から受け取ります :-->

* 最初の 500,000 件の処理には 100 MB。

* 10 万回の追加操作ごとに 10 MB。

  例えば、600,000 件の操作を行う組織は 110 MB を受け取ります。

組織は、最大 50 個のデータストアを持つことができます。 これらのデータストアの合計サイズは、組織のデータストアの合計サイズを超えることはできません。

## Workfront Fusion でのデータストアの作成

* [データストアの設定](#set-up-the-data-store)
* [データ構造の設定](#set-up-the-data-structure)

### データストアの設定

モジュールでデータストアを使用するには、まずWorkfront Fusion でデータストアを作成する必要があります。

>[!NOTE]
>
>組織で使用可能なデータストアの数には制限があります。作成するデータストアの数が上限を超えると、Workfrontで [!UICONTROL &#x200B; ストアの最大数に達しました &#x200B;] エラーが返されます。
>
>詳しくは、この記事の[「ストアの最大数に達しました」エラー](#maximum-stores-reached-error)を参照してください。

1. Workfront Fusion アカウントにログインします。
1. 左ナビゲーションパネルの「**[!UICONTROL データストア]**」をクリックします。
1. 画面の右上隅にある「**[!UICONTROL データストアを追加]**」をクリックします。
1. 新規データストアの設定を入力します。

   Workfront Fusion モジュールのフィールドの太字のタイトルは、必要な設定を示しています。

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

1. データストアを作成または編集する場合は、「**[!UICONTROL 追加]**」をクリックします。
1. 表示される&#x200B;**[!UICONTROL データ構造を追加]**&#x200B;ボックスで、次のフィールドを設定します。

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
        <li> <p>「<strong>[!UICONTROL Add item]</strong>」をクリックして、1 つの列のプロパティを手動で指定します。</p> <p>データストア列の「<strong>[!UICONTROL Name]</strong>」と「<strong>[!UICONTROL Type]</strong>」を入力して、対応するプロパティを定義します。</p> </li> 
        <li> <p>「<strong>[!UICONTROL Generator]</strong>」をクリックして、入力したサンプルデータの列を特定します。</p> 
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
          <p>値をデータストアに追加するには、手動で行うか、Workfront Fusion データストアモジュールを使用します。</p> 
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

Workfront Fusion の [!UICONTROL &#x200B; データストア &#x200B;] 領域で、既存のデータストアのプロパティとコンテンツを編集できます。

* [データストアのプロパティの編集](#edit-the-properties-of-a-data-store)
* [データストアの内容の編集](#edit-the-contents-of-a-data-store)

### データストアのプロパティの編集

データストアのプロパティには、データストアで使用されているデータ構造と、データストアのサイズが含まれます。

1. 左側のナビゲーションパネルで **[!UICONTROL データストア]**![&#x200B; データストアアイコン &#x200B;](assets/data-store-icon.png) をクリックして、[!UICONTROL &#x200B; データストア &#x200B;] 領域を開きます。
1. 編集するデータストアの横にある「**[!UICONTROL 編集]**![&#x200B; データストアを編集 &#x200B;](assets/data-store-edit.png) をクリックします。
1. （オプション）このデータストアで使用するデータ構造を別の既存のデータ構造に変更する場合は、**[!UICONTROL データ構造]**&#x200B;ドロップダウンから選択します。

   または

   （オプション）このデータストアで使用するデータ構造をまったく新しいデータ構造に変更する場合は、この記事の[データ構造の設定](#set-up-the-data-structure)を参照してください。

1. （オプション）データストアのサイズを変更する場合は、新しいサイズを「**[!UICONTROL データストレージサイズ (MB)]**」フィールドに入力します。
1. 「**[!UICONTROL 保存]**」をクリックします。

### データストアの内容の編集

1. 左側のナビゲーションパネルで **[!UICONTROL データストア]** アイコン ![&#x200B; データストアアイコン &#x200B;](assets/data-store-icon.png) をクリックして、[!UICONTROL &#x200B; データストア &#x200B;] 領域を開きます。
1. 編集するデータストアの横にある「**[!UICONTROL 参照]**」をクリックします。
1. （オプション）列を目的の場所にドラッグして並べ替えます。
1. （オプション）1 つのセルを[!UICONTROL 編集]する場合は、そのセルの&#x200B;**[!UICONTROL 編集]**&#x200B;アイコンをクリックしてから、目的の値を入力します。
1. （オプション）データストアに新しい項目を追加する場合は、「**[!UICONTROL 追加]**」をクリックしてから新しい項目の情報を入力します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## トラブルシューティング

* [失われたデータをデータストアから復元](#restoring-lost-data-from-a-data-store)
* [「容量不足」エラー](#out-of-space-error)
* [「ストアの最大数に達しました」エラー](#maximum-stores-reached-error)

### 失われたデータをデータストアから復元

現在、失われたデータの復元を自動化できるツールはありません。

#### 回避策

1. 項目がデータストアに挿入されたシナリオのすべての実行ログを調べます。

   実行ログの確認について詳しくは、[&#x200B; シナリオの実行履歴の表示 &#x200B;](/help/workfront-fusion/manage-scenarios/view-scenario-execution-history.md) を参照してください。

1. データをコピーします。
1. データをデータストアに再度挿入します。

   データストアにデータの挿入する方法については、[データストアのコンテンツの編集](#edit-the-contents-of-a-data-store)を参照してください。

### 「[!UICONTROL 容量不足]」エラー

「[!UICONTROL 容量不足]」エラーが発生するのは、以前に作成したデータストアに、割り当て済みのデータストアストレージが既に割り当てられている場合です。

#### 回避策

1. 既存のデータストアのいずれかを編集して、使用するスペースを減らします。これにより、新しいデータストア用の空き容量ができます。

   詳しくは、[データストアのプロパティの編集](#edit-the-properties-of-a-data-store)を参照してください。

>[!NOTE]
>
>追加のデータストアが不要であることが確実でない限り、すべてのスペースを 1 つのデータストアに割り当てることがないようにすることをお勧めします。

### 「[!UICONTROL ストアの最大数に達しました]」エラー

組織が使用可能なすべてのデータストアを使用したので、[!UICONTROL &#x200B; 最大ストア数に達しました &#x200B;] エラーが発生します。

#### 回避策

既存のデータストアの数を減らすには、次のいずれかの操作を検討します。

* 既存のデータストアを結合する
* 未使用のデータストアを削除する
