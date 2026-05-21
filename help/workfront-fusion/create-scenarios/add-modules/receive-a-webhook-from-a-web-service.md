---
title: コネクタを使用しないweb サービスのWebhookの設定
description: 現在、web サービスにWorkfront Fusionに専用コネクタがないが、Webhookの送信をサポートしている場合は、カスタム Webhook モジュールをインスタントトリガーとして使用して、そのサービスをシナリオに追加できます。
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
TQID: https://experienceleague.adobe.com/Ux37ZShkz3kxnJg3Guwqvqt8TISuzV0kAVZ-kKfy0zI
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 37%

---

# コネクタを使用しないweb サービスのWebhookの設定

現在、web サービスにWorkfront Fusionに専用コネクタがないが、Webhookの送信をサポートしている場合は、カスタム Webhook モジュールをインスタントトリガーとして使用して、そのサービスをシナリオに追加できます。 このプロセスはWebhookの受信と呼ばれ、接続するアプリケーション側で何らかの設定が必要です。

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

## Web フックを受信

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. Webhookを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. **Webhook > Custom Webhook** モジュールを追加して、シナリオを開始します。
1. 「Webhook」フィールドの横にある「**追加**」をクリックします。
1. 表示されるボックスに&#x200B;**Webhook名**&#x200B;を入力します
1. （オプション） webhookを設定します。

   手順については、[Webhook](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)を参照してください。

1. 「**保存**」をクリックします。

1. **アドレスをクリップボードにコピー**、次に「**OK**」をクリックします。

1. Web サービスにログインし、以下の操作を行います。

   1. Web サービスの「設定」領域で、Webhookを作成します。

      具体的な手順は、アプリケーションによって異なります。 アプリケーションのドキュメントで「Webhookの作成」を検索することをお勧めします。
   1. 手順3でクリップボードにコピーしたアドレスを貼り付けます。
   1. Web フックをトリガーするイベントを選択します。

1. シナリオを実行します。

   イベントが発生すると、カスタム Webhook モジュールのトリガーとシナリオが実行されます。
