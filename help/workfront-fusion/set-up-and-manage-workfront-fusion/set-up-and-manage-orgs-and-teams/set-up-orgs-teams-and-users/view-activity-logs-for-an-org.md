---
title: 組織のアクティビティログの表示
description: シナリオの作成やアクティブ化など、組織のアクティビティのログを表示できます。
author: Becky
feature: Workfront Fusion
exl-id: 3cf851e3-50a1-4baa-8318-a24e1f467134
source-git-commit: edeed099b26dae635889fd35de61d66a1ea1ffc1
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 9%

---

# 組織のアクティビティログの表示

シナリオの作成やユーザーの招待など、組織のアクティビティのログを表示できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
   <td> <p>新規：Ultimate</p> <p>または</p> <p>現在：使用できません</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：使用できません</p> </td> 
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
   <td role="rowheader">アクセスレベル設定</td> 
   <td> <p>アクティビティログを使用するには、Fusion 管理者である必要があります。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>この機能は、[!DNL Workfront Fusion] を含むUltimate Workfront プランを使用している組織でのみ使用できます。 追加の製品購入は必要ありません。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[Workfront ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++



## アクティビティログの表示

1. 左側のナビゲーションパネルで、**組織概要**![ 組織概要アイコン ](assets/org-overview-icon.png) をクリックします。
1. アクティビティログを表示する組織に現在所属していない場合は、画面の右上隅にある組織名をクリックし、ドロップダウンから組織を選択します。
1. 画面上部付近の「**[!UICONTROL Activity Logs]**」タブをクリックします。

   アクティビティログページが開きます。
1. （オプション）指定した条件で結果を制限するには、アクティビティログをフィルタリングします。

   手順については、この記事の [ アクティビティログのフィルタリング ](#filter-the-activity-logs) を参照してください。
1. （オプション）適用したフィルターをクリアするには、画面の右上付近にあるフィルターを見つけて、フィルターのボックスの **X** をクリックします。
1. （任意）ログをエクスポートします。

   手順については、この記事の [ アクティビティログのエクスポート ](#export-the-activity-logs) を参照してください。


## アクティビティログのフィルタリング

1. 左側のナビゲーションパネルで、**組織概要**![ 組織概要アイコン ](assets/org-overview-icon.png) をクリックします。
1. アクティビティログを表示する組織に現在所属していない場合は、画面の右上隅にある組織名をクリックし、ドロップダウンから組織を選択します。
1. 画面上部付近の「**[!UICONTROL Activity Logs]**」タブをクリックします。

   アクティビティログページが開きます。
1. **フィルター**![ フィルターアイコン ](assets/filter-activity-log.png) をクリックします。
1. フィールドをクリックして、次のフィルターを 1 つ以上設定します。

   * **開始日と終了日**：カレンダーから日付を選択し、（オプション）時間を入力します。
   * **ユーザー**：ドロップダウンからユーザーを選択します。
   * **チーム**：ドロップダウンからチームを選択します。 自分がメンバーになっているチームのみがドロップダウンに表示されます。
   * **エンティティ**：アクティビティログを表示する Fusion オブジェクトのタイプを選択します。
   * **アクション**：アクティビティログを表示するアクションを選択します。

1. **適用** をクリックします。

## アクティビティログのエクスポート

1. 左側のナビゲーションパネルで、**組織概要**![ 組織概要アイコン ](assets/org-overview-icon.png) をクリックします。
1. アクティビティログを表示する組織に現在所属していない場合は、画面の右上隅にある組織名をクリックし、ドロップダウンから組織を選択します。
1. 画面上部付近の「**[!UICONTROL Activity Logs]**」タブをクリックします。

   アクティビティログページが開きます。
1. カレンダーから日付範囲を選択し、（オプション）時間を入力します。
1. Excel ファイルと CSV ファイルのどちらをエクスポートするかを選択します。
1. 「**適用**」をクリックします。
