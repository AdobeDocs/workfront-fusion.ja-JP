---
content-type: reference
title: テンプレートを編集
description: この記事では、Fusion テンプレートの編集方法について説明します。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 473dba8b-faa4-432f-9357-c2146e86b261
source-git-commit: 72abd9b5aa73d54edd73dc16f7695d2b01cc8624
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 46%

---

# テンプレートを編集

Adobe Workfront Fusionのテンプレートは、さまざまなワークフローを自動化および合理化するように設計されている、事前定義済みのシナリオです。 テンプレートを活用すれば、すべてをゼロから構築する必要はなく、統合と自動化をすばやく設定できます。

管理者の場合は、他のユーザーが作成したテンプレートを表示、変更、名前変更、公開、承認、削除する権限があります。

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
        <p>現在：Workfront Fusionのライセンスは必要ありません。</p>
        <p>または</p>
        <p>レガシー：任意</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">製品</td>
      <td>
        <p>新規：</p>
        <ul>
          <li>[!UICONTROL Select]または[!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusionを購入する必要があります。</li>
          <li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusionが含まれています。</li>
        </ul>
        <p>または</p>
        <p>現在：組織はAdobe Workfront Fusionを購入する必要があります。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on Adobe Workfront Fusion licenses, see [Adobe Workfront Fusion licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md).
-->

+++

## Workfront Fusion テンプレートの管理者としての編集

1. 左側のナビゲーションパネルで「**[!UICONTROL 管理]**」をクリックして、[!UICONTROL 管理]エリアを開きます。
1. 左側のナビゲーションパネルで「**[!UICONTROL すべてのテンプレート]**」をクリックします。
1. 編集するテンプレートの右側にある「**[!UICONTROL 詳細]**」をクリックします。
1. （オプション）右上隅の&#x200B;**オプション**&#x200B;をクリックし、**名前を変更**&#x200B;を選択して、テンプレートの名前を変更します。
1. （オプション）テンプレートの言語を変更するには、**[!UICONTROL 新しいテンプレートを作成]** ![&#x200B; シナリオ設定アイコン &#x200B;](assets/fusion-scenario-settings-icon.png)をクリックし、言語ドロップダウンから言語を選択します。

   >[!IMPORTANT]
   >
   >言語の選択は、システム設定で使用できる言語に対応し、パブリックテンプレートの名前と説明にのみ関係します。テンプレートを保存した後は、テンプレート言語を変更することはできません。

1. （オプション）テンプレートの説明を編集するには、**[!UICONTROL テンプレートの設定]** ![&#x200B; シナリオ設定アイコン &#x200B;](assets/fusion-scenario-settings-icon.png)をクリックし、説明を入力します。
1. 標準シナリオを作成する場合と同じ方法で、アプリ、モジュール、ツールを追加または編集します。

   モジュールにコンテキストヘルプを追加するには、この記事の[設定[!UICONTROL ウィザード]機能](#set-up-wizard-functionality)を参照してください。

   <!--For more information on building a scenario, see [Create a scenario in Adobe Workfront Fusion](../../../workfront-fusion/scenarios/create-a-scenario.md).-->

   >[!NOTE]
   >
   >接続、資格情報またはプライバシーの影響を受けるその他の情報を追加する必要があるモジュールがテンプレートに含まれている場合、この情報はテンプレートユーザーと共有されません。

1. （オプション）「**[!UICONTROL 1回実行]**」をクリックして、テンプレートをテストします。
1. **[!UICONTROL 保存]** アイコン ![保存アイコン &#x200B;](assets/save-icon.png)をクリックします。


## [!UICONTROL &#x200B; ウィザード]機能の設定

[!DNL Workfront Fusion template] [!UICONTROL ウィザード]では、今後テンプレートを使用するユーザーに対して、モジュールで使用される特定のフィールドに関する手順や情報を提供します。

1. テンプレートに追加されたモジュールをクリックして、モジュールのフィールドを表示します。
1. [!UICONTROL &#x200B; ウィザード &#x200B;]情報を追加するフィールドを見つけ、そのフィールドの下の&#x200B;**[!UICONTROL ウィザード]**&#x200B;で使用を有効にします。
1. ユーザーに対して表示する情報を、「[!UICONTROL ヘルプ]」フィールドに入力します。
1. （オプション）テンプレートの使用時にユーザーに対してこのテキストを表示するには、「**[!UICONTROL デフォルト値として使用]**」を有効にします。
1. 情報を入力する各フィールドに対して、手順 2～4 を繰り返します。
1. 「**[!UICONTROL OK]**」をクリックして、変更を保存してモジュールを閉じます。

公開プロセスは、標準ユーザーの場合と同じです。 詳しくは、[&#x200B; テンプレートの公開と共有](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md) セクションを参照してください。

## テンプレートのステータス

テンプレート名の下のテンプレートページでステータスを確認できます。

以下のステータスを使用できます。

* **[!UICONTROL 非公開]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。
* **[!UICONTROL 公開済み]**：このテンプレートは、テンプレート作成者とそのチームに対してのみ表示されます。公開したテンプレートは、必要に応じて承認用に送信できます。 共有可能なリンクをコピーすることもできます。
* **[!UICONTROL 承認済み]**：このテンプレートは、すべての Workfront Fusion ユーザーの「[!UICONTROL 公開テンプレート]」タブに表示されます。画面の右上隅にある[!UICONTROL &#x200B; オプション &#x200B;]をクリックして、共有可能なリンクをコピーすることもできます。

「[!UICONTROL チームテンプレート]」タブから、ステータスを確認することができます。テンプレートが公開されると、テンプレート名の右側にアイコンが表示されます。

* **目のアイコン**: テンプレートが公開されました。チームに表示されます。
* **黄色のチェックマークアイコン**: テンプレートが公開され、チームのみが表示され、「公開テンプレート」タブに追加する承認待ちの状態になっています。
* **緑のチェックマークアイコン**: テンプレートは「公開テンプレート」タブで使用でき、Workfront Fusion ユーザーなら誰でも表示できます。 [!UICONTROL &#x200B; チームテンプレート &#x200B;] タブにも表示されます。 テンプレート作成者またはチームメンバーは、引き続きテンプレートを編集できます。

アイコンのないテンプレートは[!UICONTROL プライベート]ステータスになります。これらは公開されておらず、チームにのみ表示されます。

## テンプレートのSVG情報を探す

1. 左側のナビゲーションパネルで「**[!UICONTROL 管理]**」をクリックして、[!UICONTROL 管理]エリアを開きます。
1. 左側のナビゲーションパネルで「**[!UICONTROL テンプレート]**」をクリックします。
1. 情報を検索するテンプレートをクリックします。
1. 右上隅の&#x200B;**オプション**&#x200B;をクリックします。
1. *SVG図*&#x200B;を選択します。

ここでは、SVG図とSVGコードを表示できます。
