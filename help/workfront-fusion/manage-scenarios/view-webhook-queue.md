---
title: kのキュー
description: 多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。 インスタントトリガーは、webhookとも呼ばれ、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中の場合など、処理を待っている間にWebhookのキューに入ります。 Webhookのキューを表示できます。
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
TQID: https://experienceleague.adobe.com/FtTjoNtYNM9kuPDMaHa4883m13pLO2MRat5ohnjXuAM
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 47%

---

# Web フックのキューを表示する

多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。 インスタントトリガーは、webhookとも呼ばれ、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中の場合など、処理を待っている間にWebhookのキューに入ります。 Webhookのキューを表示できます。

受信Webhook データは、シナリオ設定パネルの「データは機密」オプションの設定方法に関係なく、常にキューに保存されます。 データがシナリオで処理されると、そのデータはキューから完全に削除されます。

Webhook について詳しくは、[インスタントトリガー（Webhook）](/help/workfront-fusion/references/modules/webhooks-reference.md)を参照してください。

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

## Web フックのキューを表示する

受信 Web フックからのメッセージはすべて、Web フックのキューに保存されます。

シナリオに現在キューがある場合、そのシナリオにバナーが表示されます。

![&#x200B; キューのバナー](assets/queue-banner.png)

Webhookのキューを表示するには：

1. 左側のメニューで、「**[!UICONTROL Web フック]**」をクリックします。
1. キューを表示するWebhookを探します。
1. 受信したイベント ボタンでイベントの数を探します。

   ![Webhook キュー](assets/webhook-queue.png)

1. ボタンをクリックして、キュー内のイベントに関する詳細を表示します。
