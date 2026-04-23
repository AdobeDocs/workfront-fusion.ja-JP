---
title: Dropbox モジュール
description: Adobe Workfront Fusionでは、Dropboxを使用するワークフローを自動化したり、複数のサードパーティ製アプリケーションやサービスに接続したりできます。これにより、Dropboxでファイルやフォルダーの監視、検索、取得、一覧表示、作成、編集などの作業を自動化できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 29ce5940-4d71-4719-ab5e-f03c44b28c8c
source-git-commit: 72abd9b5aa73d54edd73dc16f7695d2b01cc8624
workflow-type: tm+mt
source-wordcount: '3292'
ht-degree: 75%

---

# [!DNL Dropbox] モジュール

Adobe Workfront Fusion シナリオでは、[!UICONTROL Dropbox]または[!DNL Dropbox Business]を使用するワークフローを自動化し、複数のサードパーティ製アプリケーションやサービスに接続できます。これにより、[!UICONTROL Dropbox]でファイルやフォルダーの監視、検索、取得、一覧表示、作成、編集などの作業を自動化できます。

シナリオの作成手順について詳しくは、[シナリオの作成：記事のインデックス](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

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

* [!DNL Dropbox] モジュールを使用するには、[!DNL Dropbox] アカウントが必要です。

>[!IMPORTANT]
>
>* Dropbox コネクタを使用するには、まずDropboxでアプリケーションを作成する必要があります。
>   詳しくは、Dropbox開発者ガイドの「アプリケーションの作成」を参照してください。
>* アプリケーションの作成時に、次のリダイレクト URIを使用します：`https://app.workfrontfusion.com/oauth/cb/dropbox`
>* Dropbox は、ユーザーが 50 人を超えるアプリケーションを承認する必要があります。
>   詳しくは、Dropbox 開発者ガイドの「Production approval」を検索してください。

## Dropbox APIについて

Dropbox コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.dropboxapi.com/2    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td><ul><li><p>Dropbox</p><p>v5.3.9</p></li><li><p>Dropbox Business</p><p>v1.0.12</p></li></ul></td> 
  </tr>
 </tbody> 
 </table>


## [!DNL Dropbox] への接続の作成

[!DNL Dropbox] モジュールへの接続を作成するには、以下を実行します。

1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

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
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>この接続を本番環境と非本番環境のどちらで使用するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Dropbox] [!UICONTROL Client ID] を入力します。 </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Dropbox] [!UICONTROL Client Secret] を入力します。 </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Account Type]</td>
        <td>個人用 Dropbox アカウントとビジネス用アカウント（Dropbox Business）のどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Exclude dropbox-api-path-root header]</td>
        <td>このオプションを有効にすると、App Folder アクセス権を持つDropbox アプリのdropbox-api-path-root ヘッダーが除外されます</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。## [!DNL Dropbox] モジュールとそのフィールド

## [!DNL Dropbox] モジュールとそのフィールド

[!DNL Dropbox] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Dropbox]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガーモジュール](#trigger-modules)
* [&#x200B; [!DNL Dropbox] ファイルおよびフォルダーを取得するためのモジュール](#modules-for-getting-dropbox-files-and-folders)
* [&#x200B; [!DNL Dropbox] ファイルおよびフォルダーを作成および編集するためのモジュール](#modules-for-creating-and-editing-dropbox-files-and-folders)
* [その他のモジュール](#other-modules)

### トリガーモジュール

#### [!UICONTROL ファイルを監視]

このトリガータイプのモジュールは、指定されたフォルダー内のファイルが変更されたときに、ファイルの詳細を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>変更を監視するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch also subfolders]</td> 
   <td> <p> このオプションを有効にすると、選択したフォルダー内のサブフォルダーも変更されたファイルがないか監視されます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit] </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!DNL Dropbox] ファイルおよびフォルダーを取得するためのモジュール

* [[!UICONTROL ファイルをダウンロード]](#download-a-file)
* [[!UICONTROL フォルダーメタデータを取得]](#get-a-folder-metadata)
* [[!UICONTROL フォルダー内のすべてのファイル／サブフォルダーを一覧表示]](#list-all-filessubfolders-in-a-folder)
* [[!UICONTROL ファイルリビジョンを一覧表示]](#list-file-revisions)
* [[!UICONTROL ファイル／フォルダーを検索]](#search-filesfolders)

#### [!UICONTROL ファイルをダウンロード]

このアクションモジュールは、フォルダーからファイルをダウンロードします。

ファイルとその場所を指定します。

このモジュールは、ファイルの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

>[!NOTE]
>
>このモジュールは、後続のモジュールにファイルを提供するのに役立ちます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>ファイルを選択する方法</td> 
   <td> <p> ファイルパスをマッピングするか、ファイルを手動で選択するかを選びます。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>ファイルパス／ファイル</p> </td> 
   <td> <p style="font-weight: bold;">ファイルパス</p> <p>ターゲットパスを入力するか、ファイルにマッピングします。</p> <p style="font-weight: bold;">ファイル</p> <p>ファイルをメニューから選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーメタデータを取得]

このアクションモジュールは、共有フォルダーの詳細を取得します。

フォルダーの ID を指定します。

このモジュールは、フォルダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>共有フォルダー ID</td> 
   <td> <p> 詳細を取得するフォルダーの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダー内のすべてのファイル／サブフォルダーを一覧表示]

このアクションモジュールは、特定のフォルダー内のファイルまたはフォルダーを一覧表示します。

フォルダーの ID を指定します。

このモジュールは、ファイルまたはフォルダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>リスト </td> 
   <td> <p>ファイルを取得するか、フォルダーを取得するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>ダウンロード可能なファイルのみを表示</td> 
   <td> <p> ダウンロード可能なファイルのみを返すには、このオプションを有効にします。Google ドキュメントなど、一部の種類のファイルはダウンロードできません。</p> </td> 
  </tr> 
  <tr> 
   <td>フォルダー </td> 
   <td> <p>ファイルまたはフォルダーを取得するフォルダーを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>制限 </td> 
   <td> <p>シナリオの実行サイクルごとにモジュールが一覧表示するレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルリビジョンを一覧表示]

このアクションモジュールは、特定のファイルのすべてのファイルリビジョン（バージョン履歴）を取得します。\
ファイルの ID を指定します。

このモジュールは、レコードに関連付けられた標準フィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>ファイルを選択する方法</td> 
   <td> <p> ファイルパスをマッピングするか、ファイルを手動で選択するかを選びます。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>ファイルパス／ファイル</p> </td> 
   <td> <p><b>ファイルパス</b></p> <p>ターゲットパスを入力するか、ファイルにマッピングします。</p> <p><b>ファイル</b></p> <p>ファイルをメニューから選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>制限</p> </td> 
   <td> <p>シナリオの実行サイクルごとにモジュールが一覧表示するレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイル／フォルダーを検索]

この検索モジュールは、指定された検索クエリに一致するレコードを [!DNL Dropbox] のオブジェクト内で検索します。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>検索語句を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>検索するフォルダーを選択します。このモジュールは、フォルダーを選択しない場合、[!DNL Dropbox] アカウント全体を検索します。</p> </td> 
  </tr> 
  <tr> 
   <td>ファイルステータス</td> 
   <td> <p> 検索に含めるファイルステータスを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>ファイルカテゴリ</td> 
   <td> <p> 検索に含めるファイルカテゴリを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>ファイル拡張子</td> 
   <td> <p>検索に含めるファイル拡張子ごとに、<b>項目を追加</b>をクリックし、ファイル拡張子を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>制限 </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!DNL Dropbox] ファイルおよびフォルダーを作成および編集するためのモジュール

* [[!UICONTROL フォルダーを作成]](#create-a-folder)
* [[!UICONTROL テキストファイルを作成／上書き]](#createoverwrite-a-text-file)
* [[!UICONTROL 共有リンクを作成／更新]](#createupdate-a-share-link)
* [[!UICONTROL ファイル／フォルダーを削除]](#delete-a-filefolder)
* [[!UICONTROL ファイル／フォルダーを移動]](#move-a-filefolder)
* [[!UICONTROL ファイル／フォルダーの名前を変更]](#rename-a-filefolder)
* [[!UICONTROL ファイルを復元]](#restore-a-file)
* [ファイルを[!UICONTROL アップロード]](#upload-a-file)

#### [!UICONTROL フォルダーを作成]

このアクションモジュールは、新規フォルダーを作成します。

フォルダーのパスと名前を指定します。

このモジュールは、フォルダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name] </td> 
   <td> <p>新規フォルダーの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>新規フォルダーを作成する場所のパスを入力またはマッピングします。</p> <p>メモ：   <p>[!DNL Dropbox Business] アカウント （チーム スペースを含む）を使用している場合は、スラッシュ <code>/</code>を削除するか、<strong>ここをクリックしてフォルダー</strong>を選択し、ルートにチーム フォルダーを作成する必要があります。</p> <p>スラッシュが削除されない場合は、エラー <code>[409] path/malformed_path/..</code> が返されます。</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Auto rename]</td> 
   <td> <p> このオプションを有効にすると、同じ名前のフォルダーがターゲットの場所に既に存在する場合は、新規フォルダーの名前が変更されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL テキストファイルを作成／上書き]

このアクションモジュールは、DOC ファイルを作成するか、既存のファイルの内容を上書きします。

ソースファイルとフォルダーを指定します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select to]</td> 
   <td> <p> DOC ファイルを作成するか上書きするかを選択します。</p><ul><li><b>作成</b></p>ファイルを作成するフォルダーを選択します。</li><li><b>上書き</b><p>上書きするファイルの選択方法を選択し、ファイルパスをマッピングするか、ファイルを選択します。 </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>前のモジュールからソースファイルを選択するか、ソースファイルのコンテンツをマッピングします。 </p> <p>ファイルを作成する場合は、<b>Empty</b>を選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 共有リンクを作成／更新]

このアクションモジュールは、ファイルへの公開リンクを作成します。

ファイルとリンクに関する情報を指定します。

このモジュールは、リンクの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> ファイルパスをマッピングするか入力するか、手動でファイルを選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path / File]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>パスを入力するか、ターゲットファイルにマッピングします。</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>ターゲットファイルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Requested Visibility]</p> </td> 
   <td> <p>リンクがパブリック、チーム用、またはパスワード制限されているかどうかを選択します。</p> <p><b>メモ：</b></p><p> [!UICONTROL Teamのみ]は、Dropbox Business アカウントでのみ使用できます。 [!UICONTROL Access with password]は、[!DNL Dropbox Pro]またはDropbox Business アカウントでのみ使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Link's Expiration Date]</td> 
   <td> <p> リンクの有効期限が切れて、アクセスできなくなる日時を入力します。このフィールドを空のままにした場合、リンクは期限切れになりません。サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">型強制</a>を参照してください。</p>  </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Link's Access Level]</p> </td> 
   <td> <p>リンクの受信者に対する権限を設定します。</p> <ul><li><strong>[!UICONTROL Viewer]</strong> <p>リンクを使用するユーザーは、コンテンツを表示してコメントできます。</p> </li><li><strong>[!UICONTROL エディター]</strong><p> リンクを使用するユーザーは、コンテンツを編集、表示、コメントできます。 このアクセスレベルは、クラウドベースのドキュメントでのみ使用できます。</p> </li><li><strong>[!UICONTROL Max]</strong> <p>リンクを使用するユーザーは、リンクを設定できる最大アクセスレベルを受け取ります。</p></li><ul> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL ファイル／フォルダーを削除]

このアクションモジュールは、ファイルまたはフォルダーを削除します。

ファイルまたはフォルダーを指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> ファイルパスをマッピングするか入力するか、手動でファイルを選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL ファイルまたはフォルダーのパス &#x200B;] / [!UICONTROL ファイルまたはフォルダー]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>ターゲットパスを入力するか、ファイルまたはフォルダーにマッピングします。</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>メニューからファイルまたはフォルダーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイル／フォルダーを移動]

このアクションモジュールは、ファイルまたはフォルダーを別の場所に移動します。

ファイルまたはフォルダー、および移動する方法と場所を指定します。

このモジュールは、ファイルまたはフォルダーの ID と関連するフィールドのほか、接続でアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ファイル / フォルダーを選択する方法] </td> 
   <td> <p>ファイルまたはフォルダーのパスをマップまたは入力するか、ファイルまたはフォルダーを手動で選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL ファイル / フォルダーパス &#x200B;] /</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>ターゲットパスを入力するか、ファイルまたはフォルダーにマッピングします。</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>ファイルまたはフォルダーのどちらを移動するかを選択し、次にファイルまたはフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL To Folder]</p> </td> 
   <td> <p>ファイルまたはフォルダーのターゲットの場所を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL New Name]</p> </td> 
   <td> <p>新しい場所にあるファイルまたはフォルダーの新しい名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Auto Rename]</p> </td> 
   <td> <p>このオプションを有効にすると、同じ名前のファイルまたはフォルダーが存在する場合、モジュールはファイルまたはフォルダー名の後に ([!UICONTROL NUMBER]) を付加して、新しいファイルまたはフォルダーの名前を変更します。それ以外の場合は、ターゲットの場所にあるファイルまたはフォルダーが上書きされます。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Allow ownership transfer]</p> </td> 
   <td> <p>このオプションを有効にすると、移動されるコンテンツの所有権が移転される結果になる場合であっても、所有者による移動が許可されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイル／フォルダーの名前を変更]

このアクションモジュールは、ファイルまたはフォルダーの名前を変更します。

ファイルまたはフォルダーと新しい名前を指定します。

このモジュールは、ファイルまたはフォルダーの ID と関連するフィールドのほか、接続でアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>ファイルを選択する方法</td> 
   <td> <p> ファイルパスをマッピングするか入力するか、手動でファイルを選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>ファイルまたはフォルダーのパス／ファイルまたはフォルダー</p> </td> 
   <td> <p style="font-weight: bold;">ファイルまたはフォルダーのパス</p> <p>ターゲットパスを入力するか、ファイルまたはフォルダーにマッピングします。</p> <p style="font-weight: bold;">ファイルまたはフォルダー</p> <p>ファイルまたはフォルダーのどちらを移動するかを選択し、次にファイルまたはフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>名前を変更 </td> 
   <td> <p>ファイル拡張子を含む、ファイルの新しい名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL ファイルを復元]

このアクションモジュールは、ファイルの以前のバージョンを復元します。

ファイルと必要なリビジョン番号を指定します。

このモジュールは、バージョンの ID と関連するフィールドのほか、接続でアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> ファイルパスをマッピングするか入力するか、手動でファイルを選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path] / [!UICONTROL File]</p> </td> 
   <td> <p><strong>[!UICONTROL File Path]</strong> </p> <p>ターゲットパスを入力するか、ファイルにマッピングします。</p> <p><strong>[!UICONTROL File]</strong> </p> <p>ファイルをメニューから選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Revision]</p> </td> 
   <td> <p>復元するリビジョンのリビジョン番号を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをアップロード]

このアクションモジュールは、ファイルをフォルダーにアップロードします。

ファイルの場所、アップロードするファイル、ファイルの新しい名前（オプション）などの情報を指定します。

このモジュールは、ファイルの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder]</td> 
   <td> <p> ファイルのアップロード先となる [!DNL Dropbox] のフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> <p><b>メモ：</b></p><p> アップロードされたファイルの最大サイズは150 MBです。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing file]</td> 
   <td> <p> 既存のファイルを新しいファイルで置き換えるには、このオプションを有効にします。このオプションを無効にしたままにすると、アップロードされたファイルの名前が変更されます。</p> </td> 
  </tr> 
 </tbody> 
</table>


### その他のモジュール

#### [!UICONTROL API 呼び出しを実行]

このアクションモジュールでは、[!DNL Dropbox] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Dropbox] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Dropbox] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection-to-dropbox" class="MCXref xref">接続を[!DNL Dropbox]</a>に作成する」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://api.dropboxapi.com</code> からの相対パスを入力します。例： <code>/2/files/list_folder</code></p>  </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers] </td> 
   <td> <p>希望するリクエストヘッダーを入力します。Workfront Fusion は認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p> リクエストクエリ文字列を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body] </td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：   <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例：**

次のAPI呼び出しは、[!DNL /Text files] アカウントの[!DNL Dropbox] フォルダーから最初の10 ファイルを返します。

URL：`/2/files/list_folder`

本文：

```
{
"path": "/Text files",
"limit": 10,
"recursive": false,
"include_deleted": false
}
```

検索結果は、[!UICONTROL バンドル]／[!UICONTROL 本文]にあるエントリ内のモジュールの「出力」に表示されます。

この例では、10件のチケットが返されました。

>[!ENDSHADEBOX]

## よくある問題

* [ファイルをアップロードまたは更新できない](#unable-to-upload-or-update-a-file)
* [共有リンクで参照された画像がレンダリングされない](#image-referenced-via-a-shared-link-does-not-render)

### ファイルをアップロードまたは更新できない

ファイルのアップロードまたは更新が失敗する理由は、次のとおりです。

* アップロードされるファイルが大きすぎて、利用中の [!DNL Dropbox] プランで許可されている最大ファイルサイズを超えている場合や、[!DNL Dropbox] アカウントのストレージ割当をすべて使い切った場合。[!DNL Dropbox] アカウントから既存のファイルを削除するか、プランをアップグレードする必要があります。
* ファイルをアップロードしようとしている選択済みのフォルダーが存在しなくなった場合。シナリオが停止するので、ターゲットフォルダーをもう一度選択する必要があります。

### 共有リンクで参照された画像がレンダリングされない

[!UICONTROL Dropbox]／[!UICONTROL 共有リンクを作成]で返される URL は、画像に直接リンクされるのではなく、[!DNL Dropbox] ページにリンクされています。画像を強制的にダウンロードするには、末尾の `?dl=0` を `?dl=1` に置き換えます。（Web ブラウザーや Facebook メッセンジャーなどで）画像を強制的にレンダリングするには、URL の末尾に `&raw=1` を追加します。

Web サイトまたはその他のWorkfront Fusion モジュールの画像の直接リンクまたは生リンクを取得する必要がある場合は、次の方法で最初の共有URLを変更する必要があります。

元の URL：

`https://www.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png?dl=0`

1. `www` を `dl` に置き換えます。
1. `?dl=0` を削除します。

最終的な URL：

`https://dl.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png`

URL を自動的に変更するには、次のように `replace()` 関数を 2 回実行します。

* www を dl に置き換えます。

  ![wwwをdl](/help/workfront-fusion/references/apps-and-modules/assets/www-to-dl-350x32.png)に置き換える

* さらに、?dl=0 を削除します。

  ![DL](/help/workfront-fusion/references/apps-and-modules/assets/remove-dl0-350x33.png)を削除

これを 1 回で実行するには、これらの関数を次のように組み合わせます。

![両方を置換](/help/workfront-fusion/references/apps-and-modules/assets/replace-both-350x47.png)

次のコードをコピーして、フィールドにペーストすることもできます。`1.url` を URL に置き換えます。

```
{{replace(replace(1.url; "?dl=0"; ""); "www"; "dl")}}
```
