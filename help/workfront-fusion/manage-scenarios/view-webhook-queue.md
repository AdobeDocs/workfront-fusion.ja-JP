---
title: キュー
description: 多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。インスタントトリガー（Webhook とも呼ばれます）は、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中であるなど、処理を待っている間、Webhook のキューに移動します。 Webhook のキューを確認できます。
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
source-git-commit: 3d06958b6f706f4f974230853fb6553232656fd3
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 25%

---

# Web フックのキューを表示する

多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。インスタントトリガー（Webhook とも呼ばれます）は、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中であるなど、処理を待っている間、Webhook のキューに移動します。 Webhook のキューを確認できます。

シナリオ設定パネルの「データは機密です」オプションの設定方法に関係なく、受信 Webhook データは常にキューに保存されます。 シナリオで処理されたデータは、キューから完全に削除されます。

Webhook について詳しくは、[ インスタントトリガー（Webhook） ](/help/workfront-fusion/references/modules/webhooks-reference.md) を参照してください。

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

## Web フックのキューを表示する

受信 Web フックからのメッセージはすべて、Web フックのキューに保存されます。

シナリオに現在キューがある場合、そのシナリオにバナーが表示されます。

![ キューバナー ](assets/queue-banner.png)

Webhook のキューを表示するには：

1. 左側のメニューで「**[!UICONTROL Webhooks]**」をクリックします。
1. キューを表示する Webhook を見つけます。
1. 「受信したイベント」ボタンでイベントの数を見つけます。

   ![Webhook キュー ](assets/webhook-queue.png)

1. ボタンをクリックすると、キュー内のイベントに関する詳細が表示されます。
