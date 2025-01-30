---
title: 新しいテンプレートの作成
description: ' [!DNL Adobe] Workfront Fusion で新しいシナリオテンプレートを作成できます。'
author: Becky
feature: Workfront Fusion
exl-id: 9cb9bd04-e9ae-4162-a1b9-d71566582b7a
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 36%

---

# 新しいテンプレートの作成

[!DNL Adobe] Workfront Fusion で新しいシナリオテンプレートを作成できます。

>[!TIP]
>
>新しいテンプレートを作成する前に、「[!UICONTROL Public templates]」タブをチェックして、作成するテンプレートが既に使用可能になっていないことを確認します。

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

## 新規テンプレートの作成

シナリオの作成と同様のプロセスでテンプレートを作成できます。Fusion 管理者は、既存のシナリオからテンプレートを作成することもできます。

* [テンプレートの作成](#build-a-template)
* [シナリオからのテンプレートの作成](#create-a-template-from-a-scenario)

### テンプレートの作成

1. 左側 **[!UICONTROL Templates]** ナビゲーションパネルで ![ テンプレートアイコン ](assets/templates-icon.png) をクリックします。
1. 右上隅の「**[!UICONTROL Create a new template]**」をクリックします。
1. （任意）左上隅のデフォルト **[!UICONTROL New template name]** を置き換えて、テンプレートの名前を変更します。
1. （オプション）テンプレートの言語を変更するには、![ シナリオ設定アイコン ](assets/scenario-settings-icon.png) をクリックし **[!UICONTROL Set up a template]**、「言語」ドロップダウンから言語を選択します。

   >[!IMPORTANT]
   >
   >言語の選択は、システム設定で使用できる言語に対応し、パブリックテンプレートの名前と説明にのみ関係します。テンプレートを保存した後は、テンプレート言語を変更することはできません。

1. （オプション）テンプレートの説明を入力するには、![ シナリオ設定アイコン **[!UICONTROL Set up a template]** クリックし ](assets/scenario-settings-icon.png) 説明を入力します。
1. シナリオにモジュールを追加するのと同じプロセスを使用して、アプリ、モジュール、ツールを追加します。

   手順については、「[ モジュールの追加 ](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md) の記事を参照してください。

   モジュールにコンテキストヘルプを追加するには、この記事の [ ウィザード機能の設定 ](#set-up-wizard-functionality) を参照してください。

   シナリオの作成について詳しくは、[ シナリオ作成のワークフロー ](/help/workfront-fusion/create-scenarios/plan-a-scenario/create-a-scenario-workflow.md) を参照してください。

   >[!NOTE]
   >
   >接続、資格情報またはプライバシーの影響を受けるその他の情報を追加する必要があるモジュールがテンプレートに含まれている場合、この情報はテンプレートユーザーと共有されません。

1. （任意）「**[!UICONTROL Run once]**」をクリックしてテンプレートをテストします。
1. **[!UICONTROL Save]** アイコン ![ 保存アイコン ](assets/save-icon.png) をクリックして、テンプレートを保存します。

テンプレートを保存すると、チームメンバーに表示されます。 チーム外でテンプレートにアクセスできるようにする場合は、リクエストを送信して承認および公開する必要があります。 リクエストはAdobe Workfront Fusion チームに送信され、承認が求められます。 承認されたテンプレートには、チーム外の他のユーザーがアクセスできます。

テンプレートの公開について詳しくは、[ [!DNL Adobe Workfront Fusion]  テンプレート](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md)の公開と共有を参照してください。

### シナリオからのテンプレートの作成

>[!NOTE]
>
>シナリオからテンプレートを作成するには、Fusion 管理者である必要があります。

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. テンプレートを作成するシナリオを選択します。
1. ページの右上隅付近にある&#x200B;**管理**&#x200B;ドロップダウンをクリックします。
1. 「**テンプレートとして複製**」を選択します。

   シナリオが新規テンプレートページにコピーされます。
1. （任意）左上隅のデフォルト **[!UICONTROL New template name]** を置き換えて、テンプレートの名前を変更します。
1. （オプション）テンプレートの言語を変更するには、![ シナリオ設定アイコン ](assets/scenario-settings-icon.png) をクリックし **[!UICONTROL Set up a template]**、「言語」ドロップダウンから言語を選択します。

   >[!IMPORTANT]
   >
   >言語の選択は、システム設定で使用できる言語に対応し、パブリックテンプレートの名前と説明にのみ関係します。テンプレートを保存した後は、テンプレート言語を変更することはできません。

1. （オプション）テンプレートの説明を入力するには、![ シナリオ設定アイコン **[!UICONTROL Set up a template]** クリックし ](assets/scenario-settings-icon.png) 説明を入力します。
1. シナリオにモジュールを追加するのと同じプロセスを使用して、必要に応じてアプリ、モジュール、ツールを編集します。

   手順については、「[ モジュールの追加 ](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md) の記事を参照してください。

   モジュールにコンテキストヘルプを追加するには、この記事の [[!UICONTROL Wizard] 機能の設定 ](#set-up-wizard-functionality) を参照してください。

   >[!NOTE]
   >
   >接続、資格情報またはプライバシーの影響を受けるその他の情報を追加する必要があるモジュールがテンプレートに含まれている場合、この情報はテンプレートユーザーと共有されません。

1. （任意）「**[!UICONTROL Run once]**」をクリックしてテンプレートをテストします。
1. **[!UICONTROL Save]** アイコン ![ 保存アイコン ](assets/save-icon.png) をクリックします。

## [!UICONTROL Wizard] 機能の設定 {#set-up-wizard-functionality}

[!DNL Workfront Fusion template] [!UICONTROL Wizard] を使用すると、モジュールで使用される特定のフィールドに関連する手順や情報を、テンプレートの今後のユーザーに提供できます。

1. テンプレートの作成時に、テンプレートに追加されたモジュールをクリックすると、モジュールのフィールドが表示されます。
1. 情報を追加するフィールドを見つけ [!UICONTROL Wizard]、そのフィールドの **[!UICONTROL Use in Wizard]** を有効にします。
1. ユーザーに表示する情報を「[!UICONTROL Help]」フィールドに入力します。
1. （オプション）テンプレートの使用時にこのテキストを表示するには、**[!UICONTROL Use as default value]** を有効にします。
1. 情報を入力する各フィールドに対して、手順 2～4 を繰り返します。
1. 「**[!UICONTROL OK]**」をクリックして変更を保存し、モジュールを閉じます。
