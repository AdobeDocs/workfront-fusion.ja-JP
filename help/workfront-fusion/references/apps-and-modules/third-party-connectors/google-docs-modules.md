---
title: Google ドキュメントモジュール
description: Adobe Workfront Fusion [!DNL Google Docs] module を使用すると、自分の  [!DNL Google Docs]  や  [!DNL Google Docs]  （ユーザー向け）でドキュメントをモニター、作成、編集  [!DNL Google Workspace]  取得できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: cd44250d-c2cd-46b2-8773-15b30472a8d8
source-git-commit: 5a95b2c191d4e6d8750dc57a47923f416612b4a9
workflow-type: tm+mt
source-wordcount: '3222'
ht-degree: 65%

---

# [!DNL Google Docs] モジュール

[!DNL Adobe Workfront Fusion] [!DNL Google Docs] モジュールを使用すると、[!DNL Google Docs] や [!DNL Google Docs] （[!DNL Google Workspace] ユーザー用）のドキュメントを監視、作成、編集、取得できます。

[!DNL Google Docs] を [!DNL Adobe Workfront Fusion] で使用するには、[!DNL Google] アカウントが必要です。[!DNL Google] アカウントをまだお持ちでない場合は、[!DNL Google] アカウントのヘルプページで作成できます。

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

[!DNL Google Docs] モジュールを使用するには、Google アカウントが必要です。

## Google Docs API の情報

Google Docs コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://docs.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.4.13</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Docs] モジュールとそのフィールド

[!DNL Google Docs] モジュールを設定する際、[!UICONTROL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Google Docs] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### ドキュメント

* [[!UICONTROL Watch Documents]](#watch-documents)
* [[!UICONTROL List Documents]](#list-documents)
* [[!UICONTROL Get Content of a Document]](#get-content-of-a-document)
* [[!UICONTROL Create a Document]](#create-a-document)
* [[!UICONTROL Create a Document From a Template]](#create-a-document-from-a-template)
* [[!UICONTROL Insert a Paragraph to a Document]](#insert-a-paragraph-to-a-document)
* [[!UICONTROL Insert an Image to a Document]](#insert-an-image-to-a-document)
* [[!UICONTROL Replace an Image with a New Image]](#replace-an-image-with-a-new-image)
* [[!UICONTROL Replace Text in a Document]](#replace-text-in-a-document)
* [[!UICONTROL Download a Document]](#download-a-document)
* [[!UICONTROL Delete a Document]](#delete-a-document)

#### [!UICONTROL Watch Documents]

このトリガーモジュールは、選択したフォルダーで新しいドキュメントが作成または変更されたときに、ドキュメントの詳細を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Documents]</td> 
   <td> <p style="color: #000000;">作成済み（[!UICONTROL By Created Date]）ドキュメントと変更済み（[!UICONTROL By Modified Date]）ドキュメントのどちらをウォッチするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>監視するドライブのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>作成されたドキュメントまたは変更されたドキュメントの監視するフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>作成されたドキュメントまたは変更されたドキュメントの監視するフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>監視する共有ドライブを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Shared Drive]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Workfront Fusion が 1 回の実行サイクルで返すドキュメントの数の上限を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Documents]

このアクションモジュールは、選択したフォルダーからドキュメントのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>ドキュメントのリスト元のドライブのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>ドキュメントをリストするフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>ドキュメントをリストするフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>ドキュメントのリストを表示する共有ドライブを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すドキュメントの数の上限を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Content of a Document]

このアクションモジュールは、指定されたドキュメントを取得します。

権限の拡張が必要になる場合があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get Content of a Document]</td> 
   <td> <p>ドキュメントのドキュメント ID をマッピングするかドロップダウンメニューから手動でドキュメントを選択するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>取得するドキュメントを含むドライブのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>取得するドキュメントを含むフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>取得するドキュメントを含むフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>取得するドキュメントを含む共有ドライブを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>モジュールの出力で返すオブジェクトを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Image] (デフォルト)</li> 
     <li>[!UICONTROL Drawing]</li> 
     <li>[!UICONTROL Chart]</li> 
    </ul> <p>メモ：  <p>これらのオブジェクトをさらにマッピングする場合は、このモジュールの出力で（[!UICONTROL inlineObjects] の代わりに） [!UICONTROL Inline Objects Array] 値を使用してください。</p> <p>[!UICONTROL Inline Objects Array] のオブジェクトは、ドキュメントに表示されるのと同じ順序で並べ替えられます。 これにより、以後の処理が容易になります。</p> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document]

このアクションモジュールを使用すると、選択したフォルダーに新しいドキュメントを作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>ドキュメントの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td> <p>ドキュメントのコンテンツを入力します。HTML がサポートされています。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>ドキュメントを作成するドライブのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>ドキュメントを作成するフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>ドキュメントを作成するフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>ドキュメントを作成する共有ドライブを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Header]</td> 
   <td> <p> このオプションを有効にして、ヘッダーをドキュメントに挿入し、ヘッダーのテキストを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Footer] </td> 
   <td> <p>このオプションを有効にして、フッターをドキュメントに挿入し、ヘッダーのテキストを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document From a Template]

このアクションモジュールは、既存のテンプレートドキュメントのコピーを作成し、任意のタグを置き換えます。また、このモジュールでは、画像を URL で新しい画像に置き換えることもできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Create a Document from a Template]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>このオプションを選択して、ドキュメントテンプレートをマッピングします。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br>このオプションを選択して、ドロップダウンメニューからドキュメントテンプレートを選択します。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>テンプレートが配置されているドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>テンプレートが配置されているフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>テンプレートが配置されているフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>テンプレートが配置されている共有ドライブを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>変数の代わりに新規ドキュメントに入力する値を入力します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Tags]</strong> <br>ドキュメントテンプレートに含まれるタグを入力します。 <code>&#123;&#123;&#125;&#125;</code> を使用しないでください。例：<code>&#123;&#123;name&#125;&#125;</code> の代わりに <code>name</code> を使用します。</li> 
     <li><strong>[!UICONTROL Replaced Value]</strong><br>タグの値を入力します。</li> 
    </ul> <p>例えば、ソースドキュメントの <code> &#123;&#123;name&#125;&#125;</code> 変数はここで名前フィールドとして表示され、<code>John</code> などの値を挿入できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Images Replacement]</p> </td> 
   <td> <p>現在の画像を置き換える [!UICONTROL Image Object ID] と [!UICONTROL Image URL] へのリンクを入力します。</p> <p>メモ：画像 ID はモジュールを使用して取得できます [!UICONTROL Get a Document] このモジュールで ID は配列 [!UICONTROL Inline Object Array] に格納されます。</p> <p>[!DNL Google] ドキュメント内の画像に ALT テキストを追加することをお勧めします。 </p> <p>[!DNL Google Docs] 画像に ALT テキストを追加するには、次の手順に従います。</p> 
    <ol> 
     <li value="1">画像を右クリックします。</li> 
     <li value="2">[!UICONTROL ALT text] オプションを選択します。</li> 
     <li value="3">[!UICONTROL Title] フィールドに [!UICONTROL ALT text] を入力し、[!UICONTROL OK] をクリックします。</li> 
    </ol> <p>ALT テキストを画像に追加すると、ALT テキストが括弧内のフィールド名に表示されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>新規ドキュメントの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>テンプレートが配置されているドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>ドキュメントを作成するフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>ドキュメントを作成するフォルダーを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>ドキュメントを作成する共有ドライブを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert a Paragraph to a Document]

このアクションモジュールは、既存のドキュメントに新しい段落を追加または挿入します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>このオプションを選択して、ドキュメントをマッピングします。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> このオプションを選択して、ドロップダウンメニューからドキュメントを選択します。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>段落を追加するドキュメントが存在するドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>段落を追加するドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>段落を追加するドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>段落を追加するドキュメントが存在する共有ドライブを選択し、そのドキュメントを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert a Paragraph]</p> </td> 
   <td> <p>新しいテキストをドキュメントに挿入する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>テキストを挿入するインデックス番号を入力します。[!UICONTROL Get a Document] モジュールを使用してインデックス番号を取得できます。</p> <p>ドキュメント内のすべての文字（非表示を含む）を表示するには、[!UICONTROL Show] アドオンを使用します。 アドオンは、[!UICONTROL Add-ons]/[!UICONTROL Get add-ons] の下にあります。 [!UICONTROL Show] を検索して [!UICONTROL Show] アドオンをインストールします。</p> </li> 
         <li> <p><strong>[!UICONTROL Inserted text]</strong> </p> <p>ドキュメントに挿入するテキストを入力します。</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>テキストコンテンツを挿入するヘッダーとフッターを選択し、挿入するテキストを対応するフィールドに入力します。</p> <p>ヘッダーまたはフッターに既にテキストが含まれている場合は、新しいテキストが既存のテキストの前に追加されます。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>ドキュメントの本文コンテンツの最後に入力したテキストを追加します。</p> <p>新しい段落のスタイルは、リストや箇条書きなど、現在の挿入インデックスにある段落からコピーされます。</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>テキストコンテンツを挿入するヘッダーとフッターを選択し、挿入するテキストを対応するフィールドに入力します。</p> <p>ヘッダーまたはフッターに既にテキストが含まれている場合は、新しいテキストが既存のテキストの後に追加されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Appended Text]</td> 
   <td>ドキュメントに追加するテキストの入力またはマッピング</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert an Image to a Document]

このアクションモジュールは、URL からドキュメントに画像を挿入します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>このオプションを選択して、ドキュメントテンプレートをマッピングします。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> このオプションを選択して、ドロップダウンメニューからドキュメントを選択します。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>画像の追加先のドキュメントが存在するドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>画像の追加先のドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>画像の追加先のドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>画像の追加先のドキュメントが存在する共有ドライブを選択し、ドキュメントを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert an Image]</p> </td> 
   <td> <p>新しい画像をドキュメントに挿入する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>画像を挿入するインデックス番号を入力します。[!UICONTROL Get a Document] モジュールを使用すると、[!UICONTROL Index number] を取得できます。</p> <p>ドキュメント内のすべての文字（非表示を含む）を表示するには、[!UICONTROL Show] アドオンを使用します。 アドオンは、[!UICONTROL Add-ons]/[!UICONTROL Get add-ons] の下にあります。 [!UICONTROL Show] を検索して [!UICONTROL Show] アドオンをインストールします。</p> </li> 
         <li> <p><strong>[!UICONTROL Image URL]</strong> </p> <p>ドキュメントに挿入する画像の URL を入力します。</p> <p>最大画像サイズは 50 MB です。25 メガピクセルを超えないようにしてください。PNG、JPEG、または GIF 形式のみがサポートされます。</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>画像を挿入するヘッダーとフッターを選択し、対応するフィールドに画像 URL を入力します。</p> <p>最大画像サイズは 50 MB です。画像は 25 メガピクセルを超えないようにしてください。PNG、JPEG、または GIF 形式のみがサポートされます。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>ドキュメントの本文コンテンツの最後に特定の画像を追加します。</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>画像を挿入するヘッダーとフッターを選択し、対応するフィールドに挿入する画像 URL を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Height Magnitude in Points/Width Magnitude in Points]</p> </td> 
   <td> <p>挿入する画像のサイズを定義します。アスペクト比は維持されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace an Image with a New Image]

このアクションモジュールは、既存の画像を置き換えます。元の画像のアスペクト比は維持されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>このオプションを選択して、ドキュメントテンプレートをマッピングします。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> このオプションを選択して、ドロップダウンメニューからドキュメントを選択します。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>画像を置き換えるドキュメントが存在するドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>画像を置き換えるドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>画像を置き換えるドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>画像を置き換えるドキュメントが存在する共有ドライブを選択し、ドキュメントを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Image URL]</p> </td> 
   <td> <p>既存の画像を置き換える新しい画像の URL を入力またはマッピングします。</p> <p>画像は、ドキュメント内での表示順に表示されます。例えば、<code>Body: Image No. 1</code> はドキュメント内の最初の画像です。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace Text in a Document]

このアクションモジュールは、ドキュメント内のテキストを置き換えます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>このオプションを選択して、ドキュメントテンプレートをマッピングします。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> このオプションを選択して、ドロップダウンメニューからドキュメントを選択します。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>テキストを追加する文書が保存されているドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>テキストを追加したい文書が保存されているフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>テキストを追加したい文書が保存されているフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>テキストを追加したいドキュメントが保存されている共有ドライブを選択し、ドキュメントを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace a Text]</p> </td> 
   <td> <p>置き換える各テキストを追加します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Old text to be replaced]</strong> </p> <p>置き換えるテキストを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL New text to be inserted]</strong> </p> <p>新しいテキストを入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a Document]

このアクションモジュールは、選択したドキュメントを変換およびダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>ダウンロードするドキュメントが保存されているドライブのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>ダウンロードするドキュメントが保存されているフォルダーを選択し、そのドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>ダウンロードするドキュメントが保存されているフォルダーを選択し、そのドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>ダウンロードするドキュメントが保存されている共有ドライブを選択し、ドキュメントを選択します。</p> <p>メモ：このフィールドで [!DNL Google Docs] オプションを選択し、[!DNL Google Workspace] ユーザーでない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Type] </p> </td> 
   <td> <p>ダウンロードしたドキュメントのターゲットファイル形式を選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Document]

このアクションモジュールは、ドキュメントを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>削除するドキュメントが保存されるドライブのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>削除するドキュメントが保存されているフォルダーを選択し、そのドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>削除するドキュメントが保存されているフォルダーを選択し、そのドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>削除するドキュメントが存在する共有ドライブを選択し、ドキュメントを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>ダウンロードするドキュメントが含まれているドライブを選択し、ドキュメントを選択します。このオプションは、「[!UICONTROL Choose a Drive]」フィールドで「[!DNL Google Docs]」を選択した場合に使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> 1 つ以上の画像を置き換えるドキュメントを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Make All Links in a Document Clickable]](#make-all-links-in-a-document-clickable)

#### [!UICONTROL Make an API Call]

このアクションモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p><code>https://docs.googleapis.com/</code> への相対パスを入力します。例：<code>/v1/documents/{presentationID}</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例えば、<code>{"Content-type":"application/json"}</code>。認証ヘッダーは [!DNL Workfront Fusion] によって追加されます。</p> </td> 
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

**例：**&#x200B;次の API 呼び出しでは、Google ドキュメントの指定したドキュメントの詳細を取得します。

**URL：**

/v1/documents/1ujkf-GDgB0TQSYPrxbCSK4Uso54tHVMqHZEVZZxB6aY

**メソッド：**

[!UICONTROL GET]

![API 呼び出しの例 ](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

取得したドキュメントの詳細は、モジュールの出力の [!UICONTROL Bundle] > [!UICONTROL Body] にあります。

![API 呼び出しの出力 ](/help/workfront-fusion/references/apps-and-modules/assets/api-output.png)

#### [!UICONTROL Make All Links in a Document Clickable]

このアクションモジュールは、ドキュメント内のすべてのリンクを検索し、クリック可能にします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Make All Links in a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>このオプションを選択して、ドキュメントテンプレートをマッピングします。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> このオプションを選択して、ドロップダウンメニューからドキュメントを選択します。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>リンクをクリック可能にするドキュメントが存在するドライブのタイプを選択します。このオプションは、前のフィールドで [!UICONTROL By Dropdown] を選択した場合に使用できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>リンクをクリック可能にするドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>リンクをクリック可能にするドキュメントが存在するフォルダーを選択し、ドキュメントを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] Shared Drive]</strong> （[!DNL Google Workspace] ユーザーのみ使用可能）</p> <p>[!UICONTROL Use Domain Admin Access] 行するかどうかを選択します。 [!UICONTROL Yes] を選択すると、ドメイン管理者として要求が発行され、要求者が管理者であるすべての共有ドライブが返されます。</p> <p>リンクをクリック可能にするドキュメントが存在する共有ドライブを選択し、ドキュメントを選択します。</p> <p>メモ：このフィールドで「[!DNL Google Docs]」オプションを選択し、[!DNL Google Workspace] ユーザーではない場合、エラー <code>[400] Invalid Value</code> が返されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>リンクを更新するドキュメントが含まれているドライブを選択し、ドキュメントを選択します。このオプションは、[!UICONTROL Choose a Drive field] で [!DNL Google Docs] を選択した場合に使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> リンクを更新するドキュメントを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
