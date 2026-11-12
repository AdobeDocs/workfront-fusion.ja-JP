---
title: チームの役割の表示と管理
description: 各チームには「役割」タブがあり、チームの役割を表示したり、独自の役割を作成したり、各役割に含まれる権限を選択したり、役割を更新または削除したりできます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: a3a6922afd713cd002cdf472c7ef62c1855b80d9
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 11%
---
# チームの役割の表示と管理

チームで利用可能な役割を表示したり、独自の役割を作成したり、各役割に含まれる権限を選択したりできます。 また、役割を更新および削除することもできます。

カスタム役割には、次のような利点があります。

* 各チームメンバーは、担当の業務に必要なアクセス権のみを有しているため、重要なシナリオを誤って変更するリスクを軽減できます。
* カスタム役割は、事前に定義された役割にチームを組み込むのではなく、組織の働き方により適しています。
* サポートに連絡しなくても、自分でアクセスを管理できます。

組織、チーム、および定義済みのチームの役割の概要については、[組織とチームの概要](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md)を参照してください。 定義済みの役割に含まれる権限については、[組織とチームの役割](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)を参照してください。

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td> 
     <p>チームに<b>[!UICONTROL Manage members]</b>権限が必要です。 定義済みの役割では、この権限はチーム管理者と組織所有者の役割に含まれます。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 各チームの役割を管理する担当者

チームの&#x200B;**[!UICONTROL メンバーの管理]**&#x200B;権限を持つユーザーは誰でも、そのチームの役割を作成、更新、削除、割り当てることができます。

* 組織の所有者は、すべてのチームで役割を作成および管理できます。
* 組織管理者は、自分がメンバーであり、**[!UICONTROL メンバーを管理]**&#x200B;権限を持つチームでのみ役割を管理できます。
* チーム管理者は、チーム内の役割を管理できます。

## 役割の作成または編集

1. Fusionで、左側のナビゲーションで「**チームの概要**」をクリックします。
1. （条件付き）役割を表示するチームのページに参加していない場合は、ページの上部にある「**チーム**」ドロップダウンをクリックし、適切なチームを選択します。
1. 「**[!UICONTROL 役割]**」タブを開きます。

   このタブには、定義済みの役割を含め、チームで使用可能な役割が一覧表示されます。 役割ごとに、役割の名前と「権限なし」、「メンバー」、「カスタム ・ 19権限」などの権限の概要がリストに表示されます。

1. 役割を作成するには、**[!UICONTROL 役割を作成]**&#x200B;をクリックします。

   または

   役割を編集するには、編集する役割の行にある&#x200B;**[!UICONTROL 編集]**&#x200B;をクリックします。

   <!-- BECKY CHECK ME: The Edit button is available for the predefined roles as well as custom roles. Confirm the title of the edit page, whether you can rename the predefined roles, and what happens to users who already have the role. -->

1. **[!UICONTROL 役割の名前]** フィールドに役割の名前を入力します。
1. **[!UICONTROL 役割テンプレート]** ドロップダウンで、開始するテンプレートを選択します。

   テンプレートは、役割の初期権限を設定します。 デフォルトのテンプレートは&#x200B;**[!UICONTROL Viewer]**&#x200B;です。

1. **[!UICONTROL スコープ付き権限]**&#x200B;領域で、役割に含める権限を選択します。

   権限は、**[!UICONTROL Automations]**、**[!UICONTROL Connections]**、**[!UICONTROL Team]**&#x200B;などの領域ごとにグループ化されます。 各領域について、次のいずれかを実行できます。

   * エリア内のすべての権限を一度に設定するには、エリア名の横にある&#x200B;**[!UICONTROL アクセスなし]**、**[!UICONTROL 表示のみ]**、または&#x200B;**[!UICONTROL フルアクセス]**&#x200B;をクリックします。
   * 特定の権限を選択するには、各権限のチェックボックスをオンまたはオフにします。

   権限のリストについては、この記事の役割[&#128279;](#permissions-that-you-can-include-in-a-role)に含めることができる権限を参照してください。

   <!-- BECKY CHECK ME: Confirm the options in the Role template dropdown and what each one selects. Confirm exactly what No access, View only, and Full access select in each area (in the screenshot, View only selects the view permissions). Confirm whether there is a Description field, and whether there are areas below Team on the page (the screenshots end at Team). -->

1. 「**[!UICONTROL 保存]**」をクリックします。 保存せずにページを閉じるには、**[!UICONTROL キャンセル]**&#x200B;をクリックします。
1. （オプション）役割を削除するには、「**[!UICONTROL 役割]**」タブの役割の行にある「**[!UICONTROL 削除]**」をクリックします。

   <!-- BECKY CHECK ME: Confirm why the Delete button is unavailable (dimmed) for some roles, such as Team Operator, Team Member, and Team Admin in the screenshot, whether there is a confirmation prompt, and what happens to users who have the role. Update this step and add a note, if needed. -->

作成した役割は、チーム内で使用できます。 チームメンバーに割り当てることができます。

### 役割に含めることができる権限

<table style="table-layout:auto">
 <col>
 <col>
 <thead>
  <tr>
   <th>領域</th>
   <th>権限</th>
  </tr>
 </thead>
 <tbody>
 <tr>
   <td role="rowheader">[!UICONTROL Automations]</td>
   <td>リストの表示、詳細の表示、実行履歴の表示、通知の管理、統計のリセット、1回実行、スケジュールの編集、アクティブ化、非アクティブ化、作成、編集、公開、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Incomplete executions]</td>
   <td>表示、管理</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Webhook]</td>
   <td>表示、キューの表示、作成、編集、キューの管理、優先度の変更、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 接続]</td>
   <td>表示、作成、編集、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Keys]</td>
   <td>表示、作成、編集、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL データ ストア &#x200B;]</td>
   <td>リストの表示、レコードの参照、作成、編集、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL データ構造]</td>
   <td>表示、作成、編集、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Templates]</td>
   <td>リストの表示、詳細の表示、作成、編集、削除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Team]</td>
   <td>チームの表示、チーム設定の編集、メンバーの管理、チームの削除</td>
  </tr>
 </tbody>
</table>

<!-- BECKY CHECK ME: Confirm that this list is complete, and add a description of what each permission allows, if needed. The list is taken from the Create role page, which may have more areas below Team. -->

## 役割を別のチームに複製

あるチームの役割を別のチームにコピーして、各チームで同じ役割を再作成する必要がないようにすることができます。

1. この記事の「[役割の作成または編集](#create-or-edit-a-role)」の説明に従って、チームの&#x200B;**[!UICONTROL 役割]** タブを開きます。
1. 「**[!UICONTROL チームに複製]**」をクリックします。

   **[!UICONTROL 別のチームへの役割の複製]** ページが開きます。

1. 「**[!UICONTROL ターゲットチーム]**」ドロップダウンで、役割を複製するチームを選択します。

   現在のチームの役割を一覧表示するテーブルが表示されます。

1. テーブル内の各ロールについて、以下を確認して設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Source role]</td> 
      <td> <p>現在のチームの役割とその権限の概要。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Action]</td> 
      <td> <p>役割をどうするか。 例えば、<b>[!UICONTROL Copy into existing role]</b>は、ソースロールの権限を、ターゲットチームに既に存在するロールにコピーします。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Target]</td> 
      <td> <p>ソースの役割がコピーされるターゲットチームの役割。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL の変更]</td> 
      <td> <p>ターゲットの役割とソースの役割が異なるかどうか。 例えば、<b>[!UICONTROL Already in sync]</b>は、ターゲットの役割がソースの役割と同じ権限を既に持っていることを意味します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Users]</td> 
      <td> <p>役割を持つユーザーに関する情報。 例えば、<b>[!UICONTROL No matching users]</b>は、含めるユーザーがないことを意味します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Status]</td> 
      <td> <p>複製した後の役割の結果。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL クローン]**」をクリックします。 複製せずにページを閉じるには、**[!UICONTROL キャンセル]**&#x200B;をクリックします。

<!-- BECKY CHECK ME: The screenshot shows the Clone roles to another team page after a target team is selected. Confirm the options in the Action dropdown (for example, whether you can create a new role in the target team), the options in the Target dropdown, what the checkbox in the Users column does (for example, whether it also assigns the role to matching users in the target team) and what "matching users" means, what the Changes column shows when the roles differ, and what the Status column shows before and after you clone. -->

<!-- BECKY CHECK ME: Confirm whether the Target team dropdown lists all teams or only the teams that you can manage, and whether the Clone to team button is visible to everyone who can manage roles. -->

## ユーザーへの役割の割り当て

カスタムの役割は、定義済みの役割を割り当てるのと同じように割り当てます。 手順については、[&#x200B; チームへのユーザーの追加](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md)および[&#x200B; ユーザーの役割の表示または編集](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md#view-or-edit-user-roles-for-a-team)を参照してください。

<!-- BECKY CHECK ME: Confirm that custom roles appear in the role dropdowns in both of these procedures. -->

## 考慮事項

* 組織の権限のカスケード： すべてのチームでアクションを実行するアクセス権を与えるには、チームの役割を作成する代わりに、組織の役割を割り当てます。 詳しくは、[組織とチームの役割](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)を参照してください。
* 作成した役割は1つのチームに属します。

<!-- BECKY CHECK ME: The Slack thread says that defining a role that is available in all teams was out of scope for the initial release. Confirm that a role belongs to a single team, and that you clone it to use it in another team. -->
