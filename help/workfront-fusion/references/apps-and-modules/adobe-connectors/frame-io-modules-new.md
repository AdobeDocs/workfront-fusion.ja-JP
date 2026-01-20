---
title: Frame.io モジュール
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io]  アカウント。'
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: 3cb613c11500dfc94774783ee0b38e6f1768de20
workflow-type: ht
source-wordcount: '4539'
ht-degree: 100%

---

# [!DNL Frame.io] V4 モジュール

>[!IMPORTANT]
>
>この記事では、Frame.io コネクターの新しいバージョンについて説明します。このコネクターは、Frame.io バージョン 4 への接続に使用します。
>
>Frame.io コネクターのレガシーバージョンの手順について詳しくは、[Frame.io レガシーコネクター](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)を参照してください。

Adobe Workfront Fusion [!DNL Frame.io] モジュールでは、[!DNL Frame.io] アカウント内のアセットとコメントを監視、作成、更新、取得、削除できます。

Workfront には、接続先の Frame.io のバージョンに基づく 2 つの Frame.io コネクターが用意されています。

| コネクター | Frame.io バージョン |
|---|---|
| Frame.io | V4 |
| Frame.io（レガシー） | V3 |

Frame.io コネクターのレガシーバージョンの手順について詳しくは、[Frame.io レガシーコネクター](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)を参照してください。


Frame.io コネクタの紹介ビデオについては、以下を参照してください。

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意の Adobe Workfront Workflow パッケージと任意の Adobe Workfront Automation および Integration パッケージ</p><p>Workfront Ultimate</p><p>Workfront Fusion を追加購入した Workfront Prime および Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>Work またはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

[!DNL Frame.io] モジュールを使用するには、[!DNL Frame.io] アカウントが必要です。

## Frame.io API 情報

Frame.io コネクターは、次を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.frame.io/v4</td> 
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

ユーザー資格情報を使用して自動的に接続したり、ユーザー資格情報の接続を手動で作成したり、サーバー間接続を作成したりできます。

* [ユーザーの資格情報を使用して自動的に接続](#connect-automatically-with-user-credentials#)
* [ユーザー資格情報接続の手動作成](#create-a-user-credentials-connection-manually)
* [サーバー間接続の作成](#create-a-server-to-server-connection)

### ユーザーの資格情報を使用して自動的に接続

この方法では、Frame.io にログインしている場合に自動的に接続が作成されます。または、Frame.io のログインページに接続され、ログインできるようになります。

1. 任意の Frame.io モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 接続に名前を入力します。
1. 「**続行**」をクリックします。
1. Frame.io アカウントにログインするように求められたら、ログインします。
1. 複数の Frame.io 組織に属している場合は、この接続に使用する組織を選択します。

接続が作成されます。

### ユーザー資格情報接続の手動作成

ユーザー資格情報接続を作成するには、Frame.io にログインするか、クライアント ID またはクライアントシークレットを指定します。

サーバー間接続を作成するには、まず Adobe Developer Console にアプリケーションを設定する必要があります。

* [Adobe Developer Console でのユーザー資格情報の作成](#create-user-credentials-in-the-adobe-developer-console)
* [ユーザー認証接続の設定](#configure-a-user-authentication-connection)

#### Adobe Developer Console でのユーザー資格情報の作成

Adobe Developer Console プロジェクトのサーバー間資格情報がまだない場合は、作成できます。

1. [Adobe Developer Console](https://developer.adobe.com/) を開きます。
1. この接続に使用する既存のプロジェクトを Adobe Developer Console で選択します。

   または

   Adobe Developer Console で新規プロジェクトを作成します。手順について詳しくは、[空のプロジェクトの作成](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)を参照してください。

1. プロジェクトの概要ページまたは新しいプロジェクトの基本を学ぶページで、「**API を追加**」をクリックします。
1. 開いたページで、**Frame.io API** を見つけてクリックします。
1. 認証タイプを選択ページで「**ユーザー認証**」を選択し、「**次へ**」をクリックします。
1. ユーザー認証資格情報を追加ページで、「**OAuth Web アプリ**」を選択し、「**次へ**」をクリックします。
1. OAuth Web アプリ資格情報を設定ページで、次を入力します。   <table style="table-layout:auto">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Default redirect URI]</td>
          <td>
            <p><code>https://oauth.app.workfrontfusion.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Redirect URI pattern]</td>
          <td>
            <p><code>https://oauth\.app\.workfrontfusion\.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
       </tbody>
    </table>
1. 「**次へ**」をクリックします。
1. 「**設定済み API を保存**」をクリックします。
1. 製品ページで、作成した資格情報のカードをクリックします。

   ここでは、クライアント ID とクライアントシークレットを確認できます。

>[!NOTE]
>
> Adobe Workfront Fusion で接続の設定を開始する際は、このウィンドウを開いたままにすることをお勧めします。クライアント ID をコピーし、このページからクライアントシークレットを取得およびコピーして、接続フィールドに貼り付けることができます。


#### ユーザー認証接続の設定

1. 任意の Frame.io モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 「接続を作成」ボックスで、「**詳細設定を表示**」をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection type]</td>
          <td>
            <p>「<b>IMS ユーザー認証</b>」を選択します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>この接続の名前を入力します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]</td>
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の作成手順について詳しくは、この記事の <a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">Adobe Developer Console でのユーザー資格情報の作成</a>を参照してください。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の作成手順について詳しくは、この記事の <a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">Adobe Developer Console でのユーザー資格情報の作成</a>を参照してください。</p>
        </tr>
       </tbody>
    </table>
1. Frame.io アカウントにログインするように求められたら、ログインします。
1. 複数の Frame.io 組織に属している場合は、この接続に使用する組織を選択します。

接続が作成されます。


### サーバー間接続の作成

サーバー間接続を作成するには、まず Adobe Developer Console にアプリケーションを設定する必要があります。

* [Adobe Developer Console でのサーバー間資格情報の作成](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [サーバー間接続の設定](#configure-a-server-to-server-connection)

#### Adobe Developer Console でのサーバー間資格情報の作成

Adobe Developer Console プロジェクトのサーバー間資格情報がまだない場合は、作成できます。

1. [Adobe Developer Console](https://developer.adobe.com/) を開きます。
1. この接続に使用する既存のプロジェクトを Adobe Developer Console で選択します。

   または

   Adobe Developer Console で新規プロジェクトを作成します。手順について詳しくは、[空のプロジェクトの作成](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)を参照してください。

1. プロジェクトの概要ページまたは新しいプロジェクトの基本を学ぶページで、「**API を追加**」をクリックします。
1. 開いたページで、**Frame.io API** を見つけてクリックします。
1. 認証タイプを選択ページで「**サーバー間認証**」を選択し、「**次へ**」をクリックします。
1. 資格情報の名前を入力します。これにより、後で Adobe Admin Console の API 資格情報領域で資格情報を識別できます。
1. 「**次へ**」をクリックします。
1. 製品プロファイルを選択ページで、接続先の Frame.io アカウントを含む製品プロファイルを選択します。
1. 「**設定済み API を保存**」をクリックします。
1. 製品ページで、作成した資格情報のカードをクリックします。

   ここでは、クライアント ID とクライアントシークレットを確認できます。

>[!NOTE]
>
> Adobe Workfront Fusion で接続の設定を開始する際は、このウィンドウを開いたままにすることをお勧めします。クライアント ID をコピーし、このページからクライアントシークレットを取得およびコピーして、接続フィールドに貼り付けることができます。


#### サーバー間接続の設定

1. 任意の Frame.io モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection type]</td>
          <td>
            <p>「<b>IMS サーバーからサーバーへ</b>」を選択します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>この接続の名前を入力します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]</td>
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の作成手順について詳しくは、この記事の <a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">Adobe Developer Console でのサーバー間資格情報の作成</a>を参照してください。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の作成手順について詳しくは、この記事の <a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">Adobe Developer Console でのサーバー間資格情報の作成</a>を参照してください。</p>
        </tr>
       </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。




## [!DNL Frame.io] モジュールとそのフィールド

[!DNL Frame.io] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Frame.io]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アセット](#assets)
* [コメント](#comments)
* [フォルダー](#folders)
* [プロジェクト](#projects)
* [共有](#shares)
* [ワークスペース](#workspaces)
* [メタデータ](#metadata)
* [その他](#other)

### アセット

* [[!UICONTROL アセットの作成]](#create-an-asset)
* [[!UICONTROL アセットの削除]](#delete-an-asset)
* [[!UICONTROL アセットの取得]](#get-an-asset)
* [[!UICONTROL アセットのリスト]](#list-assets)
* [削除されたアセットの監視](#watch-asset-deleted)
* [新しいアセットの監視](#watch-new-asset)

#### [!UICONTROL アセットの作成] <!--different for v4-->

このアクションモジュールでは、新しいアセットを作成できます。ローカルファイルをアップロードするか、アセットを作成するリモートファイルの URL を指定できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、アセットを作成するプロジェクトを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>ワークスペースを選択するか、アセットを作成するプロジェクトを含むワークスペースの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>アセットを作成するプロジェクトを選択するか、プロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>アセットを作成するパスを選択します。</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td> <p>Enter the name of the file that you want to use for this asset.</p> </td> 
  </tr> -->
    <tr> 
    <td role="rowheader">アップロードタイプ </td> 
    <td> <p>アセットをローカルファイルから作成するか、リモートライフから作成するかを選択します。</p> </td> 
   </tr>
    <tr> 
    <td role="rowheader">ファイルサイズ </td> 
    <td> <p>ローカルファイルをアップロードする場合は、ファイルサイズをバイト単位で入力するか、マッピングします。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>リモートファイルからアセットを作成する場合、アップロードするファイルの URL を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前をマッピングします。</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">[!UICONTROL Media type] </td> 
   <td> <p>Select the media type for this asset.</p> </td> 
  </tr> -->
  </tbody> 
</table>

#### [!UICONTROL アセットの作成（レガシー）] <!--different for v4-->

このアクションモジュールでは、新しいアセットを作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、アセットを作成するプロジェクトを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>ワークスペースを選択するか、アセットを作成するプロジェクトを含むワークスペースの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>アセットを作成するプロジェクトを選択するか、プロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>アセットを作成するパスを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td> <p>このアセットに使用するファイルの名前を入力します。</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">ファイルサイズ </td> 
    <td> <p>ファイルサイズをバイト単位で入力またはマッピングします。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>ファイルを作成する場合、アップロードするファイルの URL を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Media type] </td> 
   <td> <p>このアセットのメディアタイプを選択します。</p> </td> 
  </tr> 
  </tbody> 
</table>

#### [!UICONTROL アセットの削除]

このアクションモジュールは、指定したアセットを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、削除するアセットを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>削除するアセットを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットの取得]

このアクションモジュールは、アセットの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、取得するアセットを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>取得するアセットを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットのリスト]

この検索モジュールは、指定されたプロジェクトのフォルダー内のすべてのアセットを取得します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、リストするアセットを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 返されたアセットの最大数] </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 削除されたアセットの監視

このトリガーモジュールは、アセットが削除されたときにシナリオを開始します。

このモジュールに使用する Webhook を選択するか、「Webhook」フィールドの横にある「追加」をクリックして、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>新しい Webhook の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、削除されたアセットを監視するアカウントの ID をマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 新しいアセットの監視

このトリガーモジュールは、新しいアセットが作成される際にシナリオを開始します。

このモジュールに使用する Webhook を選択するか、「Webhook」フィールドの横にある「追加」をクリックして、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>新しい Webhook の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、新しいアセットを監視するアカウントの ID をマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### コメント

* [[!UICONTROL コメントを作成]](#create-a-comment)
* [[!UICONTROL コメントを削除]](#delete-a-comment)
* [[!UICONTROL コメントを取得]](#get-a-comment)
* [[!UICONTROL コメントをリスト]](#list-comments)
* [[!UICONTROL コメントをアップデート]](#update-a-comment)
* [更新されたコメントの監視](#watch-comment-updated)
* [新規コメントの監視](#watch-new-comment)

#### [!UICONTROL コメントの作成]

このアクションモジュールは、新しいコメントまたは返信をアセットに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、コメントを追加するアセットを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>アカウントを選択するか、コメントを追加するアセットを含むワークスペースの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>プロジェクトを選択するか、コメントを追加するアセットが含まれるプロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>コメントを追加するアセットへのパスを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> コメントまたは返信のテキスト内容を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>コメントのリンク先となるビデオのフレーム番号を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page] </td> 
   <td> <p>アセットが PDF の場合は、コメントを添付するページを入力またはマッピングします。</p> </td> 
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
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、削除するコメントを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>削除するコメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントの取得]

このアクションモジュールは、指定されたコメントの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、詳細を取得するコメントを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>詳細を取得するコメントを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントのリスト]

この検索モジュールは、指定されたアセットのすべてのコメントを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>コメントを取得するアセットを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>コメントを取得するアセットを含むワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>コメントを取得するアセットを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>コメントのリストするアセットにつながるパスを選択します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 返されたコメントの最大数] </td> 
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
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>コメントを更新するアセットを含むプロジェクトを所有するアカウントを選択またはマッピングします。</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Page] </td> 
   <td> <p>アセットが PDF の場合は、コメントを添付するページを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 更新されたコメントの監視

このトリガーモジュールは、コメントが更新されたときにシナリオを開始します。

このモジュールに使用する Webhook を選択するか、「Webhook」フィールドの横にある「追加」をクリックして、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>新しい Webhook の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、更新されたコメントを監視するアカウントの ID をマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 新規コメントの監視

このトリガーモジュールは、コメントが作成されたときにシナリオを開始します。

このモジュールに使用する Webhook を選択するか、「Webhook」フィールドの横にある「追加」をクリックして、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>新しい Webhook の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、新しいコメントを監視するアカウントの ID をマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### フォルダー

#### フォルダーの作成

このアクションモジュールは、Frame.io に新しいフォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>フォルダーを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>フォルダーを作成するワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>フォルダーを作成する場所を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>フォルダーを作成するパスを選択します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>新しいフォルダーの名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### プロジェクト

* [プロジェクトの作成](#create-a-project)
* [Frame.io プロジェクトへのユーザーの招待](#invite-users-to-frameio-project)
* [プロジェクトのリスト](#list-projects)

#### プロジェクトの作成

このアクションモジュールは、Frame.io に新しいプロジェクトを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>プロジェクトを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>プロジェクトを作成するワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>新しいプロジェクトの名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Frame.io プロジェクトへのユーザーの招待

このアクションモジュールは、指定された Frame.io プロジェクトにユーザーを招待します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>ユーザーを招待するプロジェクトを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>ユーザーを招待するプロジェクトを含むワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">プロジェクト ID </td> 
   <td> <p>ユーザーを招待するプロジェクトを選択またはマッピングします。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">ユーザー ID </td> 
   <td> <p>プロジェクトに招待するユーザーを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プロジェクトのリスト]

この検索モジュールは、指定したチームのすべてのプロジェクトを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>プロジェクトを取得するアセットを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>プロジェクトを取得するアセットを含むワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 返されたプロジェクトの最大数] </td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが返すプロジェクトの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 共有

* [共有リンクへのアセットの追加](#add-an-asset-to-a-share-link)
* [共有リンクの作成](#create-a-share-link)

#### 共有リンクへのアセットの追加

このアクションモジュールは、Frame.io の共有リンクにアセットを追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アセットを追加する共有リンクを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share link ID] </td> 
   <td> <p>アセットを追加する共有リンクを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>共有リンクに追加するアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 共有リンクの作成

このアクションモジュールは、Frame.io に新しい共有リンクを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>共有リンクを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>共有リンクを作成するワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>共有リンクを作成するプロジェクトを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">アクセス </td> 
   <td> <p>このリンクへの公開アクセス権と制限アクセス権のどちらを持つかを選択します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">アセット </td> 
   <td> <p>共有リンクに追加するアセットごとに、「<b>項目を追加</b>」をクリックして、アセットの ID を入力します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">説明 </td> 
   <td> <p>共有リンクの説明を入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>共有リンクの有効期限日を入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>新しい共有リンクの名前を入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>共有リンクのパスフレーズを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### ワークスペース

#### ワークスペースの作成

このアクションモジュールは、Frame.io に新しいワークスペースを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>ワークスペースを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>ワークスペースの新しい名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### ワークスペースのリスト

このモジュールは、アカウント内のすべてのワークスペースをリストします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>ワークスペースを取得するアセットを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 返されたワークスペースの最大数] </td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが返すワークスペースの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### メタデータ

* [アカウントレベルフィールドの作成](#create-an-account-level-field)
* [アカウントレベルフィールドの削除](#delete-an-account-level-field)
* [メタデータの取得](#get-metadata)
* [アカウントレベルフィールドのリスト](#list-account-level-fields)
* [アカウントレベルフィールド定義の更新](#update-an-account-level-field-definition)
* [複数のファイルにわたるメタデータの更新](#update-metadata-across-multiple-files)

#### アカウントレベルフィールドの作成

このアクションモジュールは、新しいアカウントレベルのメタデータフィールドを作成および設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>メタデータを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">フィールドタイプ </td> 
   <td> <p>作成するメタデータフィールドのタイプを選択し、そのフィールドのオプションを設定します。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>新しいフィールドの名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### アカウントレベルフィールドの削除

このアクションモジュールは、単一のアカウントレベルのメタデータフィールドを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>削除するメタデータフィールドを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">フィールド定義 ID </td> 
   <td> <p>削除するフィールドの ID を入力またはマッピングします。アカウントレベルのフィールドをリストモジュールを使用して、フィールド ID を検索できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### メタデータの取得

このアクションモジュールは、Frame.io 内のファイルのメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>メタデータを取得するファイルを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">ファイル ID </td> 
   <td> <p>メタデータを取得するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">null を表示 </td> 
   <td> <p>このオプションを有効にすると、値が null のフィールドが出力に含まれます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### アカウントレベルフィールドのリスト

このモジュールは、指定されたアカウントに関するアカウントレベルのメタデータフィールドのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>フィールドをリストするアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned agreements]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すフィールドの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### アカウントレベルフィールド定義の更新

このモジュールは、単一の既存のメタデータフィールドの定義を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>メタデータを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">フィールド定義 ID </td> 
   <td> <p>更新するフィールドの ID を入力またはマッピングします。アカウントレベルのフィールドをリストモジュールを使用して、フィールド ID を検索できます。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">フィールドタイプ </td> 
   <td> <p>フィールドのフィールドタイプを変更する場合は、作成するメタデータフィールドのタイプを選択し、そのフィールドのオプションを設定します。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>フィールドの新しい名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 複数のファイルにわたるメタデータの更新

このモジュールは、1 つ以上のファイルのメタデータフィールドを、指定した値で更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>メタデータを更新するファイルを含むアカウントを選択するか、マッピングします。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>ワークスペースを選択するか、アセットを作成するプロジェクトを含むワークスペースの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>アセットを作成するプロジェクトを選択するか、プロジェクトの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File IDs] </td> 
   <td> <p>メタデータを更新するファイルごとに、「<b>項目を追加</b>」をクリックして、ファイルの ID を入力するか、マッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values] </td> 
   <td> <p>メタデータを更新するフィールドごとに、「<b>項目を追加</b>」をクリックし、フィールド定義の ID およびそのフィールドに入力する値を入力するか、マッピングします。「ファイル ID」フィールドで指定されたすべてのファイルが、このフィールド値で更新されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [イベントの監視](#watch-events)
* [更新されたメタデータ値の監視](#watch-metadata-value-updated)


#### [!UICONTROL カスタム API 呼び出しの実行]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://api.frame.io</code> からの相対パスを入力します。例： <code> /v4/me</code></p> <p>メモ：使用可能なエンドポイントの一覧については、[!DNL Frame.io] API リファレンスを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query string] </td> 
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

#### イベントの監視

このインスタントトリガーモジュールは、選択されたイベントが Frame.io で発生するとシナリオを開始します。

既存の Webhook を選択するか、新しい Webhook を作成できます。

新しい Webhook を作成するには：

1. 「Webhook」フィールドの横にある「**追加**」をクリックします。
1. 以下の情報を入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
     <td role="rowheader">Webhook 名 </td> 
      <td> <p>新しい Webhook の名前を入力します。</p> </td> 
     </tr> 
     <tr> 
       <td role="rowheader">[!UICONTROL Connection] </td> 
       <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
     </tr> 
     <tr> 
     <td role="rowheader">[!UICONTROL Account ID] </td> 
      <td> <p>イベントを監視するワークスペースを含むアカウントを選択するか、マッピングします。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Workspace ID]</td> 
      <td> <p>イベントを監視するワークスペースの ID を入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Events]</td> 
      <td> <p>このモジュールをトリガーするイベントを選択します。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**保存**」をクリックして Webhook を保存し、モジュールに戻ります。
1. イベントを監視モジュールで「**OK**」をクリックし、設定を保存します。


#### 更新されたメタデータ値の監視

このトリガーモジュールは、コメントが更新されたときにシナリオを開始します。

このモジュールに使用する Webhook を選択するか、「Webhook」フィールドの横にある「追加」をクリックして、次の情報を入力します。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>新しい Webhook の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順について詳しくは、この記事の<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> [!DNL Frame.io] を Adobe Workfront Fusion に接続</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>アカウントを選択するか、更新されたメタデータ値を監視するアカウントの ID をマッピングします。</p> </td> 
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
