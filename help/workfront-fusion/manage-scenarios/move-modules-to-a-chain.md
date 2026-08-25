---
title: チェーンへのモジュールの移動
description: シナリオ内のモジュールのグループを選択し、マッピングやデータ構造を手動で再作成することなく、新しいチェーン化されたシナリオに移動できます。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: f1a80f64edc410ae76bfbba1280df7232e2d09c5
workflow-type: tm+mt
source-wordcount: 513
ht-degree: 17%

---

# チェーンへのモジュールの移動

>[!IMPORTANT]
>
>この機能はBetaにあり、ミッションクリティカルな実稼動ワークフローには推奨されません。 Betaの機能では、動作が変更され、エッジケースが完全に処理されない場合があります。

シナリオ内のモジュールのグループを選択し、マッピングやデータ構造を手動で再作成することなく、新しいチェーン化されたシナリオに移動できます。 これにより、大規模なシナリオを簡単にモジュール化できます。

Workfront Fusionは、モジュールグループをチェーンに移動し、次のような機能を提供します。

* 選択したモジュールを新しく作成したシナリオに移動します。
* 別のブラウザーウィンドウで新しいシナリオを開きます。
* 元のシナリオで選択したモジュールを、チェーン/子シナリオモジュールを呼び出しに置き換えます。
* 新しい子シナリオに必要な入出力データ構造を自動的に作成します。
* 既存のシナリオの動作を維持するので、モジュールを移動する前と同じようにシナリオを実行し続けます。
* マッピングを自動的に更新：
  * 子シナリオに移動されたモジュールは、チェーン/親モジュールの入力からデータを受信を通じてデータを受信します。
  * 子シナリオからの出力は、親シナリオに自動的に公開されます。
  * ブループリントの既存のマッピングは、新しい構造に合わせて調整されます。

連鎖シナリオの計画について詳しくは、[複数のシナリオを連鎖させる](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)を参照してください。

チェーンモジュールの設定方法については、[ チェーンモジュール ](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md)を参照してください。

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

チェーンに移動するモジュールは、シナリオ内に既に存在する必要があり、複数のモジュールを選択する必要があります。

## 制限事項

次の状況では、選択したモジュールをチェーンに移動することはできません。

* 選択したモジュールは、単一の連続したフローの一部ではありません。 例えば、2つの異なる未接続ルートから同時にモジュールを選択することはできません。
* 選択範囲には、Webhook モジュールが含まれます。
* 選択には、別のチェーンモジュールが含まれます。
* 選択にはルーターモジュールが含まれており、そのルーターのルートをすべて選択しているわけではありません。
* 選択したモジュールにはエラーハンドラーのルートがあり、そのルートも選択していません。

## モジュールのチェーンへの移動

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 移動するモジュールを含むシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. [!UICONTROL Shift]を押しながら、移動するモジュールをクリックして、チェーンに移動するモジュールを選択します。
1. 選択したモジュールのいずれかを右クリックします。
1. 「**[!UICONTROL チェーンに移動]**」を選択します。
