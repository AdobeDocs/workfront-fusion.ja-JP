---
title: 不完全な実行の表示と解決
description: '[!UICONTROL Incomplete executions] フォルダーには、エラーが原因で正常に完了しなかったシナリオ実行が格納されます。 保存された未完了の実行は、手動または自動で解決できます。'
author: Becky
feature: Workfront Fusion
exl-id: 974b32b4-d86a-48cd-a8d4-1ae2cf309b9b
source-git-commit: 3d06958b6f706f4f974230853fb6553232656fd3
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 34%

---

# シナリオの実行履歴の表示

シナリオのイベントや実行に関する情報を表示したり、シナリオのすべての実行で特定のデータを検索したりできます。

シナリオ実行は、シナリオの 1 回の実行を表します。

シナリオイベントは、シナリオを編集、アクティブ化または非アクティブ化するなどの、シナリオに対する変更です。

>[!NOTE]
>
>シナリオの履歴には、過去 30 日間のシナリオのイベントと実行がすべて表示されます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の [!DNL Workfront Fusion] 管理者である必要があります。</p>
     <p>チームの [!DNL Workfront Fusion] 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## シナリオ履歴の表示


### 「履歴」タブでのシナリオ履歴の表示

「[!UICONTROL History]」タブには、「[!UICONTROL Scenario detail]」ページで使用可能な詳細情報よりも詳細に表示されます。 また、「[!UICONTROL History]」タブで、実行をフィルタリングして並べ替えることもできます。

1. 左側のパネルで「**[!UICONTROL Scenario]**」タブをクリックし、シナリオをクリックします。

   または

   シナリオエディターでシナリオを操作している場合は、ウィンドウの左上隅付近にある左向き矢印 ![](assets/exit-editing-arrow.png) をクリックします。

1. シナリオ名の近くにある **履歴** をクリックします。
   ![ 「履歴」タブ ](assets/history-tab.png)

   シナリオの実行ごとに、次の詳細が表示されます。

   * 実行が **[!UICONTROL Started]** 行された日付
   * 実行 ID
   * **[!UICONTROL Status]** （成功または失敗）
   * 実行 **[!UICONTROL Duration]**
   * **[!UICONTROL Operations]** 数
   * **[!UICONTROL Data Transfer]** のサイズ

   >[!NOTE]
   >
   >実行の詳細がストレージに書き込まれる一方で、シナリオ履歴では、最近実行されたシナリオの横に&#x200B;**処理**&#x200B;バッジが表示されます。処理は、シナリオの実行直後に行われます。数分以上続くことはありません。シナリオ実行の処理中は、シナリオ実行の詳細が表示されない場合があります。

1. 特定のシナリオ実行の詳細を表示するには、右端の **詳細** をクリックします。 [!UICONTROL details] リンクは、実行に詳細がある場合にのみ表示されます。
1. イベントを表示するには、「イベントを表示 **をオンに切り替え** す。


### 「シナリオ詳細」ページでのシナリオ履歴の表示


1. 左側のパネルで「**[!UICONTROL Scenario]**」タブをクリックし、シナリオをクリックします。

   または

   シナリオエディターでシナリオを操作している場合は、ウィンドウの左上隅付近にある左向き矢印 ![](assets/exit-editing-arrow.png) をクリックします。

1. 右側のパネルの「**[!UICONTROL History]**」タブをクリックします。
1. （任意）選択したシナリオ実行の詳細を確認するには、右側のパネルで「実行」をクリックします。

   バンドルの処理について詳しくは、[ シナリオ実行フロー ](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md) を参照してください

   >[!NOTE]
   >
   >* シナリオ履歴では、最近実行したシナリオの横に&#x200B;**処理履歴**&#x200B;バッジが表示され、実行の詳細がストレージに書き込まれます。処理は、シナリオの実行直後に行われます。数分以上続くことはありません。シナリオ実行の処理中は、シナリオ実行の詳細が表示されない場合があります。

1. イベントを表示するには、「**イベント**」タブをクリックします。

## シナリオ実行履歴のフィルタリング

実行履歴をフィルターして、指定した値を持つ実行のみを表示できます。

1. この記事の [[[!UICONTROL History]] タブのシナリオ実行履歴の表示 ](#view-scenario-history-on-the-history-tab) の説明に従って、シナリオの全ページ履歴を開きます。
1. フィルターの基準にする列のヘッダーに ![](assets/fusion-scenario-filter-icon.png) る「[!UICONTROL filter]」アイコンをクリックします。
1. [!UICONTROL filter] ダイアログで、フィルターに使用する値を入力します。
1. **[!UICONTROL Save]** をクリックします。

フィルターがアクティブな列のフィルターアイコンはオレンジ色です。

<!-- don't see how to do this
## Sort the scenario execution history

You can sort the scenario execution history.

1. Open the full-page history for a scenario as described in [View scenario execution history on the [!UICONTROL History] tab](#view-scenario-execution-history-on-the-history-tab) in this article.
1. Click the [!UICONTROL Sort] icon in the header of the column you want to filter by.
1. Optional: To reverse the order of the sort, click the [!UICONTROL Sort] icon again.
-->

## シナリオのすべての実行を検索

1. この記事の [[[!UICONTROL History]] タブのシナリオ実行履歴の表示 ](#view-scenario-history-on-the-history-tab) の説明に従って、シナリオの全ページ履歴を開きます。
1. 実行リストの上部にある「**[!UICONTROL Fulltext search]**」をクリックします。

   または

   **Ctrl + Shift + F** （Windows）または **Cmd + Shift + F** （Mac）と入力します
[!UICONTROL Search in history] ウィンドウが開きます。

1. （オプション）特定のテキストを含む実行を検索するには、検索ウィンドウの検索バーにテキス **[!UICONTROL Search in history]** を入力します。

   正確にテキストを検索するには、テキストを二重引用符（&quot;例&quot;）で囲みます。

   >[!INFO]
   >
   >**例：** 特定のプロジェクトを作成した実行を検索する場合は、[!UICONTROL Fulltext search] のバーにプロジェクト ID を入力します。
   >
   >&quot;625ef2ef0006036bd1794b6e52d737c5&quot;

1. （オプション）日付範囲で検索を制限するには、検索の開始日と終了日を [!UICONTROL By date range] の領域で選択します。

   >[!NOTE]
   >
   >* 過去 30 日間のみ実行できます。
   >
   >* [!DNL Workfront Fusion] は、30 日間、ebhook ペイロードを保存します。Webhook ペイロードが作成されてから 30 日以上アクセスすると、「[!UICONTROL Failed to read file from storage.]」というエラーが発生する


1. （オプション）ステータスで検索を制限するには、**[!UICONTROL By status]** ールドロップダウンで目的のステータスを選択します。


   利用可能なステータスは、次のとおりです。

   * [!UICONTROL All]

   * [!UICONTROL Error]

   * [!UICONTROL Warning]

   * [!UICONTROL Success]

1. （オプション） **[!UICONTROL Sort by dates]** ドロップダウンに表示する結果の順序を変更します。

1. （任意）シナリオ実行 ID をコピーするには、「**[!UICONTROL Copy execution ID]**」アイコンをクリックします 目的の実行の行に <img src="assets/copy-fusion-execution-id-icon.png"> ります。

1. （任意） [!UICONTROL Fulltext search] の結果をクリックして、情報を含むシナリオモジュール出力バンドルを調べます。
