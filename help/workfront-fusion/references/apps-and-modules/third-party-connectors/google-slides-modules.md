---
title: Google Slides モジュール
description: Adobe Workfront Fusion Google Slides モジュールを使用すると、プレゼンテーションの作成、更新、リスト作成、削除を行ったり、Google Slides アカウントでプレゼンテーションに画像をアップロードしたりできます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 6f5f97b9-b06a-4336-b349-ee9e2606d4bf
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 56%

---

# [!DNL Google Slides] モジュール

[!DNL Adobe Workfront Fusion] [!DNL Google Slides] モジュールを使用すると、プレゼンテーションの作成、更新、リスト作成、削除を行ったり、[!DNL Google Slides] アカウントでプレゼンテーションに画像をアップロードしたりできます。

[!DNL Google Slides] と [!DNL Workfront Fusion] を併用する場合、[!DNL Google] アカウントが必要です。[!DNL Google] アカウントをまだお持ちでない場合は、[!DNL Google] アカウントのヘルプページで作成できます。

[!DNL Google Drive] には [!DNL Google Slides] も必要です。

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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

[!DNL Google Slides] モジュールを使用するには、[!DNL Google] アカウントが必要です。

## Google スライド API 情報

Google スライド コネクタでは、次を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://slides.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.5.9</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Slides] モジュールとそのフィールド

[!DNL Google Slides] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Google Slides]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [プレゼンテーション](#presentation)
* [その他](#other)

### プレゼンテーション

* [[!UICONTROL スライドを追加または削除]](#adddelete-a-slide)
* [[!UICONTROL テンプレートからプレゼンテーションを作成]](#create-a-presentation-from-a-template)
* [[!UICONTROL ページ／サムネールを取得]](#get-a-pagethumbnail)
* [[!UICONTROL プレゼンテーションを取得]](#get-a-presentation)
* [[!UICONTROL プレゼンテーションをリスト]](#list-presentations)
* [[!UICONTROL グラフを更新]](#refresh-a-chart)
* [[!UICONTROL プレゼンテーションに画像をアップロード]](#upload-an-image-to-a-presentation)
* [[!UICONTROL プレゼンテーションを監視]](#watch-presentations)

#### [!UICONTROL スライドを追加または削除]

指定したプレゼンテーションのスライドを作成するか、既存のスライドを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the method]</td> 
   <td> <p>新しいスライドを追加するか、スライドを削除するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Enter a Slide ID]</td> 
   <td> <p>スライドを削除する場合は、スライド ID を手動で入力するか、リストからスライドを選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Presentation ID]</td> 
   <td> <p>プレゼンテーションを選択するか、スライドを追加または削除するプレゼンテーションのプレゼンテーション ID をマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Slide Object ID]</td> 
   <td> <p>スライドを削除していて、手動でスライドを入力することを選択した場合は、スライド ID を入力またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Predefined layout type]</td> 
   <td> <p> 追加したスライドで使用する定義済みのスライドレイアウトを選択します。追加のフィールド（[!UICONTROL Title] など）の値を指定します。</p> 
    <ul> 
     <li>[!UICONTROL Blank layout, with no placeholders]</li> 
     <li>[!UICONTROL Layout with a caption at the bottom]</li> 
     <li>[!UICONTROL Layout with a title and subtitle]</li> 
     <li>[!UICONTROL Layout with a title and body]</li> 
     <li>[!UICONTROL Layout with a title and two columns]</li> 
     <li>[!UICONTROL Layout with only a title]</li> 
     <li>[!UICONTROL Layout with a section title]</li> 
     <li>[!UICONTROL Layout with a title and subtitle on one side and description on the other]</li> 
     <li>[!UICONTROL Layout with one title and one body, arranged in a single column]</li> 
     <li>[!UICONTROL Layout with a main point]</li> 
     <li>[!DNL Layout with a big number heading]</li> 
    </ul> <p>このフィールドは、スライドを追加する場合に使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Content]</td> 
   <td> <p>スライドのテキストコンテンツを入力またはマッピングします。 フィールドは、選択したテンプレートに基づいて使用可能になります。</p> <p>このフィールドは、スライドを追加する場合に使用できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL テンプレートからプレゼンテーションを作成]

このアクション モジュールは、プレゼンテーションをコピーし、`{{Name}}` のようなすべてのタグを指定されたデータに置き換えることで `{{Email}}` 新しいプレゼンテーションを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>新しいプレゼンテーションの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy a Presentation]</td> 
   <td> <p> 既存のプレゼンテーションをコピーする場合は、オプションを選択します。</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy of Existing Presentation ID]</td> 
   <td> <p> コピーする既存のプレゼンテーションのパスまたはプレゼンテーション ID を入力します。このフィールドは、プレゼンテーション [!UICONTROL By Mapping] を作成する場合に表示されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>リストするプレゼンテーションがある [!DNL Google Drive] を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul> <p>このフィールドは、プレゼンテーション [!UICONTROL By Dropdown] を作成する場合に表示されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> プレゼンテーションを選択するか、テンプレートとして使用するプレゼンテーションのプレゼンテーション ID を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values] </td> 
   <td> <p>次の値を追加します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Tag]</strong>：プレゼンテーションで置き換えるタグを入力します。例： <code>&#123;&#123;Name&#125;&#125;</code></li> 
     <li><strong>[!UICONTROL Replaced Value]</strong>：既存のタグを置き換える値を入力します。たとえば、プレゼンテーションに文字列 <code>&#123;&#123;Name&#125;&#125;</code> があり、置き換えられた値が Sample の場合、<code>&#123;&#123;Name&#125;&#125;</code> は <code>Sample</code> に置き換えられます。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 新しいドライブの場所 ]</td> 
   <td> <p>新しいプレゼンテーションを保存または追加する [!DNL Google Drive] を選択してください：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 新しいドキュメントの場所 ]</p> </td> 
   <td> <p>プレゼンテーションを保存または追加するフォルダを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 共有 ] </td> 
   <td> <p>プレゼンテーションを共有する場合に選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 他者の電子メール アドレスと共有 ]</td> 
   <td> <p> プレゼンテーションを共有する電子メール アドレスを入力します。 このフィールドに電子メールを入力せずに [ 共有 ] オプションを有効にすると、プレゼンテーションはすべてのユーザーと共有できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ページ／サムネールを取得]

このアクション モジュールは、指定されたページまたはプレゼンテーション内のページのサムネイルの最新バージョンを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プレゼンテーションとページ ID を入力 ]</td> 
   <td> <p> プレゼンテーションとページ ID を手動で入力するか、リストから選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 取得するプレゼンテーション ID を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page Object ID]</td> 
   <td> <p> ページオブジェクトの詳細を表示するスライドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Page Thumbnail]</td> 
   <td> <p> ページのサムネール情報を表示する場合は、このチェックボックスを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プレゼンテーションを取得]

指定したプレゼンテーションの最新バージョンを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>リストするプレゼンテーションがある [!DNL Google Drive] を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 取得するプレゼンテーションを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プレゼンテーションをリスト]

このモジュールは、指定された場所にあるすべてのプレゼンテーションのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive location]</td> 
   <td> <p>リストするプレゼンテーションが格納されている [!DNL Google Drive] を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p>リストするプレゼンテーションのフォルダーの場所を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>1 つのシナリオの実行サイクルでモジュールが返すプレゼンテーションの最大数を入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL グラフを更新]

アクション モジュールは、ID で指定されたプレゼンテーションに保存されているグラフ データを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プレゼンテーション ID を入力 ]</td> 
   <td> <p> プレゼンテーション ID を手動で入力するか、リストから選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>一覧からプレゼンテーションを選択する場合は、一覧に表示するプレゼンテーションの [!DNL Google Drive] を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>プレゼンテーションを選択するか、更新するグラフを含むプレゼンテーションのプレゼンテーション ID を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Chart Object ID]</td> 
   <td> <p> データを手動で入力する場合は、更新するグラフの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プレゼンテーションに画像をアップロード]

指定したデータを使用して画像をアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>画像のアップロード先のプレゼンテーションを選択する方法を選択します。</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!DNL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>ドロップダウンから選択する場合は、画像を追加するプレゼンテーションがある [!DNL Google Drive] を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 画像のアップロード先のプレゼンテーションのプレゼンテーション ID を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メソッドの選択 ]</td> 
   <td> <p> 画像の置き換え方法を選択します。</p>
   <ul>
   <li><p><b>テキストタグを置換して画像をアップロード</b></p><p>「値」フィールドで、アップロードする各画像に対して <b> 項目を追加 </b> をクリックし、画像のタグと新しい画像の URL を入力します。</p></li>
   <li><p><b>画像を置換して画像をアップロード</b></p><p>「値」フィールドで、アップロードする各画像に対して「<b> 項目を追加 </b> をクリックし、画像のオブジェクト ID、置き換えメソッド、新しい画像の URL を入力します。</p></li>
   </ul>
  <p>メモ：画像のサイズは 50MB 未満、25 メガピクセルを超えることはできず、PNG、JPEG、または GIF 形式にする必要があります。</p>   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プレゼンテーションを監視]

このトリガー モジュールは、新しいプレゼンテーションが作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch] </td> 
   <td> <p>プレゼンテーションを監視するには、次のオプションを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Created Date]</p> </li> 
     <li> <p>[!UICONTROL Modified Date]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>1 つのシナリオの実行サイクルでWorkfront Fusion が返すプレゼンテーションの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

* [[!UICONTROL プレゼンテーションへのリンクの挿入]](#insert-links-in-a-presentation)
* [[!UICONTROL API 呼び出しの実行]](#make-an-api-call)

#### [!UICONTROL プレゼンテーションへのリンクの挿入]

このモジュールは、プレゼンテーション内のすべてのリンクをクリック可能にするか、一致するすべての入力テキストにリンクを挿入します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>画像のアップロード先のプレゼンテーションを選択する方法を選択します。</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>リストするプレゼンテーションがある [!DNL Google Drive] を選択します。</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Shared Drive]</li> 
    </ul> <p>このフィールドは、プレゼンテーション [!UICONTROL By Dropdown] を作成する場合に表示されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>リストするプレゼンテーションのフォルダーの場所を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select]</td> 
   <td> <p>プレゼンテーション内のすべてのリンクをクリック可能にするか、すべての一致する入力テキストにリンクを挿入するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text Inputs]</td> 
   <td>リンクを挿入する場合は、リンクを追加する各テキスト項目に対して [<b> 項目の追加 </b>] をクリックし、テキストと関連するリンクを入力します。 アイテムは、プレゼンテーションに表示されるたびに、指定したサイトに自動的にリンクされます。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL API 呼び出しの実行]

許可された任意の API 呼び出しを実行します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Slides] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p><code>https://developers.google.com/slides/</code> からの相対パスを入力します。例：プレゼンテーション。</p> <p>使用可能なエンドポイントの一覧については、<a href="https://developers.google.com/slides/reference/rest">[!DNL Google Slides] API ドキュメント</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>希望するリクエストヘッダーを入力します。認証ヘッダーを追加する必要はありません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> リクエストクエリ文字列を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例：** API 呼び出しを使用して、入力したプレゼンテーション ID のプレゼンテーションの詳細を取得できます。プレゼンテーション ID は、[!DNL Google Slides] 内でプレゼンテーションを開いた時に URL の中で確認できます。

![API 呼び出しの例 ](/help/workfront-fusion/references/apps-and-modules/assets/api-call-350x13.png)

次の API 呼び出しは、プレゼンテーションの詳細を返します。

![ プレゼンテーションの詳細 ](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details.png)

一致した検索結果は、モジュールの「出力」にある[!UICONTROL バンドル]／[!UICONTROL 本文]／[!UICONTROL presentationId] で確認できます。

この例では、要求されたプレゼンテーションの詳細が返されました。

![ プレゼンテーションの詳細 ](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details-2.png)

>[!ENDSHADEBOX]
