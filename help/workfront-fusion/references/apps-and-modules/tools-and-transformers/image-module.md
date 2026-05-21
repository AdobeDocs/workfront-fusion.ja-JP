---
title: 画像モジュール
description: Adobe Workfront Fusion 画像モジュールを使用すると、特定の画像に関する情報（サイズ、タイプなど）を取得し、画像を別のファイル形式に変換し、画像のサイズを直接変更できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: a7696c9d-002d-4bb4-ae10-1f69dc5e66fe
TQID: https://experienceleague.adobe.com/1YlCzSkD3MpRG6VcTPHk-sW0RXK1hexs6QPmQdN07Ps
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 741
ht-degree: 84%

---

# 画像モジュール

Adobe Workfront Fusion [!UICONTROL Image] モジュールを使用すると、特定の画像（サイズ、種類など）に関する情報を取得し、画像を別のファイル形式に変換して、画像のサイズを直接変更できます。

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



## [!UICONTROL 画像]モジュールとそのフィールド

このモジュールを設定する際には、次のフィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

* [[!UICONTROL 形式の変換]](#convert-a-format)
* [[!UICONTROL メタデータの抽出]](#extract-metadata)
* [[!UICONTROL サイズ変更]](#resize)

### [!UICONTROL 形式の変換]

この変換モジュールは、画像ファイルの形式を変更します。 このモジュールは、以下の形式と互換性があります。

* PNG
* JPG
* GIF
* BMP

ソースファイルと出力の両方が、これらのいずれかの形式である必要があります。 例えば、[!UICONTROL 画像]／[!UICONTROL 形式を変換]するモジュールは、PNG ファイルを BMP ファイルに、または BMP を JPG に変換できます。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output format]</td> 
   <td>モジュールでソースファイルを変換する形式を選択します。 </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL メタデータの抽出]

この変換モジュールは、モジュールに関する基本情報を返します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL サイズ変更]

この変換モジュールは、指定した条件に従って画像の高さと幅を変更します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to]</td> 
   <td>高さと幅の比率を維持するか、寸法を指定した高さと幅に変更するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL According to]</td> 
   <td> <p>モジュールが画像の新しいサイズを決定する方法を選択します。 このフィールドは、目的のフィールドで高さと幅の比率の維持を選択した場合に表示されます。 このフィールドでの選択に基づいて、他のフィールドが表示されます。</p> 
    <ul> 
     <li> <p>[!UICONTROL Maximum width]</p> <p>画像を指定した幅に縮小します。 高さは自動的に計算されます。</p> </li> 
     <li> <p>[!UICONTROL Maximum height]</p> <p>画像を指定した高さに縮小します。 幅は自動的に計算されます。</p> </li> 
     <li> <p>[!UICONTROL Maximum height or width]</p> <p>画像の高さと幅が指定した値を超えないように画像を縮小します。 このオプションでは高さと幅の比率が維持されるので、寸法のどちらかが指定より小さくなる場合があります。 例えば、高さと幅の両方を 40 と指定した場合、400x300 の画像は 40x30 に縮小されます。</p> </li> 
     <li> <p>[!UICONTROL Minimum width]</p> <p>画像を指定した幅に拡大します。 高さは自動的に計算されます。</p> </li> 
     <li> <p>[!UICONTROL Minimum height]</p> <p>画像を指定した高さに拡大します。 幅は自動的に計算されます。</p> </li> 
     <li> <p>[!UICONTROL Minimum height or width]</p> <p>高さと幅が指定した値以上になるように画像を拡大します。 このオプションでは高さと幅の比率が維持されるので、寸法のどちらかが指定より大きくなる場合があります。 例えば、高さと幅の両方を 300 と指定した場合、40x30 の画像は 400x300 に拡大されます。</p> </li> 
     <li> <p>[!UICONTROL Percent]</p> <p>指定した値に基づいて、画像サイズをパーセンテージで変更します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Width]</td> 
   <td>サイズ変更した画像の希望の幅をピクセル単位で入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Height]</td> 
   <td>サイズ変更した画像の希望の高さをピクセル単位で入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Change by percentage]</td> 
   <td>画像をパーセンテージで変更する場合は、画像を変更するパーセンテージを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

## トラブルシューティング

### エラーによりアクションが終了しました

アクションは、次のいずれかの原因でエラーで終了する可能性があります。

* 受信したデータがJPG/GIF/PNG/BMP形式ではありません
* 画像のサイズを変更する際に、最大幅/高さの制限を超えました。 画像サイズは、幅 3840 ピクセルと高さ 2160 ピクセルを超えないようにする必要があります
* 画像のサイズまたは形式を変更する際に、画像の許容サイズを超えました。
