---
title: Microsoft Dynamics 365 モジュール
description: Adobe Workfront Fusionでは、Microsoft Dynamics 365を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
TQID: https://experienceleague.adobe.com/hugbkrxjvBcwIiPQMfM9VIcRby-zpFK6U5hRmrF38Lc
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: b5520579-b31f-4df7-9281-f0d9f91e2edcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1884
ht-degree: 81%

---

# [!DNL Microsoft Dynamics 365 modules]

Adobe Workfront Fusion のシナリオでは、[!DNL Microsoft Dynamics 365] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365] コネクタでは [!DNL Dynamics Finance and Operations] をサポートしていません。
>
>[!DNL Microsoft Dynamics 365 Finance and Operations] コネクタについて詳しくは、[[!DNL Microsoft Dynamics 365 Finance and Operations]  モジュール ](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/dynamics-finance-operations-modules.md)を参照してください。

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

## 前提条件

[!DNL Microsoft Dynamics] 365 を使用するには、[!DNL Microsoft Dynamics 365] アカウントが必要です。

## Workfront Fusion への Microsoft Dynamics 365 の接続

[!DNL Microsoft Dynamics 365] アカウントへの接続を、[!DNL Microsoft Dynamics 365] モジュール内から直接作成できます。

>[!NOTE]
>
>一部のMicrosoft アプリでは、同じ接続を使用し、個々のユーザー権限に関連付けられています。 したがって、接続を作成する際に、権限の同意画面には、現在のアプリケーションに必要な新しい権限に加えて、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーがExcel コネクタを介して付与された「テーブルの読み取り」権限を持ち、Outlook コネクタで電子メールを読み取るための接続を作成した場合、権限の同意画面には、既に付与された「テーブルの読み取り」権限と新たに必要な「電子メールの書き込み」権限の両方が表示されます。

1. 任意の [!DNL Microsoft Dynamics 365] モジュールで、「[!UICONTROL 接続]」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。


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
          <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>（オプション）</p></td>
          <td>[!DNL Microsoft Dynamics] [!UICONTROL Client ID] を入力します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>（オプション）</p></td>
          <td>[!DNL Microsoft Dynamics] [!UICONTROL Client Secret] を入力します。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]</td>
          <td>Workfrontのインスタンスがこの接続の認証に使用するURLを入力します。 <p>デフォルト値は <code>https://oauth.my.workfront.com/integrations/oauth2</code> です。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Resource]</td>
          <td><code>>https://</code>なしで[!DNL Dynamics 365] アカウントのアドレスを入力してください。</p>
        </tr>
      </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

>[!NOTE]
>
>[!DNL Microsoft Azure] ポータルにWorkfront Fusionを登録する場合は、次のリダイレクト URIを使用します。
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## [!DNL Microsoft Dynamics 365] モジュールとそのフィールド

[!DNL Microsoft Dynamics 365] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Microsoft Dynamics 365]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

* [[!UICONTROL レコードの監視（リアルタイム）]](#watch-records-real-time)
* [[!UICONTROL レコードの監視（定期）]](#watch-records-scheduled)

#### [!UICONTROL レコードの監視（リアルタイム）]

このインスタントトリガーモジュールでは、指定したレコード（オブジェクト）が [!DNL Dynamics 365] で作成または更新されたときにシナリオを実行します。

このモジュールには web フックが必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>このモジュールで使用する web フックを選択します。 </p> <p>新規の web フックを追加するには、次の手順に従います。</p> 
    <ol> 
     <li value="1"> <p>「Web フック」フィールドの右にある「<strong>[!UICONTROL Add]</strong>」をクリックします。</p> </li> 
     <li value="2"> <p>「<strong>[!UICONTROL Webhook name]</strong>」フィールドに、web フックのわかりやすい名前を入力します。</p> </li> 
     <li value="3"> <p>「<strong>[!UICONTROL Connection]</strong>」フィールドで、使用する接続を選択します。</p> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </li> 
     <li value="4"> <p>「<strong>[!UICONTROL Save]</strong>」をクリックして web フックを保存し、モジュールに戻ります。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの監視（定期）]

このスケジュールされたトリガーモジュールは、指定したオブジェクト内のレコードがこのシナリオの最後のスケジュールされた実行後に作成または更新されたときにシナリオを実行します。

モジュールの出力は、見つかったレコードが新規または更新されたかどうかを示します。 レコードが時間内に追加および更新された場合は、新しいレコードとして返されます。

この処理は、指定した間隔で定期的に実行されます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> "
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include]</td> 
   <td>モジュールで<strong>[!UICONTROL New Records Only]</strong>、<strong>[!UICONTROL Updated Records Only]</strong>または<strong>[!UICONTROL New and Updated Records]</strong>を監視するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>このシナリオで監視する [!UICONTROL Microsoft Dynamics 365] レコードタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。 選択したエンティティタイプに基づいてフィールドを使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL レコードの作成]](#create-record)
* [[!UICONTROL API 呼び出しの実行]](#make-an-api-call)
* [[!UICONTROL レコードを削除]](#delete-record)
* [[!UICONTROL レコードの読み取り]](#read-records)
* [[!UICONTROL レコードの更新]](#update-record)


#### [!UICONTROL レコードの作成]

このアクションモジュールでは、アポイントメントやタスクなどのエンティティを作成します。

作成するエンティティに関する情報を指定します。

このモジュールは、新規エンティティの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>このモジュールで作成するエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL マップするフィールドを選択]</td> 
   <td>レコードの作成時に値を含めるフィールドを選択します。 使用可能なフィールドは、エンティティタイプによって異なります。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td> 選択したフィールドです。 特定のプロパティに対してレコードに含める値を入力します。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードを削除]

このアクションモジュールは、エンティティを削除します。

エンティティの ID を指定します。

このモジュールは、エンティティの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>このモジュールで削除するエンティティのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>モジュールが削除するレコードの一意の [!DNL Microsoft Dynamics 365] ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL API 呼び出しの実行]

このアクションモジュールは、[!DNL Microsoft Dynamics 365] API に対して認証済みのカスタム呼び出しを実行します。 これにより、他の [!DNL Microsoft Dynamics 365] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールは、ステータスコード、ヘッダーおよび本文に関する情報を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

詳しくは、[!DNL Dynamics 365 Customer Engagement Web API] の使用に関する [!DNL Microsoft] のドキュメントを参照してください。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p><code>&lt;Instance URL>/api/data/v9.1/</code> からの相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> <p>詳しくは、</p> </td> 
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

#### [!UICONTROL レコードの読み取り]

このアクションモジュールは、[!DNL Microsoft Dynamics 365] の 1 つのエンティティからデータを読み取ります。

エンティティの ID を指定します。

このモジュールは、エンティティの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>このモジュールで読み取るエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>このモジュールで読み取るレコードの一意の [!DNL Microsoft Dynamics 365] ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの更新]

このアクションモジュールは、エンティティを更新します。

エンティティの ID を指定します。

このモジュールは、更新したレコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>モジュールで更新するエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL マップするフィールドを選択]</td> 
   <td>レコードの作成時に値を含めるフィールドを選択します。 使用可能なフィールドは、エンティティタイプによって異なります。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td>選択したフィールドです。 特定のプロパティに対してレコードに含める値を入力します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>モジュールで更新するレコードの一意の [!DNL Microsoft Dynamics] 365 ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### 検索

#### [!UICONTROL レコードを検索]

この検索モジュールは、指定した検索クエリに一致する [!DNL Microsoft Dynamics 365] 内のオブジェクトのレコードを検索します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を Workfront Fusion に接続</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>モジュールで更新するエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filters]</td> 
   <td> <p>この検索に使用するフィルターを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Standard Filters]</strong> </p> <p>フィールドと演算子を選択し、検索する値を入力またはマッピングして、フィルターを設定します。 AND または OR ルールを使用してフィルターを作成できます。</p> </li> 
     <li> <p><strong>[!UICONTROL Query Functions]</strong> </p> <p>検索に使用する [!DNL Dynamics 365] web API クエリ関数を入力します。 </p> <p>クエリ関数について詳しくは、[!DNL Microsoft] ドキュメントの <a href="https://docs.microsoft.com/en-us/dynamics365/customer-engagement/web-api/queryfunctions?view=dynamics-ce-odata-9">web API クエリ関数リファレンス</a>を参照してください。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>返される項目の順序を指定します。 複数の並べ替えを追加できます。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>結果の並べ替えに使用するフィールドを指定します。</p> </li> 
     <li> <p><strong>[!UICONTROL Direction]</strong> </p> <p>並べ替えの方向（昇順または降順）を指定します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>
