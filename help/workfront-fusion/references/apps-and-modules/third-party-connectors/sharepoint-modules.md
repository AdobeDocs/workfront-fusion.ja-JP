---
title: SharePoint モジュール
description: Adobe Workfront Fusion のシナリオでは、Microsoft SharePoint Onlineを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '4130'
ht-degree: 48%

---

# Microsoft SharePoint Online モジュール

Adobe Workfront Fusion のシナリオでは、Microsoft SharePoint Onlineを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[&#x200B; シナリオの作成：記事のインデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

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

## Microsoft SharePoint OnlineのWorkfront Fusion への接続 {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [アカウントを使用してMicrosoft SharePoint OnlineをWorkfront Fusion [!DNL Microsoft]  接続](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [詳細設定を使用したMicrosoft SharePoint OnlineのWorkfront Fusion への接続](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)
* [証明書認証を使用した、Microsoft SharePoint OnlineのWorkfront Fusion への接続](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-certificate-authorization)

### [!DNL Microsoft] アカウントを使用してMicrosoft SharePoint OnlineをWorkfront Fusion に接続する

[!DNL Microsoft] アカウントを使用して、Microsoft SharePoint Onlineへの接続を作成できます。 [!DNL Sharepoint] アカウントを Workfront Fusion に接続する手順について詳しくは、[Adobe Workfront Fusion への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください

### 詳細設定を使用したMicrosoft SharePoint OnlineのWorkfront Fusion への接続

接続に資格情報を含めるには、「詳細設定を表示」オプションを有効にします。 このタイプの接続の場合は、クライアント ID、クライアント秘密鍵およびテナント ID が必要になります。

1. 任意のSharePoint モジュールで、「接続」フィールドの近くにある **[!UICONTROL 追加]** をクリックして、**[!UICONTROL 接続を作成]** ボックスを開きます。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection type]</p> </td> 
      <td>クライアントの資格情報を使用するには、「<b>Microsoft 365 メール </b>」を選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>接続に名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client ID]</p> </td> 
      <td>接続先のSharePoint アプリケーションのクライアント ID を入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client secret]</p> </td> 
      <td>接続先のSharePoint アプリケーションのクライアントの秘密鍵を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL テナント ID]</p> </td> 
      <td>接続先のSharePoint アプリケーションのテナント ID を入力します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

### 証明書認証を使用した、Microsoft SharePoint OnlineのWorkfront Fusion への接続

証明書認証を使用してSharePointに接続できます。

>[!IMPORTANT]
>
>証明書認証を使用するには、まずMicrosoft Entra でアプリを作成し、そこに証明書をアップロードする必要があります。
>
>手順については、Microsoft ドキュメントの [Microsoft Entra 証明書ベースの認証の認証機関を設定する方法 &#x200B;](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-configure-certificate-authorities) を参照してください。

1. 任意のSharePoint モジュールで、「接続」フィールドの近くにある **[!UICONTROL 追加]** をクリックして、**[!UICONTROL 接続を作成]** ボックスを開きます。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection type]</p> </td> 
      <td>証明書認証を使用するには、<b>Microsoft SharePoint Online（証明書の認証） </b> を選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>接続に名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client ID]</p> </td> 
      <td>接続先のSharePoint アプリケーションのクライアント ID を入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 拇印 &#x200B;]</p> </td> 
      <td>接続先のSharePoint アプリケーションの拇印を入力します。</td> 
     </tr> 
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Microsoftで資格情報を作成したときに生成された証明書または秘密鍵を入力します。 </p>
          <p>秘密鍵または証明書を抽出するには：</p>
          <ol>
            <li>
              <p><b>[!UICONTROL Extract]</b> をクリックします。</p>
            </li>
            <li>
            <p>証明書と秘密鍵のどちらを抽出するかを選択します。</li>
            <li>
              <p>抽出するファイルのタイプを選択します。</p>
            </li>
            <li>
              <p>秘密鍵または証明書を含むファイルを選択します。</p>
            </li>
            <li>
              <p>ファイルのパスワードを入力します。</p>
            </li>
            <li>
              <p><b>[!UICONTROL Save]</b> をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody> 
   </table>

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

## Microsoft SharePoint モジュールとそのフィールド

Workfront Fusion でMicrosoft SharePoint Online モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のMicrosoft SharePoint Online フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

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
* [フォルダーの取得](#get-a-folder)
* [フォルダーまたはファイルの更新](#update-a-folder-or-a-file)
* [フォルダー項目の監視](#watch-folder-items)

#### ファイルを作成

このモジュールは、SharePoint で行われた変更を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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

#### フォルダーの取得

このモジュールは、指定されたフォルダーに関する詳細を取得しました

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイト、ドライブ、およびファイルを入力                IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>取得するフォルダーの <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL フォルダーパス &#x200B;]</strong> を入力するか、マップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>フォルダーの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### フォルダーまたはファイルの更新

フォルダーまたはファイルのメタデータを更新します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイト、ドライブ、およびファイルを入力                IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>取得するフォルダまたはファイルの <strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>、および <strong>[!UICONTROL フォルダまたはアイテム ID]</strong> を入力またはマップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>フォルダーの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  </tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>更新するメタデータフィールドごとに、「<b> 項目を追加 </b> をクリックし、フィールドのパスと値を入力します。</td> 
  <tr>
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td>Workfront Fusion が 1 つのシナリオの実行サイクルで返す最大項目数を入力します。</td> 
  <tr>
  </tr>
</tbody> 
</table>

### 項目

* [[!UICONTROL &#x200B; 項目をコピー &#x200B;]](#copy-an-item)
* [[!UICONTROL 項目の作成]](#create-an-item)
* [[!UICONTROL 項目の削除]](#delete-an-item)
* [[!UICONTROL 項目の取得]](#get-an-item)
* [詳細を取得](#get-details)
* [[!UICONTROL 項目のリスト]](#list-items)
* [[!UICONTROL 項目を移動]](#move-an-item)
* [[!UICONTROL &#x200B; 項目を更新 &#x200B;]](#update-an-item)
* [[!UICONTROL 項目の監視]（予定）](#watch-items-scheduled)


#### [!UICONTROL &#x200B; 項目をコピー &#x200B;]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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

#### 詳細を取得

このモジュールは、指定された URL から項目の詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Web URL</td> 
   <td> 詳細を取得する項目の URL を入力またはマッピングします。 </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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

* [ページの取得](#get-a-page)
* [リストページ](#list-pages)
* [ページを公開](#publish-a-page)
* [ページのウォッチ](#watch-pages)

#### [!UICONTROL ページを取得]

このアクションモジュールは、指定されたページのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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

#### リストページ

このモジュールは、すべてのページのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL リスト ページ &#x200B;]</td> 
   <td> <p>リストするページの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>一覧表示するページを含むサイトの <strong>[!UICONTROL サイト ID]</strong> を入力するか、マップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>リストするページを含むサイトを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す最大ページ数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### ページを公開

このアクションモジュールは、選択したページの最新バージョンを公開します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ページを公開 &#x200B;]</td> 
   <td> <p>公開するページの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> および <strong>[!UICONTROL Page ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>公開するページを含んだサイトを選択し、ページを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### ページのウォッチ

このトリガーモジュールは、指定したサイトでページが変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイト ID の入力 &#x200B;]</td> 
   <td> <p>リストするページの識別方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>監視するページを含むサイトの <strong>[!UICONTROL サイト ID]</strong> を入力するか、マップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>ウォッチするページを含むサイトを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返す最大ページ数を入力またはマッピングします。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineのWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
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
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例えば、<code>{"Content-type":"application/json"}</code>。Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
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
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to Workfront Fusion, see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>既存の Webhook を選択するか、「追加」をクリックして接続を入力し、新しい Webhook を作成します。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
