---
title: Fusionの組織とチームの概要
description: Adobe Workfront Fusion の組織とチームの機能を使用すると、企業は Fusion 内のシナリオや他の機能へのアクセスを制御できます。
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
TQID: 'https://experienceleague.adobe.com/rWg9TitUlX092UIFTY1LUZsR7UlmWwE5dItl6wnlBMA'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: f9cdbcf936fc6b022f6513f47b9b377424731419
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 39%
---
# Adobe Workfront Fusion組織とチームの概要

Adobe Workfront Fusion の組織とチームの機能を使用すると、企業は Fusion 内のシナリオや他の機能へのアクセスを制御できます。

Adobe Workfront Fusion最大の事業体です。 たとえば、Fusion組織は、企業全体のFusion アカウントを表すことができます。

チームは、組織内の小さなグループで、シナリオ、接続、テンプレートなどのFusion リソースを共有します。

チームの作成手順については、[ チームの作成](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/create-a-team.md)を参照してください。

## 組織

Workfront Fusion ユーザーは組織に属しています。

ユーザーをチームに追加する前に、ユーザーを組織に追加する必要があります。

### 組織リソース

次のリソースはFusion組織全体に影響を与えるため、組織レベルで所有および処理されます。

* **ワーカープール：**: ワーカープールは、特定の組織に特化したWorkfront Fusion処理リソースの量です。

  詳しくは、[ ワーカープール ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/worker-pools.md)を参照してください。

* **操作**: Adobe Workfront Fusionでの操作は、モジュールによって実行されるタスクです。

  詳しくは、[操作](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md)を参照してください。

### 組織の役割

ユーザーには、組織内で次のいずれかの役割があります。

* **[!UICONTROL 所有者]**：所有者は、組織で使用可能なすべての権限を持っています。
* **[!UICONTROL 管理者]**：組織がAdobe Identity Management System （IMS）に対して有効になっている場合、またはIMS以外の組織の新規ユーザーを招待できる場合、管理者はAdobe Admin Consoleでユーザーを管理できます。 テンプレートを承認することもできます。
* **[!UICONTROL メンバー]**: メンバーはWorkfront Fusionを使用できますが、組織を変更することはできません。
* **[!UICONTROL 会計士]**：会計士は、組織ダッシュボードでライセンス情報を確認できますが、アクションを実行することはできません。
* **[!UICONTROL アプリ開発者]**：この役割の機能は現在使用できません。近い将来に使用可能になる予定です。 現時点では、この役割にユーザーを割り当てることはお勧めしません。

各組織の役割でユーザーが使用できる特定のアクションについて詳しくは、[組織とチームの役割](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)を参照してください。

## チーム

チームとは、特定のリソースへのアクセスを共有するユーザーのグループです。 これらのリソースには以下が含まれます。

* シナリオ
* 接続
* Webhook
* キー
* データストア
* データ構造
* メール通知の設定

>[!NOTE]
>
>チームはリソースを共有するため、単一のメンバーだけで済む場合が多くあります。 たとえば、トレーニング中のユーザーは、個々のWorkfrontアカウントとのつながりを構築できます。 また、Workfrontの個々のアカウントには、チームメンバー全員がアクセスできます。 この場合、ユーザーはトレーニングチームの唯一のメンバーであることをお勧めします。

組織には必要な数のチームが含まれ、ユーザーは 1 つ以上のチームに属する場合があります。

ユーザーは、左側のナビゲーションパネルにあるドロップダウンリストからチームを選択できます。 ユーザー自身が属するチームのみが表示されます。 チームを選択すると、ユーザーはそのチームのリソースにアクセスできます。

### チームの役割

ユーザーは、各チームで次の役割のいずれかを持ちます。

* **[!UICONTROL チーム管理者]**：管理者は、チームメンバーの役割を追加、削除、または変更できます。 また、他のチームの役割が利用できるアクションを実行することもできます。
* **[!UICONTROL チームメンバー]**：チームメンバーの役割として、ユーザーはシナリオを作成および実行できます。
* **[!UICONTROL チームモニタリング]**：[!UICONTROL モニタリング]の役割を使用すると、ユーザーはシナリオの実行情報にアクセスできますが、シナリオを設計したり、「アクティブ」ステータスを変更したりすることはできません。
* **[!UICONTROL チームオペレーター]**：[!UICONTROL オペレーター]の役割を使用すると、ユーザーは実行データを表示し、シナリオの「アクティブ」ステータスを変更できます。
* **[!UICONTROL チーム制限メンバー]**：この役割の機能は現在使用できません。近い将来に使用可能になる予定です。 現時点では、この役割にユーザーを割り当てることはお勧めしません。

各チームの役割でユーザーが使用できる特定のアクションについて詳しくは、[組織とチームの役割](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)を参照してください。

### カスタムチームの役割

<!-- BECKY CHECK ME: The source material (the Slack announcement) says flexible permissions are live in QA and for internal customers, with a limited pilot with paid customers next, then general availability. Confirm availability at the 2026-11-12 release before publishing, and whether this section should say that the feature is available only to some organizations. -->

定義済みのチームの役割に加えて、各チームには&#x200B;**[!UICONTROL 役割]** タブがあり、独自の役割を作成できます。 役割を作成、更新、削除し、各役割に含まれる権限を正確に選択できます。 固定された役割セットに限定されなくなりました。

手順については、[ チームの役割の表示と管理](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-and-manage-team-roles.md)を参照してください。

カスタム役割を使用すると、次のことが可能になります。

* 各従業員に必要なアクセス権のみを付与し、重要なシナリオを誤って変更するリスクを低減します。
* あらかじめ定義された役割にチームを組み込むのではなく、組織の働き方に合わせてアクセス権を設定できます。
* サポートに連絡することなく、自分でアクセスを管理。

チームの&#x200B;**[!UICONTROL メンバーの管理]**&#x200B;権限を持つユーザーは誰でも、そのチームの役割を作成、更新、削除、割り当てることができます。 定義済みの役割では、この権限はチーム管理者と組織所有者の役割に含まれます。

* 組織の所有者は、すべてのチームで役割を作成および管理できます。
* 組織管理者は、自分がメンバーであり、**[!UICONTROL メンバーを管理]**&#x200B;権限を持つチームでのみ役割を管理できます。
* チーム管理者は、チーム内の役割を管理できます。

<!-- BECKY CHECK ME: The source does not describe the steps in the Roles tab, the list of permissions that you can choose from, or whether you can edit or delete the predefined roles. Add the steps and permissions list once confirmed. Also confirm that Team Admins can manage roles (the source says the Manage members permission was previously given to Team Admin and Org Owner roles, and that team and org admins can create roles only in the teams where they are admins). -->
