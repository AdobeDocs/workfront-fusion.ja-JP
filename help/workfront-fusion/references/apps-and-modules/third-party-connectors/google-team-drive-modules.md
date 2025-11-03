---
title: Google チームドライブモジュール
description: ' [!DNL Adobe Workfront Fusion Google Team Drive] モジュールを使用すると、ファイルを監視、アップロード、更新、コピー、削除または取得を行ったり、 [!DNL Google Shared] ドライブ内にフォルダーを作成したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 95dd9d23-1df9-40da-8fd0-646cc697bfc8
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 66%

---

# [!DNL Google Team Drive] モジュール

Adobe Workfront Fusion [!DNL Google Team Drive] モジュールを使用すると、ファイルのモニター、アップロード、更新、コピー、削除または取得や、フ [!DNL Google Shared Drive] ルダー内のフォルダーの作成を行うことができます。

Adobe Workfront Fusion で [!DNL Google Team Drive] を使用するには、[!DNL Google Workspace] アカウントが必要です。 アカウントをお持ちでない場合は、[[!DNL Google Workspace] 新規登録サイト](https://workspace.google.com/business/signup/welcome)で [!DNL Google Workspace] アカウントを作成できます。

Adobe Workfront Fusion のシナリオでは、[!DNL Google Team Drive] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

[!DNL Google Team Drive] モジュールを使用するには、[!DNL Google Team Drive] が必要です。

## [!DNL Google Team Drive] モジュールとそのフィールド

[!DNL Google Team Drive] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Google Team Drive]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

**太字** （Workfront Fusion シナリオでは、**このドキュメントの記事では** ない）で表示されるモジュールダイアログフィールドは必須です。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### トリガー

#### [!UICONTROL ファイルの監視]

指定されたフォルダーに新しいファイルが追加または変更されると、ファイルの詳細が返されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 監視する共有ドライブを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>共有ドライブ内のフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p> 監視するファイルのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] files to format] </td> 
   <td> <p>監視する [!DNL Google Documents] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Sheets] files to format] </td> 
   <td> <p>監視する [!DNL Google Sheets] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] files to format] </td> 
   <td> <p>監視する [!DNL Google Slides] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] files to format] </td> 
   <td> <p>監視する [!DNL Google Drawings] ファイルの変換形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td> <p> フォルダー内の新規ファイルと変更ファイルを監視するか、新規ファイルのみを監視するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td> <p> Workfront Fusion が 1 つの実行サイクルで返すファイルの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL ファイルをアップロード]](#upload-a-file)
* [[!UICONTROL ファイルを更新]](#update-a-file)
* [[!UICONTROL ファイルをコピー]](#copy-a-file)
* [[!UICONTROL ファイルの削除]](#delete-a-file)
* [[!UICONTROL ファイルをごみ箱に移動]](#move-a-file-to-trash)
* [[!UICONTROL ファイルの取得]](#get-a-file)
* [[!UICONTROL ファイルリストの取得]](#get-a-file-list)
* [[!UICONTROL フォルダーの作成]](#create-a-folder)

#### [!UICONTROL ファイルのアップロード]

指定した共有ドライブにファイルをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive] </td> 
   <td> <p>ファイルのアップロード先の共有ドライブを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>共有ドライブ内のフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>共有ドライブにアップロードするファイルを指定します。</p> <p>前のモジュールからアップロードするファイルをマッピングします（例：）[!UICONTROL HTTP] &gt; [!UICONTROL ファイルを取得 ] または [!UICONTROL Dropbox] &gt; [!UICONTROL ファイルを取得） ] を選択するか、ファイル名とファイルデータを手動で入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td> <p> 共有フォルダーに表示するファイルのタイトルを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a File]</td> 
   <td> <p> このオプションを有効にすると、共有フォルダー内の対応する Google 形式にファイルが変換されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを更新]

ファイル名やファイルの内容を変更できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 更新するファイルが含まれている共有ドライブを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>共有ドライブ内のフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> 更新するファイルの ID を入力（マップ）します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title] </td> 
   <td> <p>更新したファイルの新しいタイトルを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a File]</td> 
   <td> <p> このオプションを有効にすると、共有フォルダー内の対応する [!DNL Google] 形式にファイルを変換します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをコピー]

指定したファイルを選択したフォルダーにコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> コピーするファイルがある共有ドライブを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>ファイルのコピー先のーゲットフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> コピーするファイルの ID を入力（マップ）します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL The name of the copy file]</p> </td> 
   <td> <p>コピー先でファイル名を変更する場合は、新しいファイル名を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを削除]

指定したファイルを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> 削除するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをゴミ箱に移動]

指定したファイルをごみ箱に移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> ごみ箱に移動するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルの取得]

指定されたファイルに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] files to format] </td> 
   <td> <p>[!DNL Google Documents] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Sheets] files to format] </td> 
   <td> <p>[!DNL Google Sheets] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] files to format] </td> 
   <td> <p>[!DNL Google Slides] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] files to format] </td> 
   <td> <p>[!DNL Google Drawings] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> 取得するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルリストを取得]

検索語に基づいてファイルやフォルダーの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> ファイルの一覧を表示する共有ドライブを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>ファイルの一覧を表示するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>実行する検索のタイプを選択します（以下を参照）。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Query]</p> </td> 
   <td> 
    <ul> 
     <li style="font-weight: bold;"> <p>[!UICONTROL Search within file names]</p> <p style="font-weight: normal;">「[!UICONTROL Search for exact term Search]」オプションが選択されている場合はファイル拡張子を含むファイル名を入力し、「[!UICONTROL Search for names containing the searched term]」オプションが選択されている場合は名前の一部を入力します。</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Fulltext search]</p> <p>検索語を入力して、ファイル名、説明、内容を検索します。</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Custom search query]</p> <p>[!DNL Google] 検索クエリの語句を入力します。詳しくは、[!DNL Google] の<a href="https://developers.google.com/drive/api/v2/ref-search-terms">検索クエリのドキュメント</a>を参照してください。例： <code>fullText contains '"Hello world"'</code></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td>ファイル、フォルダ、またはその両方を取得するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p> Workfront Fusion が 1 つの実行サイクルで返すファイルまたはフォルダーの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーを作成]

新しいフォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> フォルダーを作成する共有ドライブを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>フォルダーを作成するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the new folder]</td> 
   <td> <p> 新しいフォルダーの名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>
