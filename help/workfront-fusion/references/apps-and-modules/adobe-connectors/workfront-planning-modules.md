---
title: Adobe Workfront Planning モジュール
description: ' [!DNL Adobe Workfront Planning] modules を使用すると、 [!DNL Adobe Workfront Fusion] 2}Workfront Planning アカウント内のイベントに基づくシナリオの開始、契約書およびその他のレコードの作成、読み取り、更新、設定した条件を使用したレコードの検索、およびドキュメントのアップロードを行うことができます。 [!DNL Adobe] '
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 68%

---

# [!DNL Adobe Workfront Planning] モジュール

[!DNL Adobe Workfront Planning] モジュールを使用すると、Workfront Planning でイベントが発生した場合にシナリオをトリガー設定できます。 レコードを作成、読み取り、更新、削除したり、[!DNL Adobe Workfront Planning] アカウントへのカスタム API の呼び出しを実行したりできます。

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

[!DNL Workfront Planning] アカウントへの接続を、[!DNL Workfront Fusion] モジュール内から直接作成できます。

1. 任意の [!DNL Adobe Workfront Planning] モジュールで、「接続」ボックスの横にある「**[!UICONTROL Add]**」をクリックします。

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
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションにあります。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションにあります。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]<p>（オプション）</p></td>
          <td>Workfrontのインスタンスで、この接続の認証に使用する URL を入力します。 <p>デフォルト値は <code>https://oauth.my.workfront.com/integrations/oauth2</code> です。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>ホストのプレフィックスを入力します。<p>デフォルト値は <code>origin-</code> です。</p>
        </tr>
      </tbody>
    </table>
1. 「**[!UICONTROL Continue]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Workfront Planning] モジュールとそのフィールド

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
      <td> <p>選択した条件を満たすレコードのみを監視するフィルターを設定できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。AND ルールを追加すると、複数のフィルターを使用できます。</p> <p>メモ：既存の [!DNL Workfront] web フックのフィルターは編集できません。[!DNL Workfront] イベントのサブスクリプションに別のフィルターを設定するには、現在の web フックを削除し、新しい web フックを作成します。</p> <p>イベントフィルターについて詳しくは、Workfront モジュール記事の <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">[!DNL Workfront]/[!UICONTROL Watch Events] モジュールのイベント購読フィルター </a> を参照してください。</p> </td> 
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
      <td>削除するフィールドの ID を入力またはマッピングします。</td> 
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
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] 認証ヘッダーを自動的に追加します。</p>
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
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

<!--
### Searches

#### Search records

This action module retrieves a list of records based on criteria you specify.

-->

### 未分類


#### レコードを作成

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
      <td>これらのフィールドは、選択したレコードタイプに基づきます。</td> 
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

<!--

### Get all records

This action module retrieves all records from an [!DNL Adobe Workfront Planning] account.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>For instructions on creating a connection to [!DNL Adobe Workfront Planning], see <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Create a connection to [!DNL Adobe Workfront Planning]</a> in this article.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> 
      </tr>
  </tbody>
</table>

-->

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
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
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
      <td>これらのフィールドは、選択したレコードタイプに基づきます。</td> 
      </tr>
     <tr>
  </tbody>
</table>
