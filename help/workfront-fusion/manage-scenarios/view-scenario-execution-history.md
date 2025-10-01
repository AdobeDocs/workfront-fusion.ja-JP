---
title: シナリオの実行履歴の表示
description: シナリオのイベントや実行に関する情報を表示したり、シナリオのすべての実行で特定のデータを検索したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 974b32b4-d86a-48cd-a8d4-1ae2cf309b9b
source-git-commit: c0a4e563657871f856b7d449432d563c6caa27a1
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 58%

---

# シナリオの実行履歴の表示

シナリオのイベントや実行に関する情報を表示したり、シナリオのすべての実行で特定のデータを検索したりできます。

シナリオ実行は、シナリオの 1 回の実行を表します。

シナリオイベントは、シナリオを編集、アクティブ化または非アクティブ化するなどの、シナリオに対する変更です。

>[!NOTE]
>
>シナリオの履歴には、過去 30 日間のシナリオのすべての実行が表示されます。

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## シナリオ履歴の表示


### 「履歴」タブでのシナリオ履歴の表示

「[!UICONTROL 履歴]」タブには、[!UICONTROL シナリオの詳細]ページよりも詳細な情報が表示されます。また、[!UICONTROL 履歴]タブで実行のフィルタリングや並べ替えができます。

1. 左パネルの「**[!UICONTROL シナリオ]**」タブをクリックし、シナリオをクリックします。

   または

   シナリオエディターでシナリオに取り組んでいる場合は、ウィンドウの左上隅にある左矢印 ![&#x200B; 編集を終了 &#x200B;](assets/exit-editing-arrow.png) をクリックします。

1. シナリオ名の近くにある **履歴** をクリックします。
   ![&#x200B; 「履歴」タブ &#x200B;](assets/history-tab.png)

   シナリオの実行ごとに、次の詳細が表示されます。

   * 実行が&#x200B;**[!UICONTROL 開始]**&#x200B;した日付
   * 実行 ID
   * **[!UICONTROL ステータス]**（成功または失敗）
   * 実行&#x200B;**[!UICONTROL 期間]**
   * **[!UICONTROL 操作]**&#x200B;の回数
   * **[!UICONTROL データ転送]**&#x200B;のサイズ

   >[!NOTE]
   >
   >実行の詳細がストレージに書き込まれる一方で、シナリオ履歴では、最近実行されたシナリオの横に&#x200B;**処理**&#x200B;バッジが表示されます。処理は、シナリオの実行直後に行われます。数分以上続くことはありません。シナリオ実行の処理中は、シナリオ実行の詳細が表示されない場合があります。

1. 特定のシナリオ実行の詳細を表示するには、右端の **詳細** をクリックします。 [!UICONTROL 詳細]リンクは、実行に詳細が含まれる場合にのみ表示されます。

   シナリオ実行の詳細の表示について詳しくは、[&#x200B; 特定のシナリオ実行の表示 &#x200B;](/help/workfront-fusion/manage-scenarios/view-a-specific-scenario-execution.md) を参照してください。
1. イベントを表示するには、「イベントを表示 **をオンに切り替え** す。


### 「シナリオ詳細」ページでのシナリオ履歴の表示


1. 左パネルの「**[!UICONTROL シナリオ]**」タブ、シナリオの順にクリックします。

   または

   シナリオエディターでシナリオに取り組んでいる場合は、ウィンドウの左上隅にある左矢印 ![&#x200B; 編集を終了 &#x200B;](assets/exit-editing-arrow.png) をクリックします。

1. 右側のパネルの **[!UICONTROL 履歴]** タブをクリックします。
1. （任意）選択したシナリオ実行の詳細を確認するには、右側のパネルで「実行」をクリックします。

   バンドルの処理について詳しくは、[&#x200B; シナリオ実行フロー &#x200B;](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md) を参照してください

   >[!NOTE]
   >
   >* シナリオ履歴では、最近実行したシナリオの横に&#x200B;**処理履歴**&#x200B;バッジが表示され、実行の詳細がストレージに書き込まれます。処理は、シナリオの実行直後に行われます。数分以上続くことはありません。シナリオ実行の処理中は、シナリオ実行の詳細が表示されない場合があります。

1. イベントを表示するには、「**イベント**」タブをクリックします。

## シナリオ実行履歴のフィルタリング

実行履歴をフィルターして、指定した値を持つ実行のみを表示できます。

1. この記事の[「[!UICONTROL 履歴]」タブでシナリオの実行履歴を表示](#view-scenario-history-on-the-history-tab)で説明されているように、シナリオの全ページ履歴を開きます。
1. フィルタリングの基準にする列のヘッダーにある [!UICONTROL &#x200B; フィルター &#x200B;] アイコン ![&#x200B; シナリオフィルターアイコン &#x200B;](assets/fusion-scenario-filter-icon.png) をクリックします。
1. 「[!UICONTROL フィルター]」ダイアログで、フィルタリングしたい値を入力します。
1. 「**[!UICONTROL 保存]**」をクリックします。

フィルターがアクティブな列のフィルターアイコンはオレンジ色です。

<!-- don't see how to do this
## Sort the scenario execution history

You can sort the scenario execution history.

1. Open the full-page history for a scenario as described in [View scenario execution history on the [!UICONTROL History] tab](#view-scenario-execution-history-on-the-history-tab) in this article.
1. Click the [!UICONTROL Sort] icon in the header of the column you want to filter by.
1. Optional: To reverse the order of the sort, click the [!UICONTROL Sort] icon again.
-->

## シナリオのすべての実行を検索

1. この記事の[「[!UICONTROL 履歴]」タブでシナリオの実行履歴を表示](#view-scenario-history-on-the-history-tab)で説明されているように、シナリオの全ページ履歴を開きます。
1. 実行リスト上部にある「**[!UICONTROL フルテキスト検索]**」をクリックします。

   または

   **Ctrl+Shift+F**（Windows）または **Cmd+Shift+F**（MAC）
[!UICONTROL 履歴で検索]ウィンドウが開きます。

1. (オプション）特定のテキストを含む実行を検索するには、**[!UICONTROL 履歴で検索]**&#x200B;ウィンドウの検索バーにテキストを入力します。

   正確にテキストを検索するには、テキストを二重引用符（&quot;例&quot;）で囲みます。

   >[!INFO]
   >
   >**例：**&#x200B;特定のプロジェクトを作成した実行を検索したい場合、[!UICONTROL フルテキスト検索]バーにプロジェクトIDを入力します。
   >
   >&quot;625ef2ef0006036bd1794b6e52d737c5&quot;

1. (オプション）日付範囲で検索を制限するには、[!UICONTROL 日付範囲別]エリアで検索の開始日と終了日を選択します。

   >[!NOTE]
   >
   >* 過去 30 日間のみ実行できます。
   >
   >* Workfront Fusion は、Webhook ペイロードを 30 日間保存します。 作成後 30 日を超える web フックペイロードにアクセスすると、「[!UICONTROL ストレージからファイルを読み取れませんでした。]」というエラーが発生します。


1. （オプション）検索をステータスで制限するには、**[!UICONTROL ステータス別]**&#x200B;ドロップダウンで目的のステータスを選択します。


   利用可能なステータスは、次のとおりです。

   * [!UICONTROL すべて]

   * [!UICONTROL エラー]

   * [!UICONTROL 警告]

   * [!UICONTROL 成功]

1. （オプション）**[!UICONTROL 日付順に並べ替え]**&#x200B;ドロップダウンで表示される結果の順序を変更します。

1. （オプション）シナリオ実行 ID をコピーするには、**[!UICONTROL 実行 ID をコピー]**&#x200B;アイコンをクリックします。 目的の実行の行に <img src="assets/copy-fusion-execution-id-icon.png"> ります。

1. （オプション）[!UICONTROL &#x200B; フルテキスト検索]の結果をクリックして、その情報を含むシナリオモジュール出力バンドルを調べます。
