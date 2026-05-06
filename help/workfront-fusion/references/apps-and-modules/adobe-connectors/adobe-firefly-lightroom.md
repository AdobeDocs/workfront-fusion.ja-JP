---
title: Adobe Firefly モジュール
description: Adobe Workfront Fusionでは、Adobe Firefly Lightroomを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: 965cb643039be36eb3608cd801439a6a055974e4
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 16%

---

# Adobe Firefly Lightroom モジュール

<!--add to tocs-->

Adobe Workfront Fusionでは、Adobe Firefly Lightroomを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成手順が必要な場合は、[ シナリオの作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

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

Adobe Firefly Lightroom コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブなAdobe Firefly Lightroom アカウントが必要です。

## Adobe Firefly Lightroomへの接続の作成

Adobe Firefly Lightroom モジュールの接続を作成するには：

1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">接続名</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">環境</td>
        <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">タイプ</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">クライアント ID</td>
        <td>Adobe クライアント IDを入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションで確認できます。</td>
        </tr>
        <tr>
        <td role="rowheader">クライアントシークレット</td>
        <td>Adobe Client Secretを入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションで確認できます。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。


## Adobe Firefly Lightroomのモジュールとそのフィールド

Adobe Firefly Lightroom モジュールを設定すると、Workfront Fusionに次のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Adobe Firefly Lightroomの追加フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [XMPを追加](#add-xmp-to-image)
* [Lightroomの編集を適用](#apply-lightroom-edits)
* [Lightroom プリセットの適用](#apply-lightroom-presets)
* [自動角度補正](#auto-straighten)
* [自動トーン](#auto-tone)


### XMPを追加

このモジュールは、XMP ベースのLightroom プリセットを画像に適用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Firefly Lightroomへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Adobe Firefly Lightroomへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像URL</td> 
   <td>XMPを適用する画像を表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストレージタイプ</td> 
   <td>画像を保存するストレージのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">XMP content</td> 
   <td>画像に追加するXMP コンテンツのテキストを入力またはマッピングします。 これはXML文字列である必要があります。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">オリエンテーション</td> 
    <td>画像に適用するEXIF方向を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力ストレージ</td> 
    <td>出力ファイルの保存場所を選択します。 <p>Fusionの内部ストレージは、シナリオの外部に画像を保存しませんが、シナリオ内の他のモジュールが画像にアクセスできるようにします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力タイプ</td> 
   <td>出力ファイルのファイルタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>モジュールが既に存在する場合に出力を上書きできるようにする場合は、「はい」を選択します。 これは、Adobe クラウドストレージにのみ適用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画質</td> 
   <td>出力画像の画質を入力またはマッピングします。 1が最も低いクォリティ、12が最も高いクォリティです。 これは、JPEG ファイルにのみ適用されます。</td> 
  </tr> 
 </tbody> 
</table>

### Lightroomの編集を適用

このモジュールは、1つまたは複数のLightroom編集を画像に適用します。 編集には、露光量、コントラスト、シャープネス、彩度が含まれます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Firefly Lightroomへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Adobe Firefly Lightroomへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像URL</td> 
   <td>XMPを適用する画像を表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストレージタイプ</td> 
   <td>画像を保存するストレージのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オプションを編集</td> 
   <td>画像に適用する編集オプションを設定します。<p>オプションについて詳しくは、Adobe Firefly Lightroom API ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/lightroom/api/#operation/applyEdits">Lightroom編集の適用</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力ストレージ</td> 
    <td>出力ファイルの保存場所を選択します。 <p>Fusionの内部ストレージは、シナリオの外部に画像を保存しませんが、シナリオ内の他のモジュールが画像にアクセスできるようにします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力タイプ</td> 
   <td>出力ファイルのファイルタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>モジュールが既に存在する場合に出力を上書きできるようにする場合は、「はい」を選択します。 これは、Adobe クラウドストレージにのみ適用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画質</td> 
   <td>出力画像の画質を入力またはマッピングします。 1が最も低いクォリティ、12が最も高いクォリティです。 これは、JPEG ファイルにのみ適用されます。</td> 
  </tr> 
 </tbody> 
</table>

### Lightroom プリセットの適用

このモジュールでは、特定のプリセットXMP ファイルを使用して、1つ以上のXMP Lightroom プリセットを特定の画像に適用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Firefly Lightroomへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Adobe Firefly Lightroomへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像URL</td> 
   <td>XMPを適用する画像を表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストレージタイプ</td> 
   <td>画像を保存するストレージのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プリセット</td> 
   <td>適用する各プリセットについて、<b>項目を追加</b>をクリックし、プリセットの事前署名済みURLを入力し、そのストレージタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力ストレージ</td> 
    <td>出力ファイルの保存場所を選択します。 <p>Fusionの内部ストレージは、シナリオの外部に画像を保存しませんが、シナリオ内の他のモジュールが画像にアクセスできるようにします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力タイプ</td> 
   <td>出力ファイルのファイルタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>モジュールが既に存在する場合に出力を上書きできるようにする場合は、「はい」を選択します。 これは、Adobe クラウドストレージにのみ適用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画質</td> 
   <td>出力画像の画質を入力またはマッピングします。 1が最も低いクォリティ、12が最も高いクォリティです。 これは、JPEG ファイルにのみ適用されます。</td> 
  </tr> 
 </tbody> 
</table>

### 自動角度補正

このモジュールは、自動角度補正を適用して画像を自動角度補正します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Firefly Lightroomへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Adobe Firefly Lightroomへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像URL</td> 
   <td>XMPを適用する画像を表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストレージタイプ</td> 
   <td>画像を保存するストレージのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Upright モード</td> 
   <td>使用するUpright モードのタイプを選択します。 値を設定しない場合は、適切なモードが自動的に提供されます。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">切り抜きを制限</td> 
   <td>角度補正された画像を切り抜いて、空白のエッジをすべて削除するかどうかを選択します。</td> 
  </tr> 
 <tr> 
   <td role="rowheader">出力ストレージ</td> 
    <td>出力ファイルの保存場所を選択します。 <p>Fusionの内部ストレージは、シナリオの外部に画像を保存しませんが、シナリオ内の他のモジュールが画像にアクセスできるようにします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力タイプ</td> 
   <td>出力ファイルのファイルタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>モジュールが既に存在する場合に出力を上書きできるようにする場合は、「はい」を選択します。 これは、Adobe クラウドストレージにのみ適用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画質</td> 
   <td>出力画像の画質を入力またはマッピングします。 1が最も低いクォリティ、12が最も高いクォリティです。 これは、JPEG ファイルにのみ適用されます。</td> 
  </tr> 
 </tbody> 
</table>


### 自動トーン

このモジュールは、画像上の露光量、コントラスト、シャープネス、彩度を自動的に補正します。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Firefly Lightroomへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >Adobe Firefly Lightroomへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像URL</td> 
   <td>XMPを適用する画像を表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストレージタイプ</td> 
   <td>画像を保存するストレージのタイプを選択します。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">出力ストレージ</td> 
    <td>出力ファイルの保存場所を選択します。 <p>Fusionの内部ストレージは、シナリオの外部に画像を保存しませんが、シナリオ内の他のモジュールが画像にアクセスできるようにします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">出力タイプ</td> 
   <td>出力ファイルのファイルタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>モジュールが既に存在する場合に出力を上書きできるようにする場合は、「はい」を選択します。 これは、Adobe クラウドストレージにのみ適用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画質</td> 
   <td>出力画像の画質を入力またはマッピングします。 1が最も低いクォリティ、12が最も高いクォリティです。 これは、JPEG ファイルにのみ適用されます。</td> 
  </tr> 
 </tbody> 
</table>


