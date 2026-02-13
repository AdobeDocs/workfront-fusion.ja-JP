---
title: Slack モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Slack を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 4c14fa36-8333-40d6-bd0a-fc6b0d9f4410
source-git-commit: 88147d0305595e1d0d388f510ed43fc5beaa4b64
workflow-type: tm+mt
source-wordcount: '4581'
ht-degree: 38%

---

# [!DNL Slack] モジュール

>[!IMPORTANT]
>
>この記事では、2025 年 11 月 17 日（PT）にリリースされた新しいSlack コネクタで使用できるモジュールについて説明します。
>
>従来のSlack コネクタについては、[[!DNL Slack] modules （Legacy） ](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/slack-modules.md) を参照してください。

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Slack] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成手順について詳しくは、[シナリオの作成：記事のインデックス](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

モジュールについて詳しくは、[モジュール：記事インデックス](/help/workfront-fusion/references/modules/modules-toc.md)の記事を参照してください。

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
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

* [!DNL Slack] モジュールを使用するには、[!DNL Slack] アカウントが必要です。
* OAuth@接続を作成する場合は、次の URL を組織の許可リストに追加する必要があります。
   * ボットトークン：`https://oauth.app.workfrontfusion.com/oauth/cb/slack3`
   * ユーザートークン：` https://oauth.app.workfrontfusion.com/oauth/cb/slack2`

## Slack API の情報

Slack コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>{{ifempty （parameters.domain, 'https://slack.com/api/'） }}</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v4.0.15</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Slack] モジュールとそのフィールド

[!DNL Slack] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Slack]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [メッセージ](#messages)
* [ファイル](#files)
* [チャネル](#channels)
* [反応](#reactions)
* [スター](#stars)
* [保存済みの項目](#saved-items)
* [ピン留め](#pins)
* [ユーザー](#users)
* [リマインダー](#reminders)
* [イベント](#events)
* [プロファイル](#profile)
* [その他](#other)

### メッセージ

+++ **[!UICONTROL メッセージを作成]**

このアクションモジュールは、新しいメッセージを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>メッセージを作成するチャネルの選択方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>「<strong>[!UICONTROL Channel ID or name]</strong>」フィールドに、メッセージを投稿するチャネル ID またはチャネルの名前を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>チャネルのタイプを選択し、チャネルを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>作成するメッセージのテキストコンテンツを入力します。</p> <p>メモ：テキストの書式設定について詳しくは、[!DNL Slack] ドキュメント内の<a href="https://api.slack.com/reference/surfaces/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blocks]</td> 
   <td>ブロックは、メッセージをカスタマイズおよび整理するために使用できる再利用可能なコンポーネントです。ブロックについて詳しくは、[!DNL Slack] ドキュメント内の <a href="https://api.slack.com/block-kit">Block Kit</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スレッド メッセージ ID （タイムスタンプ） ]</td> 
   <td>新しいメッセージが返信の場合は、返信するメッセージのタイムスタンプを入力します。 既に返信になっているメッセージのタイムスタンプを入力しないでください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reply broadcast]</td> 
   <td> <p>次の両方に該当する場合、<strong>[!UICONTROL Yes]</strong> を選択します。</p> 
    <ul> 
     <li> <p>新しいメッセージは別のメッセージへの返信</p> </li> 
     <li> <p>新しいメッセージをチャネル内の全員に表示する</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Link names]</p> </td> 
   <td> <p>このオプションを有効にすると、名前とチャネルで <code>@username</code> または <code>#channel</code> 書式を使用できるようになります。 </p> <p>詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse message text]</p> </td> 
   <td> <p>このオプションを有効にすると、自動解析を行うことができるようになります。 </p> <p>詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> <p>メモ：元のメッセージで [!UICONTROL Link names] オプションまたは [!UICONTROL Parse message text] オプションを使用した場合は、[!UICONTROL Update a Message] モジュールの実行時にもオプションを指定する必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Use markdown]</p> </td> 
   <td> <p>このオプションを有効にすると、[!DNL Slack] がテキスト内でマークダウンを使用できるようになります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Unfurl primarily text-based content]</p> </td> 
   <td> <p>このオプションを有効にすると、主にテキストベースのコンテンツを展開できるようになります。 </p> <p>[!DNL Slack] での展開について詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/reference/messaging/link-unfurling">メッセージ内のリンクを展開</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Unfurl media content]</p> </td> 
   <td> <p>このオプションを有効にすると、メディアコンテンツを展開できるようになります。 </p> <p>[!DNL Slack] での展開について詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/reference/messaging/link-unfurling">メッセージ内のリンクを展開</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL メッセージを削除]**

このアクションモジュールは、指定されたメッセージを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>チャネル ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メッセージ ID （タイムスタンプ） ]</td> 
   <td> <p> 削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、Watch Private Channel モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL プライベートチャネルメッセージを取得]**

このアクションモジュールは、選択したチャネルからメッセージの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel]</p> </td> 
   <td> <p>メッセージを含むチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Public Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL パブリックチャネルメッセージを取得]**

このアクションモジュールは、指定されたパブリックチャネルから指定された ID を持つメッセージを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>メッセージを含むチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Public Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL リストへの返信]**

このアクションモジュールは、会話に投稿されたメッセージのスレッドを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>返信を取得するメッセージを含んだチャネルのタイプを選択し、チャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 親メッセージ ID （タイム スタンプ） ]</td> 
   <td> <p> 返信を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Public Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す返信の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL メッセージの検索]**

この検索モジュールは、検索クエリに一致するメッセージを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>検索に使用するクエリを入力します。 </p> <p>マッピングパネルからの式の作成については、<a href="/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> の組み込み関数を使用した項目のマッピング」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオの実行サイクルごとにモジュールが返すレコードの最大数を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by] </td> 
   <td> <p>返されたメッセージをスコアまたはタイムスタンプで並べ替えるかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>メッセージを昇順または降順で並べ替えるかどうかを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL メッセージを更新]**

このアクションモジュールを使用すると、既存のメッセージを編集できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>必要なメッセージを選択する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Channel ID or name]</strong> フィールドで、チャネル ID またはメッセージを含むチャネルを入力またはマッピングし、メッセージの <strong>[!UICONTROL Time Stamp (Message ID)]</strong> を入力します。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>チャネルのタイプを選択し、チャネルを選択して、メッセージを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>更新するメッセージの新しいテキストコンテンツを入力します。</p> <p>詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blocks]</td> 
   <td>ブロックは、メッセージをカスタマイズおよび整理するために使用できる再利用可能なコンポーネントです。ブロックについて詳しくは、[!DNL Slack] ドキュメント内の <a href="https://api.slack.com/block-kit">Block Kit</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Link names]</p> </td> 
   <td> <p>このオプションを有効にすると、名前とチャネルで <code>@username</code> または <code>#channel</code> 書式を使用できるようになります。 </p> <p>詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse message text]</p> </td> 
   <td> <p>このオプションを有効にすると、自動解析を行うことができるようになります。 </p> <p> 詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> <p>メモ：元のメッセージで [!UICONTROL Link names] オプションまたは [!UICONTROL Parse message text] オプションを使用した場合は、メッセージを更新モジュールの実行時にもオプションを指定する必要があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ダイレクトメッセージを見る]**

このトリガーモジュールは、ダイレクトメッセージに新しいメッセージが追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するダイレクトメッセージの会話を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL マルチパーティダイレクトメッセージを見る]**

このトリガーモジュールは、新しいメッセージがマルチパーティダイレクトメッセージチャネルに追加されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するダイレクトメッセージの会話を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL プライベートチャネルメッセージを監視]**

このトリガーモジュールは、新しいメッセージがプライベートチャネル（グループ）に追加されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するプライベートチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL パブリックチャネルメッセージの監視]**

このトリガーモジュールは、新しいメッセージがパブリックチャネルに追加されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するパブリックチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### ファイル

+++ **[!UICONTROL ファイルを削除]**

このアクションモジュールは、指定されたファイルを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>削除するファイルの ID を入力またはマップします。 </p> <p>メモ：ファイル ID は、[!DNL Watch Files] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ファイルの取得]**

このアクションモジュールは、指定されたファイルに関する詳細を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>取得するファイルの ID を入力またはマッピングします。 </p> <p>メモ：ファイル ID は、[!DNL Watch Files] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ファイルをリストする]**

このアクションモジュールは、指定されたフィルターに基づいてファイルのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>取得するファイルのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel type]</p> </td> 
   <td> <p>ファイルをリストするチャネルを表すチャネルのタイプを選択し、チャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の作成者 ]</td> 
   <td> <p>ユーザーを選択すると、指定したユーザーによって作成されたファイルのみが返されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 開始日 ]</td> 
   <td>ファイルの返却元となる最も早い日付を入力します。 サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制：[!DNL Adobe Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 日付から ]</td> 
   <td>ファイルを返す日付の最後の日付を入力します。 サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制：[!DNL Adobe Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオ実行サイクルでモジュールが返す最大ファイル数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--

+++ **[!UICONTROL Download a File]**

This action module downloads a file from a URL. It must follow the [!UICONTROL Slack] >[!UICONTROL Get a File] module in a scenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL private download]</td> 
   <td> <p>Map the <b>[!UICONTROL URL Private download]</b> value from the [!DNL Slack] >[!UICONTROL Get a File] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

+++ **[!UICONTROL ファイルのアップロード]**

このアクションモジュールは、[!DNL Slack] にファイルを作成またはアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL チャンネル ]</td> 
   <td> <p>ファイルのアップロード先のチャネルごとに「<b>[!UICONTROL 項目の追加 ]</b>」をクリックし、チャネルのタイプとチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>アップロードするファイルのタイトルを入力</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スレッド ID （タイムスタンプ） ]</td> 
   <td> <p>ファイルを返信としてアップロードする場合、返信するメッセージのタイムスタンプを入力またはマップします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 初期コメント ]</td> 
   <td> <p>ファイルを紹介するメッセージのテキストを入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ファイルの監視]**

このトリガーモジュールは、新しいファイルが追加されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>モジュールで監視するファイルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td> <p>ファイルを監視するチャネルのタイプを選択してから、チャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の作成者 ]</td> 
   <td> <p>ユーザーを選択すると、指定したユーザーによって作成されたファイルのみが返されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す最大ファイル数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### チャネル

+++ **[!UICONTROL チャネルのアーカイブ]**

このアクションモジュールは、チャネルをアーカイブします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>アーカイブするチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルの作成]**

新しいチャネルを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Name]</p> </td> 
   <td> <p>新しいチャネルの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL はプライベートです ]</td> 
   <td>新しいチャネルをプライベートに設定するには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルを取得]**

このアクションモジュールは、ワークスペースチャネルに関する情報を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>情報を取得するチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルへの参加]**

このアクションモジュールは、ユーザーをチャネルに結合します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>結合するチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルから移動]**

このアクションモジュールは、チャネルからユーザーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>終了するチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルを一覧表示]**

この検索モジュールは、ワークスペース内のすべてのチャネルのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Exclude archived]</p> </td> 
   <td> <p>「[!UICONTROL Yes]」を選択して、結果のアーカイブ済みチャネルを除外します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>取得するチャネルのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す最大チャネル数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネル内のメンバーを一覧表示]**

この検索モジュールは、選択したチャネルのユーザーのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>リストを取得するメンバーを含むチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public]／[!UICONTROL Private Channel]</td> 
   <td>メンバーを一覧表示するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返すメンバーの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルの目的の設定]**

チャネルの目的を変更するアクションモジュール

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>目的を変更するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / User / [!UICONTROL Multiple IM Channel]</td> 
   <td>目的を変更するチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の目的 ]</td> 
   <td>チャネルの新しい目的を入力またはマッピングします。 このフィールドは、書式設定やリンクをサポートしていません。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルのトピックの設定]**

このアクションモジュールはチャネルのトピックを変更します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>トピックを変更するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM Channel]</td> 
   <td>トピックを変更するチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL トピック ]</td> 
   <td>チャネルの新しいトピックを入力またはマッピングします。 このフィールドは、書式設定やリンクをサポートしていません。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルのアーカイブ解除]**

このアクションモジュールは、チャネルのアーカイブを解除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>アーカイブ解除するチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 反応

+++ **[!UICONTROL 反応を追加]**

このアクションモジュールは、項目に反応を追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>反応を追加するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>反応を追加するチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メッセージ ID （タイムスタンプ） ]</td> 
   <td> <p> 反応を追加するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 反応（絵文字）名 ]</td> 
   <td>反応に使用する絵文字の名前を入力またはマッピングします。 例：<code>thumbsup</code>。 </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL リストの反応]**

このアクションモジュールは、ユーザーが行った反応を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User]</p> </td> 
   <td> <p>リストする反応を行ったユーザーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す反応の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 反応を削除]**

このアクションモジュールは、項目から反応を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>反応を削除するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>反応を削除するチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> 反応を削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 反応（絵文字）名 ]</td> 
   <td>メッセージから削除する絵文字の名前を入力またはマッピングします。 例：<code>thumbsup</code>。 </td> 
  </tr> 
 </tbody> 
</table>

+++

### スター

+++ **[!UICONTROL 星を追加]**

このアクションモジュールは、チャネルを星つきチャネルにします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>星を追加するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>星を追加するチャネルまたはユーザーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 星の削除]**

このアクションモジュールは、星空チャネルから星を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>星を追加するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>星を追加するチャネルまたはユーザーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

### 保存済みの項目

+++ **[!UICONTROL 保存済みアイテムの削除]**

このアクションモジュールは、保存された項目から項目を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 保存された項目から削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>保存した項目から削除するファイルを入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL アイテムの保存]**

このアクションモジュールは、保存された項目に項目を追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 保存するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>保存するファイルを入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### ピン留め

+++ **[!UICONTROL アイテムをピン留め]**

このアクションモジュールは、チャネルに項目をピン留めします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>項目をピン留めするチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パブリック ] / [!UICONTROL プライベート ] / [!UICONTROL マルチ IM チャネル ] / [!UICONTROL ユーザー ]</td> 
   <td>項目をピン留めするチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> ピン留めするメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 項目のピン留めを解除]**

このアクションモジュールは、チャネルから項目のピン留めを解除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>項目のピン留めを解除するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パブリック ] / [!UICONTROL プライベート ] / [!UICONTROL マルチ IM チャネル ] / [!UICONTROL ユーザー ]</td> 
   <td>項目のピン留めを解除するチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> ピン留めを解除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### ユーザー

+++ **[!UICONTROL ユーザーの取得]**

このアクションモジュールは、ワークスペースのメンバーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User ID]</p> </td> 
   <td> <p>詳細を取得するユーザーのユーザー ID を入力またはマッピングします。</p> <p>メモ：ユーザー ID は、[!DNL List Users] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーの招待]**

このアクションモジュールは、1 ～ 30 人のユーザーをパブリックまたはプライベートチャネルに招待します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>ユーザーを招待するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パブリック ] / [!UICONTROL プライベート チャネル ]</td> 
   <td>ユーザーを招待するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Users]</td> 
   <td> <p>チャネルに追加するユーザーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーのキック]**

このアクションモジュールは、チャネルからユーザーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>ユーザーを削除するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パブリック ] / [!UICONTROL プライベート チャネル ]</td> 
   <td>ユーザーを削除するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Users]</td> 
   <td> <p>チャネルから削除するユーザーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL List Users]**

このアクションモジュールは、ワークスペース内のすべてのユーザーのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Limit]</p> </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す最大ユーザー数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーの検索]**

このアクションモジュールは、メールアドレスを使用して、1 人のユーザーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email] </p> </td> 
   <td> <p>詳細を取得するユーザーのメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーのウォッチ]**

このトリガーモジュールは、新しいユーザーが [!DNL Slack] ワークスペースに追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す最大ユーザー数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### リマインダー

<!--

+++ **[!UICONTROL List Reminders]**

This action module returns a list of all reminders created by or given to the currently authenticated user.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Limit]</p> </td> 
   <td> <p>Enter or map the maximum number of reminders you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Reminder]**

This action module retrieves details about a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to retrieve details for.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

+++ **[!UICONTROL リマインダーの作成]**

このアクションモジュールはリマインダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td>リマインダーのコンテンツを入力またはマッピング</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 時間 ]</td> 
   <td> <p>このリマインダーが行われる日時を入力またはマップします。 次のいずれかを入力します。 </p> 
    <ul> 
     <li> <p>Unix タイムスタンプ（最大で 5 年後）</p> </li> 
     <li> <p>リマインダーが表示されるまでの秒数（24 時間以内の場合） </p> </li> 
     <li> <p>自然言語の説明（例：「15 分以内」または「毎週木曜日」）</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User] </p> </td> 
   <td> <p>リマインダーを受信するユーザーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

<!--

+++ **[!UICONTROL Complete a Reminder]**

This action module completes a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to complete.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Delete a Reminder]**

This action module deletes a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to delete.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

### イベント

+++ **[!UICONTROL 新しいイベント]**

このインスタント トリガーは、新しいメッセージまたは他のイベントが作成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>使用する Webhook を選択します。</p> <p>または</p> <p>新しい Webhook を作成します。</p> 
    <ol> 
     <li value="1"> <p>「<b>[!UICONTROL Add]</b>」をクリックします。</p> </li> 
     <li value="2"> <p>イベントタイプを選択します。</p> </li> 
     <li value="3"> <p>接続を選択または追加します。 [!DNL Slack] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!UICONTROL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </li> 
     <li value="4"> <p>プロンプトが表示されたら、視聴するチャネルを選択します。</p> </li> 
     <li value="5"> <p>「<b>[!UICONTROL Save]</b>」をクリックして web フックを保存し、モジュールに戻ります。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

+++

### プロファイル

+++ **[!UICONTROL ステータスの設定]**

このアクションモジュールは、ユーザーの現在のステータスを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL ステータス テキスト ]</p> </td> 
   <td> <p>ステータステキストを入力またはマッピングします。 次の点に注意してください。</p> 
    <ul> 
     <li> <p>最大 100 文字まで入力できます。</p> </li> 
     <li> <p>マークアップや、ユーザーメンションなどの他の書式を使用できます。</p> </li> 
     <li> <p>ステータステキストに絵文字を含めるには、書式 <code>:emojiname:</code> を使用します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ステータス絵文字 ]</td> 
   <td> <p>ステータスを表すために使用する絵文字を入力またはマッピングします。 <code>:emojiname:</code> の形式を使用します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 状態の有効期限 ]</td> 
   <td>ステータスを期限切れにする日時を入力またはマッピングします。 サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制</a>を参照してください。</td> 
  </tr> 
 </tbody> 
</table>

+++

### その他

+++ **[!UICONTROL API 呼び出しを実行]**

このアクションモジュールでは、[!DNL Slack] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Slack] モジュールでは不可能なデータフロー自動処理を実現できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://slack.com/api/</code> からの相対パスを入力します。例：<code>/users/identity</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] によって認証ヘッダーが追加されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td>API 呼び出しに使用するベース URL を選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

## 用語

[!DNL Slack] モジュールを設定する場合、次の用語が役立つ場合があります。

* **DM**：[!UICONTROL ダイレクトメッセージ]
* **IM**：[!UICONTROL インスタントメッセージ]
* **プライベートチャネル**：以前は[!UICONTROL グループ化]
* **ダイレクトメッセージ**：以前は [!UICONTROL IM]
* **チャネル**：API ドキュメントの[!UICONTROL 会話]、[!DNL Slack] アプリの[!UICONTROL チャネル]。
