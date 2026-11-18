---
title: kのキュー
description: 多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。 インスタントトリガーは、webhookとも呼ばれ、これらのイベントを使用してシナリオを開始できます。 イベントは、シナリオが既に実行中の場合など、処理を待っている間にWebhookのキューに入ります。 Webhookのキューを表示できます。
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
TQID: 'https://experienceleague.adobe.com/FtTjoNtYNM9kuPDMaHa4883m13pLO2MRat5ohnjXuAM'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 1c28e4007e3e9d6503618482002e506f9393ee57
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 26%
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

Webhookのキューページのレイアウトは、**[!UICONTROL シナリオ]**&#x200B;および&#x200B;**[!UICONTROL Webhook]**&#x200B;のリストと同じです。

>[!NOTE]
>
>検索と並べ替えは、現在テーブルに読み込まれているイベントにのみ適用され、キュー全体には適用されません。 より多くのイベントを含めるには、最初に追加のイベントを読み込みます。

Webhookのキューを表示および管理するには：

1. 左側のメニューで、「**[!UICONTROL Web フック]**」をクリックします。
1. キューを表示するWebhookを探します。
1. イベントの数フルキュー列を探します。

   ![Webhook キュー](assets/webhook-queue.png)

1. キュー内のイベントの詳細を表示するには、**操作** ボタンをクリックします。

   Webhookのキューページが開きます。 このページには、次の列を持つテーブル内のキュー内のイベントが一覧表示されます。**[!UICONTROL ID]**、**[!UICONTROL 作成日時]**、**[!UICONTROL サイズ]**、および&#x200B;**[!UICONTROL 詳細]**。

1. （オプション）テーブル内のイベントをフィルタリングするには、テーブルの上の&#x200B;**[!UICONTROL 検索]** フィールドにテキストを入力します。
1. （オプション）イベントを並べ替えるには、**[!UICONTROL ID]**、**[!UICONTROL 作成日時]**、または&#x200B;**[!UICONTROL サイズ]**&#x200B;列ヘッダーをクリックします。
1. （オプション）各ページに表示されるイベントの数を変更するには、ページの下部にある「**[!UICONTROL 表示]**」ドロップダウンリストで数値を選択します。
1. （オプション）イベントのページ間を移動するには、ページの下部にある&#x200B;**[!UICONTROL First]**、**[!UICONTROL Previous]**、**[!UICONTROL Next]**、または&#x200B;**[!UICONTROL Last]**&#x200B;をクリックします。

   これらのボタンは、キューにイベントのページが1つしかない場合は使用できません。

1. （オプション）イベントのペイロードを表示するには、イベントの行の&#x200B;**[!UICONTROL 詳細]**&#x200B;をクリックします。

   詳細ダイアログが開き、イベントのペイロードが表示されます。

1. （オプション）イベントを削除するには：

   1. 次のいずれかの操作を行って、削除するイベントを選択します。

      * 選択する各イベントの横にあるチェックボックスをオンにします。
      * 現在ロードされているイベントだけでなく、キュー全体を選択するには、「**[!UICONTROL すべてを選択]**」チェックボックスを選択します。 次に、選択範囲から除外するイベントのチェックボックスをオフにします。

   1. 画面下部近くのバーで、**削除**&#x200B;をクリックします。
