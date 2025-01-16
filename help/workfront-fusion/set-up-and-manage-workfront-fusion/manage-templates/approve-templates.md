---
content-type: reference
title: テンプレートを承認または却下
description: この記事では、Fusion テンプレートを承認または却下する方法について説明します。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: dafecd8b-96e5-46da-9ab6-15f0bc9b52a4
source-git-commit: 23e9f383b25c7b3789c413e557b94418e48a636b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 17%

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
      <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
      <td><p>任意</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td>
      <td><p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p></td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td>
      <td>
        <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
        <p>または</p>
        <p>レガシー：任意</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">製品</td>
      <td>
        <p>新規：</p>
        <ul>
          <li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li>
          <li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li>
        </ul>
        <p>または</p>
        <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on [!DNL Adobe Workfront Fusion] licenses, see [[!DNL Adobe Workfront Fusion] licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md).-->

+++

## [!DNL Workfront Fusion] テンプレートを承認または却下する

テンプレートを承認すると、「[!UICONTROL Public templates]」タブに表示されるようになり、すべてのユーザーが使用できるようになります。

テンプレートを承認しない場合は、「[!UICONTROL Public templates]」タブから削除され、そのテンプレートを作成したチームでのみ使用できるようになります。

1. 左側のナビゲーションパネルで「**[!UICONTROL Administration]**」をクリックして、[!UICONTROL Administration] 領域を開きます。
1. 左側のナビゲーションパネルで「**[!UICONTROL Templates]**」をクリックします。
1. テンプレートを承認する場合は、テンプレートの右側の **[!UICONTROL Approve]** をクリックします。
1. テンプレートの承認を取り消す場合は、テンプレートの右側にある「**[!UICONTROL Disapprove]**」をクリックします。

>[!NOTE]
>
>以前に承認および編集されたテンプレートを承認する場合は、2 回目の承認で元のテンプレートが上書きされます。


## テンプレートのステータス

ステータスは、テンプレートページのテンプレート名で確認できます。

以下のステータスを使用できます。

* **[!UICONTROL Private]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。
* **[!UICONTROL Published]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。 公開したら、必要に応じて承認用にテンプレートを送信できます。 共有可能なリンクをコピーすることもできます。
* **[!UICONTROL Approved]**：このテンプレートは、すべてのWorkfront Fusion ユーザーに対して「[!UICONTROL Public templates]」タブに表示されます。 画面の右上隅にある「[!UICONTROL Options]」をクリックして、共有可能なリンクをコピーすることもできます。

また、「ステータス」タブからステータ [!UICONTROL Team templates] を確認することもできます。 テンプレートが公開されると、テンプレート名の右側にアイコンが表示されます。

* **目のアイコン**：テンプレートが公開され、チームに対してのみ表示され、承認リクエストが送信されませんでした。
* **黄色のチェックマークアイコン**：テンプレートは公開され、チームに対してのみ表示され、「公開テンプレート」タブに追加される承認が保留中です。
* **緑のチェックマークアイコン**：テンプレートは、「公開テンプレート」タブに表示され、すべてのWorkfront Fusion ユーザーに表示されます。 また、「[!UICONTROL Team templates]」タブにも表示されます。 テンプレート作成者またはチームメンバーは、引き続き編集できます。

アイコンのないテンプレートのステータスは [!UICONTROL Private] です。 これらは公開されておらず、チームにのみ表示されます。


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
