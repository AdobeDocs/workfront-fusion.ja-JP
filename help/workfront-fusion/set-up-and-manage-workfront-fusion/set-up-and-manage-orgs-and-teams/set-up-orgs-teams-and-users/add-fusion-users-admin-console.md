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
source-git-commit: f7c1d5b1de74cc0c59e3a00938bed14b489500db
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 40%

---

# Adobe Admin Console を使用してAdobe Workfront Fusion にユーザーを追加する

[!DNL Adobe Admin Console] にユーザーを追加してWorkfront Fusion に割り当てたり、[!DNL Adobe Admin Console] 内の既存のユーザーをAdobe Workfront Fusion に割り当てたりできます。

ユーザーの追加方法など、[!DNL Adobe Admin Console] でのWorkfront Fusion について説明しているビデオについては、[[!DNL Fusion]  オンAdobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank} を参照してください。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
  </tr>
   <tr> 
   <td role="rowheader">アクセスレベル設定</td> 
   <td>組織のAdobe製品の製品設定管理者である必要があります。</td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

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

1. （オプション）引き続き [Workfront Fusion でのユーザーのアクセスレベルを変更 &#x200B;](#change-a-users-access-level-in-workfront-fusion) します。

## Workfront Fusion でのユーザーのアクセスレベルを変更

* [ユーザーの役割を管理者に変更](#change-a-users-role-to-admin)
* [ユーザーの役割を Member、Accountant、または App Developer に変更する](#change-a-users-role-to-member-accountant-or-app-developer)

### ユーザーの役割を管理者に変更

ユーザーに管理者の役割を割り当てる場合は、[!DNL Adobe Admin Console] で実行する必要があります。

1. ユーザーを追加したWorkfront Fusion [!UICONTROL &#x200B; 製品プロファイル &#x200B;] ページで、「**[!UICONTROL 管理者]**」タブを選択します。

1. 「**[!UICONTROL 管理者を追加]**」をクリックします。

1. **[!UICONTROL 製品プロファイル管理者を追加]** ボックスで、管理者になるユーザーのメールアドレスまたは名前を入力し、表示されるリストでユーザーを選択します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   ユーザーは、Workfront Fusion の管理者になりました。

### ユーザーの役割を Member、Accountant、または App Developer に変更する

メンバー、経理担当、アプリ開発者のロールは、Workfront Fusion 内で処理されます。

手順については、[&#x200B; ユーザーの役割の表示または編集 &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md) を参照してください。

## [!DNL Adobe Admin Console] 内の既存のユーザーをWorkfront Fusion に割り当てる

Fusion で既存のユーザーをチームに追加できます。 これは Fusion 内で処理されます。

手順については、[&#x200B; チームにユーザーを追加する &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md) を参照してください。
