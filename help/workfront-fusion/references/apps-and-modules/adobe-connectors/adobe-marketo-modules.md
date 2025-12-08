---
title: Marketo モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Marketo] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: da417ac7-e532-45f7-86d9-3643b5f9f203
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: ht
source-wordcount: '2237'
ht-degree: 100%

---

# [!DNL Marketo] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Marketo] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

Marketo コネクタの紹介ビデオについては、次を参照してください。

* [Marketo](https://video.tv.adobe.com/v/3427026/){target=_blank}

シナリオの作成手順について詳しくは、[シナリオの作成：記事インデックス](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

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

[!DNL Marketo] モジュールを使用するには、[!DNL Marketo] アカウントが必要です。

## Marketo API 情報

Marketo コネクターは、次を使用します。

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

1. 任意の Marketo モジュールで、「接続」フィールドの横にある「**追加**」をクリックします。
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
          <p>新しい接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>本番環境と非本番環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Account / Munchkin ID]</td>
        <td>
          <p>[!DNL Marketo] アカウントまたは [!DNL Marketo] [!UICONTROL Munchkin] ID を入力します。これは、アカウントに割り当てられたベース URL またはエンドポイントの一意の部分で、[!UICONTROL REST] API 経由で [!DNL Marketo] にアクセスするのに使用します。これを検索する手順について詳しくは、[!DNL Marketo] ドキュメントの [Base URL](https://developers.marketo.com/rest-api/base-url/) を参照してください。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Marketo クライアント ID を入力します。これを検索する手順について詳しくは、[!DNL Marketo] ドキュメントの [Authentication](https://developers.marketo.com/rest-api/authentication/) を参照してください。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Marketo クライアントシークレットを入力します。これらを検索する手順について詳しくは、[!DNL Marketo] ドキュメントの [Authentication](https://developers.marketo.com/rest-api/authentication/) を参照してください。</td>
      </tr>
     </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Marketo] モジュールとそのフィールド

[!DNL Marketo] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Marketo]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

* [[!UICONTROL イベントを監視（即時）]](#watch-events-instant)
* [[!UICONTROL レコードを監視]](#watch-records)

#### [!UICONTROL イベントを監視（即時）]

このトリガーモジュールは、レコードが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>モジュールで使用する web フックを入力します。</p> <p>詳しくは、<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhook</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードを監視]

このトリガーモジュールは、レコードが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Activity]</strong> </p> <p>監視するアクティビティのタイプを選択します。 </p> <p>モジュールは、新しいアクティビティのみを監視します。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Lead]</strong> </p> <p>「<b>イベントタイプ</b>」フィールドで、新しいレコード、更新されたレコード、新しいレコードと更新されたレコードの両方、または特定のフィールドの更新を監視するかどうかを選択します。特定のフィールドの更新を監視する場合は、モジュールで監視するフィールドを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Program]</strong> </p> <p>「<b>イベントタイプ</b>」フィールドで、新しいレコード、更新されたレコード、または新しいレコードと更新されたレコードの両方を監視するかどうかを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL リードをリストに追加]](#add-leads-to-a-list)
* [[!UICONTROL プログラムの複製]](#clone-a-program)
* [[!UICONTROL レコードの作成]](#create-a-record)
* [[!UICONTROL カスタム API 呼び出し]](#custom-api-call)
* [[!UICONTROL ファイルのダウンロード]](#download-a-file)
* [[!UICONTROL レコードの読み取り]](#read-a-record)
* [[!UICONTROL リストからリードを削除]](#remove-leads-from-a-list)
* [[!UICONTROL キャンペーンをスケジュール]](#schedule-a-campaign)
* [[!UICONTROL レコードの更新]](#update-a-record)
* [[!UICONTROL ファイルのアップロード]](#upload-a-file)

#### [!UICONTROL リードをリストに追加]

このアクションモジュールは、リード ID を使用して 1 つまたは複数のリードをリストに追加します。一度に 300 リードまで追加できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>リードを追加するリストの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>リストに追加するリードごとに、<b>[!UICONTROL Add]</b> をクリックし、追加するリードの ID を入力またはマッピングします。モジュールがリストに追加できるリードは 300 件までです。</p> <p>マップの切り替えをクリックして、リストに追加する既存のリードのコレクションをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プログラムの複製]

このアクションモジュールは、既存のプログラムの ID を使用してプログラムのコピーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Existing Program ID]</td> 
   <td>コピーするプログラムの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New Program Name]</p> </td> 
   <td> <p>新しいプログラムの名前を入力またはマッピング</p> <p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>新しいプログラムを配置するフォルダーの ID を入力またはマップします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードを作成]

このアクションモジュールは、[!DNL Marketo] に新しいレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL Folder]／[!UICONTROL Program Name]</td> 
   <td>フォルダーまたはプログラムを作成する場合は、新しいレコードの名前を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>フォルダーまたはプログラムを作成する場合は、新しいレコードの説明を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder ID]</td> 
   <td>フォルダーまたはプログラムを作成する場合は、新しいレコードを作成する親フォルダーの ID を入力またはマッピングします。</td> 
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

#### [!UICONTROL カスタム API 呼び出し]

このアクションモジュールでは、[!DNL Marketo] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Marketo] モジュールでは不可能なデータフロー自動処理を実現できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://{your-base-url}.mktorest.com/</code> への相対パスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエスト方法</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>API 呼び出しに追加するフィールドごとに、「<b>項目を追加</b>」をクリックして、フィールドのキーと値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをダウンロード]

このアクションモジュールは、ファイル ID を使用してファイルをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>ダウンロードするファイルの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの読み取り]

このアクションモジュールは、ID を使用してレコードに関する情報を読み取ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL &lt;Object&gt; ID]</td> 
   <td>情報を取得するオブジェクトの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストからリード削除]

このアクションモジュールは、リード ID を使用して、1 つまたは複数のリードをリストから削除します。一度に 300 リードまで削除できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>リードを削除するリストの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>リストから削除するリードごとに、「<b>[!UICONTROL Add item]</b>」をクリックし、削除するリードの ID を入力するかマッピングします。モジュールがリストから削除するリードは最大 300 人まで追加できます。 </p> <p>マップの切り替えをクリックして、リストから削除する既存のリードのコレクションをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL キャンペーンをスケジュール]

このアクションモジュールは、特定の日付の既存のキャンペーンをスケジュールします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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

#### [!UICONTROL レコードを更新]

このアクションモジュールは、ID を使用して既存のレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL Company]／[!UICONTROL Lead]／[!UICONTROL Program ID]</td> 
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

#### [!UICONTROL ファイルをアップロード]

このアクションモジュールは、新しいファイルを [!UICONTROL Marketo] にアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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

* [[!UICONTROL レコードをリスト]](#list-records)
* [[!UICONTROL レコードを検索]](#update-a-record)

#### [!UICONTROL レコードをリスト]

このアクションモジュールは、特定のタイプのすべてのレコードを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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

#### [!UICONTROL レコードを検索]

この検索モジュールは、特定の検索条件に一致するレコードのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Marketo] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">[!DNL Marketo] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
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
   <td> <p>検索の基準となるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value / values]</td> 
   <td>検索するフィールドの値を入力します。フィールドで複数の値を検索できる場合は、検索する値ごとに「<b>[!UICONTROL Add item]</b>」をクリックして値を入力します。</td> 
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
