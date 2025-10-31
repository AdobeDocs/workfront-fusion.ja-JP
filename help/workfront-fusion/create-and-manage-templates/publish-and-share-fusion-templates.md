---
title: テンプレートの公開と共有
description: テンプレートを作成すると、すべてのチームメンバーがテンプレートを使用できるようになります。テンプレートをチーム外のユーザーと共有する場合は、まずテンプレートを公開する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 99a1227d-bff9-479f-b8b9-efcf7cea3708
source-git-commit: 3a977d805c10fda7209b0634c6e32e818a980691
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 49%

---

# テンプレートの公開と共有

テンプレートを作成すると、すべてのチームメンバーがテンプレートを使用できるようになります。テンプレートをチーム外のユーザーと共有する場合は、まずテンプレートを公開する必要があります。

テンプレートの作成について詳しくは、[&#x200B; 新しいテンプレートの作成 &#x200B;](/help/workfront-fusion/create-and-manage-templates/create-new-fusion-templates.md) を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++

## 前提条件

テンプレートは、公開または共有する前に作成する必要があります。

## テンプレートの公開

1. 左側のナビゲーションパネルで、**[!UICONTROL テンプレート]**&#x200B;をクリックします。
1. 「**[!UICONTROL チームテンプレート]**」タブをクリックします。
1. 公開するテンプレートの行で「**公開**」をクリックします。

   または


   公開するテンプレートの名前をクリックし、画面の右上隅にある **[!UICONTROL 公開]** ボタンをクリックします。

## Workfront Fusion テンプレートの共有

テンプレートを公開した後には、それを共有できます。

1. 左側のナビゲーションパネルで、**[!UICONTROL テンプレート]**&#x200B;をクリックします。
1. 「**[!UICONTROL チームテンプレート]**」タブをクリックします。
1. 共有するテンプレートの名前をクリックして、テンプレートを開きます。
1. **公開済み** タブをクリックして、そのバージョンのテンプレートを開きます。
1. （条件付き）共有可能なリンクが必要な場合は、「**[!UICONTROL 公開リンクを共有]**」をクリックします。

   >[!NOTE]
   >
   >このリンクを共有できますが、テンプレート自体は [!UICONTROL &#x200B; チームテンプレート &#x200B;] タブに残り、公開されません。

1. （条件付き）テンプレートを公開したい場合は、「**[!UICONTROL 承認をリクエスト]**」をクリックして、承認を得るために管理者にテンプレートを送信します。

   >[!NOTE]
   >
   >* テンプレートが承認されると、公開されます。 [!UICONTROL &#x200B; 公開テンプレート &#x200B;] は、組織やチームに関係なく、すべてのWorkfront Fusion ユーザー用の「[!UICONTROL &#x200B; 公開テンプレート &#x200B;]」タブに表示されます。
   >* メールでレビューするテンプレートの受信に関する通知は、管理者には送信されません。承認が急を要する場合は、管理者に直接お問い合わせください。


## テンプレートのステータス

Fusion は、様々なバージョン（プライベート、公開済み、承認済み）をテンプレートのページの様々なタブに保存します。

以下のステータスを使用できます。

* **[!UICONTROL 非公開]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。
* **[!UICONTROL 公開済み]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。承認用に公開済みのテンプレートを送信したり、共有可能なリンクをコピーしたりすることができます。
* **[!UICONTROL 承認済み]**：このテンプレートは、すべての Workfront Fusion ユーザーの「[!UICONTROL 公開テンプレート]」タブに表示されます。「[!UICONTROL オプション]」をクリックして、共有可能なリンクをコピーすることができます。

<!--You can also check the status from the [!UICONTROL Team templates] tab. If a template is published, it will have an icon to the right of the template name.

* **Eye icon**: The template is published, it is visible only for the team, and the approval request was not sent.
* **Yellow checkmark icon**: The template is published, it is visible only for the team, and the approval request was sent.
* **Green checkmark icon**: The template is published and public. It is visible for any Workfront Fusion user in the [!UICONTROL Public templates] tab. It is also still visible in the [!UICONTROL Team templates] tab, and the template author or their team member can still edit it.

Templates without icons have [!UICONTROL Private] status. They are not published and are visible only to the team.
-->
