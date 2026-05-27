---
title: Microsoft Teams モジュール
description: Adobe Workfront Fusionでは、Adobe Teamsを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: d3a37c06-8f92-4065-bc00-c35f84b03f82
TQID: https://experienceleague.adobe.com/UZjZpYNF8EL5-cej0xjNp2k2gHlr8vwsS1UHwXQx1hM
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 3660
ht-degree: 14%

---

# Microsoft Teams モジュール

<!-- ADD REDIRECTS -->

Adobe Workfront Fusionでは、Microsoft Teamsを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

Microsoft Teams モジュールを使用するには、モジュールでアクションを実行できるMicrosoft Teams アカウントが必要です。

## Microsoft Teams サービスとWorkfront Fusionの接続

Microsoft Teams アカウントをWorkfront Fusionに接続する手順については、[Adobe Workfront Fusionへの接続の作成 – 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリでは、同じ接続を使用し、個々のユーザー権限に関連付けられています。 したがって、接続を作成する際に、権限の同意画面には、現在のアプリケーションに必要な新しい権限に加えて、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーがExcel コネクタを介して付与された「テーブルの読み取り」権限を持ち、Outlook コネクタで電子メールを読み取るための接続を作成した場合、権限の同意画面には、既に付与された「テーブルの読み取り」権限と新たに必要な「電子メールの書き込み」権限の両方が表示されます。

## Microsoft Teams モジュールとそのフィールド

Microsoft Teams モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Microsoft Teamsの追加フィールドが表示されることがあります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [チーム](#team)
* [チャネル](#channel)
* [メッセージ](#message)
* [メンバー](#member)
* [オンライン会議](#online-meeting)
* [その他](#other)

### チーム

* [グループからのチームの作成](#create-a-team-from-a-group)
* [Office 365 グループの作成](#create-an-office-365-group)
* [チームまたはグループの削除](#delete-a-team-or-group)
* [チームを編成](#get-a-team)
* [チームとグループをリストアップ](#list-all-teams-and-groups)
* [参加したチームを一覧表示](#list-joined-teams)
* [チームの更新](#update-a-team)
* [チームを見る](#watch-teams)

#### グループからのチームの作成

このアクションモジュールは、既存のMicrosoft Office 365 グループからチームを作成し、新しいチームの設定を行います。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>チームを作成するグループを選択します。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">メンバーがチャネルを作成および更新できるようにします</td> 
   <td>メンバーによるチャネルの作成と更新を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーによるチャネルの削除を許可</td> 
   <td>メンバーがチャネルを削除することを許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーによるアプリの追加と削除を許可</td> 
   <td>メンバーにアプリの追加と削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーによるタブの作成、更新、削除を許可</td> 
   <td>メンバーによるタブの作成、更新、削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーによるコネクタの作成と削除を許可</td> 
   <td>メンバーによるコネクタの作成と削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザーがメッセージを編集できるようにする</td> 
   <td>ユーザーによるメッセージの編集を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザーによるメッセージの削除を許可</td> 
   <td>ユーザーによるメッセージの削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">所有者がメッセージを削除することを許可</td> 
   <td>メッセージの削除を所有者に許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンション@team許可</td> 
   <td>メンションを許可するかどうかを選択@teamます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンション@channel許可</td> 
   <td>メンションを許可するかどうかを選択@channelます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Giphyを許可</td> 
   <td>このチームに対してGiphyの使用を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ステッカーとミームを許可</td> 
   <td>ユーザーにステッカーとミームの追加を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">カスタムミームを許可</td> 
   <td>ユーザーがカスタムミームを含めることができるようにするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ゲストによるチャネルの作成と更新を許可</td> 
   <td>ゲストによるチャネルの作成と更新を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ゲストによるチャネルの削除を許可</td> 
   <td>ゲストによるチャネルの削除を許可するかどうかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### Office 365 グループの作成

このアクションモジュールは、Microsoft Office 365でグループを作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">表示名</td> 
   <td> <p>このグループのアドレス帳に表示される名前を入力またはマッピングします。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">グループのエイリアス</td> 
   <td>このグループの電子メールエイリアスを入力またはマッピングします。 小文字、数字、アンダースコアを使用できます。 Office 365 グループ タイプの場合、グループの電子メール エイリアス （[Alias]@[Your Domain].onmicrosoft.com）になります。 セキュリティ グループ タイプの場合、エイリアスはニックネームとして機能します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループタイプ</td> 
   <td>Office 365 グループを作成するか、セキュリティ グループを作成するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td>このグループの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">セキュリティ有効</td> 
   <td>グループのセキュリティを有効にする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">所有者</td> 
   <td>このグループの所有者を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバー</td> 
   <td>このグループのメンバーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### チームまたはグループの削除

このアクションモジュールは、指定されたチームまたはグループを削除します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>削除するグループのIDを入力またはマッピングします。</p> 
   </tr> 
 </tbody> 
</table>

#### チームを編成

このモジュールは、指定したMicrosoft チームまたはOffice 365 グループのプロパティと関係を取得します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>詳細を取得するグループのIDを入力またはマッピングします。</p> 
   </tr> 
 </tbody> 
</table>

#### チームとグループをリストアップ

このモジュールには、組織に関連付けられているMicrosoft Teams グループとOffice 365 グループのすべてのチームが一覧表示されます。 フィルターを使用すると、指定した条件を満たす結果のみを返すことができます。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フィルター</td> 
   <td> <p>フィルターを設定して、選択した条件を満たすチームとグループのみを返すことができます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。 AND または OR ルールを追加すると、複数のフィルターを使用できます。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>


#### 参加チームのリスト

このアクションモジュールは、このモジュールで使用される接続に関連付けられたユーザーが参加したチームを一覧表示します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### チームの更新

このアクションモジュールは、Microsoft TeamsまたはOffice 365 グループ内の指定されたチームのプロパティを更新します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">表示名</td> 
   <td> <p>このグループのアドレス帳に表示される名前を入力またはマッピングします。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">グループのエイリアス</td> 
   <td>このグループの電子メールエイリアスを入力またはマッピングします。 小文字、数字、アンダースコアを使用できます。 Office 365 グループ タイプの場合、グループの電子メール エイリアス （[Alias]@[Your Domain].onmicrosoft.com）になります。 セキュリティグループタイプの場合、エイリアスはニックネームとして機能します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td>このグループの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">セキュリティ有効</td> 
   <td>グループのセキュリティを有効にする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">表示</td> 
   <td>Office 365 グループの表示を指定します。</td> 
  </tr> 
 </tbody> 
</table>

#### チームを見る

このトリガーモジュールは、チームが編成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フィルター</td> 
   <td> <p>フィルターを設定して、選択した条件を満たすチームとグループのみを監視できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。 AND または OR ルールを追加すると、複数のフィルターを使用できます。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

### チャネル

* [チャネルの作成](#create-a-channel)
* [チャネルの削除](#delete-a-channel)
* [チャネルを取得](#get-a-channel)
* [チャネルのリストアップ](#list-channels)
* [チャネルの更新](#update-a-channel)

#### チャネルの作成

このアクションモジュールは、指定したチームの新しいチャネルを作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>Microsoft Teamsで、チャネルを作成するチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル名</td> 
   <td>新しいチャネルの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>説明</td> 
   <td>新しいチャネルの説明を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### チャネルの削除

このアクションモジュールは、指定したチャネルをMicrosoft チームから削除します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャンネルを削除するMicrosoft Teamsのチーム IDを入力するか、マッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>削除するチャネルのIDを入力またはマッピングします。</td> 
  </tr> 
  </tbody> 
</table>

#### チャネルを取得

このモジュールは、チャネルのプロパティと関係を取得します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>詳細を取得するチャネルを所有するMicrosoft Teamsで、チームのIDを入力またはマッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>詳細を取得するチャネルのIDを入力またはマッピングします。</td> 
  </tr> 
  </tbody> 
</table>

#### チャネルのリストアップ

このモジュールは、指定したチームがMicrosoft Teamsで所有するチャネルを一覧表示します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>Microsoft Teamsで、チャネルをリストアップするチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返すチャネルの最大数を設定します。</td> 
  </tr> 
  </tbody> 
</table>

#### チャネルの更新

このアクションモジュールは、指定したチャネルの説明を更新します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>更新するチャネルを所有するMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル名</td> 
   <td>更新するチャネルの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>説明</td> 
   <td>チャネルの新しい説明を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### メッセージ

* [チャネルメッセージへの返信](#reply-to-a-channel-message)
* [メッセージを送信](#send-a-message)
* [メッセージを見る](#watch-messages)
* [返信を見る](#watch-new-replies)

#### チャネルメッセージへの返信

このアクションモジュールは、指定したチャネル内のメッセージに対する返信を作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>返信するメッセージを含むチャネルを所有するMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>返信するメッセージを含むチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td>メッセージ ID</td> 
   <td>返信するメッセージのIDを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td>コンテンツタイプ</td> 
   <td>メッセージをプレーンテキスト形式とHTML形式のどちらで送信するかを選択します。</td> 
  </tr> 
  <tr> 
   <td>返信メッセージ</td> 
   <td>送信する返信メッセージの本文を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### メッセージを送信

このアクションモジュールは、チームのチャネルまたはチャットにメッセージを送信します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">メッセージタイプ/td&gt; 
   <td> <p>チャネルメッセージとチャットメッセージのどちらを送信するかを選択します。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャンネルにメッセージを送信する場合は、メッセージの送信先のチャンネルを所有するMicrosoft Teamsのチーム IDを入力するか、マッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>メッセージをチャネルに送信する場合は、メッセージを送信するチャネルのIDを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>新しいチャットを作成</td> 
   <td>チャットメッセージを送信する場合は、新しいチャットを作成するかどうかを選択します。
   <ul><li><b>はい</b><p>1対1のチャットとグループのチャットのどちらかを選択し、チャットに含めるメンバーを選択します。 このモジュールが使用する接続に関連付けられているユーザーを選択する必要があり、1対1のチャットには、そのユーザーと他の1人のユーザーのみを含める必要があります。</p><p>グループチャットを作成する場合は、トピック フィールドでトピックを設定できます。</p>
   <li><b>いいえ</b><p>メッセージを送信するチャネルを所有するチームのIDを入力またはマッピングしてから、チャネルのIDを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>メッセージ</td> 
   <td>送信するメッセージの本文を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>コンテンツタイプ</td> 
   <td>メッセージをプレーンテキスト形式とHTML形式のどちらで送信するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### メッセージを見る

メッセージがチームのチャネルまたはチャットに送信されると、このトリガーモジュールはシナリオを開始します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">注目すべきメッセージの種類</td> 
   <td> <p>チャネルメッセージとチャットメッセージのどちらを視聴するかを選択します。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャネルメッセージを監視している場合は、メッセージを監視するチャンネルを所有するMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>チャネルメッセージを監視している場合は、メッセージを監視するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td>チャット ID</td> 
   <td>チャットメッセージを視聴している場合は、メッセージを視聴するチャットを選択します。</td> 
  </tr> 
  <tr> 
   <td>返されるメッセージの最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返すメッセージの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### 返信を見る

このトリガーモジュールは、指定されたメッセージによって新しい返信が受信されたときにシナリオを開始します。

このモジュールは、個人アカウントでは使用できません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>返信を監視するチャネルを所有するMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>返信を監視するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td>メッセージ ID</td> 
   <td>返信を監視するチャットを選択します。</td> 
  </tr> 
  <tr> 
   <td>返される返信の最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返す返信の最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

### メンバー

* [メンバーを追加](#add-a-member)
* [グループへのメンバーの追加](#add-a-member-to-a-group)

#### メンバーを追加

このアクションモジュールは、Microsoft Teamsにメンバーを追加します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">メンバー名</td> 
   <td> <p>Microsoft Teamsに追加するメンバーの名前を入力するか、マッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>パスワード</td> 
   <td>メンバーのパスワードを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### グループへのメンバーの追加

このアクション モジュールは、メンバーをOffice 365 グループに追加します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>メンバーを追加するグループを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>メンバーID</td> 
   <td>グループに追加するメンバーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### オンライン会議

* [オンラインミーティングの作成](#create-an-online-meeting)
* [オンライン会議の削除](#delete-an-online-meeting)
* [オンラインミーティングを予約](#get-an-online-meeting)
* [オンライン会議の更新](#update-an-online-meeting)

#### オンラインミーティングの作成

このアクションモジュールは、ユーザーのカレンダー上のイベントに関連付けられていないスタンドアロンミーティングを作成します。 このミーティングは、ユーザーのカレンダーには表示されません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">件名</td> 
   <td>このミーティングの件名を入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">開始日時</td> 
   <td>ミーティングを開始する日時を入力またはマッピングします。 サポートされている日付形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">終了日時</td> 
   <td>ミーティングを終了する日時を入力またはマッピングします。 サポートされている日付形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">許可された発表者</td> 
   <td>この会議に出席できるグループを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">参加者</td> 
   <td>会議に追加する各参加者について、<b>項目を追加</b>をクリックし、参加者の名前と役割を選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">参加者がカメラを有効にできるようにする</td> 
   <td>参加者が自分のカメラを有効にできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">参加者がマイクを有効にできるようにする</td> 
   <td>参加者が自分のマイクを有効にできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ミーティングチャットを許可</td> 
   <td>ミーティングチャットを有効にするか、無効にするか、またはミーティングコールの期間に制限するかを選択します</td> 
   </tr> 
   <tr> 
   <td role="rowheader">チームの反応を許可</td> 
   <td>このミーティングに対してTeamsの反応を有効にするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">スレッド ID</td> 
   <td>この会議に関連付けられているスレッドのIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">メッセージ ID</td> 
   <td>この会議に関連付けられているメッセージのIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">返信チェーンメッセージ ID</td> 
   <td>この会議に関連付けられている返信チェーンのIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出入りをアナウンス</td> 
   <td>参加者の出入りを通知するミーティングを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">範囲</td> 
   <td>ロビーで待機を回避できる参加者のグループを選択します。 これらの参加者は会議に直接参加します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ダイヤルインユーザーがロビーをバイパスできるようにする</td> 
   <td>ダイヤルインユーザーがロビーをバイパスできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">自動記録</td> 
   <td>会議を自動的に記録するかどうかを選択します。</td> 
   </tr> 
   </tbody> 
</table>

#### オンライン会議の削除

このアクションモジュールは、指定されたIDのオンラインミーティングを削除します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">会議ID</td> 
   <td> <p>削除する会議のIDを入力またはマッピングします。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### オンラインミーティングを予約

このアクションモジュールは、指定されたIDを持つオンラインミーティングの詳細を取得します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">会議ID</td> 
   <td> <p>詳細を取得する会議のIDを入力またはマッピングします。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### オンライン会議の更新

このアクションモジュールは、指定されたIDでオンラインミーティングを更新します。



<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">会議ID</td> 
   <td>更新する会議のIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">件名</td> 
   <td>このミーティングの件名を入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">開始日時</td> 
   <td>ミーティングを開始する日時を入力またはマッピングします。 サポートされている日付形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">終了日時</td> 
   <td>ミーティングを終了する日時を入力またはマッピングします。 サポートされている日付形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">許可された発表者</td> 
   <td>この会議に出席できるグループを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">参加者</td> 
   <td>会議に追加する各参加者について、<b>項目を追加</b>をクリックし、参加者の名前と役割を選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">参加者がカメラを有効にできるようにする</td> 
   <td>参加者が自分のカメラを有効にできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">参加者がマイクを有効にできるようにする</td> 
   <td>参加者が自分のマイクを有効にできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ミーティングチャットを許可</td> 
   <td>ミーティングチャットを有効にするか、無効にするか、またはミーティングコールの期間に制限するかを選択します</td> 
   </tr> 
   <tr> 
   <td role="rowheader">チームの反応を許可</td> 
   <td>このミーティングに対してTeamsの反応を有効にするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">スレッド ID</td> 
   <td>この会議に関連付けられているスレッドのIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">メッセージ ID</td> 
   <td>この会議に関連付けられているメッセージのIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">返信チェーンメッセージ ID</td> 
   <td>この会議に関連付けられている返信チェーンのIDを入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出入りをアナウンス</td> 
   <td>参加者の出入りを通知するミーティングを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">範囲</td> 
   <td>ロビーで待機を回避できる参加者のグループを選択します。 これらの参加者は会議に直接参加します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ダイヤルインユーザーがロビーをバイパスできるようにする</td> 
   <td>ダイヤルインユーザーがロビーをバイパスできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">自動記録</td> 
   <td>会議を自動的に記録するかどうかを選択します。</td> 
   </tr> 
   </tbody> 
</table>

### その他

* [ユーザーの有無を確認する](#check-presence-of-users)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [ユーザーを検索](#search-users)

#### ユーザーの有無を確認する

このアクションモジュールは、選択したユーザーがMicrosoft Teamsに存在するかどうかを確認します。

このモジュールは個人アカウントをサポートしていません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ユーザーID</td> 
   <td> <p>プレゼンスを確認するユーザーを選択します。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### カスタム API 呼び出しの実行

このアクションモジュールは、Microsoft Teams APIにカスタムリクエストを行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Microsoft Teams アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://graph.microsoft.com</code> からの相対パスを入力します。 例：<code> /v1.0/groups</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
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
 </tbody> 
</table>

#### ユーザーを検索

このモジュールは、指定した条件を使用してユーザーを検索します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusionに接続する方法については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フィルター</td> 
   <td> <p>フィルターを設定して、選択した条件を満たすユーザーのみを返すことができます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。 AND または OR ルールを追加すると、複数のフィルターを使用できます。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>
