---
title: Microsoft Teams モジュール
description: Adobe Workfront Fusion のシナリオでは、Teams を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
source-git-commit: f5b49cca308fad01167aed27e4716a3d630cb026
workflow-type: tm+mt
source-wordcount: '3642'
ht-degree: 10%

---

# Microsoft Teams モジュール

<!-- ADD REDIRECTS -->

Adobe Workfront Fusion のシナリオでは、Microsoft Teamsを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[&#x200B; シナリオの作成：記事のインデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

Microsoft Teams モジュールを使用するには、モジュールでアクションを実行できるMicrosoft Teams アカウントが必要です。

## Microsoft Teams サービスのWorkfront Fusion への接続

Microsoft Teams アカウントをAdobe Workfront Fusion に接続する手順については、[Workfront Fusion への接続の作成 – 基本手順 &#x200B;](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

## Microsoft Teams モジュールとそのフィールド

Workfront Fusion でMicrosoft Teams モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のMicrosoft Teams フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

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
* [チームの取得](#get-a-team)
* [すべてのチームとグループをリストする](#list-all-teams-and-groups)
* [参加したチームのリスト](#list-joined-teams)
* [チームの更新](#update-a-team)
* [チームを見る](#watch-teams)

#### グループからのチームの作成

この操作モジュールは、既存のMicrosoft Office 365 グループからチームを作成し、新しいチームの設定を構成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>チームを作成するグループを選択します。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">メンバーにチャネルの作成および更新を許可</td> 
   <td>メンバーがチャネルを作成および更新できるようにするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーがチャネルを削除することを許可</td> 
   <td>メンバーがチャネルを削除できるようにするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーにアプリの追加と削除を許可</td> 
   <td>メンバーにアプリの追加と削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーがタブを作成、更新、および削除することを許可</td> 
   <td>メンバーがタブを作成、更新、および削除できるようにするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンバーがコネクタを作成および削除できるようにする</td> 
   <td>メンバーがコネクタを作成および削除できるようにするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザーが自分のメッセージを編集できるようにする</td> 
   <td>ユーザーが自分のメッセージを編集できるようにするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザーによるメッセージの削除を許可</td> 
   <td>ユーザーによるメッセージの削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">所有者にメッセージの削除を許可</td> 
   <td>所有者によるメッセージの削除を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンション@team 許可</td> 
   <td>メンションを許可するかどうかを選択@team ます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メンション@channel 許可</td> 
   <td>メンションを許可するかどうかを選択@channel ます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Giphy を許可</td> 
   <td>このチームで Giphy の使用を許可するかどうかを選択してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ステッカーとミームを許可</td> 
   <td>ユーザーにステッカーとミームを含めるかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">カスタム ミームを許可</td> 
   <td>ユーザーにカスタムミームを含めるかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ゲストによるチャネルの作成および更新を許可</td> 
   <td>ゲストによるチャネルの作成と更新を許可するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ゲストによるチャネルの削除を許可</td> 
   <td>ゲストによるチャネルの削除を許可するかどうかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### Office 365 グループの作成

この操作モジュールは、Microsoft Office 365 にグループを作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">表示名</td> 
   <td> <p>このグループがアドレス帳に表示する名前を入力またはマップします。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">グループのエイリアス</td> 
   <td>このグループの電子メールエイリアスを入力またはマッピングします。 小文字、数字、アンダースコアを使用できます。 Office 365 グループの種類の場合、これはグループのメール エイリアス （[Alias]@[Your Domain].onmicrosoft.com）になります。 セキュリティ・グループ・タイプの場合、エイリアスはニックネームとして機能します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループタイプ</td> 
   <td>Office 365 グループとセキュリティ グループのどちらを作成するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td>このグループの説明を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">セキュリティが有効</td> 
   <td>グループのセキュリティを有効にする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">所有者</td> 
   <td>このグループの所有者を選択してください。</td> 
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
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>削除するグループの ID を入力またはマッピングします。</p> 
   </tr> 
 </tbody> 
</table>

#### チームの取得

指定したMicrosoft チームまたは Office 365 グループのプロパティとリレーションシップを取得します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>詳細を取得するグループの ID を入力またはマッピングします。</p> 
   </tr> 
 </tbody> 
</table>

#### すべてのチームとグループをリストする

このモジュールには、組織に関連付けられているMicrosoft Teamsおよび Office 365 グループのすべてのチームが一覧表示されます。 フィルターを適用して、指定した条件を満たす結果のみを返すことができます。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フィルター</td> 
   <td> <p>フィルターを設定して、選択した条件を満たすチームおよびグループのみを返すことができます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。AND または OR ルールを追加すると、複数のフィルターを使用できます。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>


#### 参加したチームのリスト

このアクションモジュールには、このモジュールで使用される接続に関連付けられたユーザーが参加しているチームが一覧表示されます。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### チームの更新

この操作モジュールは、Microsoft Teamsまたは Office 365 グループの指定されたチームのプロパティを更新します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">表示名</td> 
   <td> <p>このグループがアドレス帳に表示する名前を入力またはマップします。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">グループのエイリアス</td> 
   <td>このグループの電子メールエイリアスを入力またはマッピングします。 小文字、数字、アンダースコアを使用できます。 Office 365 グループの種類の場合、これはグループのメール エイリアス （[Alias]@[Your Domain].onmicrosoft.com）になります。 セキュリティ グループ タイプの場合、エイリアスはニックネームとして機能します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td>このグループの説明を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">セキュリティが有効</td> 
   <td>グループのセキュリティを有効にする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">可視性</td> 
   <td>Office 365 グループの表示を指定します。</td> 
  </tr> 
 </tbody> 
</table>

#### チームを見る

このトリガーモジュールは、チームが作成されるとシナリオを開始します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フィルター</td> 
   <td> <p>フィルターを設定して、選択した条件を満たすチームおよびグループのみを監視できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。AND または OR ルールを追加すると、複数のフィルターを使用できます。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

### チャネル

* [チャネルの作成](#create-a-channel)
* [チャネルの削除](#delete-a-channel)
* [チャネルの取得](#get-a-channel)
* [チャネルのリスト](#list-channels)
* [チャネルの更新](#update-a-channel)

#### チャネルの作成

このアクションモジュールは、指定されたチームの新しいチャネルを作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャンネルを作成するMicrosoft Teamsのチームを選択します。</p> </td> 
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

指定したチャンネルをMicrosoft チームから削除します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャンネルを削除するMicrosoft Teamsのチームの ID を入力またはマッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>削除するチャネルの ID を入力またはマッピングします。</td> 
  </tr> 
  </tbody> 
</table>

#### チャネルの取得

このモジュールは、チャネルのプロパティと関係を取得します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>詳細を取得するチャネルを所有するMicrosoft Teamsのチームの ID を入力またはマッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>詳細を取得するチャネルの ID を入力またはマッピングします。</td> 
  </tr> 
  </tbody> 
</table>

#### チャネルのリスト

このモジュールは、Microsoft Teams で指定されたチームが所有するチャネルの一覧を表示します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャネルをリストするMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返す最大チャネル数を設定します。</td> 
  </tr> 
  </tbody> 
</table>

#### チャネルの更新

指定したチャネルの説明を更新します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>更新するチャンネルがあるMicrosoft Teamsのチームを選択します。</p> </td> 
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
* [メッセージの送信](#send-a-message)
* [メッセージを見る](#watch-messages)
* [新しい返信をウォッチ](#watch-new-replies)

#### チャネルメッセージへの返信

このアクションモジュールは、指定されたチャネルでメッセージへの返信を作成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>返信先のメッセージが含まれるチャネルを所有するMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>返信するメッセージを含むチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td>メッセージ ID</td> 
   <td>返信するメッセージの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>コンテンツタイプ</td> 
   <td>メッセージをプレーンテキストで送信するか、HTML形式で送信するかを選択します。</td> 
  </tr> 
  <tr> 
   <td>返信メッセージ</td> 
   <td>送信する返信メッセージの本文を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### メッセージの送信

このアクションモジュールは、チームのチャネルまたはチャットにメッセージを送信します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">メッセージタイプ/td&gt; 
   <td> <p>チャネルメッセージとチャットメッセージのどちらを送信するかを選択します。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャンネルにメッセージを送信する場合は、メッセージの送信先のチャンネルを持つMicrosoft Teamsのチームの ID を入力するか、マッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>チャネルにメッセージを送信する場合、メッセージの送信先のチャネルの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>新しいチャットを作成</td> 
   <td>チャットメッセージを送信する場合は、新しいチャットを作成するかどうかを選択します。
   <ul><li><b>はい</b><p>1 対 1 のチャットとグループチャットのどちらを希望するかを選択し、チャットに含めるメンバーを選択します。 このモジュールが使用する接続に関連付けられているユーザーを選択する必要があります。また、1 対 1 のチャットには、そのユーザーと他の 1 人のユーザーのみが含まれている必要があります。</p><p>グループチャットを作成する場合は、「トピック」フィールドでトピックを設定できます。</p>
   <li><b>いいえ</b><p>メッセージの送信先のチャネルを所有するチームの ID を入力またはマッピングしてから、チャネルの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>メッセージ</td> 
   <td>送信するメッセージの本文を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>コンテンツタイプ</td> 
   <td>メッセージをプレーンテキストで送信するか、HTML形式で送信するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### メッセージを見る

このトリガーモジュールは、メッセージがチームのチャンネルまたはチャットに送信されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">監視するメッセージのタイプ</td> 
   <td> <p>チャネルメッセージを視聴するか、チャットメッセージを視聴するかを選択します。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>チャネルメッセージをウォッチしている場合は、メッセージをウォッチするチャネルを持つMicrosoft Teamsのチームを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>チャネル ID</td> 
   <td>チャネルメッセージを視聴している場合、メッセージを視聴するチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td>チャット ID</td> 
   <td>チャットメッセージを見ている場合は、メッセージを見たいチャットを選択します。</td> 
  </tr> 
  <tr> 
   <td>返されるメッセージの最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すメッセージの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### 新しい返信をウォッチ

このトリガーモジュールは、指定されたメッセージが新しい返信を受信したときにシナリオを開始します。

このモジュールは、個人用アカウントには使用できません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> <p>返信を監視するチャネルを持つMicrosoft Teamsのチームを選択します。</p> </td> 
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
   <td>返信の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返す返信の最大数を設定します。</td> 
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
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">メンバー名</td> 
   <td> <p>Microsoft Teamsに追加するメンバーの名前を入力またはマッピングします。</p> </td> 
   </tr> 
  <tr> 
   <td>パスワード</td> 
   <td>メンバーのパスワードを入力またはマップします。</td> 
  </tr> 
 </tbody> 
</table>

#### グループへのメンバーの追加

このアクション モジュールは、Office 365 グループにメンバーを追加します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">グループ ID</td> 
   <td> <p>メンバーを追加するグループを選択します。</p> </td> 
   </tr> 
  <tr> 
   <td>メンバー ID</td> 
   <td>グループに追加するメンバーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### オンライン会議

* [オンライン会議の作成](#create-an-online-meeting)
* [オンライン会議を削除する](#delete-an-online-meeting)
* [オンライン ミーティングを取得する](#get-an-online-meeting)
* [オンライン ミーティングの更新](#update-an-online-meeting)

#### オンライン会議の作成

このアクションモジュールは、ユーザーのカレンダー上のイベントに関連付けられていないスタンドアロンの会議を作成します。 この会議はユーザーの予定表には表示されません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">件名</td> 
   <td>この会議の件名を入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">開始日時</td> 
   <td>会議を開始する日時を入力またはマップします。 サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">終了日時</td> 
   <td>会議を終了する日時を入力またはマップします。 サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">許可された発表者</td> 
   <td>この会議への出席を許可するグループを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者</td> 
   <td>会議に追加する各出席者について、[<b> アイテムの追加 </b>] をクリックし、出席者の名前と役割を選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者がカメラを有効にできるようにする</td> 
   <td>出席者が自分のカメラを使用できるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者がマイクを有効にできるようにします</td> 
   <td>出席者が自分のマイクを有効にできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">会議チャットを許可</td> 
   <td>会議チャットを有効にするか、無効にするか、または会議通話の期間に制限するかを選択します</td> 
   </tr> 
   <tr> 
   <td role="rowheader">チームの反応を許可</td> 
   <td>この会議でチームの反応を有効にするかどうかを選択してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">スレッド ID</td> 
   <td>この会議に関連付けられているスレッドの ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">メッセージ ID</td> 
   <td>この会議に関連付けられているメッセージの ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">返信チェーンメッセージ ID</td> 
   <td>この会議に関連付けられている返信チェーンの ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">エントリと離脱をアナウンス</td> 
   <td>出席者の入退室時に会議で通知するかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">範囲</td> 
   <td>ロビーでの待機をバイパスできる参加者のグループを選択します。 これらの出席者は、会議に直接参加します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ダイヤルインユーザーがロビーを回避できるようにします</td> 
   <td>ダイヤルインユーザーがロビーを回避できるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">自動的に記録</td> 
   <td>ミーティングを自動的に記録するかどうかを選択してください。</td> 
   </tr> 
   </tbody> 
</table>

#### オンライン会議を削除する

このアクション モジュールは、指定された ID を持つオンライン会議を削除します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">会議 ID</td> 
   <td> <p>削除する会議の ID を入力またはマップします。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### オンライン ミーティングを取得する

このアクション モジュールは、指定された ID を持つオンライン会議の詳細を取得します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">会議 ID</td> 
   <td> <p>詳細を取得する会議の ID を入力またはマッピングします。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### オンライン ミーティングの更新

このアクション モジュールは、指定された ID でオンライン会議を更新します。



<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">会議 ID</td> 
   <td>更新する会議の ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">件名</td> 
   <td>この会議の件名を入力またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">開始日時</td> 
   <td>会議を開始する日時を入力またはマップします。 サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">終了日時</td> 
   <td>会議を終了する日時を入力またはマップします。 サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">許可された発表者</td> 
   <td>この会議への出席を許可するグループを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者</td> 
   <td>会議に追加する各出席者について、[<b> アイテムの追加 </b>] をクリックし、出席者の名前と役割を選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者がカメラを有効にできるようにする</td> 
   <td>出席者が自分のカメラを使用できるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者がマイクを有効にできるようにします</td> 
   <td>出席者が自分のマイクを有効にできるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">会議チャットを許可</td> 
   <td>会議チャットを有効にするか、無効にするか、または会議通話の期間に制限するかを選択します</td> 
   </tr> 
   <tr> 
   <td role="rowheader">チームの反応を許可</td> 
   <td>この会議でチームの反応を有効にするかどうかを選択してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">スレッド ID</td> 
   <td>この会議に関連付けられているスレッドの ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">メッセージ ID</td> 
   <td>この会議に関連付けられているメッセージの ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">返信チェーンメッセージ ID</td> 
   <td>この会議に関連付けられている返信チェーンの ID を入力またはマップします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">エントリと離脱をアナウンス</td> 
   <td>出席者の入退室時に会議で通知するかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">範囲</td> 
   <td>ロビーでの待機をバイパスできる参加者のグループを選択します。 これらの出席者は、会議に直接参加します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">ダイヤルインユーザーがロビーを回避できるようにします</td> 
   <td>ダイヤルインユーザーがロビーを回避できるようにするかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">自動的に記録</td> 
   <td>ミーティングを自動的に記録するかどうかを選択してください。</td> 
   </tr> 
   </tbody> 
</table>

### その他

* [ユーザーの有無を確認](#check-presence-of-users)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [ユーザーを検索](#search-users)

#### ユーザーの有無を確認

選択したユーザーがMicrosoft Teamsに存在するかどうかを確認します。

このモジュールは個人用アカウントをサポートしていません。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ユーザー ID</td> 
   <td> <p>プレゼンスを確認するユーザーを選択します。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### カスタム API 呼び出しの実行

このアクションモジュールは、Microsoft Teams API に対してカスタムリクエストを実行します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Microsoft Teams アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://graph.microsoft.com</code> からの相対パスを入力します。例：<code> /v1.0/groups</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft Teams アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フィルター</td> 
   <td> <p>フィルターを設定して、選択した条件を満たすユーザーのみを返すことができます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。AND または OR ルールを追加すると、複数のフィルターを使用できます。</p> </td> 
   </tr> 
  <tr> 
   <td>返される結果の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
 </tbody> 
</table>



