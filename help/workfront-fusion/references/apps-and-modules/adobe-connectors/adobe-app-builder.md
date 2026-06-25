---
title: Adobe App Builder モジュール
description: Adobe App Builder コネクタを使用すると、シナリオでカスタム関数を使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 92661a0c-436b-4fbd-808a-a4fbe3cd2339
source-git-commit: eb4c1ed6991606928beccbb57a8a86182e58a9e7
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 19%

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

### カスタムコードブロックの実行

このモジュールでは、コードブロックを実行できます。 コードブロックは、モジュールの設定時に設定し、シナリオの実行中にモジュールが実行されるときに実行されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>実行するカスタム関数を含む接続を選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Code ブロック &#x200B;]</td> 
   <td>モジュールを実行するコードブロックを入力します。<p>読みやすいようにコードを書式設定するには、「<b> コードを書式設定</b>」アイコンをクリックします。</td> 
  </tr> 
   </tbody> 
</table>

### パッケージからカスタム関数を実行する

このモジュールは、パッケージから関数を実行します。

パッケージについて詳しくは、[&#x200B; カスタム関数パッケージの使用](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md)を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>実行するカスタム関数を含む接続を選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ &#x200B;]</td> 
   <td>シナリオで実行する関数を含むパッケージを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 変数] </td> 
   <td>シナリオで実行する関数を選択します。</p></td> 
  </tr> 
   </tbody> 
</table>

### パッケージから変数を使用

このモジュールは、パッケージで設定された変数をシナリオに取り込みます。

パッケージについて詳しくは、[&#x200B; カスタム関数パッケージの使用](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md)を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>実行するカスタム関数を含む接続を選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ &#x200B;]</td> 
   <td>シナリオに取り込む変数を含むパッケージを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 変数] </td> 
   <td>シナリオに取り込む変数を選択します。</p></td> 
  </tr> 
   </tbody> 
</table>

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



