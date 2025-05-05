---
title: SharePoint モジュール
description: 1 つのシナリオで  [!DNL Adobe Workfront Fusion] 、Microsoft SharePoint Onlineを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '3124'
ht-degree: 59%

---

# Microsoft SharePoint Online モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、Microsoft SharePoint Onlineを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

Microsoft SharePoint Online モジュールを使用するには、Microsoft SharePoint Online アカウントが必要です。

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

## Microsoft SharePoint Onlineの [!DNL Workfront Fusion] への接続 {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [Microsoft SharePoint Onlineと  [!DNL Workfront Fusion]  アカウントを使用した  [!DNL Microsoft]  の接続](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [詳細設定を使用して  [!DNL Workfront Fusion] Microsoft SharePoint Onlineのへの接続](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)

### [!DNL Microsoft] アカウントを使用したMicrosoft SharePoint Onlineの [!DNL Workfront Fusion] への接続

[!DNL Microsoft] アカウントを使用して、Microsoft SharePoint Onlineへの接続を作成できます。 [!DNL Sharepoint] アカウントを [!DNL Workfront Fusion] に接続する手順については、[ [!DNL Adobe Workfront Fusion]  への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

### 詳細設定を使用したMicrosoft SharePoint Onlineの [!DNL Workfront Fusion] への接続

[!DNL Microsoft] アカウントを使用せずにMicrosoft SharePoint Onlineを [!DNL Workfront Fusion] に接続するには、クライアント ID、クライアント秘密鍵、テナント ID が必要です。

1. **[!UICONTROL 2&rbrace;Microsoft SharePoint Online]** ボックスの上部付近にある「追加 **をクリックして、**&#x200B;[!UICONTROL &#x200B; 接続を作成 &#x200B;]&#x200B;**ボックスを開きます。**

1. （オプション）デフォルトの&#x200B;**[!UICONTROL 接続名]**&#x200B;を変更
1. 「**[!UICONTROL 詳細設定を表示]**」をクリック
1. Microsoft SharePoint Online **[!UICONTROL クライアント ID]** と **[!UICONTROL クライアントシークレット]** を入力します。

1. 「**[!UICONTROL 続行]**」をクリックします。
1. 表示されるログインウィンドウで、アプリにログインするための資格情報を入力します（まだ入力していない場合）。
1. （条件付き）「**[!UICONTROL 許可]**」ボタンが表示されたら、ボタンをクリックしてアプリを [!DNL Workfront Fusion] に接続します。

## Microsoft SharePoint Online モジュールとそのフィールド

Microsoft SharePoint Online モジュールを設定すると、以下に示 [!DNL Workfront Fusion] フィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のMicrosoft SharePoint Online フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

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

#### ファイルを作成

このモジュールは、SharePoint で行われた変更を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>変更を取得するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>、および <strong>[!UICONTROL フォルダー ID]</strong> を、ファイルを作成する場所に入力するかマップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>ファイルを作成する場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
      <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p>
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
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>作成するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>、および <strong>[!UICONTROL フォルダー ID]</strong> を入力するか、フォルダーを作成する場所にマップします。</p> </li> 
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
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>取得するファイルの <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL ファイル ID]</strong> を入力またはマップします。</p> </li> 
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
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに、<strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong> および<strong>[!UICONTROL folder ID]</strong> を入力またはマッピングします。</p> </li> 
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

* [[!UICONTROL &#x200B; 項目をコピー &#x200B;]](#copy-an-item)
* [[!UICONTROL 項目の作成]](#create-an-item)
* [[!UICONTROL 項目の削除]](#delete-an-item)
* [[!UICONTROL 項目の取得]](#get-an-item)
* [[!UICONTROL 項目のリスト]](#list-items)
* [[!UICONTROL 項目の移動]](#move-an-item)
* [[!UICONTROL 項目の更新]](#update-an-item)
* [[!UICONTROL 項目の監視]（予定）](#watch-items-scheduled)


#### [!UICONTROL &#x200B; 項目をコピー &#x200B;]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">サイト ID、ドライブ ID およびフォルダー ID の入力</td> 
   <td> <p>コピーする項目を含むサイトとドライブの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>コピーする項目の <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>、および <strong>[!UICONTROL 項目 ID]</strong> を入力またはマップします。</p> </li> 
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

#### [!UICONTROL 項目の作成]

このアクションモジュールは、SharePoint リストに新しい項目を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Create an Item]</td> 
   <td> <p>アイテムを作成するサイトとドライブの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL サイト ID]</strong> と <strong>[!UICONTROL リスト ID]</strong> を入力またはマップし、アイテムを作成します。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の作成先となるリストが含まれているサイトを選択したあと、そのリストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>新しいアイテムに設定する各フィールドについて、<b> アイテムの追加 </b> をクリックし、フィールドのキー（フィールドを識別する）と、そのフィールドに新しいアイテムに設定する値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目の削除]

このアクションモジュールは、SharePoint リスト内の既存の項目を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>削除する項目を含んだサイトおよびリストを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>削除する項目の <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL アイテム ID]</strong> を入力またはマップします。</p> </li> 
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
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get an Item]</td> 
   <td> <p>取得する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>データを返すアイテムの <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL アイテム ID]</strong> を入力するか、マップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の取得元のリストが含まれるサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目をリスト]

このアクションモジュールは、指定されたリスト内のすべての項目のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Items]</td> 
   <td> <p>項目を取得するリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>項目を一覧表示するリストの <strong>[!UICONTROL サイト ID]</strong> と <strong>[!UICONTROL リスト ID]</strong> を入力またはマップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の取得元のリストが含まれるサイトを選択し、リストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返す項目の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目を移動]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">サイト ID、ドライブ ID およびフォルダー ID の入力</td> 
   <td> <p>移動する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>移動する項目の <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL アイテム ID]</strong> を入力またはマップします。</p> </li> 
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

#### [!UICONTROL 項目を更新]

このアクションモジュールは、SharePoint リスト内の既存の項目を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>更新する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>更新する項目の <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL アイテム ID]</strong> を入力またはマップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新する項目が含まれるサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>新しいアイテムの更新を行うフィールドごとに、<b> アイテムの追加 </b> をクリックし、フィールドのキー（フィールドを識別する）と、そのフィールドにアイテムに設定する新しい値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目を監視]（予定）

このトリガーモジュールは、項目が作成または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>作成時刻（新しい項目）または変更時刻（更新された項目）のどちらでリストを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>監視するサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>監視する <strong>[!UICONTROL サイト ID]</strong> と <strong>[!UICONTROL リスト ID]</strong> を入力またはマップします。</p> </li> 
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

* [[!UICONTROL リストを作成]](#create-a-list)
* [[!UICONTROL リストを取得]](#get-a-list)
* [[!UICONTROL リストをリスト]](#list-lists)
* [[!UICONTROL リストを監視]](#watch-lists)

#### [!UICONTROL リストを作成]

このアクションモジュールは、SharePoint に新しいリストを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Site ID]</td> 
   <td> <p>リストを作成するサイトを識別する方法を選択します。</p> 
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
   <td>新しいリストに設定する列ごとに、[<b> 項目の追加 </b>] をクリックし、フィールドに <strong>[!UICONTROL 名 &#x200B;]</strong> を入力して、新しい列に設定する値の <strong>[!UICONTROL 型 &#x200B;]</strong> を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストを取得]

このアクションモジュールは、指定されたリストのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a List]</td> 
   <td> <p>取得する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>返す <strong>[!UICONTROL サイト ID]</strong> と <strong> リスト ID</strong> を入力またはマップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するリストが含まれるサイトを選択し、リストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストを一覧表示]

このアクションモジュールは、指定したサイト内のすべての項目のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Lists]</td> 
   <td> <p>リストを取得するサイトを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>返すリストを含む <strong>[!UICONTROL サイト ID]</strong> を入力するか、マップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するリストが含まれているサイトを選択します。ドロップダウンは、フォローしているサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すリストの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストを監視]

このトリガーモジュールは、リストの作成または変更時にシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>作成時刻（新しい項目）または変更時刻（更新された項目）のどちらでリストを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイト ID の入力 &#x200B;]</td> 
   <td> <p>リストで監視するサイトの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>リストを監視する場所に <strong>[!UICONTROL サイト ID]</strong> 入力するかマップします。</p> </li> 
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

#### [!UICONTROL ページを取得]

このアクションモジュールは、指定されたページのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Page]</td> 
   <td> <p>取得するページを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> および <strong>[!UICONTROL Page ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するページを含むサイトを選択し、ページを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### サイト

* [[!UICONTROL サイトを取得]](#get-a-site)
* [[!UICONTROL サイトを検索]](#search-sites)

#### [!UICONTROL サイトを取得]

このアクションモジュールは、指定されたサイトのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
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

#### [!UICONTROL サイトを検索]

このアクションモジュールは、指定したパラメーターでサイトを検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>更新する項目を含むサイトとドライブの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに、<strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL Drive ID]</strong>、<strong>[!UICONTROL Folder ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新する項目が含まれるサイトを選択し、ドライブを選択して、フォルダーを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> トークンは、モジュールが変更の取得を開始する時点を識別します。  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL API 呼び出しを実行]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint Onlineの [!DNL Workfront Fusion]</a> への接続」を参照してください。</p> </td> 
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
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例えば、<code>{"Content-type":"application/json"}</code>。認証ヘッダーは [!DNL Workfront Fusion] によって追加されます。</p> </td> 
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
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to [!DNL Workfront Fusion], see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to [!DNL Workfront Fusion]</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>既存の Webhook を選択するか、「追加」をクリックして接続を入力し、新しい Webhook を作成します。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
