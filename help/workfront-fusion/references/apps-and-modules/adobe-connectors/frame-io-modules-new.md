---
title: Frame.io(ベータ版)モジュール
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io]  アカウント'
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: d81785ec60dfd74583a54a75ab1bfc1a253d8faf
workflow-type: tm+mt
source-wordcount: '2168'
ht-degree: 46%

---

# [!DNL Frame.io] ベータ版(V4)モジュール

>[!IMPORTANT]
>
>この記事では、Frame.io コネクタの新しい(ベータ)バージョンについて説明します。 このコネクタは、バージョン 4 への接続 Frame.io ために使用されます。
>
>Frame.io コネクタのレガシーバージョンの手順については、[Frame.io レガシーコネクタ ](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md) を参照してください。

[!DNL Adobe Workfront Fusion] [!DNL Frame.io] モジュールでは、[!DNL Frame.io] アカウント内のアセットとコメントを監視、作成、更新、取得、削除できます。

Workfront には、接続先の Frame.io のバージョンに基づいて 2 つの Frame.io コネクタが用意されています。

| コネクタ | Frame.io バージョン |
|---|---|
| Frame.io (ベータ版) | V4 |
| Frame.io （レガシー） | V3 |

Frame.io コネクタのレガシーバージョンの手順については、[Frame.io レガシーコネクタ ](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md) を参照してください。


Frame.io コネクタの紹介ビデオについては、以下を参照してください。

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

## アクセス要件

+++ この記事の機能に対するアクセス要件表示拡張。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Systems ワークフロントパッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在:仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Systems ワークフロントフュージョンライセンス版**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>究極のワークフロントパッケージ:ワークフロントフュージョンが含まれています。</li></ul>
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

Frame.io コネクタは、次のものを使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベースURL</td> 
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

接続プロセスは、従来の Frame.io コネクタとBeta Frame.io コネクタのどちらを使用しているかによって異なります。

1. 任意の Frame.io Beta モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。

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
            <p>IMD ユーザー認証接続を作成するか、IMS サーバーからサーバーへの接続を作成するかを選択します。</p>
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
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の検索手順については、アドビデベロッパー向けドキュメントで<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >資格情報</a>を参照してください。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。<p>資格情報の検索手順については、アドビデベロッパー向けドキュメントで<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >資格情報</a>を参照してください。</p>
        </tr>
       </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Frame.io] モジュールとそのフィールド

[!DNL Frame.io] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Frame.io] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳細については、「 [あるモジュールから別のへの情報のマップ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップの切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アセット](#assets)
* [コメント](#comments)
* [フォルダー](#folders)
* [プロジェクト](#projects)
* [株式](#shares)
* [ワークスペース](#workspaces)
* [その他](#other)

### アセット

* [[!UICONTROL アセット作成]](#create-an-asset)
* [[!UICONTROL アセット削除]](#delete-an-asset)
* [[!UICONTROL アセットを取得]](#get-an-asset)
* [[!UICONTROL &#x200B; アセットのリスト &#x200B;]](#list-assets)
* [[!UICONTROL &#x200B; アセットの更新 &#x200B;]](#update-an-asset)

#### [!UICONTROL アセット作成] <!--different for v4-->

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
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
   <td role="rowheader">[!UICONTROL メディアの種類 &#x200B;] </td> 
   <td> <p>このアセットのメディアタイプを選択します。</p> </td> 
  </tr> 
  </tbody> 
</table>

#### [!UICONTROL &#x200B; アセットの削除 &#x200B;]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>アカウントを選択するか、削除するアセットを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>削除するアセットを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL &#x200B; アセットの取得 &#x200B;]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>取得するアセットを含むアカウントのアカウントを選択するか、ID をマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>取得するアセットを選択またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストアセット]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>アカウントを選択するか、リストするアセットを含むアカウントの ID をマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 返されるアセットの最大数 &#x200B;] </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### コメント

* [[!UICONTROL コメントを作成]](#create-a-comment)
* [[!UICONTROL コメントを削除]](#delete-a-comment)
* [[!UICONTROL コメントを取得]](#get-a-comment)
* [[!UICONTROL コメントをリスト]](#list-comments)
* [[!UICONTROL コメントをアップデート]](#update-a-comment)

#### [!UICONTROL コメントの作成]

このアクションモジュールは、新しいコメントまたは返信をアセットに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>コメントを追加するアセットを含むアカウントのアカウントを選択するか、ID をマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>コメントを追加するアセットを含むワークスペースのアカウントを選択するか、ID をマップします。</p> </td> 
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
   <td role="rowheader">[!UICONTROL ページ &#x200B;] </td> 
   <td> <p>アセットがPDFの場合は、コメントを添付するページを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントを削除]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>削除するコメントが含まれているアカウントのアカウントを選択するか、ID をマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>削除するコメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL &#x200B; コメントを取得 &#x200B;]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>アカウントを選択するか、詳細を取得するコメントを含むアカウントの ID をマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>詳細を取得するコメントを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントの一覧表示]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>コメントを取得するアセットを含んだアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>コメントを取得するアセットを含むワークスペースを選択またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>コメントを取得するアセットを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>コメントリストアセットのリンク先パスを選択します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments] </td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが返すコメントの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントを更新する]

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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>コメントを更新するアセットを含んだプロジェクトを含んだアカウントを選択またはマッピングします。</p> </td> 
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
   <td role="rowheader">[!UICONTROL ページ &#x200B;] </td> 
   <td> <p>アセットがPDFの場合は、コメントが添付されているページを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### フォルダー

#### フォルダーを作成

この操作モジュール、Frame.io 内に新しいフォルダーが作成されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>フォルダーを作成するアカウントを選択またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>フォルダーを作成するワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>フォルダを作成する場所を選択します。</p> </td> 
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

* [プロジェクトを作成](#create-a-project)
* [プロジェクトのリスト](#list-projects)

#### プロジェクトを作成

このアクションモジュール、Frame.io で新しいプロジェクトを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
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
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>プロジェクトを取得するアセットを含んだアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>プロジェクトを取得するアセットを含むワークスペースを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 返されるプロジェクトの最大数 &#x200B;] </td> 
   <td> <p>プロジェクトの最大数を入力またはマッピング
   各シナリオ実行サイクル中にモジュールを返す必要があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 株式

* [共有リンクへのアセットの追加](#add-an-asset-to-a-share-link)
* [共有リンク作成](#create-a-share-link)

#### 共有リンクへのアセット追加

このアクション モジュールは、Frame.io の共有リンクにアセットを追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>アセットを追加する共有リンクを含むアカウントを選択またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share リンク ID] </td> 
   <td> <p>アセットを追加する共有リンクを選択またはマップします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>共有リンクに追加するアセットの ID を入力またはマップします。</p> </td> 
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
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>共有リンクを作成するアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>共有リンクを作成するワークスペースを選択またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>共有リンクを作成するプロジェクトを選択またはマップします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">アクセス </td> 
   <td> <p>このリンクパブリックアクセスまたは制限付きアクセスのどちらを使用するかを選択します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">アセット </td> 
   <td> <p>共有リンクに追加するアセットごとに、[ <b>項目の追加</b> ] をクリックし、アセットの ID を入力します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">説明 </td> 
   <td> <p>共有リンクの説明を入力またはマップします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>共有リンクの有効期限日を入力またはマップします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>新しい共有リンクの名前を入力またはマップします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前 </td> 
   <td> <p>共有リンクのパスフレーズを入力またはマップします。</p> </td> 
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
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>ワークスペースを作成するアカウントを選択またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>ワークスペースの新しい名前を入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### ワークスペースリスト

モジュールアカウント内のすべてのワークスペースが一覧表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>[!DNL Frame.io] への接続を作成する手順については、この記事にある<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Frame.io] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アカウント ID] </td> 
   <td> <p>ワークスペースを取得するアセットを含むアカウントを選択またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 最高画質 返されたワークスペースの数] </td> 
   <td> <p>ワークスペースの最大数を入力またはマッピング
   各シナリオ実行サイクル中にモジュールを返す必要があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

#### [!UICONTROL カスタム API 呼び出しの実行]

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
   <td> <p><code>https://api.frame.io</code> からの相対パスを入力します。例： <code> /v4/me</code></p> <p>メモ：使用可能なエンドポイントの一覧については、[!DNL Frame.io] API リファレンスを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳細については、「 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエスト メソッド</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL クエリ文字列] </td> 
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
