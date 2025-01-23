---
title: SharePoint モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、SharePoint を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '2270'
ht-degree: 84%

---

# [!DNL SharePoint] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL SharePoint] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

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
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## 前提条件

[!DNL SharePoint] モジュールを使用するには、[!DNL SharePoint] アカウントが必要です。

## SharePoint API の情報

SharePoint コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.14.2</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL SharePoint] を [!DNL Workfront Fusion] に接続 {#connect-sharepoint-to-workfront-fusion}

* [ [!DNL Microsoft]  アカウントを使用して、 [!DNL SharePoint]  を  [!DNL Workfront Fusion]  に接続](#connect-sharepoint-to-workfront-fusion-using-a-microsoft-account)
* [詳細設定を使用して、 [!DNL SharePoint]  を  [!DNL Workfront Fusion]  に接続](#connect-sharepoint-to-workfront-fusion-using-advanced-settings)

### [!DNL Microsoft] アカウントを使用して、[!DNL SharePoint] を [!DNL Workfront Fusion] に接続

[!DNL Microsoft] アカウントを使用して、[!DNL SharePoint] への接続を作成することができます。[!DNL Sharepoint] アカウントを [!DNL Workfront Fusion] に接続する手順については、[ [!DNL Adobe Workfront Fusion]  への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) を参照してください。

### 詳細設定を使用して、[!DNL SharePoint] を [!DNL Workfront Fusion] に接続

[!DNL Microsoft] アカウント無しで [!DNL SharePoint] から [!DNL Workfront Fusion] に接続するには、クライアント ID、クライアントシークレット、テナント ID が必要です。

1. **[!DNL SharePoint]** ボックスの上部付近の **[!UICONTROL Add]** をクリックして、**[!UICONTROL Create a connection]** ボックスを開きます。

1. （任意）デフォルト **[!UICONTROL Connection name]** を変更します。
1. **[!UICONTROL Show advanced settings]** をクリックします。
1. [!DNL SharePoint] **[!UICONTROL Client ID]** と **[!UICONTROL Client Secret]** を入力します。

1. **[!UICONTROL Continue]** をクリックします。
1. 表示されるログインウィンドウで、アプリにログインするための資格情報を入力します（まだ入力していない場合）。
1. （条件付き） **[!UICONTROL Allow]** ボタンが表示された場合は、ボタンをクリックしてアプリを [!DNL Workfront Fusion] に接続します。

## [!DNL SharePoint] モジュールとそのフィールド

[!DNL SharePoint] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL SharePoint] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ドライブ項目](#drive-item)
* [項目](#item)
* [リスト](#list)
* [ページ（ベータ版）](#page-beta)
* [サイト](#site)
* [その他](#other)

### ドライブ項目

* [ファイルを作成](#create-a-file)
* [フォルダーを作成](#create-a-folder)
* [ファイルの取得](#get-a-file)
* [フォルダー項目の監視](#watch-folder-items)

#### 変更を取得

このモジュールは、SharePoint で行われた変更を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>変更を取得するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Folder ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>変更を取得する場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> </td> 
  </tr>  </tbody> 
</table>

#### フォルダーを作成

このアクションモジュールは、SharePoint に新しいフォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>作成するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Folder ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>フォルダーを作成する場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder name]</td> 
   <td>新しいフォルダーの名前を入力またはマッピングします。</td> 
  </tr>
  </tbody> 
</table>

#### ファイルの取得

このアクションモジュールは、指定された SharePoint ファイルを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL File ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>ファイルの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### フォルダー項目の監視

このトリガーモジュールは、選択したフォルダー内の項目が更新されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL folder ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するフォルダーの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>1 回のシナリオ実行サイクルで [!DNL Workfront Fusion] が返す項目の最大数を入力します。</td> 
  <tr>
  </tr>
</tbody> 
</table>

### 項目

* [[!UICONTROL Copy an item]](#copy-an-item)
* [[!UICONTROL Create an item]](#create-an-item)
* [[!UICONTROL Delete an item]](#delete-an-item)
* [[!UICONTROL Get an Item]](#get-an-item)
* [[!UICONTROL List Items]](#list-items)
* [[!UICONTROL Move Item]](#move-an-item)
* [[!UICONTROL Update an item]](#update-an-item)
* [[!UICONTROL Watch Items] （スケジュール型）](#watch-items-scheduled)


#### [!UICONTROL Copy Item]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Workfront Fusion]</a> への [!DNL SharePoint] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">サイト ID、ドライブ ID およびフォルダー ID の入力</td> 
   <td> <p>コピーする項目を含んだサイトおよびリストを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Item ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>「項目タイプ」フィールドで、フィールドを移動するかフォルダーを移動するかを選択します。コピーする項目を含むサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> 項目のコピー先となるフォルダーの ID を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>項目の新しいコピーの名前を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an item]

このアクションモジュールは、SharePoint リストに新しい項目を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Create an Item]</td> 
   <td> <p>項目を作成するサイトおよびリストを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong> と <strong>[!UICONTROL List ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の作成先となるリストが含まれているサイトを選択したあと、そのリストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>新しい項目に設定するフィールドごとに、フィールドのキー（フィールドを識別する情報）と、そのフィールドの新しい項目に設定する値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an item]

このアクションモジュールは、SharePoint リスト内の既存の項目を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>削除する項目を含んだサイトおよびリストを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Item ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>削除する項目が含まれているサイトを選択し、リストを選択したあと、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Item]

このアクションモジュールは、指定された項目のデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get an Item]</td> 
   <td> <p>取得する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Item ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の取得元のリストが含まれるサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Items]

このアクションモジュールは、指定されたリスト内のすべての項目のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Items]</td> 
   <td> <p>項目を取得するリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong> と <strong>[!UICONTROL List ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の取得元のリストが含まれるサイトを選択し、リストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返す項目の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an Item]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Workfront Fusion]</a> への [!DNL SharePoint] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">サイト ID、ドライブ ID およびフォルダー ID の入力</td> 
   <td> <p>移動する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Item ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>「項目タイプ」フィールドで、フィールドを移動するかフォルダーを移動するかを選択します。コピーする項目を含むサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> 項目の移動先フォルダーの ID を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>移動した項目の名前を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an item]

このアクションモジュールは、SharePoint リスト内の既存の項目を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>更新する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong>、<strong>[!UICONTROL Item ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新する項目が含まれるサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>新しい項目に対して更新する各フィールドに対して、フィールドのキー（フィールドを識別する）と、そのフィールドに対して項目に含める新しい値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Items] （スケジュール型）

このトリガーモジュールは、項目が作成または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>作成時刻（新しい項目）または変更時刻（更新された項目）のどちらでリストを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>監視するサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong> と <strong>[!UICONTROL List ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するサイトを選択し、リストを選択します。これらのドロップダウンは、後続のサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返す項目の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### リスト

* [[!UICONTROL Create a List]](#create-a-list)
* [[!UICONTROL Get a List]](#get-a-list)
* [[!UICONTROL List Lists]](#list-lists)
* [[!UICONTROL Watch Lists]](#watch-lists)

#### [!UICONTROL Create a List]

このアクションモジュールは、SharePoint に新しいリストを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Site ID]</td> 
   <td> <p>サイトを識別する方法を選択し、リストを作成する場所を一覧表示します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>リストを作成する <strong>[!UICONTROL Site ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>リストを作成するサイトを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display Name]</td> 
   <td>新しいリストの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>新しいリストの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Add Columns]</td> 
   <td>新しいリストに設定する列ごとに、フィールドの <strong>[!UICONTROL Name]</strong> を入力し、新しい列に設定する値の <strong>[!UICONTROL Type]</strong> を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a List]

このアクションモジュールは、指定されたリストのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a List]</td> 
   <td> <p>取得する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong> と <strong> リスト ID</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するリストが含まれるサイトを選択し、リストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Lists]

このアクションモジュールは、指定されたリスト内のすべての項目のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Lists]</td> 
   <td> <p>リストを取得するサイトを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するリストが含まれているサイトを選択します。ドロップダウンは、フォローしているサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すリストの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Lists]

このトリガーモジュールは、リストの作成または変更時にシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>作成時刻（新しい項目）または変更時刻（更新された項目）のどちらでリストを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>監視するサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>監視するリストがある <strong>[!UICONTROL Site ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するサイトを選択します。ドロップダウンは、ユーザーがフォローしているサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すリストの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### ページ（ベータ版）

>[!NOTE]
>
>[!DNL Microsoft Graph] のバージョン `beta` の API は変更される場合があります。実稼動アプリケーションでのこれらの API の使用はサポートされていません。

#### [!UICONTROL Get a Page]

このアクションモジュールは、指定されたページのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Page]</td> 
   <td> <p>取得するページを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> と <strong>[!UICONTROL Page ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するページを含むサイトを選択し、ページを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### サイト

* [[!UICONTROL Get a Site]](#get-a-site)
* [[!UICONTROL Search Sites]](#search-sites)

#### [!UICONTROL Get a Site]

このアクションモジュールは、指定されたサイトのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Site]</td> 
   <td> <p>取得するページを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するサイトを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Sites]

このアクションモジュールは、指定したパラメーターでサイトを検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword of Display Name]</td> 
   <td> <p>サイトを検索する検索語を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すサイトの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

* [変更を取得](#get-changes)
* [API 呼び出しを実行](#make-an-api-call)
* [イベントの監視](#watch-events)

#### 変更を取得

このモジュールは、SharePoint フォルダーで行われた追加、更新、および削除を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>更新する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに <strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL Drive ID]</strong>、<strong>[!UICONTROL Folder ID]</strong> を入力するかマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新する項目が含まれるサイトを選択し、ドライブを選択して、フォルダーを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> トークンは、モジュールが変更の取得を開始する時点を識別します。  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL SharePoint] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL SharePoint] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://graph.microsoft.com</code> からの相対パスを入力します。例：<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>標準の JSON オブジェクトの形式でリクエストのヘッダーを追加します（例：<code>{"Content-type":"application/json"}</code>）。認証ヘッダーは [!DNL Workfront Fusion] によって追加されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>API 呼び出しで送信するデータのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p>JSON で <code>if</code> のような条件ステートメントを使用する場合、条件文の外側に引用符を置きます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### イベントを監視する

このインスタントトリガーモジュールは、SharePoint で項目が追加、更新、または削除されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
  <!--
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL SharePoint] account to [!DNL Workfront Fusion], see <a href="#connect-sharepoint-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect [!DNL SharePoint] to [!DNL Workfront Fusion]</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>既存の web フックを選択するか、「追加」をクリックして新しい web フックを作成します。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
