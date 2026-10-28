---
title: 組織のインサイトダッシュボードの表示
description: Fusion管理者は、組織の実行指標を表示するダッシュボードを表示できます。
author: Becky
feature: Workfront Fusion
exl-id: 8f80f86a-69e5-48a1-9812-87322a4959a6
TQID: 'https://experienceleague.adobe.com/tBZCbpImQxY42gOE8e04aQwCJC8EKgrDTIAt6Sw1KaU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 45c755a2f6152b6e230864e4c840d0334705bd22
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 5%
---
# 組織のインサイトダッシュボードの表示

Fusion Insights ダッシュボードでは、どのシナリオが最も頻繁に実行されているか、どこで遅延が発生しているか、ワーカープールがどの程度効果的に動作しているかをすばやく確認できます。 これにより、実行ボリューム、キューの深さ、プールの使用率、シナリオレベルのパフォーマンスをリアルタイムで可視化できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>Adobe Workfront Workflow UltimateとAdobe Workfront Automation and Integration Ultimate</p><p>Workfront Ultimate</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## インサイトダッシュボードコンポーネント

>[!NOTE]
>
>指標はワーカープールで表示されます。 別のワーカープールを表示するには、ダッシュボードの左上隅付近にある「プール」フィールドをクリックし、指標を表示するプールを選択します。

<!--

>[!NOTE]
>
>Organizations can request provisioning for one additional worker pool (for a total of 2).

-->

Fusion Insights ダッシュボードでは、次の指標を確認できます。

* **失敗した実行ログ**
この表には、組織全体で失敗したシナリオまたは警告したシナリオの実行がすべて一覧表示されるため、ダッシュボードを離れることなく問題の実行を検索してトラブルシューティングを行うことができます。
* **組織操作**
このグラフでは、組織で使用されている操作の数を表示できます。 特定のチームまたはシナリオを選択し、先週、月、または年の操作を表示できます。
* **操作ごとの上位シナリオ**
このグラフでは、最も多くの操作を使用しているシナリオを表示できます。 特定のチームを選択するか、最終日、週、または月のデータを表示できます。

<!--

* **Executions waiting to be processed**
   This chart shows the number of executions waiting to be processed (also known as the execution backlog) at a given point in time. 

   A high number of executions waiting to be processed may affect performance in your Fusion instance. You will receive a notification if your execution backlog reaches 5000 executions. We recommend identifying responsible scenarios and modifying or disabling them. If the high execution backlog persists, the Fusion team will protect the performance of your Fusion instance by disabling the responsible scenarios.
* **Pool Utilization**
   This chart shows worker pool utilization over time. If this chart routinely shows worker pool utilization, you may want to assign some scenarios to another pool.

   If a pool is nearing 100% utilization, other resources that use the same pool may be delayed or disrupted. If this occurs, we recommend reassigning a high-usage scenario to another worker pool, or modifying existing scenarios to be less resource intensive.
* **Executions per scenario**
   This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

   You can use this chart to identify which scenarios may be causing an execution backlog or high worker pool utilization. 
* **Duration of executions**
   This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

   You can use this chart to identify scenarios that are taking longer than usual, including those affected by issues with a connected app or service.

-->

## Fusion Insights ダッシュボードを見る

1. Fusionで、左側のナビゲーションで「**インサイト**」をクリックします。

   ダッシュボードが開きます。

1. 特定の時点のデータを表示するには、ダッシュボードにカーソルを合わせて、表示する時点の上にカーソルを合わせます。

   すべてのグラフにその時点に線が表示され、各グラフにその時点のデータを示すウィンドウが表示されます。
1. シナリオごとの実行チャートまたは実行の期間チャートで特定のシナリオのデータを表示するには、データを表示するシナリオの色のバーをクリックします。 すべてのシナリオを表示するビューに戻るには、グラフをもう一度クリックします。
1. シナリオごとの実行チャートまたは実行の期間チャートに表示される特定のシナリオに移動するには、シナリオの色のバーを右クリックし、**新しいタブでシナリオを開く**&#x200B;を選択します。
1. グラフを展開するには、そのグラフの右上隅にある&#x200B;**展開** アイコン ![展開アイコン ](assets/expand-icon.png)をクリックします。
1. ダッシュボードの時間範囲を変更するには、ダッシュボードの右上隅にある「時間範囲」フィールドで、新しい時間枠を選択します。 使用可能な最長時間は24時間で、最短は15分です。
1. グラフを更新するには、ダッシュボードの右上隅付近にある「更新」アイコンをクリックします。
1. 別のワーカープールを表示するには、ダッシュボードの左上隅付近にある「プール」フィールドをクリックし、表示するプールを選択します。

## インサイトダッシュボードのカスタマイズ

インサイトダッシュボードに表示するウィジェットと、その順序を選択できます。

### ウィジェットの追加、削除、並べ替え

1. 左側のナビゲーションで、**インサイト** ![ インサイトアイコン ](assets/insights-icon.png)をクリックします。
1. インサイトヘッダーの「**[!UICONTROL カスタマイズ]**」をクリックします。

   サイドパネルが開きます。 すべてのウィジェットが、プレビュー、ウィジェット名、説明を表示するカードとしてリストされます。

1. ウィジェットを表示または非表示にするには、そのカードをクリックするか、カードの「**[!UICONTROL ウィジェットを追加]**」または「**[!UICONTROL ウィジェットを削除]**」ボタンをクリックします。

   表示されるウィジェットにはチェックマークが付きます。
1. ウィジェットを並べ替えるには、ウィジェットカードをパネル内の新しい位置にドラッグします。

   破線で囲まれたプレースホルダーとドロップバーにカードの到達場所が表示されます。

選択肢はブラウザーごとに保存されます。 後のリリースで追加されたウィジェットは、パネルに自動的に表示されます。

すべてのウィジェットを削除すると、「このページにはウィジェットがありません」というメッセージが表示されます。

## インサイトダッシュボードを更新する

各ウィジェットのデータを再読み込みするには、**[!UICONTROL カスタマイズ]**&#x200B;の横にある&#x200B;**[!UICONTROL 更新]**&#x200B;をクリックします。

* 各ウィジェットはフィルターを保持します。
* すべてのウィジェットの読み込みが完了するまで、**[!UICONTROL 更新]** ボタンに保留状態が表示されます。
* グラフは前のグラフを読み込み中のスピナーの下に置き、実行ログはデータの再読み込み中にスピナーの下のテーブルを暗くします。
* 更新が失敗した場合、ウィジェットは最後の良好なデータを保持します。

## インサイトツアーを見る

インサイトダッシュボードを初めて開いたときに、ウェルカムダイアログでツアーを開始するかスキップするかを選択できます。

ツアーでは、保存された順序で各ウィジェットがハイライト表示されます。また、タイトルバーの&#x200B;**[!UICONTROL カスタマイズ]** ボタンとパネル、**[!UICONTROL 更新]** ボタン、および&#x200B;**[!UICONTROL ツアーを再生]** ボタンもハイライト表示されます。

ツアーをいつでも再開するには、タイトルバーのツアー情報アイコン ![情報アイコン ](assets/insights-tour-information.png)をクリックします。

シナリオのリンクからインサイトダッシュボードを開くと、ツアーは開始されません。 詳しくは、この記事の「[ シナリオからインサイトダッシュボードを開く](#open-the-insights-dashboard-from-a-scenario)」を参照してください。

## IDでシナリオとチームを検索

**[!UICONTROL 組織の操作]**&#x200B;および&#x200B;**[!UICONTROL 操作ごとの上位シナリオ]** ウィジェットでは、**[!UICONTROL シナリオ]**&#x200B;および&#x200B;**[!UICONTROL チーム]**&#x200B;のフィールドがIDと名前で一致します。 各オプションは、「ID 123」などの名前の下にIDを表示します。

* リストには、最初の500のシナリオと最初の200のチームが読み込まれます。 読み込まれたリストにないIDを入力すると、Fusionは短い遅延後に自動的に検索します。
* シナリオをクリアすると、そのシナリオに対して自動的に入力されたチームもクリアされます。

>[!NOTE]
>
>実行ログのシナリオフィルターがIDで一致しません。

## シナリオからインサイトダッシュボードを開く

特定のシナリオとチームに絞り込まれた&#x200B;**[!UICONTROL 組織操作]** ウィジェットで、インサイトダッシュボードを開くことができます。

シナリオからインサイトページに移動するには：

1. シナリオの詳細ページを開きます。

   1. 左パネルの「**[!UICONTROL シナリオ]**」タブをクリックし、詳細が必要なシナリオをクリックします。

      または

      シナリオエディターでシナリオを操作している場合は、ウィンドウの左上隅付近にある左矢印![編集矢印を終了](assets/exit-editing-arrow.png)をクリックします。
      1. ページの上部にある「**レポート**」タブをクリックします。

* **[!UICONTROL 組織操作]** ウィジェットが開き、そのシナリオとチームがフィルタリングされ、ページがウィジェットにスクロールされます。
* ページからウィジェットを削除した場合は、代わりに「**[!UICONTROL ウィジェットを追加]**」ボタン付きの警告が表示されます。

## ダークモードの使用

インサイトダッシュボードとそのウィジェットは、ダークモード設定に自動的に従います。 設定を変更すると、ページは再読み込みなしで即座に更新され、現在の状態が維持されます。 ライトモードは変更されません。

## パフォーマンスウィジェットアクセス

**[!UICONTROL パフォーマンス]** ウィジェットは、次のいずれかの権限を持つユーザーにのみ表示されます。

* アクティブな組織内の組織編集
* 管理者ページの組織ビュー

ウィジェットは、ページと他のユーザー用の&#x200B;**[!UICONTROL カスタマイズ]** パネルから非表示になっています。 後でユーザーにアクセス権が付与されると、ウィジェットは保存された位置に戻ります。 インサイト URLを直接開いても、このチェックはバイパスされません。

## 実行ログの実行のフィルタリングとトリアージ

実行ログを使用して、組織全体で失敗したシナリオ実行や警告を返したシナリオ実行を検索し、繰り返し失敗した後に自動的に非アクティブ化されたシナリオを再アクティブ化します。

1. 実行ログで、次のいずれかの方法で実行をフィルタリングします。

   * [!UICONTROL チーム]
   * [!UICONTROL シナリオ]
   * [!UICONTROL 実行タイプ ]
   * [!UICONTROL 日付範囲]
   * [!UICONTROL 非アクティブ化状態]
   * [!UICONTROL  エラーメッセージ ]

   ほとんどのフィルターでは、選択した値のみ、またはそれ以外のすべての値に一致するように選択できます。

1. 実行をクリックすると、そのエラーに関する詳細が表示されます。
1. 繰り返しエラーが発生した後に自動的に非アクティブ化された1つ以上のシナリオを再アクティブ化するには、実行を選択し、**アクティブ化**&#x200B;をクリックします。

   >[!NOTE]
   >
   >シナリオを再アクティブ化する前に、期限が切れた資格情報やコネクタの問題など、エラーの原因を調査して、シナリオがすぐに再び失敗しないようにします。
