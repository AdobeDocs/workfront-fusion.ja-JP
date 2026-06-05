---
title: 特定のシナリオ実行のリトリガー
description: 特定のシナリオ実行を再トリガーして、更新されたシナリオブループリントを使用してデータを処理したり、データフローを表示したりできます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 0c732add9c1ec75d7aed43bb7097bb1c95aa6408
workflow-type: tm+mt
source-wordcount: 523
ht-degree: 18%

---

# 特定のシナリオ実行のリトリガー

特定のシナリオ実行を再トリガーして、更新されたシナリオブループリントを使用してデータを処理したり、データフローを表示したりできます。 実行を再試行すると、シナリオはその実行のデータを使用して実行されます。

例えば、シナリオを更新してイシューの作成などのアクションを追加する場合、更新前に発生した実行を再トリガーできます。 更新されたシナリオは、元のシナリオのトリガーイベントを使用して実行されますが、更新されたアクションが含まれます。 この例では、シナリオは新しい実行の一部としてイシューを作成します。

リトリガーは、Webhookトリガーを持つシナリオと子シナリオで使用できます。

Webhookを使用するシナリオをリトリガーする場合、元のWebhook イベントを再度使用できるため、シナリオをリトリガーするためにイベントを再作成する必要はありません。

連鎖シナリオを使用する場合は、子シナリオにも再トリガーを適用できます。 子シナリオは、親シナリオを再トリガーせずに、元の実行時に親シナリオから送信されたデータを使用して再トリガーできます。

Webhook について詳しくは、[インスタントトリガー（Webhook）](/help/workfront-fusion/references/modules/webhooks-reference.md)を参照してください。

シナリオの連鎖について詳しくは、[複数のシナリオを連鎖させる](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)を参照してください。

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

## 実行を再試行

シナリオ実行は、シナリオの図、シナリオの履歴領域、または特定のシナリオ実行のページから再試行できます。

### シナリオダイアグラムからの実行のリトリガー

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. リトリガーする実行を実行したシナリオを選択します。

   シナリオの図が開きます。
1. ページの右側にある実行リストで、リトリガーする実行を探します。
1. そのシナリオの&#x200B;**Retrigger**&#x200B;をクリックします。

![図からのリトリガー](assets/retrigger-from-diagram.png)

### シナリオ履歴から実行を再トリガー

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. リトリガーする実行を実行したシナリオを選択します。

   シナリオの図が開きます。

1. シナリオ名のすぐ下の「**履歴**」タブをクリックします。
1. リトリガーする実行を探します。 必要に応じて、フルテキスト検索を使用して検索できます。
1. そのシナリオの&#x200B;**Retrigger**&#x200B;をクリックします。

![履歴からのリトリガー](assets/retrigger-from-history.png)

### シナリオ実行ページからシナリオをリトリガーする

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. リトリガーする実行を実行したシナリオを選択します。

   シナリオの図が開きます。
1. ページの右側にある実行リストで、リトリガーする実行を探します。
1. 実行をクリックして開きます。
1. 実行ページで、**Retrigger**&#x200B;をクリックします。


![実行からのリトリガー](assets/retrigger-from-execution.png)






