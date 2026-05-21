---
title: 特定のシナリオの実行の表示
description: シナリオイベントのフィルタリングや検索など、特定のシナリオ実行の詳細を表示できます。
author: Becky
feature: Workfront Fusion
exl-id: 34dd9836-9a1b-4ce2-b24e-ae769888a52a
TQID: https://experienceleague.adobe.com/Msh3ArxBUIu6YDZjL7eXpxlEBiYABHN-Q7xUlJ-qU0g
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 422
ht-degree: 26%

---

# 特定のシナリオの実行の表示

シナリオイベントのフィルタリングや検索など、特定のシナリオ実行の詳細を表示できます。

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

## 特定の実行の表示

シナリオのシナリオ履歴から実行を表示できます。


1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックし、シナリオをクリックします。

   または

   シナリオエディターでシナリオを操作している場合は、ウィンドウの左上隅付近にある左矢印![編集矢印を終了](assets/exit-editing-arrow.png)をクリックします。

1. シナリオの名前の近くにある&#x200B;**履歴**をクリックします。
   ![履歴タブ ](assets/history-tab.png)


1. 表示する実行を見つけ、その実行の行の右端にある&#x200B;**詳細**&#x200B;をクリックします。 [!UICONTROL 詳細]リンクは、実行に詳細が含まれる場合にのみ表示されます。

   シナリオダイアグラムが開き、右側の実行詳細パネルが開きます。

   この実行用に出力を生成したモジュールには、緑色のタイトルが付けられます。

   実行されなかったモジュールはグレー表示になります。

1. モジュールの出力を表示するには、モジュールの近くにある出力の詳細バブルをクリックします。 バブル内の数値は、モジュールが出力するバンドルの数を表します。

   ![ モジュール付近のバブルを出力](assets/output-bubble.png)

1. フィルターを通過したバンドルを表示するには、フィルターをクリックします。 フィルターの近くにある数値は、フィルターを通過したバンドルの数を表します。
1. 実行パネルで特定のモジュールまたはイベントを検索するには、**実行イベントを検索** ボックスに検索語を入力します。 入力時に結果が表示されます。
1. 成功や警告などのステータスで実行パネルの検索結果を制限するには、「**ステータスフィルター**」ドロップダウンをクリックし、ステータスを選択します。




>[!NOTE]
>
>特定のモジュールへのリンクを作成するには、次のページを表示するときにURLに`?moduleId=<module-id>`を追加します。
>
>* シナリオ編集ページ （URLの末尾は`/edit`）
>* 特定のシナリオの実行（URLの末尾は`/logs/<log-id>`）
>
>`<module-id>`は、シナリオを表示する際に、モジュールラベルの横にある番号を参照します。
>
>これは、シナリオのデバッグやモジュール設定のコピーに役立ちます。
