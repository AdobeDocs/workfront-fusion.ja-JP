---
title: Marketo モジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、 [!DNL Marketo] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: da417ac7-e532-45f7-86d9-3643b5f9f203
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1740'
ht-degree: 86%

---

# [!DNL Marketo] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Marketo] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

Marketo コネクタの紹介ビデオについては、次を参照してください。

* [Marketo](https://video.tv.adobe.com/v/3427026/){target=_blank}

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

[!DNL Marketo] モジュールを使用するには、[!DNL Marketo] アカウントが必要です。

## Marketo API の情報

Marketo コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.14.19</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Marketo] を Workfront Fusion に接続 {#connect-marketo-to-workfront-fusion}

[!DNL Marketo] アカウントへの接続を、[!DNL Marketo] モジュール内から直接作成できます。

1. 任意の [!DNL Marketo] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. [!DNL Marketo] アカウントまたは [!UICONTROL Munchkin] ID[!DNL Marketo] 入力します。 これは、[!UICONTROL REST] API を介して [!DNL Marketo] ーザーにアクセスするために使用する、アカウントに割り当てられたベース URL またはエンドポイントの一意の部分です。 これを検索する手順については、[!DNL Marketo] ドキュメントの[ベース URL](https://developers.marketo.com/rest-api/base-url/) を参照してください。
1. [!UICONTROL Client ID] と [!UICONTROL Client secret] を入力します。 これらを検索する手順については、[!DNL Marketo] ドキュメントの[認証](https://developers.marketo.com/rest-api/authentication/)を参照してください。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Marketo] モジュールとそのフィールド

[!DNL Marketo] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Marketo] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

* [[!UICONTROL Watch events (Instant)]](#watch-events-instant)
* [[!UICONTROL Watch records]](#watch-records)

#### [!UICONTROL Watch events (Instant)]

このトリガーモジュールは、レコードが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>モジュールで使用する web フックを入力します。</p> <p>Webhook について詳しくは、[!DNL Adobe Workfront Fusion]</a> の <!--<a href="For instructions, see [Instant triggers (webhooks) in Adobe Workfront Fusion](/help/workfront-fusion/).-->" class="MCXref xref"&gt; インスタントトリガー（Webhook）を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch records]

このトリガーモジュールは、レコードが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Activity]</strong> </p> <p>監視するアクティビティのタイプを選択します。 </p> <p>モジュールは、新しいアクティビティのみを監視します。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Lead]</strong> </p> <p>新しいレコード、更新されたレコード、新しいレコードと更新されたレコードの両方、または特定のフィールドの更新を監視するかどうかを選択します。特定のフィールドの更新を監視する場合は、モジュールで監視するフィールドを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Program]</strong> </p> <p>新しいレコード、更新されたレコード、または新しいレコードと更新されたレコードの両方を監視するかどうかを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Add Leads to a List]](#add-leads-to-a-list)
* [[!UICONTROL Clone a Program]](#clone-a-program)
* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Custom API call]](#custom-api-call)
* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Remove Leads from a List]](#remove-leads-from-a-list)
* [[!UICONTROL Schedule a Campaign]](#schedule-a-campaign)
* [[!UICONTROL Update a record]](#update-a-record)
* [[!UICONTROL Upload a File]](#upload-a-file)

#### [!UICONTROL Add Leads to a List]

このアクションモジュールは、リード ID を使用して 1 つまたは複数のリードをリストに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>リードを追加するリストの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>リストに追加するリードごとに「<b>[!UICONTROL Add]</b>」をクリックし、追加するリードの ID を入力またはマッピングします。 モジュールがリストに追加できるリードは 300 件までです。</p> <p>マップの切り替えをクリックして、リストに追加する既存のリードのコレクションをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clone a Program]

このアクションモジュールは、既存のプログラムの ID を使用してプログラムのコピーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Existing Program ID]</td> 
   <td>コピーするプログラムの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New Program Name]</p> </td> 
   <td> <p>新しいプログラムの名前を入力またはマッピング</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>新しいプログラムを配置するフォルダーの ID を入力またはマップします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a record]

このアクションモジュールは、[!DNL Marketo] に新しいレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Folder]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select fields to map]</td> 
   <td>会社またはリードを作成する場合は、新しいレコードの作成時に値を設定するフィールドを選択し、これらのフィールドに値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Program Type]</td> 
   <td>プログラムを作成する場合は、作成するプログラムのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Program Channel] </td> 
   <td>プログラムを作成する場合は、プログラムを作成するプログラムチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] / [!UICONTROL Program Name]</td> 
   <td>フォルダーまたはプログラムを作成する場合は、新しいレコードの名前を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>フォルダーまたはプログラムを作成する場合は、新しいレコードの説明を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder ID]</td> 
   <td>フォルダーまたはプログラムを作成する場合は、新しいレコードを作成する親フォルダの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Costs]</td> 
   <td>プログラムを作成する場合は、コストを追加します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td>プログラムを作成する場合は、タグを追加します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API call]

このアクションモジュールでは、[!DNL Marketo] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Marketo] モジュールでは不可能なデータフロー自動処理を作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://{your-base-url}.mktorest.com/</code> への相対パスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a>での HTTP リクエストメソッドを参照してください。</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが操作するレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a File]

このアクションモジュールは、ファイル ID を使用してファイルをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>ダウンロードするファイルの ID をマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

このアクションモジュールは、ID を使用してレコードに関する情報を読み取ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Campaign]</p> </li> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL List]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>このモジュールの出力バンドルに含める情報を選択します。フィールドは、選択した [!UICONTROL Record Type] に基づいて使用できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL <Object> ID]</td> 
   <td>情報を取得するオブジェクトの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove Leads from a List]

このアクションモジュールは、リード ID を使用して、1 つまたは複数のリードをリストから削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>リードを削除するリストの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>リストから削除するリードごとに「<b>[!UICONTROL Add]</b>」をクリックし、削除するリードの ID を入力またはマッピングします。 モジュールがリストから削除するリードは最大 300 人まで追加できます。 </p> <p>マップの切り替えをクリックして、リストから削除する既存のリードのコレクションをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Schedule a Campaign]

このアクションモジュールは、特定の日付の既存のキャンペーンをスケジュールします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>スケジュールを設定するキャンペーンの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Schedule for Date]</p> </td> 
   <td>キャンペーンを実行する日付を選択します。このフィールドを空白にした場合、キャンペーンはシナリオが開始されてから 5 分後に実行されます。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a record]

このアクションモジュールは、ID を使用して既存のレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Company] / [!UICONTROL Lead] / [!UICONTROL Program ID]</td> 
   <td>更新するレコードの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select fields to map]</td> 
   <td>会社またはリードを更新する場合は、値を更新するフィールドを選択し、これらのフィールドに値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Program Name]</td> 
   <td>プログラムを更新する場合は、プログラムの新しい名前を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>プログラムを更新する場合は、プログラムの新しい説明を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>プログラムを更新する場合は、プログラムの新しい開始日を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>プログラムを更新する場合は、プログラムの新しい終了日を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Costs]</td> 
   <td>プログラムを更新する場合は、コストを追加します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td>プログラムを更新する場合は、タグを追加します</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

このアクションモジュールは、[!UICONTROL Marketo] に新しいファイルをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>新しいファイルを配置するフォルダーの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>アップロードするファイルの説明を入力します。</td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL List records]](#list-records)
* [[!UICONTROL Search Records]](#update-a-record)

#### [!UICONTROL List records]

このアクションモジュールは、特定のタイプのすべてのレコードを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>リストに表示するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Read all campaigns]</p> </li> 
     <li> <p>[!UICONTROL Read all programs]</p> </li> 
     <li> <p>[!UICONTROL Read all leads] </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field]</td> 
   <td>リードの取得を選択した場合は、リストからリードを取得するか、プログラムからリードを取得するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>このモジュールの出力バンドルに含める情報を選択します。フィールドは、選択した [!UICONTROL Record Type] に基づいて使用できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Records]

この検索モジュールは、特定の検索条件に一致するレコードのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>検索するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Campaigns]</p> </li> 
     <li> <p>[!UICONTROL Leads]</p> </li> 
     <li> <p>[!UICONTROL Programs]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Field]</p> </td> 
   <td> <p>名前、プログラム名またはワークスペース名で検索するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values]</td> 
   <td>検索する値ごとに「<b>[!UICONTROL Add item]</b>」をクリックし、値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>