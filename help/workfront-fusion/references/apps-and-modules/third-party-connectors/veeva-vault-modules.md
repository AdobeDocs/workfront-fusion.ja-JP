---
title: Veeva Vault モジュール
description: Adobe Workfront Fusion のシナリオでは、Veeva Vault を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
source-git-commit: 4f5a4cf8691e5bb47eec6f6b2842369c5c6fbad8
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 16%

---

# Veeva Vault モジュール

Adobe Workfront Fusion のシナリオでは、Veeva Vault を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[&#x200B; シナリオの作成：記事のインデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

Veeva Vault モジュールを使用するには、Veeva Vault アカウントが必要です。

## Veeva Vault モジュールとそのフィールド

Workfront Fusion で Veeva Vault モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の Veeva Vault フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### ドキュメント

* [1 つのドキュメントの作成](#create-a-single-document)
* [複数のドキュメントの作成](#create-multiple-documents)
* [1 つのドキュメントの削除](#delete-a-single-document)
* [ドキュメントのエクスポート](#export-documents)
* [1 つのドキュメントの取得](#get-a-single-document)
* [ユーザーアクションの開始](#initiate-user-action)
* [ドキュメントのリスト](#list-documents)
* [ドキュメントのエクスポート結果の取得](#retrieve-document-export-results)
* [複数のドキュメントの更新](#update-multiple-documents)
* [1 つのドキュメントの更新](#update-a-single-document)

#### 1 つのドキュメントの作成

このモジュールは、単一のドキュメント、バインダーまたはテンプレートを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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

#### 複数のドキュメントの作成

このモジュールは、CSV ファイルを使用して複数のドキュメントまたはテンプレートを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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

#### 1 つのドキュメントの削除

このモジュールは、単一のドキュメント、バインダーまたはテンプレートを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>タイプ</p> </td> 
   <td> <p>ドキュメント、バインダー、またはテンプレートを削除するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>ドキュメント ID/バインダー ID/テンプレート名</p> </td> 
   <td> <p>削除するフィールドを選択します。</td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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

#### ユーザーアクションの開始

このモジュールは、ドキュメントをレビュー用に送信したり、ドキュメントの状態を変更したりするなど、ドキュメントとバインダーに対するアクションを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ジョブ ID</p> </td> 
   <td> <p>結果を返すジョブの ID を入力またはマッピングします。 </p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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



#### オブジェクトリスト

このモジュールは、認証された Vault 内のすべての Vault オブジェクトを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続 </td> 
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td><code>baseurl/api/v</code> を基準とした相対パスを入力します。  例：<code>/objects/documents</code>。 <code>baseurl/api/v/</code> は既に含まれているため、含めないでください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メソッド</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
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
   <td> <p>Veeva Vault アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>監査タイプ</p> </td> 
   <td> <p>データを取得する監査タイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>開始日</p> </td> 
   <td> <p>取得する監査の開始日を入力またはマップします。</p><p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>終了日</p> </td> 
   <td> <p>取得する監査の終了日を入力またはマップします。</p><p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
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


