---
title: Jira モジュール
description: Adobe Workfront Fusion シナリオでは、Jira ソフトウェアを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: b74a3618-c4a1-4965-a88d-1643bfab12db
source-git-commit: 017341e045a703f5d6e933a6df860f4fc8c0649d
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 36%

---

# Jira モジュール

>[!NOTE]
>
>これらの手順は、新しいバージョンの Jira コネクタに適用されます。このバージョンには、Jira というラベルのみが付いています。 従来の Jira Cloud および Jira Server コネクタについては、[Jira ソフトウェアモジュール &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-software-modules.md) を参照してください。

Adobe Workfront Fusion シナリオでは、Jira を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

Jira コネクタは、Jira Cloud と Jira Data Server の両方で使用できます。

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

* Jira モジュールを使用するには、Jira アカウントが必要です。
* Jira で OAuth2 アプリケーションを作成するには、Jira Developer Consoleにアクセスできる必要があります。

## Jira のWorkfront Fusion への接続

Jira への接続を作成する手順は、基本接続と OAuth2 接続のどちらを作成しているかによって異なります。

* [Jira への OAuth2 接続の作成](#create-an-oauth2-connection-to-jira)
* [Jira への基本的な接続の作成](#create-a-basic-connection-to-jira)

### Jira への OAuth2 接続の作成

Jira への OAuth2 接続を作成するには、Fusion で接続を設定する前に、Jira でアプリケーションを作成する必要があります。

* [Jira での OAuth2 アプリケーションの作成](#create-an-oauth2-application-in-jira)
* [Fusion で OAutt2 接続を設定](#configure-the-oauth2-connection-in-fusion)

#### Jira での OAuth2 アプリケーションの作成

>[!IMPORTANT]
>
>Jira 接続用に OAuth2 アプリケーションを作成して設定するには、Jira Developer Consoleにアクセスできる必要があります。

1. [Jira Developer Console](https://developer.atlassian.com/console.myapps/) に移動します。
1. マイアプリ領域で、「**作成**」をクリックし、「**OAuth 2.0 統合**」を選択します。
1. 統合の名前を入力し、開発者条件に同意して、「**作成**」をクリックします。

   アプリケーションが作成され、アプリケーション設定領域に移動します。
1. 左側のナビゲーションパネルで **権限** をクリックします。
1. 権限領域で、「**Jira API**」行を探します。
1. Jira API の行で「**追加**」をクリックし、同じ行で「**続行**」をクリックします。
1. 次の範囲を有効にします。

   * Jira 問題データの表示（`read:jira-work`）
   * ユーザープロファイルの表示（`read:jira-user`）
   * イシューの作成と管理（`write:jira-work`）

1. 左側のナビゲーションで、「**認証**」をクリックします。
1. OAuth 2.0 認証用の行で「**追加**」をクリックします。
1. 「**コールバック URL**」フィールドに、Workfront Fusion データセンターに基づいて、次のいずれかの URL を入力します。

   | Fusion データセンター | コールバック URL |
   |---|---|
   | US | `https://app.workfrontfusion.com/oauth/cb/workfront-jira2` |
   | EU | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira2` |
   | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira2` |

1. 左側のナビゲーションで、「**設定**」をクリックします。
1. （オプション）「説明」フィールドに説明を入力して、そのフィールドの下にある **変更を保存** をクリックします。
1. クライアント ID とクライアントシークレットを「設定」領域から安全な場所にコピーするか、Fusion で接続を設定する際にこのページを開いたままにします。
1. 続けて [Fusion で OAutt2 接続を設定する &#x200B;](#configure-the-oauth2-connection-in-fusion) を実行します。

#### Fusion で OAuth2 接続を設定

1. 任意の Jira モジュールで、「接続」フィールドの横にある **追加** をクリックします。
1. 次のフィールドを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>接続タイプ</p> </td> 
      <td> <p><b>OAuth 2</b> を選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>接続名</p> </td> 
      <td> <p>新しい接続の名前を入力します。</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">サービス URL</td>
      <td>Jira インスタンスの URL を入力します。 これは、Jira へのアクセスに使用する URL です。</td>
     </tr>
     <tr>
      <td role="rowheader">Jira アカウントタイプ</td>
       <td>Jira Cloud と Jira データセンターのどちらに接続するかを選択します。</td>
     </tr>
     <tr> 
      <td role="rowheader">クライアント ID</td> 
      <td> <p><a href="#create-an-oauth2-application-in-jira" class="MCXref xref" data-mc-variable-override="">Jira での OAuth2 アプリケーションの作成 </a> で作成した Jira アプリケーションのクライアント ID を入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">クライアントシークレット</td> 
      <td> <p><a href="#create-an-oauth2-application-in-jira" class="MCXref xref" data-mc-variable-override="">Jira での OAuth2 アプリケーションの作成 </a> で作成した Jira アプリケーションのクライアントシークレットを入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">追加範囲</td> 
      <td>この接続に追加する追加のスコープを入力してください。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API バージョン</td> 
      <td>この接続を接続する Jira API バージョンを選択します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

### Jira への基本的な接続の作成

Jira への基本的な接続の作成は、Jira Cloud への接続を作成するか Jira データセンターへの接続を作成するかによって異なります。

* [Jira Cloud への基本的な接続の作成](#create-a-basic-connection-to-jira-cloud)
* [Jira データセンターへの基本接続の作成](#create-a-basic-connection-to-jira-data-center)

#### Jira Cloud への基本的な接続の作成

>[!IMPORTANT]
>
> Jira Cloud への基本的な接続を作成するには、Jira API トークンが必要です。
>Jira API トークンの取得手順については、Atlassian ドキュメントの [Atlassian アカウントの API トークンの管理 &#x200B;](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account) を参照してください。


1. 任意の Jira モジュールで、「接続」フィールドの横にある **追加** をクリックします。
1. 次のフィールドを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>接続タイプ</p> </td> 
      <td> <p>基本接続と OAuth 2 接続のどちらを作成するかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>接続名</p> </td> 
      <td> <p>新しい接続の名前を入力します。</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">サービス URL</td>
      <td>Jira インスタンスの URL を入力します。 これは、Jira へのアクセスに使用する URL です。</td>
     </tr>
     <tr>
      <td role="rowheader">Jira アカウントタイプ</td>
       <td>Jira Cloud と Jira データセンターのどちらに接続するかを選択します。</td>
     </tr>
     <tr> 
      <td role="rowheader">メール</td> 
      <td>メールアドレスを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API トークン</td> 
      <td>API トークンを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API バージョン</td> 
      <td>この接続を接続する Jira API バージョンを選択します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

#### Jira データセンターへの基本接続の作成

>[!IMPORTANT]
>
> Jira データセンターへの基本的な接続を作成するには、Jira 個人アクセストークン（PAT）が必要です。
>Jira 個人アクセストークンの取得手順については、Atlassian ドキュメントの [Atlassian アカウントの API トークンの管理 &#x200B;](https://confluence.atlassian.com/enterprise/using-personal-access-tokens-1026032365.html) を参照してください。
>PAT を作成する際の考慮事項については、この記事の [PAT の設定 &#x200B;](#configure-your-pat) を参照してください。

1. 任意の Jira モジュールで、「接続」フィールドの横にある **追加** をクリックします。
1. 次のフィールドを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>接続タイプ</p> </td> 
      <td> <p>基本接続と OAuth 2 接続のどちらを作成するかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>接続名</p> </td> 
      <td> <p>新しい接続の名前を入力します。</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">サービス URL</td>
      <td>Jira インスタンスの URL を入力します。 これは、Jira へのアクセスに使用する URL です。</td>
     </tr>
     <tr>
      <td role="rowheader">Jira アカウントタイプ</td>
       <td>Jira Cloud と Jira データセンターのどちらに接続するかを選択します。</td>
     </tr>
     <tr> 
      <td role="rowheader">PAT （個人用アクセストークン）</td> 
      <td>Jira 個人用アクセストークンを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API バージョン</td> 
      <td>この接続を接続する Jira API バージョンを選択します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

##### PAT の設定

Jira データセンターへの基本的な接続を作成するには、Jira 個人アクセストークン（PAT）が必要です。

Jira 個人アクセストークンの取得手順については、Atlassian ドキュメントの [Atlassian アカウントの API トークンの管理 &#x200B;](https://confluence.atlassian.com/enterprise/using-personal-access-tokens-1026032365.html) を参照してください。

PAT の設定時には、次の情報が必要になる場合があります

* リダイレクト URL

  | Fusion データセンター | リダイレクト URL |
  |---|---|
  | US | `https://app.workfrontfusion.com/oauth/cb/workfront-jira` |
  | EU | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira` |
  | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira` |

* ファイル設定

PAT を使用するには、ファイル `jira/bin/WEB-INF/classes` のファイル `jira-config.properties` で次の項目を有効にする必要があります。

* `jira.rest.auth.allow.basic = true`
* `jira.rest.csrf.disabled = true`

このファイルが存在しない場合は、作成する必要があります。

## Jira モジュールとそのフィールド

Jira モジュールを設定する場合、Workfront Fusion では以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の Jira フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

#### レコードを監視

このトリガーモジュールは、レコードが追加、更新または削除された時点でシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Webhook</td> 
   <td> <p>レコードのウォッチに使用する Webhook を選択するか、新しい Webhook を作成します。 </p> <p>新しい Webhook を作成するには：</p> 
    <ol> 
     <li><strong> 追加 </strong> をクリックします</li> 
     <li>Web フックの名前を入力します。</li> 
     <li> Web フックに使用する接続を選択します。 <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </li> 
     <li> <p>ソフトウェアで監視するレコードの種類を選択します。</p> 
      <ul> 
       <li>イシュー</li> 
       <li>コメント </li> 
       <li>作業ログ </li> 
       <li>プロジェクト </li> 
       <li>スプリント</li> 
       <li>添付ファイル </li> 
      </ul> </li> 
     <li>このシナリオをトリガーする 1 つ以上のイベントタイプを選択します。</li> 
     <li>このモジュールの Jira クエリ言語フィルターを入力します。<p>JQL について詳しくは、Atlassian のヘルプサイトで <a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a> を参照してください。 </p></li>
     <li><b> 保存 </b> をクリックして、Webhook を保存します。 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [スプリントにイシューを追加](#add-issue-to-sprint)
* [レコードを作成](#create-a-record)
* [カスタム API 呼び出し](#custom-api-call)
* [レコードの削除](#delete-a-record)
* [添付ファイルのダウンロード](#download-an-attachment)
* [レコードを読み取る](#read-a-record)
* [レコードの更新](#update-a-record)

#### スプリントにイシューを追加

このアクションモジュールは、スプリントに 1 つ以上のイシューを追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">スプリント ID</td> 
   <td>イシューを追加するスプリントのスプリント ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">問題 ID またはキー</td> 
   <td>スプリントに追加するイシューまたはキーごとに、「<b> 項目を追加 </b>」をクリックして、イシュー ID またはキーを入力します。 1 つのモジュールに最大 50 個まで入力できます。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードを作成

このアクションモジュールは、Jira に新しいレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>モジュールで作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li>添付ファイル</li> 
     <li>コメント</li> 
     <li>イシュー</li> 
     <li>プロジェクト</li> 
     <li>スプリント </li> 
     <li>作業ログ</li> 
     <li>ユーザー</li> 
     <li>ボード</li> 
     <li>カテゴリ</li> 
     <li>フィルター</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td> 他のフィールドに入力します。 フィールドは、選択したレコードタイプに応じて使用できます。 </td> 
  </tr> 
 </tbody> 
</table>

#### カスタム API 呼び出し

このアクションモジュールを使用すると、Jira API に対してカスタム認証呼び出しを行うことができます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>相対パスを入力します<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">メソッド</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ヘッダー</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">クエリ文字列</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">本文</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### レコードの削除

このアクションモジュールは、指定されたレコードを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>モジュールで削除するレコードのタイプを選択します。 </p> 
    <ul> 
     <li>コメント</li> 
     <li>イシュー</li> 
     <li>プロジェクト</li> 
     <li>スプリント </li> 
     <li>作業ログ</li> 
     <li>添付ファイル</li> 
     <li>ボード</li> 
     <li>カテゴリ</li> 
     <li>フィルター</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">（レコードタイプ） ID</td> 
   <td>削除するレコードの ID またはキーを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 添付ファイルのダウンロード

このアクションモジュールは、指定された添付ファイルをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID</td> 
   <td>ダウンロードする添付ファイルの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードを読み取る

このアクションモジュールは、Jira で指定されたレコードからデータを読み取ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>モジュールで読み取る Jira レコードのタイプを選択します。</p> 
    <ul> 
     <li>添付ファイル</li> 
     <li>コメント</li> 
     <li>イシュー</li> 
     <li>プロジェクト</li> 
     <li>スプリント </li> 
     <li>作業ログ</li> 
     <li>ユーザー</li> 
     <li>ボード</li> 
     <li>カテゴリ</li> 
     <li>フィルター</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力</td> 
   <td>受け取る出力を選択します。出力オプションは、「レコードタイプ」フィールドで選択したレコードのタイプに基づいて使用できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">（レコードタイプ） ID</td> 
   <td> <p>モジュールで読み取るレコードの一意の Jira ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### レコードの更新

このアクションモジュールは、イシューやプロジェクトなどの既存のレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>モジュールで更新するレコードのタイプを選択します。レコードタイプを選択すると、そのレコードタイプに固有の他のフィールドがモジュールに表示されます。</p> 
    <ul> 
     <li>コメント</li> 
     <li>イシュー</li> 
     <li>プロジェクト</li> 
     <li>スプリント </li> 
     <li>移行の問題</li> 
     <li>カテゴリ </li> 
     <li>フィルター </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID またはキー</td> 
   <td>更新するレコードの ID またはキーを入力またはマッピングします。</td> 
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td> 他のフィールドに入力します。 フィールドは、選択したレコードタイプに応じて使用できます。 </td> 
  </tr> 
 </tbody> 
</table>

### 検索

>[!IMPORTANT]
>
>従来の Jira コネクターで使用されていた検索モジュールでは、次のエラーが発生する場合があります。
>
>`[410] The requested API has been removed. Please migrate to the /rest/api/3/search/jql API. A full migration guideline is available at https://developer.atlassian.com/changelog/#CHANGE-2046`
>
>これは、Jira 側の廃止によるものです。
>
>このエラーが発生した場合は、従来の Jira コネクターの検索モジュールを新しいコネクターの検索モジュールに置き換えることができます。新しいコネクターでは、使用する API バージョンを選択できます。接続を作成する場合は、必ず V3 を選択します。
>
> ![&#x200B; 新しい Jira コネクタの API バージョンオプション &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/jira-version-option.png)
>
>メモ：
>
>* 影響を受けるのは検索モジュールのみです。現時点では、Fusion コネクターで使用される他の Jira API エンドポイントは、この廃止の影響を受けません。
>
>* 地理的なロールアウトによって不整合が発生する場合があります。Atlassian はこの変更を地域的に展開しています。つまり、一部の Jira クラウドインスタンスでは、引き続き一時的に古いエンドポイントをサポートしている可能性があります。これにより、環境間で動作に一貫性がなくなる可能性があります。

#### レコードの検索

この検索モジュールは、指定した検索クエリに一致する Jira のオブジェクト内のレコードを検索します。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Jira アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Jira をWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>モジュールで検索するレコードのタイプを選択します。レコードタイプを選択すると、そのレコードタイプに固有の他のフィールドがモジュールに表示されます。</p> 
    <ul> 
     <li>イシュー</li> 
     <li>プロジェクト</li> 
     <li>ユーザー</li> 
     <li>スプリント</li> 
     <li>ボード</li> 
     <li>作業ログ</li> 
     <li>コメント</li> 
     <li>トランジションの問題</li> 
     <li>カテゴリ</li> 
    </ul> </td> 
  <tr> 
   <td role="rowheader"> <p>最大結果数</p> </td> 
   <td> <p>シナリオの実行サイクルごとにモジュールが取得するレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
    <td role="rowheader">オフセット</td> 
    <td> 詳細を取得する最初の項目の ID を入力またはマッピングします。 これは、レコードにページ番号を付ける方法です。 オフセットとして 5000 番目の項目を入力すると、モジュールは項目 5000-9999 を返します。</td> 
   </tr>
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td> 他のフィールドに入力します。 フィールドは、選択したレコードタイプに応じて使用できます。 </td> 
  </tr> 
 </tbody> 
</table>
