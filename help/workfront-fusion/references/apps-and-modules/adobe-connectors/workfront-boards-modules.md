---
title: Adobe Workfront Boardsのモジュール
description: Adobe Workfront Boards コネクタを使用すると、Workfront Boards内のプロセスを自動化し、サードパーティのアプリケーションやサービスに接続できます。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: dcc5044d-8fdf-4a74-b664-e965e714ce92
TQID: https://experienceleague.adobe.com/0yHy2mMpsOxPH-cphARzE3LmIlAmYLNQTpXxFgb6dvo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 2906
ht-degree: 20%

---

# Adobe Workfront Boardsのモジュール

>[!NOTE]
>
>Boards Fusion コネクタはベータ版です。 その結果、このコネクタのサポートは限定的であり、ボードの将来の開発によって変更される可能性があります。 さらに、Fusion コネクタのプロセスに影響を与える可能性のある、GraphQL APIへの変更が予告なく行われる場合があります。

Adobe Workfront ボードは、列やカードを含む共有ボードへのアクセスを提供することで、チームの共同作業を可能にする柔軟なツールです。

Adobe Workfront Boards モジュールを使用すると、レコードの読み取りまたは更新、Workfront Boards APIへのAPI呼び出し、またはボード上でアクションが発生したときにシナリオをトリガーできます。

<!--For general information on Workfront Boards, see [Boards overview](/help/quicksilver/agile/boards-overview.md).-->

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

## 前提条件

Adobe Workfrontで掲示板を設定してから、掲示板に接続する必要があります。

## Adobe Workfront Boards APIの情報

Adobe Workfront Boards コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.23.6</td> 
  </tr>
 </tbody> 
 </table>

## Workfront ボードへの接続の作成

>[!NOTE]
>
>Workfront接続を使用してWorkfront ボードに接続したり、別のWorkfront ボード接続を作成したりできます。

Workfront ボード接続を作成するには：

1. 任意の [!DNL Adobe Workfront Boards] モジュールで、「接続」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。

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
          <td role="rowheader">[!UICONTROL Client ID]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]<p>（オプション）</p></td>
          <td>Workfrontのインスタンスがこの接続の認証に使用するURLを入力します。 <p>デフォルト値は <code>https://oauth.my.workfront.com/integrations/oauth2</code> です。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>ホストの接頭辞を入力します。<p>デフォルト値は <code>origin-</code> です。</p>
        </tr>
      </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## Adobe Workfront ボードのモジュールとそのフィールド

Workfront Boards モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Workfront ボードのフィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [カード](#cards)
* [ボード](#boards)
* [列](#columns)
* [タグ](#tags)
* [コメント](#comments)
* [その他](#other)

### カード

* [チェックリスト項目を追加](#add-checklist-item)
* [サブタスクを追加](#add-subtask)
* [カードの作成](#create-a-card)
* [カードを移動](#move-a-card)
* [カードを読む](#read-a-card)
* [カードの更新](#update-a-card)

#### チェックリスト項目を追加

このアクションモジュールは、指定したカードにチェックリスト項目を追加します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>チェックリスト項目を追加するカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL チェックリスト項目]</td> 
   <td>追加する各チェックリスト項目について、「項目を追加」をクリックし、チェックリスト項目の名前を入力して、項目が完了したかどうかを選択します。</p></td> 
  </tr> 
 </tbody> 
</table>

#### サブタスクを追加

このアクションモジュールは、ボードのカードにサブタスクを追加します。 カードは接続されたカードである必要があります。 サブタスクは、カードが表すWorkfront タスクにも追加されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 親カード ID]</td> 
   <td>サブタスクを追加するカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>サブタスクを追加するカードを含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>新しいサブタスクの名前を入力またはマッピングします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードの作成

このアクションモジュールは、Workfront ボード上に新しいカードを作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>カードを追加するボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列ID]</td> 
   <td>サブタスクを追加する列のIDを入力またはマッピングします。<p>列IDは、ボードを読み取りモジュールから返される情報で確認できます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>新しいカードの名前を入力またはマッピングします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードを移動

このアクションモジュールは、カードを同じボード上の別の列に移動します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>移動するカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>移動するカードを含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination column ID]</td> 
   <td>カードを移動する列のIDを入力またはマッピングします。<p>列IDは、ボードを読み取りモジュールから返される情報で確認できます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To index]</td> 
   <td>カードの新しい列の位置を入力またはマッピングします。<p>インデックス 0の列の一番上の位置。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードを読む

このアクションモジュールは、特定のカードに関する情報を取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>読み取りたいカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>読み取りたいカードを含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードの更新

このアクションモジュールは、指定したカードの情報を更新します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>更新するカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>更新するカードを含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>カードの新しい名前を入力またはマッピングします。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>カードの新しい説明を入力またはマッピングします。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Estimation]</td> 
   <td>このカードを完了するために必要な時間の見積もりを入力またはマッピングします。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Due date]</td> 
   <td>このカードの期日を入力またはマッピングします。</p>
   <p>サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</p>
   </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Status]</td> 
   <td>カードの新しいステータスを選択します。</p></td> 
  </tr> 
 </tbody> 
</table>

### ボード

* [ボードの作成](#create-a-board)
* [ボードを読む](#read-a-board)

#### ボードの作成

このアクションモジュールは、Workfrontでボードを作成します。 作成するボードのタイプを指定できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ボード名]</td> 
   <td>新しいボードの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Template]</td> 
   <td>作成するボードの種類のテンプレートを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ボードを読む

このアクションモジュールは、ボードのカード、列、タグ、メンバーなど、1つのボードに関する情報を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>情報を取得するボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
 </tbody> 
</table>

### 列

* [列の作成](#create-a-column)
* [列の検索](#search-for-a-column)
* [列の更新](#update-a-column)

#### 列の作成

このアクションモジュールは、指定したボードに新しい列を作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>列を追加するボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列ID]</td> 
   <td>更新する列のIDを入力またはマッピングします。<p>列IDは、ボードを読み取りモジュールから返される情報で確認できます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列名]</td> 
   <td>列の新しい名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 列の検索

この検索モジュールは、指定した名前の列に関する情報を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>取得する列を含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列名]</td> 
   <td>取得する列の名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 列の更新

このアクション モジュールは、指定された列の名前またはWIP制限を更新します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>取得する列を含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列名]</td> 
   <td>取得する列の名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL WIP Limit]</td> 
   <td>列の新しいWIP制限を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### タグ

* [カードにタグを追加](#add-a-tag-to-a-card)
* [タグの作成](#create-a-tag)

#### カードにタグを追加

このアクションモジュールは、カードにタグを追加します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>タグを追加するカードのIDを入力するか、マッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>タグを追加するカードを含むボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag ID]</td> 
   <td>追加するタグのIDを入力またはマッピングします。<p>タグ IDは、ボードを読み取りモジュールから返される情報で確認できます。</p></td> 
  </tr> 
 </tbody> 
</table>

#### タグの作成

このアクションモジュールは、新しいタグを作成し、色を割り当てます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>タグを作成するボードのIDを入力またはマッピングします。<p>Workfrontで掲示板を表示すると、URLに掲示板IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL タグ名]</td> 
   <td>新しいタグの名前を入力するか、マッピングします。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL タグカラー]</td> 
   <td>このタグのカラーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### コメント

* [コメントを作成](#create-a-comment)
* [カードのコメントを読む](#read-card-comments)

#### コメントを作成

このアクションモジュールは、指定したカードにコメントを作成しました。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>コメントを追加するカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>追加するコメントのテキストを入力またはマッピングします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードのコメントを読む

このアクションモジュールは、指定したカードからコメントを取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>コメントを取得するカードのIDを入力またはマッピングします。<p>Workfrontでカードを表示すると、URLにカード IDが表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>1回の実行サイクルでモジュールに返すコメントの最大数を入力します。</p></td> 
  </tr> 
 </tbody> 
</table>

### その他

#### カスタム API 呼び出しの実行

このアクションモジュールは、Workfront Boards APIをカスタム呼び出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p><code> https://&lt;WORKFRONT_DOMAIN&gt;/boards-service/graphql?</code> への相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p><p>ほとんどのボードでは、メソッドはPOSTです。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。 これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> { "Content-type":"application/json-stringify()"}</code></p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>Workfront ボードの場合、通常、このセクションは空のままになります。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>JSON埋め込みGraphql形式のAPI呼び出しの本文コンテンツを追加します </p> <p>例：</p><p>次の使用例は、列名を更新します。 <code>boardId</code>と<code>columnId</code>は、ハードコードされているか、以前のモジュールからマッピングされているGUIDとして含めることができます。<p><pre>{<br> "query": "mutation { updateColumn （boardId: \"\", columnId: \"\", updateColumnInput: { name: \"\" }） { id name }}"<br>}</pre><p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


#### カスタム GraphQL API呼び出しを行う

このアクションモジュールは、Workfront Boards APIに対してカスタム GraphQL リクエストを行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront ボードに接続したり、特定のWorkfront ボード接続を使用したりできます。 </p><p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成</a>」を参照してください。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>この呼び出しのメソッドを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 操作名]</td> 
   <td> <p>この操作の名前を入力します。 これにより、呼び出しの追跡とデバッグが簡単になります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variables data source]</td> 
   <td> <p>変数がフォームからのものか、コレクションからのものかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variables]</td> 
   <td> <p>追加する各変数について、<b>項目を追加</b>をクリックし、変数のキーと値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
   </tr> 
 </tbody> 
</table>
