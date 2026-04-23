---
title: Adobe Substance モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Adobe Substance] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: 85e2e832-0347-4270-b360-4a07224f2bcc
source-git-commit: 72abd9b5aa73d54edd73dc16f7695d2b01cc8624
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 36%

---

# [!DNL Adobe Substance] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Adobe Substance] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

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

[!DNL Adobe Substance] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!DNL Adobe Substance] アカウントが必要です。



## [!DNL Adobe Substance] モジュールとそのフィールド

[!DNL Adobe Substance] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Substance]」フィールドが表示される場合があります。モジュール内のフィールド名の横にアスタリスク記号が表示されている場合は、必須フィールドを示しています。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [合成](#composites)
* [シーン](#scenes)
* [スペース](#spaces)

### 合成

#### 3D オブジェクト合成を生成

このアクションモジュールは、選択したヒーローアセットを含む3D コンポジットのコンテンツを生成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td>必要に応じて他のフィールドを設定します。 フィールドについて詳しくは、<a href="https://s3d.adobe.io/docs#/operations/v1/composites/compose">Adobe Substance API ドキュメント </a>を参照してください。</td> 
  </tr> 
  <!--
  <tr>
   <td role="rowheader">Camera name</td> 
   <td>Enter or map the name of an existing camera that has been previously defined in the source 3D file.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Content class</td> 
   <td>Select whether you want the composite to have the style of art or of a photo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Enable ground plane</td> 
   <td>Enable this to enable the auto-generated ground plane under the hero asset. This is useful if the 3D scene contains only a hero asset, without additional elements.</td> 
  </tr>
  -->
 </tbody> 
</table>

### シーン

* [3D ファイルを変換](#convert-3d-files)
* [3D シーンを作成](#create-3d-scene)
* [3D シーンを記述](#describe-3d-scene)
* [3D オブジェクトをレンダリング](#render-3d-object)
* [3D オブジェクトのレンダリング（基本バージョン）](#render-3d-object-basic-version)

#### 3D ファイルを変換

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">形式</td> 
   <td>ファイルを変換する形式を選択します。</td> 
  </tr> 
<tr> 
   <td role="rowheader">モデルのエントリポイント</td> 
   <td>変換は通常、有効な3D モデルと見なされる最初のファイルを取ります。 複数のオプションがある場合に、このエントリポイントを定義して曖昧さを排除します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ソース</td> 
   <td>変換する各ファイルについて、<b> 「項目を追加</b>」をクリックし、ファイル情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### 3D シーンを作成

このアクションモジュールは、指定したアセットを使用してシーンを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <td role="rowheader">エンコード</td> 
   <td>シーンのファイルタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ファイルベース名</td> 
   <td>出力ファイルの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td>必要に応じて他のフィールドを設定します。 フィールドについて詳しくは、<a href="https://s3d.adobe.io/docs#/operations/v1/scenes/assemble">Adobe Substance API ドキュメント </a>を参照してください。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">ソース</td> 
   <td>使用する各ファイルについて、「<b> アイテムを追加</b>」をクリックし、ファイル情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### 3D シーンを記述

このアクション モジュールは、3D シーン コンテンツに関する情報を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <td role="rowheader">シーンファイル</td> 
   <td>説明するシーン ファイルにパスを入力またはマッピングします。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">ソース</td> 
   <td>記述する各ファイルについて、<b> 「項目を追加</b>」をクリックし、ファイル情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### 3D オブジェクトをレンダリング

このアクションモジュールは、シーンの画像をレンダリングします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
   <td role="rowheader">その他のフィールド</td> 
   <td>必要に応じて他のフィールドを設定します。 フィールドについて詳しくは、<a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render">Adobe Substance API ドキュメント </a>を参照してください。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">ソース</td> 
   <td>使用する各ファイルについて、「<b> アイテムを追加</b>」をクリックし、ファイル情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### 3D オブジェクトのレンダリング（基本バージョン）

このアクションモジュールは、シーンの画像をレンダリングしますが、3D オブジェクトモジュールをレンダリングするオプションは少なくなります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
   <td role="rowheader">その他のフィールド</td> 
   <td>必要に応じて他のフィールドを設定します。 フィールドについて詳しくは、<a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render-basic">Adobe Substance API ドキュメント </a>を参照してください。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">ソース</td> 
   <td>使用する各ファイルについて、「<b> アイテムを追加</b>」をクリックし、ファイル情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

### スペース

#### スペースを作成

このアクションモジュールを使用すると、ファイルをアップロードして一時的に保存できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Adobe Substance] アカウントをWorkfront Fusionに接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusionへの接続の作成 – 基本手順</a>を参照してください。</p> </td> 
  </tr> 
   <td role="rowheader">ファイル名</td> 
   <td>アップロードするファイルの名前を入力またはマッピングします。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">ファイルデータ</td> 
   <td>ファイルのバイナリデータを入力またはマッピングします。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">名前</td> 
   <td>マルチパートフォーム値の名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
