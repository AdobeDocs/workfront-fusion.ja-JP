---
title: Google Drive のモジュール
description: ' [!DNL Adobe Workfront Fusion Google Drive]  モジュールを使用すると、 [!DNL Google Drive] 内のファイル、フォルダー、または共有ドライブを監視、検索、作成、更新、削除、管理できます。'
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 788f4e1b-d774-45ad-a8be-b16922c1d5dc
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2102'
ht-degree: 57%

---

# [!DNL Google Drive] モジュール

Adobe Workfront Fusion [!DNL Google Drive] モジュールを使用すると、[!DNL Google Drive] 内のファイル、フォルダー、共有ドライブを監視、検索、作成、更新、削除、管理できます。

Adobe Workfront Fusion シナリオでは、[!DNL Google Drive] アカウントを複数のサードパーティのアプリケーションやサービスに接続できます。

シナリオの作成方法については、[&#x200B; シナリオの作成：記事のインデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Google Drive API に関する情報

Google ドライブコネクタは以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://www.googleapis.com/drive/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v4.1.22</td> 
  </tr>
 </tbody> 
 </table>



## Workfront Fusion への [!DNL Google Drive] の接続

[!DNL @gmail.com] または [!DNL @googlemail.com] ユーザーを使用する場合は、[!DNL Google Cloud Platform] で OAuth クライアントを作成して、[!UICONTROL &#x200B; クライアント ID] と [!UICONTROL &#x200B; クライアントシークレット &#x200B;] を取得する必要があります。

OAuth クライアントを作成（および [!UICONTROL &#x200B; クライアント ID] と [!UICONTROL &#x200B; クライアントシークレット &#x200B;] を取得）する手順については、[&#x200B; カスタム OAuth クライアントを使用した  [!DNL Google Services]  へのAdobe Workfront Fusion の接続 &#x200B;](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md) を参照してください。

[!DNL Google Drive] アカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

## [!DNL Google Drive] モジュールとそのフィールド

[!DNL Google Drive] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Google Drive]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)



* [トリガー](#triggers)
* [アクション](#actions)

### トリガー

* [[!UICONTROL &#x200B; すべてのファイルを監視 &#x200B;]](#watch-all-files)
* [[!UICONTROL &#x200B; コメントを見る &#x200B;]](#watch-comments)
* [[!UICONTROL &#x200B; フォルダー内のファイルを監視 &#x200B;]](#watch-files-in-folder)
* [[!UICONTROL 共有ファイルを監視]](#watch-shared-files)

#### [!UICONTROL &#x200B; すべてのファイルを監視 &#x200B;]

このトリガーモジュールは、[!DNL Google Drive] ージ内のファイルが追加または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p>監視するファイルの種類を選択します。</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] files to format]</td>
    <td>[!DNL Google Documents] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td>
    <td>[!DNL Google Spreadsheets] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td>
    <td>[!DNL Google Slides] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td>
    <td>[!DNL Google Drawings] の変換先のファイル形式を選択します。</td>
  </tr>  
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>新規ファイルとすべての変更を監視するか、新規ファイルのみを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Workfront Fusion が 1 つのサイクルでダウンロードする結果の最大数（シナリオ実行ごとの繰り返し数）を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL コメントを監視]

このトリガーモジュールは、選択したファイルにコメントが追加または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File]</td> 
   <td>コメントを監視するファイルを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>すべての変更を監視するか、新しいコメントのみを監視するかを選択</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned comments]</td> 
   <td>Workfront Fusion が 1 つのサイクルで返すコメントの最大数（シナリオ実行ごとの繰り返し数）を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL &#x200B; フォルダー内のファイルを監視 &#x200B;]

このトリガーモジュールは、指定したフォルダー内でファイルが追加または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Select the folder to be watched]</td>
    <td >ファイルを監視したいドライブ上のフォルダーを選択します。</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL What files to watch]</td>
   <td> <p>監視するファイルの種類を選択します。</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] files to format]</td>
    <td>[!DNL Google Documents] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td>
    <td>[!DNL Google Spreadsheets] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td>
    <td>[!DNL Google Slides] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td>
    <td>[!DNL Google Drawings] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Watch]</td>
    <td>新規ファイルとすべての変更を監視するか、新規ファイルのみを監視するかを選択します。</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL Maximum number of downloaded files]</td>
    <td>Workfront Fusion が 1 つのサイクルでダウンロードする結果の最大数（シナリオ実行ごとの繰り返し数）を設定します。</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 共有ファイルの監視]

新規ファイルが共有されたときや、既存の共有ファイルが更新されたときにトリガーされます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select the folder to be watched]</td> 
   <td>監視するファイルが含まれている共有フォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p>監視するファイルの種類を選択します。</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] files to format]</td>
    <td>[!DNL Google Documents] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td>
    <td>[!DNL Google Spreadsheets] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td>
    <td>[!DNL Google Slides] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td>
    <td>[!DNL Google Drawings] の変換先のファイル形式を選択します。</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>新規ファイルとすべての変更を監視するか、新規ファイルのみを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Workfront Fusion が 1 つのサイクルでダウンロードする結果の最大数（シナリオ実行ごとの繰り返し数）を設定します。</td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL &#x200B; ファイルのコピー &#x200B;]](#copy-a-file)
* [[!UICONTROL fFolder の作成 &#x200B;]](#create-a-folder)
* [[!UICONTROL ファイルを削除]](#delete-a-file)
* [[!UICONTROL ファイルを取得]](#get-a-file)
* [[!UICONTROL 共有リンクを取得]](#get-a-share-link)
* [[!UICONTROL &#x200B; ファイルをごみ箱に移動する &#x200B;]](#move-a-filefolder-to-trash)
* [[!UICONTROL ファイル／フォルダを検索]](#search-for-filesfolders)
* [[!UICONTROL ファイルを更新]](#update-a-file)
* [[!UICONTROL ファイルをアップロード]](#upload-a-file)

#### [!UICONTROL &#x200B; ファイルのコピー &#x200B;]

このアクションモジュールは、ファイルを新しい場所にコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>ファイルのコピー先を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>コピーするファイルを含むフォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>コピーするファイルの ID をマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the copy]</td> 
   <td>新規ファイルのタイトルを入力します。元のファイル名を変更しない場合は、このフィールドを空白のままにしておきます。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーを作成]

このアクションモジュールは、指定された場所にフォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>フォルダーの作成先を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New folder location]</td> 
   <td>新規フォルダーを作成する場所に移動します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the new folder]</td> 
   <td>作成するフォルダーの名前を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Share folder]</td> 
   <td>[!UICONTROL Share]リンクを使用してこのフォルダーを他のユーザーと共有する場合は、このオプションを選択します。選択しない場合、共有リンクを使用できるのは所有者のみになります。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを削除]

このアクションモジュールは、ファイルまたはフォルダーを完全に削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>削除するファイルの ID をマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを取得]

このアクションモジュールは、指定された ID を持つファイルを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] files to format]</td> 
   <td>[!DNL Google Documents] の変換先のファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Spreadsheets] files to format]</td> 
   <td>[!DNL Google Spreadsheets] の変換先のファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] files to format]</td> 
   <td>[!DNL Google Slides] の変換先のファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] files to format]</td> 
   <td>[!DNL Google Drawings] の変換先のファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>取得するファイルの ID をマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 共有リンクを取得]

この操作モジュールは、Google ドライブ内のファイルの共有リンクを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>取得する共有リンクの対象ファイルの ID をマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL &#x200B; ファイルをごみ箱に移動する &#x200B;]

このアクションモジュールは、ファイルまたはフォルダーをごみ箱に移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>ゴミ箱に移動するファイルの ID をマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイル／フォルダを検索]

この検索モジュールは、検索条件に基づいてファイルまたはフォルダを検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>検索する宛先ドライブを選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL List a folder]</td> 
   <td>ファイルまたはフォルダーを検索するフォルダーに移動します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td> <p> 検索対象を、ファイル、フォルダまたはその両方から選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Search]</p> </td> 
   <td> <p>実行する検索のタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Search within file/folder names]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>検索するファイル名の一部または完全なファイル名（拡張子を含む）を入力します。</p> </li> 
       <li> <p><strong>[!UICONTROL Search Options]</strong> </p> <p>完全に一致する用語を検索するか、検索語を含む名前を検索するかを選択します。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Fulltext]検索</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>[!DNL Google Drive] で検索する検索語を入力します。</p> </li> 
      </ul> </li> 
     <li> <p><strong>カスタム検索クエリを入力</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>カスタム検索クエリを入力します。詳しくは、この記事の[!UICONTROL Search for Files]の節を参照してください。</p> </li> 
       <li> <p><strong>上記で選択したフォルダをクエリに追加</strong> </p> <p>親コレクション内のフォルダーを検索します。これにより、上記で選択したフォルダー内にあるすべてのファイルとフォルダーが検索されます。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すファイルまたはフォルダーの最大数を設定します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td>モジュールが結果を返さない場合にシナリオが停止しないようにするには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを更新]

このアクションモジュールは、ファイルのメタデータまたはコンテンツを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>更新するファイルを含む宛先を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Move to a folder]</td> 
   <td>ファイルを特定のフォルダに移動する場合は、ファイルの移動先のフォルダを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>更新するファイルの ID をマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>更新されたファイルのタイトルを入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Change a file content]</td> 
   <td>ファイルのコンテンツを置き換えるかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>コンテンツを置き換える場合は、前のモジュールからソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ファイルの変換 &#x200B;]</td> 
   <td>ファイルを対応するGoogle ファイル形式に変換する場合は、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをアップロード]

ファイルを [!DNL Google Drive] にアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Drive] アカウントをWorkfront Fusion に接続する手順については、<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Google Drive] の接続 &rbrack; を参照してください </a></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Destination]</td> 
   <td> <p>ファイルのアップロード先を選択します。</p> 
    <ul> 
     <li>[!DNL My Drive]</li> 
     <li>[!DNL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>ファイルをアップロードするフォルダーを選択します。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>新規ファイルのタイトルを入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a file]</td> 
   <td>このオプションを有効にすると、モジュールはファイルを対応する [!DNL Google] 形式に変換できます。</td> 
  </tr> 
 </tbody> 
</table>

## トラブルシューティング

### ファイルをアップロードまたは更新できない

ファイルのアップロードまたは更新に失敗する理由はいくつかあります。

* アップロードしたファイルが大きすぎるため、[!DNL Google Drive] プランで許可されているファイル サイズの上限を超えています。または、[!DNL Google Drive] ストレージの上限を超えています。 ストレージプランをアップグレードするか、[!DNL Google Drive] サービスから既存のファイルを削除することができます。
* ファイルのアップロード先として選択したフォルダーが存在しません。この場合、シナリオは停止し、モジュールで別のターゲットフォルダーを選択する必要があります。

<!-- Not present February 2025

## Search for files

In the module List files in a folder you can use your own query which consists of these parts:

* **[!UICONTROL Field]** - Attribute of the file that is being searched, for example, the attribute `name` of the file.

* **[!UICONTROL Operator]** - Test that is performed on the data to provide a match, for example, `contains`.

* **[!UICONTROL Value]** - The content of the attribute that is tested, for example, the name of the file `My cool document`.

Combine clauses with the conjunctions `and` or `or`, and negate the query with `not`.

* [Fields](#fields)
* [Value types](#value-types)
* [Operators](#operators)
* [Examples](#examples)

### Fields 

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Field </th> 
   <th>Value Type </th> 
   <th>Operators</th> 
   <th> <p> Description</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>[!UICONTROL title]</code></td> 
   <td>string</td> 
   <td><code>contains</code><sup>1</sup>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Name of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL fullText]</code> </td> 
   <td>string </td> 
   <td><code>contains</code><sup>2, 3</sup> </td> 
   <td> <p> Full text of the file including name, description, content, and indexable text.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL mimeType]</code> </td> 
   <td> string</td> 
   <td><code>contains</code>, <code>=</code>, <code>!=</code></td> 
   <td> <p> MIME type of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL modifiedDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code> &lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date of the last modification to the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL lastViewedByMeDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code>&lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date that the user last viewed a file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL trashed]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Whether the file is in the trash or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL starred]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p>Whether the file is starred or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL parents]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Whether the [!UICONTROL parents] collection contains the specified ID.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL owners]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who own the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL writers]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to modify the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL readers] </code> </td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to read the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL sharedWithMe]</code> </td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Files that are in the user's "Shared with me" collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL properties] </code> </td> 
   <td>collection</td> 
   <td><code>has </code> </td> 
   <td> <p> Public custom file properties.</p> </td> 
  </tr> 
 </tbody> 
</table>

Consider the following about operators in these fields:

* The `contains` operator only performs prefix matching for a `title`.

   For example, the title "HelloWorld" matches for `title contains 'Hello'` but not for `title contains 'World'`.

* The `contains` operator only performs matching on entire string tokens for `fullText`.

   For example, if the full text of a doc contains the string "HelloWorld" only the query `fullText contains 'HelloWorld'` returns a result. Queries such as `fullText contains 'Hello'` would not return results in this scenario.

* The `contains` operator matches on an exact alphanumeric phrase if it is surrounded by double quotes.

   For example, if the `fullText` of a doc contains the string "Hello there world", then the query `fullText contains '"Hello there"'` returns a result, but the query `fullText contains '"Hello world"'` does not.

   Furthermore, because the search is alphanumeric, if the `fullText` of a doc contains the string "Hello_world", then the query `fullText contains '"Hello world"'` returns a result.

* Fields of `type` date are currently not comparable to each other, only to constant dates.

### Value types

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Value Type</th> 
   <th> <p> Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>String </td> 
   <td> <p>Surround with single quotes '. Escape single quotes in queries with <code>\'</code>, e.g.,<code> 'Valentine\'s Day'</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Boolean </td> 
   <td> <p><code>true </code>or <code>false</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Date </td> 
   <td> <p>RFC 3339 format, default timezone is UTC, e.g., <code>2012-06-04T12:00:00-08:00</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Operators

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Operator </th> 
   <th> <p>Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>contains</code></td> 
   <td> <p>The content of one string is present in the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>=</code> </td> 
   <td> <p> The content of a string or boolean is equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>!=</code> </td> 
   <td> <p> The content of a string or boolean is not equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;</code> </td> 
   <td> <p> A date is earlier than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;=</code> </td> 
   <td> <p> A date is earlier than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>></code> </td> 
   <td> <p> A date is later than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>>=</code> </td> 
   <td> <p> A date is later than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>in </code> </td> 
   <td> <p>An element is contained within a collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>and </code> </td> 
   <td> <p>Return files that match both clauses.</p> </td> 
  </tr> 
  <tr> 
   <td><code>or </code> </td> 
   <td> <p>Return files that match either clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>not </code> </td> 
   <td> <p>Negates a search clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>has </code> </td> 
   <td> <p>A collection contains an element matching the parameters.</p> </td> 
  </tr> 
 </tbody> 
</table>

For compound clauses, you can use parentheses to group clauses together. For example:
`modifiedDate > '2012-06-04T12:00:00' and (mimeType contains 'image/' or mimeType contains 'video/')` This search returns all files with an image or video MIME type that their last modification was after June 4, 2012. Because `and` and `or` operators are evaluated from left to right, without parentheses, the above example would return only images modified after June 4, 2012, but would return all videos, even those before June 4, 2012.

### Examples 

All examples on this page show the unencoded `<q>q</q>` parameter, where `title = 'hello'` is encoded as `title+%3d+%27hello%27`. Client libraries handle this encoding automatically.

* Search for files with the name "hello"
   <pre>title = 'hello'</pre>
* Search for folders using the folder-specific MIME type
   <pre>mimeType = 'application/vnd.google-apps.folder'</pre>
* Search for files that are not folders
   <pre>mimeType != 'application/vnd.google-apps.folder'</pre>
* Search for files with a name containing the words "hello" and "goodbye"
   <pre>title contains 'hello' and [!UICONTROL name] contains 'goodbye'</pre>
* Search for files with a name that does not contain the word "hello"
   <pre>not title contains 'hello'</pre>
* Search for files containing the word "hello" in the content
   <pre>fullText contains 'hello'</pre>
* Search for files not containing the word "hello" in the content
   <pre>not fullText contains 'hello'</pre>
* Search for files containing the exact phrase "hello world" in the content
   <pre>fullText contains '"hello world"'fullText contains '"hello_world"'</pre>
* Search for files with a query containing the "\" character (e.g., "\authors")
   <pre>fullText contains '\\authors'</pre>
* Search for files writeable by the user `test@example.org`
   <pre>'test@example.org' in [!DNL writers]</pre>
* Search for the ID `1234567` in the `parents` collection. This finds all files and folders located directly in the folder whose ID is `1234567`.
   <pre>'1234567' in [!UICONTROL parents]</pre>
* Search for the alias ID `appDataFolder` in the `parents` collection. This finds all files and folders located directly under the [Application Data folder](https://developers.google.com/drive/api/v2/appdata).
   <pre>'appDataFolder' in parents</pre>
* Search for files writeable by the users `test@example.org` and `test2@example.org`
   <pre>'test@example.org' in writers and 'test2@example.org' in writers</pre>
* Search for files containing the text "important" which are in the trash
   <pre>fullText contains 'important' and trashed = true</pre>
* Search for files modified after June 4th 2012
   <pre>modifiedDate > '2012-06-04T12:00:00' // default time zone is UTC</pre><pre>modifiedDate > '2012-06-04T12:00:00-08:00'</pre>
* Search for files shared with the authorized user with "hello" in the name
   <pre>sharedWithMe and title contains 'hello'</pre>
* Search for files with a [custom file property](https://developers.google.com/drive/api/v2/properties) named `additionalID` with the value `8e8aceg2af2ge72e78`.
   <pre>properties has { key='additionalID' and value='8e8aceg2af2ge72e78' and visibility='PRIVATE' }</pre>

Source of this guide is [[!DNL Google Drive] documentation](https://developers.google.com/drive/api/v2/search-shareddrives).

-->
