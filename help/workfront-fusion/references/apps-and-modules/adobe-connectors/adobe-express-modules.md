---
title: Adobe Expressモジュール
description: Adobe Workfront Fusionでは、Adobe Expressを使用してワークフローを自動化できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: eab04db9a38020ed973f98d7f8f290ccd183251c
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 18%

---

# Adobe Expressモジュール

Adobe Workfront Fusionでは、Adobe Expressを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

Adobe Express コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブなAdobe Express アカウントが必要です。

## Adobe Expressへの接続の作成

Adobe Express モジュールの接続を作成するには、次の手順を実行します。

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


## Adobe Express モジュールとそのフィールド

Adobe Express モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Adobe Expressの追加フィールドが表示されることがあります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

#### レンディションの書き出し

このモジュールは、文書をJPGまたはPNG形式で書き出します。 4時間有効なページレンディション用の事前署名済みURLを提供できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Expressへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Adobe Expressへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドキュメント</td> 
   <td>レンディションを書き出すドキュメントを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">ページ番号</td> 
   <td>レンディションに含めるページ番号を入力またはマッピングします。 レンディション要求が行われるページ番号をコンマ区切りの文字列で示します。 例えば、「1,2,3」のように指定します。 ページ範囲も指定できます。 例えば、「1-3」には、ページ 1、2、3が含まれます。 もう1つの例は「1,3-5」で、ページ 1、3、4、5が含まれます。 「1 – 」はすべてのページを指定するのに使用でき、「5 – 」は最後のページの5 ページを示します。 指定しない場合、最初のページはデフォルトで考慮されます。 ページ番号は1から始まります。</td> 
  </tr>
  <tr> 
   <td role="rowheader">レンディションタイプ</td> 
   <td>書き出すレンディションの種類（画像、ビデオ、PDF）を選択します</td> 
  </tr>
  <tr> 
   <td role="rowheader">形式</td> 
   <td>レンディションのファイル形式を選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">PDF type</td> 
   <td>PDFを書き出す場合は、標準PDFを書き出すか、を印刷するかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">サイズ</td> 
   <td>画像またはビデオを書き出す場合は、最も長い辺のサイズをピクセル単位で入力またはマッピングします。 縦横比は維持されます。 画像の場合、サポートされる最小サイズは1 pxで、サポートされる最大サイズは8192 pxです。 指定しない場合は、デフォルトのページサイズが考慮されます。</td> 
  </tr>
  <tr> 
   <td role="rowheader">個々のPDF ファイルのダウンロード</td> 
   <td>PDFを書き出す場合は、ページを個別のPDF ファイルとしてダウンロードするかどうかを選択します。 trueの場合、各ページは独自のPDF ファイルとしてダウンロードされます。 falseの場合、すべてのページが1つのPDF ファイルに結合されます。</td> 
  </tr>
  <tr> 
   <td role="rowheader">構成</td> 
   <td>PDFを書き出す場合は、PDFを標準設定と印刷設定のどちらにするかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">アクセシビリティステージ</td> 
   <td>標準のPDFを書き出す場合は、PDFにアクセシビリティタグを含めるかどうかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">裁ち落とし</td> 
   <td>印刷PDFを書き出す場合は、書き出しに裁ち落としを含めるかどうかを選択します</td> 
  </tr>
  <tr> 
   <td role="rowheader">裁ち落とし設定/量</td> 
   <td>裁ち落としマージンの量を入力します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">裁ち落とし設定/単位</td> 
   <td>量がインチまたはミリメートルのどちらを指しているかを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">切り抜き</td> 
   <td>印刷PDFを書き出す場合は、書き出しに切り抜き設定を含めるかどうかを選択します</td> 
  </tr>
  <tr> 
   <td role="rowheader">切り抜き設定/量</td> 
   <td>切り抜き余白の量を入力します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">切り抜き設定/単位</td> 
   <td>量がインチまたはミリメートルのどちらを指しているかを選択します。</td> 
  </tr>
 </tbody> 
</table>

#### バリエーションの生成

このモジュールは、指定された入力パラメーターに基づいてドキュメントのバリエーションを作成します。 処理後、生成された文書は一時的に保存され、指定されたフォルダー内でユーザーが利用できるようになります。 文書は30日間アクセスできます。その後、システムは自動的にそれを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Expressへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Adobe Expressへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドキュメント</td> 
   <td>バリエーションを生成するドキュメントを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">ページ番号</td> 
   <td>レンディションに含めるページ番号を入力またはマッピングします。 バリエーションのリクエストを行うページ番号をコンマ区切りの文字列で指定します。 例えば、「1,2,3」のように指定します。 ページ範囲も指定できます。 例えば、「1-3」には、ページ 1、2、3が含まれます。 もう1つの例は「1,3-5」で、ページ 1、3、4、5が含まれます。 「1 – 」はすべてのページを指定するのに使用でき、「5 – 」は最後のページの5 ページを示します。 指定しない場合、最初のページはデフォルトで考慮されます。 ページ番号は1から始まります。</td> 
  </tr>
  <tr> 
   <td role="rowheader">優先ドキュメント名。</td> 
   <td>新しい文書の名前を入力またはマッピングします。 名前を指定しない場合、または名前が既に使用されている場合、システムは一意の名前を生成します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">プロジェクト ID</td> 
   <td>バリエーションを保存するプロジェクトのIDを入力します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td>他のフィールドの値を入力します。 使用可能なフィールドは、選択した文書に基づいています。</td> 
  </tr>
 </tbody> 
</table>


### 検索

#### タグ付きドキュメントの取得

このモジュールは、タグ付きドキュメントのリストと関連するメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Expressへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Adobe Expressへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">索引を開始</td> 
   <td>ページネーション開始インデックスを入力またはマッピングします。 このオプションは、結果の別のリストを取得し、そのリストを続行する場合に使用します。 デフォルトのインデックスは0です。</td> 
  </tr>
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>実行サイクルごとにモジュールが返す結果の最大数を入力またはマッピングします。</td> 
  </tr>
  <tr> 
   <td role="rowheader">並べ替え基準</td> 
   <td>結果を並べ替える属性を選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">方向</td> 
   <td>結果を昇順または降順に並べ替えるかどうかを選択します。</td> 
  </tr>
 </tbody> 
</table>

#### ドキュメントの詳細を取得

このモジュールは、指定された文書内のページとタグ付き要素の詳細を取得します。 ドキュメントのページと各ページに関するメタデータのページ付きリストを返します。 ドキュメントにタグ付けされた要素がある場合、APIにはサイズや位置などの詳細情報が含まれます。 ドキュメントにタグ付けされた要素がない場合は、空の配列が返されます。 応答には、ユーザーがドキュメントのページをナビゲートするのに役立つページ化情報が含まれます。 1 サイクルで最大10 ページを返すことができます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Expressへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Adobe Expressへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドキュメント</td> 
   <td>ページと詳細を返すドキュメントを選択します。</td> 
  </tr>
  <tr> 
   <td role="rowheader">開始ページ</td> 
   <td>詳細を取得する最初のページのページ番号を入力またはマッピングします。</td>

#### ジョブのステータスの取得

このモジュールは、ジョブ IDによってジョブのステータスを取得します。 ジョブのタイプに応じて、応答にはジョブ固有の詳細が含まれる場合があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Expressへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >Adobe Expressへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ジョブ ID</td> 
   <td>詳細を取得するジョブのIDを入力またはマッピングします。</td> 
  </tr>

