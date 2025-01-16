---
description: ' [!DNL Adobe Workfront Fusion]  シナリオ内では、Anaplan を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 81c9b141-4e40-430f-99f1-c44b7a833bcd
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1619'
ht-degree: 85%

---

# [!DNL Anaplan] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Anaplan] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!DNL Anaplan] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!UICONTROL Anaplan] アカウントが必要です。
* ワークスペース、モデル、その他の [!DNL Anaplan] オブジェクトを操作する前に、[!UICONTROL Anaplan] アカウントで設定 [!DNL Workfront Fusion] る必要があります。

## Anaplan API 情報

Anaplan コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://api.anaplan.com/2/0/
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.11.5/td&gt; 
 </tbody> 
</table>

## [!DNL Anaplan] を [!DNL Workfront Fusion] に接続 {#connect-anaplan-to-workfront-fusion}

[!DNL Anaplan] モジュールへの接続を作成するには、以下を実行します。

1. [!UICONTROL Connection] ボックスの横にある [**[!UICONTROL Add]**] をクリックします。
1. 接続タイプを選択します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Basic]</td> 
      <td> <p>[!DNL Anaplan] [!UICONTROL Basic] 接続では、接続を作成するために必要なのはメールアドレスとパスワードのみです。 </p> <p>接続の名前を入力してから、メールアドレスと、[!DNL Anaplan] アカウントのパスワードを入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL CA Certificate]</td> 
      <td> <p>[!DNL Anaplan] [!UICONTROL CA Certificate] 接続には、[!UICONTROL Certificate Key]、[!UICONTROL Encoded Data]、および [!UICONTROL Encoded Signed Data] が必要です。 これらは、[!DNL Anaplan] アカウントで生成できます。手順については、[!DNL Anaplan] ドキュメントを参照してください。</p> <p>接続の名前を入力し、[!DNL Anaplan] アカウントで生成した [!UICONTROL Certificate Key]、[!UICONTROL Encoded Data]、[!UICONTROL Encoded Signed Data] を入力します。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL Continue]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Anaplan] モジュールとそのフィールド

[!DNL Anaplan] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Anaplan] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

#### [!DNL Watch records]

このトリガーモジュールは、選択されたタイプのレコードが作成または更新されると、シナリオを開始します。

>[!NOTE]
>
>このモジュールは、新しいレコードのデータを返します。変更された既存レコードのデータは返されません。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Anaplan] への接続を作成する手順については、この記事で <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">監視するオブジェクトのタイプ</td> 
   <td>監視する項目のタイプを選択します。シナリオは、このタイプのレコードが作成または更新されるときに始まります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">&lt;Object&gt; ID</td> 
   <td>監視対象のオブジェクトに関連付けられている Anaplan 内のオブジェクト（モデルやモジュールなど）の ID を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">制限</td> 
   <td> <p>各シナリオ実行サイクルでモジュールに実行させる「アクション」の対象となるレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Create a list item]](#create-a-list-item)
* [[!UICONTROL Make a custom API Call]](#make-a-custom-api-call)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Run an action]](#run-an-action)
* [[!UICONTROL Update a record]](#update-a-record)
* [[!UICONTROL Upload a file]](#upload-a-file)

#### [!UICONTROL Create a list item]

このアクションモジュールは、Anaplan のリストに新しい項目を追加します。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Connection]</td>
        <td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Workspace ID]</td>
        <td>項目の追加先となるリストが含まれている Anaplan ワークスペースの ID を選択またはマッピングします。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Model ID]</td>
        <td>項目の追加先となるリストが含まれているモデルの ID を選択またはマッピングします。</td>
    </tr>
    <tr>
        <td>[!UICONTROL List ID]</td>
        <td>項目の作成先となるリストの ID を選択またはマッピングします。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Name]</td>
        <td>新しい項目の名前を入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Code]</td>
        <td>新しい項目のコードを入力します。同じ名前の行項目を区別できるようにするユーザー生成のコードです。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Parent]</td>
        <td>新しい項目を作成する親項目の名前を入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Properties]</td>
        <td>項目を追加するリストにカスタムプロパティがある場合は、値を追加するプロパティを選択し、値を追加します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Subsets]</td>
        <td>項目を追加するリストにカスタムサブセットがある場合は、項目を追加するサブセットを選択し、「<b>[!UICONTROL Yes]</b>」を選択して新しい項目をそのサブセットに追加します。</td>
    </tr>
</table>

#### [!UICONTROL Make a custom API Call]

このモジュールを使用すると、[!DNL Anaplan] API へのカスタム API 呼び出しを実行できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>相対パスを入力します <code>https://api.anaplan.com/2/0/</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a>での HTTP リクエストメソッドを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>リクエストクエリ文字列を入力します。</p> </td> 
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

#### [!UICONTROL Delete a record]

このアクションモジュールは既存のレコードを削除します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>削除するオブジェクトを含む Anaplan ワークスペースの ID を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model ID]</td> 
   <td>削除するオブジェクトを含む Anaplan ワークスペースの ID を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">削除</td> 
   <td> <p>削除するオブジェクトのタイプを選択します。</p> 
    <ul> 
     <li> <p><b>アクション</b> </p> <p>削除するアクションを選択またはマッピングします。</p> </li> 
     <li> <p><b>リスト項目</b> </p> <p>アイテムを削除するリストを選択し、削除するアイテムの ID またはコードを入力またはマッピングします。</p>  </li> 
     <li> <p><b>[!UICONTROL File]</b> </p> <p>削除するファイルを選択またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

このアクションモジュールは 1 つのレコードを読み取ります。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>読み取るレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p><b>モデル</b> </p> <p>読み取りたいモデルの ID を選択またはマッピングします。</p> </li> 
     <li> <p><b>モデルリスト</b> </p> <p>読み取りたいリストを含むワークスペースとモデルの ID を選択またはマッピングしてから、リストを選択します。[!UICONTROL Data type] フィールドで、データとメタデータのどちらを読み取るかを選択します。</p> </li> 
     <li> <p><b>モデルのバージョン</b> </p> <p>読み取りたいモデルの ID を選択またはマッピングします。</p> </li> 
     <li> <p><b>ユーザー</b> </p> <p>使用されているアカウントの所有者に関するデータを返すか、別のユーザーに関するデータを返すかを選択します。別のユーザーを選択する場合は、ユーザーの名前を選択します。</p> </li> 
     <li> <p><b>ワークスペース</b> </p> <p>読み取りたい Workspace の ID を選択またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Run an action]

このアクションモジュールは、アクションを読み込み、書き出し、削除、または処理します。

<table style="table-layout:auto"> 
     <col/>
     <col/>
     <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection]</td>
        <td>[!DNL Anaplan] への接続の作成については、この記事の <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect Anaplan to Workfront Fusion]</a> を参照してください。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Workspace ID]</td>
        <td>アクションを実行する [!DNL Anaplan] ワークスペースの ID を選択またはマッピングします。</td>
      </tr>
      <tr >
        <td role="rowheader">[!UICONTROL Model ID]</td>
        <td>アクションを実行するモデルの ID を選択またはマッピングします。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Action type]</td>
        <td>
          <p>実行するアクションを選択します</p>
            <ul>
              <li>
                <p><b>[!UICONTROL Delete]</b>
                </p>
                <p>削除するアクションの ID を入力またはマッピングします。</p>
              </li>
              <li>
                <p><b>[!UICONTROL Export]</b>
                </p>
                <p>使用する書き出し定義の ID を入力またはマッピングします。次のファイル形式に書き出すことができます。</p>
                  <ul>
                    <li>
                      <p>XLS</p>
                    </li>
                    <li>
                      <p>XLSX</p>
                    </li>
                    <li>
                      <p>CSV</p>
                    </li>
                  </ul>
                </li>
                <li>
                  <p><b>[!UICONTROL Import] </b>
                  </p>
                  <p style="font-weight: normal;">使用する読み込み定義の ID を入力またはマッピングします。</p>
                </li>
                <li>
                 <p><b>[!UICONTROL Process]</b>
                 </p>
                  <p>使用するプロセスの ID を入力またはマッピングします。 </p>
                </li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>


#### [!UICONTROL Update a record]

このアクションモジュールは [!UICONTROL Anaplan] で 1 つのレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>更新するレコードの種類を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL List item]</b> </p> <p>フィールドについては、この記事の<a href="#create-a-list-item" class="MCXref xref">リスト項目を作成</a>を参照してください。</p> </li> 
     <li> <p><b>[!UICONTROL Module cell data]</b> </p> <p>セルデータを更新すると、そのデータを使用するすべての下流の計算も更新されます。</p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Model ID]</b> </p> <p>更新するセルを含むモデルを選択またはマッピングします。</p> </li> 
       <li> <p><b>[!UICONTROL Module ID]</b> </p> <p>更新するセルを含むモジュールを選択またはマッピングします</p> </li> 
       <li> <p><b>[!UICONTROL Line item name]</b> </p> <p>更新するセルの行項目を選択またはマッピングします</p> </li> 
       <li> <p style="font-weight: bold;">[!UICONTROL Dimension ID]</p> <p>行項目上のディメンションを選択またはマッピングします。</p> 
       <p><b>メモ：</b> 
       <ul>
       <li> ディメンションキー（値）は、<code>dimensionName</code>（次）または <code>dimensionId</code>（ID）のいずれかである必要があります。</li>
       <li>項目キー（値）は、<code>itemName</code>（テキスト）、<code>itemCode</code>（テキスト）、または <code>itemId</code>（ID）である必要があります。</li>
       <li>ディメンションキーと項目キーは同じタイプ（テキストまたは ID）である必要があります。
       </ul>
        </p> 
        <p>ディメンションの詳細については、[!DNL Anaplan Anapedia] でディメンションを検索してください。</p> </li> 
       <li> <p><b>[!UICONTROL Value]</b> </p> <p>セルの新しい値を入力またはマッピングします。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Model current fiscal year]</b> </p> <p>会計年度を更新するモデルのワークスペース ID とモデル ID を入力し、次にモデルの新年を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

このアクションモジュールは、Anaplan にファイルをアップロードします。ファイルは、既に Anaplan にアップロードされている必要があります。このモジュールを使用して、Analyplan 内の追加の場所にアップロードできます。
<table style="table-layout:auto">
<col>
<col>
<tbody>
<tr>
<td role="rowheader">[!UICONTROL Connection]</td>
<td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Workspace ID]</td>
<td>ファイルをアップロードする [!DNL Anaplan] ワークスペースの ID を、選択またはマッピングします。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Model ID]</td>
<td>ファイルをアップロードするモデルの ID を、選択またはマッピングします。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL File ID]</td>
<td>アップロードするファイルの ID を選択またはマッピングします。</td>
</tr>
</tbody>
</table>
</div>

### 検索

#### [!UICONTROL Get record]

この検索モジュールは、選択したタイプのアクセス可能なすべてのレコードを返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Anaplan] への接続を作成する手順については、この記事にある<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Anaplan] の接続を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record types]</td> 
   <td> <p>取得するレコードのタイプを選択します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Workspaces]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Models]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Line items]</b> </p> <p>取得する [!DNL line] 項目を含むモデルの ID を、選択またはマッピングします。</p> </li> 
       <li> <p><b>[!UICONTROL Model lists]</b> </p> <p>取得するモデルリストを含むワークスペース ID とモデル ID を、選択またはマッピングします。</p> </li> 
       <li> <p><b>[!UICONTROL Model calendar]</b> </p> <p>取得するモデルカレンダーが含まれるワークスペースの ID を、選択またはマッピングします。</p> </li> 
       <li> <p><b>モデルのバージョン</b> </p> </li> 
       <li> <p>取得するモデルバージョンを含むモデルの ID [!UICONTROL ] を選択またはマッピングします。</p> </li> 
       <li> <p><b>[!UICONTROL Users]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Views]</b> </p> <p>モジュールまたはモデルのどちらで表示するかを選択し、取得する表示を含むモジュールまたはモデルの ID を、選択またはマッピングします。</p> </li> 
      </ul> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Return workspace size]</td> 
   <td>このオプションを有効にすると、ワークスペースの現在のサイズの見積もりを返します。この見積もりは、ワークスペースに含まれるすべてのモジュールのサイズに基づいて行われます。</td> 
  </tr> 
 </tbody> 
</table>
