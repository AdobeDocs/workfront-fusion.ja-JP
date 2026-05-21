---
title: Adobe Firefly モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Adobe Firefly] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
TQID: https://experienceleague.adobe.com/1hI4NuUl2eEAgWyXRKLHQ3-6MM9-2tFyujGbRfHSBmU
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 3886
ht-degree: 16%

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

### アダプティブ合成を生成

このアクションモジュールは、被写体の画像をマスクされた場所の背景画像にシームレスに合成します。 シャドウを強く適用する方法、オブジェクトの照明とカラーを背景と調和させる方法、元の背景のディテールをマスクされた領域内に保持するかどうかを制御できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background &gt; Image &gt; Source]</td> 
   <td>背景画像の提供方法を選択します。 背景画像は、オブジェクトが合成される目的のシーンです。<ul><li><p><b>画像をアップロード</b></p><p>背景画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>背景画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background &gt; Fill Area Mask &gt; Source]</td> 
   <td>塗りつぶし領域マスクの提供方法を選択します。 塗りつぶし領域マスクは、オブジェクトが配置される背景の領域を示します。<ul><li><p><b>画像をアップロード</b></p><p>塗りつぶし領域マスク画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>塗りつぶし領域マスク画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object &gt; Image &gt; Source]</td> 
   <td>オブジェクト画像の提供方法を選択します。 オブジェクト画像は、背景に合成するオブジェクトのソース画像です。<ul><li><p><b>画像をアップロード</b></p><p>オブジェクト画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>オブジェクト画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object &gt; Mask &gt; Source]</td> 
   <td>オブジェクトマスクの提供方法を選択します。 オブジェクトマスクは、オブジェクトのセグメンテーションマスクです。<ul><li><p><b>画像をアップロード</b></p><p>オブジェクトマスク画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>オブジェクトマスク画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 3の数値を入力します。 モジュールは、この数の複合バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]*</td> 
   <td>「<b>項目を追加</b>」をクリックしてシード値を追加し、整数を入力またはマッピングします。 バリエーションごとに1つのシードを使用します。 シード値の数は、両方が指定されている場合、[!UICONTROL バリエーション数]値と一致する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Harmonization]*</td> 
   <td>0 ～ 1の値を入力して、オブジェクトのカラーと照明を背景に合わせて調整する量を制御します。 <code>0.0</code>は最小調和を適用し、<code>1.0</code>は最大調和を適用します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shadow Intensity]*</td> 
   <td>0 ～ 1の数値を入力して、合成された結果のシャドウの適用度を制御します。 値を小さくすると、シャドウが小さくなります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 背景を保持]*</td> 
   <td>合成の際に、マスクされた領域内に元の背景のディテールを保持するかどうかを選択します。 <ul><li><b>はい</b><p>マスクされた領域内の元の背景のディテールは、合成中に保持されます。</p></li><li><b>いいえ</b><p>マスクされた領域内の元の背景のディテールは、合成中は保持されません。</p></li><li><b>未定義</b><p>このオプションのデフォルトのビヘイビアーを使用します。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output &gt; Media Type]*</td> 
   <td>生成されたコンポジットを保存するファイル形式を選択します。</td> 
  </tr> 
 </tbody> 
</table>

* これらのフィールドは詳細フィールドで、**[!UICONTROL 詳細設定を表示]**&#x200B;を選択しない限り表示されません。

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

### Image5で画像を生成

このアクションモジュールは、[!DNL Adobe Firefly] Image5 モデルを使用して画像を生成します。 生成をガイドするテキストプロンプトと、必要に応じて参照画像を指定します。

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
   <td>生成する画像の説明を入力またはマッピングします。 プロンプトは1 ～ 1500文字の範囲である必要があります。 プロンプトの詳細を指定すると、画像に表示される内容をより詳細に制御できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Aspect Ratio]</td> 
   <td>生成された画像のシェイプを選択します。 参照画像が指定されている場合は、<b>自動</b>を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 解像度]</td> 
   <td>生成された画像の解像度を選択します。 高解像度の場合、生成に時間がかかります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 参照画像]</td> 
   <td>オプションで、生成をガイドする参照画像を1つ指定します。 「<b>項目を追加</b>」をクリックし、画像を入力します。 参照画像を使用する場合は、[!UICONTROL Aspect Ratio]を<b>Auto</b>に設定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seed]*</td> 
   <td>「<b>項目を追加</b>」をクリックし、整数を入力またはマッピングして、特定の生成結果を再現します。 ランダムな結果を生成するには、空のままにします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロンプトの推論]*</td> 
   <td>生成時に使用するプロンプト推論戦略を選択します。<ul><li><p><b>品質 – 画像の説明を生成</b></p><p>モジュールの出力に画像の説明を生成します。</p></li><li><p><b>スピード – より速い生成、説明なし</b></p><p>画像は速く生成されますが、画像の説明は空のままになります。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]*</td> 
   <td>言語と地域コードを入力またはマッピングして、生成されたコンテンツを特定の国と言語に合わせてカスタマイズします。 <p>ロケールは、ISO 639-1言語コードおよびISO 3166-1地域で指定する必要があります。</p><p>例： <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]*</td> 
   <td>リクエストごとに生成する画像の数を入力します。 現在、1つのみがサポートされています。 複数の画像を生成するには、個別のリクエストを送信します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model]*</td> 
   <td>画像の生成に使用する[!DNL Firefly] モデルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>1回の実行サイクル中にモジュールが処理する結果の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

* これらのフィールドは高度であり、**[!UICONTROL 高度な設定を表示]**&#x200B;を選択しない限り表示されません。

### 正確な合成を生成

このアクションモジュールは、背景の画像のマスクされた領域に被写体を配置し、生成ハーモナイゼーションを適用して、被写体が背景に自然に溶け込むようにします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Firefly] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >[!DNL Adobe Firefly]</a> への接続の作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background &gt; Image &gt; Source]</td> 
   <td>背景画像の提供方法を選択します。 背景画像は、オブジェクトが合成される目的のシーンです。<ul><li><p><b>画像をアップロード</b></p><p>背景画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>背景画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background &gt; Fill Area Mask &gt; Source]</td> 
   <td>塗りつぶし領域マスクの提供方法を選択します。 塗りつぶし領域マスクは、オブジェクトが配置される背景の領域を示します。<ul><li><p><b>画像をアップロード</b></p><p>塗りつぶし領域マスク画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>塗りつぶし領域マスク画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object &gt; Image &gt; Source]</td> 
   <td>オブジェクト画像の提供方法を選択します。 オブジェクト画像は、背景に合成するオブジェクトのソース画像です。<ul><li><p><b>画像をアップロード</b></p><p>オブジェクト画像をアップロードするか、以前のモジュールから画像ファイルをマッピングします。</p></li><li><p><b>画像URL</b></p><p>オブジェクト画像のURLを入力またはマッピングします。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL バリエーション数]</td> 
   <td>1 ～ 3の数値を入力します。 モジュールは、この数の複合バリエーションを生成します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]*</td> 
   <td>「<b>項目を追加</b>」をクリックしてシード値を追加し、整数を入力またはマッピングします。 バリエーションごとに1つのシードを使用します。 シード値の数は、両方が指定されている場合、[!UICONTROL バリエーション数]値と一致する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blend]*</td> 
   <td>0 ～ 1の値を入力して、オブジェクトの調和された外観と元の外観のブレンドを制御します。 <code>0.0</code>は完全な調和を適用し、<code>1.0</code>は元のオブジェクトの外観を保持します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output &gt; Media Type]*</td> 
   <td>生成されたコンポジットを保存するファイル形式を選択します。</td> 
  </tr> 
 </tbody> 
</table>

* これらのフィールドは詳細フィールドで、**[!UICONTROL 詳細設定を表示]**&#x200B;を選択しない限り表示されません。

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


### ビデオを生成

このアクションモジュールは、テキストプロンプトからビデオを生成します。 ビデオ生成をガイドする1つ以上の参照画像を指定することもできます。

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
   <td>生成するビデオの説明を入力またはマッピングします。 プロンプトの詳細を表示すると、ビデオに表示される内容をより詳細に制御できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image &gt; Conditions]</td> 
   <td>オプションで、ビデオ生成をガイドする1つ以上の参照画像を指定します。 各参照画像の「<b>項目を追加</b>」をクリックします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイズ &#x200B;]</td> 
   <td>「<b>項目を追加</b>」をクリックし、生成されたビデオのサイズを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bit Rate Factor]*</td> 
   <td>生成されたビデオのビットレート係数を指定するには、0 ～ 63の数値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Video Settings &gt; Camera Motion]*</td> 
   <td>生成されたビデオで使用するカメラモーションを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ビデオ設定/プロンプトスタイル &#x200B;]*</td> 
   <td>生成されたビデオに使用するプロンプトスタイルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Video Settings &gt; Shot Angle]*</td> 
   <td>生成されたビデオで使用するショット角度を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Video Settings &gt; Shot Size]*</td> 
   <td>生成されたビデオで使用するショットサイズを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>1回の実行サイクル中にモジュールが処理する結果の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

* これらのフィールドは詳細フィールドで、**[!UICONTROL 詳細設定を表示]**&#x200B;を選択しない限り表示されません。

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

