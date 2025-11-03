---
title: MIME モジュール
description: MIME タイプは、Adobe Workfront Fusion で使用できます。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプが text/html のファイルは、MIME タイプが image/jpeg のファイルとは異なる方法でブラウザーで処理されます。MIME タイプは、オペレーティングシステムとハードウェアに関係なく機能します。
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 70%

---

# [!UICONTROL MIME] モジュール

MIME タイプは、Adobe Workfront Fusion で使用できます。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプが `text/html` のファイルは、ブラウザーによって、MIME タイプが `image/jpeg` のファイルとは異なる方法で処理されます。MIME タイプは、オペレーティングシステムとハードウェアに関係なく機能します。

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



## [!UICONTROL MIME] モジュールとそのフィールド

* [ファイル拡張子の取得](#get-a-file-extension)
* [MIME タイプの取得](#get-a-mime-type)

### [!UICONTROL ファイル拡張子を取得]

この変換サービスモジュールは、指定された MIME タイプの元のファイル拡張子を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME type]</td> 
   <td> <p>ファイル拡張子を決定する MIME タイプを入力またはマッピングします。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL MIME タイプの取得]

この変換モジュールは、指定されたファイル名、パスまたは拡張子に関連付けられた MIME タイプを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL File]</td> 
   <td> <p>MIME タイプを決定するファイルを入力またはマッピングします。 </p> <p>次を使用してファイルを入力できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File path]</strong> </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span>/file/image.jpeg</p> </li> 
     <li><strong>[!UICONTROL File name]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span>image.jpeg</p> </li> 
     <li><strong>[!UICONTROL File extension]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span>jpeg</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
