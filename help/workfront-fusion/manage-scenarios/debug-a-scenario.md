---
title: シナリオのデバッグ
description: Adobe Workfront Fusion 開発ツールを使用すると、シナリオを理解し、トラブルシューティングできます。 開発ツールは、Chrome デベロッパーツールにさらにパネルを追加します。 このデバッガーパネルを使用すると、シナリオのすべての手動実行を確認し、実行されたすべての操作を確認し、実行されたすべての API 呼び出しの詳細を表示できます。 エラーが発生したモジュール、操作または単一の応答を確認し、その知識を使用してシナリオを改良できます。
author: Becky
feature: Workfront Fusion
exl-id: 34215370-27e3-4c28-8bd1-a16268900b86
TQID: 'https://experienceleague.adobe.com/7NXYVXxbQvgKnqvRUNV-ySBApe9kl-Kn57sSKCh4NLE'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '1962'
ht-degree: 58%
---
# シナリオのデバッグ

Adobe Workfront Fusion開発ツールは、シナリオの理解とトラブルシューティングに役立ちます。 開発ツールを使用すると、シナリオのすべての手動実行を確認し、実行されたすべての操作を確認し、実行されたすべてのAPI呼び出しの詳細を確認できます。 エラーが発生したモジュール、操作または単一の応答を確認し、その知識を使用してシナリオを改良できます。

>[!NOTE]
>
>デバッガーパネルへのログインは、機密シナリオ、自動実行、正常な操作に対して制限されるか、利用できなくなります。

>[!NOTE]
>
>新しいエクスペリエンスでは、いくつかの開発ツール ツールがシナリオエディターに組み込まれているため、開発ツールを開かずに使用できます。
>
>| ツール | 新しいエクスペリエンスのどこにあるか |
>| ---------- | ---------- |
>| アプリのメタデータを取得 | モジュールを右クリックし、**アプリメタデータ**&#x200B;を選択します。 |
>| マッピングをコピー | ソースモジュールを右クリックし、**マッピングをコピー**&#x200B;を選択してから、互換性のあるモジュールに貼り付けます。 |
>| フィルターをコピー | フィルターされたリンクを右クリックし、**フィルターをコピー**&#x200B;を選択してから、別のリンクに貼り付けます。 |
>| モジュール名をコピー | モジュールを右クリックし、**モジュール名をコピー**&#x200B;または&#x200B;**モジュール名を貼り付け**&#x200B;を選択します。 |
>| スワップ接続 | 検索と置換を開き、「**接続**」タブを使用します。 |
>| スワップ変数 | 検索と置換を開き、「**変数**」タブを使用します。 |
>| リマップソース | 検索と置換を開き、「**Source**」タブを使用します。 |
>
>これらのツールは、DevToolの「**ツール**」タブでも、モジュールのフォーカス、マッピングによるモジュールの検索、Base 64で引き続き利用できます。 マッピングで`base64()`関数とバイナリ変換関数を使用することもできます。
>
>また、シナリオエディターで[Live Trail](/help/workfront-fusion/manage-scenarios/live-trail.md)と実行履歴からリクエストと応答の詳細を直接表示することもできます。 検索と置換について詳しくは、[&#x200B; シナリオ内の変数、ソース、接続の検索と置換](/help/workfront-fusion/manage-scenarios/find-and-replace.md)を参照してください。
<!-- BECKY CHECK ME: DevTool screenshots (10/27/26) show all ten tools still on the Tools tab, so this note now says the seven built-in tools are available in both places. The release notes implied only Focus a module, Find modules by mapping, and Base 64 would remain. Confirm after release whether the other seven are removed from the DevTool, and update this note and the Tools section if so.  -->
<!-- BECKY CHECK ME: note added from the 10/23/26 release notes; the DevTool is NOT being removed. This article still needs a fuller restructure (new/classic split for the seven tools, Live Trail section or separate article). Confirm the menu labels. -->

Fusion 開発ツールの概要ビデオとチュートリアルについては、

* [Fusion開発ツール](https://video.tv.adobe.com/v/3427031/){target=_blank}
* [開発ツールのチュートリアル](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/fusion/troubleshooting-and-error-handling/dev-tool-walkthrough.html?lang=ja)

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

## 開発ツールへのアクセス

Adobe統合シェルでFusionを使用する場合、または新しいFusion エクスペリエンスに更新した場合は、シナリオエディターから開発ツールにアクセスできます。

### 新しいエクスペリエンスでの開発ツールへのアクセス

1. デバッグするシナリオのシナリオエディターに移動します。

   シナリオエディターを見つけるには、[&#x200B; シナリオエディター](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md)を参照してください。

1. コントロール領域の3点アイコンをクリックし、**開発ツール**&#x200B;を選択します。

または

1. デバッグするシナリオのシナリオエディターに移動します。
1. ページの空の領域（モジュールではなく）を右クリックします。
1. 「**開発者ツールを開く**」を選択します。

開発ツールがカンバスの下のパネルで開きます。

<!-- BECKY CHECK ME: new-experience access steps from your 10/27/26 notes (three-dot menu in Controls, or right-click). Confirm the menu label ('DevTool') and the 'panel below the canvas' description, and add a screenshot. I assumed the Helper tools icon steps below apply to the classic experience only; confirm. -->

### クラシックエクスペリエンスの開発ツールへのアクセス

1. 画面の下部にある「**ヘルパーツール** ![&#x200B; ヘルパーツール &#x200B;](assets/debugger-icon.png)」アイコンをクリックします。

または

1. デバッグするシナリオのシナリオエディターに移動します。

   シナリオエディターを見つけるには、[&#x200B; シナリオエディター](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md)を参照してください。

1. ページの何もないエリア（モジュール上以外）を右クリックします。
1. 「**開発者ツールを開く**」を選択します。

## Workfront Fusion開発ツールの使用

Workfront Fusion Devtoolは、3つの主要セクションとヘルプリンクに分かれています。 これらは、開発ツールウィンドウの左パネルにあります。

* [ライブストリーム](#live-stream)
* [シナリオデバッガー](#scenario-debugger)
* [ツール](#tools)
* **開発ツールのヘルプ**：疑問符アイコンをクリックして、開発ツールに関する記事を開きます。

<!-- BECKY CHECK ME: the DevTool left panel now has a fourth item, 'DevTool help' (question mark icon), per your 10/27/26 screenshots. Confirm the label, that it opens this article or another one, and whether to apply this to the classic experience too. Retake the left-panel screenshot. -->

### ライブストリーム

ライブストリームは、シナリオで「1 回実行」をクリックすると、バックグラウンドで発生していることを表示します。

<!-- BECKY CHECK ME: HOLD: in the new experience, Live Stream shows a 'no events available' message even while a scenario is running, which may be a bug. No updates have been made to this section. Re-test after release before changing anything here. If it is intended behavior, this section may need to point to Live Trail instead. -->

1. **[!UICONTROL ライブストリーム]** アイコン ![&#x200B; ライブストリームアイコン &#x200B;](assets/live-stream-icon.png)をクリックして、「ライブストリーム」セクションを開きます。
1. 次のいずれかの操作を行います。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>アクション</th> 
      <th>手順</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td role="rowheader">リクエスト情報の表示</td> 
      <td> <p>シナリオの各モジュールに関して、次の情報を表示できます。</p> 
       <ul> 
        <li> <p>リクエストヘッダー（API エンドポイント URL、http メソッド、リクエストが呼び出された日時、リクエストヘッダー、クエリ文字列）</p> </li> 
        <li> <p>リクエスト本文</p> </li> 
        <li> <p>応答ヘッダー</p> </li> 
        <li> <p>応答本文</p> </li> 
       </ul> <p>この情報を表示するには、Workfront Fusion開発ツールの右側のパネルにある適切なタブをクリックします。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>コンテンツによるイベントの検索</p> </td> 
      <td> <p>Workfront Fusion開発ツールの左側のパネルの検索フィールドに検索語を入力すると、検索語を含むリクエストのみが表示されます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>リクエストのリストをクリア </p> </td> 
      <td> <p>開発ツールの左パネルの右上隅にあるゴミ箱アイコンをクリックして、Workfront Fusion開発ツールで記録されたリクエストのリストをクリアします。 </p> </td> 
     </tr> 
     <!--
     <tr>
      <td role="rowheader"> <p>Enable Console Logging</p> </td> 
      <td> <p>Click the computer icon <img src="assets/console-computer-icon.png"> in the top-right corner of the Devtool's left panel.</p> <p>Logging in the console is enabled when the computer icon is green.</p> </td> 
     </tr>
     -->
     <tr> 
      <td role="rowheader"> <p>Raw JSON 形式または cURL でリクエストを取得</p> </td> 
      <td> 
       <ul> 
        <li> <p><strong>Raw JSON</strong> </p> <p>開発ツールの右パネルの右上隅にある <strong>[!UICONTROL Copy RAW]</strong> をクリックします。</p> </li> 
        <li> <p><strong>cURL</strong> </p> <p>開発ツールの右パネルの右上隅にある <strong>[!UICONTROL Copy cURL]</strong> をクリックします。</p> </li> 
       </ul> </td> 
     </tr> 
    </tbody> 
   </table>

### シナリオデバッガー

>[!NOTE]
>
>エラーが発生したシナリオからデバッガーにすばやく移動するには、モジュール出力のエラーメッセージで「**詳細を取得**」をクリックします。
>
>![&#x200B; モジュール出力の詳細を取得](assets/go-to-debugger.png)

シナリオデバッガーは、より複雑なシナリオで役に立ちます。 シナリオ実行の履歴が表示され、名前または ID でモジュールを検索できます。

1. **[!UICONTROL Scenario Debugger]** アイコン ![Debugger アイコン &#x200B;](assets/scenario-debugger-icon.png)をクリックして、Scenario Debuggerを開きます。

   シナリオデバッガーには、シナリオ内のモジュールが一覧表示されます。 各モジュールには、名前、アプリとアクション、モジュール IDを含む番号付きバッジが表示されます。

1. （オプション）「**名前またはIDでモジュールを検索」フィールドに検索語（名前またはモジュール ID）を入力します。**
1. モジュール名をクリックします。

   モジュールの最新の実行のサイクルは、モジュールリストの横に表示されます。 モジュールに実行データがない場合、シナリオデバッガーに&#x200B;**結果が見つかりません**&#x200B;と表示されます。

1. サイクルを展開し、操作をクリックします。

   各操作は、成功したかどうか、およびそれにかかる時間（例：**操作1**、所要時間0 ミリ秒）を示します。

1. リクエストの詳細を確認します。 タブを使用して以下を表示：

   * **リクエストヘッダー**: API エンドポイント URL、HTTP メソッド、リクエストの呼び出し時、リクエストヘッダー。
   * **リクエスト本文**
   * **応答ヘッダー**
   * **応答本文**

1. （オプション）リクエストをコピーするには、**Copy RAW**&#x200B;または&#x200B;**Copy cURL**&#x200B;をクリックします。

<!-- BECKY CHECK ME: Scenario Debugger steps expanded from your 10/27/26 new-experience DevTool screenshots. Confirm: (1) the 'Search modules by Name or ID' label; (2) that the module list sub-labels, badge (module ID), cycle/operation layout, and 'No Result found' state are described correctly; (3) the tab names, since Response Body was partly hidden behind the Copy buttons in the screenshot; (4) whether Copy RAW and Copy cURL copy the request only or the request and response; (5) whether the classic experience's Scenario Debugger looks the same, or this needs a new/classic split. The screenshot also shows a collapsed 'Live trail' tab with an event count on the right edge of the editor; see the Live Trail article. Retake the Scenario Debugger screenshots. -->

### ツール

Workfront Fusionの開発ツールは、容易にシナリオを設定できます。

1. **[!UICONTROL ツール]** アイコン ![&#x200B; コンソールツールアイコン &#x200B;](assets/console-tools-icon.png)をクリックして、ツールを開きます。
1. （オプション）ツールを見つけるには、**ツール名で検索** フィールドにそのツール名を入力します。
1. 使用するツールを選択します。
1. 下記のフィールドを設定します。
1. 「**[!UICONTROL 実行]**」をクリックします。

ツールを選択するまで、パネルの右側でツールを選択するよう求められます。 「ツール」タブの下部にあるリンクをクリックすると、開発ツールに関する記事に移動します。

<!-- BECKY CHECK ME: added from your 10/27/26 screenshots: the 'Search tool by name' field, the select-a-tool prompt, and the link to the DevTool article. Confirm the field label and link destination; retake the Tools screenshot. -->

ツールとそのフィールド：

* [モジュールのフォーカス](#focus-a-module)
* [マッピングによるモジュールの検索](#find-modules-by-mapping)
* [アプリのメタデータの取得](#get-app-metadata)
* [マッピングのコピー](#copy-mapping)
* [フィルターのコピー](#copy-filter)
* [モジュール名をコピー](#copy-module-name)
* [接続の交換](#swap-connection)
* [変数の交換](#swap-variable)
* [Base 64](#base-64)
* [ソースを再マッピング](#remap-source)

#### [!UICONTROL モジュールのフォーカス]

ID で指定したモジュールの設定が開きます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Module ID]</td>
        <td>モジュールのIDを入力して、設定を開きます。</td>
    </tr>
</table>

#### [!UICONTROL マッピングによるモジュールの検索]

指定した語句に対応するモジュールの値を検索できます。 出力には、検索した語句を含んだモジュールの ID が含まれています。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword]</td> 
   <td> <p> 検索する語句を入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Use Only Values]</p> </td> 
   <td> <p>モジュールフィールドの値のみを検索する場合は、このオプションを有効にします。</p> <p>モジュールフィールドの名前も検索する場合は、このオプションを無効にします。</p> <p>検索は、name および label パラメーターを使用して実行されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アプリのメタデータの取得]

アプリのモジュール名または ID でアプリのメタデータを取得します。 これは、例えば、シナリオで使用されるアプリのバージョンを知る必要がある場合に便利です。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>メタデータを取得するモジュールを選択します。</td>
    </tr>
</table>

#### [!UICONTROL マッピングのコピー]

ソースモジュールからターゲットモジュールに値をコピーします。

>[!CAUTION]
>
>正しいソースモジュールとターゲットモジュールを設定していることを確認します。 別のタイプのモジュールを選択すると、ターゲットモジュール内の値は削除されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> フィールド値のコピー元となるモジュールを選択するか、そのモジュールの ID を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>ソースモジュール値の挿入先となるモジュールを選択するか、そのモジュールの ID を入力します。</p> <p>重要：ターゲットモジュール内の値は上書きされます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フィルターのコピー]

ソースモジュールからターゲットモジュールにフィルター設定をコピーします。

>[!NOTE]
>
>コピー操作は、選択したモジュールの左側に配置されたフィルターに対して実行されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> フィルター値のコピー元となるモジュールを選択するか、そのモジュールの ID を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>ソースモジュールのフィルター値の挿入先となるモジュールを選択するか、そのモジュールの ID を入力します。</p> <p>重要：ターゲットモジュール内の値は上書きされます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Preserve Fallback Route setting]</p> </td> 
   <td> <p>ソースフィルターは、フォールバックルートとして設定されます。 ターゲットフィルターがフォールバックルートとして設定されるように指定するには、このオプションを有効にします。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL モジュール名をコピー]

選択したモジュールの名前をクリップボードにコピーします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Module] </td> 
   <td> <p>名前をコピーするモジュールを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 接続の交換]

同じアプリのシナリオ内のすべてのモジュールに、ソースモジュールの接続を複製します。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>接続の複製元となるモジュールを選択するか、そのモジュールの ID を入力します。</td>
    </tr>
</table>

#### [!UICONTROL 変数の交換]

指定された変数をシナリオ内で検索し、新しい変数に置き換えます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable to Find]</td> 
   <td> <p> シナリオの変数モジュールから置換する変数ピルを見つけ、この（[!UICONTROL 変数を検索]）フィールドにコピーします。 フィールドには二重波括弧で囲まれて表示されます。 例：<code>&#123;&#123;5.value&#125;&#125;</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace With]</p> </td> 
   <td> <p>シナリオの変数モジュールから変数を置き換える変数ピルを見つけ、この（[!UICONTROL Variable to Find]） フィールドにコピーします。 フィールドには二重波括弧で囲まれて表示されます。 例：<code>&#123;&#123;5.value&#125;&#125;</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module]</p> </td> 
   <td> <p>変数を置き換える変数モジュールを選択します。 モジュールが選択されていない場合、変数はシナリオ全体で置き換えられます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Base 64]

入力したデータを Base64 にエンコードまたは Base64 からデコードできます。 一部のリクエストは Base64 にエンコードされています。 このツールは、エンコードされたリクエスト内の特定のデータを検索する場合に役立ちます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation] </td> 
   <td> <p>[!UICONTROL Raw Data] フィールドのデータを Base64 にエンコードするか、Base64 を生データにデコードするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Raw Data]</p> </td> 
   <td> <p> 上記の [!UICONTROL Operation] フィールドで選択したオプションに応じて、Base64 にエンコードするデータ、または生データにデコードする Base64 を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ソースを再マッピング]

マッピングソースをあるモジュールから別のモジュールへ変更できるようになります。

最初に、シナリオでルートへのソースモジュールとして使用するモジュールを追加する必要があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module] </td> 
   <td> <p> シナリオ内の他のモジュールのマッピングソースとして置き換えるモジュールを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>新しいマッピングソースとして使用するモジュールを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module to Edit]</p> </td> 
   <td> <p>シナリオ全体でマッピングを変更しない場合は、マッピングを変更するモジュールを選択します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
