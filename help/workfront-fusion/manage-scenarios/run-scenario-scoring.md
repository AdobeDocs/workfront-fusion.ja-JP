---
title: シナリオスコアリングエキスパートの実行
description: シナリオスコアリングエキスパートは、ベストプラクティスに従ってシナリオが確実に設定されるようにするのに役立ちます。 シナリオをチェックし、構造と組織に関する推奨事項を提供します。
author: Becky
feature: Workfront Fusion
exl-id: b668e7f6-dac5-4ac9-b3f3-109f70eaa2c4
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 11%

---

# シナリオスコアリングエキスパートの実行

>[!IMPORTANT]
>
>シナリオスコアリングエキスパートは一時的に無効になっています。

シナリオスコアリングエキスパートは、ベストプラクティスに従ってシナリオが確実に設定されるようにするのに役立ちます。 シナリオをチェックし、構造と組織に関する推奨事項を提供します。

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
   <td> <p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## シナリオスコアリングエキスパートの実行

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオ・スコアリング・エキスパートを実行するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. 画面の下部付近にあるシナリオスコアリングエキスパートアイコン ![ シナリオスコアリングエキスパート ](assets/scoring-expert-icon.png) をクリックします。

   シナリオスコアリングエキスパートパネルが開きます。
1. **評価** をクリックします。

シナリオスコアリングエキスパートは、10 点中のスコアを返し、どのチェックに合格または失敗したかを示します。 チェックが失敗した場合、シナリオのスコアリング・エキスパートは、シナリオがこれらのチェックを確実に満たす方法の推奨事項を提供します。

![ シナリオスコア ](assets/scenario-score.png)

## シナリオスコアリングチェック

シナリオスコアリングエキスパートでは、次のチェックを使用します。

* シナリオに名前を付ける必要があります。
* すべてのモジュールにラベルを付ける必要があります。
* シナリオは、設定されたスケジュールで実行する必要があります。

  手順については、[ シナリオのスケジュール設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。
* シナリオのブループリントのサイズは 5 MB 未満にする必要があります。

  詳しくは、[Fusion パフォーマンスガードレール ](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#scenarios) を参照してください。
* Workfront インスタントトリガーモジュールを使用する場合は、フィルタリングする必要があります。

  手順については、[Workfront/[!UICONTROL  イベントをウォッチ ] モジュールのイベント購読フィルター ](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules) を参照してください。
