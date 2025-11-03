---
title: Box モジュール
description: Adobe Workfront Fusion シナリオでは、Box を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。 指定されたフォルダーを監視して、ファイルの変更を確認したり、既存のファイルを変更および削除したり、新しいファイルをフォルダーにアップロードしたりします。
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 26%

---

# Box モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Box] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。 指定されたフォルダーを監視して、ファイルの変更を確認したり、既存のファイルを変更および削除したり、新しいファイルをフォルダーにアップロードしたりします。

シナリオの作成方法については、[&#x200B; シナリオの作成：記事のインデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。 モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

## 前提条件

[!DNL Box] モジュールを使用するには、[!DNL Box] アカウントが必要です。

## Box API 情報

ボックスコネクタでは、次の機能を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.box.com/2.0
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v3.0.3</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Box] モジュールとそのフィールド

[!DNL Box] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Box]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

* [[!UICONTROL &#x200B; 新規ファイル イベント &#x200B;]](#new-file-event)
* [新規フォルダーイベント](#new-folder-event)
* [[!UICONTROL ファイルの監視]](#watch-files)

#### [!UICONTROL &#x200B; 新規ファイル イベント &#x200B;]

選択したアクションがファイルに対して実行されると、このインスタント トリガー モジュールはシナリオを開始します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>送信メッセージを監視するために使用する Webhook を選択するか、Webhook を追加します。 </p><p>Webhook を追加するには、<strong>[!UICONTROL Add]</strong> をクリックして、Webhook の名前と接続、監視するファイル、監視するトリガーを入力します。</p> <p> [!UICONTROL Box] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> サービスへの接続 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 新規フォルダーイベント

このインスタントトリガーモジュールは、フォルダーで選択アクションが発生するとシナリオを開始します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>送信メッセージを監視するために使用する Webhook を選択するか、Webhook を追加します。 </p><p>Webhook を追加するには、<strong>[!UICONTROL Add]</strong> をクリックして、Webhook の名前と接続、監視するフォルダー、監視するトリガーを入力します。</p> <p> [!UICONTROL Box] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> サービスへの接続 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルの監視]

このトリガーモジュールは、新しいファイルが追加されたとき、または既存のファイルが監視対象のフォルダー内で更新されたときに、シナリオを開始します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Box] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">監視フォルダー</td> 
   <td> <p>監視するフォルダーを選択します。 シナリオでは、1 つのフォルダーを監視できます。</p> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">監視</td> 
   <td> <p>監視するファイルのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>新しいファイルのみ</strong> </p> <p>新しいファイルが追加されると、シナリオが開始します。</p> </li> 
     <li> <p><strong>新しいファイルとすべての変更</strong> </p> <p>このシナリオは、ファイルが追加されたとき、またはファイルの内容やファイル属性（名前など）が変更されたときに開始されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ダウンロードされたファイルの最大数</p> </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すファイルの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

<!--* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Update a file]](#update-a-file)
* [[!UICONTROL Upload] a file](#upload-a-file)-->
* [フォルダーを作成](#create-a-folder)
* [フォルダーの取得](#get-a-folder)
* [フォルダーメタデータの取得](#get-folder-metadata)
* [API 呼び出しを実行](#make-an-api-call)
* [フォルダーメタデータの更新](#update-folder-metadata)

<!--#### [!UICONTROL Delete a file] 

This action module deletes a file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to delete.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

This action module downloads a file.

You specify the ID of the file.

>[!NOTE]
>
>This module is useful for providing files to subsequent modules.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to retrieve.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a file] 

This action module updates a file.

You specify the ID of the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to update.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file] 

This action module uploads a file.

You specify the file. You can also provide a new filename for the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Select the folder where you want to upload the file.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>If this module is not successful, consider the following:
>
>* The size of the file might exceed the maximum file size limit for your [!DNL Box] plan, or you may have used all of your [!DNL Box] account's storage quota. To get more storage space, delete existing files from [!DNL Box] or upgrade your [!DNL Box] account.
>* [!DNL Box] does not upload more than one files with the same name to a single folder. If the destination folder contains a file with the same name as the file being uploaded, the scenario run terminates with an error. To avoid this, rename the file. If you want to update the file, use the **[!UICONTROL Update a file]** module.-->

#### フォルダーを作成

このアクションモジュールは、指定された親フォルダー内に新しい空のフォルダーを作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td> <p>新しいフォルダーの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 親フォルダー &#x200B;]</td> 
   <td> <p>新しいフォルダーを作成するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL フォルダーアップロード E メール アクセス &#x200B;]</td> 
   <td> <p>このパラメーターを設定すると、ユーザーはこのフォルダー用に自動的に作成されたメールアドレスにファイルをメールで送信できます。 「共同作業者」オプションでは、共同作業者に対して登録済みのメールのみが許可されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 同期状態 &#x200B;]</td> 
   <td> <p>フォルダーをユーザーのデバイスに同期するかどうかを指定します。 これは Box Sync （廃止）で使用され、Box Drive では使用されません。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### フォルダーの取得

このアクションモジュールは、フォルダーの最初の 100 エントリなど、フォルダーの詳細を取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>詳細を取得するフォルダーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### フォルダーメタデータの取得

このアクションモジュールは、フォルダー ID でフォルダーメタデータを取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>このメタデータ取得に使用する範囲を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>メタデータを取得するフォルダーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### API 呼び出しを実行

このアクションモジュールは、Box API に対してカスタム呼び出しを行います。



<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Bynder] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">Workfront Fusion [!DNL Bynder] への </a> の接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td><code>https://api.box.com</code> への相対パスを入力します。 <p>例： <code>/2.0/users/me</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
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

#### フォルダーメタデータの更新

フォルダーのメタデータを作成または更新します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>このメタデータの更新に使用する範囲を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>メタデータを更新するフォルダーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>


### 検索

#### コンテンツの検索

この検索モジュールは、ユーザーまたは企業が使用できる項目を検索します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>検索する文字列を入力またはマッピングします。 このクエリは、項目名、説明、ファイルのテキストコンテンツおよび異なる項目タイプのその他の様々なフィールドと照合されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>このモジュールで使用される接続で資格情報が使用されるユーザーに関連付けられたコンテンツを検索するか、企業全体に関連付けられたコンテンツを検索するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> <p>ファイル、フォルダー、Web リンクのどちらを検索するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>関連度または変更日のどちらで並べ替えるかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ごみ箱コンテンツ &#x200B;]</td> 
   <td> <p>ハッシュ化されたコンテンツとハッシュ化されていないコンテンツのどちらを検索するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 親フォルダー ID]</td> 
   <td> <p>特定のフォルダーを検索するには、検索する各フォルダーに対して「<b> 項目を追加 </b>」をクリックし、フォルダーの ID を入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の作成元 &#x200B;]</td> 
   <td> <p>特定の日付範囲で作成されたアセットを検索するには、その範囲内の最も古い日付を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の作成先 &#x200B;]</td> 
   <td> <p>特定の日付範囲で作成されたアセットを検索するには、その日付範囲の最新の日付を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL が次から更新されました：]</td> 
   <td> <p>特定の日付範囲で更新されたアセットを検索するには、範囲内の最も古い日付を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の更新先 &#x200B;]</td> 
   <td> <p>特定の日付範囲で更新されたアセットを検索するには、その範囲の最新の日付を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>モジュールの応答で返す属性ごとに、「<b> 項目を追加 </b>」をクリックしてフィールドを入力します。</p><p>これは、通常は標準応答で返されないフィールドをリクエストするために使用できます。 このパラメーターを指定すると、明示的に指定しない限り、応答で標準フィールドが返されないことに注意してください。 </p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ファイル拡張子 &#x200B;]</td> 
   <td> <p>検索を特定のファイル拡張子に制限するには、ファイル拡張子のコンマ区切りリストを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズの基点 &#x200B;]</td> 
   <td> <p>特定のサイズ範囲のアセットを検索するには、範囲の小さい方の端をバイト単位で入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL のサイズを指定 &#x200B;]</td> 
   <td> <p>特定のサイズ範囲のアセットを検索するには、範囲の大きい方の端をバイト単位で入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 所有者ユーザー ID]</td> 
   <td> <p>特定のユーザーが所有するアセットを検索するには、所有者 ID のコンマ区切りリストを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各実行サイクルでモジュールが返す結果の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>


