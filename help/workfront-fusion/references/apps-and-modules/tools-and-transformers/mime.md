---
title: MIME モジュール
description: MIME タイプは、Adobe Workfront Fusion で使用できます。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプが text/html のファイルは、MIME タイプが image/jpeg のファイルとは異なる方法でブラウザーで処理されます。MIME タイプは、オペレーティングシステムとハードウェアに関係なく機能します。
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 72%

---

# [!UICONTROL MIME] モジュール

MIME タイプは、Adobe Workfront Fusion で使用できます。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプが `text/html` のファイルは、ブラウザーによって、MIME タイプが `image/jpeg` のファイルとは異なる方法で処理されます。MIME タイプは、オペレーティングシステムとハードウェアに関係なく機能します。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>Workfront Fusion ライセンス要件なし</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

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
