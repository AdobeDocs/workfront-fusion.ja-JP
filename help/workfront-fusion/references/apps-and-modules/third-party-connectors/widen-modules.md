---
title: Widen モジュール
description: Adobe Workfront Fusion のシナリオでは、[!UICONTROL Widen] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 69%

---

# [!DNL Widen] モジュール

Adobe Workfront Fusion のシナリオでは、[!UICONTROL Widen] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

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

## [!DNL Widen] を Workfront Fusion に接続  {#connect-widen-to-workfront-fusion}

[!DNL Widen] アカウントへの接続を、[!DNL Widen] モジュール内から直接作成できます。

1. 任意の [!DNL Widen] モジュールで、「[!UICONTROL 接続]」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 接続先の環境とアカウントのタイプを選択します。 これは情報提供のみを目的としており、Fusion の「接続」領域に表示されます。
1. 接続する [!DNL Widen] ドメインを選択します。
1. [!DNL Widen] アカウントのトークンを入力します。このトークンの場所について詳しくは、[[!DNL Widen] API に関する FAQ](https://community.widen.com/collective/s/article/API-FAQs)を参照してください。
1. 「**[!UICONTROL 続行]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Widen] モジュールとそのフィールド

[!DNL Widen] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Widen]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガーモジュール](#trigger-modules)
* [アクションモジュール](#action-modules)
* [モジュールの検索](#search-modules)

### トリガーモジュール

#### [!UICONTROL アセットを監視]

このトリガーモジュールは、アセットが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
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

* [[!UICONTROL コレクションへのアセットの追加]](#add-assets-to-collections)
* [[!UICONTROL カスタム API 呼び出し]](#custom-api-call)
* [[!UICONTROL ファイルをダウンロード]](#download-file)
* [[!UICONTROL アセット情報の読み取り]](#read-asset-info)
* [[!UICONTROL コレクションからアセットを削除]](#remove-assets-from-collection)
* [[!UICONTROL アセットのメタデータの更新]](#update-asset-metadata)
* [[!UICONTROL ファイルをアップロード]](#upload-a-file)

#### [!UICONTROL コレクションへのアセットの追加]

このアクションモジュールは、1 つ以上のアセットをコレクションに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td>アセットの追加先のコレクションごとに「<strong>[ コレクション ID]</strong> をクリックし、[!UICONTROL コレクション ID] を入力またはマッピングします。</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> コレクションに追加するアセットごとに、「<strong>[!UICONTROL Assets ID]</strong> をクリックし、アセット ID を入力またはマッピングします。</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カスタム API 呼び出し]

このアクションモジュールは、[!DNL Widen] API に対して認証済みのカスタム呼び出しを実行します。これにより、他の [!DNL Widen] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
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
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] によって認証ヘッダーが追加されます。</p> </td> 
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

#### [!UICONTROL ファイルをダウンロード]

このアクションモジュールは、[!DNL Widen] アカウントからアセットをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>ダウンロードするアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセット情報の読み取り]

このアクションモジュールは、個々のアセットを一意の ID で取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
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

#### [!UICONTROL コレクションからアセットを削除]

このアクションモジュールは、コレクションから 1 つ以上のアセットを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td>アセットを削除するコレクションごとに、「<strong>[ コレクション ID]</strong>」をクリックして、[!UICONTROL コレクション ID] を入力またはマッピングします。</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> コレクションから削除する各アセットに対して、<strong>[!UICONTROL Assets ID] をクリックし </strong> アセット ID を入力またはマッピングします。</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するアセットの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL アセットメタデータを更新]

このアクションモジュールは、アセットのメタデータフィールドを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
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

#### [!UICONTROL ファイルをアップロード]

このアクションモジュールは、ファイルを [!DNL Widen] アカウントにアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
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
   <td>ファイルのアップロードに含めるメタデータフィールドを選択します。各フィールドに、そのフィールド用の [!UICONTROL value] を入力します。</td> 
  </tr> 
 </tbody> 
</table>

### モジュールの検索

* [[!UICONTROL コレクションアセットの読み取り]](#read-collection-assets)
* [[!UICONTROL アセットの検索]](#search-assets)

#### [!UICONTROL コレクションアセットの読み取り]

このアクションモジュールは、コレクション内のアセットのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
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

#### [!UICONTROL アセットの検索]

この検索モジュールは、特定の検索条件に一致するアセットのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Widen] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-widen-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Widen] への </a> の接続」を参照してください。</p> </td> 
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
   <td>このオプションを有効にして検索にドキュメントテキストを含めるか、false に設定してタイトルが検索条件に一致するアセットのみを含めます。</td> 
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
