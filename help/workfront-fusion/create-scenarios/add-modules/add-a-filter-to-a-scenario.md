---
title: シナリオへのフィルターの追加
description: 場合によっては、特定の条件を満たすバンドルのみで作業する必要があります。フィルターを使用すると、そのようなバンドルを選択できます。
author: Becky
feature: Workfront Fusion
exl-id: b507dca0-0e85-4ab7-8310-b6e6bcb7ae12
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 30%

---

# シナリオへのフィルターの追加

場合によっては、特定の条件を満たすバンドルのみで作業する必要があります。フィルターを使用すると、そのようなバンドルを選択できます。

例えば、特定のユーザーに割り当てられたタスクのみを取り込む [!UICONTROL Watch records] のトリガーを [!DNL Workfront] 用するシナリオを作成できます。

2 つのモジュール間にフィルターを追加すると、前のモジュールから受け取ったバンドルが特定のフィルター条件を満たしているかどうかを確認できます。

* 満たしている場合、バンドルはシナリオ内の次のモジュールに渡されます。
* 満たしていない場合、バンドルの処理は終了します。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

両方のモジュールをシナリオに追加した後で、それらの間にフィルターを追加する必要があります。

## 2 つのモジュール間にフィルターを追加します。

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. フィルターを追加するモジュールの間にあるレンチアイコン ![ レンチアイコン ](assets/wrench-icon.png) をクリックし、「**フィルターを設定** を選択します。
1. 表示されたボックスに、フィルタの **[!UICONTROL Label]** を入力します。
1. フィルター **[!UICONTROL Condition]** を定義します。

   最初のフィールドにフィルターの基準にするフィールド、演算子、（必要に応じて）フィールドと比較する値を入力します。

   >[!TIP]
   >
   >マッピングパネルからフィルターフィールドに値を入力できます
   >マッピングについて詳しくは、「[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)」を参照してください。

   例えば、フィルターで XML で終わる [!DNL Adobe Workfront] 内のファイルを渡す場合は、最初のボックスにと **[!UICONTROL File name]** を入力します。2 つ目のボックスに **[!UICONTROL xml]** を入力します。 それらの間のドロップダウンメニューで、「**[!UICONTROL Ends with (case insensitive)]**」を選択します。 このフィルターは、最初のモジュール（Workfront）からの受信バンドルに適用されます。XML ファイルを含むバンドルのみが次のモジュールに渡されます。

   ![ フィルターの設定 ](assets/set-up-filter-box.png)

1. **[!DNL OK]** をクリックします。

## フィルターをコピー

現在、シナリオエディターには、フィルターをコピーする機能が含まれています。

>[!NOTE]
>
>フィルターのどちらかの側のモジュールをコピーすると、フィルターもコピーされます。
>
>モジュールのコピーについて詳しくは、「[ モジュールまたはシナリオをコピーする  [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md)」を参照してください。

モジュールをコピーせずにフィルターをコピーするには、Fusion 開発ツールを使用できます

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. 画面の下部にある開発ツールアイコン ![ 開発ツールアイコン ](assets/debugger-icon.png) をクリックして、Fusion 開発ツールを開きます。

   開発ツールアイコンが表示されない場合、開発ツールを開く手順については [ シナリオのデバッグ ](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) を参照してください。

1. 左側のバーにある **[!UICONTROL Tools]** アイコン ![ 開発ツール ツール ](assets/devtools-tools-icon.png) をクリックします。

1. 「**[!UICONTROL Copy Filter]**」をクリックして、右側のパネルで **[!UICONTROL Copy Filter]** ツールを設定します。

   1. コピーするフィルターの直後に、**[!UICONTROL Source Module]** をモジュールとして設定します。
   1. フィルターを直接配置するモジュールとして **[!UICONTROL Target Module]** を設定します。

1. **[!UICONTROL Run]** をクリックします。
