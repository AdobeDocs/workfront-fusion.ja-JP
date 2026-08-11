---
title: 通知オプションの設定
description: メール通知オプションは、チームレベルで設定されます。
author: Becky
feature: Workfront Fusion
exl-id: 570a09fc-01a9-4952-8a2b-8bfdd86d0bd8
TQID: https://experienceleague.adobe.com/-HytP4gfrhiiSn-dg5ndg1YC6NTMC-NURYzSFgO5kIo
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 90a58033e240271b88d01b9daef9763f38264056
workflow-type: tm+mt
source-wordcount: 665
ht-degree: 15%

---

# 通知オプションの設定

組織でAdobe統合シェルを使用している場合は、Adobe通知領域から通知を受け取ります。

組織がAdobe Unified Shellに移行されていない場合は、チームが受け取る通知を選択できます。 通知はチームレベルで設定されます。

通知の送信先となる状況を制御できます。

* 警告の通知：シナリオ実行が警告をログに記録すると、Fusionは通知を送信します。
* エラー時に通知：シナリオの実行が失敗すると、Fusionが通知を送信します。
* シナリオが無効になっている場合に通知する：Fusionは、連続エラーが多すぎるなど、シナリオが自動的に非アクティブ化されたときに通知を送信します。

通知は、チームレベルまたはシナリオレベルで設定できます。 シナリオレベルの通知は、チームレベルで設定された通知を上書きします。 つまり、シナリオ設定がチーム設定と直接矛盾する場合は、シナリオ設定に従います。 チーム通知の設定には、その設定の上書きがあるかどうかが表示されます。

デフォルトでは、すべての通知タイプがWorkfront Fusionで有効になっています。

>[!IMPORTANT]
>
>Workfront Fusionから通知を受け取るには、Adobe CX Enterprise通知設定でFusion通知を有効にする必要があります。 これらの設定にアクセスするには、画面の右上隅にある通知ベルをクリックし、設定アイコンをクリックします。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">役割</td> 
   <td> 
     <p>通知設定を調整するFusion組織およびチームのメンバーである必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## チームレベルの通知設定の表示と管理

1. Workfront Fusionで、左側のナビゲーションで「**チームの概要**」をクリックします。
1. 「**通知オプション**」タブをクリックします。

   通知オプションリストが開きます。 オーバーライドがある場合は、その設定の横にオーバーライドの数が表示されます。

1. （条件付き）上書きがある場合は、チーム通知設定を上書きするシナリオを表示するには、その設定の3点メニューをクリックします。

   このメニューのシナリオをクリックすると、そのシナリオに直接移動できます。

   ![ シナリオメニューを上書き](assets/view-notification-override.png)

1. 通知タイプの既定の設定を復元するには、この記事の「[通知の既定の設定を復元する](#restore-notification-defaults)」を参照してください。

通知オプションリストへの変更は、自動的に保存されます。

## シナリオレベルの通知設定

個々のシナリオの通知設定は、そのシナリオのシナリオ設定パネルで設定されます。

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. シナリオの下部にある[!UICONTROL  シナリオ設定] アイコン ![ シナリオ設定アイコン ](assets/scenario-settings-icon.png)をクリックします。
1. シナリオ設定パネルで、パネルの下部にある&#x200B;**詳細設定を表示**&#x200B;をクリックします。
1. 必要に応じて、警告&#x200B;**の**&#x200B;通知、エラー&#x200B;**の**&#x200B;通知、**シナリオが無効な場合の通知**&#x200B;の設定を調整します。
1. 「**OK**」をクリックして、シナリオ設定を保存して終了します。

## 通知の既定値に戻す

チームの通知設定を「通知オプション」タブからデフォルトに戻すことができます。 これにより、通知オプションが有効に設定され、その通知タイプのシナリオ通知の上書きが削除されます。

通知タイプが現在デフォルトに設定されている場合、**デフォルトに戻す** アイコンは表示されません。

1. Workfront Fusionで、左側のナビゲーションで「**チームの概要**」をクリックします。
1. 「**通知オプション**」タブをクリックします。

   通知オプションリストが開きます。 通知タイプが現在デフォルトに設定されていない場合は、その通知タイプに「デフォルトに戻す」アイコンが表示されます。

   ![既定の表示に戻す](assets/restore-notification-defaults.png)

1. シナリオの上書きを含め、その通知タイプのデフォルト設定を復元するには、その通知タイプの&#x200B;**デフォルトにリセット** アイコン ![ デフォルトにリセット ](assets/restore-default-icon.png)をクリックします。

通知オプションリストへの変更は、自動的に保存されます。

<!--

## Set notification options

If your organization is not on the Adobe Unified Shell, you can set notification settings directly in Fusion.

Email notification options are set on the team level.

1. In the left navigation panel, click **[!UICONTROL Team]**
1. Select the **[!UICONTROL Notification Options]** tab.
1. Enable the notifications that you want the team to receive.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">'[!UICONTROL Warning in scenario run]'</td> 
      <td> <p>Receive an email when there is a warning in a scenario run</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Errors in scenario run]</td> 
      <td>Receive an email when there is an error in a scenario run.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Scenario deactivation]</p> </td> 
      <td><p>Receive an email when a scenario deactivates.</p><p>In some cases, a scenario might be deactivated by the Workfront Fusion engineering team because the scenario is causing performance or other issues. In these cases, you do not receive notifications in Workfront Fusion. </p></td>

</tr>
</tbody>
</table>

Changes to notification options save automatically.

-->
