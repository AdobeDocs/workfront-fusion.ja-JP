---
title: キュー
description: 多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。インスタントトリガー（Webhook とも呼ばれます）は、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中であるなど、処理を待っている間、Webhook のキューに移動します。 Webhook のキューを確認できます。
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 25%

---

# Web フックのキューを表示する

多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。インスタントトリガー（Webhook とも呼ばれます）は、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中であるなど、処理を待っている間、Webhook のキューに移動します。 Webhook のキューを確認できます。

シナリオ設定パネルの「データは機密です」オプションの設定方法に関係なく、受信 Webhook データは常にキューに保存されます。 シナリオで処理されたデータは、キューから完全に削除されます。

Webhook について詳しくは、[&#x200B; インスタントトリガー（Webhook） &#x200B;](/help/workfront-fusion/references/modules/webhooks-reference.md) を参照してください。

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
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Web フックのキューを表示する

受信 Web フックからのメッセージはすべて、Web フックのキューに保存されます。

シナリオに現在キューがある場合、そのシナリオにバナーが表示されます。

![&#x200B; キューバナー &#x200B;](assets/queue-banner.png)

Webhook のキューを表示するには：

1. 左側のメニューで、「**[!UICONTROL Web フック]**」をクリックします。
1. キューを表示する Webhook を見つけます。
1. 「受信したイベント」ボタンでイベントの数を見つけます。

   ![Webhook キュー &#x200B;](assets/webhook-queue.png)

1. ボタンをクリックすると、キュー内のイベントに関する詳細が表示されます。
