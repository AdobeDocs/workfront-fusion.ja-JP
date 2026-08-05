---
title: Adobe Content Tagger modules
description: Adobe Workfront Fusionでは、Adobe Content Taggerを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: 801e8cb1a4c807aaa4275382c2d6211cf3cd6d1f
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 20%

---

# Adobe Content Tagger modules

Adobe Workfront Fusionでは、Adobe Content Taggerを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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
   <p>オペレーションベース：オペレーションベースのライセンスを持つ組織で使用できます</p>
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

## Adobe Content Taggerへの接続の作成

Adobe Content Tagger モジュールの接続を作成するには、次の手順を実行します。

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


## Adobe Content Tagger モジュールとそのフィールド

Adobe Content Tagger モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Adobe Content Taggerの追加フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

* [カラーのタグ付け](#tag-colors)
* [タグキーワード](#tag-keywords)
* [画像内のテキストへのタグ付け](#tag-text-in-an-image)

#### カラーのタグ付け

このモジュールは、異なるピクセルカラーでカバーされている画像の割合を40のカラーカテゴリーにソートして返します。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Content Taggerへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >Adobe Content Taggerへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像ファイル名</td> 
   <td>カラーをタグ付けする画像のファイル名を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像データ</td> 
   <td>カラーをタグ付けする画像のファイルデータを入力またはマッピングします。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">画像フォーマット</td> 
    <td>カラーをタグ付けする画像の画像タイプを選択します。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">カラー数</td> 
    <td>返すカラー数を入力またはマッピングします。 すべての結果を返すには、0と入力します。</p></td> 
  </tr> 
 <tr> 
   <td role="rowheader">最小カバレッジ</td> 
   <td>カラーをタグ付けする最小カバレッジを入力またはマッピングします。 少なくともこの量の画像をカバーするカラーのみが返されます。 値1は画像の100%で、値0.5は画像の50%を表します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">抽出前に画像のサイズを変更します。</td> 
   <td>「はい」を選択して、画像のサイズを320 x 320に変更してからカラーを抽出します。 「いいえ」を選択して、フルサイズ画像からカラーを抽出します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">前景/背景マスクを有効にする</td> 
   <td>画像全体、前景、背景のカラーを個別にレポートする場合は、「はい」を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トーンの取得</td> 
   <td>カラーに加えて、暖色系、中立系、寒色系のトーンに関するデータを取得する場合は、「はい」を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返されるカラーの最大数</td> 
   <td>1回の実行サイクルで返されるモジュールの最大色数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>



#### タグキーワード

このモジュールは、ドキュメントの件名を最もよく表すキーワードまたはキーフレーズを抽出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Content Taggerへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >Adobe Content Taggerへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">文書ファイル名</td> 
   <td>キーワードを抽出するドキュメントのファイル名を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像データ</td> 
   <td>キーワードを抽出するドキュメントのファイルデータを入力するか、マッピングします。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">画像フォーマット</td> 
    <td>キーワードを抽出するドキュメントの形式を選択します。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">アプリケーション ID</td> 
   <td>ドキュメントのアプリケーション IDを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">キーフレーズの数</td> 
   <td>モジュールに返すキーフレーズの数を入力またはマッピングします。 すべての結果を返すには、0と入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">関連性の最小化</td> 
   <td>結果を返さないスコアしきい値を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">キーフレーズの最小長（単語）</td> 
   <td>キーフレーズに必要な最小単語数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">キーフレーズの最大長（単語）</td> 
   <td>キーフレーズに必要な最大単語数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">セマンティック単位深度</td> 
   <td>階層的な応答をどの程度の深さで行うかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">エンティティタイプ</td> 
   <td>キーフレーズを制限する各エンティティタイプについて、<b>項目を追加</b>をクリックし、エンティティタイプの情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### 画像内のテキストへのタグ付け

このモジュールは、画像にテキストが存在するかどうかを示し、存在する場合はテキストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe Content Taggerへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >Adobe Content Taggerへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像ファイル名</td> 
   <td>テキストを抽出する文書のファイル名を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">画像データ</td> 
   <td>テキストを抽出する文書のファイルデータを入力するか、マッピングします。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">画像フォーマット</td> 
    <td>テキストを抽出する文書の形式を選択します。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">辞書でフィルター</td> 
   <td>英語の辞書にある単語のみを返すかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">最小確率</td> 
   <td>最小確率を入力またはマッピングします。モジュールは、少なくともこれだけの確率で認識された単語のみを返します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">最小関連性</td> 
   <td>返されるテキストがカバーする画像の最小パーセントを入力します。 関連性は、抽出されたテキストのバウンディングボックスの領域の割合として、画像全体に対する割合として計算されます。 0.01は、画像の少なくとも1%を占めるテキストに変換されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>1回の実行サイクルでモジュールが返す結果の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
