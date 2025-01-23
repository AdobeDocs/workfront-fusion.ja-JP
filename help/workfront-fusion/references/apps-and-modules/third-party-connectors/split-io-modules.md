---
title: Split.io モジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、 [!DNL Split.io] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 7d738a96-5424-4c30-831f-82e1d4c6f9d2
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1492'
ht-degree: 86%

---

# [!DNL Split.io] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Split.io] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!DNL Split.io] モジュールを使用するには、[!DNL Split.io] アカウントが必要です。

## Split.io API 情報

Split.io コネクタは以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.split.io/internal/api</td>
   </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.34.1</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Split.io] を [!DNL Workfront Fusion] に接続 {#connect-split-io-to-workfront-fusion}

[!DNL Split.io] アカウントへの接続を、[!DNL Split.io] モジュール内から直接作成できます。

1. 任意の [!DNL Split.io] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続に名前を入力します。
1. [!DNL Split.io] API キーを入力します。

   [!DNL Split.io] API キーについて詳しくは、[!DNL Split.io] ドキュメントの[API キー](https://help.split.io/hc/en-us/articles/360019916211-API-keys)を参照してください。

1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Split.io] モジュールとそのフィールド

[!DNL split.io] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL split.io] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [検索](#searches)

### アクション

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Get Split]](#get-split)
* [[!UICONTROL Get Split Definition in Environment]](#get-split-definition-in-environment)
* [[!UICONTROL Create Split]](#create-split)
* [[!UICONTROL Delete Split]](#delete-split)
* [[!UICONTROL Create Split Definition in Environment]](#create-split-definition-in-environment)
* [[!UICONTROL Remove Split Definition from Environment]](#remove-split-definition-from-environment)
* [[!UICONTROL Partial Update Split Definition in Environment]](#partial-update-split-definition-in-environment)
* [[!UICONTROL Associate Tags]](#associate-tags)

#### [!UICONTROL Custom API Call]

このアクションモジュールでは、[!DNL split.io] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL split.io] モジュールでは不可能なデータフロー自動処理を作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://api.split.io/internal/api/v2/</code> への相対パスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが操作するレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split]

このアクションモジュールがスプリットを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>取得するスプリットを含むワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>取得するスプリットの名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split Definition in Environment]

このアクションモジュールは、指定された環境から特定のスプリット定義を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>取得するスプリット定義を含むワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>取得するスプリット定義を含む環境を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>スプリット定義を取得するスプリットの名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split]

このアクションモジュールは、トラフィックタイプを指定して、組織内に新しいスプリットを作成します。

>[!NOTE]
>
>API はどの環境でもスプリットを設定しません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>スプリットを作成するワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Traffic Type ID or Name]</td> 
   <td>分割の作成に使用するトラフィックタイプを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>作成する分割の名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Description]</td> 
   <td>作成する分割の [!UICONTROL split] の説明を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Split]

このアクションモジュールは、組織から分割を削除します。これにより、すべての環境から分割定義の設定が自動的に解除されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>分割を削除するワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>削除する分割の名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split Definition in Environment]

このアクションモジュールは、特定の環境の分割定義を設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>分割定義を作成するワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>分割定義を作成する環境を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>定義を作成する分割の名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>分割定義に追加するコメントを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Rules]</td> 
   <td> <p>定義に追加するターゲティングルールごとに「<b>[!UICONTROL Add item]</b>」をクリックし、ルールを入力またはマッピングします。</p> <p>ターゲットルールについて詳しくは、[!DNL Split.io] ドキュメントの<a href="https://docs.split.io/reference#create-split-definition-in-environment">環境で分割定義を作成</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default rule]</td> 
   <td> <p>他のルールの仕様を満たさないトラフィックに対して分割で使用するルールを入力またはマッピングします。</p> <p>ターゲットルールについて詳しくは、[!DNL Split.io] ドキュメントの<a href="https://docs.split.io/reference#create-split-definition-in-environment">環境で分割定義を作成</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default treatment]</td> 
   <td> <p>分割が強制終了した場合、または顧客がトラフィック配分に含まれていない場合に分割で使用する処理を入力またはマッピングします。</p> <p>処理について詳しくは、[!DNL Split.io] ドキュメントの<a href="https://docs.split.io/reference#create-split-definition-in-environment">環境で分割定義を作成</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Treatments]</td> 
   <td> <p>定義に追加する処理ごとに「<b>[!UICONTROL Add item]</b>」をクリックし、処理を入力またはマッピングします。</p> <p>処理について詳しくは、[!DNL Split.io] ドキュメントの<a href="https://docs.split.io/reference#create-split-definition-in-environment">環境で分割定義を作成</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove Split Definition from Environment]

このアクションモジュールは、特定の環境の分割定義の設定を解除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>分割定義を削除するワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>スプリット定義を削除する環境を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>定義を削除するスプリットの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>分割定義に追加するコメントを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Partial Update Split Definition in Environment]

このアクションモジュールは、特定の環境のスプリット定義を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>スプリット定義を更新するワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>スプリット定義を更新する環境を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>定義を更新するスプリットの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update content]</td> 
   <td> <p>更新する分割の属性ごとに「<b>[!UICONTROL Add item]</b>」をクリックし、必要な変更を入力またはマップします。</p> <p>詳しくは、[!DNL Split.io] ドキュメント内の<a href="https://docs.split.io/reference#partial-update-split-definition-in-environment">環境でスプリット定義を部分更新</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>分割定義に追加するコメントを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Associate Tags]

このアクションモジュールは、指定したオブジェクトにタグを追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>タグを追加するワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Name]</td> 
   <td>タグを追加するオブジェクト名を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type]</td> 
   <td> <p>タグを追加するオブジェクトのタイプを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> <p>追加するタグごとに「<b>[!UICONTROL Add item]</b>」をクリックし、タグを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL Get Workspaces]](#get-workspaces)
* [[!UICONTROL Get Environments]](#get-environments)
* [[!UICONTROL Get Splits]](#get-splits)
* [[!UICONTROL List Split Definitions in an Environment]](#list-split-definitions-in-an-environment)
* [[!UICONTROL Get Traffic Types]](#get-traffic-types)

#### [!UICONTROL Get Workspaces]

この検索モジュールは、組織のワークスペースを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールで取得するワークスペースの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Environments]

この検索モジュールは、環境のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>リストに表示する環境を含むワークスペースを選択またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Splits]

この検索モジュールは、分割のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>リストに表示するスプリットを含むワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>それぞれのシナリオ実行サイクル中にモジュールが取得するスプリットの最大数を、入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Split Definitions in an Environment]

この検索モジュールは、特定の環境のスプリット定義のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>リストに表示するスプリット定義を含むワークスペースを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>リストに表示するスプリット定義を含む環境を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>それぞれのシナリオ実行サイクル中にモジュールが取得するスプリット定義の最大数を、入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Traffic Types]

この検索モジュールは、トラフィックタイプのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Split.io] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">[!DNL Split.io] を [!UICONTROL Workfront Fusion] へ接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>リストに表示するトラフィックタイプを含むワークスペースを選択またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
