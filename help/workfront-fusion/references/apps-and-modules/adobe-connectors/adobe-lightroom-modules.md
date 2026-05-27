---
title: Adobe Lightroom モジュール
description: Adobe Lightroom モジュールを使用すると、Adobe Lightroom アカウント内のイベントに基づいてAdobe Workfront Fusion シナリオを開始できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
TQID: https://experienceleague.adobe.com/mpTM66zk6PRthMvpk302CQ6MkOs5qEqPODNcvv-Qauo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 3230
ht-degree: 22%

---

# [!DNL Adobe Lightroom] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Adobe Lightroom] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

シナリオの作成手順が必要な場合は、[&#x200B; シナリオの作成：記事インデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

モジュールについて詳しくは、[モジュール：記事インデックス](/help/workfront-fusion/references/modules/modules-toc.md)の記事を参照してください。

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

[!DNL Adobe Lightroom] コネクタを使用する前に、以下の前提条件が満たされていることを確認してください。

* アクティブな [!DNL Adobe Lightroom] アカウントが必要です。
* Adobe Admin ConsoleでOAuth Web アプリを設定する必要があります。 詳しくは、この記事の「[Adobe Admin ConsoleでのOAuth アプリケーションの設定](#configure-an-oauth-application-in-the-adobe-admin-console)」を参照してください。

## Adobe Lightroom APIについて

Adobe Lightroom コネクタでは、次の機能が使用されます。

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

Adobe Lightroomに接続するには、まずAdobe Admin ConsoleでOAuth アプリを設定する必要があります。 このアプリを設定したら、Workfront Fusionから接続を作成できます。

### Adobe Admin ConsoleでのOAuth アプリケーションの設定

1. Adobe Admin ConsoleでのOAuth Web アプリの設定を開始します。

   手順については、Adobe開発者向けドキュメントの「[User Authentication Implementation Guide](https://developer.adobe.com/developer-console/docs/guides/authentication/UserAuthentication/implementation)」を参照してください。
1. OAuth Web アプリを設定する場合は、次の値を入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>
          <ul>
            <li>AdobeID</li>
            <li>lr_partner_rendition_apis</li>
            <li>openid</li>
            <li>offline_access</li>
            <li>lr_partner_apis</li>
          </ul>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL リダイレクト URI]</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/adobe-lightroom5</code></td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Redirect URI pattern]</td>
        <td><code>https://app\.workfrontfusion\.com/oauth/cb/adobe-lightroom5</code></td>
        </tr>
      </tbody>
    </table>

### Workfront FusionからAdobe Lightroomへの接続を作成する

[!DNL Adobe Lightroom] モジュールへの接続を作成するには、以下を実行します。

1. 任意のAdobe Lightroom モジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL Add]**&#x200B;をクリックします。

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
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID]を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。


## Adobe Lightroom モジュールとそのフィールド

[!DNL Adobe Lightroom] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Lightroom]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [その他](#other)
* [アセット](#assets)
* [アルバム](#albums)

### その他

* [ヘルスチェック](#health-check)
* [ユーザーカタログメタデータの取得](#retrieve-user-catalog-metadata)

#### ヘルスチェック

このアクションモジュールは、Lightroom サービスが現在実行中かどうかを示すLightroom サーバーバージョン IDを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Credentials]</td>
      <td>
        <p>特定のサーバーが実行されていることを確認するために特定の資格情報を指定する場合は、<b>項目を追加</b>をクリックし、資格情報を入力します。</p><p>認証ヘッダーは自動的に追加されます。</p>
      </td>
    </tr>
  </tbody>
</table>

#### ユーザーカタログメタデータの取得

このアクションモジュールは、Adobe Lightroomのカタログからメタデータを取得します。 カタログには、アセット、アルバム、その他のリソースが含まれます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Credentials]</td>
      <td>
        <p>正しいユーザーアカウントにアクセスできるように特定の資格情報を指定する場合は、「項目を追加」をクリックし、資格情報を入力します。</p><p>認証ヘッダーは自動的に追加されます。</p>
      </td>
    </tr>
  </tbody>
</table>

### アセット

* [アセットのオリジナルファイルの作成](#create-an-asset-original-file)
* [アセットの作成](#create-an-asset)
* [アセットの外部XMP開発設定ファイルの作成](#create-an-asset-external-xmp-develop-setting-file)
* [元のファイルのレンディションを生成](#generate-renditions-for-an-original-file)
* [カタログアセットの取得](#get-a-catalog-asset)
* [最新のアセットを入手する外部XMP開発設定](#get-the-latest-asset-external-xmp-develop-setting-file)
* [最新のアセットレンディションを入手](#get-the-latest-asset-rendition)
* [アセットの取得](#retrieve-assets)

#### アセットのオリジナルファイルの作成

このアクションモジュールは、アセットの元のファイルを作成してアップロードします。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アセットを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>ファイルを作成してアップロードするアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL コンテンツの長さ（バイト） &#x200B;]</td>
      <td>
        <p>コンテンツの長さをバイト単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL バイト範囲]</td>
      <td>
        <p>リクエストのバイト範囲を入力またはマッピングします。これには、RFC 2616で定義されている最初と最後のバイトとエンティティの長さが含まれます。 この情報は、データが大きすぎて1回の呼び出しでアップロードできない場合にのみ含める必要があります。</p>
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
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アセットを作成するカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>新しいアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset type]</td>
      <td>
        <p>アセットが画像か動画かを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user created]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00</code>でマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00</code>でマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL の取得日]</td>
      <td>
        <p>アセットの取得日を形式<code>YYYY-MM-DDT00:00:00-00:00</code>で入力またはマッピングします。 取得された日付が<code>0000-00-00T00:00:00</code>に設定されている場合、これはサーバーによって設定されます。 </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File name]</td>
      <td>
        <p>Lightroomに読み込むアセットのファイル名を入力するか、マッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name of Device Imported On]</td>
      <td>
        <p>アセットを読み込むデバイスの名前を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Account ID of User Who Imported]</td>
      <td>
        <p>アセットを読み込むユーザーのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL インポートタイムスタンプ &#x200B;]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00</code>でマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アセットの外部XMP開発設定ファイルの作成

このアクションモジュールでは、アセットの外部XMP develop settings ファイルをアップロードするか、別のアセットの外部xmp develop settings ファイルからコピーして外部XMP develop settings ファイルを作成するという2つのワークフローをサポートしています。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL コンテンツ長（バイト単位） &#x200B;]</td>
      <td>
        <p>コンテンツの長さをバイト単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 新規アップロードまたはXMP/develop ファイルのコピー]</td>
      <td>
        <p>新しいファイルをアップロードするか、既存のアセットからファイルをコピーするかを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アセットを作成するカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>ファイルをアップロードまたはコピーするアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Link to XMP/develop file]</td>
      <td>
        <p>アップロードまたはコピーするファイルへのリンクを入力またはマッピングします。</p><p>ファイルをコピーする場合はJSON、ファイルをアップロードする場合はXMLである必要があります。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 元のファイルのレンディションを生成

このアクションモジュールは、元のファイルのレンディションを非同期で生成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Rendition Type （s） （セミコロン区切り） &#x200B;]</td>
      <td>
        <p>作成するレンディションのレンディションタイプを入力します。 複数のタイプを入力する場合は、セミコロン（;）で区切ります。 <p>考えられるタイプは次のとおりです。</p><ul><li><code>fullsize</code></li><li><code>2560</code></li></ul></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL コンテンツの長さ（バイト） &#x200B;]</td>
      <td>
        <p>コンテンツの長さをバイト単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>レンディションを生成するカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>ファイルのレンディションを作成するアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### カタログアセットの取得

このアクションモジュールは、カタログ内の1つのアセットに関する情報を取得します。 カタログは、このモジュールで使用される接続で資格情報が表されるユーザーが所有する必要があります。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アセットを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>情報を取得するアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>


#### 最新のアセットを取得する外部XMP開発設定ファイル

このアクションモジュールは、最新のアセット外部XMP設定ファイルを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>XMP開発設定ファイルに関連付けられているアセットを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>XMP開発設定ファイルに関連付けられているアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 最新のアセットレンディションを入手

このアクションモジュールは、指定したタイプの最新のアセットレンディションを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>レンディションを取得するアセットを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>レンディションを取得するアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL レンディションの種類]</td>
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
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アセットを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 開始タイムスタンプ &#x200B;]</td>
      <td>
        <p>タイムスタンプを入力またはマッピングします。 モジュールは、このタイムスタンプの後に更新されたレコードを返します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 指定した時間より前に取得したアセットを返す]</td>
      <td>
        <p>日付を形式<code>YYYY-MM-DDT00:00:00</code>で入力してください。 モジュールは、この日付より前にキャプチャされた結果を返します。</p><p> このフィールドをフィールド <code>Return assets captured after given time</code>と共に使用することはできません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 指定された時間が経過した後に取得されたアセットを返します]</td>
      <td>
        <p>日付を形式<code>YYYY-MM-DDT00:00:00</code>で入力してください。 モジュールは、この日付より前にキャプチャされた結果を返します。</p><p> このフィールドをフィールド <code>Return assets captured before given time</code>と共に使用することはできません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 返されたアセットの最大数]</td>
      <td>
        <p>シナリオの実行サイクルごとにモジュールが返すレコードの最大数を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SHA256 ハッシュ値の元のファイル &#x200B;]</td>
      <td>
        <p>元のファイルのハッシュ値を入力またはマッピングします。 一致するハッシュを持つAssetsが返されます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL スタック内にあるアセットを非表示にしますか？"]</td>
      <td>
        <p>スタック内のアセットを非表示にするには、「はい」を選択します（スタック内のアセットは返されません）。 「いいえ」を選択すると、検索結果のスタック内にアセットが含まれます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset サブタイプ値]</td>
      <td>
        <p>返すサブタイプ値のセミコロン区切りリストを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset IDs]</td>
      <td>
        <p>最大100個のアセット IDをコンマで区切って入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 除外するアセットの種類]</td>
      <td>
        <p>完全なアセットと不完全なアセットのどちらを除外するかを選択します。 すべてのアセットを含めるには、このフィールドを空白のままにします。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Group values]</td>
      <td>
        <p>グループ値のセミコロン区切りリストを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name values]</td>
      <td>
        <p>名前の値のセミコロン区切りリストを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL のお気に入りステータス &#x200B;]</td>
      <td>
        <p>結果を返すお気に入りのステータスを入力またはマッピングします。</p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### アルバム

* [アルバムへのアセットの追加](#add-assets-to-an-album)
* [アルバムの作成](#create-an-album)
* [アルバムの削除](#delete-an-album)
* [アルバムを入手](#get-an-album)
* [アルバムのアセットのリスト](#list-assets-of-an-album)
* [アルバムの取得](#retrieve-albums)
* [アルバムの更新](#update-album)

#### アルバムへのアセットの追加

このアクションモジュールは、指定したアルバムに1つ以上のアセットを追加します。 1回の実行サイクルで最大50個のアセットを追加できます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アセットを追加するアルバムを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>アセットを追加するアルバムのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Assets]</td>
      <td>
        <p>アルバムに追加する各アセットについて、<b>項目を追加</b>をクリックし、次のフィールドを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Asset ID]</td>
      <td>
        <p>アルバムに追加するアセットのIDを入力またはマッピングします</p>
      </td>
    <tr>
      <td role="rowheader">このアセットはアルバムカバーですか？&rbrack;</td>
      <td>
        <p>このアセットをアルバムを表す画像として表示するかどうかを選択します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Order]</td>
      <td>
        <p>アセットの順序を指定します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL サービス ペイロード &#x200B;]</td>
      <td>
        <p>アセットに含めるメタデータを入力するか、マッピングします。 これは、最大長1～24文字の単一のテキスト文字列である必要があります。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL リモート ID]</td>
      <td>
        <p>アセットの識別子を入力します。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムの作成

このアクションモジュールは、Lightroomで新しいアルバムを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アルバムを作成するカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>新しいアルバムのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL サブタイプ &#x200B;]</td>
      <td>
        <p>アルバムのサブタイプを選択します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL サービス ID]</td>
      <td>
        <p>アルバムを作成するサービスのAPI キーを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Date User Created]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00Z</code>でマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Date User Updated]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00Z</code>でマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL アルバム名]</td>
      <td>
        <p>新しいアルバムの名前を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カバーID]</td>
      <td>
        <p>このアルバムの表紙として使用するアセットのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Parent ID]</td>
      <td>
        <p>このアルバムの親のIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL サービス ペイロード &#x200B;]</td>
      <td>
        <p>アルバムメタデータを文字列として入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL リモート ID]</td>
      <td>
        <p>アセットの識別子を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Created date]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00Z</code>でマッピングします。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 更新日]</td>
      <td>
        <p>日付を入力するか、形式<code>YYYY-MM-DDT00:00:00-00:00Z</code>でマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL アルバムは削除されますか？]</td>
      <td>
        <p>外部に関連付けられたコンテンツが削除された場合は、このオプションを有効にします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL：アフィリエイトコンテンツを編集する場所]</td>
      <td>
        <p>ユーザーがこのアルバムのコンテンツを編集できるURLがある場合は、ここにURLを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to view affiliated content]</td>
      <td>
        <p>ユーザーがこのアルバムのコンテンツを表示できるURLがある場合は、ここにURLを入力します。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムの削除

このアクションモジュールは、アルバムを削除します。

削除されたアルバムは、現在削除している同じクライアントアプリによって作成されている必要があり、サブタイプは`project`または`project_set`である必要があります。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>削除するアルバムを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>削除するアルバムのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 子アルバムを削除？]</td>
      <td>
        <p>削除したアルバムの子アルバムを削除するかどうかを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

### アルバムを入手

このアクションモジュールは、指定されたアルバムを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>取得するアルバムを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>取得するアルバムのIDを入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムのアセットのリスト

このアクションモジュールは、指定したアルバム内のアセットのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>アルバムを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>アセットを一覧表示するアルバムのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Capture Assets Before Time]</td>
      <td>
        <p>日付を形式<code>YYYY-MM-DDT00:00:00</code>で入力してください。 モジュールは、この日付より前にキャプチャされた結果を返します。</p><p> このフィールドをフィールド <code>Return assets captured after given time</code>と共に使用することはできません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Capture Assets After Time]</td>
      <td>
        <p>日付を形式<code>YYYY-MM-DDT00:00:00</code>で入力してください。 モジュールは、この日付より前にキャプチャされた結果を返します。</p><p> このフィールドをフィールド <code>Return assets captured before given time</code>と共に使用することはできません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ending Asset Order Value]</td>
      <td>
        <p>終了アセットの注文値を入力またはマッピングします。</p><p> このフィールドは、フィールド <code>Capture Assets After Time</code>でのみ使用できます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starting Asset Order Value]</td>
      <td>
        <p>開始アセットの注文値を入力またはマッピングします。</p><p> このフィールドは、フィールド <code>Capture Assets BEfore Time</code>でのみ使用できます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Number of Assets to Return （1-500） &#x200B;]</td>
      <td>
        <p>シナリオの実行サイクルごとにモジュールが返すレコードの最大数を入力します。 この数値は1 ～ 500である必要があります。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL スタック内にあるアセットを非表示にしますか？"]</td>
      <td>
        <p>スタック内のアセットを非表示にするには、「はい」を選択します（スタック内のアセットは返されません）。 「いいえ」を選択すると、検索結果のスタック内にアセットが含まれます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL サブタイプ値（セミコロン区切り） &#x200B;]</td>
      <td>
        <p>返すサブタイプ値のセミコロン区切りリストを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL フラグ値（セミコロン区切り） &#x200B;]</td>
      <td>
        <p>返すフラグ値のセミコロン区切りリストを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Additional Data Fields to Include （セミコロン区切り） &#x200B;]</td>
      <td>
        <p>アセットが含まれている場合は、すべてのフィールドが含まれます。含まれていない場合は、IDと自己参照リンクのみが返されます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 除外するアセットの種類]</td>
      <td>
        <p>完全なアセットと不完全なアセットのどちらを除外するかを選択します。 すべてのアセットを含めるには、このフィールドを空白のままにします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset IDs]</td>
      <td>
        <p>最大100個のアセット IDをコンマで区切って入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL プレゼンテーション フィルターに基づいてアルバムアセットをフィルタリング &#x200B;]</td>
      <td>
        <p>このフィールドを「true」に設定すると、アルバムに設定されているプレゼンテーションフィルターに基づいて、すべてのアルバムアセットがフィルタリングされます。 このパラメーターを使用すると、プレゼンテーションフィルターの設定に関係なく、拒否されたアセットが常に除外されます。 album_filtersに「true」以外の値が設定されている場合、プレゼンテーションフィルターは適用されません。 デフォルトの動作は、すべてのアセットを表示することです。 このパラメーターは、フラグパラメーターと共に使用することはできません。 </p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムの取得

このアクションモジュールは、指定したカタログ内のアルバムのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>取得するアルバムを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtypes]</td>
      <td>
        <p>返すサブタイプ値のセミコロン区切りリストを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 現在の結果より前のアルバム名]</td>
      <td>
        <p>結果をページネーションする場合は、前のページに最後のアルバムの名前を入力するか、マッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Number of Albums to Return]</td>
      <td>
        <p>1回の実行サイクルでWorkfront Fusionが返すアセットの最大数を設定します。 このフィールドのデフォルト値は100です。このモジュールは、制限境界の複数のアルバムが同じ<code>name_after</code>値を持つ場合、この制限よりも多くのアルバムを返す場合があります。</p>
      </td>
    </tr>
  </tbody>
</table>

#### アルバムを更新

このアクションモジュールは、指定されたアルバムを更新します。

更新されたアルバムは、現在更新中の同じクライアントアプリによって作成されている必要があり、サブタイプは`project`または`project_set`である必要があります。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Lightroom] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >[!DNL Adobe Lightroom]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL カタログ ID]</td>
      <td>
        <p>更新するアルバムを含むカタログのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Album ID]</td>
      <td>
        <p>更新するアルバムのIDを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
      <td>
      <td>このモジュールの他のフィールドについては、この記事の「<a href="#create-an-album" class="MCXref xref" > アルバムを作成</a>」を参照してください。</td>
      </td>
    </tr>
  </tbody>
</table>
