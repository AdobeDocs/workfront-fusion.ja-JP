---
title: Adobe Creative Cloud ライブラリモジュール
description: ' [!DNL Adobe Workfront Fusion Adobe Creative Cloud]  ライブラリモジュールを使用すると、要素やライブラリが作成または更新されたときにシナリオを開始できます。また、要素をアップロード、取得、アーカイブまたはリストすることも、 [!DNL Adobe Creative Cloud Libraries]  API を呼び出すこともできます。'
author: Becky
feature: Workfront Fusion
exl-id: 85607e4e-538a-427f-8a99-a0ab65a75ac2
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 66%

---

# Adobe Creative Cloud ライブラリモジュール

[!DNL Adobe Workfront Fusion] [!DNL Adobe Creative Cloud Libraries] モジュールを使用すると、要素やライブラリが作成または更新されたときにシナリオを開始できます。また、要素をアップロード、取得、アーカイブまたはリストすることも、[!DNL Adobe Creative Cloud Libraries] API を呼び出すこともできます。

シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

>[!IMPORTANT]
>
>現在、Creative Cloud Libraries コネクタでは接続を作成できません。 既存の接続は期待どおりに動作します。

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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

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

## [!UICONTROL Adobe Creative Cloud ライブラリ]モジュールおよびそのフィールド

[!UICONTROL Adobe Creative Cloud ライブラリ]モジュール設定時に、[!DNL Workfront Fusion] には以下のフィールドが表示されます。これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Creative Cloud Libraries] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [要素](#elements)

* [ライブラリ](#libraries)

* [その他](#other)


### 要素

* [[!UICONTROL 要素のアーカイブ]](#archive-an-element)

* [[!UICONTROL 要素の取得]](#get-an-element)

* [[!UICONTROL 要素のリスト]](#list-elements)

* [[!UICONTROL 要素のアップロード]](#upload-an-element)

* [!UICONTROL [Watch New Element in Library]](#watch-new-element-in-library)

* [[!UICONTROL 更新された要素の監視]](#watch-updated-elements)


#### [!UICONTROL 要素のアーカイブ]

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
      <td >アーカイブする要素を含むライブラリを選択またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>アーカイブする要素を選択またはマッピングします。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 要素の取得]

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
      <td>取得する要素を含むライブラリを選択またはマッピングします。</td>
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

#### [!UICONTROL リスト要素]

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
      <td >要素をリストするライブラリを選択またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Order by]</td>
      <td>結果を名前で並べ替えるか、要素が最後に変更された日付で並べ替えるかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type]</td>
      <td >MIME タイプを入力またはマッピングして、指定した MIME タイプで識別される要素のみに結果を制限します。 例：<code>string</code>。</td>
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

#### [!UICONTROL ライブラリの新しい要素を監視]

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


#### [!UICONTROL アップデートされた要素を監視]

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

* [[!UICONTROL 新しいライブラリを監視]](#watch-new-libraries)

* [[!UICONTROL アップデートされたライブラリを監視]](#watch-updated-libraries)


#### [!UICONTROL 新しいライブラリを監視]

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

#### [!UICONTROL アップデートされたライブラリを監視]

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

* [API 呼び出しを実行](#make-an-api-call)
* [アセットのアップロード](#upload-an-asset)

#### [!UICONTROL API 呼び出しを実行]

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
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
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


#### [!UICONTROL  アセットをアップロード ]

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
      <td >アセットのアップロード先となるライブラリを選択します。</td>
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
            <p><b>[!UICONTROL sync,async]</b>（デフォルト）</p>
            <p>リクエストの同期処理が試行されます。処理時間が 5000 ミリ秒を超えると、非同期モニター応答が返されます。リクエストが完了するまで、モニター URL をポーリングする必要があります。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 要素タイプ ]</td>
      <td >アップロードする要素のタイプを選択します</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ファイルの種類 ]</td>
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





