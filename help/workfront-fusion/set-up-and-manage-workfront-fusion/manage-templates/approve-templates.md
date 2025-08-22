---
content-type: reference
title: テンプレートを承認または却下
description: この記事では、Fusion テンプレートを承認または却下する方法について説明します。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: dafecd8b-96e5-46da-9ab6-15f0bc9b52a4
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 41%

---

# 「公開」タブ用のテンプレートを承認または却下

Adobe Workfront Fusion テンプレートは、様々なワークフローを自動化および効率化するために設計された事前定義済みのシナリオです。 これらのテンプレートを使用すると、最初からすべてを構築する必要なく、統合と自動化をすばやく設定できます。

管理者の場合は、「公開テンプレート」タブで、特定のテンプレートを組織全体で共有するかどうかを選択できます。

ユーザーは、承認用に作成したテンプレートを送信して、公開テンプレートページで共有できます。<!--do the have to be requested or can an admin just choose to approve?-->

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">Adobe Workfront プラン</td>
      <td><p>任意</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">Adobe Workfront プラン</td>
      <td><p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p></td>
    </tr>
    <tr>
      <td role="rowheader">Adobe Workfront Fusion ライセンス**</td>
      <td>
        <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
        <p>または</p>
        <p>レガシー：任意</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">製品</td>
      <td>
        <p>新規：</p>
        <ul>
          <li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：Adobe Workfront Fusion は、組織で購入する必要があります。</li>
          <li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li>
        </ul>
        <p>または</p>
        <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on Adobe Workfront Fusion licenses, see [Adobe Workfront Fusion licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md).-->

+++

## Workfront Fusion テンプレートの承認または却下

テンプレートを承認すると、「[!UICONTROL &#x200B; 公開テンプレート &#x200B;]」タブに表示され、すべてのユーザーが使用できるようになります。

テンプレートを却下すると、「[!UICONTROL 公開テンプレート]」タブからテンプレートが削除され、作成したチームのみが使用できます。

1. 左側のナビゲーションパネルで「**[!UICONTROL 管理]**」をクリックして、[!UICONTROL 管理]エリアを開きます。
1. 左側のナビゲーションパネルで「**[!UICONTROL テンプレート]**」をクリックします。
1. テンプレートを承認する場合は、テンプレートの右側にある「**[!UICONTROL 承認]**」をクリックします。
1. テンプレートを却下する場合は、テンプレートの右側にある「**[!UICONTROL 却下]**」をクリックします。

>[!NOTE]
>
>以前に承認および編集されたテンプレートを承認する場合は、2 回目の承認で元のテンプレートが上書きされます。


## テンプレートのステータス

ステータスは、テンプレートページのテンプレート名で確認できます。

以下のステータスを使用できます。

* **[!UICONTROL 非公開]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。
* **[!UICONTROL 公開済み]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。公開したら、必要に応じて承認用にテンプレートを送信できます。 共有可能なリンクをコピーすることもできます。
* **[!UICONTROL 承認済み]**：このテンプレートは、すべての Workfront Fusion ユーザーの「[!UICONTROL 公開テンプレート]」タブに表示されます。画面の右上隅にある [!UICONTROL &#x200B; オプション &#x200B;] をクリックして、共有可能なリンクをコピーすることもできます。

「[!UICONTROL チームテンプレート]」タブから、ステータスを確認することができます。テンプレートが公開されると、テンプレート名の右側にアイコンが表示されます。

* **目のアイコン**：テンプレートが公開され、チームに対してのみ表示され、承認リクエストが送信されませんでした。
* **黄色のチェックマークアイコン**：テンプレートは公開され、チームに対してのみ表示され、「公開テンプレート」タブに追加される承認が保留中です。
* **緑のチェックマークアイコン**：テンプレートは、「公開テンプレート」タブに表示され、すべてのWorkfront Fusion ユーザーに表示されます。 「[!UICONTROL &#x200B; チームテンプレート &#x200B;]」タブにも表示されます。 テンプレート作成者またはチームメンバーは、引き続き編集できます。

アイコンのないテンプレートは[!UICONTROL プライベート]ステータスになります。これらは公開されておらず、チームにのみ表示されます。


<!--

## Questions about how this works

Editing

1. If an admin edits a template, do they have to publish again? ... Do they have to approve again?
1. What does publishing actually do?
1. Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
1. What is the admin approving? Does a user have to submit it for approval? 



What does "Publishing" mean?
What does "Approving" mean?
If an admin edits a template, do they have to publish again? ... Do they have to approve again?
Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
What is the admin approving? Does a user have to submit it for approval?

-->
