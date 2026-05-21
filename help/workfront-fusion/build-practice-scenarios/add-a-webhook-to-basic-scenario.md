---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 基本シナリオへの Webhook の追加
description: Webhookは、インスタントトリガーとも呼ばれ、特定のスケジュールではなく、変更があるたびにトリガーを開始できる特定の種類のシナリオモジュールです。
author: Becky
feature: Workfront Fusion
exl-id: 28ecca1f-a9c3-4b3d-95f5-73cb9a5dc4b9
TQID: https://experienceleague.adobe.com/V3cpVf8NzJdGjSZvPA0Hy0Uui-zSdd986plS1Us0oNI
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 513
ht-degree: 24%

---

# 基本シナリオへの Webhook の追加

Webhookは、インスタントトリガーとも呼ばれ、特定のスケジュールではなく、変更があるたびにトリガーを開始できる特定の種類のシナリオモジュールです。

この例では、リクエストが特定のリクエストキューに送信されるとすぐにシナリオを開始するWebhookを追加します。 その後、シナリオはこれらのリクエストをプロジェクトに変換します。

この例では、[基本シナリオの作成](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)で作成したシナリオを変更します。

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

## 前提条件

この手順に従う前に、[基本シナリオの作成](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)で説明したシナリオを作成する必要があります。

## Webhookの追加と設定


### Webhook モジュールの追加

1. シナリオエディターでシナリオを開きます。
1. 最初のモジュールを右クリックし、**モジュールを削除**&#x200B;を選択します。

   モジュールが削除され、空白のプレースホルダーが残ります。

1. 空白のモジュールをクリックし、アプリケーションのリストから&#x200B;**Adobe Workfront**&#x200B;を選択します。
1. 「**イベントを視聴**」を選択します。
1. 「Webhook」フィールドの横にある「**追加**」をクリックします。
1. 「レコードタイプ」フィールドで「**問題**」を選択すると、問題の変更がトリガーされます。
1. 「状態」フィールドで、**新しい状態**&#x200B;を選択します。 これは、フィルターに使用される必須フィールドです。この例では説明しません。
1. 「レコードの生成元」フィールドで、「**新しいレコードのみ**」を選択します。 これにより、問題が追加されたときに、更新または削除されたときではなく、シナリオをトリガーできます。
1. 「**保存**」をクリックして、モジュール設定を保存します。

## 2つ目のモジュールを更新する

1. シナリオを開きます。
1. 「**オブジェクトを変換**」モジュールをクリックして開きます。
1. 「問題ID」フィールドで、黒いID ブロックを削除します。 ブロックは黒です。これは、マッピング元のモジュールが使用できなくなったためです。
1. 最初のモジュール（監視イベント）の下にあるID ブロックを選択して、2番目のモジュールにマッピングします。
1. 「**OK**」をクリックします。



### 検証と活用

1. シナリオエディターの左下隅にある「**[!UICONTROL 1 回実行]**」をクリックします。

   新しいリクエストを監視するには、シナリオが実行されている必要があります。
1. Fusionが接続しているWorkfront環境に移動し、問題を追加します。

   シナリオを実行する必要があります。
1. 出力を調べて、シナリオが期待どおりに実行されていることを確認します。
1. シナリオが期待どおりに機能していることを確認したら、画面の左下にある&#x200B;**スケジュール** トグルを&#x200B;**オン**&#x200B;にクリックします。

   これにより、シナリオがアクティブになります。
1. Workfront Fusionで、左下隅付近の&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックして、シナリオの進行状況を保存します。
