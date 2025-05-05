---
title: Publishと共有テンプレート
description: テンプレートを作成すると、すべてのチームメンバーがテンプレートを使用できるようになります。テンプレートをチーム外のユーザーと共有する場合は、まずテンプレートを公開する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 99a1227d-bff9-479f-b8b9-efcf7cea3708
source-git-commit: 7acc27ab2ce80b964b7f9fbb302816aa75964ab5
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 33%

---

# Publishと共有テンプレート

テンプレートを作成すると、すべてのチームメンバーがテンプレートを使用できるようになります。テンプレートをチーム外のユーザーと共有する場合は、まずテンプレートを公開する必要があります。

テンプレートの作成について詳しくは、[ 新しいテンプレートの作成 ](/help/workfront-fusion/create-and-manage-templates/create-new-fusion-templates.md) を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

テンプレートは、公開または共有する前に作成する必要があります。

## テンプレートのPublish

1. 左側のナビゲーションパネルで、「**[!UICONTROL Templates]**」をクリックします。
1. 「**[!UICONTROL Team templates]**」タブをクリックします。
1. 公開するテンプレートの行で **0&rbrace;Publish&rbrace; をクリックします。**

   または


   公開するテンプレートの名前をクリックし、画面の右上隅にある「**[!UICONTROL Publish]**」ボタンをクリックします。

## [!DNL Workfront Fusion] テンプレートを共有

テンプレートを公開した後には、それを共有できます。

1. 左側のナビゲーションパネルで、「**[!UICONTROL Templates]**」をクリックします。
1. 「**[!UICONTROL Team templates]**」タブをクリックします。
1. 共有するテンプレートの名前をクリックして、テンプレートを開きます。
1. **公開済み** タブをクリックして、そのバージョンのテンプレートを開きます。
1. （条件付き）共有可能なリンクが必要な場合は、[**[!UICONTROL Share public link]**] をクリックします。

   >[!NOTE]
   >
   >このリンクを共有できますが、テンプレート自体は「[!UICONTROL Team templates]」タブに残り、公開されません。

1. （条件付き）テンプレートを公開する場合は、「**[!UICONTROL Request Approval]**」をクリックして管理者に送信し、承認を得ます。

   >[!NOTE]
   >
   >* テンプレートが承認されると、公開されます。 組織やチームに関係なく、すべての [!DNL Workfront Fusion] ユーザーの「[!UICONTROL Public templates]」タブに [!UICONTROL Public templates] が表示されます。
   >* メールでレビューするテンプレートの受信に関する通知は、管理者には送信されません。承認が急を要する場合は、管理者に直接お問い合わせください。


## テンプレートのステータス

Fusion は、様々なバージョン（プライベート、公開済み、承認済み）をテンプレートのページの様々なタブに保存します。

以下のステータスを使用できます。

* **[!UICONTROL Private]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。
* **[!UICONTROL Published]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。 承認用に公開済みのテンプレートを送信したり、共有可能なリンクをコピーしたりすることができます。
* **[!UICONTROL Approved]**：このテンプレートは、すべてのWorkfront Fusion ユーザーに対して「[!UICONTROL Public templates]」タブに表示されます。 画面の右上隅にある「[!UICONTROL Options]」をクリックして、共有可能なリンクをコピーできます。

<!--You can also check the status from the [!UICONTROL Team templates] tab. If a template is published, it will have an icon to the right of the template name.

* **Eye icon**: The template is published, it is visible only for the team, and the approval request was not sent.
* **Yellow checkmark icon**: The template is published, it is visible only for the team, and the approval request was sent.
* **Green checkmark icon**: The template is published and public. It is visible for any Workfront Fusion user in the [!UICONTROL Public templates] tab. It is also still visible in the [!UICONTROL Team templates] tab, and the template author or their team member can still edit it.

Templates without icons have [!UICONTROL Private] status. They are not published and are visible only to the team.
-->
