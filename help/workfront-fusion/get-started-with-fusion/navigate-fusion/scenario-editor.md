---
title: シナリオエディター
description: シナリオエディターを使用すると、視覚的なインターフェイスでシナリオを作成および編集できます。
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: f968b9141173725160cea36575ad4e02a09a5e3f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 33%

---

# シナリオエディター

シナリオエディターを使用すると、視覚的なインターフェイスでシナリオを作成および編集できます。

![ シナリオエディター ](assets/scenario-editor.jpg)

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
   <td> <p>Standard</p><p>Work またはそれ以上</p> </td> 
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

これらのコントロールの一部を表示するには、コントロール領域の 3 ドットアイコンをクリックする必要がある場合があります。

| アクション | 詳細 |
|----------|----------|
| 保存します。 <p>![ 保存アイコン ](assets/save-icon.png)</p> | シナリオを保存した後、将来アクセスする必要がある場合、「...」メニューから新しいバージョンを使用できます。以前に保存したシナリオのバージョンは 60 日間のみ使用できます。 |
| シナリオ設定 <p>![ シナリオ設定アイコン ](assets/scenario-settings-icon.png)</p> | シナリオ設定パネルには、シナリオの詳細設定が含まれています。 使用可能な設定について詳しくは、[ シナリオ設定の設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。 |
| メモ  <p>![ メモアイコン ](assets/notes-icon.png)</p> | シナリオに関するメモを作成します。 他のユーザーは、シナリオ内でこれらのメモを表示できます。 |
| 自動整列 <p>![ 自動整列アイコン ](assets/auto-align-icon.png)</p> | シナリオ内のモジュールを自動整列します。 |
| 検索モジュール ![ 検索モジュール ](assets/search-modules-icon.png)  </p> | モジュールを探すための検索語句を入力し、そのモジュールに表示する検索結果をクリックします。 モジュール名、ID、タイプまたはアプリケーションで検索できます。 |
| 説明フロー  <p>![ フローの説明アイコン ](assets/explain-flow-icon.png) </p> | 移動するドットがシナリオ内でのデータのフローを示すアニメーションを表示します。 |
| DevTool <p>![DevTool アイコン ](assets/devtool-icon.png)</p> | 開発ツールを使用すると、シナリオのすべての手動実行を確認し、実行されたすべての操作を確認し、実行されたすべての API 呼び出しの詳細を確認できます。 エラーの原因となったモジュール、操作、または単一の応答を確認し、その知識を使用してシナリオを絞り込むことができます。 詳しくは、[ シナリオのデバッグ ](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) を参照してください。 |
| ブループリントをエクスポート  <p>![ ブループリントアイコンを書き出し ](assets/export-blueprint-icon.png) </p> | 現在のシナリオのブループリントを書き出します。 |
| ブループリントを読み込み  <p>![ ブループリントを読み込みアイコン ](assets/import-blueprint-icon.png) </p> | 以前に書き出したシナリオのブループリントを読み込みます。 |
| 以前のバージョン  <p>![ 以前のバージョンのアイコン ](assets//previous-version-icon.png) </p> | このシナリオの以前のバージョンを表示します。 |

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
