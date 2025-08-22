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
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 42%

---

# Adobe Admin Console を使用してAdobe Workfront Fusion にユーザーを追加する

[!DNL Adobe Admin Console] にユーザーを追加してWorkfront Fusion に割り当てたり、[!DNL Adobe Admin Console] 内の既存のユーザーをAdobe Workfront Fusion に割り当てたりできます。

ユーザーの追加方法など、[!DNL Adobe Admin Console] でのWorkfront Fusion について説明しているビデオについては、[[!DNL Fusion]  オンAdobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank} を参照してください。



この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront プラン*</td> 
   <td> <p>[!UICONTROL Pro] 以降</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン*</td> 
   <td> <p>[!UICONTROL Plan]、[!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：Workfront Fusion のライセンス要件はありません。</p>
   <p>または</p>
   <p>従来のライセンス要件：[!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の必要な商品：Adobe Workfrontのプランで [!UICONTROL Select] または [!UICONTROL Prime] をお持ちの場合、この記事に記載されている機能を使用するには、Adobe Workfront Fusion とAdobe Workfrontを購入する必要があります。 Workfront Fusion は、[!UICONTROL Ultimate] Workfront プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事に記載されている機能を使用するには、Adobe Workfront Fusion とAdobe Workfrontを購入する必要があります。</p>
   </td> 
  </tr>
   <tr> 
   <td role="rowheader">[!DNL Adobe] 管理者権限</td> 
   <td>組織の [!DNL Adobe] 製品の [!UICONTROL Product Configuration Administrator] 管理者である必要があります。</td> 
  </tr>
  </tbody> 
</table>

&#42;保有するプラン、ライセンスタイプ、アクセス権を確認するには、Workfront 管理者に問い合わせてください。

&#42;&#42;Adobe Workfront Fusion ライセンスについては、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。



## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++


## 前提条件

Workfrontで [!DNL Admin Console] を使用する前に、コンソールに招待するメールが届きます。

1. [!DNL Adobe] を初めて使用する場合で、組織の [!DNL Adobe] ソフトウェアとサービスを管理する管理者権限があることを知らせるメールを受け取った場合には、メール内のボタンをクリックして [!DNL Adobe] アカウントを作成して、[!DNL Admin Console] を開きます。

   または

   既に Adobeアカウント がある場合は、[[!DNL Adobe Admin Console] ページ](https://adminconsole.adobe.com)に移動します。


## [!DNL Adobe Admin Console] とWorkfront Fusion に新しいユーザーを追加します。

1. [[!DNL Adobe Admin Console] page](https://adminconsole.adobe.com/) から、上部のナビゲーションバーにある **[!UICONTROL Products]** タブを選択し、**Workfront Fusion** 製品タイルを選択します。

   ![Admin Console 内の Fusion](assets/fusion-product-admin-console.png)

1. 表示されるリストで、ユーザーを追加する組織を選択します。

   ![Admin Console 内の Fusion インスタンス](assets/fusion-instances-admin-console.png)

1. 表示されるリストで、「**[!UICONTROL 製品プロファイル]**」タブを選択した状態で、Workfront Fusion の [!UICONTROL &#x200B; 製品プロファイル &#x200B;] リンクの名前をクリックします。

   >[!IMPORTANT]
   >
   > [!UICONTROL 製品プロファイル]自体には、変更を加えないでください。

1. リストの上で「**[!UICONTROL ユーザー]**」タブを選択し、「**[!UICONTROL ユーザーを追加]**」をクリックします。

1. **[!UICONTROL この製品プロファイルにユーザーを追加]**&#x200B;ボックスに、追加するユーザーのメールアドレスまたは名前を入力し、表示されるリストからそのユーザーを選択します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   ユーザーはWorkfront Fusion で作成されます。

1. （オプション）引き続き [Workfront Fusion でのユーザーのアクセスレベルを変更 ](#change-a-users-access-level-in-workfront-fusion) します。

## Workfront Fusion でのユーザーのアクセスレベルを変更

* [ユーザーの役割を管理者に変更](#change-a-users-role-to-admin)
* [ユーザーの役割を Member、Accountant、または App Developer に変更する](#change-a-users-role-to-member-accountant-or-app-developer)

### ユーザーの役割を管理者に変更

ユーザーに管理者の役割を割り当てる場合は、[!DNL Adobe Admin Console] で実行する必要があります。

1. ユーザーを追加したWorkfront Fusion [!UICONTROL &#x200B; 製品プロファイル &#x200B;] ページで、「**[!UICONTROL 管理者]**」タブを選択します。

1. 「**[!UICONTROL 管理者を追加]**」をクリックします。

1. **[!UICONTROL 製品プロファイル管理者を追加]** ボックスで、管理者になるユーザーのメールアドレスまたは名前を入力し、表示されるリストでユーザーを選択します。

1. **[!UICONTROL 保存]**&#x200B;をクリックします。

   ユーザーは、Workfront Fusion の管理者になりました。

### ユーザーの役割を Member、Accountant、または App Developer に変更する

メンバー、経理担当、アプリ開発者のロールは、Workfront Fusion 内で処理されます。

手順については、[ ユーザーの役割の表示または編集 ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md) を参照してください。

## [!DNL Adobe Admin Console] 内の既存のユーザーをWorkfront Fusion に割り当てる

Fusion で既存のユーザーをチームに追加できます。 これは Fusion 内で処理されます。

手順については、[ チームにユーザーを追加する ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md) を参照してください。
