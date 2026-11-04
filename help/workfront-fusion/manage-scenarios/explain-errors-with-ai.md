---
title: AIによるシナリオエラーの説明
description: シナリオの実行が失敗した場合は、エラーの横にある「説明」をクリックすると、問題の原因とその解決方法について、簡単な言葉で簡単に説明できます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: e2420c8a25fd9e38c4b0300b00560fe1837a5e43
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 15%
---
# AIによるシナリオエラーの説明

シナリオの実行に失敗した場合、AIは問題とその解決方法を、わかりやすい言葉で短く説明します。 説明は元のエラーの横に表示されるので、両方を同時に読むことができます。

Workfront Fusionの次の領域のエラーを説明できます。

* シナリオデザイナーでのモジュールエラーの詳細
* シナリオの実行履歴の実行の詳細
* インサイトページの[!UICONTROL 失敗した実行ログ ] テーブル

>[!NOTE]
>
>「**[!UICONTROL 説明]**」ボタンは、新しいシナリオデザイナーでのみ使用できます。 レガシーシナリオデザイナーでは使用できません。

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## モジュール出力の詳細でエラーを説明する

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. エラーを説明するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. スケジュールどおりにシナリオを実行するか、**1回実行**&#x200B;をクリックしてシナリオを実行します。
1. モジュールが失敗した場合は、モジュールのエラーの詳細を開きます。
1. 「**[!UICONTROL 説明]**」をクリックします。

   ボタンはエラーの下にあります。

   ![ モジュール出力の説明エラー](assets/explain-in-module-output.png)

説明はエラーの下に表示されます。

>[!NOTE]
>
> * AIが説明を生成すると、読み込み状態が表示されます。
> * 説明の生成に失敗した場合は、**[!UICONTROL もう一度やり直す]**&#x200B;をクリックします。
> * 組織がAIの利用制限に達した場合、説明の代わりに利用制限のメッセージが表示されます。

## シナリオの実行履歴のエラーの説明

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックし、シナリオをクリックします。
1. シナリオの名前の近くにある&#x200B;**[!UICONTROL 履歴]**&#x200B;をクリックします。
1. 表示する失敗した実行をクリックします。

   実行の詳細の各エラーには、その下に「**[!UICONTROL 説明]**」ボタンがあります。

1. 説明するエラーの下にある「**[!UICONTROL 説明]**」をクリックします。

   実行で複数のモジュールが失敗した場合は、各エラーを個別に説明できます。

   ![実行履歴で説明する](assets/explain-in-execution-details.png)

実行の表示について詳しくは、[ シナリオの実行履歴を表示](/help/workfront-fusion/manage-scenarios/view-scenario-execution-history.md)および[特定のシナリオ実行を表示](/help/workfront-fusion/manage-scenarios/view-a-specific-scenario-execution.md)を参照してください。

>[!NOTE]
>
> * AIが説明を生成すると、読み込み状態が表示されます。
> * 説明の生成に失敗した場合は、**[!UICONTROL もう一度やり直す]**&#x200B;をクリックします。
> * 組織がAIの利用制限に達した場合、説明の代わりに利用制限のメッセージが表示されます。

## インサイトページでのエラーの説明

1. Fusionで、左側のナビゲーションで「**[!UICONTROL インサイト]**」をクリックします。
1. [!UICONTROL 失敗した実行] テーブルで、表示する失敗した行にカーソルを合わせます。

   「**[!UICONTROL 説明]**」ボタンが表示されます。

1. 「**[!UICONTROL 説明]**」をクリックします。

   ![ インサイトページで説明](assets/explain-failed-execution-log.png)

   ポップアップが開き、エラーとAIの説明が表示されます。

インサイトページについて詳しくは、[組織のインサイトダッシュボードの表示](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/view-insights-dashboard.md)を参照してください。

>[!NOTE]
>
> * AIが説明を生成すると、読み込み状態が表示されます。
> * 説明の生成に失敗した場合は、**[!UICONTROL もう一度やり直す]**&#x200B;をクリックします。
> * 組織がAIの利用制限に達した場合、説明の代わりに利用制限のメッセージが表示されます。
