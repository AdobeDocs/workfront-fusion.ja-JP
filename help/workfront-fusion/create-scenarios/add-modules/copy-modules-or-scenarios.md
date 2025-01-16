---
title: モジュールまたはシナリオのコピー
description: Adobe Workfront Fusion では、モジュール、モジュールのグループまたはシナリオ全体をコピーできます。 この機能を使用すると、シナリオやシナリオの一部を再度作成しなくても再利用できます。
author: Becky
feature: Workfront Fusion
exl-id: 5cece7d4-b2c7-4276-8a6f-f65bad799c7a
source-git-commit: 55fe4bc46bc50ad9ccfd1b234e89028cf3cd12d5
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 51%

---

# モジュールまたはシナリオのコピー

Adobe Workfront Fusion では、モジュール、モジュールのグループまたはシナリオ全体をコピーできます。 この機能を使用すると、シナリオやシナリオの一部を再度作成しなくても再利用できます。

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

## 前提条件

モジュールは、コピーする前にシナリオに存在する必要があります。

## モジュールまたはモジュールのグループのコピー

モジュールをコピーすると、コピー元のモジュールのすべてのフィールド値と設定が保持されます。

モジュールを同じシナリオの別の領域に貼り付けたり、別のシナリオにペーストしたりできます。

モジュールを別のシナリオに貼り付ける場合は、次の点を考慮してください。

* コピーしなかった別のモジュールから情報を取り込むフィールド値は、その情報にアクセスできなくなります。新しいシナリオから情報を取り込むには、これらのフィールドを設定する必要があります。
* 別のチームまたは組織が所有するシナリオにモジュールを貼り付ける場合は、新しいシナリオを所有するチームまたは組織が所有する接続にすべての接続を更新する必要があります。

### モジュールのコピー

モジュールのグループをコピーする方法は、単一のモジュールをコピーする場合と似ています。

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. モジュールをコピーするシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. コピーするモジュールを右クリックします。

   >[!NOTE]
   >
   >複数のモジュールを選択するには、[!UICONTROL shift] を押したまま、コピーするモジュールをクリックします。 モジュールのグループをコピーすると、接続線、フィルター、ルーティングロジックもコピーされます。

1. 「**[!UICONTROL Copy module]**」を選択します。
1. シナリオのコピー先となる領域にカーソルを移動します。
1. 右クリックし、「**[!UICONTROL Paste]**」を選択します。
1. ペーストしたモジュールをシナリオ内の適切な場所にドラッグして、シナリオに接続します。

   キーボードショートカットを使用してコピー＆ペーストすることもできます。

## クローンによるシナリオのコピー

シナリオをクローンすると、シナリオのコピーが作成され、編集できます。

1. シナリオの詳細ページを開きます。

   1. 左側のパネルで「**[!UICONTROL Scenario]**」タブをクリックし、詳細を表示するシナリオをクリックします。

      または

      シナリオエディターでシナリオに取り組んでいる場合は、ウィンドウの左上隅にある左矢印 ![](assets/exit-editing-arrow.png) をクリックします。

1. ページの右上にある **[!UICONTROL Options]** を右クリックします。
1. 「**[!UICONTROL Clone]**」を選択します。
1. （オプション）新しいシナリオの名前を入力します。
1. （オプション） **[!UICONTROL Keep the states of any new modules the same as those being duplicated]** を有効にして、コピーしたシナリオに、元のシナリオで処理された最新のレコードに関する情報も含まれるようにします。
1. 「**[!UICONTROL Save]**」をクリックして、シナリオを作成します。

## ブループリントを使用したシナリオのコピー

シナリオのブループリントは、特定の時点での特定のシナリオの配置、マッピング、フィールド値を表します。シナリオのブループリントをコンピューター上の JSON ファイルに書き出し、シナリオの新規作成時に読み込むことができます。シナリオのブループリントから読み込んだシナリオは編集できます。

シナリオのブループリントは、シナリオ全体を表します。シナリオから特定のモジュールのみをコピーする場合は、「[モジュールまたはモジュールのグループのコピー](#copy-a-module-or-a-group-of-modules)」を参照してください。

### シナリオのブループリントの書き出し

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. ブループリントを書き出すシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. シナリオで、シナリオ設定領域の **[!UICONTROL More]** メニューをクリックします。
1. **[!UICONTROL Export Blueprint]** をクリックします。

   JSON ファイルが作成され、コンピューターにダウンロードされます。このファイルは、[!DNL Downloads] フォルダーにあります。

### ブループリントの読み込み

>[!IMPORTANT]
>
>ブループリントを既存のシナリオに読み込むと、既存のシナリオがシナリオのブループリントに置き換えられます。既存のシナリオにブループリントを追加することはできません。

1. シナリオの新規作成を開始します。
1. シナリオで、シナリオ設定領域の **[!UICONTROL More]** メニューをクリックします。
1. **[!UICONTROL Import Blueprint]** をクリックします。
1. 表示されるダイアログで、「**[!UICONTROL Browse]**」をクリックします
1. 読み込むブループリントに移動し、「**[!UICONTROL Open]**」をクリックします。
1. **[!UICONTROL Save]** をクリックします。

   JSON ファイルが作成され、コンピューターにダウンロードされます。このファイルは、[!UICONTROL Downloads] フォルダーにあります。

## テンプレートを使用したシナリオのコピーおよび再利用

[!DNL Workfront Fusion] シナリオの開始点としてテンプレートを作成できます。テンプレートからシナリオを作成する場合、テンプレートを変更せずにシナリオを変更できます。テンプレートには、フィールドの値は保存されません。

テンプレートを使用してシナリオを作成する方法について詳しくは、[ テンプレートを使用したシナリオの作成 ](/help/workfront-fusion/create-scenarios/add-modules/create-scenarios-with-fusion-templates.md) を参照してください。

## トラブルシューティング

[ モジュールまたはモジュールのグループをコピー ](#copy-a-module-or-a-group-of-modules) の説明に従ってモジュールをコピーおよび貼り付けようとしており、貼り付け時に何も表示されない場合は、ブラウザーのサイト設定をチェックして、クリップボードからの貼り付けが許可されていることを確認します。
