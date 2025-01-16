---
title: Microsoft Dynamics 365 モジュール
description: ' [!DNL Adobe Workfront Fusion] シナリオでは、Microsoft Dynamics 365 を使用するワークフローを自動化したり、このモジュールを複数のサードパーティアプリケーションおよびサービスに接続したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1549'
ht-degree: 78%

---

# [!DNL Microsoft Dynamics 365 modules]

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Microsoft Dynamics 365] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365] コネクタでは [!DNL Dynamics Finance and Operations] をサポートしていません。

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

[!DNL Microsoft Dynamics] 365 を使用するには、[!DNL Microsoft Dynamics 365] アカウントが必要です。

## Workfront Fusion への Microsoft Dynamics 365 の接続

[!DNL Microsoft Dynamics 365] アカウントへの接続を、[!DNL Microsoft Dynamics 365] モジュール内から直接作成できます。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

1. 任意の [!DNL Microsoft Dynamics 365] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続に名前を入力します。
1. 「**[!UICONTROL Resource]**」フィールドに、`https://` を付けずに [!DNL Dynamics 365] アカウントのアドレスを入力します。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

>[!NOTE]
>
>[!DNL Microsoft Azure] ポータルでの [!DNL Workfront Fusion] の登録時に、次のリダイレクト URI を使用します。
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## [!DNL Microsoft Dynamics 365] モジュールとそのフィールド

[!DNL Microsoft Dynamics 365] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Microsoft Dynamics 365] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Watch Records (Scheduled)]](#watch-records-scheduled)
* [[!UICONTROL Watch Records (Real Time)]](#watch-records-real-time)
* [[!UICONTROL Create Record]](#create-record)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Delete Record]](#delete-record)
* [[!UICONTROL Read Records]](#read-records)
* [[!UICONTROL Update Record]](#update-record)
* [[!UICONTROL Search Records]](#search-records)

### [!UICONTROL Watch Records (Scheduled)]

この定期的なトリガーモジュールでは、[!DNL Dynamics 365] でのスケジュールされた最後の実行後に、指定したオブジェクト内のレコードが作成または更新されたときにシナリオを実行します。

このモジュールの出力は、検出されたレコードが新規か更新かを示します（期間内に追加された場合も更新された場合も、新規としてマークされます）。この情報は、シナリオ内の後続のモジュールにマッピングできます。

この処理は、指定した間隔で定期的に実行されます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include]</td> 
   <td>モジュールで <strong>[!UICONTROL Only new records]</strong>、<strong>[!UICONTROL Updated records only]</strong>、<strong>[!UICONTROL New records and all changes]</strong> のいずれを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>シナリオで監視する [!UICONTROL Microsoft Dynamics 365] レコードタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Watch Records (Real Time)]

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
     <li value="1"> <p>「Webhook」フィールドの右側にある「<strong>[!UICONTROL Add]</strong>」をクリックします</p> </li> 
     <li value="2"> <p>「<strong>[!UICONTROL Webhook]</strong> name」フィールドに、Webhook のわかりやすい名前を入力します。</p> </li> 
     <li value="3"> <p><strong>[!UICONTROL Connection]</strong> フィールドで、選択した接続を使用するために選択します</p> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </li> 
     <li value="4"> <p>「<strong>[!UICONTROL Save]</strong>」をクリックして Webhook を保存し、モジュールに戻ります。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Create Record]

このアクションモジュールでは、アポイントメントやタスクなどのエンティティを作成します。

作成するエンティティに関する情報を指定します。

このモジュールは、新規エンティティの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>このモジュールで作成するエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>レコードの作成時に値を含めるフィールドを選択します。 使用可能なフィールドは、エンティティタイプによって異なります。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td> これらは、選択したフィールドです。 特定のプロパティに対してレコードに含める値を入力します。 </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Make an API Call]

このアクションモジュールでは、[!DNL Microsoft Dynamics 365] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Microsoft Dynamics 365] モジュールでは達成できないデータフローの自動化を作成できます。

このモジュールは、ステータスコード、ヘッダーおよび本文に関する情報を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

詳しくは、[!DNL Dynamics 365 Customer Engagement Web API] の使用に関する [!DNL Microsoft] のドキュメントを参照してください。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p><code>&lt;Instance URL>/api/data/v9.1/</code> への相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion]</a> での HTTP リクエストメソッドを参照してください。</p> <p>詳しくは、</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] によって、認証ヘッダーが追加されます。</p> </td> 
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

### [!UICONTROL Delete Record]

このアクションモジュールは、エンティティを削除します。

エンティティの ID を指定します。

このモジュールは、エンティティの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>このモジュールで削除するエンティティのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>モジュールで削除するレコードの一意の [!DNL Microsoft Dynamics 365] ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Read Records]

このアクションモジュールは、[!DNL Microsoft Dynamics 365] の 1 つのエンティティからデータを読み取ります。

エンティティの ID を指定します。

このモジュールは、エンティティの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
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
   <td>モジュールが読み取るレコードの一意の [!DNL Microsoft Dynamics 365] ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update Record]

このアクションモジュールは、エンティティを更新します。

エンティティの ID を指定します。

このモジュールは、更新したレコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>モジュールで更新するエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>レコードの作成時に値を含めるフィールドを選択します。 使用可能なフィールドは、エンティティタイプによって異なります。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td>これらは、選択したフィールドです。 特定のプロパティに対してレコードに含める値を入力します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>モジュールで更新するレコードの一意の [!DNL Microsoft Dynamics] 365 ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Search Records]

この検索モジュールは、指定された検索クエリに一致するレコードを [!DNL Microsoft Dynamics 365] 内のオブジェクトで検索します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>[!DNL Microsoft Dynamics 365] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">[!DNL Microsoft Dynamics 365] を [!DNL Workfront Fusion]</a> に接続を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>モジュールで更新するエンティティのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filters]</td> 
   <td> <p>この検索に使用するフィルターを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Standard Filters]</strong> </p> <p>フィールドと演算子を選択し、検索する値を入力またはマッピングして、フィルターを設定します。AND または OR ルールを使用してフィルターを作成できます。</p> </li> 
     <li> <p><strong>[!UICONTROL Query Functions]</strong> </p> <p>検索に使用する [!DNL Dynamics 365] web API クエリ関数を入力します。 </p> <p>クエリ関数について詳しくは、[!DNL Microsoft] ドキュメントの <a href="https://docs.microsoft.com/en-us/dynamics365/customer-engagement/web-api/queryfunctions?view=dynamics-ce-odata-9">web API クエリ関数リファレンス</a>を参照してください。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>返される項目の順序を指定します。複数の並べ替えを追加できます。</p> 
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
