---
title: Workfront Fusion モジュール
description: Workfront Fusion コネクタを使用すると、レコード、フック、シナリオ、接続などのシナリオ内から独自のFusionの編成を管理できます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 1665553df806ba49ee9b52199fdcc587a5bb6337
workflow-type: tm+mt
source-wordcount: 1374
ht-degree: 25%

---

# Workfront Fusion モジュール

Workfront Fusion コネクタを使用すると、シナリオ内から独自のFusion組織を管理できます。 Fusionをサードパーティのアプリまたはサービスに接続する他のコネクタとは異なり、このコネクタは、シナリオがAdobe Workfront コネクタでWorkfrontを管理する方法と同様に、Fusion独自のAPIを呼び出すことができます。

シナリオの作成手順について詳しくは、[シナリオの作成：記事のインデックス](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## Workfront FusionとWorkfront Fusionの連携

1. 任意のWorkfront Fusion モジュールで、Connection フィールドの横にある&#x200B;**[!UICONTROL Add]**&#x200B;をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection type]</td> 
      <td>作成する接続のタイプを選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td>接続に名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client ID]</td> 
      <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。 これは、[!DNL Adobe Developer Console]の[!UICONTROL Credentials]の詳細セクションにあります。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Client Secret]</td> 
      <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、[!DNL Adobe Developer Console]の[!UICONTROL Credentials]の詳細セクションにあります。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Organization ID]</td> 
      <td>[!DNL Adobe] IMS組織IDを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Region]</td> 
      <td>この接続のFusion領域を選択します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## Workfront Fusion モジュールとそのフィールド

Workfront Fusion モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [書き出し](#export)
* [その他](#misc)

### アクション

* [レコードの複製](#clone-a-record)
* [レコードの作成](#create-a-record)
* [レコードの削除](#delete-a-record)
* [レコードのリスト](#list-records)
* [レコードの読み取り](#read-a-record)
* [レコードの更新](#update-a-record)

#### レコードの複製

このモジュールは、指定されたレコードのコピーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> 複製するレコードタイプを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">シナリオ ID</td> 
   <td> 複製するシナリオのIDを入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">名前</td> 
   <td> 新しいシナリオの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードの作成

このモジュールは、指定されたデータを含むレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> 作成するレコードのタイプを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">チーム ID</td> 
   <td> このレコードを所有するチームのIDを入力するか、マッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">名前</td> 
   <td> 新しいレコードの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードの削除

このモジュールは、指定されたレコードを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> 削除するレコードのタイプを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td>他のフィールドの値を入力します。 使用可能なフィールドは、選択したレコードタイプによって異なります。 </td> 
  </tr> 
 </tbody> 
</table>

#### レコードのリスト

このモジュールは、カーソルベースのページングフィルターとプロパティフィルターを使用して、ページ化されたレコードのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td>リストを返すレコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロパティ</td> 
   <td>結果を返す各プロパティフィルターについて、<b>項目を追加</b>をクリックし、フィルターするフィールド、演算子、値を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始</td> 
   <td>返された結果を開始する場所を入力します。 これはページネーションに使用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>実行サイクルごとにモジュールが返す最大レコード数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">次で注文</td> 
   <td>結果を並べ替えるフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方向</td> 
   <td>結果を昇順と降順のどちらで注文するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードの読み取り

このモジュールは、指定されたレコードを取得します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> 削除するレコードのタイプを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">その他のフィールド</td> 
   <td>他のフィールドの値を入力します。 使用可能なフィールドは、選択したレコードタイプによって異なります。 </td> 
  </tr> 
 </tbody> 
</table>

#### レコードの更新

指定したレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> 更新するレコードのタイプを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">名前</td> 
   <td> レコードの新しい名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID</td> 
   <td> 更新するレコードの ID を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

### 書き出し

#### アクティビティログの書き出し

このモジュールは、アクティビティログを書き出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ファイルタイプ</td> 
   <td>ログを書き出すファイル形式を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロパティ</td> 
   <td>結果を返す各プロパティフィルターについて、<b>項目を追加</b>をクリックし、フィルターするフィールド、演算子、値を入力します。 フィールドが存在するかどうかでフィルタリングすることもできます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始</td> 
   <td>返された結果を開始する場所を入力します。 これはページネーションに使用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>実行サイクルごとにモジュールが返す最大レコード数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">次で注文</td> 
   <td>結果を並べ替えるフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方向</td> 
   <td>結果を昇順と降順のどちらで注文するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### その他

* [フックのキュー統計を取得](#get-queue-statistics-for-a-hook)
* [レコードの依存関係を取得](#get-record-dependencies)
* [接続のシナリオのリスト](#list-scenarios-for-a-connection)
* [Adobe Workfront Fusionの地域と組織のリスト](#list-the-fusion-regions-and-organizations)

#### フックのキュー統計を取得

このモジュールは、指定されたフックのキュー統計を返します。現在キューに入っているイベントの数、キューの制限、フックが有効かどうかを示します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">フック ID</td> 
   <td> 詳細を返すフックのIDを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードの依存関係を取得

このモジュールは、レコードの依存関係を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> 依存関係を取得するレコードタイプを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">シナリオ ID</td> 
   <td> 依存関係を取得するレコードのIDを入力またはマッピングします。 </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### 接続のシナリオのリスト

このモジュールは、特定の接続を参照するページ分割されたシナリオのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">接続ID</td> 
   <td>シナリオを返す接続のIDを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロパティ</td> 
   <td>結果を返す各プロパティフィルターについて、<b>項目を追加</b>をクリックし、フィルターするフィールド、演算子、値を入力します。 フィールドが存在するかどうかでフィルタリングすることもできます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始</td> 
   <td>返された結果を開始する場所を入力します。 これはページネーションに使用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>実行サイクルごとにモジュールが返す最大レコード数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">次で注文</td> 
   <td>結果を並べ替えるフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方向</td> 
   <td>結果を昇順と降順のどちらで注文するかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### Adobe Workfront Fusionの地域と組織のリスト

このモジュールは、接続で使用される資格情報のIMS ユーザープロファイルの資格情報とアクセスに基づいて、接続がアクセスできるFusion組織ごとにリージョンと組織IDを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront FusionをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">Workfront FusionをWorkfront Fusionに接続</a>」を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

