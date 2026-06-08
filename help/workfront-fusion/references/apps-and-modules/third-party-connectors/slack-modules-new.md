---
title: Slack モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Slack を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 4c14fa36-8333-40d6-bd0a-fc6b0d9f4410
TQID: https://experienceleague.adobe.com/fHIb5n3hU15APXxrrQiEmT-KS9aIlN-4hjUByFfpG-I
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 81d1dfcdb5c15f6a93e2793f9a0e41821b65c7e3
workflow-type: tm+mt
source-wordcount: 4620
ht-degree: 37%

---

# [!DNL Slack] モジュール

>[!IMPORTANT]
>
>この記事では、2025年11月17日（PT）にリリースされた新しいSlack コネクタで使用可能なモジュールについて説明します。
>
>従来のSlack コネクタについて詳しくは、[[!DNL Slack] modules （Legacy） &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/slack-modules.md)を参照してください。

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
* OAuth@接続を作成する場合は、組織の接続に次のURLを追加する必要があります。
   * ボットトークン：`https://oauth.app.workfrontfusion.com/oauth/cb/slack3`
   * ユーザートークン：` https://oauth.app.workfrontfusion.com/oauth/cb/slack2`

## Slack APIについて

Slack コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td><pre><code>&#123;&#123;ifempty(parameters.domain, 'https://slack.com/api/')&#125;&#125;</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v4.0.15</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Slack] モジュールとそのフィールド

[!DNL Slack] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Slack]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td>ブロックは、メッセージをカスタマイズおよび整理するために使用できる再利用可能なコンポーネントです。 ブロックについて詳しくは、[!DNL Slack] ドキュメント内の <a href="https://api.slack.com/block-kit">Block Kit</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スレッド メッセージ ID （タイムスタンプ） &#x200B;]</td> 
   <td>新しいメッセージが返信の場合は、返信するメッセージのタイムスタンプを入力します。 返信済みのメッセージのタイムスタンプは入力しないでください。</td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>チャネル ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メッセージ ID （タイムスタンプ） &#x200B;]</td> 
   <td> <p> 削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、Watch Private Channel Moduleなどの別のモジュールを使用して取得できます。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel]</p> </td> 
   <td> <p>メッセージを含むチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Public Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL パブリックチャネルメッセージを取得]**

このアクションモジュールは、指定されたパブリックチャネルから特定のIDを持つメッセージを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>メッセージを含むチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Public Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 返信を一覧表示]**

このアクションモジュールは、会話に投稿されたメッセージのスレッドを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>返信を取得するメッセージを含むチャネルのタイプを選択し、そのチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 親メッセージ ID （タイムスタンプ） &#x200B;]</td> 
   <td> <p> 返信を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Public Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクル中にモジュールが返す最大返信数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL メッセージを検索]**

この検索モジュールは、検索クエリに一致するメッセージを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>検索に使用するクエリを入力します。 </p> <p>マッピングパネルから数式を作成する方法については、<a href="/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md" class="MCXref xref">組み込み関数を使用してアイテムを[!DNL Adobe Workfront Fusion]</a>にマッピングするを参照してください。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>必要なメッセージを選択する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL チャネル IDまたは名前]</strong> フィールドに、メッセージを含むチャネル IDまたはチャネルのチャネル IDを入力またはマッピングしてから、メッセージの<strong>[!UICONTROL タイムスタンプ （メッセージ ID） &#x200B;]</strong>を入力します。 .</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>チャネルのタイプを選択し、チャネルを選択して、メッセージを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>更新するメッセージの新しいテキストコンテンツを入力します。</p> <p>詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blocks]</td> 
   <td>ブロックは、メッセージをカスタマイズおよび整理するために使用できる再利用可能なコンポーネントです。 ブロックについて詳しくは、[!DNL Slack] ドキュメント内の <a href="https://api.slack.com/block-kit">Block Kit</a> を参照してください。</td> 
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

+++ **[!UICONTROL ダイレクトメッセージの視聴]**

このトリガーモジュールは、新しいメッセージがダイレクトメッセージに追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するダイレクトメッセージ会話を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL マルチパーティダイレクトメッセージの視聴]**

このトリガーモジュールは、新しいメッセージがマルチパーティダイレクトメッセージチャネルに追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するダイレクトメッセージ会話を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返すメッセージの最大数を入力します。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するプライベートチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返すメッセージの最大数を入力します。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>新しいメッセージを監視するパブリックチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### ファイル

+++ **[!UICONTROL ファイルを削除]**

このアクションモジュールは、指定したファイルを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>削除するファイルのIDを入力するか、マッピングします。 </p> <p>メモ：ファイル IDは、[!DNL Watch Files] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>取得するファイルのIDを入力またはマッピングします。 </p> <p>メモ：ファイル IDは、[!DNL Watch Files] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ファイルをリストする]**

このアクションモジュールは、指定したフィルターに基づいてファイルのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>取得するファイルのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel type]</p> </td> 
   <td> <p>ファイルを一覧表示するチャネルを表すチャネルのタイプを選択し、チャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created by]</td> 
   <td> <p>指定したユーザーが作成したファイルのみを返すユーザーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Date from]</td> 
   <td>ファイルを返す最も古い日付を入力します。 サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制：[!DNL Adobe Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Date to]</td> 
   <td>ファイルを返す最新の日付を入力します。 サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制：[!DNL Adobe Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオ実行サイクル中にモジュールが返すファイルの最大数を入力またはマッピングします。</td> 
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

このアクションモジュールは、[!DNL Slack]にファイルを作成またはアップロードします

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL チャンネル &#x200B;]</td> 
   <td> <p>ファイルをアップロードする各チャネルについて、<b>[!UICONTROL Add item]</b>をクリックし、チャネルタイプとチャネルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>アップロードするファイルのタイトルを入力します</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スレッド ID （タイムスタンプ） &#x200B;]</td> 
   <td> <p>ファイルを返信としてアップロードする場合は、返信するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 初期コメント &#x200B;]</td> 
   <td> <p>ファイルを導入するメッセージのテキストを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ファイルの監視]**

このトリガーモジュールは、新しいファイルが追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL Created by]</td> 
   <td> <p>指定したユーザーが作成したファイルのみを返すユーザーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクル中にモジュールが返すファイルの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### チャネル

+++ **[!UICONTROL チャネルをアーカイブ]**

このアクションモジュールは、チャネルをアーカイブします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>アーカイブするチャネルのIDを入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルの作成]**

このアクションモジュールは、新しいチャネルを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Name]</p> </td> 
   <td> <p>新しいチャネルの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL はプライベートです]</td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>情報を取得するチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルに参加]**

このアクションモジュールは、ユーザーをチャネルに結合します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>結合するチャネルのIDを入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルを残す]**

このアクションモジュールは、チャネルからユーザーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>残すチャネルのIDを入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td> <p>シナリオ実行サイクルごとにモジュールが返すチャネルの最大数を設定します。</p> </td> 
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
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>リストするメンバーを含むチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public]／[!UICONTROL Private Channel]</td> 
   <td>メンバーを一覧表示するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返す最大メンバー数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルの目的を設定]**

このアクションモジュールは、チャネルの目的を変更します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL Purpose]</td> 
   <td>チャネルの新しい目的を入力するか、マッピングします。 このフィールドでは、書式設定やリンクはサポートされていません。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルのトピックの設定]**

このアクションモジュールは、チャネルのトピックを変更します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL Topic]</td> 
   <td>チャネルの新しいトピックを入力またはマッピングします。 このフィールドでは、書式設定やリンクはサポートされていません。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL チャネルのアーカイブ解除]**

このアクションモジュールは、チャネルをアーカイブ解除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>アーカイブを解除するチャネルのIDを入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 反応

+++ **[!UICONTROL 反応を追加]**

このアクションモジュールは、アイテムに反応を追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL メッセージ ID （タイムスタンプ） &#x200B;]</td> 
   <td> <p> 反応を追加するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reaction （絵文字）名]</td> 
   <td>反応に使用する絵文字の名前を入力またはマッピングします。 例：<code>thumbsup</code>。 </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL リアクションのリスト]**

このアクションモジュールは、ユーザーが実行したリアクションを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User]</p> </td> 
   <td> <p>リストするリアクションを行ったユーザーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクル中にモジュールが返す最大応答数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 反応を削除]**

このアクションモジュールは、アイテムから反応を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
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
   <td> <p> 反応を削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reaction （絵文字）名]</td> 
   <td>メッセージから削除する絵文字の名前を入力またはマッピングします。 例：<code>thumbsup</code>。 </td> 
  </tr> 
 </tbody> 
</table>

+++

### スター

+++ **[!UICONTROL 星を追加]**

このアクションモジュールは、チャネルをスター付きチャネルにします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>星を追加するチャンネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>星を追加するチャネルまたはユーザーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 星を削除]**

このアクションモジュールは、スター付きのチャンネルから星を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>星を追加するチャンネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL User] / [!UICONTROL Multiple IM channel]</td> 
   <td>星を追加するチャネルまたはユーザーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

### 保存済みの項目

+++ **[!UICONTROL 保存した項目を削除]**

このアクションモジュールは、保存されたアイテムからアイテムを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 保存されたアイテムから削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>保存したアイテムから削除するファイルを入力するか、マッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL アイテムを保存]**

このアクションモジュールは、保存されたアイテムにアイテムを追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 保存するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td> <p>保存するファイルを入力するか、マッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### ピン留め

+++ **[!UICONTROL アイテムをピン留めする]**

このアクションモジュールは、項目をチャネルにピン留めします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>アイテムをピン留めするチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL Multiple IM channel] / [!UICONTROL User]</td> 
   <td>アイテムをピン留めするチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> ピン留めするメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL アイテムのピン留めを解除]**

このアクションモジュールは、チャネルからアイテムを展開します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>アイテムのピン留めを解除するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private] / [!UICONTROL Multiple IM channel] / [!UICONTROL User]</td> 
   <td>アイテムのピン留めを解除するチャネルまたはユーザーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> ピン留めを解除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Private Channel] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### ユーザー

+++ **[!UICONTROL ユーザーを取得]**

このアクションモジュールは、ワークスペースのメンバーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User ID]</p> </td> 
   <td> <p>詳細を取得するユーザーのユーザーIDを入力またはマッピングします。</p> <p>注意：ユーザーIDは、[!DNL List Users] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーを招待]**

このアクションモジュールは、パブリックチャネルまたはプライベートチャネルに1～30人のユーザーを招待します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>ユーザーを招待するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private channel]</td> 
   <td>ユーザーを招待するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Users]</td> 
   <td> <p>チャネルに追加するユーザーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーをキック]**

このアクションモジュールは、チャネルからユーザーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel type]</td> 
   <td>ユーザーを削除するチャネルのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Public] / [!UICONTROL Private channel]</td> 
   <td>ユーザーを削除するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Users]</td> 
   <td> <p>チャネルから削除するユーザーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーを一覧表示]**

このアクションモジュールは、ワークスペース内のすべてのユーザーのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Limit]</p> </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返すユーザーの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーを検索]**

このアクションモジュールは、メールアドレスを使用して、1人のユーザーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email] </p> </td> 
   <td> <p>詳細を取得するユーザーの電子メールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ユーザーを監視]**

このトリガーモジュールは、新しいユーザーが[!DNL Slack] ワークスペースに追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>シナリオ実行サイクルごとにモジュールが返すユーザーの最大数を設定します。</p> </td> 
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

+++ **[!UICONTROL リマインダーを作成]**

このアクションモジュールはリマインダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td>リマインダーの内容を入力またはマッピングします</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Time]</td> 
   <td> <p>このリマインダーが表示される日時を入力またはマッピングします。 次のいずれかを入力します。 </p> 
    <ul> 
     <li> <p>Unixのタイムスタンプ（最大5年後）</p> </li> 
     <li> <p>リマインダーまでの秒数（24時間以内の場合） </p> </li> 
     <li> <p>自然言語の説明（例：「15分で」または「毎週木曜日」）</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User] </p> </td> 
   <td> <p>リマインダーを受け取るユーザーを選択します。</p> </td> 
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

このインスタントトリガーは、新しいメッセージやその他のイベントが作成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>使用するWebhookを選択します。</p> <p>または</p> <p>新しいWebhookを作成します。</p> 
    <ol> 
     <li value="1"> <p>「<b>[!UICONTROL Add]</b>」をクリックします。</p> </li> 
     <li value="2"> <p>イベントタイプを選択します。</p> </li> 
     <li value="3"> <p>接続を選択または追加します。 [!DNL Slack] アカウントを[!UICONTROL Workfront Fusion]に接続する手順については、「<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – Basic instructions</a>」を参照してください</p> </li> 
     <li value="4"> <p>メッセージが表示されたら、視聴するチャネルを選択します。</p> </li> 
     <li value="5"> <p>「<b>[!UICONTROL Save]</b>」をクリックして web フックを保存し、モジュールに戻ります。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

+++

### プロファイル

+++ **[!UICONTROL ステータスを設定]**

このアクションモジュールは、ユーザーの現在のステータスを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Status text]</p> </td> 
   <td> <p>ステータステキストを入力またはマッピングします。 次の点に注意してください。</p> 
    <ul> 
     <li> <p>最大100文字まで入力できます。</p> </li> 
     <li> <p>マークアップや、ユーザーのメンションなどの他の書式設定を使用できます。</p> </li> 
     <li> <p><code>:emojiname:</code>形式を使用して、ステータス テキストに絵文字を含めることができます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ステータス絵文字]</td> 
   <td> <p>ステータスを表すために使用する絵文字を入力またはマッピングします。 <code>:emojiname:</code> の形式を使用します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ステータスの有効期限]</td> 
   <td>ステータスの有効期限を設定する日時を入力またはマッピングします。 サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制</a>を参照してください。</td> 
  </tr> 
 </tbody> 
</table>

+++

### その他

+++ **[!UICONTROL API 呼び出しの実行]**

このアクションモジュールは、[!DNL Slack] API に対して認証済みのカスタム呼び出しを実行します。 これにより、他の [!DNL Slack] モジュールでは不可能なデータフロー自動処理を作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを[!DNL Workfront Fusion]に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">接続を[!DNL Adobe Workfront Fusion]に作成 – 基本的な手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://slack.com/api/</code> からの相対パスを入力します。 例：<code>/users/identity</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
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
