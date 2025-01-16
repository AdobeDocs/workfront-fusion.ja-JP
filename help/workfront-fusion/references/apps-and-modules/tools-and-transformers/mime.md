---
title: MIME モジュール
description: MIME タイプは、Adobe Workfront Fusion で使用できます。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプが text/html のファイルは、MIME タイプが image/jpeg のファイルとは異なる方法でブラウザーで処理されます。MIME タイプは、オペレーティングシステムとハードウェアに関係なく機能します。
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 88%

---

# [!UICONTROL MIME] モジュール

MIME タイプは、Adobe Workfront Fusion で使用できます。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプが `text/html` のファイルは、ブラウザーによって、MIME タイプが `image/jpeg` のファイルとは異なる方法で処理されます。MIME タイプは、オペレーティングシステムとハードウェアに関係なく機能します。

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

## [!UICONTROL MIME] モジュールとそのフィールド

### [!UICONTROL Get a MIME type]

この変換サービスモジュールは、指定された名前、パス、または拡張子に関連付けられた MIME タイプを返します。

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

### [!UICONTROL Get a file extension]

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
