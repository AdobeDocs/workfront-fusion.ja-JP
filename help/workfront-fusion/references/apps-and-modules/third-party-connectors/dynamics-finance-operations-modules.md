---
title: Microsoft Dynamics 365財務および運営モジュール
description: Adobe Workfront Fusionでは、Microsoft Dynamics 365 Finance and Operationsを使用するワークフローを自動化したり、複数のサードパーティ製アプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 96f8d4f1-f97b-4da8-8d82-83cccb54ec68
TQID: https://experienceleague.adobe.com/MSvJMXg8hyI8piqHpn1OnEPEoCcP1Tn-za1veFtHeIo
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1147
ht-degree: 40%

---

# [!DNL Microsoft Dynamics 365 Finance and Operations modules]

Adobe Workfront Fusion のシナリオでは、[!DNL Microsoft Dynamics 365] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365 Finance and Operations] コネクタでは [!DNL Dynamics 365] をサポートしていません。
>
>Microsoft Dynamics 365 モジュールについては、[[!DNL Microsoft Dynamics 365 modules]](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md)を参照してください。



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



## 接続の作成

Microsoft Dynamics 365財務および運用モジュールの接続を作成するには：

1. Microsoft Dynamics 365 Finance and Operations モジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL Add]**&#x200B;をクリックします。

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
          <p>標準のDynamics Finance and Operations接続を作成するか、認証コードを使用して接続を作成するかを選択します。</p>
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
        <td>Dynamics Finance and Operations [!UICONTROL Client ID]を入力します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Dynamics Finance and Operations [!UICONTROL Client Secret]を入力します。 </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL テナント ID]</td>
        <td>Dynamics Finance and Operations テナント IDを入力します。</td>
        </tr>
        <tr>
        <td role="rowheader">リソース</td>
        <td>Dynamics Finance and Operations アカウントのURLを入力します（https://は使用しません）。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。



## Microsoft Dynamics 365財務および運営モジュールとそのフィールド

>[!IMPORTANT]
>
>Dynamics 365 F&amp;O APIを通じて使用可能なデータエンティティは、インスタンスによって異なります。 APIを通じてどのエンティティが使用できるかわからない場合は、「data」エンドポイントを使用してインスタンス内のエンティティを調べてみると便利です。 Dynamics 365 Finance and Operationsの「データ」エンドポイントは、OData サービスにアクセスするためのルート URLです。 このエンドポイントを使用すると、標準のOData プロトコルを使用して、システムによって公開されたさまざまなデータエンティティと対話できます。
>
>カスタム API呼び出しモジュールを使用して、これらのエンティティを取得できます。
>
><!--For more information -->



### エンティティ項目を作成

このアクションモジュールは、Microsoft Dynamics 365 Finance and Operationsで新しいエンティティ項目を作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Microsoft Dynamics 365 Finance and OperationsをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref">接続を作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL エンティティ ]</td>
     <td>作成するDynamics FinanceおよびOperations エンティティ タイプを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Body]</td>
     <td> <p>新しいエンティティアイテムに含めるデータを含むJSON本文を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>



### エンティティ項目を削除

このアクションモジュールは、Dynamics Finance and Operationsからエンティティ項目を削除します。 項目は、プライマリキーフィールドで識別されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Microsoft Dynamics 365 Finance and OperationsをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref">接続を作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL エンティティ ]</td>
     <td>削除するDynamics FinanceおよびOperations エンティティ タイプを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL プライマリキーフィールド ]</td>
     <td> プライマリキーフィールドで項目を識別します。 指定するプライマリキーフィールドごとに、<b>項目を追加</b>をクリックし、その項目を識別する一意のキーと値を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

### カスタム API 呼び出しの実行

このアクションモジュールは、Dynamics Finance and Operations APIをカスタム呼び出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
    <td> <p>Microsoft Dynamics 365 Finance and OperationsをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref">接続を作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Dynamics Finance and OperationsのURLに対する相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。 これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> {"Content-type":"application/json"}</code></p> <p>メモ：エラーが表示され、エラーの発生元を特定するのが困難な場合は、Workfront ドキュメントに基づいてヘッダーの変更を考慮してください。 カスタム API 呼び出しで 422 HTTP リクエストエラーが返される場合は、<code>"Content-Type":"text/plain"</code> ヘッダーを使用してみてください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query string]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> <p>ヒント：情報は、クエリパラメーターではなく、JSON 本文を使用して送信することをお勧めします。</p> </td> 
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



### エンティティ項目の読み取り

このアクションモジュールは、エンティティ項目からデータを返します。 項目は、プライマリキーフィールドで識別されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Microsoft Dynamics 365 Finance and OperationsをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref">接続を作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL エンティティ ]</td>
     <td>読み取るDynamics FinanceおよびOperations エンティティの種類を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL プライマリキーフィールド ]</td>
     <td> プライマリキーフィールドで項目を識別します。 指定するプライマリキーフィールドごとに、<b>項目を追加</b>をクリックし、その項目を識別する一意のキーと値を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

### エンティティ項目を更新

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Microsoft Dynamics 365 Finance and OperationsをWorkfront Fusionに接続する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref">接続を作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL エンティティ ]</td>
     <td>更新するDynamics FinanceおよびOperations エンティティの種類を入力するか、マッピングします。</td> 
  </tr>  
  <tr> 
    <td>[!UICONTROL プライマリキーフィールド ]</td>
     <td> プライマリキーフィールドで項目を識別します。 指定するプライマリキーフィールドごとに、<b>項目を追加</b>をクリックし、その項目を識別する一意のキーと値を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Body]</td>
     <td> <p>新しいエンティティアイテムに含めるデータを含むJSON本文を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 検索

この検索モジュールは、指定した条件に基づいて結果を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Workfront を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL エンティティ ]</td> 
   <td>検索するDynamics FinanceおよびOperations エンティティの種類を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>検索するフィールド、クエリで使用する演算子、およびそのフィールドで検索する値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Sort by]</td> 
   <td> <p>結果を並べ替えるフィールドを入力するか、マッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>


<!--

### List All

This module lists all records for a given entity.  The item is identified by its Primary key fields.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>For instructions about connecting Microsoft Dynamics 365 Finance and Operations to Workfront Fusion, see <a href="#create-a-connection" class="MCXref xref">Create a connection</a> in this article.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>
     <td>Choose the Dynamics Finance and Operations entity type that you want the module to list.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>
     <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Watch Record

This trigger module starts a scenario when a record of the given type is created or updated.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
    <td> <p>For instructions about connecting Microsoft Dynamics 365 Finance and Operations to Workfront Fusion, see <a href="#create-a-connection" class="MCXref xref">Create a connection</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to watch.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
 </tbody> 
</table>

-->
