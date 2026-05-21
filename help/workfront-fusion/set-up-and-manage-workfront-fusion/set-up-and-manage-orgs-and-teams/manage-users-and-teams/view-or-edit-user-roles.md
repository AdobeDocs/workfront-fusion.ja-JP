---
title: 組織内のAdobe Workfront Fusion ユーザーの管理
description: 組織内のAdobe Workfront Fusion ユーザーの管理
author: Becky
feature: Workfront Fusion
exl-id: 32c221fa-856b-4921-9fa6-5e60f2aa08cd
TQID: https://experienceleague.adobe.com/XdJ9BXb-lRUhJG-8ThzonprCyEEAIk--hKzVlfHJm4Q
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 25%

---

# ユーザーの役割を表示または編集

Adobe Workfront Fusion管理者は、Workfront Fusion内でユーザーロールを管理できます。


>[!NOTE]
>
>現在Adobe Admin Consoleに移行中の組織の場合、Workfrontでユーザーを管理することはできません（ユーザーの追加または削除）。 移行が完了したら、Adobe Admin Consoleでこれらのアクションを実行できます。

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
     <p>Workfront Fusionの管理者である必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 組織のユーザーの役割の表示または編集

Adobe Workfront Fusion管理者は、組織のユーザーロールを表示および更新できます。

1. Workfront Fusion管理者としてログインしている間、左側のナビゲーションで「**[!UICONTROL すべてのユーザー]**」を選択します。
1. 表示したいユーザーの行で&#x200B;**[!UICONTROL 詳細]**&#x200B;をクリックします。
1. （オプション）組織内のユーザーの役割を更新するには、ユーザーの役割を変更する組織の行の&#x200B;**[!DNL Role]**&#x200B;列にあるドロップダウンをクリックし、新しい役割を選択します。

### 組織の所有者を追加または変更する際の考慮事項

組織には複数の所有者を持つことができます。

所有者ロールにユーザーを割り当てる場合、または所有者ロールからユーザーを割り当てる場合は、次の点を考慮してください。

* 所有者のみが所有者の役割を割り当てることも、現在の所有者に別の役割を割り当てることもできます。
* 管理者のみが所有者にアップグレードできます。
* 所有者が1人しかない場合、その所有者の役割を変更または削除することはできません。
* 所有者が1人しかない場合、その所有者は、組織内に他のユーザーがいる場合は削除できません。
* 管理者に所有者の役割が割り当てられている場合、その管理者は組織内のすべてのチームで自動的に管理者になります。
* 所有者が別の役割に割り当てられている場合、そのユーザーはすべてのチームで自動的にチームメンバーになります。
* 新しいチームが作成されると、すべての所有者がチーム管理者として自動的に割り当てられます。

## チームのユーザーの役割の表示または編集

Adobe Workfront Fusionの管理者とチーム管理者は、ユーザーロールを表示および更新できます。

1. Workfront Fusion管理者としてログインしている間、左側のナビゲーションで「**[!UICONTROL すべてのユーザー]**」を選択します。
1. 表示したいユーザーの行で&#x200B;**[!UICONTROL 詳細]**&#x200B;をクリックします。
1. ユーザーの役割を表示または編集するチームを含む組織の行の&#x200B;**[!DNL Role]**&#x200B;列にある「チーム」アイコンをクリックします。
1. （オプション）チーム内のユーザーの役割を更新するには、ユーザーの役割を変更するチームの行の&#x200B;**[!DNL Role]**&#x200B;列にあるドロップダウンをクリックし、新しい役割を選択します。
