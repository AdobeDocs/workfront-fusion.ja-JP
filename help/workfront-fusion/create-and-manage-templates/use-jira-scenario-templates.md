---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: テンプレートを使用して Adobe Workfront Fusion と Jira を接続
description: これらのテンプレートを使用して、Adobe Workfront FusionとJira間のワークフローを自動化します。
author: Becky
feature: Workfront Fusion
exl-id: 7e30c105-54be-4499-b573-949137e6a5e6
source-git-commit: 72abd9b5aa73d54edd73dc16f7695d2b01cc8624
workflow-type: tm+mt
source-wordcount: '4171'
ht-degree: 4%

---

# テンプレートを使用して Adobe Workfront Fusion と Jira を接続

Adobe workfront Fusionでは、FusionとJira間の共通ワークフローを自動化できるテンプレートを提供しています。

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
   <p>Workfront: Workfront Automation and Integrationが含まれていないSelect パッケージまたはPrime Workfront パッケージがある場合は、Adobe Workfront Fusionを購入する必要があります。</p><p>Jira: Jira Cloudのライセンスが必要です</p>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td> <p>Workfront：ユーザー、カスタムフォーム、カスタムフィールドを作成するための権限。</p> <p>Jira: ユーザーとカスタムフィールドを作成し、画面とwebhookを変更するための権限。</td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 前提条件

### Workfront

* Adobe Developer Consoleのテクニカルアカウントが必要です。

  詳しくは、Adobe ドキュメントの[&#x200B; テクニカルアカウントの設定](https://developer.adobe.com/cloud-storage/guides/getting-started/technical-account-setup)を参照してください。
* Adobe Admin Console製品プロファイル領域のテクニカルアカウントにシステム管理者権限を付与する必要があります。

  詳しくは、「[Adobe Admin Consoleを使用してWorkfrontでシステム管理者を作成する](https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/add-users/create-manage-users/admin-console#create-system-administrators-in-workfront-with-the-adobe-admin-console)」を参照してください。

### Jira

JiraにOAuth2認証を使用している場合（推奨）、[https://developer.atlassian.com/console](https://developer.atlassian.com/console)にOAuth2 アプリケーションを設定する必要があります。 詳細と手順については、「[JiraへのOAuth2接続の作成](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#create-an-oauth2-connection-to-jira)」を参照してください。

<!--

When configuring this application, you will need the following scopes:

* `read:jira-work` 
* `read:jira-user`
* `write:jira-work`

-->

## 前提条件

これらのモジュールは、次の要素を前提としています。

* Workfrontは、マーケティングキャンペーンプロジェクト全体の情報源です
* Jiraは技術チームによって使用されており、Workfrontで開始されたプロジェクトの一部を満たしています。
* すべてのJira ユーザーがWorkfrontにアクセスできるわけではなく、その逆も同様です。
* WorkfrontとJiraはクラウドでホストされています。

## データモデル（フィールドマッピング）


| Workfront | Jira | 方向 | メモ |
|---|---|---|---|
| ObjId | WF ID * | WF→Jira | Jiraのイシュー作成時 |
| Jira キー* | イシューキー | Jira → WF | Jiraのイシュー作成時 |
| Jira URL * | - | Jira → WF | WFからJiraへのユーザークリック可能なリンク |
| - | WF リンク * | WF→Jira | Jiraのユーザーのクリック可能なリンクからWFへ |
| 名前 | 概要 | WF→Jira |  |
| 説明 | 説明 | WF→Jira |  |
| ステータス | WF ステータス | WF→Jira | WF ステータス |
| Jira ステータス * | ステータス | Jira → WF | Jira ステータス |
| 予定完了日 | 期日 | WF→Jira | 予定完了日 |
| メモ | コメント | WF↔Jira | 双方向コピー |
| ドキュメント | 添付ファイル | WF→Jira | 問題作成時の添付ファイルや、作成後の新しいドキュメントのコメントとして使用できます。 |

\*これらのフィールドは、この統合設定の一部として設定されます。 手順については、[Workfront、Jira、およびWorkfront Fusionでの前提条件の設定](/help/workfront-fusion/create-and-manage-templates/use-jira-scenario-templates.md#configure-prerequisites-in-workfront-jira-and-workfront-fusion)を参照してください。

## Workfront、Jira、Workfront Fusionでの前提条件の設定

Jira統合テンプレートを使用するには、次の設定を実行する必要があります。

* [Jiraの設定](#configure-jira)
* [Workfrontの設定](#configure-workfront)
* [Workfront Fusionでの接続の設定](#configure-connections-in-workfront-fusion)

### Jiraの設定

これらのモジュールを使用するには、Jiraで次を作成する必要があります。

* システム統合ユーザー
* 3つの特定のカスタムフィールド

#### Jiraでのシステム統合ユーザーの作成

1. Jiraで、System Integration Userという名前の特定のユーザーを作成します。 このユーザーは、Workfront Fusionでのみ使用する必要があり、人間のユーザーを表すものではありません。 このユーザーの資格情報は、Workfront Fusion接続で使用されます。

#### Jiraで必要なカスタムフィールドを作成する

この統合では、接続先のJira アカウントに3つの特定のフィールドが必要です。 これらのフィールドがないと、統合は失敗します

1. Jiraで、**設定** （歯車アイコン）に移動し、**作業項目**&#x200B;を選択します。
1. 左側のナビゲーションで、**カスタムフィールド**&#x200B;を選択します。
1. 画面の右上隅にある「**カスタムフィールドを作成」をクリックします。**
1. 次のフィールドを作成します。

   | フィールド名 | フィールドタイプ |
   |---|---|
   | WF ID | テキストフィールド（1行） |
   | WF ステータス | テキストフィールド（1行） |
   | WF リンク | URL フィールド |

   Jiraでのリンクの作成について詳しくは、フィールドの作成に関するJira ドキュメントを参照してください。
1. 新しく作成したフィールドをJira プロジェクトに関連付けられた画面に追加します。

   Jiraの画面について詳しくは、作業項目の画面の設定に関するJira ドキュメントを参照してください。


### Workfrontの設定

これらのモジュールを使用するには、Workfrontで以下を作成する必要があります。

* システム統合ユーザー
* 特定のカスタムフォーム

#### WorkfrontでのSystem Integration Userの作成

1. Workfrontで、System Integration ユーザーを作成します。 このユーザーはWorkfront Fusionでのみ使用され、人間のユーザーを表すものではありません。 このユーザーに割り当てられたタスクは、WorkfrontとJiraを同期するシナリオをトリガーします。

   手順については、Workfront ドキュメントの「[&#x200B; ユーザーを追加](https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users)」を参照してください。

#### Workfrontでのカスタムフォームの作成

1. Workfrontでは、カスタムフォームの作成を開始します。

   手順については、Workfront ドキュメントの「[&#x200B; カスタムフォームの作成](https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form)」を参照してください。
1. フォームに「**JIRA Fields**」という名前を付けます。
1. カスタムフォームに次のフィールドを含めます。

| フィールド名 | フィールドタイプ |
|---|---|
| Jira Key | 1 行のテキストフィールド |
| Jira URL | 1 行のテキストフィールド |
| Jira ステータス | 1 行のテキストフィールド |

1. JiraとWorkfront間でマッピングするフィールドを追加します。
1. カスタムフォームを保存します。

>[!NOTE]
>
>他のユーザーによる編集からこのフォームを制限することをお勧めします。 これを実現するには、カスタムフォームに追加したユーザーに表示アクセス権のみを付与します。
>
>手順については、Workfront ドキュメントの「[&#x200B; カスタムフォームを共有する](https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/customize/custom-forms/manage-custom-forms/share-access-to-a-custom-form)」を参照してください。

### Workfront Fusionでの接続の設定

接続を作成する前に、JiraとWorkfrontでシステム統合ユーザーを作成しておく必要があります。

これらの接続を作成する場合は、作成したシステム統合ユーザーの資格情報を必ず使用してください。

必要に応じて、テンプレートの設定の一環として、これらの接続を作成できます。

* Workfrontへの接続を作成する手順については、「[WorkfrontをWorkfront Fusionに接続](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#connect-workfront-to-workfront-fusion)」を参照してください。Workfront モジュール
* Jiraへの接続を作成する手順については、「Jira Software modules」の「[JiraをWorkfront Fusionに接続](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion)」を参照してください。


## シナリオ

すぐに使用できる8つのJira用テンプレートを使用して、一般的なワークフローを複製し、実装を高速化できます。 テンプレートは特定のビジネスニーズに合わせて完全にカスタマイズでき、要件の進化に応じて拡張することができます。

すべてのシナリオを実装する必要はありません。 最小限の実装にはシナリオ 1が必要で、Workfrontでの割り当てからJIRA課題への一方向統合が行われます。  WorkfrontとJIRA間の強固な相互接続と双方向の相互接続を強化するために、さらにシナリオを追加できます。  プロジェクトからエピックへの統合、JIRAの問題からWorkfrontの問題やタスクへの対応など、ケースを処理するシナリオを作成することもできます。

これらのテンプレートまたはこれらのテンプレートの拡張機能を使用する場合は、カスタム設定と見なされます。サポートと実装には、Adobe Professional ServicesまたはAdobe パートナーを使用することをお勧めします。

* **[WorkfrontからJiraへ：Workfront タスクまたはイシューの割り当てからJIRA イシューを作成](#scenario-1-workfront-to-jira-create-jira-issue-from-workfront-task-or-issue-assignment)**
* [JIRAからWorkfrontへ：JIRAからWorkfrontへ：JiraからWorkfrontに対して、問題とコメントに関する更新情報を送り返します](#scenario-2-jira-to-workfront-send-updates-on-issues-and-comments-back-to-workfront-from-jira)
* [WorkfrontからJiraへの移行：Workfront タスクからJIRAへの移行の問題](#scenario-3-workfront-to-jira-changes-to-workfront-task-to-jira-issue)
* [WorkfrontからJiraへの移行：Workfrontの問題からJIRAの問題への変更](#scenario-4-workfront-to-jira-changes-to-workfront-issue-to-jira-issue)
* [WorkfrontからJiraへ：Workfront タスクまたは問題に関する新しいメモをJIRAで作成する](#scenario-5-workfront-to-jira-create-comment-in-jira-when-new-note-on-workfront-task-or-issue)
* [WorkfrontからJiraへ：Workfrontのタスクまたは問題に関する削除されたメモに対して、JIRAでコメントを作成する](#scenario-6-workfront-to-jira-create-comment-in-jira-on-deleted-note-on-workfront-task-or-issue)
* [WorkfrontからJiraへ：新しいドキュメントがWorkfront タスクまたはイシューに追加されたときにJIRAでコメントを作成する](#scenario-7-workfront-to-jira-create-comment-in-jira-when-new-document-on-workfront-task-or-issue)
* [WorkfrontからJiraへ：Workfront タスクまたはイシューの削除済みドキュメントに対してJIRAでコメントを作成する](#scenario-8-workfront-to-jira-create-comment-in-jira-on-deleted-document-on-workfront-task-or-issue)

### 一般パラメーター

これらのテンプレートを設定する場合は、次の一般的なパラメーターを使用します。

* **JiraBaseURL**: Jira インスタンスのベース URL。 例：`https://myjira.atlassian.net/`
* **wfBaseURL**: Workfront インスタンスのベース URL。  通常：`https://<domain>.my.workfront.com` （`<domain>`は特定のWorkfront ドメイン名）。
* **defaultJIRAReporterID**：問題を作成するJIRAのユーザーのID。 （例：`557058:5aedf933-2312-40bc-b328-0c21314167f0`）
このIDは、次のいずれかの操作を行うことで取得できます。
   * JIRAでユーザーのプロファイルをクリックし、ブラウザーでURLを確認します。
（例`https://myjira.atlassian.net/jira/people/<JiraUserID>`）
   * JIRA インスタンスで次のAPI呼び出しを実行して、JIRAの特定のアカウントのIDを取得します。
     `GET /rest/api/3/user/search?query=email@example.com`


### シナリオ 1: WorkfrontからJiraへ：Workfront タスクまたはイシューの割り当てからJIRA イシューを作成する

このシナリオでは、Workfront タスクまたはイシューがSystem Integration Userに割り当てられている場合、Jira イシューが作成されます。 シナリオは、「概要」、「説明」、「期日」、「WF ステータス」および「WF ID」フィールドに入力します。 イシューが作成されると、このシナリオでは、添付ファイルのリストと、元のタスクまたはイシューに関連するメモの履歴もWorkfrontにアップロードされます。

Workfront タスクが割り当てられている場合、Jiraの問題はタスクです。 Workfront イシューが割り当てられている場合、Jira イシューはバグです。

+++**展開すると、シナリオ 1:WorkfrontをJiraに設定する手順が表示されます。Workfront タスクまたはイシューの割り当てからJIRA イシューを作成**

#### トリガーモジュールの設定

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**WorkfrontからJiraへ：Workfront タスクまたはイシュー割り当て** テンプレートからJIRA イシューを作成」をクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. [Workfront Fusion](#configure-connections-in-workfront-fusion)で作成したWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Assignment`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | （System Integration ユーザーのWorkfront IDを入力） |
   | TaskID | 存在する |  |
   | projectID | が次と等しい | （Webhookで監視するプロジェクトのIDを入力します） |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. 「**レコードの発信元**」フィールドで、「新規レコードのみ」を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. [引き続きテンプレートモジュールをWorkfrontとJiraに接続](#connect-template-modules-to-workfront-and-jira)

#### テンプレートモジュールをWorkfrontとJiraに接続する

1. **各** Workfront モジュールの「接続」フィールドで、[Configure connections in Workfront Fusion](#configure-connections-in-workfront-fusion)で作成したWorkfront接続を選択し、**OK**&#x200B;をクリックして、そのモジュールへの接続を保存します。
1. **各** Jira モジュールの「接続」フィールドで、[Configure connections in Workfront Fusion](#configure-connections-in-workfront-fusion)で作成したWorkfront接続を選択し、**OK**&#x200B;をクリックして、そのモジュールへの接続を保存します。
1. 引き続き[一般パラメーターモジュール &#x200B;](#update-the-general-parameters-module)を更新します。

#### 一般パラメーターモジュールの更新

1. テンプレートの2番目のモジュール（環境の詳細を設定）で、次の各変数について、**項目を追加**&#x200B;をクリックし、変数の名前と値を入力します

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | 作成者ユーザーがJiraに存在しない場合は、デフォルトユーザーのIDを入力します。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URLを入力します。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URLを入力します。 |

1. 続行[Jiraでカスタムフィールドをマッピング &#x200B;](#map-custom-fields-in-jira)する

<!--
#### Map custom fields in Jira.

Awaiting feedback
-->

+++

### シナリオ 2: JIRAからWorkfrontへ：JiraからWorkfrontに対して問題とコメントに関する更新を送り返す

このシナリオでは、Jiraでイシューが作成されると、Workfront タスクまたはイシューが作成されます。

>[!NOTE]
>
>このシナリオでは、Jira用のOAuth2接続が必要です。
>JiraにOAuth2認証を使用するには、[https://developer.atlassian.com/console](https://developer.atlassian.com/console)でOAuth2 アプリケーションを設定する必要があります。 詳しくは、Jira ドキュメントを参照してください。

+++**展開すると、シナリオ 2の設定手順が表示されます。JIRAからWorkfrontへ：JiraからWorkfrontに対して、問題とコメントに関する更新を送り返します**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**パート 2: JIRAからWorkfrontへ：問題に関する更新とコメントをJira** テンプレートからWorkfrontに送り返す」をクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. システム統合ユーザーの資格情報を使用する接続を選択するか、システム統合資格情報を使用してJiraへの接続を作成します。

* Jiraへの接続を作成する手順については、「Jira Software modules」の「[JiraをWorkfront Fusionに接続](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion)」を参照してください。

1. Webhook フィルターの設定

1. 続行[JiraでのWebhookの設定](#configure-a-webhook-in-jira)

#### JiraでのWebhookの設定

1. JiraでWebhookを作成します。

   手順については、Jira ドキュメントの[Webhook](https://developer.atlassian.com/server/jira/platform/webhooks/)を参照してください。

1. Webhookを設定する場合は、次の値を使用します。

   * **JQL**: project = &quot;yourProjectName&quot; （ここでyourProjectName = your JIRA プロジェクトの名前）
   * **問題**：作成、更新
   * **コメント**：作成、削除


1. 引き続き[&#x200B; テンプレートモジュールをWorkfrontとJiraに接続（モジュール 2） &#x200B;](#connect-template-modules-to-workfront-and-jira-module-2)

#### テンプレートモジュールをWorkfrontとJiraに接続する（Module 2）

1. **各** Workfront モジュールの「接続」フィールドで、[Configure connections in Workfront Fusion](#configure-connections-in-workfront-fusion)で作成したWorkfront接続を選択し、**OK**&#x200B;をクリックして、そのモジュールへの接続を保存します。
1. **各** Jira モジュールの「接続」フィールドで、[Configure connections in Workfront Fusion](#configure-connections-in-workfront-fusion)で作成したWorkfront接続を選択し、**OK**&#x200B;をクリックして、そのモジュールへの接続を保存します。
   <!--#### Map custom fields-->

+++

### シナリオ 3: WorkfrontからJiraへ：Workfront タスクからJIRAへの変更の問題

+++**展開すると、シナリオ 3の設定手順が表示されます：WF-to-Jiraの変更（タスク）**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**パート 3: WorkfrontからJiraへ：Workfront タスクからJIRA問題** テンプレートへの変更」をクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。

1. テンプレートをクリックしてエディターに入ります。
1. このシナリオを所有する組織とチームを選択します。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. 「接続」フィールドで、System Integration資格情報を使用するWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Task`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | System Integration ユーザーのWorkfront IDを入力します |
   | projectID | が次と等しい | Webhookで監視するプロジェクトのIDを入力します。 |
   | DE: Jira Key | 存在する |  |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. **レコードの発信元** フィールドで、`Updated record only`を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. **JIRA変数を設定** モジュールで、次の変数を設定し、**OK**&#x200B;をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーがJiraに存在しない場合のデフォルトユーザーのIDです。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **各** Workfront モジュールで、Connection フィールドで、System Integration資格情報を使用するWorkfront接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。
1. **各** Jira モジュールで、「接続」フィールドで、システム統合資格情報を使用するJira接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。

+++

### シナリオ 4:WorkfrontからJiraへの移行：Workfrontの問題からJIRAの問題への変更

このシナリオでは、以前に接続したJIRAの問題に対して、Workfrontの問題から更新を送信します。

+++**展開すると、シナリオ 4を設定する手順が表示されます：WorkfrontからJira: Workfrontの問題をJIRAの問題に変更**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**シナリオ 4: WF-to-Jira Changes （Issues）**」テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。

1. テンプレートをクリックしてエディターに入ります。
1. このシナリオを所有する組織とチームを選択します。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. 「接続」フィールドで、System Integration資格情報を使用するWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Issues`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | System Integration ユーザーのWorkfront IDを入力します |
   | projectID | が次と等しい | Webhookで監視するプロジェクトのIDを入力します。 |
   | DE: Jira Key | 存在する |  |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. **レコードの発信元** フィールドで、`Updated record only`を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. **JIRA変数を設定** モジュールで、次の変数を設定し、**OK**&#x200B;をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーがJiraに存在しない場合のデフォルトユーザーのIDです。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **各** Workfront モジュールで、Connection フィールドで、System Integration資格情報を使用するWorkfront接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。
1. **各** Jira モジュールで、「接続」フィールドで、システム統合資格情報を使用するJira接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。

+++

### シナリオ 5: WorkfrontからJiraへ：Workfront タスクまたは問題に関する新しいメモを作成する際に、JIRAでコメントを作成する

+++**展開すると、シナリオ 5を設定する手順が表示されます。WorkfrontからJira: Workfront タスクまたはイシューに関する新しいメモが作成されたときに、JIRAでコメントを作成します**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**シナリオ 5: WF-to-Jiraの新しいメモ（タスクとイシュー）**」テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. 「接続」フィールドで、System Integration資格情報を使用するWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Note`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. 次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | projectID<br>AND<br>TaskID | 次と等しい<br><br>が存在します | Webhookで監視するプロジェクトのIDを入力します。 |
   | または |  |  |
   | projectID<br>AND<br>OpTaskID | 次と等しい<br><br>が存在します | Webhookで監視するプロジェクトのIDを入力します。 |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. **レコードの発信元** フィールドで、`New record only`を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. **変数を設定** モジュールで、次の変数を設定し、**OK**&#x200B;をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーがJiraに存在しない場合のデフォルトユーザーのIDです。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **各** Workfront モジュールで、Connection フィールドで、System Integration資格情報を使用するWorkfront接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。
1. **各** Jira モジュールで、「接続」フィールドで、システム統合資格情報を使用するJira接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。

+++

### シナリオ 6: WorkfrontからJiraへ：Workfront タスクまたは問題に関する削除されたメモに対してJIRAでコメントを作成する

+++**展開すると、シナリオ 6を設定する手順が表示されます：WorkfrontからJiraへ：Workfront タスクまたは問題に関する削除されたメモに対するJIRAでのコメントの作成**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**シナリオ 6: WF-to-Jiraのメモの削除（タスクと問題）**」テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. 「接続」フィールドで、System Integration資格情報を使用するWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Note`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. 次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | projectID<br>AND<br>TaskID | 次と等しい<br><br>が存在します | Webhookで監視するプロジェクトのIDを入力します。 |
   | または |  |  |
   | projectID<br>AND<br>OpTaskID | 次と等しい<br><br>が存在します | Webhookで監視するプロジェクトのIDを入力します。 |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. **レコードの発信元** フィールドで、`Deleted record only`を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. 2番目のモジュールで、次の変数を設定し、**OK**&#x200B;をクリックしてモジュールを保存します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーがJiraに存在しない場合のデフォルトユーザーのIDです。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. **各** Workfront モジュールで、Connection フィールドで、System Integration資格情報を使用するWorkfront接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。
1. **各** Jira モジュールで、「接続」フィールドで、システム統合資格情報を使用するJira接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。

+++

### シナリオ 7: WorkfrontからJiraへ：Workfront タスクまたは問題に関する新しいドキュメントを作成する際に、JIRAでコメントを作成する

+++**展開すると、シナリオ 7を設定する手順が表示されます：WorkfrontからJira: Workfront タスクまたはイシューに対する新しいドキュメントの場合は、JIRAでコメントを作成します**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**シナリオ 7: WF-to-Jiraの新しい添付ファイル（タスクとイシュー）**」テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. 「接続」フィールドで、System Integration資格情報を使用するWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Document`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. **And** オプションを使用して、次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | assignedToID | が次と等しい | System Integration ユーザーのWorkfront IDを入力します |
   | projectID | が次と等しい | Webhookで監視するプロジェクトのIDを入力します。 |

1. 2つ目のモジュールで、次の変数を設定します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーがJiraに存在しない場合のデフォルトユーザーのIDです。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. **レコードの発信元** フィールドで、`New record only`を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. **各** Workfront モジュールで、Connection フィールドで、System Integration資格情報を使用するWorkfront接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。
1. **各** Jira モジュールで、「接続」フィールドで、システム統合資格情報を使用するJira接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。

+++

### シナリオ 8: WorkfrontからJiraへ：Workfront タスクまたは問題で削除されたドキュメントに対してJIRAでコメントを作成する

+++**展開すると、シナリオ 8を設定する手順が表示されます：WorkfrontからJiraへ：Workfront タスクまたはイシューの削除済みドキュメントに対するJIRAでのコメントの作成**

1. 左側のナビゲーションパネルで「**テンプレート**」タブ「![&#x200B; テンプレート」アイコン &#x200B;](assets/templates-icon.png)」をクリックします。
1. 画面の左上隅付近にある検索バーを使用して、テンプレートを検索します。 テンプレート名または含まれるアプリケーションで検索できます。
1. 「**シナリオ 8: WF-to-Jiraの添付ファイルの削除（タスクとイシュー）**」テンプレートをクリックします。

   テンプレートのビューが開き、情報とデータフローのアニメーションが表示されます。
1. 最初のモジュールでは、Webhookの追加を開始します。
1. 「接続」フィールドで、System Integration資格情報を使用するWorkfront接続を選択します。
1. **レコードタイプ** フィールドで、`Document`を選択します。
1. **状態** フィールドで、`New state`を選択します。
1. 次の操作でフィルターを設定します。

   | フィールド | 演算子 | 値 |
   |---|---|---|
   | projectID<br>AND<br>TaskID | 次と等しい<br><br>が存在します | Webhookで監視するプロジェクトのIDを入力します。 |
   | または |  |  |
   | projectID<br>AND<br>OpTaskID | 次と等しい<br><br>が存在します | Webhookで監視するプロジェクトのIDを入力します。 |

1. **Set variables** モジュールで、次の変数を設定します。

   | 変数名 | 変数値 |
   |---|---|
   | defaultJiraReporterID | これは、作成者ユーザーがJiraに存在しない場合のデフォルトユーザーのIDです。 このユーザーIDは、ユーザーのプロファイルをクリックし、ブラウザーのURLを確認することで確認できます。 例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 接続先のJira アカウントのベース URL。 |
   | wfBaseURL | 接続先のWorkfront アカウントのベース URL。 |

1. この接続&#x200B;**オプションによって行われた**&#x200B;除外の更新を有効にします。
1. **レコードの発信元** フィールドで、`Deleted record only`を選択します。
1. **Save**&#x200B;をクリックしてWebhookを保存し、**OK**&#x200B;をクリックしてトリガーモジュールを保存します。
1. **各** Workfront モジュールで、Connection フィールドで、System Integration資格情報を使用するWorkfront接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。
1. **各** Jira モジュールで、「接続」フィールドで、システム統合資格情報を使用するJira接続を選択し、**OK**&#x200B;をクリックしてモジュールを保存します。


+++
