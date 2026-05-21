---
title: GitHub モジュール
description: Adobe Workfront Fusionでは、GitHubを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: d9e6c26c-8770-40bc-a83a-8c05f86e4a3f
TQID: https://experienceleague.adobe.com/oGM3EGtQVFeEvQ1PPJQEsu9BI4-blE73oz3BR51eUWs
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1976
ht-degree: 71%

---

# [!DNL GitHub] モジュール

Adobe Workfront Fusionでは、[!UICONTROL GitHub]を使用するワークフローを自動化したり、複数のサードパーティ製アプリケーションやサービスに接続したりできます。

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

[!DNL GitHub] モジュールを使用するには、[!DNL GitHub] アカウントが必要です。

## [!DNL GitHub] を Workfront Fusion に接続

[!DNL GitHub] アカウントを [!UICONTROL Workfront Fusion] に接続する手順に関しては、[[!UICONTROL Adobe Workfront Fusion] への接続を作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

## [!DNL GitHub] モジュールとそのフィールド。

[!DNL GitHub] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL GitHub]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)

### トリガー

* [[!UICONTROL コメントを監視]](#watch-comments)
* [[!UICONTROL フォークを監視]](#watch-forks)
* [[!UICONTROL イシューを監視]](#watch-issues)
* [[!UICONTROL 取得リクエストを監視]](#watch-pull-requests)
* [[!UICONTROL リポジトリーを監視]](#watch-repositories)

#### [!UICONTROL コメントを監視]

このトリガーモジュールは、新しいコメントが追加されたり、既存のコメントが変更されたりすると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>監視するリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue number]</td> 
   <td>特定のイシューに対して行われた新しいコメントのみを検索するように検索を制限する場合は、イシューの番号を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> 1回のサイクルでWorkfront Fusionが返すコメントの最大数を設定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>新しいコメントのみを監視するか、コメントとすべての変更を監視するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォークを監視]

このトリガーモジュールは、新しいフォークが作成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>フォークを監視するリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned forks]</td> 
    <td>各シナリオ実行サイクル中にモジュールが返す最大フォーク数を入力またはマッピングします。</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イシューを監視]

このトリガーモジュールは、新しいイシューが追加されたり、既存のイシューが変更されたりすると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to watch]</td> 
   <td>このアカウントに関連付けられたすべてのリポジトリを監視するか、1つのリポジトリのみを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>1 つのリポジトリーのみのイシューの監視を選択している場合は、監視するリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> 1回のサイクルでWorkfront Fusionが返すイシューの最大数を設定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>新しいイシューのみを監視するか、新しいイシューとすべての変更を監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>監視するイシューを、そのイシューとどのように関係しているかによってフィルタリングできます。</p> 
    <ul> 
     <li>[!UICONTROL All issues]</li> 
     <li>[!UICONTROL Only issues assigned to me]</li> 
     <li>[!UICONTROL Only issues created by me]</li> 
     <li>[!UICONTROL Only issues mentioning me]</li> 
     <li>[!UICONTROL Only issues I'm subscribed to updates for]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>未完了のイシューのみを閲覧するか、クローズされたイシューのみを閲覧するかを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>追加する各タグについて、<b>項目を追加</b>をクリックし、タグを入力します。 モジュールはこれらのタグに関する問題を監視します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得リクエストを監視]

このモジュールは、新しい取得リクエストが追加されたり、または既存の取得リクエストが変更されたりするとトリガーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>監視するリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned pull requests]</td> 
   <td> <p> 1回のサイクルでWorkfront Fusionが返すプルリクエストの最大数を設定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>[!UICONTROL only open pull]リクエスト、[!UICONTROL only closed ones]またはすべてのプルリクエストのどれを監視するかを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>新規のプルリクエストのみを監視するか、新規のリクエストとすべての変更を監視するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リポジトリーを監視]

このトリガーモジュールは、リポジトリが作成または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned repositories]</td> 
   <td> <p> 1回のサイクルでWorkfront Fusionが返すリポジトリの最大数を設定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>新しいリポジトリーとすべての変更を監視するか、新しいリポジトリーのみを監視するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL 割り当て先の追加]](#add-assignees)
* [[!UICONTROL イシューへのラベルの追加]](#add-labels-to-an-issue)
* [[!UICONTROL コメントの作成]](#create-a-comment)
* [[!UICONTROL 問題の作成]](#create-an-issue)
* [[!UICONTROL イシューの取得]](#get-an-issue)
* [[!UICONTROL コメントのリスト]](#list-comments)
* [[!UICONTROL イシューからのラベルの削除]](#remove-a-label-from-an-issue)
* [[!UICONTROL 割り当て先の削除]](#remove-assignees)
* [[!UICONTROL イシューの検索]](#search-for-an-issue)
* [[!UICONTROL イシューの更新]](#update-an-issue)

#### [!UICONTROL 割り当て先を追加]

このモジュールは、指定されたイシューに割り当て先を追加します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>割り当て先を追加するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>イシューに割り当てる担当者を選択します。 対応可能な担当者には、リポジトリーへの書き込み権限を持つユーザーや、リポジトリーへの読み取り権限を持つ組織のメンバーが含まれます。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>担当者を追加するイシューのイシュー番号を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イシューにラベルを追加]

このモジュールは、イシューにラベルを追加します。 ラベルはリポジトリーレベルで定義され、リポジトリーへの書き込みアクセス権を持つユーザーのみが作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>ラベルを追加するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>イシューに追加するラベルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>ラベルを追加するイシューのイシュー番号を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントの作成]

このモジュールは、指定されたイシューに対するコメントを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>コメントを作成するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>コメントを作成するイシューのイシュー番号を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>コメントの内容を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 問題の作成]

このモジュールでは、選択したリポジトリに新しいイシューを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>イシューを作成するリポジトリを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>イシューに割り当てる担当者を選択します。 対応可能な担当者には、リポジトリへの書き込み権限を持つすべてのユーザーや、リポジトリへの読み取り権限を持つ組織のメンバーが含まれます。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Milestone]</td> 
   <td>新しいイシューに関連付けるマイルストーンを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>新しいイシューに適用するラベルを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>新しいイシューのタイトルを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>説明や追加情報など、イシューの本文の入力またはマッピング</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イシューを取得]

このモジュールは、指定されたイシューに関する詳細を取得します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>詳細を取得するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>詳細を取得するイシューの問題番号を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントのリスト]

このモジュールは、指定されたイシューに関するすべてのコメントを一覧表示します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>コメントを一覧表示するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>コメントを一覧表示するイシューのイシュー番号を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since]</td> 
   <td>モジュールは、この日付以降に作成されたコメントを返します。 サポートされている日付形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 返されたコメントの最大数]</td> 
   <td> <p> 1回のサイクルでWorkfront Fusionが返すコメントの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イシューからラベルを削除]

このモジュールは、1 つのラベルをイシューから削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>ラベルを削除するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>イシューから削除するラベルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>ラベルを削除するイシューのイシュー番号を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 割り当て先を削除]

このモジュールは、指定されたイシューから割り当て先を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>割り当て先を削除するイシューを含むリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>イシューから削除するユーザーを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>割り当て先を削除するイシューのイシュー番号を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イシューの検索]

このモジュールでは、検索条件に一致するイシューを検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> 1回のサイクルでWorkfront Fusionが返すイシューの最大数を設定します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>検索結果の並べ替え方法を選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Best match] </p> </li> 
     <li>[!UICONTROL Date created]</li> 
     <li>[!UICONTROL Date updated]</li> 
     <li>[!UICONTROL Number of comments]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort direction]</td> 
   <td> <p>昇順または降順を選択します。 </p> <p>日付の場合、<strong>[!UICONTROL descending]</strong>を選択すると、最新の日付が最初に返されます。 </p> <p>[!UICONTROL number of comments]の場合、<strong>[!UICONTROL descending]</strong>を選択すると、コメントが最も多いイシューが最初に返されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td>検索クエリを入力またはマッピングします。 検索オプションについて詳しくは、[!DNL GitHub] ヘルプサイトの<a href="https://docs.github.com/ja/github/searching-for-information-on-github/searching-issues-and-pull-requests">Issue およびプルリクエストを検索する</a>を参照してください。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イシューを更新]

このモジュールは、既存の [!DNL GitHub] イシューを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL GitHub] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>イシューを更新するリポジトリーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>イシューに割り当てる担当者を選択します。 対応可能な担当者には、リポジトリーへの書き込み権限を持つユーザーや、リポジトリーへの読み取り権限を持つ組織のメンバーが含まれます。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Milestone]</td> 
   <td>イシューに関連付けるマイルストーンを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>イシューに適用するラベルを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>更新するイシューのイシュー番号を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>イシューの更新先のステートを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>イシューの新しいタイトルを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>説明や追加情報など、イシューの新しい本文を入力またはマッピングします</td> 
  </tr> 
 </tbody> 
</table>
