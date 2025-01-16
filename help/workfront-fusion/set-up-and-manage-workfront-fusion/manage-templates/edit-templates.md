---
content-type: reference
title: テンプレートを編集
description: この記事では、Fusion テンプレートの編集方法を説明します。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 473dba8b-faa4-432f-9357-c2146e86b261
source-git-commit: 86b0d7b16a4ed7e15888f6ee1a58f0279e96fb70
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 22%

---

# テンプレートを編集

Adobe Workfront Fusion テンプレートは、様々なワークフローを自動化および効率化するために設計された事前定義済みのシナリオです。 これらのテンプレートを使用すると、最初からすべてを構築する必要なく、統合と自動化をすばやく設定できます。

管理者には、他のユーザーが作成したテンプレートを表示、変更、名前変更、公開、承認および削除する権限があります。

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

For information on [!DNL Adobe Workfront Fusion] licenses, see [[!DNL Adobe Workfront Fusion] licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md). -->

+++

## 管理者として [!DNL Workfront Fusion] テンプレートを編集する

1. 左側のナビゲーションパネルで「**[!UICONTROL Administration]**」をクリックして、[!UICONTROL Administration] 領域を開きます。
1. 左側のナビゲーションパネルで「**[!UICONTROL All Templates]**」をクリックします。
1. 編集す **[!UICONTROL Detail]** テンプレートの右側にある「」をクリックします。
1. （任意）右上隅の **オプション** をクリックして「名前を変更 **を選択して、テンプレートの名前を変更** ます。
1. （オプション）テンプレートの言語を変更するには、「**[!UICONTROL Create a new template]** ![](assets/fusion-scenario-settings-icon.png)」をクリックし、「言語」ドロップダウンから言語を選択します。

   >[!IMPORTANT]
   >
   >言語の選択は、システム設定で使用できる言語に対応し、パブリックテンプレートの名前と説明にのみ関係します。テンプレートを保存した後は、テンプレート言語を変更することはできません。

1. （オプション）テンプレートの説明を編集するには、「![](assets/fusion-scenario-settings-icon.png)」 **[!UICONTROL Set up a template]** クリックし、説明を入力します。
1. 標準シナリオを作成する場合と同じ方法で、アプリ、モジュール、ツールを追加または編集します。

   モジュールにコンテキストヘルプを追加するには、この記事の [[!UICONTROL Wizard] 機能の設定 ](#set-up-wizard-functionality) を参照してください。

   <!--For more information on building a scenario, see [Create a scenario in [!DNL Adobe Workfront Fusion]](../../../workfront-fusion/scenarios/create-a-scenario.md).-->

   >[!NOTE]
   >
   >接続、資格情報またはプライバシーの影響を受けるその他の情報を追加する必要があるモジュールがテンプレートに含まれている場合、この情報はテンプレートユーザーと共有されません。

1. （任意）「**[!UICONTROL Run once]**」をクリックしてテンプレートをテストします。
1. **[!UICONTROL Save]** アイコンをクリックし ![](assets/save-icon.png) す。


## [!UICONTROL Wizard] 機能の設定

[!DNL Workfront Fusion template] [!UICONTROL Wizard] を使用すると、モジュールで使用される特定のフィールドに関連する手順や情報を、テンプレートの今後のユーザーに提供できます。

1. テンプレートに追加されたモジュールをクリックして、モジュールのフィールドを表示します。
1. 情報を追加するフィールドを見つけ [!UICONTROL Wizard]、そのフィールドの下にある **[!UICONTROL Use in Wizard]** を有効にします。
1. ユーザーに表示する情報を「[!UICONTROL Help]」フィールドに入力します。
1. （オプション）テンプレートの使用時にこのテキストを表示するには、**[!UICONTROL Use as default value]** を有効にします。
1. 情報を入力する各フィールドに対して、手順 2～4 を繰り返します。
1. 「**[!UICONTROL OK]**」をクリックして変更を保存し、モジュールを閉じます。

公開プロセスは、標準ユーザーの場合と同じです。 詳しくは、[Publishと共有テンプレート ](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md) の節を参照してください。

## テンプレートのステータス

ステータスは、テンプレートページのテンプレート名で確認できます。

以下のステータスを使用できます。

* **[!UICONTROL Private]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。
* **[!UICONTROL Published]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。 公開したら、必要に応じて承認用にテンプレートを送信できます。 共有可能なリンクをコピーすることもできます。
* **[!UICONTROL Approved]**：このテンプレートは、すべてのWorkfront Fusion ユーザーに対して「[!UICONTROL Public templates]」タブに表示されます。 画面の右上隅にある「[!UICONTROL Options]」をクリックして、共有可能なリンクをコピーすることもできます。

また、「ステータス」タブからステータ [!UICONTROL Team templates] を確認することもできます。 テンプレートが公開されると、テンプレート名の右側にアイコンが表示されます。

* **目のアイコン**：テンプレートが公開され、チームに対して表示されます。
* **黄色のチェックマークアイコン**：テンプレートは公開され、チームに対してのみ表示され、「公開テンプレート」タブに追加される承認が保留中です。
* **緑のチェックマークアイコン**：テンプレートは、「公開テンプレート」タブに表示され、すべてのWorkfront Fusion ユーザーに表示されます。 また、「[!UICONTROL Team templates]」タブにも表示されます。 テンプレート作成者またはチームメンバーは、引き続き編集できます。

アイコンのないテンプレートのステータスは [!UICONTROL Private] です。 これらは公開されておらず、チームにのみ表示されます。

## テンプレートのSVG情報の検索

1. 左側のナビゲーションパネルで「**[!UICONTROL Administration]**」をクリックして、[!UICONTROL Administration] 領域を開きます。
1. 左側のナビゲーションパネルで「**[!UICONTROL Templates]**」をクリックします。
1. 情報を検索するテンプレートをクリックします。
1. 右上隅の **オプション** をクリックします。
1. 「*SVG図*」を選択します。

ここで、SVGダイアグラムとSVGコードを確認できます。
