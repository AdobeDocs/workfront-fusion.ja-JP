---
title: Markdown モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Markdown モジュールを使用して、Markdown をHTMLに、HTMLを Markdown に変換できます。'
author: Becky
feature: Workfront Fusion
exl-id: f1134bbf-c244-4f52-8744-f97453b2ce8a
source-git-commit: 7edfe4a7b19597ea6e56bb2ca3969d742dbaf999
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 65%

---

# [!UICONTROL Markdown] モジュール

[!DNL Adobe Workfront Fusion] シナリオでは、[!UICONTROL Markdown] モジュールを使用して、Markdown を HTMLに、HTMLを Markdown に変換できます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## [!UICONTROL HTML から Markdown に]

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

## [!UICONTROL Markdown から HTML に]

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
   <td> <p>GitHub Flavored Markdown を HTML に変換する場合は、このオプションを有効にします。</p> <p>詳しくは、[!DNL GitHub] ドキュメントの Markdown のチートシートを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sanitize]</td> 
   <td>オプションを選択して、テキストから HTML タグを取り除くか、HTML をエスケープ処理するかを指定します。</td> 
  </tr> 
 </tbody> 
</table>
