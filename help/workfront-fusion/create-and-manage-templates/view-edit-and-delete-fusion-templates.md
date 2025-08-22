---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: テンプレートの表示、編集、削除
description: Adobe Workfront Fusion を使用するには、Adobe Workfront ライセンスに加えて、Adobe Workfront Fusion ライセンスが必要です。
author: Becky
feature: Workfront Fusion
exl-id: 97e3402c-d1d0-44f6-9752-11b0f5abee22
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 44%

---

# テンプレートの表示、編集、削除

Workfront Fusion のテンプレート機能を使用すると、Workfront Fusion のシナリオの出発点として既存のテンプレートを作成および使用できます。 テンプレートは、組織のニーズや特定のユースケースに合わせて設定および変更できる、一般的なユースケースを表します。

現在使用可能な Fusion テンプレートのリストについては、[ 現在使用可能なAdobe Workfront Fusion テンプレート ](/help/workfront-fusion/create-and-manage-templates/currently-available-fusion-templates.md) を参照してください。

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

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Fusion テンプレートの表示と選択

テンプレート エリアでは、使用可能なテンプレート、テンプレートに含まれるアプリケーションおよびその構造を表示できます。 また、特定のアプリや名前を検索し、ユースケースをフィルタリングすることもできます。

1. 左側のナビゲーションで **テンプレート**![ テンプレートアイコン ](assets/templates-icon.png) をクリックします。
1. 公開されているテンプレートを表示するには、「公開テンプレート」タブをクリックします。

   または

   自分のチームに限定されたテンプレートを表示するには、「チームテンプレート」タブをクリックします。



   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Public templates]</td> 
      <td> <p> 管理者が公開および承認したすべてのテンプレート。テンプレートタイルに、テンプレートの名前、プレビュー、およびこれまでのテンプレートの使用回数を示すソケットアイコンが表示されます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Team templates]</td> 
      <td> <p>チームメンバーが作成したすべてのテンプレート（管理者が既に公開したテンプレートを含む）。テンプレートタイルには、テンプレートの名前、ステータスアイコン（このドキュメントのテンプレートの公開と共有の節を参照）、および「削除」ボタンが表示されます。</p> <b> メモ：</b> 「チームテンプレート」タブに目的のテンプレートが表示されない場合は、左側のナビゲーションまたはヘッダーで、現在、正しいチームを表示していることを確認します。</td> 
     </tr> 
    </tbody> 
   </table>
1. （オプション）特定のアプリケーションまたは名前を検索するには、「アプリまたは名前を検索」ボックスに入力を開始し、ドロップダウンに表示される用語を選択します。
1. （任意）右側の「カテゴリ別」セクションでカテゴリをクリックして、特定のカテゴリのユースケースをフィルタリングします。
1. （オプション）テンプレートのカードにカーソルを合わせて、シナリオテンプレートの構造を表示します。
1. シナリオの作成に使用するテンプレートをクリックします。

   テンプレートの図が表示されます。

1. 公開テンプレートからシナリオの作成を開始するには、左下隅にある「**テンプレートから新しいシナリオを作成**」をクリックします。

   または


   チームテンプレートからシナリオの作成を開始するには、ダイアグラムをクリックしてから、モジュールをクリックして設定を開始します。

テンプレートからシナリオを作成する手順については、[ テンプレートを使用したシナリオの作成 ](/help/workfront-fusion/create-and-manage-templates/create-scenarios-with-fusion-templates.md) を参照してください。



>[!NOTE]
>
>* アクセスするテンプレートが、自分またはチームのメンバーが作成したものではなく、まだ公開されていない場合は、作成と公開を行ったユーザーにテンプレートのリンクを共有するよう依頼できます。
>* 自分が作成した公開テンプレートが見つからない場合は、管理者に問い合わせてください。テンプレートを承認する前に、管理者が名前を変更した可能性があります。

## テンプレートを編集

「[!UICONTROL チームテンプレート]」タブで任意のテンプレートを編集できます。

1. サイドナビゲーションメニューの **[!UICONTROL テンプレート]** アイコン ![ テンプレートアイコン ](assets/templates-icon.png) をクリックします。
1. 「**[!UICONTROL チームテンプレート]**」タブをクリックします。
1. 「**[!UICONTROL プライベート]**」タブをクリックします。
1. 編集するテンプレートをクリックします。
1. 右上隅にある「**[!UICONTROL 編集]**」をクリックします。

   または

   テンプレートダイアグラムをクリックします。

1. テンプレートに変更を加えます。テンプレートの作成時に使用できたすべてのオプションにアクセスできます。これらのオプションを確認するには、[ 新しいテンプレートの作成 ](/help/workfront-fusion/create-and-manage-templates/create-new-fusion-templates.md) を参照してください。
1. **[!UICONTROL 保存]** アイコン ![ 保存アイコン ](assets/save-icon.png) をクリックします。

>[!NOTE]
>
>「[!UICONTROL チームテンプレート]」タブには、公開されたテンプレートだけでなく、管理者が既に公開したテンプレートのコピーも含まれます。これにより、すでに全員に表示されているテンプレートを編集できます。これらのテンプレートのいずれかを変更しても、変更によって公開テンプレートがすぐに上書きされることはありません。「[!UICONTROL &#x200B; 公開テンプレート &#x200B;]」タブのテンプレートは変更されず、公開されたままですが、[!UICONTROL &#x200B; チームテンプレート &#x200B;] からの変更点を含む新しいバージョンでは、公開プロセスが開始されます。 変更されたバージョンが公開および承認されると、元の公開テンプレートが上書きされます。

## テンプレートを削除

削除できるのは、まだ承認されていないテンプレートのみです。公開テンプレートを削除する場合は、管理者にお問い合わせください。

削除したテンプレートは復元できませんのでご注意ください。 チームテンプレートはチームのすべてのメンバーが使用できるので、テンプレートを削除する前にチームに問い合わせて、テンプレートが不要であることを確認することをお勧めします。

1. サイドナビゲーションメニューの **[!UICONTROL テンプレート]** アイコン ![ テンプレートアイコン ](assets/templates-icon.png) をクリックします。
1. 「**[!UICONTROL チームテンプレート]**」タブをクリックします。
1. テンプレート名の横にある「**[!UICONTROL 削除]**」をクリックします。

   または

   テンプレート名をクリックして、テンプレートに移動します。右上隅にある「**[!UICONTROL オプション]**」をクリックして、「**[!UICONTROL 削除]**」を選択します。

1. **[!UICONTROL を本当にクリックしますか？]** をクリックして削除を確定します。
