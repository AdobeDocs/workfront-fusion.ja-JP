---
title: Adobe Workfront Planning モジュール
description: ' [!DNL Adobe Workfront Planning] modules を使用すると、 [!DNL Adobe] Workfront Planning アカウント内のイベントに基づくAdobe Workfront Fusion シナリオの開始、契約書やその他のレコードの作成、読み取りまたは更新、設定した条件を使用したレコードの検索、ドキュメントのアップロードを行うことができます。'
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
source-git-commit: 30ddefa8519e6f2052308482137d0fa018676902
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 66%

---

# [!DNL Adobe Workfront Planning] モジュール

[!DNL Adobe Workfront Planning] モジュールを使用すると、Workfront Planning でイベントが発生した場合にシナリオをトリガー設定できます。 レコードを作成、読み取り、更新、削除したり、[!DNL Adobe Workfront Planning] アカウントへのカスタム API の呼び出しを実行したりできます。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td>
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

s##前提条件

Workfront Planning にアクセスするには、次のものが必要です。

* 新しいWorkfront パッケージおよびライセンス。 Workfront Planning は、従来のWorkfront パッケージまたはライセンスでは使用できません。
* Workfront Planning パッケージ。
* 組織のWorkfront インスタンスは、Adobe Unified Experience にオンボーディングされる必要があります。

## Adobe Workfront Planning API に関する情報

Adobe Workfront Planning コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://{{connection.host}}/maestro/api/{{common.maestroApiVersion}}/</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Adobe Workfront Planning] への接続の作成 {#create-a-connection-to-adobe-workfront-planning}

Workfront Fusion モジュール内から [!DNL Workfront Planning] アカウントへの直接接続を作成できます。

1. 任意の [!DNL Adobe Workfront Planning] モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。

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
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Environment]</td>
          <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Type]</td>
          <td>サービスアカウントに接続するか、個人アカウントに接続するかを選択します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]</td>
          <td>Workfrontのインスタンスで、この接続の認証に使用する URL を入力します。 <p>デフォルト値は <code>https://oauth.my.workfront.com/integrations/oauth2</code> です。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>ホストのプレフィックスを入力します。<p>デフォルト値は <code>origin-</code> です。</p>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Workfront Planning] モジュールとそのフィールド

Workfront モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加の Workfront フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。


![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)
* [未分類](#uncategorized)

### トリガー

#### イベントの監視

このトリガーモジュールは、Workfront Planning でレコード、レコードタイプまたはワークスペースが作成、更新または削除されたときにシナリオを開始します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>使用する web フックを選択するか、「追加」をクリックして新しい web フックを作成します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>レコード、レコードタイプまたはワークスペースを監視するかどうかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>古い状態と新しい状態のどちらを監視するかを選択します。<ul><li><p><b>[!UICONTROL New state]</b></p><p>レコードが指定された値<b>に</b>変化したときにシナリオをトリガーします。</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>レコードが指定された値<b>から</b>変化したときにシナリオをトリガーします。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>レコードをウォッチする場合は、レコードをウォッチするWorkspaceを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>レコードをウォッチする場合は、ウォッチするレコードのタイプを選択します。</td>
    </tr>
    </tr>
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>選択した条件を満たすレコードのみを監視するフィルターを設定できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。AND ルールを追加すると、複数のフィルターを使用できます。</p> <p>メモ：既存のWorkfront Webhook ではフィルターを編集できません。 Workfront イベントのサブスクリプションに別のフィルターを設定するには、現在の Webhook を削除し、新しい Webhook を作成します。</p> <p>イベントフィルターについて詳しくは、Workfront モジュール記事の <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Workfrontのイベント購読フィルター &gt; [!UICONTROL Watch Events] モジュール </a> を参照してください。</p> </td> 
     </tr> 
    <tr>
      <td role="rowheader">[!UICONTROL Objects to watch]</td>
      <td>レコードの新規作成、更新、新規作成および更新、削除を監視するかどうかを選択します。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Exclude updates made by this connection]</p>
      </td>
      <td>このオプションを有効にすると、このモジュールが使用する接続によって変更が行われた場合にシナリオがトリガーされなくなります。これにより、このシナリオがトリガーアクションを実行した場合に、シナリオの別のインスタンスがトリガーされるのを防ぎます。</td> 
      </tr>
  </tbody>
</table>

### アクション

* [レコードタイプの削除](#delete-a-record-type)
* [カスタム AI 呼び出しの実行](#make-a-custom-api-call)

#### レコードタイプの削除

このアクションモジュールは、Workfront Planning 内の 1 つのレコードタイプを ID で削除します。

>[!WARNING]
>
>Workfront Planning でレコード・タイプを削除すると、レコード・タイプ・テーブル内のすべてのレコードも削除されます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>削除するレコードタイプの ID を入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### カスタム API 呼び出しの実行

このモジュールは、[!DNL Adobe Workfront Planning] API に対してカスタム API 呼び出しを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>相対パスを入力します <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は認証ヘッダーを自動的に追加します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>クエリ文字列に追加するキーと値のペアごとに、「<b>項目を追加</b>」をクリックして、キーと値を入力します。</p>
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


### 検索

#### レコードの検索

このアクションモジュールは、指定した条件に基づいてレコードのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>検索するレコードを含むWorkspaceを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>検索するレコードタイプを選択します。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record Fields]</p>
      </td>
      <td>検索に使用する各フィールドについて、そのフィールドを見つけ、演算子を選択して、検索する値を入力またはマッピングします。 フィールドは、選択したレコードタイプに基づいて使用可能になります。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL フィルターの 条件 &#x200B;]</p>
      </td>
      <td>フィルターの条件の選択：<ul><li><b>AND</b><p>モジュールは、選択したフィールド値の <b> すべて </b> を満たすレコードを返します。</p></li><li><b>または</b><p>モジュールは、選択したフィールド値の <b> いずれか </b> を満たすレコードを返します。</p></li></ul></td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Limit]</p>
      </td>
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
      </tr>
  </tbody>
</table>


### 未分類


#### レコードの作成

この操作を実行すると、Workfront Planning に 1 つのレコードが作成されます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>作成するレコードのタイプを入力またはマッピングします。使用可能なレコードタイプは、Workfront Planning アカウントに基づいています。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>新しいレコードに設定する値を入力します。 これらのフィールドは、選択したレコードタイプに基づきます。</td> 
      </tr>
     <tr>
  </tbody>
</table>

### レコードの削除

このアクションモジュールは、Workfront Planning で指定されたレコードを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>削除するレコードの ID を入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

### レコードを取得

このアクションモジュールは、[!DNL Adobe Workfront Planning] から、ID で指定された、1 つのレコードを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record ID]</td>
      <td>取得するレコードの ID を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

### レコードタイプ別にレコードの取得

このアクションモジュールは、指定されたタイプのすべてのレコードを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>取得するレコードを含むワークスペースを選択またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>取得するレコードのタイプを選択します。</td>
    </tr>
     <!--<tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> -->
  </tbody>
</table>

### レコードタイプの取得

このアクションモジュールは、[!DNL Adobe Workfront Planning] アカウント内のレコードタイプのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>取得するレコードタイプを含むワークスペースを選択またはマッピングします。</td>
    </tr>
  </tbody>
</table>

### レコードの更新

Workfront Planning 内の 1 つのレコードを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>更新するレコードのタイプを入力またはマッピングします。使用可能なレコードタイプは、Workfront Planning アカウントに基づいています。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>レコードに追加する新しい値を入力します。 これらのフィールドは、選択したレコードタイプに基づきます。</td> 
      </tr>
     <tr>
  </tbody>
</table>


## 読み取り可能な `record-types` の分類に JSONata を使用

次の JSONata 式は、レコードタイプの分類を示す、人間が判読できる Planning クエリの出力を作成します。 これにより、レコードタイプ名、フィールド名およびフィールドオプション名（該当する場合）が名前で人間によって読み取り、残りの構造はそのままの状態を維持します。

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

JSONata モジュールの使用について詳しくは、[JSONata モジュール &#x200B;](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md) を参照してください。

