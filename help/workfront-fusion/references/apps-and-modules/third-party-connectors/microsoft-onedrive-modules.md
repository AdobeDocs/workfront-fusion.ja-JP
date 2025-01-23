---
title: Microsoft OneDrive モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、OneDrive を使用するワークフローを自動化し、複数のサードパーティのアプリケーションやサービスに接続できます。'
author: Becky
feature: Workfront Fusion
exl-id: d21eafad-9c67-4f42-b718-0aa4223846e6
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '3285'
ht-degree: 80%

---

# [!DNL Microsoft OneDrive] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL OneDrive] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!DNL OneDrive] モジュールを使用するには、[!DNL Microsoft OneDrive] アカウントが必要です。



## OneDrive API 情報

OneDrive コネクタでは、次の機能を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://graph.microsoft.com/v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v2.0.10</td> 
  </tr>
 </tbody> 
 </table>


## [!DNL OneDrive] サービスを [!DNL Workfront Fusion] に接続

[!DNL OneDrive] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

## [!DNL Microsoft OneDrive] モジュールとそのフィールド

[!DNL OneDrive] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL OneDrive] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ファイルまたはフォルダー](#filefolder)
* [その他](#other)

### ファイルまたはフォルダー

* [[!UICONTROL Watch Files/Folders]](#watch-filesfolders)
* [[!UICONTROL Search Files/Folders]](#search-filesfolders)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Download a file]](#download-a-file)
* [[!UICONTROL Upload a file]](#upload-a-file)
* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Get a Share Link]](#get-a-share-link)
* [[!UICONTROL Move a File/Folder]](#move-a-filefolder)
* [[!UICONTROL Copy a File]](#copy-a-file)
* [[!UICONTROL Delete a File/Folder]](#delete-a-filefolder)

#### [!UICONTROL Watch Files/Folders]

このトリガーモジュールは、ファイルまたはフォルダーが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Files/Folders]</td> 
   <td> <p>ファイルやフォルダーの監視方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL By Created Time]</b> </p> <p>新しいファイルまたはフォルダーを監視します。</p> </li> 
     <li> <p><b>[!UICONTROL By Updated Time]</b> </p> <p>更新された既存のファイルまたはフォルダーを監視します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>監視する場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>モジュールが監視するドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> <p>モジュールが監視するフォルダーに移動します。クエリを入力して、返された結果をフィルターすることもできます。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Shared With Me]</b> </p> <p>モジュールは、ドライブの所有者と共有されたファイルを監視します。</p> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>モジュールが監視する SharePoint Site を選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>モジュールが監視するドライブのグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose an Item Type]</td> 
   <td> <p>監視対象を、ファイル、フォルダまたはその両方から選択します。</p> <p>注意：[!UICONTROL Shared With Me] ドライブ内のフォルダを監視することはできません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>



#### [!UICONTROL Search Files/Folders]

この検索モジュールは、設定した条件に基づいてファイルおよびフォルダーを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>検索する場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>モジュールで検索するドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> <p>モジュールで検索するフォルダーに移動します。クエリを入力して、返された結果をフィルターすることもできます。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Shared With Me]</b> </p> <p>モジュールは、ドライブの所有者と共有されているファイルを検索します。</p> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>モジュールで検索する [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>モジュールで検索するドライブのグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose an Item Type]</td> 
   <td> <p>検索対象を、ファイル、フォルダまたはその両方から選択します。</p> <p>注意：[!UICONTROL Shared With Me] ドライブ内のフォルダは検索できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

このアクションモジュールは、指定されたファイルのメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>ファイルをファイル ID で識別するか、ファイルパスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>ファイル ID またはファイルパスの入力方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>検索する場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>取得するファイルが含まれているドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>取得するファイルが含まれている SharePoint サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>取得するファイルが含まれているドライブグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>取得するファイルが含まれているドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td> 
   <td> <p>「[!UICONTROL Enter Manually]」を選択した場合は、取得するファイルのファイル ID またはパスを入力またはマップします。</p> <p>[!UICONTROL Select from the list] を選択した場合は、取得するファイルを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a file]

このアクションモジュールは、指定されたファイルをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>ファイルをファイル ID で識別するか、ファイルパスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ファイル ID／ファイルパスを入力</td> 
   <td> <p>ファイル ID またはファイルパスの入力方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>ダウンロードするファイルがある場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>ダウンロードするファイルがあるドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>ダウンロードするファイルがある SharePoint のサイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>ダウンロードするファイルがあるドライブが属するグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>ダウンロードするファイルがあるドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td>
   <td> <p>「[!UICONTROL Enter Manually]」を選択した場合は、ダウンロードするファイルのファイル ID またはパスを入力またはマップします。</p> <p>[!UICONTROL Select from the list] を選択した場合は、ダウンロードするファイルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Convert to PDF]</td> 
   <td> <p>ファイルを PDF ファイルに変換するには、このオプションを有効にします。以下のファイル形式から変換できます。</p> 
    <table style="table-layout:auto"> 
     <col> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td> 
        <ul> 
         <li> <p> <p>CSV</p> </p> </li> 
         <li> <p> <p>DOC</p> </p> </li> 
         <li> <p> <p>DOCX</p> </p> </li> 
         <li> <p> <p>ODP</p> </p> </li> 
         <li> <p> <p>ODS</p> </p> </li> 
         <li> <p> <p>ODT</p> </p> </li> 
        </ul> </td> 
       <td> 
        <ul> 
         <li> <p> <p>POT</p> </p> </li> 
         <li> <p> <p>POTM</p> </p> </li> 
         <li> <p> <p>POTX</p> </p> </li> 
         <li> <p> <p>PPS</p> </p> </li> 
         <li> <p> <p>PPSX</p> </p> </li> 
         <li> <p> <p>PPSXM</p> </p> </li> 
        </ul> </td> 
       <td> 
        <ul> 
         <li> <p>PPT</p> </li> 
         <li> <p>PPTM</p> </li> 
         <li> <p>PPTX</p> </li> 
         <li> <p>RTF</p> </li> 
         <li> <p>XLS</p> </li> 
         <li> <p>XLSX</p> </li> 
        </ul> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

このアクションモジュールは、指定されたフォルダーにファイルをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">（フォルダーの場所 ID とパス）を入力</td> 
   <td>ターゲットフォルダーを ID で識別するか、パスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>ファイルをアップロードする場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>取得するファイルがあるドライブを選択します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>ファイルをアップロードするフォルダーがある [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>ファイルをアップロードするフォルダーを含んだドライブを所有するグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>ファイルをアップロードするフォルダーを含んだドライブを選択します。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL If the File with the Same Name Exists]</td> 
   <td>同じ名前のファイルが既に存在する場合の続行方法を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>アップロードするファイルの説明を追加します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

このアクションモジュールは、指定されたドライブに新規フォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>フォルダーを作成する場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>フォルダーを作成するドライブを選択します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>フォルダーを作成する [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>フォルダーを作成するドライブを所有するグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>フォルダーを作成するドライブを選択します。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>新規フォルダーをサブフォルダーにする場合は、サブフォルダーの親になるフォルダーに移動します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Folder Name]</td> 
   <td> <p>新しいフォルダーの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL If the Folder with the Same Name Exists]</td> 
   <td>同じ名前のファイルが既に存在する場合の続行方法を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Share Link]

このアクションモジュールは、指定されたファイルの共有リンクを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>ファイルをファイル ID で識別するか、ファイルパスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>ファイル ID またはファイルパスの入力方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>取得する共有リンクの対象となる場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>取得する共有リンクの対象ファイルが含まれているドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>取得する共有リンクの対象ファイルが含まれている SharePoint サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>取得する共有リンクの対象ファイルが含まれているドライブが属するグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>取得する共有リンクの対象ファイルが含まれているドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td> 
   <td> <p>[!UICONTROL Enter Manually] を選択した場合、共有リンクを取得するファイルのファイル ID またはパスを入力またはマップします。</p> <p>リストから [!UICONTROL Select] を選択した場合、共有リンクを取得するファイルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permission Type]</td> 
   <td> <p>リンクを持つユーザーがファイルの読み取りと書き込みを行えるようにするか、読み取り専用にするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td>リンクを持つユーザーなら誰でもファイルを使用できるようにするか、リンクを持つ組織のメンバーのみがファイルを使用できるようにするかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder]

このアクションモジュールは、ファイルまたはフォルダーを新しいフォルダーの場所に移動します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>ファイルをファイル ID で識別するか、ファイルパスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID / File Path]</td> 
   <td> <p>ファイル ID またはファイルパスの入力方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>移動するファイルまたはフォルダーが含まれる場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>移動するファイルまたはフォルダーが含まれるドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>移動するファイルまたはフォルダーが含まれる [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>移動するファイルまたはフォルダーが含まれるドライブが属するグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>移動するファイルまたはフォルダーが含まれるドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">選択 [!UICONTROL File/Folder]</td> 
   <td>ファイルを移動するか、フォルダーを移動するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</p> <p role="rowheader">[!UICONTROL Folder] / [!UICONTROL Folder ID] / [!UICONTROL Folder Path]</p> </td> 
   <td> <p>[!UICONTROL Enter Manually] を選択した場合は、移動するファイルまたはフォルダの ID またはパスを入力またはマップします。</p> <p>一覧から [!UICONTROL Select] を選択した場合は、移動するファイルまたはフォルダを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a New Folder Location]</td> 
   <td> <p>ファイルまたはフォルダーの移動先を入力する方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>ファイルまたはフォルダーの移動先を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>ファイルまたはフォルダーの移動先となるドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>ファイルまたはフォルダーの移動先となる [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>ファイルまたはフォルダーの移動先となるドライブのグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>ファイルまたはフォルダーの移動先のフォルダーが含まれるドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> <p>これを空白のままにすると、ファイルまたはフォルダーを同じ [!DNL OneDrive] 内でのみ移動できます。</p> <p>[!UICONTROL My Drive] から [!UICONTROL Site's Drive] または [!UICONTROL Group's Drive] にファイルやフォルダを移動できます。 </p> <p>[!UICONTROL Site's Drive] ージから同じサイト内の同じドライブにのみファイルを移動できます。</p> <p>ファイルを [!UICONTROL Group's Drive] から同じグループ内の同じドライブにのみ移動できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>ファイルまたはフォルダーの移動先となるフォルダーを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy a File]

このアクションモジュールは、ファイルを新しいフォルダー場所にコピーします

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>ファイルをファイル ID で識別するか、ファイルパスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>ファイル ID またはファイルパスの入力方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>コピーするファイルが含まれている場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>コピーするファイルまたはフォルダーが含まれているドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>移動するファイルが含まれている SharePoint サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>コピーするファイルが含まれているドライブのグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>コピーするファイルが含まれているドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</p> </td> 
   <td> <p>[!UICONTROL Enter Manually] を選択した場合は、コピーするファイルの ID またはパスを入力またはマップします。</p> <p>リストから [!UICONTROL Select] を選択した場合は、コピーするファイルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a New Folder Location]</td> 
   <td> <p>ファイルのコピー先を入力する方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なフォルダーのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New OneDrive location]</td> 
   <td> <p>ファイルのコピー先を選択します。このオプションは、リストから新しいフォルダー場所を選択することを選んだ場合に使用できます。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>ファイルをコピーするドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>ファイルをコピーする [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>ファイルをコピーするドライブのグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>ファイルのコピー先のフォルダーが含まれているドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> <p>これを空白のままにすると、ファイルまたはフォルダは同じ [!UICONTROL OneDrive] 内でのみコピーできます。</p> <p>[!UICONTROL My Drive] から [!UICONTROL Site's Drive] または [!UICONTROL Group's Drive] にファイルやフォルダーをコピーできます。 </p> <p>[!UICONTROL Site's Drive] から同じサイトの同じドライブにのみファイルをコピーできます。</p> <p>[!UICONTROL Group's Drive] ージから同じグループ内の同じドライブにのみファイルをコピーできます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>コピーまたはフォルダーの移動先のフォルダーを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Copied File Name]</td> 
   <td> <p>ファイルの新しいコピーの名前を入力またはマッピングします。元のファイル名を変更しない場合は、このフィールドを空白のままにすることができます。</p> <p>名前にはファイル拡張子を含める必要があります。例：<code> file.txt</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File/Folder]

このアクションモジュールは、選択されたファイルまたはフォルダーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File/Folder ID & Path)]</td> 
   <td>ファイルをファイル ID で識別するか、ファイルパスで識別するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File/Folder ID /Enter a File/Folder Path]</td> 
   <td> <p>ファイル ID またはファイルパスの入力方法を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>ID またはパスを直接入力する場合、または以前のモジュールからマッピングする場合は、このオプションを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>使用可能なファイルまたはパスのリストから選択する場合は、このオプションを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 場所 ]</td> 
   <td> <p>検索する場所を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>モジュールがドライブ ID を入力できるようにするかどうかを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>削除するファイルまたはフォルダーが含まれているドライブの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>削除するファイルまたはフォルダーが含まれている [!DNL SharePoint] サイトを選択します。利用可能なサイトとは、ログイン中のユーザーがフォローしているサイトです。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>削除するファイルまたはフォルダーが含まれているドライブのグループを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>削除するファイルまたはフォルダーが含まれているドライブを選択またはマッピングします。[!UICONTROL Enable to Enter a Drive ID] のフィールドで「[!UICONTROL No]」を選択した場合は、このフィールドは使用できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">選択 [!UICONTROL File/Folder]</td> 
   <td>ファイルを削除するか、フォルダーを削除するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td>
   <td> <p>[!UICONTROL Enter Manually] を選択した場合は、削除するファイルのファイル ID またはパスを入力するか、またはマップします。</p> <p>リストから [!UICONTROL Select] を選択した場合は、削除するファイルを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

#### [!UICONTROL Make an API Call]

このモジュールは、カスタム API 呼び出しを実行します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL OneDrive] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://graph.microsoft.com</code> からの相対パスを入力します。例：<code> /v1.0/me/drive/root/children</code></td> 
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



## ファイルをアップロードまたは更新できない場合

ファイルのアップロードまたは更新に失敗する場合は、次のような問題が考えられます。

* アップロードされたファイルが大きすぎて、利用中の [!DNL OneDrive] プランの最大ファイルサイズの上限を超えているか、[!DNL OneDrive] アカウントのストレージ割当をすべて使い切っている。ストレージスペースを増やすには、[!DNL OneDrive] から既存のファイルを削除するか、[!DNL OneDrive] アカウントをアップグレードします。
* OneDrive では、同じ名前の 2 つのファイルを 1 つのフォルダーにアップロードできない。ターゲットフォルダーにアップロードするファイルと同じ名前のファイルがある場合、シナリオの実行はエラーで終了します。解決策は、アップロードするファイルの名前を変更することです。ファイルを更新する場合は、[!UICONTROL Update a file] のアクションを使用します。
* ファイルのアップロード先として選択済みのフォルダーが存在しない。シナリオが停止するので、ターゲットフォルダーをもう一度選択する必要があります。
