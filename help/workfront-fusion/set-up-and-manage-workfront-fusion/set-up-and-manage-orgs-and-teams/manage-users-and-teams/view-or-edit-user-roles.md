---
title: 組織内のAdobe Workfront Fusion ユーザーの管理
description: 組織内のAdobe Workfront Fusion ユーザーの管理
author: Becky
feature: Workfront Fusion
exl-id: 32c221fa-856b-4921-9fa6-5e60f2aa08cd
source-git-commit: 88d7a92a4b117d10ab114e32ab5e61f03bc5a846
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 35%

---

# ユーザーの役割を表示または編集

Adobe Workfront Fusion 管理者は、Workfront Fusion 内のユーザーの役割を管理できます。


>[!NOTE]
>
>現在、組織がWorkfrontへの移行プロセスを行っている場合、Adobe Admin Consoleでユーザーを管理（ユーザーの追加または削除）することはできません。 移行が完了したら、Adobe Admin Consoleでこれらの操作を実行できます。

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 組織のユーザーの役割の表示または編集

Adobe Workfront Fusion 管理者は、組織のユーザーの役割を表示および更新できます。

1. Workfront Fusion 管理者としてログインし、左側のナビゲーションで **[!UICONTROL すべてのユーザー]** を選択します。
1. 表示したいユーザーの行で&#x200B;**[!UICONTROL 詳細]**&#x200B;をクリックします。
1. （オプション）組織内のユーザーの役割を更新するには、組織の行にある「**[!DNL Role]**」列のドロップダウンをクリックして、ユーザーの役割を変更し、新しい役割を選択します。

<!--

### Considerations when adding or changing organization Owners

Your organization can have more than one Owner. 

When assigning a user to or from an Owner role, consider the following. 

* Only an Owner can assign the Owner role, or assign another role to a current Owner.
* Only Admins can be upgraded to Owner.
* If there is only one Owner, that Owner role cannot be changed or removed.
* If there is only one Owner, that Owner cannot be deleted if there are other users in the organization.
* When an Admin is assigned an Owner role, they automatically become Admin in all teams within the org.
* When an Owner is assigned to another role, that user automatically becomes a Team Member in all teams.
* When a new team is created, all Owners are automatically assigned as Team Admins.

-->

## チームのユーザーの役割の表示または編集

Adobe Workfront Fusion 管理者とチーム管理者は、ユーザーの役割を表示および更新できます。

1. Workfront Fusion 管理者としてログインし、左側のナビゲーションで **[!UICONTROL すべてのユーザー]** を選択します。
1. 表示したいユーザーの行で&#x200B;**[!UICONTROL 詳細]**&#x200B;をクリックします。
1. ユーザーの役割を表示または編集するチームを含む組織の行の **[!DNL Role]** 列にある「チーム」アイコンをクリックします。
1. （オプション）チーム内のユーザーの役割を更新するには、チームの行にある「**[!DNL Role]**」列のドロップダウンをクリックして、ユーザーの役割を変更し、新しい役割を選択します。
