---
title: Widen モジュール
description: 1 つのシナリオで  [!DNL Adobe Workfront Fusion] 、[!UICONTROL Widen] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 89%

---

# [!DNL Widen] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!UICONTROL Widen] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!UICONTROL Widen] モジュールを使用するには、[!UICONTROL Widen] アカウントが必要です。

## API 情報の拡張

Widen コネクタでは、次の機能を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.10.11</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Widen] を [!DNL Workfront Fusion] に接続 {#connect-widen-to-workfront-fusion}

[!DNL Widen] アカウントへの接続を、[!DNL Widen] モジュール内から直接作成できます。

1. 任意の [!DNL Widen] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続する [!DNL Widen] ドメインを選択します。
1. [!DNL Widen] アカウントのトークンを入力します。このトークンの場所について詳しくは、[[!DNL Widen] API に関する FAQ](https://community.widen.com/collective/s/article/API-FAQs)を参照してください。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Widen] モジュールとそのフィールド

[!DNL Widen] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Widen] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガーモジュール](#trigger-modules)
* [アクションモジュール](#action-modules)
* [モジュールの検索](#search-modules)

### トリガーモジュール

#### [!UICONTROL Watch assets]

このトリガーモジュールは、アセットが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p>新しいアセットまたは更新されたアセットのどちらを監視するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>アセットフィールドに加えて、モジュールの出力に含めるプロパティを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に含めるフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクションモジュール

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Read asset info]](#read-asset-info)
* [[!UICONTROL Add assets to collections]](#add-assets-to-collections)
* [[!UICONTROL Remove assets from collection]](#remove-assets-from-collection)
* [[!UICONTROL Update asset metadata]](#update-asset-metadata)
* [[!UICONTROL Download File]](#download-file)
* [ファイルの [!UICONTROL Upload] 成](#upload-a-file)

#### [!UICONTROL Custom API Call]

このアクションモジュールでは、[!DNL Widen] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Widen] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>最新バージョンの [!DNL Widen] API とバージョン 1.0 のどちらを使用するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>API 呼び出しの URL を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] によって、認証ヘッダーが追加されます。</p> </td> 
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

#### [!UICONTROL Read asset info]

このアクションモジュールは、個々のアセットを一意の ID で取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>情報を読み取るアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>アセットフィールドに加えて、モジュールの出力に含めるプロパティを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に含めるフィールドを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add assets to collections]

このアクションモジュールは、1 つ以上のアセットをコレクションに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td> <p>アセットの追加先の各コレクションについて、次の操作を行います。</p> 
    <ol> 
     <li value="1"> <p> <strong>[!UICONTROL Add]</strong> をクリックします。</p> </li> 
     <li value="2"> <p>[!UICONTROL Collection ID] を入力またはマッピングします。</p> </li> 
     <li value="3"> <p><strong>[!UICONTROL Add item]</strong> をクリックします。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> <p>コレクションに追加する各アセットに対して、次の操作を行います。</p> 
    <ol> 
     <li value="1"> <p> <strong>[!UICONTROL Add]</strong> をクリックします。</p> </li> 
     <li value="2"> <p>アセット ID を入力またはマッピングします。</p> </li> 
     <li value="3"> <p><strong>[!UICONTROL Add item]</strong> をクリックします。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assets from collection]

このアクションモジュールは、コレクションから 1 つ以上のアセットを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td> <p>アセットを削除する各コレクションに対して、次の操作を実行します。</p> 
    <ol> 
     <li value="1"> <p> <strong>[!UICONTROL Add]</strong> をクリックします。</p> </li> 
     <li value="2"> <p>コレクション ID を入力またはマッピングします。</p> </li> 
     <li value="3"> <p><strong>[!UICONTROL Add item]</strong> をクリックします。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>コレクションから削除する各アセットに対して、次の操作を実行します。</p> 
    <ol> 
     <li value="1"> <p> <strong>[!UICONTROL Add]</strong> をクリックします。</p> </li> 
     <li value="2"> <p>アセット ID を入力またはマッピングします。</p> </li> 
     <li value="3"> <p><strong>[!UICONTROL Add item]</strong> をクリックします。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update asset metadata]

このアクションモジュールは、アセットのメタデータフィールドを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>メタデータを更新するアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata type]</td> 
   <td> <p>更新するメタデータのメタデータタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>更新するメタデータフィールドを選択します。各フィールドに、フィールドの新しい値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download File]

このアクションモジュールは、[!DNL Widen] アカウントからアセットをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>ダウンロードするアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

このアクションモジュールは、ファイルを [!DNL Widen] アカウントにアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Profile]</td> 
   <td> <p>モジュールで使用するアップロードプロファイルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Method]</td> 
   <td> <p>ファイルのアップロード方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL From File]</strong> </p> <p>前のモジュールからソースファイルを選択またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL By URL]</strong> </p> <p>アップロードするファイルの URL を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>アップロードしたファイルの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata Type]</td> 
   <td>アップロードするファイルのメタデータタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>ファイルのアップロードに含めるメタデータフィールドを選択します。各フィールドに、フィールドの [!UICONTROL value] を入力します。</td> 
  </tr> 
 </tbody> 
</table>

### モジュールの検索

* [[!UICONTROL Read collection assets]](#read-collection-assets)
* [[!UICONTROL Search assets]](#search-assets)

#### [!UICONTROL Read collection assets]

このアクションモジュールは、コレクション内のアセットのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>読み取るアセットを含むコレクションの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>リストする最初の項目の番号を入力またはマッピングします。これは、レコードをページ分割する方法です。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>アセットの並べ替えに使用するプロパティを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>アセットを昇順に並び替えるか、降順に並び替えるかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に含めるフィールドを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search assets]

この検索モジュールは、特定の検索条件に一致するアセットのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">[!DNL Widen] を [!DNL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search query]</td> 
   <td> <p>アセットを検索する条件を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>アセットを並べ替える方法を選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>アセットを昇順に並び替えるか、降順に並び替えるかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include deleted]</td> 
   <td>削除されたアセットを検索に含めるには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Include archived]</p> </td> 
   <td> <p>アーカイブしたアセットを検索に含めるには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search document text]</td> 
   <td>検索にドキュメントテキストを含める場合はこのオプションを有効にし、検索条件に一致するタイトルを持つアセットのみを含める場合は false にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Offset]</td> 
   <td>詳細を取得する最初の項目の番号を入力またはマッピングします。これは、レコードをページ分割する方法です。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scroll]</td> 
   <td>スクロールを許可するには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>アセットフィールドに加えて、モジュールの出力に含めるプロパティを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に含めるフィールドを選択します。</td> 
  </tr> 
 </tbody> 
</table>
