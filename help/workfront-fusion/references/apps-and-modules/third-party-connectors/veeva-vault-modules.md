---
title: Veeva Vault モジュール
description: Adobe Workfront Fusion のシナリオでは、Veeva Vault を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 2ef967b6-0a69-4801-8574-5f17c9ce991d
source-git-commit: 323e7d10795991bbcb6c1439db0af90e4331e687
workflow-type: tm+mt
source-wordcount: '3683'
ht-degree: 15%

---

# Veeva Vault モジュール

Adobe Workfront Fusion のシナリオでは、Veeva Vault を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

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

Veeva Vault モジュールを使用するには、Veeva Vault アカウントが必要です。

## Veeva Vault のWorkfront Fusion への接続

Veeva Vault モジュール内から直接 Veeva Vault アカウントへの接続を作成できます。

接続を作成する際に、パスワードを使用するか、OAuth2 認証を使用するかを選択できます。

### ユーザー名とパスワードを使用して Veeva Vault に接続します

1. 任意の Veeva Vault モジュールで、「接続」フィールドの横にある **追加** をクリックします。
1. 「**接続タイプ**」フィールドで「`Veeva Username Password`」を選択します。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">接続名</td> 
       <td> <p>接続に名前を入力します。</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">ユーザー名</td>
        <td>
          <p>Veeva Vault アカウントのユーザー名を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">パスワード</td>
        <td>
          <p>Veeva Vault アカウントのパスワードを入力します。</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">Vault の DNS</td> 
       <td>Veeva Vault DNS （ドメイン名）を入力します。</p><p>Veeva Vault DNS を見つけるには、Veeva Vault へのアクセスに使用する URL を調べます。</p>例えば、URL <code>https://my-dns.veevavault.com</code> では、DNS は <code>my-dns</code> です。 URL 全体を入力する必要はありません。</td> 
      </tr> 
     </tbody> 
    </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

### OAuth2 認証を使用した Veeva Vault への接続

1. 任意の Veeva Vault モジュールで、「接続」フィールドの横にある **追加** をクリックします。
1. 「**接続タイプ**」フィールドで「`Veeva Oauth 2`」を選択します。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">接続名</td> 
       <td> <p>接続に名前を入力します。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader">認証サーバープロバイダー</td> 
       <td> <p>この認証に使用するプロバイダーを選択します。</p> 
       <p><b> メモ：</b> 認証サーバープロバイダーとしてAzureが選択されている場合、Veeva Vault はAzure AD クライアント資格情報を使用します。</p>
       </td> 
      </tr> 
      <tr> 
       <td role="rowheader">ping ホスト</td> 
       <td> <p>PingFederate を使用している場合は、ping ホストを入力します。</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">範囲</td>
        <td>
          <p>この接続のスコープを入力してください。 範囲は、<code>{Application ID URI}/.default</code> の形式にする必要があります。 アプリケーション ID URI は、権限を公開するリソースまたはアプリに属している必要があります。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">テナント ID</td>
        <td>
          <p>認証サーバープロバイダーにAzure AD/Microsoft Entra ID を使用している場合は、この接続のテナント ID を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">クライアント ID</td>
        <td>
          <p>この接続で使用する Veeva Vault アプリケーションのクライアント ID を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">クライアントシークレット</td>
        <td>
          <p>この接続で使用する Veeva Vault アプリケーションのクライアントシークレットを入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">プロファイル ID</td>
        <td>
          <p>OAuth2 / Open ID Connect プロファイルの ID を入力します。</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">Vault の DNS</td> 
       <td>Veeva Vault DNS （ドメイン名）を入力します。</p><p>Veeva Vault DNS を見つけるには、Veeva Vault へのアクセスに使用する URL を調べます。</p>例えば、URL <code>https://my-dns.veevavault.com</code> では、DNS は <code>my-dns.veevavault.com</code> です。 </td> 
      </tr> 
      <tr>
        <td role="rowheader">セッションの有効期限（分）</td>
        <td>
          <p>セッションの有効期限を分単位で入力します。</p>
        </td>
      </tr>
     </tbody> 
    </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。


## Veeva Vault モジュールとそのフィールド

Workfront Fusion で Veeva Vault モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の Veeva Vault フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ドキュメント](#document)
* [オブジェクト](#object)
* [その他](#other)

### ドキュメント

* [1 つのドキュメントの作成](#create-a-single-document)
* [単一ドキュメントの関係の作成](#create-a-single-document-relationship)
* [複数の注釈を作成](#create-multiple-annotations)
* [複数のドキュメントの作成](#create-multiple-documents)
* [複数ドキュメントの関係の作成](#create-multiple-document-relationships)
* [1 つのドキュメントの削除](#delete-a-single-document)
* [単一ドキュメントの関係の削除](#delete-a-single-document-relationship)
* [複数の注釈を削除](#delete-multiple-annotations)
* [複数ドキュメントの関係の削除](#delete-multiple-document-relationships)
* [ファイルのダウンロード](#download-file)
* [ドキュメントのエクスポート](#export-documents)
* [1 つのドキュメントの取得](#get-a-single-document)
* [ドキュメントの注釈を取得](#get-document-annotations)
* [ドキュメントの関係の取得](#get-document-relationships)
* [ユーザーアクションの開始](#initiate-user-action)
* [ドキュメントのリスト](#list-documents)
* [ドキュメントのエクスポート結果の取得](#retrieve-document-export-results)
* [1 つのドキュメントの更新](#update-a-single-document)
* [複数の注釈を更新](#update-multiple-annotations)
* [複数のドキュメントの更新](#update-multiple-documents)

#### 1 つのドキュメントの作成

このモジュールは、単一のドキュメント、バインダーまたはテンプレートを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートを作成するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>フィールドを選択</p> </td> 
   <td> <p>データを入力するフィールドを選択し、それらのフィールドにデータを入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一ドキュメントの関係の作成

このアクションモジュールは、2 つのドキュメント間の関係を作成します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>関係を開始するドキュメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>関係を作成するバージョンの ID を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ターゲットドキュメント ID</p> </td> 
   <td> <p>関係が指すドキュメントの ID を入力します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Target のメジャーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これは地点の前の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>ターゲットのマイナーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これは点の後の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>関係タイプ</p> </td> 
   <td> <p>作成する関係のタイプを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 複数の注釈を作成

このアクションモジュールを使用すると、最大 500 個の注釈を作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>注釈</p> </td> 
   <td> <p>追加する注釈ごとに、「<b> 項目を追加 </b>」をクリックし、この記事の <a href="#annotation-fields" class="MCXref xref"> 注釈フィールド </a> に記載されているデータを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

##### 注釈フィールド

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">注釈タイプ </td> 
   <td> <p>作成する注釈のタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>この注釈に使用するプレースマークのタイプを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ページ番号</p> </td> 
   <td> <p>この注釈を表示するページ番号を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>X 座標</p> </td> 
   <td> <p>プレースマークの X 座標を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Y 座標</p> </td> 
   <td> <p>プレースマークの Y 座標を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>幅</p> </td> 
   <td> <p>プレースマークの幅を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>高さ</p> </td> 
   <td> <p>プレースマークの高さを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>スタイル</p> </td> 
   <td> <p>プレースマークのスタイルを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>リファレンス</p> </td> 
   <td> <p>参照を使用すると、注釈で外部ソースを参照できます。 注釈に追加する参照ごとに、「<b> 項目を追加 </b> をクリックして、参照のタイプ、ドキュメントバージョン ID および注釈を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>フィールドを選択</p> </td> 
   <td> <p>値を指定するフィールドを選択してから、各フィールドに値を入力してください。 使用できるフィールドは、注釈のタイプによって異なります。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### 複数のドキュメントの作成

このモジュールは、CSV ファイルを使用して複数のドキュメントまたはテンプレートを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>テンプレートとドキュメントのどちらを作成するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>ファイルデータ</p> </td> 
   <td> <p>ドキュメントの作成に使用する CSV ファイルをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 複数ドキュメントの関係の作成

このアクションモジュールは、複数のドキュメントの関係を設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>入力タイプ</p> </td> 
   <td> <p>これらの関係を作成するために指定する入力のタイプを選択します。</p> <ul><li>CSV</li><li>JSON</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ファイルデータ</p> </td> 
   <td> <p>CSV ファイルを使用する場合は、CSV ファイルデータを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>関係データ</p> </td> 
   <td> <p>JSON を使用している場合は、追加する関係ごとに「<b> 項目を追加 </b>」をクリックし、この記事の <a href="#relationship-fields" class="MCXref xref"> 関係フィールド </a> に記載されているデータを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

##### 関係フィールド

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Source ドキュメント ID </td> 
   <td> <p>関係を開始するドキュメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Sourceのメジャーバージョン</p> </td> 
   <td> <p>ソースドキュメントのメジャーバージョンを入力します。 これは地点の前の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Sourceのマイナーバージョン</p> </td> 
   <td> <p>ソースドキュメントのメジャーバージョンを入力します。 これは点の後の数字です。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ターゲットドキュメント ID</p> </td> 
   <td> <p>関係が指すドキュメントの ID を入力します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Target のメジャーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これは地点の前の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>ターゲットのマイナーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これは点の後の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>関係タイプ</p> </td> 
   <td> <p>作成する関係のタイプを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 1 つのドキュメントの削除

このモジュールは、単一のドキュメント、バインダーまたはテンプレートを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートを削除するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント ID/バインダー ID/テンプレート名</p> </td> 
   <td> <p>削除する項目を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一ドキュメントの関係の削除

このアクションモジュールは、ドキュメントから関係を削除します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>削除する関係のソースドキュメント ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>関係を削除するバージョンの ID を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>関係 ID</p> </td> 
   <td> <p>削除する関係の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 複数の注釈を削除

このアクションモジュールは注釈を削除します。 Veeva Vault で注釈を削除するには、ユーザーに権限が必要です。 最大 500 個の注釈を削除できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>注釈</p> </td> 
   <td> <p>削除する注釈ごとに、「<b> 項目を追加 </b>」をクリックし、次のフィールドを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID</p> </td> 
   <td> <p>削除する注釈の ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント バージョン ID</p> </td> 
   <td> <p>削除する注釈を含むドキュメントのバージョン番号を入力またはマップします。</td> 
  </tr> 
 </tbody> 
</table>

#### 複数ドキュメントの関係の削除

このアクションモジュールは、複数のドキュメントから関係を削除します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>入力タイプ</p> </td> 
   <td> <p>これらの関係を削除するために指定する入力のタイプを選択します。</p> <ul><li>CSV</li><li>JSON</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ファイルデータ</p> </td> 
   <td> <p>CSV ファイルを使用する場合は、CSV ファイルデータを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>関係データ</p> </td> 
   <td> <p>JSON を使用している場合は、追加する各関係に対して、「<b> 項目を追加 </b>」をクリックし、関係 ID を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### ファイルをダウンロード

このモジュールは、Veeva Vault からドキュメント、ドキュメントバージョンまたはテンプレートをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメントとテンプレートのどちらをダウンロードするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ダウンロードタイプ</p> </td> 
   <td> <p>ドキュメントまたはドキュメントバージョンのどちらをダウンロードするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント ID/テンプレート名</p> </td> 
   <td> <p>ドキュメントの ID またはダウンロードするテンプレートの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメントのチェックアウト</p> </td> 
   <td> <p>ドキュメントをダウンロードする場合、このオプションを有効にすると、ドキュメントをダウンロードする前にチェックアウトされます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>ドキュメントのバージョンをダウンロードする場合は、ダウンロードするバージョンを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントのエクスポート

このモジュールでは、ソース、レンディション、テキストなど、指定したドキュメントを書き出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートを削除するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ソース</p> </td> 
   <td> <p>書き出しにソースファイルを含めるには、このオプションを有効にします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>レンディション</p> </td> 
   <td> <p>書き出しにレンディションファイルを含めるには、このオプションを有効にします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>すべてのバージョン</p> </td> 
   <td> <p>すべてのバージョンのドキュメントファイルをエクスポートに含めるには、このオプションを有効にします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>テキスト</p> </td> 
   <td> <p>ソースドキュメントのテキストをエクスポートに含めるには、このオプションを有効にします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 1 つのドキュメントの取得

このモジュールは、単一のドキュメント、バインダーまたはテンプレートのメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、テンプレートのデータを取得するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント ID/バインダー ID/テンプレート名</p> </td> 
   <td> <p>データを取得するフィールドを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントの注釈を取得

このモジュールは、特定のドキュメントバージョンから注釈を取得します。 すべての注釈を取得することも、特定の注釈タイプのみを取得するように選択することもできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>注釈を取得するドキュメントを選択またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>注釈を取得するバージョンの ID を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される注釈の最大数</td> 
   <td>各シナリオ実行サイクルでモジュールが返す注釈の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントの関係の取得

このモジュールは、ドキュメントのすべての関係を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>関係を取得するドキュメントを選択またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>関係を取得するバージョンの ID を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される関係の最大数</td> 
   <td>各シナリオ実行サイクルでモジュールが返す関係の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーアクションの開始

このモジュールは、ドキュメントをレビュー用に送信したり、ドキュメントの状態を変更したりするなど、ドキュメントとバインダーに対するアクションを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメントに対してアクションを実行するか、バインダーに対してアクションを実行するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント/バインダー</p> </td> 
   <td> <p>アクションを実行するドキュメントまたはバインダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント バージョン/バインダーのバージョン</p> </td> 
   <td> <p>アクションを実行するドキュメントまたはバインダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>アクション</p> </td> 
   <td> <p>ドキュメントまたはバインダーに対して実行するアクションを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントのリスト

このモジュールには、選択したタイプのすべてのドキュメントが一覧表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダーまたはテンプレートを一覧表示するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントのエクスポート結果の取得

このモジュールは、以前にリクエストしたドキュメント書き出しの結果を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ジョブ ID</p> </td> 
   <td> <p>結果を返すジョブの ID を入力またはマッピングします。 </p> </td> 
  </tr> 
  </tbody> 
</table>

#### 複数の注釈を更新

このアクションモジュールは、最大 500 個の注釈を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>注釈</p> </td> 
   <td> <p>更新する注釈ごとに、「<b> 項目を追加 </b>」をクリックし、この記事の <a href="#annotation-fields" class="MCXref xref"> 注釈フィールド </a> に記載されているデータを入力します。</p> </td> 
  </tr> 
  </tbody> 
</table>

#### 複数のドキュメントの更新

このモジュールは、CSV ファイルを使用して複数のドキュメントまたはテンプレートを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>テンプレートとドキュメントのどちらを作成するかを選択</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>ファイルデータ</p> </td> 
   <td> <p>ドキュメントの作成に使用する CSV ファイルをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 1 つのドキュメントの更新

このモジュールは、1 つのドキュメント、バインダーまたはテンプレートを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、ドキュメント バージョン、バインダー、テンプレートのいずれを作成するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID/名前</p> </td> 
   <td> <p>テンプレートを更新する場合は、テンプレートの新しい名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>新しいテンプレート名</p> </td> 
   <td> <p>更新するオブジェクトの ID または名前を入力またはマップします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">  <p>フィールドを選択</p> </td> 
   <td> <p>データを入力するフィールドを選択し、それらのフィールドにデータを入力します。</td> 
  </tr> 
 </tbody> 
</table>

### オブジェクト

* [単一オブジェクトレコードの作成](#create-a-single-object-record)
* [単一のオブジェクトレコードの削除](#delete-a-single-object-record)
* [単一のオブジェクトの取得](#get-a-single-object)
* [オブジェクトレコードをリスト](#list-objects-records)
* [単一オブジェクトレコードの更新](#update-a-single-object-record)

#### 単一オブジェクトレコードの作成

このモジュールは、単一のオブジェクトレコードを作成、コピー、またはディープコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>レコードを作成またはコピーするか、またはレコードをディープコピーするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">移行モード</td> 
   <td>レコードを作成またはコピーする場合は、このオプションを有効にして、最小限の検証を使用して非初期状態のオブジェクトレコードを作成または更新し、非アクティブなレコードを作成し、<code>createdby_v</code> などの標準フィールドとシステム管理フィールドを設定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トリガーなし</td> 
   <td>true に設定され、マイグレーションモードが有効な場合、モジュールは、すべてのシステム、標準、カスタム SDKのトリガー、およびアクショントリガーをバイパスします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td><code>product__v</code>、<code>country__v</code>、<code>custom_object__c</code> など、オブジェクト名__v フィールドの値を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>レコードをディープコピーする場合は、コピーするレコードを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードフィールド</td> 
   <td>レコードをディープコピーする場合は、値を設定するフィールドを選択してから、それらの値を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一のオブジェクトレコードの削除

このモジュールは、単一のオブジェクト レコードを削除またはカスケード削除します。 カスケード レコードを削除すると、レコードとそのすべての子オブジェクトが削除されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>レコードを削除するか、レコードをカスケード削除するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td>削除するオブジェクトを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>削除するレコードの ID を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">外部 ID</td> 
   <td>レコード ID の代わりに、このユーザー定義のドキュメント外部 ID を使用できます。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一のオブジェクトの取得

このモジュールは、Vault 内の特定のオブジェクト レコードに設定されたメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td>メタデータを取得するオブジェクトを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>メタデータを取得するレコードの ID を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### オブジェクトレコードをリスト

このモジュールは、認証された Vault 内のすべての Vault オブジェクトを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ローカライズされたラベルの取得</p> </td> 
   <td> <p>「はい」を選択して、「label」および「label_plural」オブジェクトフィールドのローカライズされた（翻訳済み）文字列を取得します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

<!--#### Update a single object record-->

このモジュールは、既存のオブジェクトレコードのフィールドを更新します。

このモジュールは、単一のオブジェクトレコードを作成、コピー、またはディープコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>レコードを作成またはコピーするか、またはレコードをディープコピーするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">移行モード</td> 
   <td>このオプションを有効にすると、最小限の検証を使用して非初期状態のオブジェクトレコードを作成または更新したり、非アクティブなレコードを作成したり、<code>createdby_v</code> などの標準フィールドおよびシステム管理フィールドを設定したりできます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トリガーなし</td> 
   <td>移行モードが有効な場合、このオプションを有効にすると、システム、標準、カスタムのSDKトリガーおよびアクショントリガーがすべて回避されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td><code>product__v</code>、<code>country__v</code>、<code>custom_object__c</code> など、オブジェクト名__v フィールドの値を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>更新するレコードの ID を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">状態</td> 
   <td><code>X-VaultAPI-MigrationMode</code> が true に設定されている場合は、レコードのライフサイクル状態を指定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">状態ラベル</td> 
   <td><code>X-VaultAPI-MigrationMode</code> が true に設定されている場合は、レコードのライフサイクル状態タイプを指定します。 <code>base:object_lifecycle:</code> 形式を使用し、その後にオブジェクトの状態タイプを使用します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードフィールド</td> 
   <td>レコードをディープコピーする場合は、値を設定するフィールドを選択してから、それらの値を設定します。</td> 
  </tr> 
 </tbody> 
</table>

### その他

* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [VQL クエリの作成](#make-a-vql-query)
* [ログの読み取り](#read-logs)

#### カスタム API 呼び出しの実行

このアクションモジュールは、Veeva Vault API へのカスタム呼び出しを行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td><code>baseurl/api/v</code> を基準とした相対パスを入力します。  例えば、<code>/objects/documents</code> のようになります。<code>baseurl/api/v/</code> は既に含まれているため、含めないでください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メソッド</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ヘッダー</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">クエリ文字列</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">本文</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### VQL クエリの作成

このモジュールは、Vault クエリ言語（VQL）を使用してクエリを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>テンプレートとドキュメントのどちらを作成するかを選択</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>ファイルデータ</p> </td> 
   <td> <p>ドキュメントの作成に使用する CSV ファイルをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ログの読み取り

このモジュールは、監査記録からのデータを返します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva Vault のWorkfront Fusion への接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>監査タイプ</p> </td> 
   <td> <p>データを取得する監査タイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>開始日</p> </td> 
   <td> <p>取得する監査の開始日を入力またはマップします。</p><p>サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>終了日</p> </td> 
   <td> <p>取得する監査の終了日を入力またはマップします。</p><p>サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>結果の URL </p> </td> 
   <td> <p>結果の CSV をダウンロードする URL を取得する場合は、「CSV」を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
