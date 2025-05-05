---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Adobe Admin Console を使用してAdobe Workfront Fusion にユーザーを追加する
description: ユーザーを Adobe Admin Console に追加して Adobe Workfront Fusion に割り当てたり、Adobe Admin Console の既存のユーザーを Workfront Fusion に割り当てたりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: 7cb1c1a7-3c7a-459a-818f-d9cefcb9988b
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 55%

---

# Adobe Admin Console を使用してAdobe Workfront Fusion にユーザーを追加する

ユーザーを [!DNL Adobe Admin Console] に追加して、[!DNL Adobe Workfront Fusion] に割り当てるか、[!DNL Adobe Admin Console] に既存のユーザーを [!DNL Workfront Fusion] に割り当てます。

ユーザーの追加方法などを含む、[!DNL Adobe Admin Console] の [!DNL Workfront Fusion] を説明するビデオについて詳しくは、Adobe IMS[&#128279;](https://video.tv.adobe.com/v/3412464/){target=_blank} の [!DNL Fusion]  を参照してください。



この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td> 
   <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td> 
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] の [!DNL Adobe Workfront] プランがある場合、この記事で説明する機能を使用するには、組織で [!DNL Adobe Workfront Fusion] の購入 [!DNL Adobe Workfront] 必要です。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront] を組織で購入する必要があります。</p>
   </td> 
  </tr>
   <tr> 
   <td role="rowheader">[!DNL Adobe] 管理者権限</td> 
   <td>組織の [!DNL Adobe] 製品 [!UICONTROL Product Configuration Administrator] である必要があります。</td> 
  </tr>
  </tbody> 
</table>

&#42;ご利用のプラン、ライセンスタイプ、アクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

&#42;&#42; ライセンスについて詳 [!DNL Adobe Workfront Fusion] くは、[[!DNL Adobe Workfront Fusion]  ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。



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
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の [!DNL Workfront Fusion] 管理者である必要があります。</p>
     <p>チームの [!DNL Workfront Fusion] 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++


## 前提条件

[!DNL Workfront] に [!DNL Admin Console] を使用する前に、コンソールへの招待メールが届くはずです。

1. [!DNL Adobe] を初めて使用する場合で、組織の [!DNL Adobe] ソフトウェアとサービスを管理する管理者権限があることを知らせるメールを受け取った場合には、メール内のボタンをクリックして [!DNL Adobe] アカウントを作成して、[!DNL Admin Console] を開きます。

   または

   既に Adobeアカウント がある場合は、[[!DNL Adobe Admin Console] ページ](https://adminconsole.adobe.com)に移動します。


## [!DNL Adobe Admin Console] および [!DNL Workfront Fusion] に新しいユーザーを追加

1. [[!DNL Adobe Admin Console]  ページ ](https://adminconsole.adobe.com/) から、上部のナビゲーションバーの「**[!UICONTROL Products]**」タブを選択し、「**[!DNL Workfront Fusion]** 製品」タイルを選択します。

   ![Admin Console 内の Fusion](assets/fusion-product-admin-console.png)

1. 表示されるリストで、ユーザーを追加する組織を選択します。

   ![Admin Console 内の Fusion インスタンス](assets/fusion-instances-admin-console.png)

1. 表示されるリストで、「**[!UICONTROL Product Profiles]**」タブを選択した状態で、[!DNL Workfront Fusion] [!UICONTROL Product Profile] リンクの名前をクリックします。

   >[!IMPORTANT]
   >
   > [!UICONTROL Product Profile] 自体は変更しないでください。

1. リストの上で「**[!UICONTROL Users]**」タブを選択した状態で、「**[!UICONTROL Add User]**」をクリックします。

1. **[!UICONTROL Add users to this product profile]** ボックスに、追加するメールアドレスまたはユーザーの名前を入力し、表示されるリストでユーザーを選択します。

1. **[!UICONTROL Save]** をクリックします。

   ユーザーが [!DNL Workfront Fusion] に作成されました。

1. （オプション）[ [!DNL Workfront Fusion]](#change-a-users-access-level-in-workfront-fusion) でのユーザーのアクセスレベルの変更に進みます。

## Workfront Fusion でのユーザーのアクセスレベルを変更

* [ユーザーの役割を管理者に変更](#change-a-users-role-to-admin)
* [ユーザーの役割を Member、Accountant、または App Developer に変更する](#change-a-users-role-to-member-accountant-or-app-developer)

### ユーザーの役割を管理者に変更

ユーザーに管理者の役割を割り当てる場合は、[!DNL Adobe Admin Console] で実行する必要があります。

1. ユーザーを追加した [!DNL Workfront Fusion] [!UICONTROL Product Profile] ページで、「**[!UICONTROL Admins]**」タブを選択します。

1. **[!UICONTROL Add Admin]** をクリックします。

1. **[!UICONTROL Add product profile administrators]** ボックスに管理者になるメールアドレスまたはユーザーの名前を入力し、表示されるリストでユーザーを選択します。

1. **[!UICONTROL Save]** をクリックします。

   ユーザーは [!DNL Workfront Fusion] の管理者になりました。

### ユーザーの役割を Member、Accountant、または App Developer に変更する

メンバー、経理担当、アプリ開発者のロールは、Workfront Fusion 内で処理されます。

手順については、[ ユーザーの役割の表示または編集 ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md) を参照してください。

## [!DNL Adobe Admin Console] の既存ユーザーの [!DNL Workfront Fusion] への割り当て

Fusion で既存のユーザーをチームに追加できます。 これは Fusion 内で処理されます。

手順については、[ チームにユーザーを追加する ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md) を参照してください。
