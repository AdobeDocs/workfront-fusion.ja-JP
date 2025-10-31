---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: テンプレートの表示、編集、削除
description: Adobe Workfront Fusion を使用するには、Adobe Workfront ライセンスに加えて、Adobe Workfront Fusion ライセンスが必要です。
author: Becky
feature: Workfront Fusion
exl-id: 97e3402c-d1d0-44f6-9752-11b0f5abee22
source-git-commit: 3a977d805c10fda7209b0634c6e32e818a980691
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 42%

---

# テンプレートの表示、編集、削除

Workfront Fusion のテンプレート機能を使用すると、Workfront Fusion のシナリオの出発点として既存のテンプレートを作成および使用できます。 テンプレートは、組織のニーズや特定のユースケースに合わせて設定および変更できる、一般的なユースケースを表します。

現在使用可能な Fusion テンプレートのリストについては、[ 現在使用可能なAdobe Workfront Fusion テンプレート ](/help/workfront-fusion/create-and-manage-templates/currently-available-fusion-templates.md) を参照してください。

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
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

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
>「[!UICONTROL チームテンプレート]」タブには、公開されたテンプレートだけでなく、管理者が既に公開したテンプレートのコピーも含まれます。これにより、すでに全員に表示されているテンプレートを編集できます。これらのテンプレートのいずれかを変更しても、変更によって公開テンプレートがすぐに上書きされることはありません。「[!UICONTROL  公開テンプレート ]」タブのテンプレートは変更されず、公開されたままですが、[!UICONTROL  チームテンプレート ] からの変更点を含む新しいバージョンでは、公開プロセスが開始されます。 変更されたバージョンが公開および承認されると、元の公開テンプレートが上書きされます。

## テンプレートを削除

削除できるのは、まだ承認されていないテンプレートのみです。公開テンプレートを削除する場合は、管理者にお問い合わせください。

削除したテンプレートは復元できませんのでご注意ください。 チームテンプレートはチームのすべてのメンバーが使用できるので、テンプレートを削除する前にチームに問い合わせて、テンプレートが不要であることを確認することをお勧めします。

1. サイドナビゲーションメニューの **[!UICONTROL テンプレート]** アイコン ![ テンプレートアイコン ](assets/templates-icon.png) をクリックします。
1. 「**[!UICONTROL チームテンプレート]**」タブをクリックします。
1. テンプレート名の横にある「**[!UICONTROL 削除]**」をクリックします。

   または

   テンプレート名をクリックして、テンプレートに移動します。右上隅にある「**[!UICONTROL オプション]**」をクリックして、「**[!UICONTROL 削除]**」を選択します。

1. **[!UICONTROL を本当にクリックしますか？]** をクリックして削除を確定します。
