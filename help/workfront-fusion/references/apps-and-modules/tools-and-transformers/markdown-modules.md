---
title: Markdown モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Markdown モジュールを使用して、Markdown をHTMLに、HTMLを Markdown に変換できます。'
author: Becky
feature: Workfront Fusion
exl-id: f1134bbf-c244-4f52-8744-f97453b2ce8a
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 70%

---

# [!UICONTROL Markdown] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!UICONTROL Markdown] モジュールを使用して Markdown をHTMLに、HTMLを Markdown に変換できます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
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

## [!UICONTROL Markdown to HTML]

このモジュールは、Markdown を HTML に変換します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Markdown]</td> 
   <td> <p>Markdown 形式のプレーンテキストを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL GitHub Flavored Markdown] </td> 
   <td> <p>GitHub Flavored Markdown を HTML に変換する場合は、このオプションを有効にします。</p> <p>詳しくは、[!DNL ]Markdown のチートシート[!DNL GitHub]ドキュメントを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sanitize]</td> 
   <td>オプションを選択して、テキストから HTML タグを取り除くか、HTML をエスケープ処理するかを指定します。</td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL HTML to Markdown]

このモジュールは、HTML コードを Markdown に変換します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Markdown]</td> 
   <td> <p>Markdown に変換する HTML コードを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL GitHub Flavored Markdown] </td> 
   <td> <p>このオプションを有効にして、HTML を [!DNL GitHub Flavored Markdown] に変換します。</p> <p>詳しくは、[!DNL GitHub] ドキュメントの Markdown のチートシートを参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>
