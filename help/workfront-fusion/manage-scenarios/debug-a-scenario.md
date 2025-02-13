---
title: シナリオのデバッグ
description: Adobe Workfront Fusion 開発ツールを使用すると、シナリオを理解し、トラブルシューティングできます。開発ツールは、Chrome デベロッパーツールにさらにパネルを追加します。このデバッガーパネルを使用すると、シナリオのすべての手動実行を確認し、実行されたすべての操作を確認し、実行されたすべての API 呼び出しの詳細を表示できます。エラーが発生したモジュール、操作または単一の応答を確認し、その知識を使用してシナリオを改良できます。
author: Becky
feature: Workfront Fusion
exl-id: 34215370-27e3-4c28-8bd1-a16268900b86
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 74%

---

# シナリオのデバッグ

[!DNL Adobe Workfront Fusion] 開発ツールは、シナリオの理解とトラブルシューティングに役立ちます。 開発ツールを使用すると、シナリオのすべての手動実行を確認し、実行されたすべての操作を確認し、実行されたすべての API 呼び出しの詳細を確認できます。 エラーが発生したモジュール、操作または単一の応答を確認し、その知識を使用してシナリオを改良できます。

>[!NOTE]
>
>デバッガーパネルへのログインは、機密シナリオ、自動実行、正常な操作に対して制限されるか、利用できなくなります。

Fusion 開発ツールの概要ビデオとチュートリアルについては、

* [Fusion 開発ツール](https://video.tv.adobe.com/v/3427031/){target=_blank}
* [開発ツールのチュートリアル](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/fusion/troubleshooting-and-error-handling/dev-tool-walkthrough.html?lang=ja)

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

## 開発ツールへのアクセス

Adobe統合シェルで Fusion を使用している場合、または新しい Fusion エクスペリエンスに更新した場合は、シナリオエディターから開発ツールにアクセスできます。

1. 画面下部の **ヘルパーツール**![ ヘルパーツール ](assets/debugger-icon.png) アイコンをクリックします。

または：

1. デバッグするシナリオのシナリオエディターに移動します。

   シナリオエディターを見つけるには、[ シナリオエディター ](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md) を参照してください。

1. ページの何もないエリア（モジュール上以外）を右クリックします。
1. 「**開発者ツールを開く**」を選択します。

## [!DNL Workfront Fusion] 開発ツールの使用

Workfront Fusion 開発ツールは、3 つの主なセクションに分かれています。これらは、開発ツールウィンドウの左パネルにあります。

* [ライブストリーム](#live-stream)
* [シナリオデバッガー](#scenario-debugger)
* [ツール](#tools)

### ライブストリーム

ライブストリームは、シナリオで「1 回実行」をクリックすると、バックグラウンドで発生していることを表示します。

1. **[!UICONTROL Live Stream]** アイコン ![ ライブストリームアイコン ](assets/live-stream-icon.png) をクリックして、「ライブストリーム」セクションを開きます。
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
       </ul> <p>この情報を表示するには、[!DNL Workfront Fusion] 開発ツールの右パネルにある適切なタブをクリックします。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>コンテンツでイベントを検索</p> </td> 
      <td> <p>[!DNL Workfront Fusion] 開発ツールの左パネルにある検索フィールドに検索語を入力すると、その検索語を含むリクエストのみが表示されます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>リクエストのリストをクリア </p> </td> 
      <td> <p>開発ツールの左パネルの右上隅にあるごみ箱アイコンをクリックして、[!DNL Workfront Fusion] 開発ツールで記録されたリクエストのリストをクリアします。 </p> </td> 
     </tr> 
     <!--<tr> 
      <td role="rowheader"> <p>Enable Console Logging</p> </td> 
      <td> <p>Click the computer icon <img src="assets/console-computer-icon.png"> in the top-right corner of the Devtool's left panel.</p> <p>Logging in the console is enabled when the computer icon is green.</p> </td> 
     </tr>-->
     <tr> 
      <td role="rowheader"> <p>Raw JSON 形式または cURL でリクエストを取得</p> </td> 
      <td> 
       <ul> 
        <li> <p><strong>Raw JSON</strong> </p> <p>開発ツールの右側のパネルの右上隅にある「<strong>[!UICONTROL Copy RAW]</strong>」をクリックします。</p> </li> 
        <li> <p><strong>cURL</strong> </p> <p>開発ツールの右側のパネルの右上隅にある「<strong>[!UICONTROL Copy cURL]</strong>」をクリックします。</p> </li> 
       </ul> </td> 
     </tr> 
    </tbody> 
   </table>

### シナリオデバッガー

シナリオデバッガーは、より複雑なシナリオで役に立ちます。シナリオ実行の履歴が表示され、名前または ID でモジュールを検索できます。

1. **[!UICONTROL Scenario Debugger]** アイコン ![ デバッガーアイコン ](assets/scenario-debugger-icon.png) をクリックして、シナリオデバッガーを開きます。
1. （オプション）検索フィールドに検索語句（名前またはモジュール ID）を入力します。
1. モジュール名をクリックします。
1. 操作をクリックすると、リクエストの詳細が表示されます。

### ツール

[!DNL Workfront Fusion] 開発ツールには、シナリオを設定しやすくするツールが備わっています。

1. **[!UICONTROL Tools]** アイコン ![ コンソールツールアイコン ](assets/console-tools-icon.png) をクリックして、ツールを開きます。
1. 使用するツールを選択します。
1. 下記のフィールドを設定します。
1. **[!UICONTROL Run]** をクリックします。

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

#### [!UICONTROL Focus a Module]

ID で指定したモジュールの設定が開きます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Module ID]</td>
        <td>モジュールの ID を入力して、設定を開きます。</td>
    </tr>
</table>

#### [!UICONTROL Find Modules by Mapping]

指定した語句に対応するモジュールの値を検索できます。出力には、検索した語句を含んだモジュールの ID が含まれています。

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

#### [!UICONTROL Get App Metadata]

アプリのモジュール名または ID でアプリのメタデータを取得します。これは、例えば、シナリオで使用されるアプリのバージョンを知る必要がある場合に便利です。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>メタデータを取得するモジュールを選択します。</td>
    </tr>
</table>

#### [!UICONTROL Copy Mapping]

ソースモジュールからターゲットモジュールに値をコピーします。

>[!CAUTION]
>
>正しいソースモジュールとターゲットモジュールを設定していることを確認します。別のタイプのモジュールを選択すると、ターゲットモジュール内の値は削除されます。

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

#### [!UICONTROL Copy Filter]

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
   <td> <p>ソースフィルターは、フォールバックルートとして設定されます。ターゲットフィルターがフォールバックルートとして設定されるように指定するには、このオプションを有効にします。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Copy Module Name]

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

#### [!UICONTROL Swap Connection]

同じアプリのシナリオ内のすべてのモジュールに、ソースモジュールの接続を複製します。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>接続の複製元となるモジュールを選択するか、そのモジュールの ID を入力します。</td>
    </tr>
</table>

#### [!UICONTROL Swap Variable]

指定された変数をシナリオ内で検索し、新しい変数に置き換えます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable to Find]</td> 
   <td> <p> シナリオ内の変数モジュールから、置き換える変数ピルを見つけて、この（[!UICONTROL Variable to Find]）フィールドにコピーします。 フィールドには二重波括弧で囲まれて表示されます。例：<code>&#123;&#123;5.value&#125;&#125;</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace With]</p> </td> 
   <td> <p>シナリオの変数モジュールで、変数を置き換える変数ピルを見つけて、この（[!UICONTROL Variable to Find]）フィールドにコピーします。 フィールドには二重波括弧で囲まれて表示されます。例：<code>&#123;&#123;5.value&#125;&#125;</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module]</p> </td> 
   <td> <p>変数を置換する変数モジュールを選択します。 モジュールが選択されていない場合、変数はシナリオ全体で置き換えられます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Base 64]

入力したデータを Base64 にエンコードまたは Base64 からデコードできます。一部のリクエストは Base64 にエンコードされています。このツールは、エンコードされたリクエスト内の特定のデータを検索する場合に役立ちます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation] </td> 
   <td> <p>[!UICONTROL Raw Data] フィールドのデータを Base64 にエンコードするか、Base64 を Raw データにデコードするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Raw Data]</p> </td> 
   <td> <p> Base64 にエンコードするデータを入力するか、Raw データにデコードする場合は、上記の [!UICONTROL Operation] フィールドで選択したオプションに応じて Base64 を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remap Source]

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
