---
title: Adobe Journey Optimizer モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Adobe Journey Optimizer] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: 1d0ccf4d-9f06-4210-86ec-7da7970f6a47
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '3709'
ht-degree: 26%

---

# [!DNL Adobe Journey Optimizer] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Adobe Journey Optimizer] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。 [!DNL Adobe Journey Optimizer] モジュールを使用すると、レコードの作成、読み取り、更新、削除をしたり、[!DNL Adobe Journey Optimizer] API へのカスタム API 呼び出しを行ったりできます。


シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

[!DNL Adobe Journey Optimizer] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!DNL Adobe Journey Optimizer] アカウントが必要です。

## Adobe Journey Optimizer API の情報

Adobe Journey Optimizer コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>{{connection.url}}</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.7.11</td> 
  </tr>
 </tbody> 
 </table>

## Adobe Journey Optimizerへの接続の作成

接続は任意のAdobe Journey Optimizer モジュールで作成できます。

1. 任意のモジュールで、「接続」ボックスの横にある **[!UICONTROL 追加]** をクリックします。

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
        <td>[!UICONTROL Adobe] [!UICONTROL クライアント ID] を入力します。 これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>[!DNL Adobe] [!UICONTROL Organization ID] を入力します。これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL サンドボックス名 ]</td>
        <td>この接続で使用するサンドボックスの名前を入力します。</td>
        </tr>
      </tbody>
    </table>



   <!--Markdown 0032 placeholder-->


## [!DNL Adobe Journey Optimizer] モジュールとそのフィールド

[!DNL Adobe Journey Optimizer] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Journey Optimizer]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [設定管理](#configuration-management)
* [パッケージ管理](#package-management)
* [レコード管理](#record-management)
* [メッセージ管理](#message-management)
* [ステータスチェック](#status-checks)
* [検索](#searches)
* [その他](#other)




### 設定管理

* [設定の作成](#create-a-configuration)
* [設定のデプロイ](#deploy-a-configuration)
* [設定の更新](#update-a-configuration)
* [設定のデプロイ解除](#undeploy-a-configuration)
* [設定をデプロイできるかどうかを確認します](#check-if-configuration-can-be-deployed)
* [設定の削除](#delete-a-configuration)
* [設定の取得](#get-a-configuration)

#### 設定の作成

このアクションモジュールは、キャッピングエンドポイントまたはスロットル設定を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらを作成するかを選択します。<ul><li><p><b>キャップ</b></p><a href="#capping-fields" class="MCXref xref" > キャッピングフィールド </a> に進みます。</li><li><p><b>制限</b></p>引き続き <a href="#throttling-fields" class="MCXref xref" > フィールドのスロットル </a> を行います。</li></ul></td> 
  </tr> 
   </tbody> 
</table>

##### キャッピングフィールド

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>設定するエンドポイントの URL を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL IMS 組織 ID]</td> 
   <td>組織のAdobe IMSID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メソッド ]</td> 
   <td>この設定で使用するメソッドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サービス ]</td> 
   <td>この設定にアクションとデータソースのどちらを使用するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 最大 HTTP 接続数 ]</td> 
   <td>このエンドポイントへの同時接続の最大数を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 最大呼び出し数 ]</td> 
   <td>「期間」フィールドで指定した期間に実行されるコールの最大数を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 期間（ミリ秒） ]</td> 
   <td>最大呼び出し数フィールドに関連するミリ秒数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

##### スロットルフィールド

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>この設定の名前を入力またはマッピングします。</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>この設定の説明を入力またはマッピングします。</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL URL パターン ]</td> 
   <td>スロットルするエンドポイントの URL を入力またはマップします。</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メソッド ]</td> 
   <td>この設定で使用するメソッドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL の最大スループット ]</td> 
   <td>この設定にアクションとデータソースのどちらを使用するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 最大 HTTP 接続数 ]</td> 
   <td>このエンドポイントへの同時接続の最大数を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 最大呼び出し数 ]</td> 
   <td>このエンドポイントに必要な最大スループットを入力またはマッピングします。 この値は 200 ～ 5000 の間にする必要があります。</td> 
  </tr> 
 </tbody> 
</table>

#### 設定のデプロイ

このアクションモジュールは、指定されたキャッピング設定またはスロットル設定をデプロイします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらをデプロイするかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定 ID]</td> 
   <td>デプロイする設定の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 設定の更新

このアクションモジュールは、指定されたキャッピング設定またはスロットル設定を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらを更新するかを選択します。<ul><li><p><b>キャップ</b></p>フィールドについては、この記事の「設定を作成」の節の <a href="#capping-fields" class="MCXref xref" > キャッピングフィールド </a> を参照してください。</li><li><p><b>制限</b></p>フィールドについては、この記事の設定の作成の節の <a href="#throttling-fields" class="MCXref xref" > フィールドのスロットル </a> を参照してください。</li></ul></td> 
  </tr> 
  </tbody> 
</table>

#### 設定のデプロイ解除

このアクションモジュールは、キャッピング設定またはスロットル設定のデプロイを解除します。 設定の状態がデプロイメント前の状態（`created` または `updated`）に戻ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらをデプロイ解除するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定 ID]</td> 
   <td>デプロイ解除する設定の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 設定をデプロイできるかどうかを確認します

このアクションモジュールは、キャッピング設定またはスロットル設定をデプロイできるかどうかを検証します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらを確認するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定 ID]</td> 
   <td>確認する設定の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 設定の削除

このアクションモジュールは、キャッピングエンドポイントまたはスロットル設定を削除します。

設定がデプロイされている場合は、削除する前にデプロイ解除する必要があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらを削除するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定 ID]</td> 
   <td>削除する設定の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 設定の取得

このアクションモジュールは、指定された ID で識別されるキャッピング設定またはスロットル設定を返します。 最新の定義が返されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>取得する設定がキャッピング設定かスロットル設定かを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定 ID]</td> 
   <td>取得する設定の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>




### パッケージ管理

* [パッケージを作成](#create-a-package)
* [パッケージの更新](#update-a-package)
* [パッケージを削除](#delete-a-package)
* [パッケージの検索](#look-up-a-package)
* [パッケージのインポート](#import-a-package)
* [パッケージの公開](#publish-a-package)
* [読み込みを送信](#submit-an-import)



#### パッケージを作成

このアクションモジュールは、マルチアーティファクトパッケージを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>パッケージの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>パッケージの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiration date]</td> 
   <td>パッケージの有効期限を定義するタイムスタンプを入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージの種類 ]</td> 
   <td>作成するパッケージのタイプを選択します。<ul><li><p><b>フル</b></p>パッケージにはすべてのアーティファクトが含まれます</p></li><li><p><b>一部</b></p><p>パッケージには、追加したアーティファクトのみが含まれます。 </p></li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL アーティファクト ]</td> 
   <td>部分パッケージを作成する場合は、追加するアーティファクトごとに「<b> アーティファクトを追加 </b> をクリックし、アーティファクトの ID、タイプおよびタイトルを指定します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Sandbox]</td> 
   <td>パッケージに含める項目を含んだサンドボックスの、名前と IMS 組織 ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### パッケージの更新

このアクションモジュールは、パッケージのアーティファクトの追加や削除、またはパッケージメタデータの更新を行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選択アクション ]</td> 
   <td>実行するアクションを選択します。<ul><li><p><b>アーティファクトを追加</b></p><p>追加するアーティファクトごとに、「<b> アーティファクトを追加 </b>」をクリックし、アーティファクトの ID、タイプおよびタイトルを指定してから、パッケージの有効期限を入力またはマップします。 </p></li><li><p><b>アーティファクトを削除</b></p><p>削除するアーティファクトごとに「<b> アーティファクトを追加 </b>」をクリックし、アーティファクトの ID、タイプおよびタイトルを指定します。 </p></li><li><p><b>メタデータを更新</b></p><p>名前、説明、またはソースサンドボックスの名前または IMS 組織 ID に対して新しい値を入力します。</p></li></ul></td> 
  </tr> 
 </tbody> 
</table>

#### パッケージを削除

このアクションモジュールは、マルチアーティファクトパッケージを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>削除するパッケージの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### パッケージの検索

このアクションモジュールは、指定されたパッケージの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>詳細を返すパッケージの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### パッケージのインポート

このアクションモジュールは、指定されたターゲットサンドボックス内の競合するオブジェクトを取得します。 競合するオブジェクトは、ターゲットサンドボックスに既に存在する類似のオブジェクトを表します。

パッケージを読み込むには、まず公開する必要があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>読み込むパッケージの ID を入力またはマッピングします。</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Target サンドボックス ]</td> 
   <td>パッケージを読み込むサンドボックスの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### パッケージの公開

パッケージを読み込むには、まず公開する必要があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>公開するパッケージの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 読み込みを送信

競合を確認し、置き換えを指定した後に、このアクションモジュールによってパッケージのインポートが送信されます。 結果はペイロードとして提供され、ペイロードで指定された宛先サンドボックスの読み込みジョブが開始されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>公開するパッケージの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>読み込みジョブの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>インポートジョブの説明を入力またはマッピング</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL （宛先サンドボックス）名 ]</td> 
   <td>読み込みの送信先となるサンドボックスの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL （宛先サンドボックス） IMS 組織 ID]</td> 
   <td>読み込みの送信先となるAdobe IMSのサンドボックス組織 ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL （Source サンドボックス） ID]</td> 
   <td>公開するパッケージを含むサンドボックスの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL （Source サンドボックス）タイプ ]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL （Source サンドボックス）リンク ]</td> 
   <td>公開するパッケージのリンクを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>


<!--

### Artifact management

* [Copy artifacts synchronously](#copy-artifacts-synchronously)
* [Export artifacts asynchronously](#export-artifacts-asynchronously)
* [Import artifacts asynchronously](#import-artifacts-asynchronously)

#### Copy artifacts synchronously

This action module copies artifacts from a source sandbox into a destination sandbox.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Enter or map a name for the new file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Enter or map a description for the new file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination sandbox]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>For each artifact you want to copy, click <b>Add artifact</b> and continue to <a href="#artifact-fields" class="MCXref xref" >Artifact fields</a>.</td> 
  </tr> 
 </tbody> 
</table>

##### Artifact fields

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Enter or map the ID of the artifact.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Enter or map the artifact type, such as <code>REGISTRY_SCHEMA<code> or <code>JOURNEY</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Version]</td> 
   <td>Enter or map the visibility of the artifact. This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Enter or map the visibility (tenant or global). This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Found]</td> 
   <td>Select <b>Yes</b> if this item was found using a GET operation.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tasks]</td> 
   <td>For each task you want to add, click <b>Add task</b> and fill in the following:
   <ul>
   <li><p><b>Method</b></p></li>
   <li><p><b>Action</b></p></li>
   <li><p><b>Using</b></p></li>
   <li><p><b>With</b></p></li>
   </ul>
   </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Messages]</td> 
   <td>For each task you want to add, click <b>Add message</b> and fill in the following:
   <ul>
   <li><p><b>Status</b></p><p>Enter or map the status that this message represents, such as <code>ERROR</code>.</li>
   <li><p><b>Attempt</b></p><p>Enter or map the attempt number related to this message. This may be useful if different attempts produce different messages.</p></li>
   <li><p><b>Message</b></p><p>Enter or map the text of the message.</li>
   <li><p><b>Object</b></p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

#### Export Artifacts asynchronously

This action module exports artifacts from the specified sandbox.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Enter or map a name for the export file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Enter or map a description for the export file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>For each artifact you want to export, click <b>Add artifact</b> and continue to <a href="#artifact-fields" class="MCXref xref" >Artifact fields</a>.</td> 
  </tr> 
 </tbody> 
</table>

##### Artifact fields

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Enter or map the ID of the artifact.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Enter or map the artifact type, such as <code>REGISTRY_SCHEMA<code> or <code>JOURNEY</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Version]</td> 
   <td>Enter or map the visibility of the artifact. This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Enter or map the visibility (tenant or global). This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Found]</td> 
   <td>Select <b>Yes</b> if this item was found using a GET operation.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tasks]</td> 
   <td>For each task you want to add, click <b>Add task</b> and fill in the following:
   <ul>
   <li><p><b>Method</b></p></li>
   <li><p><b>Action</b></p></li>
   <li><p><b>Using</b></p></li>
   <li><p><b>With</b></p></li>
   </ul>
   </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Messages]</td> 
   <td>For each task you want to add, click <b>Add message</b> and fill in the following:
   <ul>
   <li><p><b>Status</b></p><p>Enter or map the status that this message represents, such as <code>ERROR</code>.</li>
   <li><p><b>Attempt</b></p><p>Enter or map the attempt number related to this message. This may be useful if different attempts produce different messages.</p></li>
   <li><p><b>Message</b></p><p>Enter or map the text of the message.</li>
   <li><p><b>Object</b></p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



#### Import Artifacts asynchronously

This action module imports a snapshot containing artifacts.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Snapshot ID]</td> 
   <td>Enter or map the ID of the snapshot you want to import.</td> 
  </tr> 
 </tbody> 
</table>

-->

### レコード管理

* [レコードを作成](#create-a-record)
* [レコードの更新](#update-a-record)
* [レコードの削除](#delete-a-record)
* [レコードにパッチを適用](#patch-a-record)
* [レコードを取得](#get-a-record)

#### レコードを作成

このアクションモジュールは、新しいコンテンツテンプレートまたはコンテンツフラグメントを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ タイプの選択 ]</td> 
   <td>コンテンツテンプレートとコンテンツフラグメントのどちらを作成するかを選択します。<ul><li><p><b>コンテンツテンプレート</b></p><a href="#template-fields" class="MCXref xref" > テンプレートフィールド </a> に進みます。</li><li><p><b>コンテンツフラグメント</b></p><a href="#fragment-fields" class="MCXref xref" > フラグメントフィールド </a> に進みます。</li></ul></td> 
  </tr> 
  </tbody> 
</table>

##### テンプレートフィールド

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>このコンテンツテンプレートの名前を入力またはマッピングします。</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>このコンテンツテンプレートの説明を入力またはマッピングします。</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>作成するテンプレートのタイプを選択します。</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL チャンネル ]</td> 
   <td>このテンプレートに含めるチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ テンプレート オリジン ]</td> 
   <td>このテンプレートのソースを選択します。</td>  
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>新しいテンプレートにカスタムプロパティを含めるには、「メタデータを追加」を選択し、メタデータのキーと値を入力またはマッピングします。 含める各カスタムフィールドに対して繰り返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メールHTML]</td> 
   <td>このテンプレートに含まれるメールのHTMLを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL エディターコンテキスト ]</td> 
   <td>メールにカスタムプロパティを含めるには、「エディターコンテキストを追加」を選択し、コンテキストのキーと値を入力またはマッピングします。 含める各カスタムフィールドに対して繰り返します。</td> 
  </tr> 
 </tbody> 
</table>

##### フラグメントフィールド

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>このコンテンツフラグメントの名前を入力またはマッピングします。</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>このコンテンツフラグメントの説明を入力またはマッピングします。</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>作成するテンプレートのタイプを選択します。</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL チャンネル ]</td> 
   <td>このテンプレートに含めるチャネルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツフラグメントオリジン ]</td> 
   <td>このフラグメントのソースを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>新しいテンプレートにカスタムプロパティを含めるには、「メタデータを追加」を選択し、メタデータのキーと値を入力またはマッピングします。 含める各カスタムフィールドに対して繰り返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td>フラグメントのコンテンツを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL エディターコンテキスト ]</td> 
   <td>メールにカスタムプロパティを含めるには、「エディターコンテキストを追加」を選択し、コンテキストのキーと値を入力またはマッピングします。 含める各カスタムフィールドに対して繰り返します。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードの更新

このアクションモジュールは、コンテンツテンプレートまたはフラグメントを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ タイプの選択 ]</td> 
   <td>キャッピング設定とスロットル設定のどちらを更新するかを選択します。<ul><li><p><b>テンプレート</b></p>フィールドについては、この記事の「レコードの作成」の節の <a href="#template-fields" class="MCXref xref" > テンプレートフィールド </a> を参照してください。</li><li><p><b>フラグメント</b></p>フィールドについては、この記事の「レコードの作成」の節の <a href="#fragment-fields" class="MCXref xref" > フラグメントフィールド </a> を参照してください。</li></ul></td> 
  </tr> 
  </tbody> 
  </table>

#### レコードの削除

このアクションモジュールは、コンテンツテンプレートまたはコンテンツフラグメントを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ タイプの選択 ]</td> 
   <td>コンテンツテンプレートとコンテンツフラグメントのどちらを削除するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL テンプレート/フラグメント ID]</td> 
   <td>削除するテンプレートまたはフラグメントの ID を入力するかマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードにパッチを適用

このアクションモジュールは、JSON ポインター形式のPATCHを使用してレコードを更新します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ タイプの選択 ]</td> 
   <td>コンテンツテンプレートまたはコンテンツフラグメントにパッチを適用するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL テンプレート/フラグメント ID]</td> 
   <td>パッチを適用するテンプレートまたはフラグメントの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ペイロード データ ]</td> 
   <td>このパッチのペイロードにレコードを追加するには： <ol><li><b> レコードを追加 </b> をクリックします。</li><li>操作（追加、削除、置換）を選択します。</li><li>「パス」フィールドで、名前と説明のどちらをパッチするかを選択します。</li><li> 「送信元」フィールドに、JSON ポインター値を含む文字列を入力またはマップします。</li><li>「値」フィールドに、操作で使用する値を入力します。</li></ol></td> 
  </tr> 
 </tbody> 
</table>

#### レコードを取得

このアクションモジュールは、指定された ID で識別されるコンテンツテンプレートまたはコンテンツフラグメントを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ タイプの選択 ]</td> 
   <td>コンテンツテンプレートとコンテンツフラグメントのどちらを取得するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL テンプレート/フラグメント ID]</td> 
   <td>取得するテンプレートまたはフラグメントの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>


### メッセージ管理

* [単一メッセージ実行のトリガー](#trigger-a-unitary-message-execution)
* [オーディエンスベースのメッセージのトリガー設定](#trigger-an-audience-based-message)
* [オーディエンスベースのメッセージのステータスの確認](#check-the-status-for-audience-based-message)



#### 単一メッセージ実行のトリガー

指定した受信者に単一のトリガーを送信します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL リクエスト ID]</td> 
   <td>このメッセージに関連付けられているリクエストの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>このメッセージに関連付けられているキャンペーンの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Recipients]</td> 
   <td>このメッセージを受信する各受信者に対して、「<b> 受信者を追加 </b>」をクリックし、次の情報を入力します。
   <ul>
   <li><p><b>タイプ</b></p>「<code>aep</code>」を選択します。</li>
   <li><p><b>ユーザー ID</b></p>受信者のAdobe Experience Platform プロファイル識別情報を入力またはマッピングします。</li>
   <li><p><b>名前空間</b></p>受信者のAdobe Experience Platform プロファイル名前空間を入力またはマッピングします。</li>
   <li><p><b>メールアドレス</b></p></li>
   <li><p><b>携帯電話番号</b></p></li>
   <li><p><b>名</b></p></li>
   <li><p><b>姓</b></p></li>
   <li><p><b>製品</b></p>このメッセージに関連付けられている製品を入力またはマップします。 これは、メッセージコンテンツの動的変数の置換に使用されます。</li>
   </ul></td> 
  </tr> 
 </tbody> 
</table>

#### オーディエンスベースのメッセージのトリガー設定

このアクションモジュールは、指定されたリクエストとキャンペーンに基づいて、オーディエンスベースのメッセージの実行をトリガーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL リクエスト ID]</td> 
   <td>このメッセージに関連付けられているリクエストの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>このメッセージに関連付けられているキャンペーンの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 製品 ]</td> 
   <td>このメッセージに関連付けられている製品を入力またはマップします。 これは、メッセージコンテンツの動的変数の置換に使用されます。</td> 
  </tr> 
 </tbody> 
</table>

#### オーディエンスベースのメッセージのステータスの確認

このアクションモジュールは、オーディエンスベースのバッチメッセージのステータスを確認します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL メッセージ実行 ID]</td> 
   <td>確認するメッセージ実行の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### ステータスチェック

<!--* [Check service health](#check-service-health)-->
* [読み込みの依存関係を確認する](#check-the-import-dependencies)
* [インポートジョブのステータスの確認](#check-the-status-of-an-import-job)

<!--

#### Check service health

This action module checks that the service represented by the connection is running.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
 </tbody> 
</table>

-->

#### 読み込みの依存関係を確認する

このアクションモジュールは、パッケージアーティファクトの依存関係を確認します。 これにより、パッケージアーティファクトをインポートする権限があるかどうかを確認できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>権限を確認するパッケージの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Target サンドボックス ]</td> 
   <td>パッケージの読み込み先のサンドボックスの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### インポートジョブのステータスの確認

このアクションモジュールは、インポートジョブが成功または失敗したかどうかを確認します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td>データを取得するジョブの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [すべての依存オブジェクトのリスト](#list-all-dependent-objects)
* [設定のリスト](#list-configurations)
* [エクスポートジョブとインポートジョブのリスト](#list-export-and-import-jobs)
* [パッケージのリスト](#list-packages)
* [レコードのリスト](#list-records)

#### すべての依存オブジェクトのリスト

この検索モジュールは、指定したパッケージ内のオブジェクトのすべての依存オブジェクトをリストします

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ オブジェクト ]</td> 
   <td>依存オブジェクトを返すパッケージ内のオブジェクトごとに、<b> オブジェクトの追加 </b> をクリックし、オブジェクトの名前と種類を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL パッケージ ID]</td> 
   <td>依存オブジェクトをリストするパッケージの ID を入力またはマップします。</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Target サンドボックス ]</td> 
   <td>依存オブジェクトをリストするパッケージを含むサンドボックスの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 設定のリスト

このアクションモジュールは、すべてのキャッピング設定またはスロットル設定をリストします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 設定タイプの選択 ]</td> 
   <td>キャッピング設定をリストするか、スロットル設定をリストするかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### エクスポートジョブとインポートジョブのリスト

この検索モジュールは、現在のエクスポートおよびインポート ジョブを一覧表示します。 クエリパラメーターを使用して、リストをフィルタリングできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
      <td>作成日または変更日のどちらで結果を並べ替えるかを選択します。</td>
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL クエリパラメーター ]</td> 
   <td>フィルターの条件にする各クエリパラメーターに対して「<b> クエリパラメーターを追加 </b>」をクリックし、フィールドと演算子を選択して、フィルターのフィールド値を入力します。</td> 
  </tr> 
 </tbody> 
</table>



#### パッケージのリスト

この検索モジュールには、組織内のすべてのパッケージが一覧表示されます。 クエリパラメーターを使用して、リストをフィルタリングできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
      <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
      <td>作成日または変更日のどちらで結果を並べ替えるかを選択します。</td>
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL クエリパラメーター ]</td> 
   <td>フィルターの条件にする各クエリパラメーターに対して「<b> クエリパラメーターを追加 </b>」をクリックし、フィールドと演算子を選択して、フィルターのフィールド値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードのリスト

この検索モジュールは、すべてのキャッピング設定またはスロットル設定をリストします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテンツ タイプの選択 ]</td> 
   <td>コンテンツテンプレートとコンテンツフラグメントのどちらを取得するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td>このリストを並べ替えるパラメーター名を入力またはマッピングします。 降順または昇順に並べ替えるには、<code>-</code> または <code>+</code> を追加します。 記号を指定しない場合、リストは降順に並べ替えられます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>このフィールドはページネーションに使用されます。 「並べ替え順」フィールドで指定されたプロパティに関する次のページの条件を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td>このリストを並べ替えるパラメーター名を入力またはマッピングします。 降順または昇順に並べ替えるには、<code>-</code> または <code>+</code> を追加します。 記号を指定しない場合、リストは降順に並べ替えられます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロパティによるフィルタ ]</td> 
   <td>追加するプロパティ フィルタごとに、[<b> アイテムの追加 </b>] をクリックし、プロパティのキーと値を入力します。 プロパティに指定した値を含むレコードがリストに含まれます。</td> 
  </tr> 
 </tbody> 
</table>


### その他


#### カスタム API 呼び出しの実行

このアクションモジュールは、Adobe Journey Optimizer API に対してカスタム API 呼び出しを行います。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>[!DNL Adobe Journey Optimizer] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >[!DNL Adobe Journey Optimizer]</a> への接続を作成を参照してください。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>ベース URL を基準とした相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は、認証、<code>x-api-key</code> および <code>x-gw-ims-org-id</code> ヘッダーを自動的に追加します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>リクエストクエリ文字列を入力します。</p>
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







<!--

* [Check if configuration can be deployed](#check-if-configuration-can-be-deployed)
* [Check service health](#check-service-health)
* [Check the import dependencies](#check-the-import-dependencies)
* [Check the status for audience-based message](#status-for-audience-based-message)
* [Copy artifacts synchronously](#copy-artifacts-synchronously)
* [Create a configuration](#create-a-configuration)
* [Create a package](#create-a-package)
* [Create a record](#create-a-record)
* [Delete a configuration](#delete-a-configuration)
* [Delete a package](#delete-a-package)
* [Delete a record](#delete-a-record)
* [Deploy a configuration](#deploy-a-configuration)
* [Export artifacts asynchronously](#export-artifacts-asynchronously)
* [Get a configuration](#get-a-configuration)
* [Get a record](#get-a-record)
* [Import a package](#import-a-package)
* [Import artifacts asynchronously](#import-artifacts-asynchronously)
* [List all dependent objects](#list-all-dependent-objects)
* [List export and import jobs](#list-import-and-export-jobs)
* [Look up a package](#look-up-a-package)
* [Make a custom API call](#make-a-custom-api-call)
* [Patch a record](#patch-a-record)
* [Publish a package](#publish-a-package)
* [Submit an import](#submit-an-import)
* [Trigger a unitary message execution](#trigger-a-unitary-message-execution)
* [Trigger an audience-based message](#trigger-an-audience-based-message)
* [Undeploy a configuration](#undeploy-a-configuration)
* [Update a configuration](#update-a-configuration)
* [Update a package](#update-a-package)
* [Update a record](#update-a-record)
* [List configurations](#list-configurations)
* [List packages](#list-packages)
* [List records](#list-records)

-->
