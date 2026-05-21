---
title: シナリオスコアリングエキスパートの実行
description: シナリオスコアリングエキスパートは、ベストプラクティスに従ってシナリオを設定するのに役立ちます。 シナリオをチェックし、その構造と組織に関する推奨事項を提供します。
author: Becky
feature: Workfront Fusion
exl-id: b668e7f6-dac5-4ac9-b3f3-109f70eaa2c4
TQID: https://experienceleague.adobe.com/g8v-odwnN-wtyzSh8wr6LSNL7xLIBs8Guw2zY-JW700
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 32%

---

# シナリオスコアリングエキスパートの実行

>[!IMPORTANT]
>
>シナリオスコアリングエキスパートは一時的に無効になっています。

シナリオスコアリングエキスパートは、ベストプラクティスに従ってシナリオを設定するのに役立ちます。 シナリオをチェックし、その構造と組織に関する推奨事項を提供します。

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

## シナリオスコアリングエキスパートの実行

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオスコアリングエキスパートを実行するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. 画面の下部にある「シナリオスコアリングのエキスパート」アイコン ![ シナリオスコアリングのエキスパート ](assets/scoring-expert-icon.png)をクリックします。

   シナリオスコアリングエキスパートパネルが開きます。
1. **評価**&#x200B;をクリックします。

Scenario Scoring Expertは、10点満点のスコアを返し、どのチェックが成功したか失敗したかを示します。 チェックが失敗した場合、シナリオスコアリングエキスパートは、シナリオがこれらのチェックを満たしていることを確認する方法に関する推奨事項を提供します。

![ シナリオスコア ](assets/scenario-score.png)

## シナリオスコアリングチェック

シナリオスコアリングエキスパートは、次のチェックを使用します。

* シナリオには名前を付ける必要があります。
* すべてのモジュールにはラベルをつける必要があります。
* シナリオは、設定されたスケジュールで実行する必要があります。

  手順について詳しくは、[シナリオのスケジュール](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)を参照してください。
* シナリオブループリントサイズは5 MB未満である必要があります。

  詳しくは、[Fusionのパフォーマンスガードレール ](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#scenarios)を参照してください。
* Workfront インスタントトリガーモジュールを使用する場合は、フィルタリングする必要があります。

  手順については、「[Workfront > [!UICONTROL Watch Events] モジュール ](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules)」の「Event サブスクリプションフィルター」を参照してください。
