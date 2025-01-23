---
title: Bynder モジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、 [!DNL Bynder] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 0a45f8a7-12cc-41cc-9135-92f4779afac0
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1425'
ht-degree: 85%

---

# [!DNL Bynder] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Bynder] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!DNL Bynder] モジュールを使用するには、[!DNL Bynder] アカウントが必要です。

## Bynder API 情報

Bynder コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.25.21</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Bynder] を Workfront Fusion に接続  {#connect-bynder-to-workfront-fusion}

* [ [!DNL Workfront Fusion] から  [!DNL Bynder]  への接続の作成](#create-a-connection-to-bynder-from-workfront-fusion)
* [[!UICONTROL Client ID] と [!UICONTROL Client Secret] の生成  [!DNL Bynder]  （オプション）](#generate-a-client-id-and-client-secret-in-bynder-optional)

### [!DNL Workfront Fusion] から [!DNL Bynder] への接続の作成

[!DNL Workfront Fusion] から [!DNL Bynder] アカウントへの接続を、[!DNL Bynder] モジュール内から直接作成できます。

1. 任意の [!DNL Bynder] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続する [!DNL Bynder] ドメインを選択します。
1. （任意）「**[!UICONTROL Advanced settings]**」をクリックして、[!UICONTROL Client ID] と [!UICONTROL Client Secret] を入力します。

   クライアント ID とクライアントシークレットの生成手順については、[ [!DNL Bynder]  でのクライアント ID とクライアントシークレットの生成（オプション）](#generate-a-client-id-and-client-secret-in-bynder-optional) を参照してください。

1. [!UICONTROL login] ウィンドウで、ユーザー名（メールアドレス）とパスワードを入力します。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

### [!DNL Bynder] での [!UICONTROL Client ID] と [!UICONTROL Client Secret] の生成（オプション）

クライアント ID とクライアントシークレットを使用して接続を作成する場合は、[!DNL Bynder] アカウントから生成できます。クライアント ID とクライアントシークレットは、[!DNL Bynder] でアプリを作成するときに生成されます。

[!DNL Bynder] でアプリを作成する手順については、[!DNL Bynder] ドキュメントの [Oauth 2.0 アプリ](https://developer-docs.bynder.com/api/authentication-oauth2-oauth-apps/) を参照してください。

>[!NOTE]
>
>[!DNL Bynder] でアプリを作成する場合、`redirect uri` として次を入力します。
>
>`https://app.workfrontfusion.com/oauth/cb/workfront-bynder`

## [!DNL Bynder] モジュールとそのフィールド

[!DNL Bynder] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Bynder] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [検索](#searches)
* [トリガー](#triggers)

### アクション

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Read asset metadata]](#read-asset-metadata)
* [[!UICONTROL Update asset metadata]](#update-asset-metadata)
* [[!UICONTROL Add assets to a collection]](#add-assets-to-a-collection)
* [[!UICONTROL Remove assets from collection]](#remove-assets-from-collection)
* [[!UICONTROL Add a tag to assets]](#add-a-tag-to-assets)
* [アセットから [!UICONTROL Remove a tag]](#remove-a-tag-from-assets)
* [[!UICONTROL Download asset]](#download-asset)
* [[!UICONTROL Upload asset]](#upload-asset)

#### [!UICONTROL Custom API Call]

このアクションモジュールでは、[!DNL Bynder] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Bynder] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールを設定する際には、次のフィールドが表示されます。

このモジュールは、ステータスコードと共に、API 呼び出しのヘッダーと本文を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td><code>https://{your-bynder-domain}/api/{api-version}/</code> への相対パスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
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

#### [!UICONTROL Read asset metadata]

このアクションモジュールは、アセットのメタデータを読み取ります。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>メタデータを取得するアセットの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update asset metadata]

このアクションモジュールは、既存のアセットのメタデータを更新します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>メタデータを更新するアセットの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>情報を入力するフィールドを選択し、メタデータを更新する情報をこれらのフィールドに入力またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Metaproperties]</p> </td> 
   <td>更新するオプションを選択し、情報を入力するか、これらのプロパティにマッピングします。メタプロパティは、アセット内の特定のフィールドを表さないアセットに関する情報です。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add assets to a collection]

このアクションモジュールは、1 つ以上のアセットをコレクションに追加します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>アセットを追加するコレクションの ID を入力またはマッピングします。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>コレクションに追加するアセットごとに「<strong>[!UICONTROL Add item]</strong>」をクリックし、アセット ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assets from collection]

このアクションモジュールは、1 つ以上のアセットをコレクションから削除します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>アセットを削除するコレクションの ID を入力またはマッピングします。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>コレクションから削除するアセットごとに「<strong>[!UICONTROL Add item]</strong>」をクリックし、アセット ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add a tag to assets]

1 つ以上のアセットへのタグの追加

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag ID]</td> 
   <td> <p>アセットに追加するタグの ID を入力またはマッピングします。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>タグ付けするアセットごとに「<strong>[!UICONTROL Add item]</strong>」をクリックし、アセット ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove a tag from assets]

1 つ以上のアセットからのタグの削除

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag ID]</td> 
   <td> <p>アセットから削除するタグの ID を入力またはマッピングします。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>タグを削除するアセットごとに「<strong>[!UICONTROL Add item]</strong>」をクリックし、アセット ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download asset]

このアクションモジュールは、1 つのアセットをダウンロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>ダウンロードするアセットの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset version]</td> 
   <td> <p>ダウンロードするアセットのバージョンを入力またはマッピングします。アセットの最新バージョンをダウンロードするには、フィールドを空のままにします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload asset]

このアクションモジュールは、1 つのアセットをアップロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save as]</td> 
   <td> <p>アップロードするファイルの保存方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL New asset]</strong> </p> <p>情報を入力するフィールドおよびメタプロパティを選択し、それらのフィールドに情報を入力します。</p> <p>アップロードしたアセットに使用するブランドの ID を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL New asset version]</strong> </p> <p>新しいバージョンをアップロードするアセットの ID を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL List record]](#list-record)
* [[!UICONTROL Search for assets]](#search-for-assets)

#### [!UICONTROL List record]

この検索モジュールは、特定のタイプのすべての項目を取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>リストするレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Read all collections]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Read information about all tags]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Read all assets of a collection]</strong> </p> <p>アセットのリストを表示するコレクションの ID を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>モジュールの出力に含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search for assets]

この検索モジュールは、指定した条件に基づいてアセットを検索します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Criteria]</td> 
   <td> <p>検索条件を入力します。 </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>検索で使用するフィールドを選択します</p> </li> 
     <li> <p><strong>[!UICONTROL Logical Operator]</strong> </p> <p>検索に使用する演算子を選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>選択したフィールドに、検索する値を入力またはマッピングします。値のタイプは、選択したフィールドのデータタイプと同じである必要があります。 </p> <p>データタイプについて詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> の項目データタイプを参照してください。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>最初に一致したアセットを返すか、一致したすべてのアセットを返すかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>並べ替えの基準となるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort Direction]</td> 
   <td> <p>昇順と降順のどちらで並べ替えるかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>モジュールの出力に含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### トリガー

#### [!UICONTROL Watch assets]

このトリガーモジュールは、アセットが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">[!DNL Bynder] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> <!--
    <td role="rowheader">Event type</td>
   --> <!--
    <td>Select whether you want to start the scenario when a new asset is created or when an existing asset is updated.</td>
   --> 
  </tr> 
  <tr>
     <td role="rowheader">[!UICONTROL Collections]</td>
   <td> <p>新しいアセットを監視するコレクションを選択します。すべてのコレクションを監視するには、このフィールドを空のままにします。</p> </td> 
  </tr> 
  <tr> <!--
    <td role="rowheader">Outputs</td>
   --> <!--
    <td>Select the fields that you want to include in the output.</td>
   --> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Limit]</td>

<td> <p>シナリオの実行サイクルごとにモジュールが返すレコードの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>
