---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 基本シナリオへの Webhook の追加
description: Webhook は、インスタントトリガーとも呼ばれ、特定のスケジュールではなく、変更が行われるたびにトリガーを開始できる特定の種類のシナリオモジュールです。
author: Becky
feature: Workfront Fusion
exl-id: 28ecca1f-a9c3-4b3d-95f5-73cb9a5dc4b9
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 4%

---

# 基本シナリオへの Webhook の追加

Webhook は、インスタントトリガーとも呼ばれ、特定のスケジュールではなく、変更が行われるたびにトリガーを開始できる特定の種類のシナリオモジュールです。

この例では、特定のリクエストキューにリクエストが送信されたらすぐにシナリオを開始する Webhook を追加します。 次に、シナリオはこれらのリクエストをプロジェクトに変換します。

この例では、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で作成したシナリオを変更します。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>Workfront Automation and Integration を含むすべてのパッケージ</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>Workfront Fusion のライセンス要件はありません。</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>Workfront Fusion で接続する任意のアプリケーションやサービスのアカウントが必要です。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

この手順を実行する前に、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で説明されているシナリオを作成する必要があります。

## Webhook の追加と設定


### Webhook モジュールの追加

1. シナリオエディターでシナリオを開きます。
1. 最初のモジュールを右クリックし、「**モジュールを削除**」を選択します。

   モジュールが削除され、空白のプレースホルダーが残ります。

1. 空のモジュールをクリックし、アプリのリストから **0&rbrace;Adobe Workfront&rbrace; を選択します。**
1. **イベントをウォッチ** を選択します。
1. Webhook フィールドの横にある「**追加**」をクリックします。
1. 「レコードタイプ」フィールドで「**イシュー**」を選択すると、イシューの変更がトリガーされるようになります。
1. 「状態」フィールドで「**新しい状態**」を選択します。 これは、フィルターに使用される必須フィールドですが、この例では扱いません。
1. 「レコード生成元」フィールドで、「**新しいレコードのみ**」を選択します。 これにより、イシューが更新や削除されたときではなく、イシューが追加されたときにシナリオがトリガーするようになります。
1. 「**保存**」をクリックして、モジュール設定を保存します。

## 2 つ目のモジュールの更新

1. シナリオを開きます。
1. **オブジェクトを変換** モジュールをクリックして開きます。
1. 「イシュー ID」フィールドで、黒の ID ブロックを削除します。 ブロックは、マッピング元のモジュールが使用できなくなったため、黒になります。
1. 最初のモジュール（イベントを監視）の下にある ID ブロックを選択して、2 番目のモジュールにマッピングします。
1. 「**OK**」をクリックします。



### テストしてアクティブ化

1. シナリオエディターの左下隅にある「**[!UICONTROL 1 回実行]**」をクリックします。

   新しいリクエストを監視するには、シナリオが実行されている必要があります。
1. Fusion が接続するWorkfront環境に移動して、問題を追加します。

   シナリオを実行する必要があります。
1. 出力を調べて、シナリオが期待どおりに実行されたことを確認します。
1. シナリオが期待どおりに動作していることを確認したら、画面の左下にある **スケジュール** トグルをクリックして **オン** にします。

   これにより、シナリオがアクティブになります。
1. Workfront Fusion で、左下隅付近の **[!UICONTROL 保存]** をクリックして、シナリオの進捗を保存します。
