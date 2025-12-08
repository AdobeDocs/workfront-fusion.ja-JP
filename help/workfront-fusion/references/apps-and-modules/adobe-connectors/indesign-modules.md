---
filename: adobe-indesign-modules
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe InDesign モジュール
description: Adobe Workfront Fusion のシナリオでは、Adobe InDesignを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
source-git-commit: 30ddefa8519e6f2052308482137d0fa018676902
workflow-type: tm+mt
source-wordcount: '1693'
ht-degree: 21%

---


# Adobe InDesign モジュール

Adobe Workfront Fusion のシナリオでは、Adobe InDesignを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

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

Adobe InDesign コネクタを使用する前に、アクティブなAdobe InDesign アカウントが必要です。

## Adobe InDesignへの接続の作成

Adobe InDesign モジュールの接続を作成するには：

1. 任意のAdobe InDesign モジュールで、「接続」ボックスの横にある **追加** をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col>
      </col>
      <col>
      </col>
      <tbody>
        <tr>
          <td role="rowheader">接続名</td>
          <td>
            <p>この接続の名前を入力します。</p>
          </td>
        </tr>
      <tr>
        <td role="rowheader">環境</td>
        <td>
          <p>本番環境と非本番環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">タイプ</td>
        <td>
          <p>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</p>
        </td>
      </tr>
        <tr>
          <td role="rowheader">クライアント ID</td>
          <td>Adobe クライアント ID を入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションにあります</td>
        </tr>
        <tr>
          <td role="rowheader">クライアントシークレット</td>
          <td>Adobeのクライアントシークレットを入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションにあります</td>
        </tr>
        <tr>
          <td role="rowheader">IMS 組織 ID</td>
          <td>Adobeの組織 ID を入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションにあります</td>
        </tr>
      </tbody>
    </table>
1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

## InDesign モジュールとそのフィールド

Workfront Fusion でAdobe InDesign モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のAdobe InDesign フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

* [レンディションの作成](#create-rendition)
* [カスタムスクリプトの削除](#delete-a-custom-script)
* [データの結合](#merge-data)
* [リンクの再マップ](#remap-links)
* [カスタムスクリプト実行リクエストを送信](#submit-a-custom-script-execution-request)

#### レンディションの作成

このアクションモジュールは、特定のInDesign ドキュメントのJPEG、PNG またはPDF レンディションを作成して返します。 `StatusCompletedRespons/output/data` の構造については、`RenditionOutputData` を参照してください。 また、`FailedEvent` で使用可能なエラーコードのリストについては、`RenditionFailedData` を参照してください。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>タイプ</p>
      </td>
      <td>作成するレンディションのファイルタイプを選択します。 
      <ul><li>JPEG</li><li>PNG</li><li>PDF</li></ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>アセット</p>
      </td>
      <td>レンディションに追加するアセットごとに、次の操作を行います。<ol><li><b> 項目を追加 </b> をクリックします。</li><li>アセットのソースを選択またはマッピングします。</li><li>宛先を入力します。 コピー先は、リソースのダウンロード先となる一時的なベースディレクトリ（作業ディレクトリ）への相対パスです。 これにより、パラメーター内のアセットが識別されます。 「。.」を使用して起動することはできません または「/」。 有効なファイル名が必要です。</td>
    </tr>
    <tr>
      <td role="rowheader">ターゲットドキュメント</td>
      <td>処理およびレンダリングするドキュメントを入力またはマッピングします。 現在、一度に 1 つのドキュメントのみがサポートされています。</td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
   <td>その他のフィールドについては、モジュールに含まれる情報を参照してください。</td>     </tr>
  </tbody>
</table>

#### カスタムスクリプトの削除

このアクションモジュールは、1 つの登録済みカスタムスクリプトを削除します。 スクリプトのすべてのバージョンは完全に削除されます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>スクリプト名</p>
      </td>
      <td>削除するスクリプトの名前を入力またはマップします。</td>
    </tr>
  </tbody>
</table>

#### データの結合

このモジュールは、CSV データをInDesign テンプレートと結合して、InDesign ドキュメントまたは PDF を作成します。 出力形式には、JPEG、PNG、PDF、InDesignのドキュメントが含まれます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>アセット</p>
      </td>
      <td>データの結合に追加するアセットごとに、次の操作を行います。<ol><li><b> 項目を追加 </b> をクリックします。</li><li>アセットのソースを選択またはマッピングします。</li><li>宛先を入力します。 コピー先は、リソースのダウンロード先となる一時的なベースディレクトリ（作業ディレクトリ）への相対パスです。 これにより、パラメーター内のアセットが識別されます。 「。.」を使用して起動することはできません または「/」。 有効なファイル名が必要です。</td>
    </tr>
    <tr>
      <td role="rowheader">ターゲットドキュメント</td>
      <td>結合のテンプレートとして使用するドキュメントを入力またはマップします。</td>
    </tr>
    <tr>
      <td role="rowheader">データソース</td>
      <td>使用するソースファイルを入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
   <td>その他のフィールドについては、モジュールに含まれる情報を参照してください。</td>     </tr>
  </tbody>
</table>

#### リンクの再マップ

このモジュールでは、InDesign ドキュメント内のファイルベースのリンクをAdobe Experience Manager（AEM）の URL に置き換えます。 これは、Adobe Asset Link を使用してAdobe Experience Managerを操作する場合に役立ちます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
      </tr>
    <tr>
      <td role="rowheader">AEM トークン</td>
      <td>AEM テクニカルアカウント用に生成されたベアラートークンを、bearer キーワードなしで入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>アセット</p>
      </td>
      <td>モジュールに追加するアセットごとに、次の操作を行います。<ol><li><b> 項目を追加 </b> をクリックします。</li><li>アセットのソースを選択またはマッピングします。</li><li>宛先を入力します。 コピー先は、リソースのダウンロード先となる一時的なベースディレクトリ（作業ディレクトリ）への相対パスです。 これにより、パラメーター内のアセットが識別されます。 「。.」を使用して起動することはできません または「/」。 有効なファイル名が必要です。</td>
    </tr>
    <tr>
      <td role="rowheader">ターゲットドキュメント</td>
      <td>リンクを再マップするドキュメントを入力またはマップします。</td>
    </tr>
    <tr>
      <td role="rowheader">データソース</td>
      <td>タグの抽出および一致に使用するソースファイルを入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
   <td>その他のフィールドについては、モジュールに含まれる情報を参照してください。</td>     </tr>
  </tbody>
</table>

#### カスタムスクリプト実行リクエストを送信

このアクションモジュールは、カスタムスクリプトの実行リクエストを送信します。 実行時にカスタムスクリプトで使用する入力アセットおよびパラメーターを定義します。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>スクリプト ID</p>
      </td>
      <td>カスタムスクリプトの ID を入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>アセット</p>
      </td>
      <td>実行リクエストを送信するアセットごとに、以下を行います。 <ol><li><b> 項目を追加 </b> をクリックします。</li><li>アセットのソースを選択またはマッピングします。</li><li>宛先を入力します。 コピー先は、リソースのダウンロード先となる一時的なベースディレクトリ（作業ディレクトリ）への相対パスです。 これにより、パラメーター内のアセットが識別されます。 「。.」を使用して起動することはできません または「/」。 有効なファイル名が必要です。</td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
   <td>その他のフィールドについては、モジュールに含まれる情報を参照してください。</td>     </tr>
  </tbody>
</table>

### 検索

* [カスタムスクリプトの詳細を取得](#get-custom-script-details)
* [データ結合タグの取得](#get-data-merge-tags)
* [ドキュメント情報の取得](#get-document-information)
* [カスタムスクリプトのリスト](#list-custom-scripts)

#### カスタムスクリプトの詳細を取得

この検索モジュールは、バージョン、ダウンロードリンク、登録日、スクリプト名など、1 つの登録済みカスタムスクリプトの詳細を取得します。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>スクリプト名</p>
      </td>
      <td>詳細を取得するスクリプトの名前を入力またはマッピングします。</td>
    </tr>
  </tbody>
</table>

#### データ結合タグの取得

このモジュールは、ドキュメントからデータ結合タグを取得します。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>アセット</p>
      </td>
      <td>モジュールに追加するアセットごとに、次の操作を行います。<ol><li><b> 項目を追加 </b> をクリックします。</li><li>アセットのソースを選択またはマッピングします。</li><li>宛先を入力します。 コピー先は、リソースのダウンロード先となる一時的なベースディレクトリ（作業ディレクトリ）への相対パスです。 これにより、パラメーター内のアセットが識別されます。 「。.」を使用して起動することはできません または「/」。 有効なファイル名が必要です。</td>
    </tr>
    <tr>
      <td role="rowheader">ターゲットドキュメント</td>
      <td>タグを取得するドキュメントを入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">データソース</td>
      <td>タグの抽出および一致に使用するソースファイルを入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">その他のフィールド</td>
   <td>その他のフィールドについては、モジュールに含まれる情報を参照してください。</td>     </tr>
  </tbody>
</table>

#### ドキュメント情報の取得

このモジュールは、INDD/IDML ドキュメントに関する包括的な情報を取得し、リクエストで指定された有効な情報タイプに基づいてデータを返します。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>アセット</p>
      </td>
      <td>モジュールに追加するアセットごとに、次の操作を行います。<ol><li><b> 項目を追加 </b> をクリックします。</li><li>アセットのソースを選択またはマッピングします。</li><li>宛先を入力します。 コピー先は、リソースのダウンロード先となる一時的なベースディレクトリ（作業ディレクトリ）への相対パスです。 これにより、パラメーター内のアセットが識別されます。 「。.」を使用して起動することはできません または「/」。 有効なファイル名が必要です。</td>
    </tr>
    <tr>
      <td role="rowheader">ターゲットドキュメント</td>
      <td>情報を取得するドキュメントを入力またはマッピングします。</td>
    </tr>
     <tr>
      <td role="rowheader">その他のフィールド</td>
   <td>その他のフィールドについては、モジュールに含まれる情報を参照してください。</td>     </tr>
  </tbody>
</table>

#### カスタムスクリプトのリスト

このモジュールは、バージョン、ダウンロードリンク、登録日、スクリプト名など、登録されているすべてのカスタムスクリプトの最新バージョンの詳細を取得します。 結果は、リストの長さに基づいてページ分割されます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
      </tr>
    <tr>
      <td role="rowheader">ページ番号</td>
      <td>開始するページ番号を入力またはマッピングします。</td>
    </tr>
  <tr> 
   <td>返される結果の最大数</td> 
   <td>Workfront Fusion が 1 つの実行サイクルで返すチームまたはグループの最大数を設定します。</td> 
  </tr> 
  </tbody>
</table>


### その他

#### カスタム API 呼び出しの実行

このモジュールは、Adobe InDesign API へのカスタム API 呼び出しを行います。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe InDesignへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Adobe InDesignへの接続の作成 </a> を参照してください。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>パス</p>
      </td>
      <td>
        <p><code>https://indesign.adobe.io/v3</code> への相対パスを入力します。</p><p> 例： <code>/create-rendition</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>メソッド</p>
      </td>
      <td>
        <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、[HTTP リクエストメソッド ] （/help/workfront-fusion/references/modules/http-request-methods.md）を参照してください。</p>
      </td>
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
      <td role="rowheader">クエリ文字列  </td>
      <td>
        <p>リクエストクエリ文字列を入力します。</p>
      </td>
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
