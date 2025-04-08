---
title: Slack モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Slack を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: c9c68a4c-f592-42d1-b15f-a525b9aa3944
source-git-commit: eb0518ba0d1a0c758cb547e362c722f4be3674c7
workflow-type: tm+mt
source-wordcount: '1954'
ht-degree: 66%

---

# [!DNL Slack] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Slack] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

[!DNL Slack] モジュールを使用するには、[!DNL Slack] アカウントが必要です。

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

[!DNL Slack] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Slack] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [メッセージ](#messages)
* [会話](#channels)
* [その他](#other)

### メッセージ

* [メッセージの作成](#create-a-message)
* [メッセージを削除](#delete-a-message)
* [プライベートチャネルメッセージの取得](#get-a-private-channel-message)
* [公開チャネルメッセージの取得](#get-a-public-channel-message)
* [メッセージを更新](#update-a-message)
* [プライベートチャネルメッセージを見る](#watch-private-channel-messages)
* [公開チャネルメッセージを視聴](#watch-public-channel-messages)

### [!UICONTROL メッセージを作成]

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
   <td role="rowheader">[！ユーザーとしての UICONTROL]</td> 
   <td>このオプションを有効にすると、このモジュールの接続で使用される資格情報を所有するユーザーとしてメッセージを投稿できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Thread message ID (time stamp)]</td> 
   <td>新しいメッセージが返信の場合は、返信先のメッセージのタイムスタンプを入力します。既に返信があるメッセージのタイムスタンプを入力しないでください。</td> 
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
   <td role="rowheader">[!UICONTROL Attachments]</td> 
   <td>メッセージに添付する項目ごとに、「<b> 項目を追加 </b>」をクリックして項目の詳細を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アイコン絵文字 ]</td> 
   <td><code>:icon-name:</code> の形式で、このメッセージのアイコンとして使用する絵文字を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アイコン URL]</td> 
   <td>このメッセージのアイコンとして使用する画像の URL を入力またはマップします。 </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL User name]</td> 
   <td>メッセージの投稿に使用するユーザー名を指定します。 ユーザー名を指定しない場合は、「Bot」という名前が使用されます。</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL メッセージを削除]

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
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> 削除するメッセージのタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、プライベートチャネルメッセージを監視モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！ユーザーとしての UICONTROL]</td> 
   <td> <p> 接続で使用された資格情報を持つユーザーとしてメッセージを削除する場合は、このオプションを有効にします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プライベートチャネルメッセージを取得]

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
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>チャネル ID を入力（マッピング）します。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>メモ：タイムスタンプは、[!UICONTROL Watch Private Channel Messages] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL  公開チャネルメッセージの取得 ]**

このアクションモジュールは、指定された公開チャネルから、指定された ID を持つメッセージを返します。

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
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Public Channel Messages] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージを更新]

このアクションモジュールを使用すると、既存のメッセージを編集できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Slack] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Choose how you want to select the message you want to .</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>In the <strong>[!UICONTROL Channel ID or name]</strong> field, enter or map the Channel ID or of the channel that contains the message, then enter the <strong>[!UICONTROL Time Stamp (Message ID)]</strong> of the message.</p> <p>Note: The Channel ID can be retrieved using the [!UICONTROL List Channels] module.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Select the type of channel, then select the channel, then select the message.</p> </li> 
    </ul> </td> 
  </tr> -->
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>更新するメッセージを含むチャネルの ID を入力またはマッピングします。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> 情報を取得するメッセージのメッセージタイムスタンプを入力またはマッピングします。</p> <p>注意：タイムスタンプは、[!UICONTROL Watch Public Channel Messages] モジュールなどの別のモジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>更新するメッセージの新しいテキストコンテンツを入力します。</p> <p>詳しくは、[!DNL Slack] ドキュメントの<a href="https://api.slack.com/docs/formatting">アプリケーションサーフェスのテキストの書式</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！ユーザーとしての UICONTROL]</td> 
   <td>このオプションを有効にすると、このモジュールの接続で使用される資格情報を所有するユーザーとしてメッセージが更新されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachments]</td> 
   <td>メッセージに添付する項目ごとに、「<b> 項目を追加 </b>」をクリックして項目の詳細を入力します。</td> 
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

### [!UICONTROL プライベートチャネルメッセージを監視]

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
   <td> <p>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すメッセージの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL パブリックチャネルメッセージの監視]

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
   <td> <p>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すメッセージの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>



### 会話

* [チャネルの取得](#get-a-channel)
* [チャネルのリスト](#list-channels)
* [チャネルのメンバーのリスト](#list-members-in-channel)

#### [!UICONTROL チャネルを取得]

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

#### [!UICONTROL チャネルを一覧表示]

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
   <td> <p>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すチャネルの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>
</table>

#### [!UICONTROL チャネル内のメンバーを一覧表示]

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
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>必要なメッセージを選択する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>「<strong>[!UICONTROL チャネル ID または名前 ]</strong>」フィールドに、ユーザーのリストを表示するチャネル ID またはチャネルのマッピングを入力します。</p> <p>メモ：チャネル ID は、[!UICONTROL List Channels] モジュールを使用して取得できます。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>チャネルのタイプを選択し、チャネルを選択します。</p> </li> 
    </ul> </td> 
  </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>[!DNL Workfront Fusion]が 1 回の実行サイクルで返すメンバーの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>


### その他

#### [!UICONTROL API 呼び出しを実行]

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
   <td><code>https://slack.com/api/</code> への相対パスを入力します。例：<code>/users/identity</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
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
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td>API 呼び出しに使用するベース URL を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アクセストークンを送信 ]</td> 
   <td>アクセストークンをヘッダーとして送信するか、クエリパラメーターとして送信するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

## 用語

[!DNL Slack] モジュールを設定する場合、次の用語が役立つ場合があります。

* **DM**：[!UICONTROL ダイレクトメッセージ]
* **IM**：[!UICONTROL インスタントメッセージ]
* **プライベートチャネル**：以前は[!UICONTROL グループ化]
* **ダイレクトメッセージ**：以前は [!UICONTROL IM]
* **チャネル**：API ドキュメントの[!UICONTROL 会話]、[!DNL Slack] アプリの[!UICONTROL チャネル]。
