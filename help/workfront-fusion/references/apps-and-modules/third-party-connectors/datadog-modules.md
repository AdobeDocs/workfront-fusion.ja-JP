---
title: Datadog モジュール
description: Adobe Workfront Fusion シナリオでは、Datadog を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: c8c5f2e3-5af1-4957-bb6f-6c19c35102c5
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 63%

---

# [!DNL Datadog] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Datadog] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

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

## [!DNL Datadog] を Workfront Fusion に接続 {#connect-datadog-to-workfront-fusion}

### API キーとアプリケーションキーを取得する {#retrieve-your-api-key-and-application-key}

[!DNL Datadog] アカウントをWorkfront Fusion に接続するには、[!DNL Datadog] アカウントから API キーとアプリケーションキーを取得する必要があります。

1. [!DNL Datadog] アカウントにログインします。
1. 左側のナビゲーションパネルで、「**[!UICONTROL 統合]**」をクリックして、「**[!UICONTROL API]**」をクリックします。
1. メイン画面で、「**[!UICONTROL API キー]**」をクリックします。
1. 紫色のバーにポインタを合わせると、API キーが表示されます。
1. API キーを安全な場所にコピーします。
1. メイン画面で、「**[!UICONTROL アプリケーションキー]**」をクリックします。
1. 紫色のバーにポインタを合わせると、アプリケーションキーが表示されます。
1. アプリケーションキーを安全な場所にコピーします。

### Workfront Fusion での [!DNL Datadog] への接続の作成

[!DNL Datadog] アカウントへの接続を、[!UICONTROL Datadog] モジュール内から直接作成できます。

1. 任意の [!UICONTROL Datadog] モジュールで、「[!UICONTROL 接続]」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. モジュールのフィールドに次のように入力します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection Name]</td> 
      <td> <p> 接続に名前を入力します。</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>この接続を実稼動環境と非実稼動環境のどちらで使用するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
     <tr> 
      <td role="rowheader">[!UICONTROL Domain] </td> 
      <td> <p>接続先のドメイン（米国または EU）を選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API キーの場所 ] </td> 
      <td> <p>API キーをヘッダーに含めるか、クエリ文字列に含めるかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td> <p> [!DNL Datadog] API キーを入力します。 </p> <p>API キーの取得手順については、この記事の<a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">API キーとアプリケーションキーを取得</a>を参照してください。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

## [!DNL Datadog] モジュールとそのフィールド

[!DNL Datadog] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Datadog]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

* [[!UICONTROL API 呼び出しを実行]](#make-an-api-call)
* [[!UICONTROL 時系列のポイントを投稿]](#post-timeseries-points)

#### [!UICONTROL API 呼び出しを実行]

このアクションモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Datadog] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Datadog] の接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL で専用ドメインを使用 ]</td> 
   <td>多くの受信トラフィックを想定している Datadog API エンドポイントの一部は、専用ドメインで動作しています。 API 呼び出しに専用ドメインを使用するには、このボックスをオンにします。</td> 
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

![Datadog API 呼び出しの例 ](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-example.png)

結果は、バンドル／本文／ダッシュボードにあるモジュールの出力に表示されます。

この例では、3 つのダッシュボードが返されました。

![Datadog API 応答 ](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-response-example.png)

#### [!UICONTROL 時系列のポイントを投稿]

モジュールを使用すると、[!DNL Datadog] のダッシュボードにグラフ化可能な時系列データを投稿できます。

圧縮ペイロードの上限は 3.2 MB（3200000）で、圧縮解除ペイロードの場合は 62 MB（62914560）です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Datadog] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL Datadog] の接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> 使用する指標のタイプを選択します。 
   <ul>
   <li>ゲージ</li>
   <li>レート</li>
   <li>カウント</li>
   </ul>
   </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL 間隔 ]</td> 
   <td> 指標のタイプがレートまたは数の場合は、対応する間隔を定義します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Points]</td> 
   <td><p>指標に関連するポイントを追加します。</p> <p>これは、ポイントの JSON 配列です。それぞれのポイントの形式は以下のとおりです。 <code>[[POSIX_timestamp, numeric_value], ...] </code></p> <p>メモ：  <p>タイムスタンプは秒単位で指定する必要があります。</p> <p>タイムスタンプは最新である必要があります。「最新」とは、10 分より後または 1 時間より前と定義されています。</p> <p> 数値の形式は、浮動小数値にする必要があります。</p> </p> <p>このフィールドには少なくとも 1 つの項目を含める必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Host]</td> 
   <td>指標を作成したホストの名前を入力します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> 指標に追加するタグごとに、「<b> 項目を追加 </b>」をクリックしてタグの値を入力します。</td> 
  </tr> 
 </tbody> 
</table>
