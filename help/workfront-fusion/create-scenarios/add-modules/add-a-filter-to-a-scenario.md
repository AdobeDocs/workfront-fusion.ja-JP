---
title: シナリオへのフィルターの追加
description: 場合によっては、特定の条件を満たすバンドルのみで作業する必要があります。フィルターを使用すると、そのようなバンドルを選択できます。
author: Becky
feature: Workfront Fusion
exl-id: b507dca0-0e85-4ab7-8310-b6e6bcb7ae12
source-git-commit: bec838423e13c3efe4f3d002f824c203cad6ecf8
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 46%

---

# シナリオへのフィルターの追加

場合によっては、特定の条件を満たすバンドルのみで作業する必要があります。フィルターを使用すると、そのようなバンドルを選択できます。

例えば、Workfrontの「[!UICONTROL  レコードをウォッチ ]」トリガーを使用して、特定のユーザーに割り当てられたタスクのみを取り込むシナリオを作成できます。

2 つのモジュール間にフィルターを追加すると、前のモジュールから受け取ったバンドルが特定のフィルター条件を満たしているかどうかを確認できます。

* 満たしている場合、バンドルはシナリオ内の次のモジュールに渡されます。
* 満たしていない場合、バンドルの処理は終了します。

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

## 前提条件

両方のモジュールをシナリオに追加した後で、それらの間にフィルターを追加する必要があります。

## 2 つのモジュール間にフィルターを追加します。

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. フィルターを追加するモジュールの間にあるレンチアイコン ![ レンチアイコン ](assets/wrench-icon.png) をクリックし、「**フィルターを設定** を選択します。
1. 表示されたボックスに、フィルターの **[!UICONTROL ラベル]** を入力します。
1. フィルター **[!UICONTROL 条件]** を定義します。

   最初のフィールドにフィルターの基準にするフィールド、演算子、（必要に応じて）フィールドと比較する値を入力します。

   >[!TIP]
   >
   >マッピングパネルからフィルターフィールドに値を入力できます
   >マッピングについて詳しくは、「[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)」を参照してください。

   例えば、フィルターで XML で終わるAdobe Workfront内のファイルを渡す場合は、最初のボックスにと **[!UICONTROL ファイル名]** を入力します。2 番目のボックスに「.**[!UICONTROL xml]**」と入力します。それらの間のドロップダウンメニューで、「**[!UICONTROL 次で終わる（大文字と小文字を区別しない）]**」を選択します。このフィルターは、最初のモジュール（Workfront）からの受信バンドルに適用されます。XML ファイルを含むバンドルのみが次のモジュールに渡されます。

   ![ フィルターの設定 ](assets/set-up-filter-box.png)

1. **[!DNL OK]** をクリックします。

## フィルターをコピー

既存のフィルターをコピーして、シナリオの他の場所に貼り付けることができます。

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. フィルターがあるモジュール間の接続ドットを右クリックします。
1. 「**フィルターをコピー**」を選択します。
1. フィルターをペーストするモジュール間の接続ドットを右クリックします。
1. フィルターの選択**貼り付け
1. （任意）フィルターを調整するには、フィルターアイコンまたはラベルをクリックし、値を入力します。詳しくは、この記事の [2 つのモジュール間でのフィルターの追加 ](#add-a-filter-between-two-modules) を参照してください。




<!--

Currently, the scenario editor does include a feature for copying a filter.

>[!NOTE]
>
>If you copy the modules on either side of the filter, the filter is also copied.
>
>For more information on copying modules, see [Copy modules or scenarios in Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md).

To copy a filter without copying modules, you can use the Fusion DevTool

1. Click the **[!UICONTROL Scenarios]** tab in the left panel.
1. Select the scenario where you want to add a filter.
1. Click anywhere on the scenario to enter the Scenario editor.
1. Open the Fusion DevTool by clicking on the DevTool icon ![DevTool icon](assets/debugger-icon.png) near the bottom of the screen.
   
   If you do not see the DevTool icon, see [Debug a scenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) for instructions on opening the DevTool.
   
1. Click the **[!UICONTROL Tools]** icon ![DevTool tools](assets/devtools-tools-icon.png) in the left side bar.

1. Click **[!UICONTROL Copy Filter]**, then configure the **[!UICONTROL Copy Filter]** tool in the right side panel:

   1. Set the **[!UICONTROL Source Module]** as the module directly after the filter you want to copy.
   1. Set the **[!UICONTROL Target Module]** as the module that you want to place the filter directly after.

1. Click **[!UICONTROL Run]**.

-->
