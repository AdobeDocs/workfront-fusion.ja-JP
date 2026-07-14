---
title: Adobe Workfront Planning モジュール
description: ' [!DNL Adobe Workfront Planning]  モジュールを使用すると、Workfront Planning アカウント内のイベントに基づいてAdobe Workfront Fusion シナリオを開始し、契約書やその他のレコードを作成、読み取りまたは更新し、設定した条件を使用してレコードを検索し、ドキュメントをアップロードできます。 [!DNL Adobe] '
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
TQID: https://experienceleague.adobe.com/QHOFWDOT-18-c0b3wLXsRV5cjGVxlcyLhvZdkev3GFg
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: f0e185778e01b71a91837531a082e88485e97ca2
workflow-type: tm+mt
source-wordcount: 6075
ht-degree: 44%

---


# Adobe Workfront Planning モジュール

[!DNL Adobe Workfront Planning] モジュールを使用すると、Workfront Planningでイベントが発生したときにシナリオをトリガーできます。 レコードを作成、読み取り、更新、削除したり、[!DNL Adobe Workfront Planning] アカウントへのカスタム API の呼び出しを実行したりできます。

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

Workfront Planningにアクセスするには、次の情報が必要です。

* 新しいWorkfront パッケージとライセンス。 Workfront Planningは、従来のWorkfront パッケージまたはライセンスでは使用できません。
* Workfront計画パッケージ。
* 組織のWorkfront インスタンスをAdobe Unified Experienceにオンボーディングする必要があります。

## Adobe Workfront計画APIの情報

Adobe Workfront Planning コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td><pre><code>https://&#123;&#123;connection.host&#125;&#125;/maestro/api/&#123;&#123;common.maestroApiVersion&#125;&#125;/</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## Workfront PlanningとWorkfront Fusionの連携

Workfront Planning コネクタは、OAuth 2.0を使用してWorkfront Planningに接続します。

Workfront Planning Fusion モジュール内から直接Workfront Planning アカウントへの接続を作成できます。

* [クライアント IDとクライアントシークレットを使用してWorkfront Planningに接続する](#connect-to-workfront-planning-using-client-id-and-client-secret)
* [サーバー間接続を使用したWorkfront Planningへの接続](#connect-to-workfront--planning-using-a-server-to-server-connection)

### クライアント IDとクライアントシークレットを使用してWorkfront Planningに接続する

1. 任意のAdobe Workfront計画モジュールで、「接続」フィールドの横にある「**追加**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p><b>Adobe Workfront認証</b>接続を選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>新しい接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Workfront クライアント ID を入力します。 これは、Workfront の設定エリアの OAuth2 アプリケーションエリアにあります。 接続している特定のアプリケーションを開いて、クライアント ID を確認します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Workfront クライアントシークレットを入力します。 これは、Workfront の設定エリアの OAuth2 アプリケーションエリアにあります。 Workfront で OAuth2 アプリケーションのクライアントシークレットがない場合は、別のシークレットを生成できます。 手順について詳しくは、Workfront ドキュメントを参照してください。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>これはデフォルト値のままにすることもできますし、Workfront インスタンスの URL に続けて <code>/integrations/oauth2</code> を入力することもできます。 <p>例： <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>ほとんどの場合、この値は <code>origin</code> にしてください。
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

   Workfront Planningにログインしていない場合は、ログイン画面が表示されます。 ログイン後、接続を許可できます。

>[!NOTE]
>
>* Workfront API への OAuth 2.0 接続は API キーに依存しなくなりました。
>* Workfront サンドボックス環境への接続を作成するには、その環境で OAuth2 アプリケーションを作成し、接続でそのアプリケーションによって生成されたクライアント ID とクライアントシークレットを使用する必要があります。

### サーバー間接続を使用したWorkfront Planningへの接続

1. 任意のAdobe Workfront計画モジュールで、「接続」フィールドの横にある「**追加**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>「<b>Adobe Workfront サーバー間接続</b>」を選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>新しい接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance name]</td>
        <td>
          <p>インスタンス（ドメインとも呼ばれます）の名前を入力します。</p><p>例：URL が <code>https://example.my.workfront.com</code> の場合は、<code>example</code> と入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance lane]</td>
        <td>
          <p>この接続の接続先となる環境タイプを入力します。</p><p>例：URL が <code>https://example.my.workfront.com</code> の場合は、<code>my</code> と入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Workfront クライアント ID を入力します。 これは、Workfront の設定エリアの OAuth2 アプリケーションエリアにあります。 接続している特定のアプリケーションを開いて、クライアント ID を確認します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Workfront クライアントシークレットを入力します。 これは、Workfront の設定エリアの OAuth2 アプリケーションエリアにあります。 Workfront で OAuth2 アプリケーションのクライアントシークレットがない場合は、別のシークレットを生成できます。 手順について詳しくは、Workfront ドキュメントを参照してください。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>この接続に適用可能なスコープを入力します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>ほとんどの場合、この値は <code>origin</code> にしてください。
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

   Workfront Planningにログインしていない場合は、ログイン画面が表示されます。 ログイン後、接続を許可できます。

>[!NOTE]
>
>* Workfront API への OAuth 2.0 接続は API キーに依存しなくなりました。
>* Workfront サンドボックス環境への接続を作成するには、その環境で OAuth2 アプリケーションを作成し、接続でそのアプリケーションによって生成されたクライアント ID とクライアントシークレットを使用する必要があります。

## [!DNL Adobe Workfront Planning] バージョン 2 モジュールとそのフィールド

>[!IMPORTANT]
>
>この節のモジュールは、Workfront Planning V2 コネクタに属しています。Workfront Planning V1 コネクタのモジュールについては、[[!DNL Adobe Workfront Planning]  バージョン 1 モジュールとそのフィールド ](#adobe-workfront-planning-version-1-modules-and-their-fields)を参照してください。

Workfront計画モジュールを設定すると、Workfront Fusionに次のフィールドが表示されます。 これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加の Workfront フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

* [ワークスペース](#workspaces-v2)
* [レコードタイプ](#record-types-v2)
* [レコード](#records-v2)
* [フィールド](#fields-v2)
* [ビュー](#views-v2)
* [権限](#permissions-v2)
* [その他](#other-v2)

### ワークスペース （V2）

* [ワークスペースの作成](#create-a-workspace-v2)
* [ワークスペースの削除](#delete-a-workspace-v2)
* [すべてのワークスペースを取得](#get-all-workspaces-v2)
* [ワークスペースを取得](#get-a-workspace-v2)
* [ワークスペースの更新](#update-a-workspace-v2)

#### ワークスペースの作成（V2）

このアクションモジュールは、Planningで新しいワークスペースを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace名]</p>
      </td>
      <td>新しいワークスペースの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>説明</p>
      </td>
      <td>新しいワークスペース/td&gt;の説明を入力またはマッピングします 
    </tr>
    <tr>
      <td role="rowheader">
        <p>色</p>
      </td>
      <td>新しいレコードタイプを表すために使用するカラーを選択します</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>アイコン</p>
      </td>
      <td>このレコードタイプに使用するアイコンをマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>所有者</p>
      </td>
      <td>ワークスペースを所有するAdobe IMSのユーザーIDを入力するか、マッピングします。</td> 
    </tr>
  </tbody>
</table>

#### ワークスペースの削除（V2）

このアクションモジュールは、IDで指定された1つのワークスペースを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace ID]</p>
      </td>
      <td>削除するワークスペースのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### すべてのワークスペースを取得（V2）

このモジュールは、すべてのワークスペースのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 返されたワークスペースの最大数]</p>
      </td>
      <td>1回の実行サイクル中にモジュールが返すワークスペースの最大数を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### ワークスペースを取得（V2）

このモジュールは、IDでワークスペースを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace ID]</p>
      </td>
      <td>取得するワークスペースのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### ワークスペースの更新（V2）

このアクションモジュールは、Planningの新しいワークスペースを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>更新するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace名]</p>
      </td>
      <td>新しいワークスペースの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>説明</p>
      </td>
      <td>新しいワークスペース/td&gt;の説明を入力またはマッピングします 
    </tr>
    <tr>
      <td role="rowheader">
        <p>色</p>
      </td>
      <td>新しいレコードタイプを表すために使用するカラーを選択します</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>アイコン</p>
      </td>
      <td>このレコードタイプに使用するアイコンをマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>所有者</p>
      </td>
      <td>ワークスペースを所有するAdobe IMSのユーザーIDを入力するか、マッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>レコードタイプセクション</p>
      </td>
      <td>このワークスペースに追加する各レコードタイプセクションについて、<b>項目を追加</b>をクリックし、セクションの名前、レコードタイプ ID、および既存のレコードタイプ IDを上書きするかどうかを入力します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>レコードタイプセクション/上書き</p>
      </td>
      <td>既存のセクションをモジュールのセクションに置き換えるかどうかを選択します。 いいえ場合は、モジュールのセクションが既存のセクションのリストに追加されます。</td> 
    </tr>
  </tbody>
</table>


### レコードタイプ （V2）

* [レコードタイプの作成](#create-a-record-type-v2)
* [レコードタイプの削除](#delete-a-record-type-v2)
* [グローバルなレコードタイプを取得](#get-global-record-types-v2)
* [レコードタイプを取得](#get-a-record-type-v2)
* [レコードタイプの取得](#get-record-types-v2)
* [レコードタイプの更新](#update-a-record-type-v2)

#### レコードタイプ（V2）の作成

このアクションモジュールは、選択したワークスペースに新しいレコードタイプを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>レコードタイプを作成するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>表示名</p>
      </td>
      <td>新しいレコードタイプの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>説明</p>
      </td>
      <td>新しいレコードタイプの説明を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>アイコン</p>
      </td>
      <td>このレコードタイプに使用するアイコンをマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>色</p>
      </td>
      <td>新しいレコードタイプを表すために使用するカラーを選択します</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Source レコードタイプ</p>
      </td>
      <td>別のレコードタイプを使用してコピーを開始する場合は、そのレコードタイプを選択します。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプの削除（V2）

このアクションモジュールは、IDで指定された1つのレコードタイプを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>削除するレコードタイプのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### グローバルなレコードタイプを取得（V2）

このモジュールは、Adobe Workfront Planning アカウント内のレコードタイプのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>ワークスペースを選択します。 モジュールは、このワークスペースに追加できるグローバルレコードタイプを返します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL返されるレコードの最大数]</p>
      </td>
      <td>1回の実行サイクル中にモジュールが返す最大レコードタイプ数を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプ（V2）を取得

このモジュールは、レコードタイプをIDで取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>取得するレコードタイプのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプを取得（V2）

このモジュールは、特定のワークスペースで使用可能なレコードタイプのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>レコードタイプを取得するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL返されるレコードの最大数]</p>
      </td>
      <td>1回の実行サイクル中にモジュールが返す最大レコードタイプ数を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプの更新（V2）

このモジュールは、レコードタイプを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>レコードタイプを更新するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>レコードタイプを更新するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>表示名</p>
      </td>
      <td>レコードタイプの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>説明</p>
      </td>
      <td>レコードタイプの説明を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>プライマリフィールド ID</p>
      </td>
      <td>レコードタイプのタイトルとして使用されるフィールドのIDを入力またはマッピングします。</td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>アイコン</p>
      </td>
      <td>このレコードタイプに使用するアイコンをマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>色</p>
      </td>
      <td>新しいレコードタイプを表すために使用するカラーを選択します</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Workspace IDとリンク可能</p>
      </td>
      <td>このレコードタイプをリンクできるワークスペースごとに、<b>項目を追加</b>をクリックし、ワークスペースのIDを入力します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Workspace IDでリンク可能/上書き</p>
      </td>
      <td>既存のワークスペースをモジュールのワークスペースに置き換えるかどうかを選択します。 ない場合は、モジュールのワークスペースが既存のワークスペースのリストに追加されます。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>動的なレコードタイプの作成が許可されました</p>
      </td>
      <td>このレコードタイプから動的レコードタイプを作成する権限を持つ各件名について、<b>項目を追加</b>をクリックし、件名のタイプとIDを入力します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>動的レコードタイプの作成/上書きを許可</p>
      </td>
      <td>既存のオブジェクトをモジュールのオブジェクトに置き換えるかどうかを選択します。 いいえ場合は、モジュールのオブジェクトが既存のオブジェクトのリストに追加されます。</td> 
    </tr>
  </tbody>
</table>



### レコード （V2）

* [レコードの作成](#create-a-record-v2)
* [レコードの削除](#delete-a-record-v2)
* [レコードを取得](#get-a-record-v2)
* [レコードタイプ別にレコードの取得](#get-records-by-record-type-v2)
* [レコードを移動](#move-records-v2)
* [レコードの検索](#search-records-v2)
* [レコードの更新](#update-a-record-v2)

#### レコードの作成（V2）

このアクションは、Workfront計画で1つのレコードを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>レコードを作成するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>作成するレコードのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>新しいレコードの値を入力します。 これらのフィールドは、選択したレコードタイプに基づいており、Workfront Planning組織に固有です。</td> 
    </tr>
  </tbody>
</table>

#### レコードの削除（V2）

このアクションモジュールは、IDで指定された1つのレコードを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>削除するレコードのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードの取得（V2）

このアクションモジュールは、IDで指定されたレコードを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace ID]</p>
      </td>
      <td>取得するレコードのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプ （V2）別にレコードを取得

このモジュールは、指定されたレコードタイプのすべてのレコードのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>取得するレコードを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>返すレコードのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>1回の実行サイクル中にモジュールが返す最大レコード数を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードの移動（V2）

このモジュールは、レコードタイプ内の1つ以上のレコードの並べ替え先を指定します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>移動するレコードを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>移動するレコードのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ワークスペース]</p>
      </td>
      <td>移動するレコードを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ワークスペース]</p>
      </td>
      <td>移動するレコードを含むワークスペースを選択します。</td> 
    </tr>
  </tbody>
</table>

#### レコードの検索（V2）

指定した条件に基づいてレコードを返します

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>取得するレコードを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>取得するレコードを含むレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Other fields]</p>
      </td>
      <td>フィルターを適用する各フィールドについて、そのフィールドの演算子と値を入力します。 これらのフィールドは、選択したレコードタイプに基づいており、Workfront Planning組織に固有です。</td> 
    </tr>
  </tbody>
</table>

#### レコードの更新（V2）

このモジュールは、指定されたレコードを更新します。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>更新するレコードを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>更新するレコードのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>更新するレコードの ID を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Other fields]</p>
      </td>
      <td>他のフィールドの値を入力します。 使用可能なフィールドは、選択したレコードによって異なります。</td> 
    </tr>
  </tbody>
</table>


### フィールド （V2）

* [フィールドを作成](#create-a-field-v2)
* [フィールドの削除](#delete-a-field-v2)
* [フィールドを取得](#get-a-field-v2)
* [レコードタイプ別のフィールドを取得](#get-fields-by-record-type-v2)
* [フィールドを更新](#update-a-field-v2)

#### フィールドの作成（V2）

このアクションモジュールは、指定したレコードタイプに新しいフィールドを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>フィールドを作成するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>フィールドを作成するレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>表示名</p>
      </td>
      <td>新しいフィールドの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>説明</p>
      </td>
      <td>新しいフィールドの説明を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>フィールドタイプ</p>
      </td>
      <td>フィールドのデータタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>選択したフィールドタイプに固有の他のフィールドを使用できます。 これらのフィールドの値を入力します。</td> 
    </tr>
  </tbody>
</table>

#### フィールドの削除（V2）

このアクションモジュールは、IDで指定された1つのフィールドを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Field ID]</p>
      </td>
      <td>削除するフィールドの ID を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### フィールドを取得（V2）

このモジュールは、IDでフィールドを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Field ID]</p>
      </td>
      <td>取得するフィールドのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプ （V2）でフィールドを取得

このモジュールは、特定のレコードタイプのフィールドのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>返すフィールドを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>フィールドを返すレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL返されるフィールドの最大数]</p>
      </td>
      <td>1回の実行サイクル中にモジュールが返す最大フィールド数を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### フィールドの更新（V2）

このモジュールは、フィールドをIDで部分的に更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソースタイプ ]</p>
      </td>
      <td>更新するフィールドを含むリソースタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Field ID]</p>
      </td>
      <td>更新するフィールドを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL表示名]</p>
      </td>
      <td>フィールドの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Description]</p>
      </td>
      <td>フィールドの説明を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROLその他のパラメーター]</p>
      </td>
      <td>他のフィールドパラメーターの値を入力します。 使用可能なパラメーターは、選択したフィールドによって異なります。</td> 
    </tr>
  </tbody>
</table>


### ビュー（V2）

* [ビューを作成](#create-a-view-v2)
* [ビューの削除](#delete-a-view-v2)
* [ビューを取得](#get-a-view-v2)
* [レコードタイプ別のビューを取得](#get-views-by-record-type-v2)
* [ビューの更新](#update-a-view-v2)

#### ビューの作成（V2）

このアクションモジュールは、選択したレコードタイプの新しいビューを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>ビューを作成するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>ビューを作成するレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>ビュー名</p>
      </td>
      <td>新しいビューの名前を入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>表示タイプ</p>
      </td>
      <td>新しいビューが表、タイムライン、またはカレンダービューのどれかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>開始日フィールド</p>
      </td>
      <td>ビューがタイムラインまたはカレンダービューの場合は、ビューがレコードをタイムラインに配置するために使用するフィールドを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>終了日フィールド。</p>
      </td>
      <td>ビューがタイムラインビューまたはカレンダービューの場合は、タイムラインの終了日を決定するためにビューが使用するフィールドを選択します。</td> 
    </tr>
  </tbody>
</table>

#### ビューの削除（V2）

このアクションモジュールは、IDで指定された単一のビューを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ビューID]</p>
      </td>
      <td>削除するビューのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### ビューを取得（V2）

このモジュールは、IDでビューを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ビューID]</p>
      </td>
      <td>取得するビューのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### レコードタイプ別のビューの取得（V2）

このモジュールは、特定のレコードタイプのビューのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>取得するビューを含むワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>取得するビューを含むレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL返されるビューの最大数]</p>
      </td>
      <td>1回の実行サイクル中にモジュールが返す最大ビュー数を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### ビューの更新（V2）

このアクションモジュールは、指定したビューを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>ビューを更新するワークスペースを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>ビューを更新するレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>ビュー ID</p>
      </td>
      <td>更新するビューを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>ビュー名</p>
      </td>
      <td>新しいビューの名前を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

### 権限（V2）

* [アクセス要求を閉じる](#dismiss-access-requests-v2)
* [リソースのすべてのメンバーとその役割を取得](#get-all-members-and-their-roles-for-a-resource-v2)
* [リソースに対する現在のユーザーの効果的な権限を取得](#get-the-current-users-effective-permissions-on-a-resource-v2)
* [リソースに対する保留中のアクセス要求のリスト](#list-pending-access-requests-for-a-resource-v2)
* [リソースへのアクセスをリクエスト](#request-access-to-a-resource-v2)

#### アクセス要求を閉じる（V2）

このアクションモジュールは、IDで指定された1つ以上のアクセス要求を却下します。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソースタイプ ]</p>
      </td>
      <td>削除するWorkspaceのIDを入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソース ID]</p>
      </td>
      <td>アクセス要求を却下するリソースのIDを入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リクエスト ID]</p>
      </td>
      <td>却下する各アクセス要求について、<b>項目を追加</b>をクリックし、要求IDを入力します。</td> 
    </tr>
  </tbody>
</table>

#### リソースのすべてのメンバーとその役割を取得（V2）

このモジュールには、リソースに明示的な共有関係を持つすべてのユーザー、グループ、およびチームが一覧表示されます。 このモジュールの接続で使用される資格情報には、リソースに対する管理権限が必要です。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソースタイプ ]</p>
      </td>
      <td>情報を取得するリソースのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソース ID]</p>
      </td>
      <td>情報を取得するリソースのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### リソースに対する現在のユーザーの効果的な権限を取得する（V2）

このモジュールは、特定のリソースに対する現在のユーザーのビュー、編集、削除、および追加の権限を返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソースタイプ ]</p>
      </td>
      <td>権限を取得するリソースタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソース ID]</p>
      </td>
      <td>権限を取得するリソースのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### リソースの保留中のアクセス要求のリスト （V2）

このモジュールは、特定のリソースに対するすべての保留中のアクセス要求を返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソースタイプ ]</p>
      </td>
      <td>情報を取得するリソースのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソース ID]</p>
      </td>
      <td>情報を取得するリソースのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### リソースへのアクセスの要求（V2）

このモジュールは、特定のリソースに対する現在のユーザーのアクセスリクエストを作成または更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソースタイプ ]</p>
      </td>
      <td>アクセスリクエストを作成または更新するリソースのタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL リソース ID]</p>
      </td>
      <td>アクセスリクエストを作成または更新するリソースのIDを入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Message]</p>
      </td>
      <td>アクセス要求に含めるメッセージのテキストを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>



### その他（V2）

* [Workfront IDから認証IDを取得](#get-auth-id-from-workfront-id-v2)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call-v2)
* [イベントの監視](#watch-events-v2)

#### Workfront ID （V2）から認証IDを取得

このモジュールは、Workfront ユーザーIDを取得し、Planningで使用する一致する認証IDを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workfront User ID]</p>
      </td>
      <td>認証IDを取得するユーザーのWorkfront IDを入力するか、マッピングします。</td> 
    </tr>
  </tbody>
</table>

#### カスタム API呼び出しを行う（V2） &lt;table

このモジュールは、Workfront Planning APIに対するカスタム呼び出しを行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Workfront を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p><code> https://&lt;WORKFRONT_DOMAIN>/maestro/api/.</code> への相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>モジュールが使用する Workfront API のバージョンを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion での HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。 これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> {"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> <p>ヒント：情報は、クエリパラメーターではなく、JSON 本文を使用して送信することをお勧めします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### イベントを見る（V2）

このトリガーモジュールは、レコード、レコードタイプ、またはワークスペースがWorkfront Planningで作成、更新、または削除されたときにシナリオを開始します。

>[!IMPORTANT]
>
>このモジュールは後で編集でき、Webhookを編集します。
>
>Webhookを更新する際には、次の点を考慮してください。
>
>* 編集されたWebhookは、Workfront イベントサブスクリプションによって新しいサブスクリプションとして扱われます。 イベントのサブスクリプション履歴は、別のイベントのサブスクリプションと見なされるため、以前のWebhook設定では保持されません。
>* 古いイベント サブスクリプションから新しいイベント サブスクリプションへの切り替えは、完全に同期されていない可能性があります。 したがって、イベントを2回受信したり（新しいサブスクリプションが古いサブスクリプションの実行開始前に開始された場合）、イベントを見逃したり（古いサブスクリプションが新しいサブスクリプションの実行開始前に停止した場合）することができます。
>
>Webhookの編集について詳しくは、[Webhookの編集](/help/workfront-fusion/manage-scenarios/edit-webhooks.md)を参照してください。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>使用する web フックを選択するか、「追加」をクリックして新しい web フックを作成します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>レコード、レコードタイプまたはワークスペースを監視するかどうかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Objects to watch]</td>
      <td>新しいレコード、更新されたレコード、新しいレコードと更新されたレコードの両方、または削除されたレコードを監視するかどうかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL設定タイプ ]</td>
      <td>シンプルな設定と高度な設定のどちらかを選択します。 <p>高度な設定について詳しくは、この記事の「<a href="#example-of-advanced-logic-in-the-watch-events-module" class="MCXref xref" >監視イベントモジュールの高度なロジックの例</a>」を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>古い状態と新しい状態のどちらを監視するかを選択します。<ul><li><p><b>[!UICONTROL New state]</b></p><p>レコードが指定された値<b>に</b>変化したときにシナリオをトリガーします。</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>レコードが指定された値<b>から</b>変化したときにシナリオをトリガーします。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>レコードを視聴する場合は、レコードを視聴するWorkspaceを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>レコードを監視する場合は、監視するレコードタイプを選択します。</td>
    </tr>
    </tr>
    <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>選択した条件を満たすレコードのみを監視するフィルターを設定できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。 AND ルールを追加すると、複数のフィルターを使用できます。</p> <p>注意：既存のWorkfront Webhookではフィルターを編集できません。 Workfront イベントのサブスクリプションに別のフィルターを設定するには、現在の Webhook を削除し、新しい Webhook を作成します。</p> <p>イベントフィルターについて詳しくは、Workfront モジュールの「Workfront &gt; [!UICONTROL Watch Events] modules</a>」の「<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref"> イベントサブスクリプションフィルター」を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Objects to watch]</td>
      <td>レコードの新規作成、 更新、新規作成および更新、削除を監視するかどうかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Exclude updates made by this connection]</p>
      </td>
      <td>このオプションを有効にすると、このモジュールが使用する接続によって変更が行われた場合にシナリオがトリガーされなくなります。 これにより、このシナリオがトリガーアクションを実行した場合に、シナリオの別のインスタンスがトリガーされるのを防ぎます。</td> 
    </tr>
  </tbody>
</table>

このモジュールで高度なロジックを使用する例については、[監視イベントモジュールの高度なロジックの例](#example-of-advanced-logic-in-the-watch-events-module)を参照してください。






## [!DNL Adobe Workfront Planning] バージョン 1 モジュールとそのフィールド

>[!IMPORTANT]
>
>このセクションのモジュールは、Workfront Planning V1 コネクタに属しています。Workfront Planning V2 コネクタのモジュールについては、[[!DNL Adobe Workfront Planning]  バージョン 2 モジュールとそのフィールド ](#adobe-workfront-planning-version-2-modules-and-their-fields)を参照してください。

Workfront計画モジュールを設定すると、Workfront Fusionに次のフィールドが表示されます。 これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加の Workfront フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。


![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)
* [未分類](#uncategorized)

### トリガー

#### イベントの監視

このトリガーモジュールは、レコード、レコードタイプ、またはワークスペースがWorkfront Planningで作成、更新、または削除されたときにシナリオを開始します。

>[!IMPORTANT]
>
>このモジュールは後で編集でき、Webhookを編集します。
>
>Webhookを更新する際には、次の点を考慮してください。
>
>* 編集されたWebhookは、Workfront イベントサブスクリプションによって新しいサブスクリプションとして扱われます。 イベントのサブスクリプション履歴は、別のイベントのサブスクリプションと見なされるため、以前のWebhook設定では保持されません。
>* 古いイベント サブスクリプションから新しいイベント サブスクリプションへの切り替えは、完全に同期されていない可能性があります。 したがって、イベントを2回受信したり（新しいサブスクリプションが古いサブスクリプションの実行開始前に開始された場合）、イベントを見逃したり（古いサブスクリプションが新しいサブスクリプションの実行開始前に停止した場合）することができます。
>
>Webhookの編集について詳しくは、[Webhookの編集](/help/workfront-fusion/manage-scenarios/edit-webhooks.md)を参照してください。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>使用する web フックを選択するか、「追加」をクリックして新しい web フックを作成します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>レコード、レコードタイプまたはワークスペースを監視するかどうかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>古い状態と新しい状態のどちらを監視するかを選択します。<ul><li><p><b>[!UICONTROL New state]</b></p><p>レコードが指定された値<b>に</b>変化したときにシナリオをトリガーします。</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>レコードが指定された値<b>から</b>変化したときにシナリオをトリガーします。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>レコードを視聴する場合は、レコードを視聴するWorkspaceを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>レコードを監視する場合は、監視するレコードタイプを選択します。</td>
    </tr>
    </tr>
    <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>選択した条件を満たすレコードのみを監視するフィルターを設定できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。 AND ルールを追加すると、複数のフィルターを使用できます。</p> <p>注意：既存のWorkfront Webhookではフィルターを編集できません。 Workfront イベントのサブスクリプションに別のフィルターを設定するには、現在の Webhook を削除し、新しい Webhook を作成します。</p> <p>イベントフィルターについて詳しくは、Workfront モジュールの「Workfront &gt; [!UICONTROL Watch Events] modules</a>」の「<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref"> イベントサブスクリプションフィルター」を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Objects to watch]</td>
      <td>レコードの新規作成、 更新、新規作成および更新、削除を監視するかどうかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Exclude updates made by this connection]</p>
      </td>
      <td>このオプションを有効にすると、このモジュールが使用する接続によって変更が行われた場合にシナリオがトリガーされなくなります。 これにより、このシナリオがトリガーアクションを実行した場合に、シナリオの別のインスタンスがトリガーされるのを防ぎます。</td> 
    </tr>
  </tbody>
</table>

このモジュールで高度なロジックを使用する例については、[監視イベントモジュールの高度なロジックの例](#example-of-advanced-logic-in-the-watch-events-module)を参照してください。

### アクション

* [レコードタイプの削除](#delete-a-record-type)
* [カスタム AI呼び出しを行う](#make-a-custom-api-call)

#### レコードタイプの削除

このアクションモジュールは、Workfront Planningの1つのレコードタイプをIDで削除します。

>[!WARNING]
>
>Workfront Planningでレコードタイプを削除すると、レコードタイプテーブル内のすべてのレコードも削除されます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>削除するレコードタイプのIDを入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

#### カスタム API 呼び出しの実行

このモジュールは、[!DNL Adobe Workfront Planning] API に対してカスタム API 呼び出しを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>相対パスを入力します <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
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
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>クエリ文字列に追加するキーと値のペアごとに、「<b>項目を追加</b>」をクリックして、キーと値を入力します。</p>
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


### 検索

#### レコードの検索

このアクションモジュールは、指定した条件に基づいてレコードのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>検索するレコードを含むWorkspaceを入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>検索するレコードタイプを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record Fields]</p>
      </td>
      <td>検索で使用する各フィールドについて、そのフィールドを見つけ、演算子を選択し、検索する値を入力またはマッピングします。 選択したレコードタイプに基づいてフィールドを使用できます。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Condition for filters]</p>
      </td>
      <td>フィルターの条件を選択します。<ul><li><b>AND</b><p>モジュールは、選択したフィールド値の<b>all</b>を満たすレコードを返します。</p></li><li><b>または</b><p>モジュールは、選択したフィールド値の<b>any</b>を満たすレコードを返します。</p></li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Limit]</p>
      </td>
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
    </tr>
  </tbody>
</table>


### 未分類


#### レコードの作成

このアクションは、Workfront計画で1つのレコードを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>作成するレコードのタイプを入力またはマッピングします。 使用可能なレコードタイプは、Workfront Planning アカウントに基づいています。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>新しいレコードの値を入力します。 これらのフィールドは、選択したレコードタイプに基づきます。</td> 
    </tr>
    <tr>
  </tbody>
</table>

### レコードの削除

このアクションモジュールは、Workfront Planningで指定されたレコードを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>削除するレコードの ID を入力またはマッピングします。</td> 
    </tr>
  </tbody>
</table>

### レコードを取得

このアクションモジュールは、[!DNL Adobe Workfront Planning] から、ID で指定された、1 つのレコードを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record ID]</td>
      <td>取得するレコードの ID を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

### レコードタイプ別にレコードの取得

このアクションモジュールは、指定されたタイプのすべてのレコードを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>取得するレコードを含むワークスペースを選択またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>取得するレコードのタイプを選択します。</td>
    </tr>
    <!--
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td>
    </tr>
    -->
  </tbody>
</table>

### レコードタイプの取得

このアクションモジュールは、[!DNL Adobe Workfront Planning] アカウント内のレコードタイプのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>取得するレコードタイプを含むワークスペースを選択またはマッピングします。</td>
    </tr>
  </tbody>
</table>

### レコードの更新

このアクションは、Workfront Planningの1つのレコードを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Workfront Planning] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >[!DNL Adobe Workfront Planning]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>更新するレコードのタイプを入力またはマッピングします。 使用可能なレコードタイプは、Workfront Planning アカウントに基づいています。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>レコードに含める新しい値を入力します。 これらのフィールドは、選択したレコードタイプに基づきます。</td> 
    </tr>
    <tr>
  </tbody>
</table>


## 読み取り可能な`record-types`の分類にJSONataを使用

次のJSONata式は、レコードタイプの内訳を示す、人間が読み取り可能なPlanning クエリの出力を作成します。 これにより、レコードタイプ名、フィールド名、およびフィールドオプション名（該当する場合）が名前で読みやすくなり、構造の残りの部分はそのまま維持されます。

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

JSONata モジュールの使用について詳しくは、[JSONata モジュール ](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md)を参照してください。

## 監視イベントモジュールの高度なロジックの例

これは、Workfront計画/監視イベントモジュールを使用する際に高度なロジックが実行するフォーマットの例です。

```
[
  {
    "fieldName": "recordTypeId",
    "fieldValue": "Rt68c886502d4b5554ee80896b",
    "comparison": "eq",
    "state": "newState"
  },
  {
    "fieldName": "data",
    "fieldValue": {
      "F68c886502d4b5554ee808975": "planning"
    },
    "comparison": "eq",
    "state": "newState"
  },
  {
    "fieldName": "data",
    "fieldValue": {
      "F68c886502d4b5554ee808975": "active"
    },
    "comparison": "eq",
    "state": "newState"
  }
]
```

Watch Event モジュールで高度なロジックを使用する場合は、次の点を考慮してください。

* 最初の`"fieldvalue":` エントリは、URLから取得した計画レコードタイプ IDです。 この例では、計画レコードタイプ IDは`Rt68c886502d4b5554ee80896b`です。
* 計画データは`data `という名前の配列内で返されます。この例では`"fieldName": "data"`と表示されます。
* 計画フィールド名は、`F`で始まるIDとして返されます。
* この例は`OR` フィルターコネクタに対して評価しているため、同じフィールド （`F68c886502d4b5554eec808975`）に2つのエントリがあります。  モジュールがフィルタリング対象にしている2つのドロップダウンオプションは`"planning"`と`"active"`です。

