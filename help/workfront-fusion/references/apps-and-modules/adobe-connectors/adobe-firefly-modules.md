---
title: Adobe Fireflyモジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、 [!DNL Adobe Firefly] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。'
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: 1219642306c03cb0aa6037493ce2f02ced80b99d
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 26%

---

# [!DNL Adobe Firefly] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Adobe Firefly] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

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
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
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

[!DNL Adobe Firefly] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!DNL Adobe Firefly] アカウントが必要です。

## Adobe FireflyAPI に関する情報

Adobe Fireflyコネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.4.24</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Adobe Firefly] への接続の作成

[!DNL Adobe Firefly] モジュールへの接続を作成するには、以下を実行します。

1. 「接続」ボックスの横にある「**[!UICONTROL Add]**」をクリックします。

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
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID] を入力します。 これは、[!DNL Adobe Developer Console] の「[!UICONTROL Credentials] 細」セクションで確認できます。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、[!DNL Adobe Developer Console] の「[!UICONTROL Credentials] 細」セクションで確認できます。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL Continue]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Firefly] モジュールとそのフィールド

[!DNL Adobe Firefly] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Firefly] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 画像を展開

このアクションモジュールは、画像を展開します（オプションで、指定したプロンプトのコンテンツも展開します）。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>画像を展開するコンテンツのプロンプトを入力またはマップします。 プロンプトが指定されない場合、画像は元の画像に一致するコンテンツで展開されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>1 ～ 4 の数字を入力してください。 モジュールは、この数の展開された画像バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expanded image format]</td> 
   <td>展開したイメージの保存先となるファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>  <p>前のモジュールからソースファイルを選択するか、ソースファイルの画像ファイル名と画像ファイル（データ）をマッピングします。</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>展開する画像のサイズを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seed]</td> 
   <td>使用するシードごとに、「<b> 項目を追加 </b>」をクリックして、整数を入力またはマッピングします。 この同じシードを別の画像を展開モジュールで使用して、異なるスタイルの類似した画像を生成することができます。 </td> 
  </tr> 
 </tbody> 
</table>

## 画像を埋める

このアクションモジュールは、画像のマスクされた領域を、必要に応じて、指定したプロンプトのコンテンツで埋めます。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>イメージを埋めるコンテンツの入力を求めるプロンプトを入力またはマップします。 プロンプトが指定されない場合、画像には元の画像と一致するコンテンツが入力されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>1 ～ 4 の数字を入力してください。 このモジュールは、この数の入力画像のバリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filled image format]</td> 
   <td>塗りつぶし画像を保存するファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image]</td> 
   <td>  <p> 入力する画像ごとに、「<b> 画像を追加 </b>」をクリックし、前のモジュールからソースファイルを選択するか、ソースファイルの画像ファイル名と画像データをマッピングします。</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mask]</td> 
   <td>  <p>  使用するマスクごとに、<b> マスクを追加 </b> をクリックします。 前のモジュールからソースファイルを選択するか、ソースファイルのマスクファイル名とマスクデータをマッピングします。 マスクファイルは、生成されたコンテンツで入力されるカスタムマスクを表します。</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>塗りつぶし画像のサイズを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>モジュールが生成する各画像に対して、「<b> 項目を追加 <b>」をクリックし、整数を入力またはマッピングします。 この同じシードを別の画像を展開モジュールで使用して、異なるスタイルの類似した画像を生成することができます。 追加するシードの数は、「バリエーション数」フィールドと同じ数にする必要があります。</td> 
  </tr> 
 </tbody> 
</table>

## 画像を生成

このアクションモジュールは、指定されたプロンプトに基づいてと画像を生成します。 オプションで参照画像を指定することもできます。この場合、生成された画像は参照画像のスタイルと一致します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Campaign] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>作成するイメージのプロンプトを入力またはマップします。 プロンプトの詳細を使用すると、画像に表示されるものを詳細に制御できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>1 ～ 4 の数字を入力してください。 モジュールは、この数の画像バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>展開したイメージの保存先となるファイル形式を選択します。 デフォルトを選択した場合、参照画像が指定されていないと、ファイル形式はJPEGになります。 参照画像を指定した場合、生成される画像のファイル形式は参照画像と同じになります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>  <p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイル（データ）をマッピングします。 参照画像のスタイルに一致する画像が生成されます。</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presets]</td> 
   <td>プリセットスタイルを使用する場合は、「項目を追加」をクリックし、使用するスタイルを入力またはマップします。<p>プリセットスタイルのリストについては、Adobe開発者ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" > 画像モデルスタイル </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Negative prompt]</td> 
   <td>生成されたコンテンツで避ける単語を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content class]</td> 
   <td>生成された画像を写真に近づけるのか、それとも作成されたアートに近づけるのかを選択します。 <ul><li><b>写真</b><p>「絞り」、「シャッタースピード」（秒単位）、「視野」（ミリメートル単位）の値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seed]</td> 
   <td>整数を入力またはマッピングします。 この同じシードを別の画像を展開モジュールで使用して、異なるスタイルの類似した画像を生成することができます。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>生成される画像のサイズを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Strength]</td> 
   <td>生成される画像がプリセットのスタイルまたは参照画像と一致する強度を表す整数を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visual intensity]</td> 
   <td>写真の既存の視覚特性の全体的な強度を表す整数を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>ロケールが指定された場合、モジュールは指定されたロケールにより関連性の高いコンテンツを生成します。 <p>ロケールは、ISO 639-1 言語コードおよび ISO 3166-1 地域で提供する必要があります。</p><p> 例： <code>en-US</code></p></td> 
  </tr> 
 </tbody> 
</table>



### カスタム API 呼び出しの実行

このアクションモジュールは、FireflyAPI へのカスタム呼び出しを行います。

使用可能な特定の API については、Adobe Developer ドキュメントの [Adobe FireflyAPI](https://developer.adobe.com/firefly-services/docs/firefly-api/) を参照してください。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p><code>https://firefly-api.adobe.io/</code> への相対パスを入力します。</p>
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
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

