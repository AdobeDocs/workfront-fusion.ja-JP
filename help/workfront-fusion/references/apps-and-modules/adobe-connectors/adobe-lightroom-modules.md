---
title: Adobe Lightroom モジュール
description: Adobe Lightroom モジュールを使用すると、Adobe Lightroom アカウントのイベントに基づいてAdobe Workfront Fusion シナリオを開始できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
source-git-commit: e1e15985db9683525250d1f9f9276224b2baf0e6
workflow-type: tm+mt
source-wordcount: '2019'
ht-degree: 22%

---

# [!DNL Adobe Lightroom] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Adobe Lightroom] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
      <td>
        <p>[!UICONTROL Pro] またはそれ以降</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
      <td>
        <p>[!UICONTROL Plan], [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td>
      <td >
        <p>[!UICONTROL Workfront Fusion for Work Automation and Integration]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">製品</td>
      <td>この記事で説明されている機能を使用するには、組織で [!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront] を購入する必要があります。</td>
    </tr>
    </tr>
  </tbody>
</table>


&#42;ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

&#42;&#42;[!DNL Adobe Workfront Fusion] ライセンスについては、[!DNL [Adobe Workfront Fusion] licenses](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

## 前提条件

[!DNL Adobe Lightroom] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!DNL Adobe Lightroom] アカウントが必要です。

## Adobe Lightroom API の情報

Adobe Lightroom コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://lr.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.17.128</td> 
  </tr>
 </tbody> 
 </table>



## Adobe Lightroomへの接続の作成

[!DNL Adobe Lightroom] モジュールへの接続を作成するには、以下を実行します。

1. 「接続」ボックスの横にある「**[!UICONTROL Add]**」をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID] を入力します。 これは、の [!UICONTROL Credentials] 細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、の [!UICONTROL Credentials] 細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL Continue]**」をクリックして接続を保存し、モジュールに戻ります。




## Adobe Lightroom モジュールとそのフィールド

[!DNL Adobe Lightroom] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Lightroom] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [その他](#other)
* [アセット](#assets)
* [アルバム](#albums)

### その他

* [ヘルスチェック](#health-check)
* [ユーザーカタログメタデータの取得](#retrieve-user-catalog-metadata)

#### ヘルスチェック

このアクションモジュールは、Lightroom サーバーのバージョン ID を取得し、Lightroom サービスが現在実行中かどうかを示します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Credentials]</td>
      <td>
        <p>特定のサーバーが実行されるように特定の資格情報を指定する場合は、「項目を追加」をクリックし、資格情報を入力します。</p><p>認証ヘッダーは自動的に追加されます。</p>
      </td>
    </tr>
  </tbody>
</table>

#### ユーザーカタログメタデータの取得

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Credentials]</td>
      <td>
        <p>特定の資格情報を指定して正しいユーザーアカウントにアクセスできるようにする場合は、「項目を追加」をクリックし、資格情報を入力します。</p><p>認証ヘッダーは自動的に追加されます。</p>
      </td>
    </tr>
  </tbody>
</table>

### アセット

* [アセットオリジナルファイルの作成](#create-an-asset-external-xmp-develop-setting-file)
* [アセットの作成](#create-an-asset)
* [外部アセットのXMP開発設定ファイルの作成](#create-an-asset-external-xmp-develop-setting-file)
* [元のファイルのレンディションの生成](#generate-renditions-for-an-original-file)
* [カタログアセットの取得](#get-a-catalog-asset)
* [最新の asset external XMP開発設定の取得](#get-the-latest-asset-external-xmp-develop-setting-file)
* [最新のアセットレンディションの取得](#get-the-latest-asset-rendition)
* [アセットの取得](#retrieve-assets)

#### アセットオリジナルファイルの作成

このアクションモジュールは、アセットの元のファイルを作成し、アップロードします。


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>作成してファイルをアップロードするアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Length of content in bytes]</td>
      <td>
        <p>コンテンツの長さをバイト単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Byte range]</td>
      <td>
        <p>RFC 2616 で定義されている最初と最後のバイトおよびエンティティ長を含む、リクエストのバイト範囲を入力またはマッピングします。 データが大きすぎて 1 回の呼び出しでアップロードできない場合にのみ含める必要があります。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Content type]</td>
      <td>
        <p>新しいファイルのコンテンツタイプを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アセットの作成

このアクションモジュールは、初期メタデータとインポート情報を含む新しいアセットを作成します。


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを作成するカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>新しいアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset type]</td>
      <td>
        <p>アセットが画像かビデオかを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user created]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Date captured]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 外部アセットのXMP開発設定ファイルの作成

このアクションモジュールは、2 つのワークフローをサポートします。 最初のワークフローでは、外部のXMP開発設定ファイルをアップロードします。 2 つ目のワークフローは、別のアセットの外部 xmp 開発設定ファイルからコピーして、外部のXMP開発設定ファイルを作成することです。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Length of content in bytes]</td>
      <td>
        <p>コンテンツの長さをバイト単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Upload new or copy XMP/develop file]</td>
      <td>
        <p>新しいファイルをアップロードするか、既存のアセットからファイルをコピーするかを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>アップロード先またはファイルのコピー先のアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Link to XMP/develop file]</td>
      <td>
        <p>アップロードまたはコピーするファイルへのリンクを入力またはマッピングします。</p><p>ファイルをコピーする場合、このファイルは JSON である必要があり、ファイルをアップロードする場合は XML である必要があります。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 元のファイルのレンディションの生成

このアクションモジュールは、元のファイルのレンディションを非同期で生成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rendition Type(s) (semi-colon separated)]</td>
      <td>
        <p>作成するレンディションのレンディションタイプを入力します。 複数の型を入力する場合は、セミコロン （;）で区切ります。 <p>可能なタイプ：</p><ul><li><code>fullsize</code></li><li><code>2560</code></li></ul></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Length of content in bytes]</td>
      <td>
        <p>コンテンツの長さをバイト単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>ファイルのレンディションを作成するアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### カタログアセットの取得

このアクションモジュールは、カタログ内の 1 つのアセットに関する情報を取得します。 カタログは、資格情報がこのモジュールで使用される接続で表されるユーザーが所有している必要があります。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>情報を取得するアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>


#### 最新の外部アセットの取得XMP開発設定ファイル

このアクションモジュールは、最新のアセットの外部XMP設定ファイルを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>XMP開発設定ファイルに関連付けられているアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 最新のアセットレンディションの取得

このアクションモジュールは、指定されたタイプの最新のアセットレンディションを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>XMP開発設定ファイルに関連付けられているアセットの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rendition type]</td>
      <td>
        <p>取得するレンディションのタイプを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アセットの取得

このアクションモジュールは、このモジュールで使用される接続で資格情報が表されるユーザーが所有するアセットを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starting timestamp]</td>
      <td>
        <p>タイムスタンプを入力またはマッピングします。 モジュールは、このタイムスタンプ以降に更新されたレコードを返します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Return assets captured before]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00</code> という形式で日付を入力します。 モジュールは、この日付より前にキャプチャされた結果を返します。</p><p> このフィールドはフィールド <code>Return assets captured after</code> と併用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned assets]</td>
      <td>
        <p>シナリオの実行サイクルごとにモジュールが返すレコードの最大数を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SHA256 Hash value of original file]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Hide assets that are inside stacks?"]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset subtype values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset IDs]</td>
      <td>
        <p>最大 100 個のアセット ID をコンマで区切って入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Types of assets to exclude]</td>
      <td>
        <p>完全なアセットまたは不完全なアセットを除外する場合に選択します。 すべてのアセットを含めるには、このフィールドを空白のままにします。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Group values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Favorite status]</td>
      <td>
        <p></p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### アルバム

* [アルバムへのアセットの追加](#add-assets-to-an-album)
* [アルバムの作成](#create-an-album)
* [アルバムの削除](#delete-an-album)
* [アルバムの取得](#get-an-album)
* [アルバムのアセットのリスト](#list-assets-of-an-album)
* [アルバムの取得](#retrieve-albums)
* [アルバムの更新](#update-album)

#### アルバムへのアセットの追加

このアクションモジュールは、指定されたアルバムに 1 つ以上のアセットを追加します。 1 つの実行サイクルに最大 50 個のアセットを追加できます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アセットを追加するアルバムを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>アセットを追加するアルバムの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Assets]</td>
      <td>
        <p>アルバムに追加するアセットごとに、「<b> アイテムの追加 </b> をクリックし、次のフィールドを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>アルバムに追加するアセットの ID を入力またはマッピングします</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Is this asset an album cover?]</td>
      <td>
        <p>このアセットを、アルバムを表す画像として表示するかどうかを選択します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Order]</td>
      <td>
        <p></p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Metadata]</td>
      <td>
        <p>アセットに含めるメタデータを入力またはマッピングします。 これは、最大長が 1～24 文字の単一のテキスト文字列である必要があります。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Remote ID]</td>
      <td>
        <p>アセットの識別子を入力します。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムの作成

Lightroomに新しいアルバムを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>アルバムを作成するカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>新しいアルバムの ID を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtype]</td>
      <td>
        <p>アルバムのサブタイプを選択します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL API key]</td>
      <td>
        <p>アルバムを作成するサービスの API キーを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user created]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00Z</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00Z</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album name]</td>
      <td>
        <p>新しいアルバムの名前を入力またはマップします。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Cover ID]</td>
      <td>
        <p>このアルバムの表紙として使用するアセットの ID を入力またはマッピングします。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Remote ID]</td>
      <td>
        <p>アセットの識別子を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Created date]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00Z</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Updated date]</td>
      <td>
        <p><code>YYYY-MM-DDT00:00:00-00:00Z</code> という形式で日付を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Is the album deleted?]</td>
      <td>
        <p>外部関連コンテンツが削除された場合は、このオプションを有効にします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to edit affiliated content]</td>
      <td>
        <p>ユーザーがこのアルバムのコンテンツを編集できる URL がある場合は、ここに URL を入力してください。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to view affiliated content]</td>
      <td>
        <p>このアルバムのコンテンツを表示できる URL がある場合は、ここに URL を入力してください。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムの削除

アルバムを削除します。

削除されたアルバムは、現在削除中の同じクライアントアプリによって作成されたものであり、サブタイプが `project` または `project_set` である必要があります。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>削除するアルバムを含むカタログの ID を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>削除するアルバムの ID を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Delete child albums?]</td>
      <td>
        <p>削除したアルバムの子アルバムを削除するかどうかを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

### アルバムの取得

指定されたアルバムを取得します

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>取得するアルバムを含むカタログの ID を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>取得するアルバムの ID を入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムのアセットのリスト

このアクションモジュールは、指定されたアルバム内のアセットのリストを取得します。



#### アルバムの取得

このアクションモジュールは、指定したカタログ内のアルバムのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>取得するアルバムを含むカタログの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtypes]</td>
      <td>
        <p>取得するアルバムの ID を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name of album to precede current results]</td>
      <td>
        <p>結果をページに分ける場合は、前のページの最後のアルバムの名前を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned albums]</td>
      <td>
        <p>1 つの実行サイクル中に返 [!DNL Workfront Fusion] アセットの最大数を設定します。 このフィールドのデフォルト値は 100 です。このモジュールは、リミット境界にある複数のアルバムが同じ <code>name_after</code> 値を持つ場合、このリミットよりも多くのアルバムを返す可能性があります。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムを更新

指定したアルバムを更新します。

更新されたアルバムは、現在更新中の同じクライアントアプリによって作成されており、サブタイプが `project` または `project_set` である必要があります。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Catalog ID]</td>
      <td>
        <p>更新するアルバムを含むカタログの ID を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>更新するアルバムの ID を入力またはマップします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
      <td>
      <td>このモジュールのその他のフィールドについては、この記事の <a href="#create-an-album" class="MCXref xref" > アルバムの作成 </a> を参照してください。</td>
      </td>
    </tr>
  </tbody>
</table>
