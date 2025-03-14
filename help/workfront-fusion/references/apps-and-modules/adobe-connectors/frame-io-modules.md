---
title: Frame.io モジュール
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io]  アカウント'
author: Becky
feature: Workfront Fusion
exl-id: 121b145c-d04d-44b9-b673-ea2928e2346d
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2510'
ht-degree: 80%

---

# [!DNL Frame.io] モジュール

[!DNL Adobe Workfront Fusion] [!DNL Frame.io] モジュールでは、[!DNL Frame.io] アカウント内のアセットとコメントを監視、作成、更新、取得、削除できます。

Frame.io コネクタの紹介ビデオについては、以下を参照してください。

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

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

[!DNL Frame.io] モジュールを使用するには、[!DNL Frame.io] アカウントが必要です。

## Frame.io API 情報

Frame.io コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.frame.io/v2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Frame.io] から [!UICONTROL Adobe Workfront Fusion] への接続

[!DNL Frame.io] には、API トークンまたは OAuth 2.0 を使用して接続できます。

[API トークンを使用した  [!DNL Frame.io]  への接続](#connect-to-frameio-using-an-api-token)

[OAuth 2.0 PKCE を使用した  [!DNL Frame.io]  への接続](#connect-to-frameio-using-oauth-20-pkce)

### API トークンを使用した [!DNL Frame.io] への接続

API トークンを使用して [!DNL Frame.io] アカウントを [!DNL Workfront Fusion] に接続するには、[!DNL Frame.io] アカウントで API トークンを作成して [!DNL Workfront Fusion] [!DNL Frame.io] の「[!UICONTROL 接続を作成]」ダイアログに挿入する必要があります。

1. [!DNL Frame.io] アカウントにログインします。
1. [!DNL Frame.io] Developer の「**[!UICONTROL トークン]**」ページに移動します。
1. 「**[!UICONTROL 新規]**」をクリックします。
1. トークンの名前を入力して使用する範囲を選択し、「**[!UICONTROL 作成]**」をクリックします。
1. 提供されたトークンをコピーします。
1. [!DNL Workfront Fusion] に移動して、[!DNL Frame.io] モジュールの「**[!UICONTROL 接続を作成]**」ダイアログを開きます。
1. 「**[!UICONTROL 接続タイプ]**」フィールドで「**[!DNL Frame.io]**」を選択します。
1. 手順 5 でコピーしたトークンを「**[!UICONTROL [!DNL Frame.io] API キー]** フィールドに入力します
1. 「**[!UICONTROL 続行]**」をクリックして接続を確立し、モジュールに戻ります。

### OAuth 2.0 PKCE を使用した [!DNL Frame.io] への接続

OAuth 2.0 PKCE とオプションのクライアント ID を使用して、[!DNL Frame.io] への接続を作成できます。接続にクライアント ID を含める場合は、[!DNL Frame.io] アカウントで OAuth 2.0 アプリを作成する必要があります。

* [OAuth 2.0 PKCE（クライアント ID なし）を使用した  [!DNL Frame.io]  への接続](#connect-to-frameio-using-using-oauth-20-pkce-without-client-id)
* [OAuth 2.0 PKCE（クライアント ID あり）を使用した  [!DNL Frame.io]  への接続](#connect-to-frameio-using-using-oauth-20-pkce-with-client-id)

#### OAuth 2.0 PKCE（クライアント ID なし）を使用した [!DNL Frame.io] への接続

1. [!DNL Workfront Fusion] に移動して、[!DNL Frame.io] モジュールの「**[!UICONTROL 接続を作成]**」ダイアログを開きます。
1. 「**[!UICONTROL 接続タイプ]**」フィールドで「**[!UICONTROL [!DNL Frame.io]OAuth 2.0 PKCE]**」を選択します。
1. 新しい接続の名前を「**[!UICONTROL 接続名]**」フィールドに入力します。
1. 「**[!UICONTROL 続行]**」をクリックして接続を確立し、モジュールに戻ります。

#### OAuth 2.0 PKCE（クライアント ID あり）を使用した [!DNL Frame.io] への接続

1. [!DNL Frame.io] で OAuth 2.0 アプリを作成します。手順については、[!DNL Frame.io] ドキュメントの [!UICONTROL OAuth 2.0 コード承認フロー] を参照してください。

   >[!IMPORTANT]
   >
   >[!DNL Frame.io] で OAuth 2.0 アプリを作成する際には：
   >
   >* リダイレクト URI として次のように入力します。
   >   
   >     * **アメリカ / APAC**:`https://app.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >     * **EMEA**: `https://app-eu.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >* 「PCKE」オプションを有効にします。


1. 提供された `client_id` をコピーします。
1. [!DNL Workfront Fusion] に移動して、[!DNL Frame.io] モジュールの「**[!UICONTROL 接続を作成]**」ダイアログを開きます。
1. 「**[!UICONTROL 接続タイプ]**」フィールドで「**[!UICONTROL [!DNL Frame.io]OAuth 2.0 PKCE]**」を選択します。
1. 新しい接続の名前を「**[!UICONTROL 接続名]**」フィールドに入力します。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 手順 2 でコピーした `client_id` を「**[!UICONTROL クライアント ID]**」フィールドに入力します。
1. 「**[!UICONTROL 続行]**」をクリックして接続を確立し、モジュールに戻ります。

## [!DNL Frame.io] モジュールとそのフィールド

[!DNL Frame.io] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Frame.io] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アセット](#assets)
* [コメント](#comments)
* [プロジェクト](#projects)
* [その他](#other)

### アセット

* [[!UICONTROL アセットの作成]](#create-an-asset)
* [[!UICONTROL アセットの削除]](#delete-an-asset)
* [[!UICONTROL アセットの取得]](#get-an-asset)
* [[!UICONTROL アセットの一覧表示]](#list-assets)
* [[!UICONTROL アセットの更新]](#update-an-asset)
* [[!UICONTROL 削除されたアセットの監視]](#watch-asset-deleted)
* [[!UICONTROL 更新されたアセットラベルの監視]](#watch-asset-label-updated)
* [[!UICONTROL 新しいアセットの監視]](#watch-new-asset)

#### [!UICONTROL アセットの作成]

このアクションモジュールでは、新しいアセットを作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>アセットを作成するプロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>アセットを作成するプロジェクトを選択するか、プロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>アセットを作成するフォルダーを選択するか、フォルダーの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>フォルダーを作成するか、ファイルを作成するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>新規ファイルまたはフォルダーの名前を入力します。</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">File Type </td> 
    <td> <p>Select the type of file you want to upload.</p> </td> 
   </tr>
  --> <!--
   <tr> 
    <td role="rowheader">File Size </td> 
    <td> <p>The file size in bytes.</p> </td> 
   </tr>
  --> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>ファイルを作成する場合、アップロードするファイルの URL を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>ファイルを作成する場合、アセットの簡単な説明を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ラベル ] </td> 
   <td> <p>ファイルを作成する場合は、ファイルが進行中か、レビューが必要か、承認済みかを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットを削除]

このアクションモジュールは、指定したアセットを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>削除するアセットが含まれるプロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> 削除するアセットが含まれるプロジェクトまたはプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>削除するアセットを含むフォルダーを選択</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>削除するアセットを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットを取得]

このアクションモジュールは、アセットの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>詳細を取得するアセットを含むプロジェクトを所有するチームを、選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> 詳細を取得するアセットを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>詳細を取得するアセットを含むフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>詳細を取得するアセットを選択するか、そのアセットの ID をマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットを一覧表示]

この検索モジュールは、指定されたプロジェクトのフォルダー内のすべてのアセットを取得します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>アセットを取得するフォルダーを含む、プロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> アセットを取得するフォルダーを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>アセットのリストを表示するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットの更新]

このアクションモジュールを使用すると、既存のアセットの名前、説明、またはカスタムフィールドを更新できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>アセットを更新するプロジェクトを所有する、チームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>アセットを更新するプロジェクトを選択するか、プロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>アセットを更新するフォルダーを選択するか、フォルダーの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>更新するアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>更新したファイルの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>更新したアセットの簡単な説明を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 削除されたアセットを監視]

このトリガーモジュールは、指定されたチームに属するアセットが削除されると、シナリオを開始します。

これはインスタントトリガーなので、使用するモジュールの Webhook を選択または作成する必要があります。

Webhook を追加する場合は、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Webhook の名前（「Asset deleted」など）を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>この Web フックが作成されるチームを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新されたアセットラベルを監視]

このトリガーモジュールは、指定されたチームセット、変更または削除されたアセットのラベルが所有する場合にシナリオを開始します。

これはインスタントトリガーなので、使用するモジュールの Webhook を選択または作成する必要があります。

Webhook を追加する場合は、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Webhook の名前（「アセットステータスが更新されました」など）を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>この Web フックが作成されるチームを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 新しいアセットを見つける]

このトリガーモジュールは、指定されたチームの新しいアセットが作成されると、シナリオを開始します。

これはインスタントトリガーなので、使用するモジュールの Webhook を選択または作成する必要があります。

Webhook を追加する場合は、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Webhook の名前（「Asset created」など）を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>この Web フックが作成されるチームを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### コメント

* [[!UICONTROL コメントを作成]](#create-a-comment)
* [[!UICONTROL コメントを削除]](#delete-a-comment)
* [[!UICONTROL コメントを取得]](#get-a-comment)
* [[!UICONTROL コメントをリスト]](#list-comments)
* [[!UICONTROL コメントをアップデート]](#update-a-comment)
* [[!UICONTROL 更新されたコメントを監視]](#watch-comment-updated)
* [[!UICONTROL 新規コメントを監視]](#watch-new-comment)

#### [!UICONTROL コメントを作成]

このアクションモジュールは、新しいコメントまたは返信をアセットに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Frame.io] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>コメントを作成するか、コメントに返信するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>コメントを追加するアセットを含むプロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>プロジェクトを選択するか、コメントを追加するアセットが含まれるプロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>フォルダーを選択するか、コメントを追加するアセットが含まれるフォルダーの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>コメントを追加するアセットを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>返信を追加するコメントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> コメントまたは返信のテキスト内容を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>コメントのリンク先となるビデオのフレーム番号を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントの削除]

このアクションモジュールは、既存のコメントを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID]</td> 
   <td> <p> コメントを削除するアセットを含むプロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> コメントを削除するアセットを含むプロジェクトを選択するか、プロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p> コメントを削除するアセットを含むフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>削除するコメントを含むアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>削除するコメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントを取得]

このアクションモジュールは、指定されたコメントの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>アセットを取得するフォルダーを含む、プロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>アセットを取得するフォルダーを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>アセットのリストを表示するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>取得するコメントを含むアセットを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>詳細を取得するコメントを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントをリスト]

この検索モジュールは、指定されたアセットのすべてのコメントを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>コメントを取得するフォルダーを含む、プロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>コメントを取得するフォルダーを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>コメントのリストを表示するアセットを含むフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>コメントのリストを表示するアセットを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが返すコメントの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントの更新]

このアクションモジュールは、既存のコメントを編集します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>コメントを更新するアセットを含むプロジェクトを所有するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>コメントを更新するアセットを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>コメントを更新するアセットを含むフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>コメントを更新するアセットを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>更新するコメントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> コメントのテキストコンテンツを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>コメントのリンク先となるビデオのフレーム番号を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新されたコメントを監視]

このトリガーモジュールは、コメントが編集されたときにシナリオを開始します。

これはインスタントトリガーなので、使用するモジュールの Webhook を選択または作成する必要があります。

Webhook を追加する場合は、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Web フックの名前（例：「編集されたコメント」）を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>この Web フックが作成されるチームを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 新規コメントを監視]

このトリガーモジュールは、新しいコメントまたは返信が作成されたときにシナリオを開始します。

これはインスタントトリガーなので、使用するモジュールの Webhook を選択または作成する必要があります。

Webhook を追加する場合は、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Web フックの名前（例：新規コメント）を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>この Web フックが作成されるチームを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### プロジェクト

#### [!UICONTROL プロジェクトのリスト]

この検索モジュールは、指定したチームのすべてのプロジェクトを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>プロジェクトを取得するチームを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>各シナリオ実行サイクルでモジュールが返すプロジェクトの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

#### [!UICONTROL API 呼び出しの実行]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Frame.io] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://api.frame.io</code> からの相対パスを入力します。例： <code> /v2/teams</code></p> <p>メモ：使用可能なエンドポイントの一覧については、[!DNL Frame.io] API リファレンスを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>リクエストクエリ文字列を入力します。クエリ文字列に含める各パラメーターに対して、<b>[!UICONTROL Add item]</b> をクリックして、フィールドの名前と必要な値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


<!-- 
**Example:** The following API call returns all teams and its details in your [!DNL Frame.io] account:

URL: `/v2/teams`

Method: `GET`

![API call example](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

The result can be found in the module's Output under Bundle > Body.

In our example, the details of 1 team were returned:

![API call output](/help/workfront-fusion/references/apps-and-modules/assets/api-call-output.png)

-->
