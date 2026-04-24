---
title: Jira ソフトウェアモジュール
description: Adobe Workfront Fusionでは、 [!DNL Jira]  ソフトウェアを使用するワークフローを自動化したり、複数のサードパーティ製アプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 92cac080-d8f6-4770-a6a6-8934538c978b
source-git-commit: bc4c5c047f4847b929c4b047be1897d8872709e9
workflow-type: tm+mt
source-wordcount: '2466'
ht-degree: 78%

---

# [!DNL Jira Software] モジュール

>[!NOTE]
>
>これらの手順は、従来のJira CloudおよびJira Server コネクタに適用されます。 Jiraと単にラベル付けされるJira コネクタの新しいバージョンについては、[Jira モジュール &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md)を参照してください。

Adobe Workfront Fusion のシナリオでは、[!DNL Jira Software] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

これらの手順は、Jira CloudとJira Serverの両方のモジュールに適用されます。

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

[!DNL Jira] モジュールを使用するには、[!DNL Jira] アカウントが必要です。

## Jira API情報

Jira コネクタでは、次の機能を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"></td> 
   <td> Jira Cloud</td> 
   <td> Jira Server</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersion</td> 
   <td> 2</td> 
   <td> 2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersionAgile</td> 
   <td> 1.0 </td> 
   <td> 1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>1.7.29</td> 
   <td>1.0.19</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Jira Software] を Workfront Fusion に接続

接続方法は、[!DNL Jira Cloud] を使用しているか、[!DNL Jira Server] を使用しているかによって決まります。

* [&#x200B; [!DNL Jira Cloud]  を Workfront Fusion に接続](#connect-jira-cloud-to-workfront-fusion)
* [&#x200B; [!DNL Jira Server]  を Workfront Fusion に接続](#connect-jira-server-to-workfront-fusion)

### [!DNL Jira Cloud] を Workfront Fusion に接続

[!DNL Jira Cloud] を Workfront Fusion に接続

[!DNL Jira Software]をWorkfront Fusionに接続するには、API トークンを作成し、サービス URLとユーザー名と共にWorkfront Fusionの[!UICONTROL Create a connection] フィールドに挿入する必要があります。

#### [!DNL Jira] での API トークンの作成

1. JiraでAPI トークンを作成します。

   手順については、Jira ドキュメントで「API トークンを作成」を検索することをお勧めします。
1. トークンを作成したら、トークンを安全な場所にコピーします。

   >[!IMPORTANT]
   >
   >このダイアログを閉じた後は、トークンを再度表示することはできません。
1. 生成されたトークンを安全な場所に保存します。
1. Workfront Fusion[で [!DNL Jira] API トークンを](#configure-the-jira-api-token-in-workfront-fusion)設定します。

#### Workfront Fusionで[!DNL Jira] API トークンを設定する

1. Workfront Fusionの任意の[!DNL Jira Cloud] モジュールで、**[!UICONTROL connection]** フィールドの横にある[!UICONTROL Add]をクリックします。
1. 次の情報を指定します。

   * **環境**
   * **タイプ**
   * **[!UICONTROL サービス URL]:**&#x200B;これは、Jira アカウントへのアクセスに使用するベース URLです。 例：`yourorganization.atlassian.net`
   * **[!UICONTROL ユーザー名]**
   * **[!UICONTROL API トークン &#x200B;]:**&#x200B;これは、この記事の[API トークンの作成 [!DNL Jira]](#create-an-api-token-in-jira) セクションで作成したAPI トークンです。

1. 「[!UICONTROL 続行]」をクリックして接続を作成し、モジュールに戻ります。

### [!DNL Jira Server] を Workfront Fusion に接続

Workfront Fusionと[!DNL Jira Server]間の接続を認証するには、コンシューマーキー、秘密鍵、およびサービス URLが必要です。 この情報については、[!DNL Jira]管理者にお問い合わせください。

* [&#x200B; [!DNL Jira]  接続の公開キーと秘密鍵の生成](#generate-public-and-private-keys-for-your-jira-connection)
* [&#x200B; [!DNL Jira] でクライアントアプリをコンシューマーとして設定する](#configure-the-client-app-as-a-consumer-in-jira)
* [Workfront Fusionで [!DNL Jira] ServerまたはJira Data Centerへの接続を作成する](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### [!DNL Jira] 接続の公開鍵と秘密鍵の生成

[!DNL Workfront Fusion Jira]接続の秘密鍵を取得するには、公開鍵と秘密鍵を生成する必要があります。 これは、コンピューターの端末を通じて行います。 ターミナルは、スタートメニューまたはコンピューターの検索バー（ブラウザーの検索バーではなく）で検索することで見つけることができます。

1. ターミナルで、次の `openssl` コマンドを実行します。

   * `openssl genrsa -out jira_privatekey.pem 1024`

     このコマンドは、1024 ビットの秘密鍵を生成します。

   * `openssl req -newkey rsa:1024 -x509 -key jira_privatekey.pem -out jira_publickey.cer -days 365`

     このコマンドは X509 証明書を作成します。

   * `openssl pkcs8 -topk8 -nocrypt -in jira_privatekey.pem -out jira_privatekey.pcks8`

     このコマンドは、秘密鍵（PKCS8形式）を`jira_privatekey.pcks8` ファイルに抽出します。

   * `openssl x509 -pubkey -noout -in jira_publickey.cer  > jira_publickey.pem`

     このコマンドは、証明書から `jira_publickey.pem` ファイルに公開鍵を抽出します。

     >[!NOTE]
     >
     >Windowsを使用している場合は、公開鍵を`jira_publickey.pem` ファイルに手動で保存する必要がある場合があります。
     >
     >1. ターミナルで、次のコマンドを実行します。
     >   
     >   `openssl x509 -pubkey -noout -in jira_publickey.cer`
     >   
     >1. `-------BEGIN PUBLIC KEY--------`と`-------END PUBLIC KEY--------`を含むターミナル出力をコピーします。
     >   
     >1. ターミナル出力を `jira_publickey.pem` という名前のファイルに貼り付けます。


1. [&#x200B; [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira) でクライアントアプリをコンシューマーとして設定するに進んでください

#### [!DNL Jira] でクライアントアプリをコンシューマーとして設定する

1. [!DNL Jira] インスタンスにログインします。
1. 左側のナビゲーションパネルで、**[!UICONTROL [!DNL Jira]設定]** ![Jira設定アイコン &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/jira-settings-icon.png) > **[!UICONTROL アプリケーション]**> **[!UICONTROL アプリケーションリンク]**&#x200B;をクリックします。
1. 「**[!UICONTROL リンクするアプリケーションの URL を入力]**」フィールドに、次のように入力します。

   ```
   https://app.workfrontfusion.com/oauth/cb/workfront-jiraserver-oauth1
   ```

1. 「**[!UICONTROL 新しいリンクを作成]**」をクリックします。「入力した URL から応答が受信しませんでした」というエラーメッセージを無視します。
1. **[!UICONTROL アプリケーションをリンク]**&#x200B;ウィンドウで、**[!UICONTROL Consumer key]** および **[!UICONTROL 共有シークレット]**&#x200B;フィールドに値を入力します。

   これらのフィールドの値を選択できます。

1. **[!UICONTROL Consumer key]** および&#x200B;**[!UICONTROL 共有シークレット]**&#x200B;フィールドの値を安全な場所にコピーします。

   これらの値は、設定プロセスの後半で必要になります。

1. URL フィールドに次のように入力します。

   | フィールド | 説明 |
   | --- | --- |
   | [!UICONTROL リクエストトークン URL] | `<Jira base url>/plugins/servlet/oauth/request-token` |
   | [!UICONTROL 認証 URL] | `<Jira base url>/plugins/servlet/oauth/authorize` |
   | [!UICONTROL アクセストークン URL] | `<Jira base url>/plugins/servlet/oauth/access-token` |

1. **[!UICONTROL 受信リンクを作成]**&#x200B;チェックボックスを選択します。
1. 「**[!UICONTROL 続行]**」をクリックします。
1. **[!UICONTROL アプリケーションをリンク]**&#x200B;ウィンドウで、次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col data-mc-conditions=""> 
    <col data-mc-conditions=""> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Consumer Key]</p> </td> 
      <td> 安全な場所にコピーした Consumer key を貼り付けます。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Consumer name]</td> 
      <td>任意の名前を入力します。この名前は、参照用です。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Public key]</td> 
      <td><code>[!DNL jira_publickey.pem]</code> ファイルから公開鍵を貼り付けます。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックします。
1. Workfront Fusion[で [!DNL Jira Server] または [!DNL Jira Data Center] への接続を](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)作成します

#### Workfront Fusionで[!DNL Jira Server]または[!DNL Jira Data Center]への接続を作成する

>[!NOTE]
>
>[!DNL Jira Server] アプリで [!DNL Jira Server] または [!DNL Jira Data Center] に接続します。

1. Workfront Fusionの任意の[!DNL Jira Server] モジュールで、**[!UICONTROL connection]** フィールドの横にある[!UICONTROL Add]をクリックします。
1. [!UICONTROL 接続の作成]パネルで、次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>接続に名前を入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td> <p>実稼動環境と非実稼動環境のどちらを使用するかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Type]</p> </td> 
      <td> <p>サービスアカウントと個人アカウントのどちらを使用しているかを選択します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Consumer Key]</td> 
      <td><a href="#configure-the-client-app-as-a-consumer-in-jira" class="MCXref xref">[!DNL Jira]</a> でのクライアントアプリのコンシューマーとしての設定で、安全な場所にコピーした Consumer key に貼り付けます。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Private Key]</td> 
      <td><a href="#generate-public-and-private-keys-for-your-jira-connection" class="MCXref xref">[!DNL Jira] 接続のパブリックキーとプライベートキーの生成</a>で作成した <code>[!DNL jira_privatekey.pcks8]</code> ファイルのとプライベートキーに貼り付けます。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Service URL]</td> 
      <td>[!DNL Jira] インスタンス URLを入力します。 例： <code>yourorganization.atlassian.net</code></td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

## [!DNL Jira Software] モジュールとそのフィールド

[!DNL Jira Software] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Jira Software]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

#### [!UICONTROL レコードの監視]

このトリガーモジュールは、レコードが追加、更新または削除された時点でシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>レコードの監視に使用する Web フックを選択します。 </p> <p>新規の web フックを追加するには、次の手順に従います。</p> 
    <ol> 
     <li value="1"><strong>[!UICONTROL Add]</strong> をクリックします。</li> 
     <li value="2">Web フックの名前を入力します。</li> 
     <li value="3"> <p>Web フックに使用する接続を選択します。 </p> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </li> 
     <li value="4"> <p>ソフトウェアで監視するレコードの種類を選択します。</p> 
      <ul> 
       <li>[!UICONTROL Comment] </li> 
       <li>[!UICONTROL Issue]</li> 
       <li>[!UICONTROL Project] </li> 
       <li>[!UICONTROL Sprint]</li> 
      </ul> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL スプリントへのイシューの追加]](#add-issue-to-sprint)
* [[!UICONTROL レコードを作成]](#create-a-record)
* [[!UICONTROL カスタム API 呼び出し]](#custom-api-call)
* [[!UICONTROL レコードの削除]](#delete-a-record)
* [[!UICONTROL 添付ファイルのダウンロード]](#download-an-attachment)
* [[!UICONTROL レコードの読み取り]](#read-a-record)
* [[!UICONTROL レコードの更新]](#update-a-record)

#### [!UICONTROL スプリントへのイシューの追加]

このアクションモジュールは、スプリントに 1 つ以上のイシューを追加します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sprint ID]</td> 
   <td>イシューを追加するスプリントのスプリント ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID or Keys]</td> 
   <td>エクスペリエンスを表示する各イシューまたはキーについて、<b>[!UICONTROL Add item]</b>をクリックし、イシューIDまたはキーを入力します。 1つのモジュールに最大50個まで入力できます。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードを作成]

このアクションモジュールは、Jira に新しいレコードを作成します。

このモジュールは、レコードに関連付けられた標準フィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで作成するレコードタイプを選択し、そのレコードタイプに固有の他のフィールドをモジュールに入力します。</p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カスタム API 呼び出し]

このアクションモジュールは、[!DNL Jira Software] API に対して認証済みのカスタム呼び出しを実行します。このモジュールを使用して、他の[!DNL Jira Software] モジュールでは実行できないデータフローの自動化を作成します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>相対パスを入力します<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードを削除]

このアクションモジュールは、指定されたレコードを削除します。

レコードの ID を指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで削除するレコードのタイプを選択します。 </p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID or Key]</td> 
   <td>削除するレコードの ID またはキーを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 添付ファイルをダウンロード]

このアクションモジュールは、特定の添付ファイルをダウンロードします。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>ダウンロードする添付ファイルの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの読み取り]

このアクションモジュールは、[!DNL Jira Software] の単一レコードからデータを読み取ります。

レコードの ID を指定します。

このモジュールは、レコードに関連付けられた標準フィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールが読み取る [!DNL Jira] レコードのタイプを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL User]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>受け取る出力を選択します。出力オプションは、「[!UICONTROL Record Type]」フィールドで選択したレコードのタイプに基づいて使用できます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>モジュールが読み取るレコードの一意の [!DNL Jira Software] ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの更新]

このアクションモジュールは、イシューやプロジェクトなどの既存のレコードを更新します。

レコードの ID を指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで更新するレコードのタイプを選択します。レコードタイプを選択すると、そのレコードタイプに固有の他のフィールドがモジュールに表示されます。</p> 
    <ul> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Transition issue]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID or Key]</td> 
   <td>更新するレコードのIDまたはキーを入力またはマッピングし、そのレコードタイプに固有の他のフィールドを入力して、モジュールに表示します。</td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL レコードをリスト表示]](#list-records)
* [[!UICONTROL レコードを検索]](#search-for-records)

>[!IMPORTANT]
>
>従来の Jira コネクターで使用されていた検索モジュールでは、次のエラーが発生する場合があります。
>
>`[410] The requested API has been removed. Please migrate to the /rest/api/3/search/jql API. A full migration guideline is available at https://developer.atlassian.com/changelog/#CHANGE-2046`
>
>これは、Jira 側の廃止によるものです。
>
>このエラーが発生した場合は、従来の Jira コネクターの検索モジュールを新しいコネクターの検索モジュールに置き換えることができます。新しいコネクターでは、使用する API バージョンを選択できます。接続を作成する際は、必ずV3を選択してください。
>
> 新しいJira コネクタの![API バージョン オプション &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/jira-version-option.png)
>
>メモ：
>
>* 影響を受けるのは検索モジュールのみです。現時点では、Fusion コネクターで使用される他の Jira API エンドポイントは、この廃止の影響を受けません。
>
>* 地理的なロールアウトによって不整合が発生する場合があります。Atlassian はこの変更を地域的に展開しています。つまり、一部の Jira クラウドインスタンスでは、引き続き一時的に古いエンドポイントをサポートしている可能性があります。これにより、環境間で動作に一貫性がなくなる可能性があります。

#### [!UICONTROL レコードをリスト表示]

この検索モジュールは、検索クエリに一致する特定のタイプのすべての項目を取得します

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールのリストに表示するレコードのタイプを選択します。レコードタイプを選択すると、そのレコードタイプに固有の他のフィールドがモジュールに表示されます。</p> 
    <ul> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint issue]</li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Max Results]</p> </td> 
   <td> <p>シナリオの実行サイクルごとにモジュールが取得するレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <!--
   <tr> 
    <td role="rowheader">Offset</td> 
    <td> Enter or map the ID of the first item you want to retrieve details for. This is a way to paginate the records. If you enter the 5000th item as the offset, the module would return items 5000-9999.</td> 
   </tr>
  --> 
 </tbody> 
</table>

#### [!UICONTROL レコードを検索]

この検索モジュールは、指定された検索クエリに一致するレコードを [!DNL Jira Software] のオブジェクト内で検索します。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Jira Software] アカウントを Workfront Fusion に接続する手順について詳しくは、この記事の <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">[!DNL Jira Software] を Workfront Fusion に接続</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで検索するレコードのタイプを選択します。レコードタイプを選択すると、そのレコードタイプに固有の他のフィールドがモジュールに表示されます。</p> 
    <ul> 
     <li>[!UICONTROL Issues]</li> 
     <li> <p>[!UICONTROL Issues by JQL (Jira Query Lanuguage)] </p> <p>JQL について詳しくは、Atlassian のヘルプサイトで <a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a> を参照してください。 </p> </li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Project by issue]</li> 
     <li>[!UICONTROL User]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
