---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 基本シナリオへのフィルターの追加
description: フィルターを使用すると、特定の条件が満たされた場合にのみシナリオを進行させることができます。
author: Becky
feature: Workfront Fusion
exl-id: 78ab27fe-e2dd-4b52-b986-77b4b7ea3b5e
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 7%

---

# 基本シナリオへのフィルターの追加

フィルターを使用すると、特定の条件が満たされた場合にのみシナリオを進行させることができます。

この例では、リクエストが特定のリクエストキューに送信された場合にのみリクエストから新しいプロジェクトを作成できるようにするフィルターをシナリオに追加します。

この例では、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で作成したシナリオを変更します。

>[!NOTE]
>
>Workfront トリガーモジュールには、特定の条件が満たされた場合にのみシナリオを開始できるフィルターが含まれます。 ただし、between-module フィルターはモジュール以外およびWorkfront以外のすべてのユースケースで使用されるので、トリガー間でフィルターを使用する方法を学ぶことが重要です。 この例では、モジュール内フィルターで満たされる可能性のある機能に対して、モジュール間フィルターを使用しています。

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

この手順を実行する前に、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で説明されているシナリオを作成する必要があります。

## フィルターの追加

### フィルターの追加準備

1. シナリオを開きます。
1. 最初のモジュールをクリックして開きます。
1. **出力** 領域で、「`Project`」を選択します。
これで、`ID`、`Name`、`Project` が選択されました。
1. 「OK」をクリックして、モジュール設定を保存します。
1. Workfrontを開きます。
1. Workfrontで、Fusion シナリオが使用するリクエストキューを表すプロジェクトを見つけます。

   このプロジェクトは、Fusion 接続が設定されているのと同じWorkfront アカウントにある必要があります。

1. URL 内のプロジェクト ID をメモします。

   例：https://\&lt;MyDomain\>.my.workfront.com/project/\&lt;ProjectID\>/tasks

### フィルターの追加と設定

1. シナリオエディターのシナリオに戻ります。
1. 1 つ目のモジュールと 2 つ目のモジュールの間にあるレンチアイコン ![ レンチアイコン ](assets/wrench-icon.png) をクリックし、「**フィルターを設定** を選択します。
1. 「ラベル」フィールドに、「リクエストキューのフィルター」などのこのフィルターのラベルを入力します。
1. **条件** 領域の上部フィールドで、最初のモジュールから `projectID` をマッピングします。

   ![ プロジェクト ID をマップ ](assets/map-proj-id.png)
1. **条件** 演算子は「次と等しい」のままにします。
1. 「**条件**」領域の下部フィールドに、「[ フィルターを追加する準備 ](#prepare-to-add-the-filter)」のプロジェクト URL からメモしたプロジェクト ID を貼り付けます。
1. **OK** をクリックして、フィルター設定を保存します。

### テストしてアクティブ化

1. Fusion が接続しているWorkfront環境に移動し、フィルターで指定したプロジェクトにイシューを追加します。 別の問題を別のプロジェクトに追加します。
1. シナリオエディターの左下にある「**[!UICONTROL Run once]**」をクリックします。
1. 出力を調べて、シナリオが期待どおりに実行されたことを確認します。

   両方の問題が最初のモジュールの出力に表示されますが、2 番目のモジュールへの入力として表示されるのは、指定したプロジェクトの問題のみです。
1. シナリオが期待どおりに動作していることを確認したら、画面の左下にある **スケジュール** トグルをクリックして **オン** にします。

   これにより、シナリオがアクティブになります。
1. [!DNL Workfront Fusion] では、左下隅付近の **[!UICONTROL Save]** をクリックして、シナリオの進捗を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。

## リソース

* フィルターについて詳しくは、[ シナリオへのフィルターの追加 ](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md) を参照してください。
