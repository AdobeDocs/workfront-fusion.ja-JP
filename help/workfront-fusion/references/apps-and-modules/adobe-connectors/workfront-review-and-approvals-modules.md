---
title: Adobe Workfrontのコンテンツと承認のモジュール
description: Adobe Workfrontのコンテンツと承認モジュールを使用すると、承認の詳細の取得、アセットに関する意思決定、承認参加者の追加または削除、承認ステージの追加または更新、ステージのロックまたはロック解除、カスタム API呼び出しの実行を行うことができます。
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8b031ed2093d4844f05c52db9fc79ce9e7e4b85c
workflow-type: tm+mt
source-wordcount: 3743
ht-degree: 17%

---

# Adobe Workfrontの統合レビューと承認のモジュール

Adobe Workfrontの統合レビューと承認のモジュールを使用すると、承認の詳細の取得、アセットに関する意思決定、承認参加者の追加または削除、承認ステージの追加または更新、ステージのロックまたはロック解除、カスタム API呼び出しの実行を行うことができます。

Workfrontの統合レビューと承認について詳しくは、Workfront ドキュメントの[統合レビューと承認の概要](https://experienceleague.adobe.com/en/docs/workfront/using/review-and-approve-work/document-approvals-overview)を参照してください。

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

Workfront コンテンツと承認にアクセスするには、次の情報が必要です。

* Adobe クラウドストレージをサポートするWorkfrontのバージョンを使用している必要があります。 お客様の組織がまだサポートされているバージョンを使用していない場合は、Adobe アカウント担当者にお問い合わせください。

## Adobe Workfront Unified Review and Approvalsに接続


1. Adobe Workfront Unified Review and Approvals モジュールで、Connection フィールドの横にある&#x200B;**Add**&#x200B;をクリックします。
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

   Workfront Unified Review and Approvalsにログインしていない場合は、ログイン画面が表示されます。 ログイン後、接続を許可できます。

## Adobe Workfrontの統合レビューと承認のモジュール

Workfront モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加の Workfront フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。


![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [検索](#searches)
* [その他](#other)

### アクション

* [参加者の追加または更新](#add-or-update-participants)
* [テンプレートの一括削除](#bulk-delete-templates)
* [テンプレートの作成](#create-a-template)
* [承認の作成](#create-an-approval)
* [ステージを作成](#create-stages)
* [ステージでの決定の削除](#delete-a-decision-on-a-stage)
* [ステージの削除](#delete-a-stage)
* [テンプレートを削除](#delete-a-template)
* [#承認の削除](#delete-an-approval)
* [決定の削除](#delete-decisions)
* [参加者を削除](#delete-participants)
* [ステージをロック](#lock-a-stage)
* [決定を下す](#make-a-decision)
* [ステージで決定する](#make-a-decision-on-a-stage)
* [ステージの参加者にリマインドする](#remind-a-participant-on-a-stage)
* [参加者に通知](#remind-participant)
* [未決定の参加者に通知](#remind-undecided-participants)
* [ステージ上の未決定の参加者にリマインドする](#remind-undecided-participants-on-a-stage)
* [ステージのロック解除](#unlock-a-stage)
* [ステージの更新](#update-a-stage)
* [テンプレートの更新](#update-a-template)
* [すべてのステージを更新](#update-all-stages)


#### 参加者の追加または更新

このアクションモジュールは、承認のデフォルトステージに参加者を追加または更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>ドキュメント ID</p>
      </td>
      <td>参加者を追加または更新するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージへの参加者の追加</p>
      </td>
      <td>参加者を追加する各ステージについて、<b>項目を追加</b>をクリックし、ステージに入ります。<p> 次に、ステージに追加する各参加者について、<b>項目を追加</b>をクリックし、参加者の詳細を入力します。</p>
      <ul>
      <li><b>参加者ID</b><p>参加者のIDを入力またはマッピングします。</p></li>
      <li><b>参加者タイプ</b><p>参加者がユーザーかチームかを選択します。</p></li>
      <li><b>参加者の役割</b><p>参加者が承認者かレビュアーかを選択します。</p></li>
      </ul> 
      </td> 
      </tr>
  </tbody>
</table>

#### テンプレートの一括削除

このモジュールは、指定した承認テンプレートを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>テンプレート ID</p></td>
      <td>削除する各テンプレートについて、<b>項目を追加</b>をクリックし、テンプレート IDを入力します。</td> 
      </tr>
  </tbody>
</table>

#### テンプレートの作成

このアクションモジュールは、承認テンプレートを作成します

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>名前</p></td>
      <td>テンプレートの名前を入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>会社 ID</p></td>
      <td>会社スコープをテンプレートに追加する場合は、会社IDを入力するか、マッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ</p>
      </td>
      <td>追加する各ステージについて、<b>項目を追加</b>をクリックし、ステージデータを入力します。<p>詳細については、この記事の「<a href="#stages-fields" class="MCXref xref" > ステージフィールド </a>」を参照してください。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>共有対象</p></td>
      <td>テンプレートを共有する各ユーザーについて、<b>項目を追加</b>をクリックし、ユーザーIDと必要なアクセスレベルをクリックします。</td> 
      </tr>
  </tbody>
</table>

#### 承認の作成

このアクションモジュールは、ステージデータやテンプレートを含むAdobe クラウドストレージ上のドキュメントの承認を作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>承認を作成するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ</p>
      </td>
      <td>追加する各ステージについて、<b>項目を追加</b>をクリックし、ステージデータを入力します。<p>詳細については、この記事の「<a href="#stages-fields" class="MCXref xref" > ステージフィールド </a>」を参照してください。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>テンプレート ID</p></td>
      <td>この承認に使用するテンプレートのIDを入力するか、マッピングします。</td> 
      </tr>
  </tbody>
</table>

#### ステージを作成

このアクションモジュールは、指定されたステージデータを使用して承認を作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>ステージを作成または更新するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ</p>
      </td>
      <td>追加する各ステージについて、<b>項目を追加</b>をクリックし、ステージデータを入力します。<p>詳細については、この記事の「<a href="#stages-fields" class="MCXref xref" > ステージフィールド </a>」を参照してください。 </p> </td> 
      </tr>
    </tr>
     <tr>
      <td role="rowheader"><p>テンプレート ID</p></td>
      <td>ステージを作成するアセットのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### ステージでの決定の削除

このモジュールは、指定されたステージから現在のユーザーの決定を削除します。 現在のユーザーは、このモジュールで使用される接続で資格情報が使用されるユーザーです。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>決定を削除するドキュメントのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ステージ ID</p></td>
      <td>削除するステージのIDを入力またはマッピングします。</td> 
      </tr>
   </tbody>
</table>


#### ステージの削除

このアクションモジュールは、指定されたステージを承認から削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>ステージを削除するドキュメントのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ステージ ID</p></td>
      <td>削除するステージのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### テンプレートを削除

このモジュールは、指定した承認テンプレートを削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>テンプレート ID</p></td>
      <td>削除するテンプレートのIDを入力するか、マッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 承認の削除

このアクションモジュールは、指定されたドキュメントの承認を削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>承認を削除するドキュメントのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 決定の削除

このモジュールは、指定されたステージから現在のユーザーの決定を削除します。 現在のユーザーは、このモジュールで使用される接続で資格情報が使用されるユーザーです。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>決定を削除するドキュメントのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 参加者を削除

このアクションモジュールは、承認から参加者を削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>参加者を削除するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>参加者タイプ</p>
      </td>
      <td>参加者がユーザーかチームかを選択します。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>参加者ID</p>
      </td>
      <td>参加者のIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### ステージをロック

このアクションモジュールは、指定された承認ステージをロックし、ステージを非アクティブに設定します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>ロックするアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ ID</p>
      </td>
      <td>ロックするステージのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 決定を下す

このアクションモジュールは、決定を承認または承認ステージに適用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>ロックするアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>決定</p></td>
      <td>承認またはステージに適用する決定を選択します。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ ID</p>
      </td>
      <td>決定を適用する各ステージについて、<b>項目を追加</b>をクリックし、ステージ IDを入力します。</td> 
      </tr>
  </tbody>
</table>

#### ステージで決定する

このモジュールは、指定されたステージに決定を適用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>決定する文書のIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ステージ ID</p></td>
      <td>決定を行うステージのIDを入力またはマッピングします。</td> 
      </tr>
    <tr>
      <td role="rowheader"><p>決定</p></td>
      <td>このステージに適用する決定を選択します。</td> 
      </tr>
  </tbody>
</table>

#### ステージの参加者にリマインドする

このモジュールは、特定のステージの特定の参加者にリマインダーを送信します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>リマインダーを送信するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ ID</p>
      </td>
      <td>リマインダーを送信するステージのIDを入力またはマッピングします。</td> 
      </tr>
    </tr>
     <tr>
      <td role="rowheader"><p>参加者ID</p></td>
      <td>リマインダーを送信する参加者のIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 参加者に通知

このモジュールは、指定した参加者にリマインダー通知を送信します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>リマインダーを送信するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>参加者ID</p>
      </td>
      <td>リマインドする参加者のIDを入力またはマッピングします。</td> 
      </tr>
      <tr>
      <td role="rowheader">
        <p>参加者タイプ</p>
      </td>
      <td>リマインドする参加者のタイプを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>参加者の役割</p>
      </td>
      <td>リマインドする参加者の役割を入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 未決定の参加者に通知

このモジュールは、指定された承認に対して、すべての未決定の参加者にリマインダー通知を送信します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>リマインダーを送信するアセットのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### ステージ上の未決定の参加者にリマインドする

このモジュールは、ステージ上のすべての未決定の参加者にリマインダー通知を送信します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>リマインダーを送信するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ ID</p>
      </td>
      <td>リマインダーを送信するステージのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### ステージのロック解除

このアクションモジュールは、指定された承認ステージのロックを解除し、ステージをアクティブに設定します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>ロックを解除するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ ID</p>
      </td>
      <td>ロックするステージのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>


#### ステージの更新

このアクションモジュールは、指定されたステージのフィールドを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>決定する文書のIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ステージ ID</p></td>
      <td>決定を行うステージのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ステージ名</p></td>
      <td>テンプレートの名前を入力またはマッピングします。</td> 
      </tr>
      <td role="rowheader">
        <p>その他のフィールド</p>
      </td>
      <td>ステージのフィールドにデータを入力します。<p>詳しくは、この記事の「<a href="#stages-fields" class="MCXref xref" > ステージフィールド </a>」を参照してください。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>共有対象</p></td>
      <td>テンプレートを共有する各ユーザーについて、<b>項目を追加</b>をクリックし、ユーザーIDと必要なアクセスレベルをクリックします。</td> 
      </tr>
  </tbody>
</table>

#### テンプレートの更新

このモジュールは、指定した承認テンプレートのフィールドを更新します。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>テンプレート ID</p></td>
      <td>テンプレートの名前を入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>名前</p></td>
      <td>更新するテンプレートのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>会社 ID</p></td>
      <td>会社スコープをテンプレートに追加する場合は、会社IDを入力するか、マッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ</p>
      </td>
      <td>追加する各ステージについて、<b>項目を追加</b>をクリックし、ステージデータを入力します。<p>詳細については、この記事の「<a href="#stages-fields" class="MCXref xref" > ステージフィールド </a>」を参照してください。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>共有対象</p></td>
      <td>テンプレートを共有する各ユーザーについて、<b>項目を追加</b>をクリックし、ユーザーIDと必要なアクセスレベルをクリックします。</td> 
      </tr>
  </tbody>
</table>

#### すべてのステージを更新

このモジュールは、既存の承認上のすべてのステージを、指定されたステージデータに置き換えます。 ドキュメントは編集可能な状態である必要があります。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>ステージを更新するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>ステージ</p>
      </td>
      <td>更新する各ステージについて、<b>項目を追加</b>をクリックし、ステージデータを入力します。<p>詳細については、この記事の「<a href="#stages-fields" class="MCXref xref" > ステージフィールド </a>」を参照してください。 </p> </td> 
      </tr>
  </tbody>
</table>

### 検索

* [テンプレートを入手](#get-a-template)
* [承認の詳細を取得](#get-approval-details)
* [複数の承認を取得](#get-multiple-approvals)
* [提案された承認を取得](#get-suggested-approvals)
* [推奨される参加者を取得](#get-suggested-participants)
* [ボットのリストアップ](#list-bots)
* [テンプレートをリスト表示](#list-templates)
* [AI ブランドレビュアーを検索](#search-ai-brand-reviews)


#### テンプレートを入手

このモジュールは、指定された承認テンプレートを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>テンプレート ID</p></td>
      <td>提案された承認参加者を取得する文書のIDを入力またはマッピングします。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           返されるテンプレートの最大数
         </td>
         <td>
              各シナリオの実行サイクル中に、モジュールが返すテンプレートの最大数を入力またはマッピングします。 
         </td>
       </tr>
  </tbody>
</table>

#### 承認の詳細を取得

この検索モジュールは、アセットの承認詳細を取得します。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>ドキュメント</p>
      </td>
      <td>承認詳細を取得するアセットのIDを入力またはマッピングします。</td> 
      </tr>
  </tbody>
</table>

#### 複数の承認を取得

このモジュールは、特定のタイプのドキュメントのリストに対する承認の詳細を取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>承認の詳細を取得する各ドキュメントについて、<b>項目を追加</b>をクリックし、ドキュメント IDを入力します。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           返される結果の最大数
         </td>
         <td>
              各シナリオ実行サイクル中にモジュールが返す結果の最大数を入力またはマッピングします。 
         </td>
       </tr>
  </tbody>
</table>

#### 提案された承認を取得

このモジュールは、以前のドキュメントバージョンから提案された承認ペイロードを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>提案された承認を取得するドキュメントのIDを入力またはマッピングします。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           返される承認の最大数
         </td>
         <td>
              シナリオ実行サイクルごとに、モジュールから返される最大承認数を入力またはマッピングします。 
         </td>
       </tr>
  </tbody>
</table>

#### 推奨される参加者を取得

このモジュールは、以前の文書の承認の承認から参加者の提案を返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ドキュメント ID</p></td>
      <td>提案された承認参加者を取得する文書のIDを入力またはマッピングします。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           返される参加者の最大数
         </td>
         <td>
              各シナリオ実行サイクル中にモジュールが返す最大参加者数を入力またはマッピングします。 
         </td>
       </tr>
  </tbody>
</table>

#### ボットのリストアップ

このモジュールは、ページ分割されたボットアカウントのリストを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ページ</p></td>
      <td>返す結果のページを入力またはマッピングします。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           返される結果の最大数
         </td>
         <td>
              各シナリオ実行サイクル中にモジュールが返す結果の最大数を入力またはマッピングします。 
         </td>
       </tr>
  </tbody>
</table>

#### リストテンプレート

このモジュールは、現在のユーザーが使用できるすべての承認テンプレートのリストを返します。 現在のユーザーは、このモジュールで使用される接続で資格情報が使用されるユーザーです。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
   </tbody>
</table>

#### AI ブランドのレビューを検索

このモジュールは、承認の一環としてドキュメントバージョン用に生成されたAI ブランドレビュー結果を返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>ボットユーザーID</p></td>
      <td>レビューを検索するボットのユーザーIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>親ドキュメント ID</p></td>
      <td>レビューを検索する親ドキュメントのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ドキュメントのバージョン ID</p></td>
      <td>リマインダーを送信するアセットのIDを入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ステージ ID</p></td>
      <td>ステージ IDを入力またはマッピングして、結果を承認の特定のステージに制限します。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>ページ</p></td>
      <td>ページ番号を入力またはマッピングして、そのページに結果を制限します。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           返されるレビューの最大数
         </td>
         <td>
              シナリオ実行サイクルごとにモジュールが返すレビューの最大数を入力またはマッピングします。 
         </td>
       </tr>
  </tbody>
</table>

### その他

* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [ステージフィールド](#stages-fields)


#### カスタム API 呼び出しの実行

このモジュールは、Adobe Workfront Unified Review and Approvals APIに対するカスタム API呼び出しを行います。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe Workfront Unified Review and Approvalsへの接続の作成手順については、この記事の「<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >Adobe Workfront Unified Review and Approvalsへの接続</a>」を参照してください。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>相対パス</p>
      </td>
      <td>
        <p><code>https://workfront.adobe.io</code> からの相対パスを入力します。 例： <code>/unified-approvals/public/api/v1/approvals/&lt;ASSET_TYPE&gt;/&lt;ASSET_ID&gt;</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>メソッド</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">ヘッダー</td>
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



#### ステージフィールド

ステージの設定時には、次のフィールドを使用できます。 すべてのモジュールですべてのフィールドを使用できるわけではありません。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">ステージ名</td>
      <td>ステージの名前を入力またはマッピングします。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>期限日</p></td>
      <td>期限が特定の日付の場合は、日付を入力またはマッピングします。</td> 
      </tr>
  </tbody>
     <tr>
      <td role="rowheader"><p>期限切れ営業日</p></td>
      <td>期限が特定の営業日後の場合は、日数を入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>納期</p></td>
      <td>期限が特定の時間の場合は、時間を入力またはマッピングします。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>参加者</p></td>
      <td>ステージに追加する各参加者について、<b>項目を追加</b>をクリックし、参加者の詳細を入力します。      
      <ul>
      <li><b>参加者ID</b><p>参加者のIDを入力またはマッピングします。</p></li>
      <li><b>参加者タイプ</b><p>参加者がユーザーかチームかを選択します。</p></li>
      <li><b>参加者の役割</b><p>参加者が承認者かレビュアーかを選択します。</p></li>
      </ul> 
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>自動ロック有効</p></td>
      <td>ステージを自動ロックするかどうかを指定します。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>決定ルール</p></td>
      <td>ステージに対して1つの決定のみを必要とするかどうかを選択します。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>親ID / 親ステージ ID</p></td>
      <td>ステージに追加する親ステージごとに、<b>項目を追加</b>をクリックし、親IDを入力します。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>トリガー</p></td>
      <td>この承認ステージのトリガーを設定するには、<b>Add item</b>をクリックし、トリガーの詳細を入力します。      <ul>
      <li><b>タイプ</b><p>「<b> アクティベーション </b>」を選択</p></li>
      <li><b>条件</b><p>承認が作成されたステージをトリガーするか、別のステージが完了したタイミングを選択します。</p></li>
      <li><b>ステージ</b><p>トリガーに追加する各ステージについて、<b>Add item</b>をクリックし、ステージ IDを入力またはマッピングします。</p></li>
      <li><b>決定</b><p>トリガーに追加する各決定について、<b>項目を追加</b>をクリックし、決定を入力またはマッピングします。</p></li>
      </ul> 
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>カスタムメッセージ</p></td>
      <td>ステージのカスタムメッセージを入力またはマッピングします。</td> 
      </tr>
</table>

