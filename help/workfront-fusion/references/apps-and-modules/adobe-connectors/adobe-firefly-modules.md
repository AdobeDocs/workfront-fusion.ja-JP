---
title: Adobe Firefly モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Adobe Firefly] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: a766080defca64b4ce5d8ecd8b19fdfc3ff26470
workflow-type: tm+mt
source-wordcount: '2519'
ht-degree: 22%

---

# [!DNL Adobe Firefly] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Adobe Firefly] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

シナリオの作成手順が必要な場合は、[&#x200B; シナリオの作成：記事インデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

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

[!DNL Adobe Firefly] コネクタを使用する前に、以下の前提条件が満たされていることを確認してください。

* アクティブな [!DNL Adobe Firefly] アカウントが必要です。

## Adobe Firefly APIについて

Adobe Firefly コネクタでは、次の機能が使用されます。

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

1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

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
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID]を入力します。 これは、[!DNL Adobe Developer Console]の[!UICONTROL Credentials]の詳細セクションにあります。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、[!DNL Adobe Developer Console]の[!UICONTROL Credentials]の詳細セクションにあります。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Firefly] モジュールとそのフィールド

[!DNL Adobe Firefly] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Firefly]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 画像を拡大

このアクションモジュールは、オプションで指定したプロンプトのコンテンツを使用して、画像を拡張します。

このモジュールは、Firefly API V3非同期で動作します。 このモジュールの以前のバージョンは推奨されません。近い将来リリースされる予定です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロンプト &#x200B;]</td> 
   <td>画像を展開するコンテンツのプロンプトを入力またはマッピングします。 プロンプトを指定しない場合、画像は元の画像に一致するコンテンツで展開されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 4の数字を入力します。 モジュールは、この数の拡張された画像バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source]</td> 
   <td>ソースファイルの提供方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 拡張された画像形式]</td> 
   <td>拡張した画像を保存するファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の展開：]</td> 
   <td>  <p>画像の配置を使用するか、マスクを使用して画像を拡大するかを選択します。</p> 
   <ul>
   <li><b>プレースメント</b><p>水平方向と垂直方向の整列、およびエッジから配置された画像のインセットを入力します。</p></li>
   <li><b>マスク</b><p>マスクのソースファイルと、マスクを反転させるかどうかを選択します。</p></li>
   </ul>
</td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズ &#x200B;]</td> 
   <td>拡大した画像の高さと幅を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>モジュールが生成する各画像について、<b>項目を追加</b>をクリックし、整数を入力またはマッピングします。 この同じシードを別の「画像を展開」モジュールで使用して、異なるスタイルの類似した画像を生成できます。 追加するシードの数は、「バリエーションの数」フィールドと同じである必要があります。</td> 
  </tr> 
 </tbody> 
</table>

### 画像を展開する（非推奨）

このモジュールは推奨されません。近い将来リリースされる予定です。 代わりに、「画像を展開」モジュールを使用します。

### 画像を塗りつぶす

このアクションモジュールは、画像のマスクされた領域を塗りつぶし、オプションで指定したプロンプトのコンテンツを入力します。

このモジュールは、Firefly API V3非同期で動作します。 このモジュールの以前のバージョンは推奨されません。近い将来リリースされる予定です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image &gt; Source]</td> 
   <td>画像ソースファイルの提供方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mask &gt; Source]</td> 
   <td>マスクソースファイルの提供方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロンプト &#x200B;]</td> 
   <td>画像を塗りつぶすコンテンツのプロンプトを入力またはマッピングします。 プロンプトを指定しない場合、画像は元の画像に一致するコンテンツで塗りつぶされます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 4の数字を入力します。 モジュールは、この数の塗りつぶされた画像のバリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filled image format]</td> 
   <td>塗りつぶされた画像を保存するファイル形式を選択します。</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>モジュールが生成する各画像について、<b>項目を追加</b>をクリックし、整数を入力またはマッピングします。 この同じシードを別の「画像を展開」モジュールで使用して、異なるスタイルの類似した画像を生成できます。 追加するシードの数は、「バリエーションの数」フィールドと同じである必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズ &#x200B;]</td> 
   <td>塗りつぶし画像のサイズを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>ロケールが指定されている場合、モジュールは、指定されたロケールに関連するコンテンツを生成します。 <p>ロケールは、ISO 639-1言語コードおよびISO 3166-1地域で指定する必要があります。</p><p> 例： <code>en-US</code></p></td> 
  </tr> 
 </tbody> 
</table>

### 画像を入力（非推奨）

このモジュールは推奨されません。近い将来リリースされる予定です。 代わりに、「画像を塗りつぶす」モジュールを使用してください。

### 画像を生成

このアクションモジュールは、指定したプロンプトに基づいて画像を生成します。 オプションで参照画像を指定することもできます。生成された画像は、参照画像のスタイルに一致します。

このモジュールは、Firefly API V3非同期で動作します。 このモジュールの以前のバージョンは推奨されません。近い将来リリースされる予定です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロンプト &#x200B;]</td> 
   <td>生成する画像のプロンプトを入力またはマッピングします。 プロンプトの詳細を指定すると、画像に表示される内容をより詳細に制御できるようになります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL モデル バージョン &#x200B;]</td> 
   <td>画像の生成に使用するFirefly モデルバージョンを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 4の数字を入力します。 モジュールは、この数の画像バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>拡張した画像を保存するファイル形式を選択します。 デフォルトを選択した場合、参照画像が提供されない場合、ファイル形式はJPEGになります。 参照画像が指定されている場合、生成された画像のファイル形式は参照画像と同じになります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 構造&gt;画像参照]</td> 
    <td>新しい画像の構造にソースファイルを提供する方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure &gt; Strength]</td> 
    <td>0 ～ 100の数値を入力して、Fireflyがソースイメージの構造にどの程度厳密に従うかを制御します。 数字が大きいほど、Fireflyは画像をより厳密に追跡しています。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スタイル &gt;画像参照]</td> 
    <td>新しい画像のスタイルのソースファイルを提供する方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure &gt; Strength]</td> 
    <td>0 ～ 100の数値を入力して、Fireflyがソースイメージのスタイルに従う厳密な順序を制御します。 数字が大きいほど、Fireflyは画像をより厳密に追跡しています。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スタイル &gt; プリセット &#x200B;]</td> 
   <td>プリセットスタイルを使用する場合は、「項目を追加」をクリックし、使用するスタイルを入力またはマッピングします。<p>プリセットスタイルの一覧については、Adobe開発者向けドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >画像モデルスタイル </a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Negative prompt]</td> 
   <td>生成されたコンテンツに避ける単語を入力するか、マッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツクラス &#x200B;]</td> 
   <td>生成された画像を写真に似たものにするか、作成したアートに似たものにするかを選択します。 <ul><li><b>写真</b><p>絞り、シャッタースピード（秒単位）、視野（ミリメートル単位）の値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seed]</td> 
   <td>モジュールが生成する各画像について、<b>項目を追加</b>をクリックし、整数を入力またはマッピングします。 この同じシードを別の「画像を展開」モジュールで使用して、異なるスタイルの類似した画像を生成できます。 追加するシードの数は、「バリエーションの数」フィールドと同じである必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズ &#x200B;]</td> 
   <td>生成する画像のサイズを選択します。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Visual intensity]</td> 
   <td>写真の既存の視覚的特性の全体的な強度を表す整数を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>ロケールが指定されている場合、モジュールは、指定されたロケールに関連するコンテンツを生成します。 <p>ロケールは、ISO 639-1言語コードおよびISO 3166-1地域で指定する必要があります。</p><p> 例： <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tileable]</td> 
   <td>このオプションを有効にすると、あらゆる方向に無限に繰り返すことができる画像を生成できます。</td> 
  </tr> 
 </tbody> 
</table>

### 画像の生成（非推奨）

このモジュールは推奨されません。近い将来リリースされる予定です。 代わりに、「画像を生成」モジュールを使用します。

### オブジェクト合成を生成

このアクションモジュールは、Fireflyで生成された画像を結合して、画像の合成画像を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロンプト &#x200B;]</td> 
   <td>生成する画像のプロンプトを入力またはマッピングします。 プロンプトの詳細を指定すると、画像に表示される内容をより詳細に制御できるようになります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 4の数字を入力します。 モジュールは、この数の画像バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ クラス &#x200B;]</td> 
   <td>生成する画像を写真に似たものにするか、アートに似たものにするかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image &gt; Source]</td> 
    <td>新しい画像の構造にソースファイルを提供する方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>拡張した画像を保存するファイル形式を選択します。 デフォルトを選択した場合、参照画像が提供されない場合、ファイル形式はJPEGになります。 参照画像が指定されている場合、生成された画像のファイル形式は参照画像と同じになります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スタイル &gt;画像参照]</td> 
    <td>新しい画像のスタイルのソースファイルを提供する方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure &gt; Strength]</td> 
    <td>0 ～ 100の数値を入力して、Fireflyがソースイメージのスタイルに従う厳密な順序を制御します。 数字が大きいほど、Fireflyは画像をより厳密に追跡しています。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スタイル &gt; プリセット &#x200B;]</td> 
   <td>プリセットスタイルを使用する場合は、「項目を追加」をクリックし、使用するスタイルを入力またはマッピングします。<p>プリセットスタイルの一覧については、Adobe開発者向けドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >画像モデルスタイル </a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズ &#x200B;]</td> 
   <td>生成するコンポジットのサイズを選択します。 </td> 
  </tr> 
 </tbody> 
</table>

### 類似した画像を生成

このアクションモジュールは、指定したソース画像と類似した画像を生成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 4の数字を入力します。 モジュールは、この数の画像バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL モデル バージョン &#x200B;]</td> 
   <td>画像の生成に使用するFirefly モデルバージョンを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>拡張した画像を保存するファイル形式を選択します。 デフォルトを選択した場合、参照画像が提供されない場合、ファイル形式はJPEGになります。 参照画像が指定されている場合、生成された画像のファイル形式は参照画像と同じになります。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Image &gt; Source]</td> 
    <td>新しい画像の構造にソースファイルを提供する方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL スタイル &gt;画像参照]</td> 
    <td>新しい画像のスタイルのソースファイルを提供する方法を選択します。<ul><li><p><b>ファイル</b></p><p>前のモジュールからソースファイルを選択するか、ソースファイルの参照画像ファイル名と参照画像ファイルをマッピングします。</p></li><li><p><b>事前定義済みURL</b></p><p>ソース画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズ &#x200B;]</td> 
   <td>生成するコンポジットのサイズを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>モジュールが生成する各画像について、<b>項目を追加</b>をクリックし、整数を入力またはマッピングします。 この同じシードを別の「画像を展開」モジュールで使用して、異なるスタイルの類似した画像を生成できます。 追加するシードの数は、「バリエーションの数」フィールドと同じである必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tileable]</td> 
   <td>このオプションを有効にすると、あらゆる方向に無限に繰り返すことができる画像を生成できます。</td> 
  </tr> 
 </tbody> 
</table>


### カスタム API 呼び出しの実行

このアクションモジュールは、Firefly APIをカスタム呼び出します。

使用可能な特定のAPIについては、Adobe Developer ドキュメントの[Adobe Firefly API](https://developer.adobe.com/firefly-services/docs/firefly-api/)を参照してください。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p><code>https://firefly-api.adobe.io/</code> からの相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は認証ヘッダーを自動的に追加します。</p>
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

