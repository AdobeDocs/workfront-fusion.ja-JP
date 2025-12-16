---
title: Adobe Campaign v7／v8 モジュール
description: ' [!DNL Adobe Campaign]  モジュールを使用すると、アカウント内のイベントに基づくAdobe Workfront Fusion シナリオの開始、契約書やその他のレコードの作成、読み取り、更新、設定した条件を使用したレコードの検索  [!DNL Adobe Campaign]  ドキュメントのアップロードを行うことができます。'
author: Becky
feature: Workfront Fusion
exl-id: 9fdff26c-c7c0-4eb8-a36f-4aeaf432b333
source-git-commit: aa5b5f1fe805f43b6398e26bf1773d7540ef1634
workflow-type: tm+mt
source-wordcount: '1401'
ht-degree: 82%

---

# [!DNL Adobe Campaign] モジュール

[!DNL Adobe Campaign] モジュールを使用すると、[!DNL Adobe Campaign v7/v8] アカウント内のイベントに基づくAdobe Workfront Fusion シナリオの開始、レコードの作成、読み取りまたは更新、設定した条件を使用したレコードの検索、カスタム API 呼び出しの実行が可能です。

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

## 前提条件

Fusion IP アドレスを [!DNL Adobe Campaign] に追加する必要があります。

* Campaign の許可リストに IP アドレスを追加する手順については、Adobe Campaign ドキュメントの[許可リストへの IP アドレスの追加](https://experienceleague.adobe.com/ja/docs/control-panel/using/sftp-management/ip-range-allow-listing#adding-ip-addresses-allow-list)を参照してください。
* 許可リストに追加する IP アドレスのリストについては、組織の [許可リストの Fusion の IP アドレスの設定 ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md) を参照してください。

## Adobe Campaign API の情報

Adobe Campaign コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.7.22</td> 
  </tr>
 </tbody> 
 </table>

## Adobe Workfront Fusion への [!DNL Adobe Campaign] の接続

>[!IMPORTANT]
>
>サーバー間接続を作成することを強くお勧めします。Adobe Campaign は、サーバー間接続のみを受け入れるように API をアップデートしました。Campaign バージョン 8 以降に接続する場合、サーバー間接続を作成する&#x200B;**必要**&#x200B;があります。
>
>Campaign の新しい接続要件について詳しくは、Campaign ドキュメント内の [Campaign テクニカルオペレーターの Adobe Developer Console への移行](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/ims-migration.html?lang=ja)を参照してください。

1. 任意の [!DNL Adobe Campaign] モジュールで、「[!UICONTROL 接続]」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
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
            <p>基本接続を作成するか、サーバー間接続を作成するかを選択します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>この接続の名前を入力します。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Base URL]</td>
          <td>[!DNL Adobe Campaign] インスタンスへの接続に使用するベース URL を入力します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Username]</td>
          <td>基本接続を作成する場合は、Adobe Campaign のユーザー名を入力します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Password]</td>
          <td>基本接続を作成する場合は、Adobe Campaign のパスワードを入力します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]</td>
          <td>サーバー間接続を作成する場合は、[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>サーバー間接続を作成する場合は、[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
        </tr>
     </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

## [!DNL Adobe Campaign] モジュールとそのフィールド

[!DNL Adobe Campaign] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Campaign]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<!--* [Triggers](#triggers)-->
* [アクション](#actions)
* [検索](#searches)

<!--### Triggers

#### [!UICONTROL Watch records]

This scheduled trigger module starts a scenario when a record changes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Campaign], see <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Create a connection to [!DNL Adobe Campaign]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Select whether you want to watch for new records, updated records, or both.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Select the resource that you want to watch for.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output]</td> 
   <td>Select the fields that you want to include in the module's output.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>For each custom field that you want to include in output, click <b>[!UICONTROL Add]</b> and enter the name of the custom field.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> 
  </tr> 
 </tbody> 
</table>-->


### アクション

* [[!UICONTROL レコードを作成]](#create-a-record)
* [[!UICONTROL レコードを削除]](#delete-record)
* [[!UICONTROL カスタム API 呼び出しを実行]](#make-a-custom-api-call)
* [[!UICONTROL アクションを実行]](#perform-an-action)
* [[!UICONTROL レコードの読み取り]](#read-a-record)
* [[!UICONTROL 登録または登録解除]](#subscribe-or-unsubscribe)
* [[!UICONTROL レコードを更新]](#update-record)

#### [!UICONTROL レコードを作成]

このアクションモジュールは、[!DNL Adobe Campaign] に新しいレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>作成するレコード [!DNL Adobe Campaign] タイプを選択するか、「**カスタムリソース**」を選択してリソースの詳細を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields] </td> 
   <td>値を設定するフィールドをレコードの作成時に選択して、それらのフィールドの値を入力します。フィールドは、選択したレコードタイプによって異なります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> 新しいレコードに追加するカスタムフィールドごとに、「<b>[!UICONTROL Add item]</b>」をクリックし、フィールドの名前と値を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの削除]

このアクションモジュールは、[!DNL Adobe Campaign] から 1 つのレコードを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>削除するリソースのタイプを選択するか、「**カスタムリソース**」を選択してリソースの詳細を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>削除するリソースの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カスタム API 呼び出しを実行]

このアクションモジュールは、[!DNL Adobe Campaign] API へのカスタム API リクエストをモジュール化します

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続の作成を参照してください。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action]</td>
      <td><p>API 呼び出しで実行するアクションを選択します。</p>
      <p>[!UICONTROL Execute query]</p>
      <p>[!UICONTROL Write]</p>
      <p>[!UICONTROL Get entity if more recent]</p>
      <p>[!UICONTROL Select all]</p>
      <p>[!UICONTROL Push event]</p>
    </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は、[!UICONTROL x-security] トークンヘッダーを自動的に追加します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL XML Body]</td>
   <td> <p>API 呼び出しの本文コンテンツを、セッション要素を使用せずに XML で追加します。 </td>     </tr>
  </tbody>
</table>


#### [!UICONTROL アクションを実行]

このアクションモジュールは、[!DNL Adobe Campaign] API で、選択されたアクションをオブジェクトに対して実行します。

特定のアクションとフィールドについては、[[!DNL Adobe Campaign]  API ドキュメント](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html)を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>アクションを実行するリソースのタイプを選択するか、「**カスタムリソース**」を選択してリソースの詳細を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td><p>オブジェクトに対して実行するアクションを選択します。</p>
   <ul>
   <li><p><b>[!DNL List]</b></p><p> 使用可能なフィールドについては、この記事の<a href="#search" class="MCXref xref" >[!UICONTROL Search]</a>を参照してください。 </p></li>
     <li><p><b>[!UICONTROL Get]</b></p><p> 使用可能なフィールドについては、この記事の<a href="#search" class="MCXref xref" >[!UICONTROL Search]</a>を参照してください。 </p></li> 
   <li><p><b>[!UICONTROL Create]</b></p><p> 使用可能なフィールドについては、この記事の<a href="#create-a-record" class="MCXref xref" >[!UICONTROL Create a record]</a>を参照してください。 </p></li>
   <li><p><b>[!UICONTROL Update]</b></p><p> 使用可能なフィールドについては、この記事の<a href="#update-record" class="MCXref xref" >[!UICONTROL Update a record]</a>を参照してください。 </p></li>
   <li><p><b>[!UICONTROL Delete]</b></p><p> 使用可能なフィールドについては、この記事の<a href="#delete-record" class="MCXref xref" >[!UICONTROL Delete a record]</a>を参照してください。 </p></li>
   </ul>
   </td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの読み取り]

このアクションモジュールは、[!DNL Adobe Campaign] からレコードを読み取ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>読み取るレコード [!DNL Adobe Campaign] タイプを選択するか、「**カスタムリソース**」を選択してリソースの詳細を入力します。</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>読み取るレコードの ID を入力またはマッピングします。</td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output] </td> 
   <td>モジュールの出力に含めるフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>出力に含めるカスタムフィールドごとに、「<b>[!UICONTROL Add]</b>」をクリックし、カスタムフィールドの名前を入力します。</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL 登録または登録解除]

このアクションモジュールは、情報サービスにユーザーを登録したり、情報サービスからユーザーの登録を解除したりします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a>への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe or unsubscribe]</td> 
   <td>情報サービスに登録するか、情報サービスから登録を解除するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Service name]</td> 
   <td>登録または登録解除するサービスを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Recipient email address] </td> 
   <td>情報サービスに登録または情報サービスから登録解除するユーザーのメールアドレスを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの更新]

このアクションモジュールは、[!DNL Adobe Campaign] 内の 1 つのレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>更新するレコード [!DNL Adobe Campaign] タイプを選択するか、「**カスタムリソース**」を選択してリソースの詳細を入力します。</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>更新するレコードの ID を入力またはマッピングします。</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Fields] </td> 
   <td>値を更新するフィールドを選択して、それらのフィールドの値を入力します。フィールドは、選択したレコードタイプによって異なります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> 更新するカスタム フィールドごとに、「<b>[!UICONTROL Add item]</b>」をクリックし、フィールドの名前と値を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

### 検索

#### [!UICONTROL 検索]

この検索モジュールは、指定された条件に基づいてレコードを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >[!DNL Adobe Campaign]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>返すレコード [!DNL Adobe Campaign] タイプを選択するか、「**カスタムリソース**」を選択してリソースの詳細を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td>検索で使用するフィールドと値を入力します。 フィールドは、選択したリソースによって異なります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
