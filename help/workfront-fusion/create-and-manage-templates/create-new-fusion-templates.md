---
title: 新しいテンプレートの作成
description: ' [!DNL Adobe] Workfront Fusion で新しいシナリオテンプレートを作成できます。'
author: Becky
feature: Workfront Fusion
exl-id: 9cb9bd04-e9ae-4162-a1b9-d71566582b7a
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 53%

---

# 新しいテンプレートの作成

[!DNL Adobe] Workfront Fusion で新しいシナリオテンプレートを作成できます。

>[!TIP]
>
>新規テンプレートを作成する前に、「[!UICONTROL パブリックテンプレート]」タブをチェックして、作成するテンプレートがまだないことを確認します。

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
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 新規テンプレートの作成

シナリオの作成と同様のプロセスでテンプレートを作成できます。Fusion 管理者は、既存のシナリオからテンプレートを作成することもできます。

* [テンプレートの作成](#build-a-template)
* [シナリオからのテンプレートの作成](#create-a-template-from-a-scenario)

### テンプレートの作成

1. 左側のナビゲーションパネルで **[!UICONTROL テンプレート]**![&#x200B; テンプレートアイコン &#x200B;](assets/templates-icon.png) をクリックします。
1. 右上隅にある「**[!UICONTROL テンプレートの新規作成]**」をクリックします。
1. （オプション）左上隅にあるデフォルトの&#x200B;**[!UICONTROL 新規テンプレート名]**&#x200B;を置き換えることで、テンプレートの名前を変更します。
1. （オプション）テンプレートの言語を変更するには、**[!UICONTROL テンプレートの設定]** ![&#x200B; シナリオ設定アイコン &#x200B;](assets/scenario-settings-icon.png) をクリックし、言語ドロップダウンから言語を選択します。

   >[!IMPORTANT]
   >
   >言語の選択は、システム設定で使用できる言語に対応し、パブリックテンプレートの名前と説明にのみ関係します。テンプレートを保存した後は、テンプレート言語を変更することはできません。

1. （任意）テンプレートの説明を入力するには、「**[!UICONTROL テンプレートの設定]**![&#x200B; シナリオ設定アイコン &#x200B;](assets/scenario-settings-icon.png)」をクリックして説明を入力します。
1. シナリオにモジュールを追加するのと同じプロセスを使用して、アプリ、モジュール、ツールを追加します。

   手順については、「[&#x200B; モジュールの追加 &#x200B;](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md) の記事を参照してください。

   モジュールにコンテキストヘルプを追加するには、この記事の [&#x200B; ウィザード機能の設定 &#x200B;](#set-up-wizard-functionality) を参照してください。

   シナリオの作成について詳しくは、[&#x200B; シナリオ作成のワークフロー &#x200B;](/help/workfront-fusion/create-scenarios/plan-a-scenario/create-a-scenario-workflow.md) を参照してください。

   >[!NOTE]
   >
   >接続、資格情報またはプライバシーの影響を受けるその他の情報を追加する必要があるモジュールがテンプレートに含まれている場合、この情報はテンプレートユーザーと共有されません。

1. （オプション）「**[!UICONTROL 1 回実行]**」をクリックして、テンプレートをテストします。
1. **[!UICONTROL 保存]** アイコン ![&#x200B; 保存アイコン &#x200B;](assets/save-icon.png) をクリックして、テンプレートを保存します。

テンプレートを保存すると、チームメンバーに表示されます。 チーム外でテンプレートにアクセスできるようにする場合は、リクエストを送信して承認および公開する必要があります。 リクエストはAdobe Workfront Fusion チームに送信され、承認が求められます。 承認されたテンプレートには、チーム外の他のユーザーがアクセスできます。

テンプレートの公開について詳しくは、[Adobe Workfront Fusion テンプレートの公開と共有 &#x200B;](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md) を参照してください。

### シナリオからのテンプレートの作成

>[!NOTE]
>
>シナリオからテンプレートを作成するには、Fusion 管理者である必要があります。

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. テンプレートを作成するシナリオを選択します。
1. ページの右上隅付近にある&#x200B;**管理**&#x200B;ドロップダウンをクリックします。
1. 「**テンプレートとして複製**」を選択します。

   シナリオが新規テンプレートページにコピーされます。
1. （オプション）左上隅にあるデフォルトの&#x200B;**[!UICONTROL 新規テンプレート名]**&#x200B;を置き換えることで、テンプレートの名前を変更します。
1. （オプション）テンプレートの言語を変更するには、**[!UICONTROL テンプレートの設定]** ![&#x200B; シナリオ設定アイコン &#x200B;](assets/scenario-settings-icon.png) をクリックし、言語ドロップダウンから言語を選択します。

   >[!IMPORTANT]
   >
   >言語の選択は、システム設定で使用できる言語に対応し、パブリックテンプレートの名前と説明にのみ関係します。テンプレートを保存した後は、テンプレート言語を変更することはできません。

1. （任意）テンプレートの説明を入力するには、「**[!UICONTROL テンプレートの設定]**![&#x200B; シナリオ設定アイコン &#x200B;](assets/scenario-settings-icon.png)」をクリックして説明を入力します。
1. シナリオにモジュールを追加するのと同じプロセスを使用して、必要に応じてアプリ、モジュール、ツールを編集します。

   手順については、「[&#x200B; モジュールの追加 &#x200B;](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md) の記事を参照してください。

   モジュールにコンテキストヘルプを追加するには、この記事の[設定[!UICONTROL ウィザード]機能](#set-up-wizard-functionality)を参照してください。

   >[!NOTE]
   >
   >接続、資格情報またはプライバシーの影響を受けるその他の情報を追加する必要があるモジュールがテンプレートに含まれている場合、この情報はテンプレートユーザーと共有されません。

1. （オプション）「**[!UICONTROL 1 回実行]**」をクリックして、テンプレートをテストします。
1. **[!UICONTROL 保存]** アイコン ![&#x200B; 保存アイコン &#x200B;](assets/save-icon.png) をクリックします。

## [!UICONTROL &#x200B; ウィザード]機能の設定 {#set-up-wizard-functionality}

[!DNL Workfront Fusion template] [!UICONTROL ウィザード]では、今後テンプレートを使用するユーザーに対して、モジュールで使用される特定のフィールドに関する手順や情報を提供します。

1. テンプレートの作成時に、テンプレートに追加されたモジュールをクリックすると、モジュールのフィールドが表示されます。
1. [!UICONTROL ウィザード]情報を追加するフィールドを見つけ、そのフィールドの「**[!UICONTROL ウィザードで使用]**」を有効にします。
1. ユーザーに対して表示する情報を、「[!UICONTROL ヘルプ]」フィールドに入力します。
1. （オプション）テンプレートの使用時にユーザーに対してこのテキストを表示するには、「**[!UICONTROL デフォルト値として使用]**」を有効にします。
1. 情報を入力する各フィールドに対して、手順 2～4 を繰り返します。
1. 「**[!UICONTROL OK]**」をクリックして、変更を保存してモジュールを閉じます。
