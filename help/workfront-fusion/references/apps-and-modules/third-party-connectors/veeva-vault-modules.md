---
title: Veeva Vault モジュール
description: Adobe Workfront Fusionでは、Veeva Vaultを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 2ef967b6-0a69-4801-8574-5f17c9ce991d
source-git-commit: d64d894cfb0e1905c135cdf5ea39f11cd7a6e5f2
workflow-type: tm+mt
source-wordcount: '4125'
ht-degree: 14%

---

# Veeva Vault モジュール

Adobe Workfront Fusionでは、Veeva Vaultを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

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

## Veeva VaultとWorkfront Fusionの連携

Veeva Vault モジュール内から直接Veeva Vault アカウントへの接続を作成できます。

接続を作成する際に、パスワードを使用するか、OAuth2認証を使用するかを選択できます。

### ユーザー名とパスワードを使用してVeeva Vaultに接続

1. どのVeeva Vault モジュールでも、「接続」フィールドの横にある「**追加**」をクリックします。
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
       <td role="rowheader">Vault DNS</td> 
       <td>Veeva Vault DNS （ドメイン名）を入力します。</p><p>Veeva Vault DNSを見つけるには、Veeva Vaultへのアクセスに使用するURLを調べます。</p>例えば、URL <code>https://my-dns.veevavault.com</code>では、DNSは<code>my-dns</code>です。 URL全体を入力する必要はありません。</td> 
      </tr> 
     </tbody> 
    </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

### OAuth2認証を使用してVeeva Vaultに接続する

1. どのVeeva Vault モジュールでも、「接続」フィールドの横にある「**追加**」をクリックします。
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
       <p><b> メモ：</b> Veeva Vaultは、AzureがAuthorization Server Providerとして選択されている場合、Azure AD クライアント資格情報を使用します。</p>
       </td> 
      </tr> 
      <tr> 
       <td role="rowheader">Ping ホスト</td> 
       <td> <p>PingFederateを使用している場合は、ping ホストを入力します。</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">範囲</td>
        <td>
          <p>この接続の範囲を入力します。 範囲は<code>{Application ID URI}/.default</code>形式にする必要があります。 アプリケーション ID URIは、権限を公開しているリソースまたはアプリケーションに属している必要があります。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">テナント ID</td>
        <td>
          <p>認証サーバープロバイダーにAzure AD/Microsoft Entra IDを使用している場合は、この接続のテナント IDを入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">クライアント ID</td>
        <td>
          <p>この接続で使用するVeeva Vault アプリケーションのクライアント IDを入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">クライアントシークレット</td>
        <td>
          <p>この接続で使用するVeeva Vault アプリケーションのクライアント秘密鍵を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">プロファイル ID</td>
        <td>
          <p>OAuth2 / Open ID Connect プロファイルのIDを入力します。</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">Vault DNS</td> 
       <td>Veeva Vault DNS （ドメイン名）を入力します。</p><p>Veeva Vault DNSを見つけるには、Veeva Vaultへのアクセスに使用するURLを調べます。</p>例えば、URL <code>https://my-dns.veevavault.com</code>では、DNSは<code>my-dns.veevavault.com</code>です。 </td> 
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

Veeva Vault モジュールを設定すると、Workfront Fusionには以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、追加のVeeva Vault フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ドキュメント](#document)
* [オブジェクト](#object)
* [マルチファイル抽出](#multi-file-extract)
* [複数ファイルの読み込み](#multi-file-load)
* [ファイルのステージング](#file-staging)
* [その他](#other)

### ドキュメント

* [単一のドキュメントを作成](#create-a-single-document)
* [単一のドキュメント関係の作成](#create-a-single-document-relationship)
* [複数の注釈を作成](#create-multiple-annotations)
* [複数のドキュメントの作成](#create-multiple-documents)
* [複数のドキュメント関係の作成](#create-multiple-document-relationships)
* [1つの文書を削除](#delete-a-single-document)
* [1つのドキュメント関係を削除](#delete-a-single-document-relationship)
* [複数の注釈を削除](#delete-multiple-annotations)
* [複数のドキュメント関係の削除](#delete-multiple-document-relationships)
* [ファイルをダウンロード](#download-file)
* [ドキュメントの書き出し](#export-documents)
* [1つのドキュメントを取得](#get-a-single-document)
* [ドキュメント注釈を取得](#get-document-annotations)
* [ドキュメントの関係を取得](#get-document-relationships)
* [ユーザー操作を開始](#initiate-user-action)
* [ドキュメントのリスト](#list-documents)
* [ドキュメント書き出し結果の取得](#retrieve-document-export-results)
* [単一ドキュメントの更新](#update-a-single-document)
* [複数の注釈を更新](#update-multiple-annotations)
* [複数ドキュメントの更新](#update-multiple-documents)

#### 単一のドキュメントを作成

このモジュールは、単一のドキュメント、バインダー、またはテンプレートを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
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

#### 単一のドキュメント関係の作成

このアクションモジュールは、2つのドキュメント間の関係を作成します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>リレーションシップの作成元となるドキュメントのIDを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>リレーションシップを作成するバージョンのIDを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ターゲットドキュメント ID</p> </td> 
   <td> <p>関係が指すドキュメントのIDを入力します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Target メジャーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これはポイントの前の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>ターゲットのマイナーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これはポイントの後の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>関係タイプ</p> </td> 
   <td> <p>作成する関係のタイプを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 複数の注釈を作成

このアクションモジュールでは、最大500個の注釈を作成できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>注釈</p> </td> 
   <td> <p>追加する注釈ごとに、<b>項目を追加</b>をクリックし、この記事の<a href="#annotation-fields" class="MCXref xref">注釈フィールド </a>に記載されているデータを入力します。</p> </td> 
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
   <td> <p>この注釈を表示するページ番号を入力するか、マッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>X座標</p> </td> 
   <td> <p>プレースマークのX座標を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Y座標</p> </td> 
   <td> <p>プレースマークのY座標を入力またはマッピングします。</p> </td> 
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
   <td> <p>参照を使用すると、注釈で外部ソースを参照できます。 注釈に追加する各参照について、<b>項目を追加</b>をクリックし、参照のタイプ、文書のバージョン ID、および注釈を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>フィールドを選択</p> </td> 
   <td> <p>値を指定するフィールドを選択し、各フィールドに値を入力します。 使用可能なフィールドは、注釈タイプによって異なります。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>テンプレートとドキュメントのどちらを作成するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>ファイルデータ</p> </td> 
   <td> <p>ドキュメントの作成に使用するCSV ファイルをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 複数のドキュメント関係の作成

このアクションモジュールは、複数のドキュメント関係を設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>入力タイプ</p> </td> 
   <td> <p>これらの関係を作成するために提供する入力のタイプを選択します。</p> <ul><li>CSV</li><li>JSON</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ファイルデータ</p> </td> 
   <td> <p>CSV ファイルを使用している場合は、CSV ファイルデータを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>関係データ</p> </td> 
   <td> <p>JSONを使用している場合は、追加する関係ごとに<b>項目を追加</b>をクリックし、この記事の<a href="#relationship-fields" class="MCXref xref">関係フィールド </a>に記載されているデータを入力します。</p> </td> 
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
   <td> <p>リレーションシップの作成元となるドキュメントのIDを入力またはマッピングします。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Source メジャーバージョン</p> </td> 
   <td> <p>ソース文書のメジャーバージョンを入力します。 これはポイントの前の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Sourceマイナーバージョン</p> </td> 
   <td> <p>ソース文書のメジャーバージョンを入力します。 これはポイントの後の数字です。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ターゲットドキュメント ID</p> </td> 
   <td> <p>関係が指すドキュメントのIDを入力します。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Target メジャーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これはポイントの前の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>ターゲットのマイナーバージョン</p> </td> 
   <td> <p>ターゲットドキュメントのメジャーバージョンを入力します。 これはポイントの後の数字です。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>関係タイプ</p> </td> 
   <td> <p>作成する関係のタイプを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 1つの文書を削除

このモジュールは、1つのドキュメント、バインダー、またはテンプレートを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートを削除するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>文書ID / バインダーID / テンプレート名</p> </td> 
   <td> <p>削除する項目を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### 1つのドキュメント関係を削除

このアクションモジュールは、ドキュメントから関係を削除します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>削除するリレーションシップのソースドキュメントのIDを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>リレーションシップを削除するバージョンのIDを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>関係ID</p> </td> 
   <td> <p>削除するリレーションシップのIDを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 複数の注釈を削除

このアクションモジュールは注釈を削除します。 Veeva Vaultで注釈を削除するには、ユーザーに権限が必要です。 最大500個の注釈を削除できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>注釈</p> </td> 
   <td> <p>削除する注釈ごとに、<b>項目を追加</b>をクリックし、次のフィールドを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID</p> </td> 
   <td> <p>削除する注釈のIDを入力するか、マッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメントのバージョン ID</p> </td> 
   <td> <p>削除する注釈を含むドキュメントのバージョン番号を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 複数のドキュメント関係の削除

このアクションモジュールは、複数のドキュメントから関係を削除します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>入力タイプ</p> </td> 
   <td> <p>これらの関係を削除するために提供する入力のタイプを選択します。</p> <ul><li>CSV</li><li>JSON</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ファイルデータ</p> </td> 
   <td> <p>CSV ファイルを使用している場合は、CSV ファイルデータを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>関係データ</p> </td> 
   <td> <p>JSONを使用している場合は、追加する各リレーションシップについて、<b>項目を追加</b>をクリックし、リレーションシップ IDを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### ファイルをダウンロード

このモジュールは、Veeva Vaultからドキュメント、ドキュメントバージョン、またはテンプレートをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメントまたはテンプレートをダウンロードするかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ダウンロードタイプ</p> </td> 
   <td> <p>ドキュメントをダウンロードするか、ドキュメントのバージョンをダウンロードするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>文書ID / テンプレート名</p> </td> 
   <td> <p>ドキュメントのIDまたはダウンロードするテンプレートの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>文書をチェックアウト</p> </td> 
   <td> <p>ドキュメントをダウンロードする場合は、ダウンロードする前にドキュメントをチェックアウトする場合に、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>ドキュメントのバージョンをダウンロードする場合は、ダウンロードするバージョンを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントの書き出し

このモジュールは、ソース、レンディション、テキストなど、指定したドキュメントを書き出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートを削除するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ソース</p> </td> 
   <td> <p>ソースファイルを書き出しに含めるには、このオプションを有効にします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>レンダリング</p> </td> 
   <td> <p>レンディションファイルを書き出しに含めるには、このオプションを有効にします。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>すべてのバージョン</p> </td> 
   <td> <p>このオプションを有効にすると、文書ファイルのすべてのバージョンが書き出しに含まれます。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>テキスト</p> </td> 
   <td> <p>書き出しにソースドキュメントテキストを含めるには、このオプションを有効にします。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 1つのドキュメントを取得

このモジュールは、単一の文書、バインダー、またはテンプレートのメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートのデータを取得するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>文書ID / バインダーID / テンプレート名</p> </td> 
   <td> <p>データを取得するフィールドを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメント注釈を取得

このモジュールは、特定のドキュメントバージョンから注釈を取得します。 すべての注釈を取得するか、特定の注釈タイプのみを取得するかを選択できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>注釈を取得するドキュメントを選択するか、マッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>注釈を取得するバージョンのIDを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される注釈の最大数</td> 
   <td>シナリオ実行サイクルごとにモジュールが返す注釈の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメントの関係を取得

このモジュールは、ドキュメントのすべての関係を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ドキュメント ID</p> </td> 
   <td> <p>関係を取得するドキュメントを選択またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>バージョン</p> </td> 
   <td> <p>関係を取得するバージョンのIDを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される関係の最大数</td> 
   <td>各シナリオ実行サイクル中にモジュールが返す関係の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザー操作を開始

このモジュールは、レビュー用にドキュメントを送信したり、状態を変更したりするなど、ドキュメントやバインダーに対するアクションを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメントまたはバインダーに対してアクションを実行するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント/バインダー</p> </td> 
   <td> <p>アクションを実行するドキュメントまたはバインダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメントのバージョン/バインダーバージョン</p> </td> 
   <td> <p>アクションを実行するドキュメントまたはバインダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>アクション</p> </td> 
   <td> <p>ドキュメントまたはバインダーで実行するアクションを選択します。</td> 
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
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、テンプレートのいずれかを一覧表示するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ドキュメント書き出し結果の取得

このモジュールは、以前に要求されたドキュメントの書き出しの結果を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ジョブ ID</p> </td> 
   <td> <p>結果を返すジョブのIDを入力またはマッピングします。 </p> </td> 
  </tr> 
  </tbody> 
</table>

#### 複数の注釈を更新

このアクションモジュールは、最大500個の注釈を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>注釈</p> </td> 
   <td> <p>更新する注釈ごとに、<b>項目を追加</b>をクリックし、この記事の<a href="#annotation-fields" class="MCXref xref">注釈フィールド </a>に記載されているデータを入力します。</p> </td> 
  </tr> 
  </tbody> 
</table>

#### 複数ドキュメントの更新

このモジュールは、CSV ファイルを使用して複数のドキュメントまたはテンプレートを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>テンプレートとドキュメントのどちらを作成するかを選択します</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>ファイルデータ</p> </td> 
   <td> <p>ドキュメントの作成に使用するCSV ファイルをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一ドキュメントの更新

このモジュールは、単一のドキュメント、バインダー、またはテンプレートを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、ドキュメントのバージョン、バインダーまたはテンプレートを作成するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID/名前</p> </td> 
   <td> <p>テンプレートを更新する場合は、テンプレートの新しい名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>新しいテンプレート名</p> </td> 
   <td> <p>更新するオブジェクトのIDまたは名前を入力またはマッピングします。</p> </td> 
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
* [単一のオブジェクトを取得](#get-a-single-object)
* [オブジェクトレコードのリスト](#list-objects-records)
* [単一オブジェクトレコードの更新](#update-a-single-object-record)

#### 単一オブジェクトレコードの作成

このモジュールは、単一のオブジェクトレコードを作成、コピー、またはディープコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>レコードを作成またはコピーするか、レコードをディープコピーするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">移行モード</td> 
   <td>レコードを作成またはコピーする場合は、このオプションを有効にして、非初期状態で最小限の検証でオブジェクトレコードを作成または更新し、非アクティブレコードを作成し、<code>createdby_v</code>などの標準フィールドやシステム管理フィールドを設定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トリガーなし</td> 
   <td>trueに設定し、移行モードが有効になっている場合、すべてのシステム、標準、カスタム SDK トリガー、およびアクショントリガーがバイパスされます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td>オブジェクト名__v フィールド値（<code>product__v</code>、<code>country__v</code>、<code>custom_object__c</code>など）を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>レコードを詳細にコピーする場合は、コピーするレコードを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードフィールド</td> 
   <td>レコードを詳細にコピーする場合は、値を指定するフィールドを選択してから、それらの値を指定します。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一のオブジェクトレコードの削除

このモジュールは、単一のオブジェクトレコードを削除またはカスケード削除します。 レコードをカスケード削除すると、レコードとそのすべての子オブジェクトが削除されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>レコードを削除するか、レコードをカスケードで削除するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td>削除するオブジェクトを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>削除するレコードのIDを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">外部 ID</td> 
   <td>レコード IDの代わりに、このユーザー定義ドキュメント外部IDを使用できます。</td> 
  </tr> 
 </tbody> 
</table>

#### 単一のオブジェクトを取得

このモジュールは、Vault内の特定のオブジェクトレコードに設定されたメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td>メタデータを取得するオブジェクトを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>メタデータを取得するレコードのIDを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### オブジェクトレコードのリスト

このモジュールは、認証済みVault内のすべてのVault オブジェクトを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ローカライズされたラベルの取得</p> </td> 
   <td> <p>ラベルおよびlabel_plural オブジェクトフィールドのローカライズされた（翻訳済みの）文字列を取得するには、「はい」を選択します。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>レコードを作成またはコピーするか、レコードをディープコピーするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">移行モード</td> 
   <td>このオプションを有効にすると、非初期状態で最小限の検証でオブジェクトレコードを作成または更新し、非アクティブレコードを作成し、<code>createdby_v</code>などの標準フィールドやシステム管理フィールドを設定できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トリガーなし</td> 
   <td>移行モードが有効になっている場合、このオプションを有効にすると、すべてのシステム、標準、カスタム SDK トリガー、およびアクショントリガーをバイパスできます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクト名</td> 
   <td>オブジェクト名__v フィールド値（<code>product__v</code>、<code>country__v</code>、<code>custom_object__c</code>など）を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコード ID</td> 
   <td>更新するレコードのIDを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">状態</td> 
   <td><code>X-VaultAPI-MigrationMode</code>がtrueに設定されている場合のレコードのライフサイクル状態を指定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">状態ラベル</td> 
   <td><code>X-VaultAPI-MigrationMode</code>がtrueに設定されている場合のレコードのライフサイクル状態タイプを指定します。 形式<code>base:object_lifecycle:</code>の後にオブジェクト状態タイプを使用します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードフィールド</td> 
   <td>レコードを詳細にコピーする場合は、値を指定するフィールドを選択してから、それらの値を指定します。</td> 
  </tr> 
 </tbody> 
</table>

### マルチファイル抽出

* [複数のファイルを抽出](#extract-multiple-files)
* [抽出結果の取得](#retrieve-extract-results)

#### 複数のファイルを抽出

このアクションモジュールは、1つ以上のデータファイルを抽出するためのローダージョブを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">データファイル</td> 
   <td>抽出する各ファイルについて、<b>項目を追加</b>をクリックし、次を入力します。
   <ul>
   <li>オブジェクトタイプ</li>
   <li>VQL条件（オプション）：特定の条件を満たすファイルのみを含めるようにデータセットをフィルタリングするには、Vault Query Language （VQL）に条件を入力します。</li>
   </ul>
    </td> 
  </tr> 
 </tbody> 
</table>

#### 抽出結果の取得

このアクションモジュールは、指定された抽出リクエストの結果を取得します。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ジョブ ID</p> </td> 
   <td> <p>結果を取得するジョブを入力またはマッピングします。 これをデータファイルの抽出モジュールからマッピングできます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">タスク ID</td> 
   <td> <p>結果を取得するタスクを入力またはマッピングします。 これをデータファイルの抽出モジュールからマッピングできます。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 複数ファイルの読み込み

* [複数のファイルをロード](#load-multiple-files)
* [ログ結果の取得](#retrieve-log-results)

#### 複数のファイルをロード

このモジュールはローダージョブを作成し、一連のデータファイルをロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ファイル</td> 
   <td>このジョブで使用するCSV ファイルにファイルパスを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Order</td> 
   <td>ファイルリストの順序を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トリガーなし</td> 
   <td>レコードまたはドキュメントのトリガーをバイパスするには、「はい」を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ログ結果の取得

このアクションモジュールは、ローダージョブの結果のログを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ジョブ ID</p> </td> 
   <td> <p>結果を取得するジョブを入力またはマッピングします。 これをデータファイルをロード モジュールからマッピングできます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">タスク ID</td> 
   <td> <p>結果を取得するタスクを入力またはマッピングします。 これをデータファイルをロード モジュールからマッピングできます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">タイプ</td> 
   <td> <p>成功したジョブと失敗したジョブのどちらを取得するかを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### ファイルのステージング

#### パスのリスト項目

このモジュールは、指定されたパスのファイルとフォルダーのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ホームディレクトリを選択</td> 
   <td>アイテムを一覧表示するホームディレクトリを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Order</td> 
   <td>ファイルリストの順序を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">トリガーなし</td> 
   <td>レコードまたはドキュメントのトリガーをバイパスするには、「はい」を選択します。</td> 
  </tr> 
 </tbody> 
</table>

### その他

* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [VQL クエリの作成](#make-a-vql-query)
* [ログの読み取り](#read-logs)

#### カスタム API 呼び出しの実行

このアクションモジュールは、Veeva Vault APIをカスタム呼び出します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td><code>baseurl/api/v</code> からの相対パスを入力します。  例：<code>/objects/documents</code> <code>baseurl/api/v/</code>は既に含まれているため、含めないでください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メソッド</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエスト方法</a>を参照してください。</p> </td> 
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

このモジュールは、Vault Query Language （VQL）を使用してクエリを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>テンプレートとドキュメントのどちらを作成するかを選択します</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>ファイルデータ</p> </td> 
   <td> <p>ドキュメントの作成に使用するCSV ファイルをマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ログの読み取り

このモジュールは、監査証跡からデータを返します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Veeva VaultをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>監査タイプ</p> </td> 
   <td> <p>データを取得する監査タイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>開始日</p> </td> 
   <td> <p>取得する監査の開始日を入力またはマッピングします。</p><p>サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>終了日</p> </td> 
   <td> <p>取得する監査の終了日を入力またはマッピングします。</p><p>サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>結果URL </p> </td> 
   <td> <p>結果のCSVをダウンロードするURLを取得する場合は、「CSV」を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
