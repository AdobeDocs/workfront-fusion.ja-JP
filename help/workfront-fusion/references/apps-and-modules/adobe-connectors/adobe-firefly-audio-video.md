---
title: Adobe Fireflyの音声および動画モジュール
description: Adobe Workfront Fusionでは、Adobe Firefly Audio and Videoを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: f54338aa35b8453ac991c9e16974f2b61fd30168
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 14%

---

# Adobe Fireflyの音声および動画モジュール

Adobe Workfront Fusionでは、Adobe Firefly Audio and Videoを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

Adobe Firefly オーディオおよびビデオコネクタを使用する前に、次の前提条件を満たしていることを確認する必要があります。

* アクティブなAdobe Firefly Audio and Video アカウントが必要です。

## Adobe Firefly Audio and Videoへの接続を作成する

Adobe Firefly オーディオおよびビデオモジュールの接続を作成するには、次の手順に従います。

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


## Adobe Firefly オーディオおよびビデオモジュールとそのフィールド

Adobe Firefly オーディオモジュールとビデオモジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Adobe Firefly オーディオおよびビデオの追加フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

* [テンプレートを記述](#describe-template)
* [音声または動画を吹き替え](#dub-audio-or-video)
* [テキストまたはオーディオからアバタービデオを生成](#generate-avatar-video-from-text-or-audio)
* [テキストから音声を生成](#generate-speech-from-text)
* [ビデオをリフレーム](#reframe-video)
* [レンダーテンプレート](#render-template)
* [文字起こし](#transcribe-media)

#### テンプレートを記述

このアクションモジュールは、MOGRT （ビデオテンプレート）ファイルを分析し、編集可能なコントロール、フォント、画像、オーディオ、ビデオ、およびその他のサポートされている値のマニフェストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>入力テンプレートファイルを指す事前署名済みURLを入力またはマッピングします。</td> 
  </tr>
 </tbody> 
</table>

#### 音声または動画を吹き替え

このアクションモジュールは、吹き替えオーディオまたはビデオを生成します。 生成されたビデオにリップシンクを含めることもできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">吹き替えタイプ</td> 
   <td>オーディオまたはビデオ吹き替えを生成するかどうかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">事前定義済みURL</td> 
   <td>モジュールが入力に使用する事前署名済みURLを入力またはマッピングします。<p>メディアストレージ用の次のドメインは、Firefly Audio and Videoで受け入れられます</p>
   <ul>
   <li>adobe.io</li>
   <li>frame.io</li>
   <li>amazonaws.com</li>
   <li>windows.net</li>
   <li>dropboxusercontent.com</li>
   <li>drive.google.com</li>
   <li>cloudfront.net</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">メディアタイプ</td> 
   <td>入力ファイルのメディアタイプを選択</td> 
  </tr>
  <tr> 
   <td role="rowheader">リップシンク</td> 
   <td>ビデオ出力用の高品質な合成リップシンクを生成するかどうかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">ターゲットロケールコード</td> 
   <td>追加する各ロケールコードについて、<b>項目を追加</b>をクリックし、ロケールコードを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">文字起こし</td> 
   <td>追加するトランスクリプトごとに、<b>項目を追加</b>をクリックし、トランスクリプトの事前署名済みURLを入力またはマッピングします。</td> 
  </tr>
 </tbody> 
</table>

#### テキストまたはオーディオからアバタービデオを生成

このアクションモジュールは、提供されたトランスクリプトまたはオーディオファイルからアバタービデオを生成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>モジュールが入力に使用する事前署名済みURLを入力またはマッピングします。   </td> 
  </tr>
  <tr> 
  <tr> 
   <td role="rowheader">ロケールコード</td> 
   <td>結果で使用する言語を表すロケールコードを選択します。</td> 
  </tr>
   <td role="rowheader">Media type （Source）</td> 
   <td>入力ファイルのメディアタイプを選択</td> 
  </tr>
  <tr> 
   <td role="rowheader">アバター</td> 
   <td>生成されたビデオに使用するアバターを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">メディアタイプ</td> 
   <td>生成されたビデオの出力メディアタイプを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">幅</td> 
   <td>生成されたビデオの幅を入力またはマッピングします。</td> 
  </tr>
  <tr> 
   <td role="rowheader">高さ</td> 
   <td>生成されたビデオの高さを入力またはマッピングします。</td> 
  </tr>
  <tr> 
   <td role="rowheader">背景</td> 
   <td>生成されたビデオに使用する背景のタイプを選択します。
   <ul>
   <li><b> ビデオ </b>：背景ビデオのURLを入力またはマッピングします。</li> 
   <li><b>画像</b>：背景画像のURLを入力またはマッピングします。</li>
   <li><b> カラー</b>: ビデオの背景に使用するカラーの16進値を入力またはマッピングします。</li> 
   </ul>
   </td>
  </tr>
 </tbody> 
</table>

#### テキストから音声を生成

このアクションモジュールは、トランスクリプトから音声を生成する。 プレーンテキストのトランスクリプトまたは事前署名されたURLを指定できます。 応答には、ジョブ IDと、ジョブを追跡するためのステータス URLが含まれます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">スクリプト</td> 
   <td>提供するスクリプトのタイプを選択します。
   <ul>
   <li><b> テキスト </b>：ソーステキストをテキストフィールドに入力またはマッピングします。</li>
   <li><b> テキストファイル </b>: URL フィールドにテキストファイルのURLを入力するか、マッピングします。</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">ロケールコード</td> 
   <td>結果で使用する言語を表すロケールコードを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">メディアタイプ</td> 
   <td>これは<code>text/plain</code>である必要があります。</td> 
  </tr>
  <tr> 
   <td role="rowheader">音声</td> 
   <td>使用する音声を選択します。 使用可能な音声は、Adobe Fireflyの音声カタログから入手できます。</td> 
  </tr>
  <tr> 
   <td role="rowheader">出力</td> 
   <td>これは<code>audio/wav</code>である必要があります。</td> 
  </tr>
 </tbody> 
</table>

#### ビデオをリフレーム

このモジュールは、指定したメディアをリフレームします。 メディアは、事前に署名されたURLを介して提供されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">事前定義済みURL</td> 
   <td>モジュールが入力に使用する事前署名済みURLを入力またはマッピングします。<p>メディアストレージ用の次のドメインは、Firefly Audio and Videoで受け入れられます</p>
   <ul>
   <li>adobe.io</li>
   <li>frame.io</li>
   <li>amazonaws.com</li>
   <li>windows.net</li>
   <li>dropboxusercontent.com</li>
   <li>drive.google.com</li>
   <li>cloudfront.net</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">シーン編集の検出</td> 
   <td>リフレームする前にシーン編集検出を適用するかどうかを選択します。 </td> 
  </tr>
  <tr> 
   <td role="rowheader">焦点</td> 
   <td>追加する各焦点について、<b>項目を追加</b>をクリックし、焦点のキーワード識別子を入力します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">オーバーレイ</td> 
   <td>追加する各オーバーレイについて、<b>項目を追加</b>をクリックし、オーバーレイ情報を入力します。
   <ul>
   <li><b>Source</b>: ソース メディアを指すURLを入力するか、マッピングします。</li> 
   <li><b>開始時間</b>：開始時間を入力するか、マッピングします。</li>
   <li><b>期間</b>: オーバーレイの期間を入力するか、マッピングします。</li> 
   <li><b>幅</b>：拡大/縮小されたオーバーレイの幅を入力またはマッピングします。</li> 
   <li><b>高さ</b>：拡大・縮小されたオーバーレイの高さを入力またはマッピングします。</li> 
   <li><b> アンカーポイント </b>: オーバーレイのアンカーポイントを選択します。</li> 
   <li><b> オフセット X</b>: オーバーレイの水平オフセットを入力またはマッピングします。</li> 
   <li><b> オフセット Y</b>: オーバーレイの垂直オフセットを入力またはマッピングします。</li> 
   <li><b>繰り返し</b>: <code>loop</code>と入力すると、GIFがループします。</li> 
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">メディアフォーマット</td> 
   <td>リフレームされたビデオの形式を選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">サイドカー形式</td> 
   <td>追加のメタデータの形式を選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">レンダリング</td> 
   <td>レンディションを追加するには、<b>項目を追加</b>をクリックし、レンディション情報を入力します。<!--add additional info--></td> 
  </tr>
 </tbody> 
</table>

#### レンダーテンプレート

このモジュールは、オーバーライドと書き出しプリセットを適用して、1つまたは複数のビデオバリエーションをレンダリングします。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">入力テンプレートファイル URL</td> 
   <td>レンダリングするテンプレートを表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr>
  <tr> 
   <td role="rowheader">フォント</td> 
   <td>追加する各フォントについて、<b>項目を追加</b>をクリックし、フォントのPostscript名とフォントファイルのURLを入力します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">フォントがない場合</td> 
   <td>レンダリングを失敗させるか、フォントが見つからない場合はデフォルトのフォントを使用するかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">メディアアセット</td> 
   <td>追加する各メディアアセットについて、<b>項目を追加</b>をクリックし、アセットを表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr>
  <tr> 
   <td role="rowheader">プリセットの書き出し</td> 
   <td>追加する各エクスポートプリセットについて、<b>項目を追加</b>をクリックしてビデオプリセットを選択し、プリセットを表す事前署名済みURLを入力またはマッピングします。</td> 
  </tr>
  <tr> 
   <td role="rowheader">バリエーション</td> 
   <td>追加する各バリエーションについて、<b>項目を追加</b>をクリックし、バリエーションの詳細を入力します。 少なくとも1つのバリエーションの詳細を入力する必要があります。<!--add data here--></td> 
  </tr>
  <tr> 
   <td role="rowheader">出力定義</td> 
   <td><b>項目を追加</b>をクリックし、追加したバリエーションとプリセットのいずれかを選択してファイル名を追加することで、出力を定義します。 バリエーションとプリセットは0にインデックス付けされます（バリエーションのリストの最初の項目は0、次は1など）。</td> 
  </tr>
 </tbody> 
</table>

#### 文字起こし

このモジュールは、オーディオまたはビデオを文字起こしします。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Fireflyへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Adobe Fireflyへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">文字起こしタイプ</td> 
   <td>音声と動画のどちらを書き起こすかを選択します。   </td> 
  </tr>
  <tr> 
   <td role="rowheader">事前定義済みURL</td> 
   <td>モジュールが入力に使用する事前署名済みURLを入力またはマッピングします。   </td> 
  </tr>
  <tr> 
  </tr>
   <td role="rowheader">メディアタイプ </td> 
   <td>入力ファイルのメディアタイプを選択</td> 
  </tr>
  <tr> 
   <td role="rowheader">ターゲットロケールコード</td> 
   <td>追加する各ロケールコードについて、<b>項目を追加</b>をクリックし、結果で使用する言語を表すロケールコードを選択します。</td> 
  <tr> 
   <td role="rowheader">キャプションフォーマット</td> 
   <td>キャプションを含めるには<code>SRT</code>と入力します。キャプションが必要ない場合は空白のままにします。</td> 
  </tr>
 </tbody> 
</table>



