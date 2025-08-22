---
title: シナリオエディター
description: シナリオエディターを使用すると、視覚的なインターフェイスでシナリオを作成および編集できます。
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 28%

---

# シナリオエディター

シナリオエディターを使用すると、視覚的なインターフェイスでシナリオを作成および編集できます。

![ シナリオエディター ](assets/scenario-editor.jpg)

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## シナリオエディターを開き、モジュールを追加します。

1. 左側のパネルで **[!UICONTROL シナリオ]**![ シナリオアイコン ](assets/scenarios-icon.png) をクリックします。
1. 疑問符アイコン ![ 質問アイコン ](assets/question-mark-full-size.png) をクリックし、開始するアプリまたはサービスを見つけてクリックします。 モジュールの設定について詳しくは、「[ モジュールの設定 ](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md)」を参照してください。

## 使用可能なシナリオエディターのアクション

### シナリオを実行

| アクション | 詳細 |
|----------|----------|
| シナリオのテスト実行を行う | シナリオをアクティベートする前に、シナリオが期待どおりに実行されることを確認します。 アクティブ化すると、シナリオはスケジュールに従って実行されます。すべてが期待どおりに実行されない場合は、[ エラー処理の追加 ](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) を参照して、エラーの処理方法を確認してください。 |

![ 「シナリオを実行」ボタン ](assets/run-your-scenario.png)

### スケジュール設定

| アクション | 詳細 |
|----------|----------|
| シナリオのスケジュール設定 | デフォルトでは、シナリオは 15 分ごとに実行されます。アクティブ化されたシナリオを実行するタイミングと頻度を定義することで、これを変更できます。Fusion シナリオは、5 分ごとに実行するようにスケジュールできます。 詳しくは、[ シナリオのスケジュール設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。 |

![ スケジュールパネル ](assets/scheduling-scenario-editor.png)

### コントロール

| アクション | 詳細 |
|----------|----------|
| 保存します。 | シナリオを保存した後、将来アクセスする必要がある場合、「...」メニューから新しいバージョンを使用できます。以前に保存したシナリオのバージョンは 60 日間のみ使用できます。 |
| シナリオ設定 | シナリオ設定パネルには、シナリオの詳細設定が含まれています。 使用可能な設定について詳しくは、[ シナリオ設定の設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。 |
| メモ | シナリオに関するメモを作成します。 他のユーザーは、シナリオ内でこれらのメモを表示できます。 |
| 自動整列 | シナリオ内のモジュールを自動整列します。 |
| 説明フロー | シナリオでのデータのフローを示すアニメーションを表示します。 |
| 開発ツール | 開発ツールを使用すると、シナリオのすべての手動実行を確認し、実行されたすべての操作を確認し、実行されたすべての API 呼び出しの詳細を確認できます。 エラーの原因となったモジュール、操作、または単一の応答を確認し、その知識を使用してシナリオを絞り込むことができます。 詳しくは、[ シナリオのデバッグ ](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) を参照してください。 |
| その他 | その他メニューで、ブループリントを読み込みまたは書き出し、シナリオを以前のバージョンに復元することができます。 |

![ コントロールパネル ](assets/controls-editor-scenario.png)

### ツール

| アクション | 詳細 |
|----------|----------|
| フロー制御 | 設定を構成して、データのフローを制御します。 詳しくは、「必要なリンク [ を参照してください ]。 |
| ツール | 「ツール」セクションには、シナリオを強化できる便利なモジュールがいくつか含まれています。 詳しくは、「必要なリンク [ を参照してください ]。 |
| テキストパーサー | テキストパーサーツールを使用して、他のシナリオモジュールで使用するテキストを解析します。 テキストパーサーは接続を必要としません。 詳しくは、「必要なリンク [ を参照してください ]。 |

![ ツールパネル ](assets/tools-scenario-editor.png)

### お気に入り

「お気に入り」アイコンを使用して、頻繁に使用するモジュールを追加できます。

![ お気に入りパネル ](assets/favorites-scenario-editor.png)
