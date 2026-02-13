---
title: Adobe Workfront基板モジュール
description: Adobe Workfront Boards コネクタを使用すると、Workfront Boards 内のプロセスを自動化し、サードパーティのアプリやサービスに接続できます。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: dcc5044d-8fdf-4a74-b664-e965e714ce92
source-git-commit: a871a130a1ac023dcb4ce8da7241918da2431d3a
workflow-type: tm+mt
source-wordcount: '2904'
ht-degree: 20%

---

# Adobe Workfront基板モジュール

>[!NOTE]
>
>Boards Fusion コネクタはベータ版ステータスです。 その結果、このコネクタのサポートは制限され、今後のボードの開発により変更される可能性があります。 また、Fusion コネクタプロセスに影響を与える可能性があるGraphQL API が、予告なく変更される場合があります。

Adobe Workfront ボードは、列やカードを含む共有ボードへのアクセスを提供することで、チームの共同作業を可能にする柔軟なツールです。

Adobe Workfront ボード モジュールを使用すると、レコードの読み取りや更新、Workfront ボード API への API 呼び出しを行ったり、ボードでアクションが発生した場合のシナリオのトリガーを設定したりできます。

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

ボードに接続するには、Adobe Workfrontでボードを設定しておく必要があります。

## Adobe Workfront ボード API 情報

Adobe Workfront ボードコネクタでは、以下を使用します。

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

## Workfront Boards への接続の作成

>[!NOTE]
>
>Workfront接続を使用してWorkfront Boards に接続するか、別のWorkfront Boards 接続を作成できます。

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
          <td>サービスアカウントに接続するか、個人アカウントに接続するかを選択します。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client ID] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>（オプション）</p></td>
          <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]<p>（オプション）</p></td>
          <td>Workfrontのインスタンスで、この接続の認証に使用する URL を入力します。 <p>デフォルト値は <code>https://oauth.my.workfront.com/integrations/oauth2</code> です。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>ホストのプレフィックスを入力します。<p>デフォルト値は <code>origin-</code> です。</p>
        </tr>
      </tbody>
    </table>
1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## Adobe Workfront Boards モジュールとそのフィールド

Workfront Fusion でWorkfront ボードモジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のWorkfront ボードフィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

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
* [カードの移動](#move-a-card)
* [カードを読み取る](#read-a-card)
* [カードの更新](#update-a-card)

#### チェックリスト項目を追加

このアクションモジュールは、指定されたカードにチェックリスト項目を追加します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>チェックリスト項目を追加するカードの ID を入力またはマッピングします<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL チェックリスト項目 &#x200B;]</td> 
   <td>追加するチェックリスト項目ごとに、「項目を追加」をクリックし、チェックリスト項目の名前を入力して、項目が完了したかどうかを選択します。</p></td> 
  </tr> 
 </tbody> 
</table>

#### サブタスクを追加

このアクションモジュールは、ボードのカードにサブタスクを追加します。 カードは接続されている必要があります。 サブタスクは、カードが表すWorkfront タスクにも追加されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 親カード ID]</td> 
   <td>サブタスクの追加先となるカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>サブタスクの追加先となるカードを含むボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>新しいサブタスクの名前を入力またはマッピングします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードの作成

Workfrontのボード上に新しいカードを作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>カードを追加するボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列 ID]</td> 
   <td>サブタスクを追加する列の ID を入力またはマッピングします。<p>列 ID は、ボードを読み取りモジュールから返される情報で見つけることができます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>新しいカードの名前を入力またはマッピングします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードの移動

このアクションモジュールは、カードを同じボード上の別の列に移動します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>移動するカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>移動するカードを含むボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 宛先列 ID]</td> 
   <td>カードの移動先の列の ID を入力またはマッピングします。<p>列 ID は、ボードを読み取りモジュールから返される情報で見つけることができます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL からインデックスへ &#x200B;]</td> 
   <td>新しい列にカードを配置する位置を入力またはマップします。<p>インデックス 0 の列の一番上の位置。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードを読み取る

このアクションモジュールは、特定のカードに関する情報を取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>読み取るカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>読み取るカードを含むボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
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
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>更新するカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>更新するカードを含むボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
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
   <td>このカードを完了するのに必要な推定時間を入力またはマップします。</p></td> 
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

* [ボードを作成](#create-a-board)
* [ボードを読み取る](#read-a-board)

#### ボードを作成

Workfrontにボードを作成します。 作成するボードのタイプを指定できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ボード名 &#x200B;]</td> 
   <td>新しいボードの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Template]</td> 
   <td>作成するボードのタイプに合ったテンプレートを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ボードを読み取る

このアクションモジュールは、ボードのカード、列、タグ、メンバーなど、1 つのボードに関する情報を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>情報を取得するボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
 </tbody> 
</table>

### 列

* [列の作成](#create-a-column)
* [列の検索](#search-for-a-column)
* [列の更新](#update-a-column)

#### 列の作成

このアクションモジュールは、指定されたボードに新しい列を作成します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>列を追加するボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列 ID]</td> 
   <td>更新する列の ID を入力またはマッピングします。<p>列 ID は、ボードを読み取りモジュールから返される情報で見つけることができます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列名 &#x200B;]</td> 
   <td>列の新しい名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 列の検索

この検索モジュールは、指定された名前を持つ列に関する情報を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>取得する列を含むボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列名 &#x200B;]</td> 
   <td>取得する列の名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 列の更新

このアクションモジュールは、指定された列の名前または WIP 制限を更新します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>取得する列を含むボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列名 &#x200B;]</td> 
   <td>取得する列の名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL の WIP 制限 &#x200B;]</td> 
   <td>列の新しい WIP 制限を入力またはマップします。</td> 
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
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>タグの追加先となるカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>タグの追加先となるカードを含んだボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag ID]</td> 
   <td>追加するタグの ID を入力またはマッピングします。<p>タグ ID は、ボードを読み取りモジュールから返される情報で見つけることができます。</p></td> 
  </tr> 
 </tbody> 
</table>

#### タグの作成

このアクションモジュールは、新しいタグを作成し、カラーを割り当てます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>タグを作成するボードの ID を入力またはマッピングします。<p>Workfrontでボードを表示する際に、URL にボード ID が含まれています。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL タグ名 &#x200B;]</td> 
   <td>新しいタグの名前を入力またはマッピングします。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL タグの色 &#x200B;]</td> 
   <td>このタグのカラーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### コメント

* [コメントの作成](#create-a-comment)
* [カードコメントを読む](#read-card-comments)

#### コメントの作成

このアクションモジュールは、指定されたカードにコメントを作成しました。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>コメントを追加するカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>追加するコメントのテキストを入力またはマップします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### カードコメントを読む

このアクションモジュールは、指定されたカードからコメントを取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>コメントを取得するカードの ID を入力またはマッピングします。<p>Workfrontでカードを表示すると、URL にカード ID が表示されます。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>1 回の実行サイクルでモジュールに返すコメントの最大数を入力します。</p></td> 
  </tr> 
 </tbody> 
</table>

### その他

#### カスタム API 呼び出しの実行

このアクションモジュールは、Workfront Boards API へのカスタム呼び出しを行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p><code> https://&lt;WORKFRONT_DOMAIN&gt;/boards-service/graphql?</code> への相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p><p>ほとんどのボードでは、メソッドは POST です。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> { "Content-type":"application/json-stringify()"}</code></p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>Workfront ボードの場合、このセクションは通常、空のままになります。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>API 呼び出しの本文コンテンツを JSON 埋め込み Graphql の形式で追加します </p> <p>例：</p><p>次の使用例は、列名を更新します。 <code>boardId</code> と <code>columnId</code> を、ハードコードされた GUID または以前のモジュールからマッピングされた GUID として含めることができます。<p><pre>{<br> "query": "mutation { updateColumn （boardId: \"\"", columnId: \"\", updateColumnInput: { name: \"\" }） { id name }}"<br>}</pre><p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


#### カスタム GraphQL API 呼び出しを行う

このアクションモジュールは、Workfront Boards API に対してカスタム GraphQL リクエストを実行します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>既存のWorkfront接続を使用してWorkfront Boards に接続することも、特定のWorkfront Boards 接続を使用することもできます。 </p><p>Workfront アプリをWorkfront Fusion に接続する手順については、この記事の <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Workfront ボードへの接続の作成 </a> を参照してください。</p> </td> 
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
   <td role="rowheader">[!UICONTROL 操作名 &#x200B;]</td> 
   <td> <p>この操作の名前を入力します。 これにより、呼び出しのトレースとデバッグが容易になります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 変数のデータ ソース &#x200B;]</td> 
   <td> <p>変数をフォームから取得するか、コレクションから取得するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variables]</td> 
   <td> <p>追加する変数ごとに、「<b> 項目を追加 </b> をクリックして、変数のキーと値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
   </tr> 
 </tbody> 
</table>
