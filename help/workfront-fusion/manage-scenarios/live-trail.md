---
title: ライブトレイルを使用したシナリオ実行のレビュー
description: ライブトレイルでは、1つのリストにモジュールリクエストと実行アクティビティを組み合わせて、シナリオ実行が表示されます。 任意の操作のリクエストと応答の詳細を開くことができます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
source-git-commit: 94449f8511d7480f1a4fc0ac6e8db9b067977abd
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 17%
---

# ライブトレイルを使用したシナリオ実行のレビュー

Live Trailは、シナリオの実行を表示します。 モジュールのリクエストと実行アクティビティを1つの時系列リストに組み合わせるので、シナリオエディターで実行を追跡し、キャンバスを離れることなく何が問題だったのかを確認できます。

>[!NOTE]
>
>この機能は、新しいシナリオエディターエクスペリエンスでのみ使用できます。 詳しくは、シナリオエディターの記事「[新しいエクスペリエンスと従来のエクスペリエンス &#x200B;](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)」を参照してください。

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## ライブトレイルを開く

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 確認するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. 例えば、**1回実行**&#x200B;をクリックして、シナリオの実行を開始します。



カンバスの右側のパネルでライブトレイルが開きます。 実行中にパネルを閉じると、画面の右側にある小さなタブを使用して、キャプチャしたイベントを失うことなく、パネルを再度開くことができます。

## ライブトレイルでのイベントの確認

Live Trailは、モジュールリクエストと実行アクティビティを発生した順序で一覧表示します。 実行できる操作：

* リストを検索します。
* ステータス別にリストをフィルタリングします。
* 実行が続く場合は、最新のイベントに従います。
* 現在のトレイルをクリアします。

## リクエストと応答の詳細の表示

1. ライブトレイルで、詳細を表示するリクエストをクリックします。

   リクエストを行ったモジュールがキャンバスに表示され、リクエストと応答の詳細がパネルで開きます。

1. 詳細を確認する： 詳細ビューには次のものが含まれます。

   * モジュールの操作の間のナビゲーション
   * リクエストヘッダーと本文
   * 応答ヘッダーと本文

1. （オプション） **Copy raw**&#x200B;または&#x200B;**Copy cURL**&#x200B;をクリックして、他の場所で使用する詳細をコピーします。

   * リクエストとレスポンスの生レポートをコピーします。
   * リクエストのcURL コマンドをコピーします。

1. リストに戻るには、パネルの左上にある戻る矢印をクリックします。

## リクエストとレスポンスの詳細が利用可能であることを確認します

リクエストとレスポンスの詳細は、スケジュールまたはトリガーされた実行ごとに保持されるわけではありません。これは、大量のストレージを必要とするためです。

* 1回実行すると、リクエストと応答の詳細が常に保持されます。
* シナリオの通常の実行の場合は、検査する実行の前に、シナリオ設定で「一時デバッグログ」をオンにします。 詳しくは、「シナリオ設定の構成」の「[一時デバッグログ &#x200B;](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#temporary-debug-logs)」を参照してください。

実行履歴から実行を開き、リクエストと応答パネルにデータがない場合、パネルは一時デバッグログ設定に移動します。
