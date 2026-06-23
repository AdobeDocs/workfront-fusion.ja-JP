---
title: Adobe App Builder モジュール
description: Adobe App Builder コネクタを使用すると、シナリオでカスタム関数を使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 92661a0c-436b-4fbd-808a-a4fbe3cd2339
source-git-commit: 73fd05c383efe0dd618e90cc7ddb0062d01086ef
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 32%

---

# Adobe App Builder モジュール

Fusionの「関数」エリアでカスタム関数を作成できます。 次に、これらの関数をAdobe App Builder モジュールの形式でシナリオに追加します。

カスタム関数はAdobe App Builderを通じて機能するため、使用するにはAdobe App Builder ライセンスが必要です。

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
   <p><ul><li>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li><li>カスタム関数を使用するには、Adobe App Builder ライセンスが必要です。</ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## Adobe App Builder モジュール

<!--

### Run a custom code block

This module allows you to run a code block. You configure the code block when you set up the module, and it is run when the module runs during a scenario execution.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Select the connection that contains the custom function that you want to run. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Code block]</td> 
   <td>Enter the block of code that you want the module to run.<p>To format the code for easier reading, click the <b>Format code</b> icon.</td> 
  </tr> 
   </tbody> 
</table>

-->

### カスタム関数またはコードブロックの実行

このモジュールでは、以前に設定したカスタム JavaScript関数を関数エリアに格納して使用できます。

カスタム関数の設定方法については、[&#x200B; カスタム関数を使用したデータのマッピング &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md)を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>実行するカスタム関数を含む接続を選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td>実行するカスタム関数を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パラメーター] </td> 
   <td>関数パラメーターの値を入力します。 使用可能なパラメーターは、関数の作成時に設定したパラメーターに基づきます。<p>パラメーターにデフォルト値がある場合、フィールドには表示されませんが、フィールドに値を入力またはマッピングすることで、パラメーターを上書きできます。</p></td> 
  </tr> 
   </tbody> 
</table>
