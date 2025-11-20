---
title: Figma モジュール
description: Adobe Workfront Fusion Figma モジュールを使用すると、コメント、ファイル、ファイルバージョン、プロジェクトのリストを取得できます。 また、コメントを投稿したり、Figma API を呼び出したりすることもできます。
author: Becky
feature: Workfront Fusion
exl-id: 1220460b-1957-4dfc-b7c1-4c97b36ea061
source-git-commit: 545bc38a619c44dd39bb746d751775f63e7aa16d
workflow-type: tm+mt
source-wordcount: '2638'
ht-degree: 79%

---

# [!DNL Figma] モジュール

Adobe Workfront Fusion [!DNL Figma] モジュールを使用すると、コメント、ファイル、ファイルバージョン、プロジェクトのリストを取得できます。 また、コメントを投稿したり、[!DNL Figma] API を呼び出したりすることもできます。

シナリオの作成手順については、[&#x200B; シナリオを作成：記事インデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <td> <p>Standard</p><p>Work またはそれ以上</p> </td> 
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

[!DNL Figma] モジュールを使用するには、[!DNL Figma] アカウントが必要です。

## Figma API 情報

Figma コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.figma.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.8.25</td> 
  </tr>
 </tbody> 
 </table>

## Figma への接続の作成

>[!IMPORTANT]
>
>* Figma は、2025 年 1 月に認証要件を変更しました。 この `Figma` 接続タイプは新しい要件を満たしています。 `Figma (Legacy)` 接続タイプは非推奨（廃止予定）となり、近い将来に削除される予定です。
>* リダイレクト URL を使用する場合は、`https://oauth.app.workfrontfusion.com/oauth/cb/figma3` を使用します。

Figma モジュールの接続を作成するには：

1. 任意の Figma モジュールで、「接続」ボックスの横にある **[!UICONTROL 追加]** をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p> レガシ タグのない <code>Figma</code> を選択します。 </p><p>Figma は、2025 年 1 月に認証要件を変更しました。 この <code>Figma</code> 接続タイプは新しい要件を満たしています。 <code>Figma (Legacy)</code> 接続タイプは非推奨（廃止予定）となり、今後削除される予定です。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Figma] [!UICONTROL クライアント ID] を入力します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Figma [!UICONTROL Client Secret] を入力します。</td>
        </tr>
        <tr>
        <td role="rowheader">カスタム スコープ</td>
        <td>この接続に必要なカスタム スコープを入力します。</td>
        </tr>
        <tr>
        <td role="rowheader">カスタム接続確認 URL</td>
        <td>接続が正常に作成されたことを検証するデフォルトのエンドポイントは次のとおりです。<code>https://api.figma.com/v1/me</code> この URL がカスタム範囲でサポートされていない場合は、カスタム検証 URL を指定します。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。



## [!DNL Figma] モジュールとそのフィールド

[!DNL Figma] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Figma]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間の情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [コメント](#comments)

* [プロジェクトとファイル](#projects-and-files)

* [コンポーネントとスタイル](#components-and-styles)

* [その他](#other)


### コメント

* [コメントの削除](#delete-a-comment)

* [コメントをリスト](#list-comments)

* [コメントを投稿](#post-a-comment)


#### [!UICONTROL コメントを削除]

このアクションモジュールは、ファイルから 1 つのコメントを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col />
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>コメントを追加もしくは削除するファイルのファイル ID を入力またはマッピングします。 </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Comment ID]</td>
      <td>削除するコメントのテキストを入力します。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL コメントを一覧表示]

この検索モジュールは、[!DNL Figma] の単一ファイルについたすべてのコメントを一覧表示します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>コメントを取得するファイルのファイル ID を入力またはマッピングします。 </p>
        <ul>
          <li>
            <p>ID が不明な場合は、<b>[!UICONTROL Find Files]</b> をクリックし、ファイルが関連付けられているプロジェクトの ID を入力またはマッピングし、ファイルを選択します。</p>
          </li>
          <li>
            <p>プロジェクトの ID が不明な場合は、<b>[!UICONTROL Find Projects]</b> をクリックし、ファイルが関連付けられているプロジェクトを所有するチームの ID を入力またはマッピングして、プロジェクトを選択してから、ファイルを選択します。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned comments]</td>
      <td>各シナリオの実行サイクル中にモジュールが返すコメントの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL コメントを投稿]

このアクションモジュールは、Figma ファイルにコメントを投稿します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td  role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>コメントを投稿するファイルのファイル ID を入力またはマッピングします。 </p>
        <ul>
          <li>
            <p>ファイルの ID が不明な場合は、<b>[!UICONTROL Find Files]</b> をクリックし、ファイルが関連付けられているプロジェクトの ID を入力またはマッピングして、ファイルを選択します。</p>
          </li>
          <li>
            <p>ファイルの ID を探していて、プロジェクトの ID が不明な場合は、<b>[!UICONTROL Find Projects]</b> をクリックし、ファイルが関連付けられているプロジェクトを所有するチームの ID を入力またはマッピングします。プロジェクトを選択したあと、ファイルを選択します。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Comment]</td>
      <td>コメントのテキストを入力します。</td>
    </tr>
  </tbody>
</table>


### プロジェクトとファイル

* [ファイルまたは画像の取得](#get-a-file-or-image)

* [ファイルのバージョン履歴のリスト](#list-file-version-history)

* [プロジェクトファイルのリスト](#list-project-files)

* [プロジェクトのリスト](#list-projects)


#### [!UICONTROL ファイルまたは画像の取得]

このアクションモジュールは、Figma ライブラリから 1 つのファイルまたは画像を取得します

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>
        <p>取得するオブジェクトのタイプを選択します。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL File]</b>
            </p>
            <p>このモジュールは、[!UICONTROL Key]で参照されるドキュメントを JSON オブジェクトとして返します。ファイルキーは、任意の Figma ファイル URL から解析できます。</p>
            <p>フィールドについては、<a href="#get-a-file-or-image-file" class="MCXref xref" >[!UICONTROL Get a file or image: File]</a>を参照してください。</p>
          </li>
          <li>
            <p><b>[!UICONTROL File nodes]</b>
            </p>
            <p>ID で参照されるノードを JSON オブジェクトとして返します。ノードは、[!UICONTROL Key]で参照される [!DNL Figma] ファイルから取得されます。</p>
            <p>フィールドについては、<a href="#get-a-file-or-image-file-nodes" class="MCXref xref" >[!UICONTROL Get a file or image: File nodes]</a>を参照してください。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Image]</b>
            </p>
            <p>このモジュールは、ファイルから画像をレンダリングします。</p>
            <p>フィールドについては、<a href="#get-a-file-or-image-image" class="MCXref xref" >[!UICONTROL Get a file or image: Image]</a>を参照してください。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Image fills]</b>
            </p>
            <p>このモジュールは、ドキュメント内の画像の塗りに存在するすべての画像のダウンロードリンクを返します。画像の塗りは、ユーザーが指定した画像を [!DNL Figma] で表現する方法です。画像を [!DNL Figma] にドラッグすると、その画像を表す単一の塗りを持つ長方形が [!DNL Figma] で作成されます。ユーザーは、その長方形（および塗りのプロパティ）を変形できます。</p>
            <p>フィールドについては、<a href="#get-a-file-or-image-image-fills" class="MCXref xref" >[!UICONTROL Get a file or image: Image fills]</a>を参照してください。</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>


##### ファイルまたは画像を取得します：ファイル

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL File key]</td>
      <td>JSON を返す元となるファイルを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Version ID]</td>
      <td>モジュールが返すファイルのバージョンを入力またはマッピングします。現在のモジュールでは、このフィールドを空白のままにします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Node IDs]</td>
      <td>
        <p>ドキュメントのサブセットのみを返すには、モジュールが返すノードを入力します。このモジュールは、リストされたノード、その子、およびルートノードとリストされたノードの間のすべてのノードを返します。</p>
        <p>返すノードごとに、「<b>[!UICONTROL Add]</b>」をクリックしてノードのテキストを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Depth]</td>
      <td>
        <p>結果を返すドキュメントツリー内の深さを表す整数を入力またはマッピングします。 </p>
        <div class="example"><span class="autonumber"><span><b>例：</b></span></span>
          <ul>
            <li>
              <p>ページのみを返すには、<code>1</code> を入力します。</p>
            </li>
            <li>
              <p>ページとトップレベルのオブジェクトを返すには、<code>2</code> を入力します。</p>
            </li>
          </ul>
        </div>
        <p>すべてのノードを返す場合は、このフィールドを空白のままにします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Geometry]</td>
      <td>ベクトルデータを返すには、<code>paths</code> を入力します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Plugin data]</td>
      <td>プラグイン ID や文字列「[!UICONTROL shared]」のコンマ区切りリスト。これらのプラグインによって書き込まれたドキュメント内に存在するすべてのデータは、<code>pluginData</code> プロパティと <code>sharedPluginData</code> プロパティの結果に含まれます。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Branch data]</td>
      <td>要求されたファイルのブランチメタデータを返すには、このオプションを有効にします。ファイルがブランチの場合、返される応答にメインファイルのキーが含まれます。ファイルにブランチがある場合、そのメタデータが返される応答に含まれます。デフォルト：<code>false</code></td>
    </tr>
  </tbody>
</table>

##### ファイルまたは画像の取得：ファイルノード

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL File key]</td>
      <td>JSON を返す元となるファイルを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Node IDs]</td>
      <td>
        <p>モジュールが返し、変換するノードを入力します。</p>
        <p>返すノードごとに、「<b>[!UICONTROL Add]</b>」をクリックしてノードのテキストを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Version ID]</td>
      <td>モジュールが返すファイルのバージョンを入力またはマッピングします。現在のモジュールでは、このフィールドを空白のままにします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Depth]</td>
      <td>
        <p>結果を返すドキュメントツリー内の深さを表す整数を入力またはマッピングします。 </p>
        <div class="example"><span class="autonumber"><span><b>例：</b></span></span>
          <ul>
            <li>
              <p>ページのみを返すには、<code>1</code> を入力します。</p>
            </li>
            <li>
              <p>ページとトップレベルのオブジェクトを返すには、<code>2</code> を入力します。</p>
            </li>
          </ul>
        </div>
        <p>すべてのノードを返す場合は、このフィールドを空白のままにします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Geometry]</td>
      <td>ベクトルデータを返すには、<code>paths</code> を入力します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Plugin data]</td>
      <td>プラグイン ID のコンマ区切りリストや文字列「shared」。これらのプラグインによって書き込まれたドキュメント内に存在するすべてのデータは、pluginData プロパティと sharedPluginData プロパティの結果に含まれます。</td>
    </tr>
  </tbody>
</table>


##### ファイルまたは画像を取得：画像

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL File key]</td>
      <td>JSON を返す元となるファイルを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Node IDs]</td>
      <td>
        <p>モジュールがレンダリングするノードを入力します。</p>
        <p>レンダリングするノードごとに、「<b>[!UICONTROL Add]</b>」をクリックしてノードのテキストを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Scale]</td>
      <td>画像を拡大・縮小するには、拡大・縮小率を入力またはマッピングします。この数は 0.01～4 の範囲で指定する必要があります。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Format]</td>
      <td>
        <p>画像出力の形式を選択します。</p>
        <ul>
          <li>
            <p>JPG</p>
          </li>
          <li>
            <p>PNG</p>
          </li>
          <li>
            <p>SVG</p>
          </li>
          <li>
            <p>PDF</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SVG - Include ID]</td>
      <td>すべての SVG 要素の ID 属性を含めるには、このオプションを有効にします。デフォルト：[!UICONTROL false]。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SVG - Simplify Stroke]</td>
      <td>内部や外部のストロークを簡略化し、可能な場合に &lt;mask&gt; の代わりにストローク属性を使用するには、このオプションを有効にします。デフォルト：[!UICONTROL true]。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Use absolute bounds]</td>
      <td>ノードがトリミングされているか、ノードの周囲のスペースが空であるかに関係なく、ノードの全寸法を使用するには、このオプションを有効にします。トリミングせずにテキストノードを書き出すには、このオプションを使用します。デフォルト：[!UICONTROL false]。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Version]</td>
      <td>モジュールが返すファイルのバージョンを入力またはマッピングします。現在のモジュールでは、このフィールドを空白のままにします。</td>
    </tr>
  </tbody>
</table>

##### ファイルまたは画像の取得：画像の塗り

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL File key]</td>
      <td>JSON を返す元となるファイルを選択します。</td>
    </tr>
  </tbody>
</table>

### [!UICONTROL ファイルのバージョン履歴のリスト]

この検索モジュールは、[!UICONTROL Figma] 内の単一ファイルのバージョン履歴を返します。
<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>バージョン履歴を取得するファイルのファイル ID を入力またはマッピングします。 </p>
        <ul>
          <li>
            <p>ファイルの ID が不明な場合は、「<b>[!UICONTROL Find Files]</b>」をクリックして、ファイルが関連付けられているプロジェクトの ID を入力またはマッピングしたあと、ファイルを選択します。</p>
          </li>
          <li>
            <p>ファイルの ID を探していて、プロジェクトの ID が不明な場合は、<b>[!UICONTROL Find Projects]</b> をクリックし、ファイルが関連付けられているプロジェクトを所有するチームの ID を入力またはマッピングします。プロジェクトを選択したあと、ファイルを選択します。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned files]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL プロジェクトファイルのリスト]

この検索モジュールは、指定されたプロジェクト内のすべてのファイルのリストを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File ID]</td>
      <td>
        <p>ファイルを取得するプロジェクトのプロジェクト ID を入力またはマッピングします。 </p>
        <ul>
          <li>
            <p>プロジェクトの ID が不明な場合は、「<b>[!UICONTROL Find Projects]</b>」をクリックして、プロジェクトが関連付けられているチームの ID を入力またはマッピングしたあと、プロジェクトを選択します。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned files]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL プロジェクトのリスト]

この検索モジュールは、指定したチーム内のすべてのプロジェクトのリストを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Team ID]</td>
      <td>ファイルを取得するプロジェクトのプロジェクト ID を入力またはマッピングします。チーム ID は、Figma のチームのページの URL で確認できます。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of returned projects]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>


### コンポーネントとスタイル

#### [!UICONTROL スタイルまたはコンポーネントを取得]

このアクションモジュールは、1 つのスタイルまたはコンポーネント、またはスタイルまたはコンポーネントのセットを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td role="rowheader">オブジェクト &gt; タイプ</td>
      <td>取得するオブジェクトのタイプを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">&lt;[!UICONTROL Object&gt; key]</td>
      <td>取得するオブジェクトのキー（一意の ID）を入力します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Team ID]</td>
      <td>チームコンポーネントまたはチームコンポーネントセットを取得する場合、レコードが関連付けられているチームの ID を入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Page Size]</td>
      <td>チームコンポーネントまたはチームコンポーネントセットを取得する場合、ページごとに返す数または結果を入力するかマッピングします。 デフォルト：30。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL After]</td>
      <td>
        <p>チームコンポーネントまたはチームコンポーネントセットを取得する場合は、結果の数を入力するかマッピングして、その数を超えると結果の取得が開始されるようにします。 これを [!UICONTROL Page Size] フィールドと組み合わせて、結果をページ分割することができます。</p>
        <p>この値はオブジェクト ID に対応していません。</p>
        <p>このフィールドは、[!UICONTROL Before] フィールドと組み合わせて使用することはできません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Before]</td>
      <td>
        <p>チームコンポーネントまたはチームコンポーネントセットを取得する場合は、結果の数を入力するかマッピングしてから、結果の取得を開始します。 これを [!UICONTROL Page Size] フィールドと組み合わせて、結果をページ分割することができます。</p>
        <p>この値はオブジェクト ID に対応していません。</p>
        <p>このフィールドは、[!UICONTROL After] フィールドと組み合わせて使用できません。</p>
      </td>
    </tr>
  </tbody>
</table>


### その他

* [API 呼び出しを実行](#make-an-api-call)

* [イベントを監視する](#watch-events)


#### [!UICONTROL API 呼び出しを実行]

このアクションモジュールは、認証について考えることなく、Figma API に対して認証済みのカスタム呼び出しを実行できます。これにより、他のモジュールでは不可能なデータフローオートメーションを作成できます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>[!DNL Figma] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">Figma への接続の作成 </a> を参照してください。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p><code>https://api.figma.com/v1/</code> への相対パスを入力します。</p>
        <p>例： <code>[!DNL files/7179110/comments]</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Method]</td>
      <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は認証ヘッダーを追加します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]</td>
      <td>
        <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"name":"something-urgent"}</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

#### [!UICONTROL イベントを見る]

このトリガーモジュールでは、[!DNL Figma] のチームスペースの特定のチームに対して次のいずれかのイベントが発生した場合、シナリオが開始されます。

* ファイルの更新

* ファイルのバージョン更新

* ファイルの削除

* ライブラリの公開

* ファイルのコメント

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>
        <p>モジュールが監視する web フックを選択します。</p>
        <p>新規の web フックを追加するには、次の手順に従います。</p>
        <ol>
          <li>
            <p>[!UICONTROL Webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</p>
          </li>
          <li>
            <p>Web フックの名前を入力します。</p>
          </li>
          <li>
            <p>この web フックに使用する接続を選択します。[!DNL Figma] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p>
          </li>
          <li>
            <p>モジュールで監視するイベントタイプを選択します。</p>
          </li>
          <li>
            <p>Web フックでイベントを監視するチームの ID を入力します。</p>
          </li>
          <li>
            <p>Webhook をアクティブにするか一時停止するかを選択します。</p>
          </li>
          <li>
            <p>Webhook の説明を入力します。</p>
          </li>
          <li>
            <p>「<b>[!UICONTROL Save]</b>」をクリックして web フックを保存し、モジュールに戻ります。</p>
          </li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>
