---
title: Datadog モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Datadog を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: c8c5f2e3-5af1-4957-bb6f-6c19c35102c5
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 82%

---

# [!DNL Datadog] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Datadog] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

[!DNL Datadog] モジュールを使用するには、[!DNL Datadog] アカウントが必要です。

## Datadog API 情報

Datadog コネクタは以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>1.0.11</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Datadog] を [!DNL Workfront Fusion] に接続する {#connect-datadog-to-workfront-fusion}

### API キーとアプリケーションキーを取得する {#retrieve-your-api-key-and-application-key}

[!DNL Datadog] アカウントを [!DNL Workfront Fusion] に接続するには、[!DNL Datadog] アカウントから API キーとアプリケーションキーを取得する必要があります。

1. [!DNL Datadog] アカウントにログインします。
1. 左側のナビゲーションパネルで「**[!UICONTROL Integrations]**」をクリックし、「**[!UICONTROL APIs]**」をクリックします。
1. メイン画面で「**[!UICONTROL API Keys]**」をクリックします。
1. 紫色のバーにポインタを合わせると、API キーが表示されます。
1. API キーを安全な場所にコピーします。
1. メイン画面で「**[!UICONTROL Application Keys]**」をクリックします。
1. 紫色のバーにポインタを合わせると、アプリケーションキーが表示されます。
1. アプリケーションキーを安全な場所にコピーします。

### [!DNL Workfront Fusion] で [!DNL Datadog] への接続を作成する

[!DNL Datadog] アカウントへの接続を、[!UICONTROL Datadog] モジュール内から直接作成できます。

1. 任意の [!UICONTROL Datadog] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. モジュールのフィールドに次のように入力します。

<table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection Type]</td> 
      <td> <p> [!UICONTROL [!DNL Datadog] Application] オプションを選択して、API に完全にアクセス [!DNL Datadog] ます。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection Name]</td> 
      <td> <p> 接続に名前を入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Domain] </td> 
      <td> <p>接続先のドメイン（米国または EU）を選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td> <p> [!DNL Datadog] API キーを入力します。 </p> <p>API キーの取得手順については、この記事の<a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">API キーとアプリケーションキーを取得</a>を参照してください。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Application Key]</td> 
      <td> <p> [!DNL Datadog] アプリケーションキーを入力します。 </p> <p>アプリケーションキーの取得手順については、この記事の<a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">API キーとアプリケーションキーを取得</a>を参照してください。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Datadog] モジュールとそのフィールド

[!DNL Datadog] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Datadog] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

* [[!UICONTROL Post Timeseries Points]](#post-timeseries-points)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Post Timeseries Points]

モジュールを使用すると、[!DNL Datadog] のダッシュボードにグラフ化可能な時系列データを投稿できます。

圧縮ペイロードの上限は 3.2 MB（3200000）で、圧縮解除ペイロードの場合は 62 MB（62914560）です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Datadog] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">[!DNL Datadog] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Series]</td> 
   <td> <p>送信する時系列を [!DNL Datadog] に追加します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Metric]</strong> </p> <p>時系列の名前を入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Type]</strong> </p> <p>指標のタイプを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Interval]</strong> </p> <p> 指標のタイプがレートまたは数の場合は、対応する間隔を定義します。</p> </li> 
     <li> <p><strong>[!UICONTROL Points]</strong> </p> <p>指標に関連するポイントを追加します。</p> <p>これは、ポイントの JSON 配列です。それぞれのポイントの形式は以下のとおりです。 <code>[[POSIX_timestamp, numeric_value], ...] </code></p> <p>メモ：  <p>タイムスタンプは秒単位で指定する必要があります。</p> <p>タイムスタンプは最新である必要があります。「最新」とは、10 分より後または 1 時間より前と定義されています。</p> <p> 数値の形式は、浮動小数値にする必要があります。</p> </p> <p>このフィールドには少なくとも 1 つの項目を含める必要があります。</p> </li> 
     <li> <p><strong>[!UICONTROL Host]</strong> </p> <p>指標を作成したホストの名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

このアクションモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Datadog] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">[!DNL Datadog] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td><code>https://api.datadoghq.com/api/</code> への相対パスを入力します。例：<code> /v1/org</code></td> 
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
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

**例：** 次の API 呼び出しは、[!DNL Datadog] アカウントのすべてのダッシュボードを返します。

URL：`/v1/dashboard`

メソッド：`GET`

![](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-example.png)

結果は、バンドル／本文／ダッシュボードにあるモジュールの出力に表示されます。

この例では、3 つのダッシュボードが返されました。

![](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-response-example.png)
