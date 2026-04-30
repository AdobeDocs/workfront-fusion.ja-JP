---
title: Webhookの編集
description: WorkfrontおよびWorkfront Planning コネクタの既存のWebhookを編集できます。
author: Becky
feature: Workfront Fusion
source-git-commit: 2561c911b9b542a7b143fae745baf4e1de45be38
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 5%

---

# Web フックを編集

既存のWebhookを編集できます。 これらのWebhookを使用するシナリオでは、新しい設定が使用されるため、新しいWebhookを作成して、影響を受けるすべてのシナリオに手動で割り当てる必要はありません。

Webhookは、次のコネクタに対してのみ編集できます。

* Workfront
* Workfront Planning

>[!IMPORTANT]
>
>Webhookを更新する際には、次の点を考慮してください。
>
>* 編集されたWebhookは、Workfront イベントサブスクリプションによって新しいサブスクリプションとして扱われます。 イベントのサブスクリプション履歴は、別のイベントのサブスクリプションと見なされるため、以前のWebhook設定では保持されません。
>* 古いイベント サブスクリプションから新しいイベント サブスクリプションへの切り替えは、完全に同期されていない可能性があります。 したがって、イベントを2回受信したり（新しいサブスクリプションが古いサブスクリプションの実行開始前に開始された場合）、イベントを見逃したり（古いサブスクリプションが新しいサブスクリプションの実行開始前に停止した場合）することができます。

## Webhookの編集

シナリオまたはWebhook リストからWebhookを編集できます。

### シナリオでのWebhookの編集

>[!NOTE]
>
>この機能は、WorkfrontまたはWorkfront Planningのインスタントトリガーモジュールを持つシナリオでのみ使用できます。

1. 編集するWebhookを含むシナリオに移動します。
1. シナリオのトリガーモジュールで、「Webhook」フィールドの横にあるドロップダウンをクリックし、「**アイテムを編集**」を選択します。

   Webhookの設定ウィンドウが開き、既存の設定が入力されます。

1. Webhookに必要な編集を加えます。
1. 「**保存**」をクリックして Webhook を保存し、モジュールに戻ります。

### Webhook リストからのWebhookの編集

1. 左側のナビゲーションで、**Webhook** ![Webhook アイコン ](assets/webhooks-icon.png)を選択します。
1. 編集するWebhookの横にあるチェックボックスをクリックします。
1. 画面下部の青いバナーで、**編集**&#x200B;をクリックします。
1. Webhookに必要な編集を加えます。
1. **保存**&#x200B;をクリックしてWebhookを保存し、Webhook リストに戻ります。

