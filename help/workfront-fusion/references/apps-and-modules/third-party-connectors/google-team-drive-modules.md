---
title: Google チームドライブモジュール
description: ' [!DNL Adobe Workfront Fusion Google Team Drive] モジュールを使用すると、ファイルを監視、アップロード、更新、コピー、削除または取得を行ったり、 [!DNL Google Shared] ドライブ内にフォルダーを作成したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 95dd9d23-1df9-40da-8fd0-646cc697bfc8
source-git-commit: cca7aa6e15df0fd313e9d4ca391994a8ef4c974a
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 74%

---

# [!DNL Google Team Drive] モジュール

[!DNL Adobe Workfront Fusion] [!DNL Google Team Drive] モジュールを使用すると、ファイルを監視、アップロード、更新、コピー、削除または取得したり、[!DNL Google Shared Drive] にフォルダーを作成したりできます。

[!DNL Google Team Drive] と [!DNL Adobe Workfront Fusion] を併用する場合、[!DNL Google Workspace] アカウントが必要です。アカウントをお持ちでない場合は、[[!DNL Google Workspace] 新規登録サイト](https://workspace.google.com/business/signup/welcome)で [!DNL Google Workspace] アカウントを作成できます。

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Google Team Drive] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!DNL Google Team Drive] モジュールを使用するには、[!DNL Google Team Drive] が必要です。

## [!DNL Google Team Drive] モジュールとそのフィールド

[!DNL Google Team Drive] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Google Team Drive] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

（このドキュメント記事では&#x200B;**なく**、[!DNL Workfront Fusion] シナリオで）**太字**&#x200B;で表示されているモジュールダイアログフィールドは必須です。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### トリガー

#### [!UICONTROL Watch Files]

指定されたフォルダーに新しいファイルが追加または変更されると、ファイルの詳細が返されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td>[!UICONTROL Convert [!DNL Google Documents] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>監視する [!DNL Google Documents] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Sheets] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>監視する [!DNL Google Sheets] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>監視する [!DNL Google Slides] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>監視する [!DNL Google Drawings] ファイルの変換先の形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td> <p> フォルダー内の新規ファイルと変更ファイルを監視するか、新規ファイルのみを監視するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td> <p> [!DNL Workfront Fusion] が 1 回の実行サイクルで返すファイルの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Upload a File]](#upload-a-file)
* [[!UICONTROL Update a File]](#update-a-file)
* [[!UICONTROL Copy a File]](#copy-a-file)
* [[!UICONTROL Delete a File]](#delete-a-file)
* [[!UICONTROL Move a File to Trash]](#move-a-file-to-trash)
* [[!UICONTROL Get a File]](#get-a-file)
* [[!UICONTROL Get a File List]](#get-a-file-list)
* [[!UICONTROL Create a Folder]](#create-a-folder)

#### [!UICONTROL Upload a File]

指定した共有ドライブにファイルをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>共有ドライブにアップロードするファイルを指定します。</p> <p>前のモジュール（例：[!UICONTROL HTTP]/[!UICONTROL Get a File] または [!UICONTROL Dropbox]/[!UICONTROL Get a file)] からアップロードするファイルをマッピングするか、ファイル名とファイルデータを手動で入力します。</p> </td> 
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

#### [!UICONTROL Update a File]

ファイル名やファイルの内容を変更できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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

#### [!UICONTROL Copy a File]

指定したファイルを選択したフォルダーにコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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

#### [!UICONTROL Delete a File]

指定したファイルを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> 削除するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File to Trash]

指定したファイルをごみ箱に移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> ごみ箱に移動するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a File]

指定されたファイルに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>[!DNL Google Documents] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Sheets] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>[!DNL Google Sheets] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>[!DNL Google Slides] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] ファイルをフォーマット &#x200B;] </td> 
   <td> <p>[!DNL Google Drawings] ファイルを変換する形式を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td> <p> 取得するファイルの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a File List]

検索語に基づいてファイルやフォルダーの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
     <li style="font-weight: bold;"> <p>[!UICONTROL Search within file names]</p> <p style="font-weight: normal;">[!UICONTROL Search for exact term Search] オプションが選択されている場合はファイル名（ファイル拡張子を含む）を入力し、[!UICONTROL Search for names containing the searched term] オプションが選択されている場合は名前の一部を入力します。</p> </li> 
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
   <td> <p> [!DNL Workfront Fusion] の 1 回の実行サイクルで返されるファイルまたはフォルダーの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

新しいフォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Team Drive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
