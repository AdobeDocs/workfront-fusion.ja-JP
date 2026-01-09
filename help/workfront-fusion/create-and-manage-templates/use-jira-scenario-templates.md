---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: テンプレートを使用してAdobe Workfront Fusion と Jira を接続
description: これらのテンプレートを使用すると、Adobe Workfront Fusion と Jira の間でワークフローを自動化できます。
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
source-git-commit: c3d1abb898eec6fc84dc1de0fb7799d13d9e3571
workflow-type: tm+mt
source-wordcount: '4171'
ht-degree: 4%

---

# テンプレートを使用してAdobe Workfront Fusion と Jira を接続

Adobe workfront Fusion は、Fusion と Jira の間の共通のワークフローを自動化できるテンプレートを提供します。

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
   <p>Workfront：お客様の組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを保有している場合は、Adobe Workfront Fusion を購入する必要があります。</p><p>Jira: Jira Cloud のライセンスが必要です</p>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td> <p>Workfront: ユーザー、カスタムフォームおよびカスタムフィールドを作成する権限。</p> <p>Jira：ユーザーおよびカスタムフィールドを作成し、画面と Webhook を変更する権限。</td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 前提条件

### Workfront

* Adobe Developer Consoleのテクニカルアカウントが必要です。

  詳細と手順については、Adobe ドキュメントの [&#x200B; テクニカルアカウントの設定 &#x200B;](https://developer.adobe.com/cloud-storage/guides/getting-started/technical-account-setup) を参照してください。
* Adobe Admin Console製品プロファイル領域のテクニカルアカウントにシステム管理者権限を適用する必要があります。

  詳細と手順については、[Adobe Admin Consoleを使用してWorkfrontでシステム管理者を作成する &#x200B;](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/admin-console#create-system-administrators-in-workfront-with-the-adobe-admin-console) を参照してください

### Jira

Jira に OAuth2 認証を使用している場合（推奨）、[https://developer.atlassian.com/console](https://developer.atlassian.com/console) で OAuth2 アプリケーションを設定する必要があります。 詳細と手順については、Jira モジュール記事の [Jira への OAuth2 接続の作成 &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#create-an-oauth2-connection-to-jira) を参照してください。

<!--

When configuring this application, you will need the following scopes:

* `read:jira-work` 
* `read:jira-user`
* `write:jira-work`

-->

## 前提

これらのモジュールは、次のことを前提としています。

* Workfrontは、マーケティングキャンペーンプロジェクト全体の信頼できる情報源です
* Jira は技術チームによって使用され、Workfrontで開始されたプロジェクトの一部を満たしています。
* すべての Jira ユーザーがWorkfrontにアクセスできるわけではありません（その逆も同様です）。
* Workfrontと Jira はクラウドでホストされています。

## データモデル（フィールドマッピング）


| Workfront | Jira | 方向 | メモ |
|---|---|---|---|
| ObjId | WF ID * | WF → Jira | Jira 問題作成時 |
| Jira キー* | 問題キー | Jira → WF | Jira 問題作成時 |
| Jira の URL * | - | Jira → WF | WF 内の Jira へのユーザークリック可能なリンク |
| - | WF リンク * | WF → Jira | Jira の WF へのユーザークリック可能なリンク |
| 名前 | 概要 | WF → Jira |  |
| 説明 | 説明 | WF → Jira |  |
| ステータス | WF ステータス | WF → Jira | WF ステータス |
| Jira のステータス * | ステータス | Jira → WF | Jira ステータス |
| 予定完了日 | 期日 | WF → Jira | 予定完了日 |
| メモ | コメント | WF ↔ Jira | 双方向コピー |
| ドキュメント | 添付ファイル | WF → Jira | イシューの作成に関する添付ファイルとして、および作成後の新規ドキュメントに関するコメント。 |

\*これらのフィールドは、この統合設定の一部として設定されます。 手順については、[Workfront、Jira、Workfront Fusion での前提条件の設定 &#x200B;](/help/workfront-fusion/create-and-manage-templates/use-jira-scenario-templates.md#configure-prerequisites-in-workfront-jira-and-workfront-fusion) を参照してください。

## Workfront、Jira およびWorkfront Fusion で前提条件を設定します

Jira 統合テンプレートを使用するには、次の設定を実行する必要があります。

* [Jira の設定](#configure-jira)
* [Workfrontの設定](#configure-workfront)
* [Workfront Fusion で接続を設定する](#configure-connections-in-workfront-fusion)

### Jira の設定

これらのモジュールを使用するには、Jira で以下を作成する必要があります。

* システム統合ユーザー
* 3 つの特定のカスタムフィールド

#### Jira でのシステム統合ユーザーの作成

1. Jira で、「システム統合ユーザー」という特定のユーザーを作成します。 このユーザーは、Workfront Fusion でのみ使用する必要があり、人間のユーザーを表すことはできません。 このユーザーの資格情報は、Workfront Fusion Connections で使用されます。

#### Jira での必要なカスタムフィールドの作成

この統合では、接続先の Jira アカウントに 3 つの特定のフィールドが必要です。 これらのフィールドがないと、統合は失敗します

1. Jira で、**設定** （歯車アイコン）に移動し、**作業項目** を選択します。
1. 左側のナビゲーションで「**カスタムフィールド**」を選択します。
1. 画面の右上隅にある「**カスタムフィールドを作成**」をクリックします。
1. 次のフィールドを作成します。

   | フィールド名 | フィールドタイプ |
   |---|---|
   | WF ID | テキストフィールド （1 行） |
   | WF ステータス | テキストフィールド （1 行） |
   | WF リンク | URL フィールド |

   Jira でのリンク作成について詳しくは、フィールドの作成に関する Jira のドキュメントを参照してください。
1. 新しく作成したフィールドを、Jira プロジェクトに関連付けられた画面に追加します。

   Jira の画面について詳しくは、作業項目画面の設定に関する Jira のドキュメントを参照してください。


### Workfrontの設定

これらのモジュールを使用するには、Workfrontで以下を作成する必要があります。

* システム統合ユーザー
* 特定のカスタムフォーム

#### Workfrontでの System Integration ユーザーの作成

1. Workfrontで、System Integration ユーザーを作成します。 このユーザーはWorkfront Fusion でのみ使用され、人間のユーザーを表すものではありません。 このユーザーに割り当てられたタスクは、Workfrontと Jira を同期するシナリオをトリガーします。

   手順については、Workfront ドキュメントの [&#x200B; ユーザーの追加 &#x200B;](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) を参照してください。

#### Workfrontでのカスタムフォームの作成

1. Workfrontで、カスタムフォームの作成を開始します。

   手順については、Workfront ドキュメントの [&#x200B; カスタムフォームの作成 &#x200B;](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) を参照してください。
1. フォームに「**JIRA フィールド**」という名前を付けます。
1. カスタムフォームに次のフィールドを含める：

| フィールド名 | フィールドタイプ |
|---|---|
| Jira キー | 1 行のテキストフィールド |
| Jira URL | 1 行のテキストフィールド |
| Jira ステータス | 1 行のテキストフィールド |

1. Jira とWorkfrontの間でマッピングするフィールドを追加します。
1. カスタムフォームを保存します。

>[!NOTE]
>
>他のユーザーによるこのフォームの編集を制限することをお勧めします。 これを行うには、カスタムフォームに追加されたユーザーが表示アクセス権のみを持つようにします。
>
>手順については、Workfront ドキュメントの [&#x200B; カスタムフォームの共有 &#x200B;](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/manage-custom-forms/share-access-to-a-custom-form) を参照してください。

### Workfront Fusion で接続を設定する

接続を作成するには、Jira およびWorkfrontで System Integration ユーザーを作成している必要があります。

これらの接続を作成する場合は、作成したシステム統合ユーザーの資格情報を使用してください。

必要に応じて、テンプレートの設定の一環として、これらの接続を作成できます。

* Workfrontへの接続を作成する方法については、Workfront モジュールに関する記事の [WorkfrontのWorkfront Fusion への接続 &#x200B;](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#connect-workfront-to-workfront-fusion) を参照してください。
* Jira への接続を作成する手順については、「Jira ソフトウェアモジュール」の [Jira をWorkfront Fusion に接続する &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion) を参照してください。


## シナリオ

Jira 用のすぐに使用できる 8 つのテンプレートは、一般的なワークフローのレプリケートと実装の高速化に役立ちます。 テンプレートは、特定のビジネスニーズに合わせて完全にカスタマイズ可能で、要件の進化に合わせて拡張できます。

すべてのシナリオを実装する必要はありません。 最小限の実装にはシナリオ 1 が必要です。これにより、Workfrontの割り当てから JIRA 問題に対する単一方向の統合が作成されます。  さらにシナリオを追加して、Workfrontと JIRA の間の堅牢性と双方向相互接続を高めることができます。  また、プロジェクトからエピックへの統合や、JIRA からWorkfrontへの問題やタスクなどのケースを処理するためのシナリオを作成することもできます。

これらのテンプレートや拡張機能を使用することは、カスタム設定と見なされるので、サポートや実装にはAdobe Professional ServicesまたはAdobe パートナーを利用することをお勧めします。

* **[Workfrontから Jira へ：Workfrontのタスクまたは問題の割り当てから JIRA の問題を作成](#scenario-1-workfront-to-jira-create-jira-issue-from-workfront-task-or-issue-assignment)**
* [JIRA からWorkfrontへ：JIRA からWorkfrontへ：Jira からWorkfrontに問題やコメントに関する更新を送信します](#scenario-2-jira-to-workfront-send-updates-on-issues-and-comments-back-to-workfront-from-jira)
* [Workfrontから Jira へ：Workfront タスクから JIRA への変更](#scenario-3-workfront-to-jira-changes-to-workfront-task-to-jira-issue)
* [Workfrontから Jira へ：Workfrontの問題が JIRA の問題に変更されました](#scenario-4-workfront-to-jira-changes-to-workfront-issue-to-jira-issue)
* [Workfrontから Jira へ：Workfrontのタスクまたは問題に関する新しいメモを作成する際に、JIRA でコメントを作成します](#scenario-5-workfront-to-jira-create-comment-in-jira-when-new-note-on-workfront-task-or-issue)
* [Workfrontから Jira へ：Workfrontのタスクまたは問題で削除したメモに対して JIRA でコメントを作成します](#scenario-6-workfront-to-jira-create-comment-in-jira-on-deleted-note-on-workfront-task-or-issue)
* [Workfrontから Jira へ：Workfrontのタスクまたは問題に関する新規ドキュメントを作成する際に、JIRA でコメントを作成します](#scenario-7-workfront-to-jira-create-comment-in-jira-when-new-document-on-workfront-task-or-issue)
* [Workfrontから Jira へ：Workfrontのタスクまたは問題で削除されたドキュメントに関するコメントを JIRA で作成します](#scenario-8-workfront-to-jira-create-comment-in-jira-on-deleted-document-on-workfront-task-or-issue)

### 一般パラメーター

これらのテンプレートを設定する際は、次の一般的なパラメーターを使用します。

* **JiraBaseURL**:Jira インスタンスのベース URL です。 例：`https://myjira.atlassian.net/`
* **wfBaseURL**:Workfront インスタンスのベース URL です。  通常：`https://<domain>.my.workfront.com` ここで、`<domain>` は特定のWorkfront ドメイン名です。
* **defaultJIRAReporterID**：問題を発生する JIRA のユーザーの ID。 （例：`557058:5aedf933-2312-40bc-b328-0c21314167f0`）
この ID を取得するには、次のいずれかの操作を行います。
   * JIRA でユーザーのプロファイルをクリックし、ブラウザーで URL を確認します。
（例 `https://myjira.atlassian.net/jira/people/<JiraUserID>`）
   * JIRA インスタンスで次の API 呼び出しを実行して、JIRA の特定のアカウントの ID を取得します。
     `GET /rest/api/3/user/search?query=email@example.com`


### シナリオ 1:Workfrontから Jira へ：Workfrontのタスクまたは問題の割り当てから JIRA の問題を作成します

このシナリオでは、Workfrontのタスクまたは問題が System Integration User に割り当てられると、Jira の問題が作成されます。 シナリオでは、「要約」、「摘要」、「納期」、「WF ステータス」および「WF ID」フィールドに入力します。 イシューが作成されると、このシナリオでは、添付ファイルのリストと、Workfrontの元のタスクまたはイシューに関連するメモの履歴もアップロードされます。

Workfront タスクが割り当てられている場合、Jira のイシューはタスクです。 Workfrontの問題が割り当てられている場合、Jira の問題はバグです。

+++**展開すると、シナリオ 1 を Jira に設定する手順が表示されます :Workfront:Workfrontのタスクまたは問題の割り当てから JIRA の問題を作成します**

#### トリガーモジュールの設定

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**Workfrontから Jira へ：Workfront タスクまたは問題割り当てから JIRA の問題を作成**」テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールで、Webhook の追加を開始します。
1. [Workfront Fusion で接続を設定 &#x200B;](#configure-connections-in-workfront-fusion) で作成したWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Assignment`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | （System Integration ユーザーのWorkfront ID を入力します） |
   | タスク ID | 存在する |  |
   | projectID | が次と等しい | （Webhook で監視する 1 つ以上のプロジェクトの ID を入力します） |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコード生成元**」フィールドで、「新規レコードのみ」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. 続いて [Workfrontと Jira へのテンプレートモジュールの接続 &#x200B;](#connect-template-modules-to-workfront-and-jira) を参照してください。

#### Workfrontと Jira へのテンプレートモジュールの接続

1. **each** Workfront モジュールの「接続」フィールドで、[Workfront Fusion で接続を設定 &#x200B;](#configure-connections-in-workfront-fusion) で作成したWorkfront接続を選択し、「**OK**」をクリックしてそのモジュールへの接続を保存します。
1. **それぞれの** Jira モジュールの「接続」フィールドで、[Workfront Fusion で接続を設定 &#x200B;](#configure-connections-in-workfront-fusion) で作成したWorkfront接続を選択し、「**OK**」をクリックしてそのモジュールへの接続を保存します。
1. [&#x200B; 一般パラメーターモジュールの更新 &#x200B;](#update-the-general-parameters-module) を続行します。

#### 一般パラメーターモジュールの更新

1. テンプレートの 2 番目のモジュール（環境の詳細を設定）で、次の各変数に対して、「**項目を追加**」をクリックし、変数の名前と値を入力します

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | 作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID を入力します。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL を入力します。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL を入力します。 |

1. 続けて [Jira でのカスタムフィールドのマッピング &#x200B;](#map-custom-fields-in-jira) を行います。

<!--#### Map custom fields in Jira. 

Awaiting feedback-->

+++

### シナリオ 2:JIRA からWorkfrontへ：問題に関する更新とコメントを Jira からWorkfrontに送り返す

このシナリオでは、Jira でイシューが作成されたときに、Workfrontのタスクまたはイシューを作成します。

>[!NOTE]
>
>このシナリオでは、Jira 用の OAuth2 接続が必要です。
>Jira に OAuth2 認証を使用するには、[https://developer.atlassian.com/console](https://developer.atlassian.com/console) で OAuth2 アプリケーションを設定する必要があります。 情報と手順については、Jira のドキュメントを参照してください。

+++**展開すると、シナリオ 2:JIRA からWorkfrontへの移行：問題とコメントに関する更新を Jira からWorkfrontに送り返す手順が表示されます**

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **パート 2:JIRA をWorkfrontに：イシューとコメントに関する更新を Jira からWorkfrontに送り返す** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールで、Webhook の追加を開始します。
1. システム統合ユーザーの資格情報を使用する接続を選択するか、システム統合の資格情報を使用して Jira への接続を作成します。

* Jira への接続を作成する手順については、「Jira ソフトウェアモジュール」の [Jira をWorkfront Fusion に接続する &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion) を参照してください。

1. Webhook フィルターの設定

1. 続いて [Jira での Webhook の設定 &#x200B;](#configure-a-webhook-in-jira) を参照してください。

#### Jira での Webhook の設定

1. Jira で、Webhook を作成します。

   手順については、Jira ドキュメントの [Webhook](https://developer.atlassian.com/server/jira/platform/webhooks/) を参照してください。

1. Webhook を設定する際は、次の値を使用します。

   * **JQL**:project = &quot;yourProjectName&quot;（yourProjectName =JIRA プロジェクトの名前）
   * **問題**：作成、更新
   * **コメント**：作成、削除されました


1. 続いて [Workfrontと Jira にテンプレートモジュールを接続する（モジュール 2） &#x200B;](#connect-template-modules-to-workfront-and-jira-module-2)

#### Workfrontと Jira へのテンプレートモジュールの接続（モジュール 2）

1. **each** Workfront モジュールの「接続」フィールドで、[Workfront Fusion で接続を設定 &#x200B;](#configure-connections-in-workfront-fusion) で作成したWorkfront接続を選択し、「**OK**」をクリックしてそのモジュールへの接続を保存します。
1. **それぞれの** Jira モジュールの「接続」フィールドで、[Workfront Fusion で接続を設定 &#x200B;](#configure-connections-in-workfront-fusion) で作成したWorkfront接続を選択し、「**OK**」をクリックしてそのモジュールへの接続を保存します。
   <!--#### Map custom fields-->

+++

### シナリオ 3:Workfrontから Jira へ：Workfront タスクから JIRA への変更

+++**展開して、シナリオ 3: WF から JIRA への変更（タスク）を設定する手順を表示**

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **パート 3:Workfrontから Jira:Workfront タスクから JIRA への変更** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。

1. テンプレートをクリックして、エディターに入ります。
1. このシナリオを所有する組織およびチームを選択します。
1. 最初のモジュールで、Webhook の追加を開始します。
1. 「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Task`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | System Integration ユーザーのWorkfront ID を入力します |
   | projectID | が次と等しい | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |
   | DE: Jira キー | 存在する |  |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコードの起源**」フィールドで、「`Updated record only`」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. **JIRA 変数を設定** モジュールで次の変数を設定し、「**OK**」をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID です。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **each** Workfront モジュールの「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択し、「**OK**」をクリックしてモジュールを保存します。
1. **各** Jira モジュールの「接続」フィールドで、システム統合資格情報を使用する Jira 接続を選択し、「**OK**」をクリックしてモジュールを保存します。

+++

### シナリオ 4:Workfrontから Jira へ：Workfront問題から JIRA 問題への変更

このシナリオでは、Workfrontの問題から、以前に接続された JIRA の問題に更新が送信されます。

+++**展開すると、「シナリオ 4:Workfrontから Jira へ：Workfrontの問題から JIRA への変更」の設定手順が表示されます**

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **シナリオ 4:WF から Jira への変更（イシュー）** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。

1. テンプレートをクリックして、エディターに入ります。
1. このシナリオを所有する組織およびチームを選択します。
1. 最初のモジュールで、Webhook の追加を開始します。
1. 「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Issues`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | System Integration ユーザーのWorkfront ID を入力します |
   | projectID | が次と等しい | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |
   | DE: Jira キー | 存在する |  |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコードの起源**」フィールドで、「`Updated record only`」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. **JIRA 変数を設定** モジュールで次の変数を設定し、「**OK**」をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID です。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **each** Workfront モジュールの「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択し、「**OK**」をクリックしてモジュールを保存します。
1. **各** Jira モジュールの「接続」フィールドで、システム統合資格情報を使用する Jira 接続を選択し、「**OK**」をクリックしてモジュールを保存します。

+++

### シナリオ 5:Workfrontから Jira へ：Workfrontのタスクまたは問題に関する新しいメモを作成する際に、JIRA でコメントを作成します

+++**展開して、「シナリオ 5:Workfrontから Jira へ」の設定手順を表示する：Workfrontのタスクまたは問題に関する新しいメモを作成する際に、JIRA でコメントを作成する**

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **シナリオ 5:WF-to-Jira 新規ノート（タスクとイシュー）** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールで、Webhook の追加を開始します。
1. 「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Note`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. 次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Equals<br><br>Exists | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |
   | または |  |  |
   | projectID<br>AND<br>OpTaskID | Equals<br><br>Exists | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコードの起源**」フィールドで、「`New record only`」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. **変数を設定** モジュールで次の変数を設定し、「**OK**」をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID です。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **each** Workfront モジュールの「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択し、「**OK**」をクリックしてモジュールを保存します。
1. **各** Jira モジュールの「接続」フィールドで、システム統合資格情報を使用する Jira 接続を選択し、「**OK**」をクリックしてモジュールを保存します。

+++

### シナリオ 6:Workfrontから Jira へ：Workfrontのタスクまたは問題で削除されたメモに対して JIRA でコメントを作成する

+++**展開すると、「シナリオ 6:Workfrontから Jira へ」の設定手順が表示されます。「Workfront」タスクまたは問題の削除済みメモに対するコメントを JIRA で作成します**

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **シナリオ 6:WF から Jira へのメモ（タスクとイシュー）を削除** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールで、Webhook の追加を開始します。
1. 「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Note`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. 次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Equals<br><br>Exists | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |
   | または |  |  |
   | projectID<br>AND<br>OpTaskID | Equals<br><br>Exists | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコードの起源**」フィールドで、「`Deleted record only`」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. 2 番目のモジュールで、次の変数を設定し、「**OK**」をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID です。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **each** Workfront モジュールの「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択し、「**OK**」をクリックしてモジュールを保存します。
1. **各** Jira モジュールの「接続」フィールドで、システム統合資格情報を使用する Jira 接続を選択し、「**OK**」をクリックしてモジュールを保存します。

+++

### シナリオ 7:Workfrontから Jira へ：Workfrontのタスクまたは問題に関する新規ドキュメントを作成する際に、JIRA でコメントを作成します

+++**展開すると、「シナリオ 7:Workfrontから Jira へ」:Workfrontのタスクまたは問題に関する新規ドキュメントを作成する際に、JIRA でコメントを作成する** の設定手順が表示されます。

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **シナリオ 7:WF から Jira への新規添付ファイル（タスクと問題）** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールで、Webhook の追加を開始します。
1. 「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Document`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | System Integration ユーザーのWorkfront ID を入力します |
   | projectID | が次と等しい | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |

1. 2 つ目のモジュールで、次の変数を設定します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID です。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコードの起源**」フィールドで、「`New record only`」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. **each** Workfront モジュールの「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択し、「**OK**」をクリックしてモジュールを保存します。
1. **各** Jira モジュールの「接続」フィールドで、システム統合資格情報を使用する Jira 接続を選択し、「**OK**」をクリックしてモジュールを保存します。

+++

### シナリオ 8:Workfrontから Jira へ：Workfrontのタスクまたは問題で削除されたドキュメントに関するコメントを JIRA で作成する

+++**展開して、「シナリオ 8:Workfrontから Jira へ」の設定手順を表示する：「Workfront」タスクまたは問題で削除されたドキュメントに対するコメントを JIRA で作成する**

1. 左側のナビゲーションパネルにある「**テンプレート**」タブ ![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. **シナリオ 8:WF から Jira への添付ファイルの削除（タスクと問題）** テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールで、Webhook の追加を開始します。
1. 「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択します。
1. 「**レコードタイプ**」フィールドで「`Document`」を選択します。
1. 「**状態**」フィールドで「`New state`」を選択します。
1. 次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Equals<br><br>Exists | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |
   | または |  |  |
   | projectID<br>AND<br>OpTaskID | Equals<br><br>Exists | Webhook で監視するプロジェクト（複数可）の ID を入力します。 |

1. **変数を設定** モジュールで、次の変数を設定します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーが Jira に存在しない場合のデフォルトユーザーの ID です。 このユーザー ID は、ユーザーのプロファイルをクリックし、ブラウザーの URL を確認すると見つかります。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先の Jira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. 「**この接続によって行われた更新を除外**」オプションを有効にします。
1. 「**レコードの起源**」フィールドで、「`Deleted record only`」を選択します。
1. 「**保存**」をクリックして Webhook を保存し、「**OK**」をクリックしてトリガーモジュールを保存します。
1. **each** Workfront モジュールの「接続」フィールドで、System Integration 資格情報を使用するWorkfront接続を選択し、「**OK**」をクリックしてモジュールを保存します。
1. **各** Jira モジュールの「接続」フィールドで、システム統合資格情報を使用する Jira 接続を選択し、「**OK**」をクリックしてモジュールを保存します。


+++

