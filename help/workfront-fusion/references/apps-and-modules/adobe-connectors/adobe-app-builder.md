---
title: Adobe App Builder モジュール
description: Adobe App Builder コネクタを使用すると、シナリオでカスタム関数を使用できます。
author: Becky
feature: Workfront Fusion
source-git-commit: 8250d4fdad8ed7ffe63cd003f6e0cb325cbbfa8d
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 31%

---

# Adobe App Builder モジュール

Fusion の関数領域で、カスタム関数を作成できます。 次に、これらの関数を、Adobe App Builder モジュールの形式でシナリオに追加します。

カスタム関数はAdobe App Builderを通じて機能するので、使用する組織のAdobe App Builder ライセンスが必要です。

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

現在利用可能なAdobe App Builder モジュールは、アクションを実行のみです。このモジュールでは、以前に設定されたカスタム JavaScript関数を使用できます。

カスタム関数の設定手順については、[&#x200B; カスタム関数を使用したデータのマッピング &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md) を参照してください。

### アクションの実行

このモジュールは、以前に設定されたカスタム関数を実行します。

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
   <td role="rowheader">[!UICONTROL パラメーター &#x200B;] </td> 
   <td>関数のパラメーターの値を入力します。 使用可能なパラメーターは、関数の作成時に設定されたパラメーターに基づいています。<p>パラメーターにデフォルト値がある場合、フィールドには表示されませんが、フィールドに値を入力またはマッピングすることで上書きできます。</p></td> 
  </tr> 
   </tbody> 
</table>


