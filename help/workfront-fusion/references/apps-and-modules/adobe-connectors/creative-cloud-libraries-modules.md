---
title: Adobe Creative Cloud ライブラリモジュール
description: ' [!DNL Adobe Workfront Fusion Adobe Creative Cloud]  ライブラリモジュールを使用すると、要素やライブラリが作成または更新されたときにシナリオを開始できます。また、要素をアップロード、取得、アーカイブまたはリストすることも、 [!DNL Adobe Creative Cloud Libraries]  API を呼び出すこともできます。'
author: Becky
feature: Workfront Fusion
exl-id: 85607e4e-538a-427f-8a99-a0ab65a75ac2
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 73%

---

# Adobe Creative Cloud ライブラリモジュール

[!DNL Adobe Workfront Fusion] [!DNL Adobe Creative Cloud Libraries] モジュールを使用すると、要素やライブラリが作成または更新されたときにシナリオを開始できます。また、要素をアップロード、取得、アーカイブまたはリストすることも、[!DNL Adobe Creative Cloud Libraries] API を呼び出すこともできます。

シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

>[!IMPORTANT]
>
>現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
      <td>
        <p>[!UICONTROL Pro] またはそれ以降</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
      <td>
        <p>[!UICONTROL Plan], [!UICONTROL Work]</p>
      </td>
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

[!DNL Adobe Creative Cloud Libraries] モジュールを使用するには、[!UICONTROL Adobe Creative Cloud] アカウントが必要です。

## Adobe Creative Cloud ライブラリ API の情報

Adobe Creative Cloud ライブラリコネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://cc-libraries.adobe.io/api/v1</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.1.7</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Adobe Creative Cloud Libraries] モジュールとそのフィールド

[!UICONTROL Adobe Creative Cloud Libraries] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Creative Cloud Libraries] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [要素](#elements)

* [ライブラリ](#libraries)

* [その他](#other)


### 要素

* [[!UICONTROL Archive an Element]](#archive-an-element)

* [[!UICONTROL Get an Element]](#get-an-element)

* [[!UICONTROL List Elements]](#list-elements)

* [[!UICONTROL Upload an Element]](#upload-an-element)

* [!UICONTROL [Watch New Element in Library]](#watch-new-element-in-library)

* [[!UICONTROL Watch Updated Elements]](#watch-updated-elements)


#### [!UICONTROL Archive an Element]

このアクションモジュールは、要素をライブラリからアーカイブします。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >アーカイブする要素を含むライブラリを選択します。</td>
    </tr>
    <tr>
      <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-LightGray" role="rowheader">[!UICONTROL Element ID]</td>
      <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-LightGray">アーカイブする要素を選択します。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Get an Element]

このアクションモジュールは、ライブラリから単一の要素を返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >取得する要素を含むライブラリを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>取得する要素の ID を入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>モジュールが返す情報のタイプを選択します。 </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>ベースデータ</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>すべての使用可能なデータ</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>ライブラリ要素に関連付けられたアセットのフラット化されたリスト</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL List Elements]

このアクションモジュールは、ライブラリ内の要素のリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >要素をリストするライブラリを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Order by]</td>
      <td>結果を名前順に並べ替えるか、要素が最後に変更された日付順に並べ替えるかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type]</td>
      <td >MIME タイプを入力して、指定した MIME タイプで識別される要素に結果を制限します。例：<code>string</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>モジュールが返す情報のタイプを選択します。 </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>ベースデータ</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>すべての使用可能なデータ</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>ライブラリ要素に関連付けられたアセットのフラット化されたリスト</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Upload an Element]

このアクションモジュールは、小さなファイルアセットを既存のライブラリにアップロードします。最大ファイルサイズは 1 GB です。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >要素をリストするライブラリを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Invocation Mode]</td>
      <td>
        <p>このリクエストプロセスを呼び出す処理モードを選択します。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL sync]</b>
            </p>
            <p>API 呼び出しが同期処理されます。処理が完了すると（呼び出しがタイムアウトしない限り）応答が配信されます。</p>
          </li>
          <li>
            <p><b>[!UICONTROL async]</b>
            </p>
            <p>非同期モニター応答は直ちに返され、リクエスト処理は非同期で実行されます。呼び出しは、完了するまでエンドポイントをポーリングする役割を持ちます。</p>
          </li>
          <li>
            <p><b>[!UICONTROL sync,async]</b> （デフォルト）</p>
            <p>リクエストの同期処理が試行されます。処理時間が 5000 ミリ秒を超えると、非同期モニター応答が返されます。リクエストが完了するまで、モニター URL をポーリングする必要があります。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type File]</td>
      <td >アップロードしたファイルの MIME タイプを入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Source File]</td>
      <td>
        <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Watch New Element in Library]

このトリガーモジュールは、要素がライブラリに追加されると、シナリオを開始します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >アップデートされた要素を監視するライブラリを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL Watch Updated Elements]

このトリガーモジュールは、ライブラリ内の要素がアップデートされると、シナリオを開始します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >新しい要素を監視するライブラリを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

### ライブラリ

* [[!UICONTROL Watch New Libraries]](#watch-new-libraries)

* [[!UICONTROL Watch Updated Libraries]](#watch-updated-libraries)


#### [!UICONTROL Watch New Libraries]

このトリガーモジュールは、新しいライブラリの作成時にシナリオを開始します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Watch Updated Libraries]

このトリガーモジュールは、既存のライブラリの更新時にシナリオを開始します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>既存のCreative Cloud Libraries接続を選択します。 現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

### その他

#### [!UICONTROL Make an API Call]

このモジュールは、[!DNL Adobe Creative Cloud Libraries] API に対してカスタム API 呼び出しを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Adobe Creative Cloud アカウントを Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion への接続を作成 - 基本手順を参照してください。</a></p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p><code>https://cc-libraries.adobe.io/api</code> への相対パスを入力します。</p>
    <p>例：<code>/v1/libraries</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL API version]</td>
      <td>
        <p>接続する [!DNL Adobe Analytics] APIのバージョンを選択します。</p>
      </td>
    </tr>    <tr>
      <td role="rowheader">[!UICONTROL Method]</td>
      <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
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
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
       <tr>
      <td role="rowheader">[!UICONTROL Upload a transient document]</td>
      <td>
      <p>一時的なドキュメントをアップロードする場合は、アップロードするドキュメントのソースファイルを入力します。</p>
      <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p>
    </td>
    </tr>

</tbody>
</table>
