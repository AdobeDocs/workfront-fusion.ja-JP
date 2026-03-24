---
title: Adobe Authenticator モジュール
description: Adobe Authenticatorモジュールを使用すれば、1回の接続でAPIを使用してあらゆるAdobe製品に接続できます。
author: Becky
feature: Workfront Fusion
exl-id: af4da661-eeee-4033-a2bb-a2196e446a3d
source-git-commit: 42ec34b1931eb9962569906d78c281bbef86a57e
workflow-type: tm+mt
source-wordcount: '1478'
ht-degree: 38%

---

# Adobe Authenticatorモジュール

Adobe Authenticator モジュールを使用すると、1つの接続を使用して、任意のAdobe APIに接続できます。 これにより、専用のFusion コネクタを持たないAdobe製品に簡単に接続できます。

HTTP モジュールよりも優れているのは、専用アプリと同様に接続を作成できることです。

使用可能なAdobe APIの一覧については、[Adobe API](https://developer.adobe.com/apis)を参照してください。 割り当てられたAPIのみを使用できる場合があります。

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

* モジュールを接続するAdobe製品へのアクセス権が必要です。
* Adobe Developer Consoleにアクセスする必要があります。
* Adobe Developer Console上に、モジュールを接続するAPIを含むプロジェクトが必要です。 実行できる操作：

   * APIを使用して新しいプロジェクトを作成します。

     または
   * 既存のプロジェクトにAPIを追加します。

  Adobe Developer Console上のプロジェクトにAPIを作成または追加する方法について詳しくは、Adobe ドキュメントの「[ プロジェクトを作成](https://developer.adobe.com/dep/guides/dev-console/create-project/)」を参照してください。

## Adobe Authenticator APIについて

Adobe Authenticator コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.1.4</td> 
  </tr>
 </tbody> 
 </table>

## 接続の作成

Adobe Authenticator接続は、Adobe Developer Console上の1つのプロジェクトに接続します。 複数のAdobe APIに同じ接続を使用するには、同じプロジェクトにAPIを追加し、そのプロジェクトに接続を作成します。

別々のプロジェクトに対して個別の接続を作成できますが、接続を使用して、その接続で指定されたプロジェクトにないAPIにアクセスすることはできません。

>[!IMPORTANT]
>
>Adobe Authenticator コネクタでは、OAuth サーバー間接続を行うか、サービスアカウント（JWT）接続を行うかを選択できます。 AdobeはJWT資格情報を非推奨にしました。この資格情報は、2025年1月1日を過ぎると機能しなくなります。 **したがって、OAuth接続を作成することを強くお勧めします。**
>
>これらの種類の接続について詳しくは、Adobe ドキュメントの[ サーバー間の認証](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/)を参照してください

接続を作成するには：

1. 任意の Adobe Authenticator モジュールで、接続フィールドの横にある「**追加**」をクリックします。
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
          <p>OAuth サーバー間接続を作成するか、サービスアカウント（JWT）接続を作成するかを選択します。 OAuth接続を作成することを強くお勧めします。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!DNL Adobe] クライアント ID を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] クライアントの秘密鍵を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>OAuth接続を選択した場合は、この接続に必要なスコープを入力します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>JWT接続を選択した場合は、[!DNL Adobe] テクニカルアカウント IDを入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>JWT接続を選択した場合は、[!DNL Adobe]組織IDを入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>JWT接続を選択した場合は、この接続に必要なメタスコープを入力します。 </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>JWT 接続を選択した場合は、資格情報が [!DNL Adobe Developer Console] で作成されたときに生成された秘密鍵を入力します。 </p>
          <p>秘密鍵または証明書を抽出するには：</p>
          <ol>
            <li value="1">
              <p><b>[!UICONTROL Extract]</b> をクリックします。</p>
            </li>
            <li value="2">
              <p>抽出するファイルのタイプを選択します。</p>
            </li>
            <li value="3">
              <p>秘密鍵または証明書を含むファイルを選択します。</p>
            </li>
            <li value="4">
              <p>ファイルのパスワードを入力します。</p>
            </li>
            <li value="5">
              <p><b>[!UICONTROL Save]</b> をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL ベース URL]</td>
        <td>この認証者が許可するベース URLを追加する必要があります。 シナリオの後半で「カスタム API呼び出しを作成」モジュールを使用する場合は、選択したURLに相対パスを追加します。 ここでURLを入力すると、カスタム API呼び出しモジュールの接続先を制御できるので、セキュリティが強化されます。<p>認証者に追加する各ベース URLについて、<b>項目を追加</b>をクリックし、ベース URLを入力します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td><code>https://ims-na1.adobelogin.com</code>の標準Adobe IMS認証URLを使用する場合は、空白のままにします。 認証にAdobe IMSを使用しない場合は、認証に使用するURLを入力します。</td>
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## モジュール

* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [カスタム API呼び出しを行う（レガシー）](#make-a-custom-api-call-legacy)
* [カスタム API呼び出しを行う（ポーリング）](#make-a-custom-api-call-polling)

### カスタム API 呼び出しの実行

このアクションモジュールを使用すると、任意のAdobe APIを呼び出すことができます。 テキストのみの本文ではなく、大きなファイルをサポートします。

このモジュールは2024年11月14日に公開されました。 この日付より前に設定されたAdobe Authenticator/カスタム API呼び出しを行うと、大きなファイルは処理されず、カスタム API呼び出しを行う（レガシー）モジュールと見なされます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Adobe Authenticator モジュールへの接続を作成する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref" >接続を作成</a>」を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>接続するAPI ポイントのベース URLを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>ベース URLに対する相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
      </td>
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
        <p>リクエストクエリ文字列を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body Type]</td>
   <td> このAPI リクエストの本文タイプを選択します。
   <ul>
   <li>生</li>
   <li>application/x-www-form-urlencoded</li>
   <li>マルチパート/フォームデータ</li>
   </ul>
      </td>
      </tr>
    <tr>
      <td role="rowheader">[!UICONTROL出力タイプ ]  </td>
      <td>
        <p>モジュールで出力するデータのタイプを選択します。 タイプを選択しない場合、モジュールはタイプを自動的に選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

### カスタム API呼び出しを行う（レガシー）

このアクションモジュールを使用すると、任意のAdobe APIを呼び出すことができます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Adobe Authenticator モジュールへの接続を作成する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref" >接続を作成</a>」を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>接続するAPI ポイントのベース URLを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>ベース URLに対する相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
      </td>
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
        <p>リクエストクエリ文字列を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

### カスタム API呼び出しを行う（ポーリング）

このモジュールはカスタム呼び出しを行い、特定の条件が満たされるか、定義された制限に達するまで呼び出しを繰り返し実行するオプションを含みます。


<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Adobe Authenticator モジュールへの接続を作成する手順については、この記事の「<a href="#create-a-connection" class="MCXref xref" >接続を作成</a>」を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>接続するAPI ポイントのベース URLを入力します。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>ベース URLに対する相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
      </td>
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
        <p>リクエストクエリ文字列を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body Type]</td>
   <td> このAPI リクエストの本文タイプを選択します。
   <ul>
   <li>生</li>
   <li>application/x-www-form-urlencoded</li>
   <li>マルチパート/フォームデータ</li>
   </ul>
      </td>
      </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Repeat Until]  </td>
      <td>
        <p>ポーリングを停止するタイミングを決定する条件付きフィルターを設定します。 ドット表記法（<code>body.status</code>、<code>body.data.state</code>、<code>headers.status</code>など）を使用して応答データを参照できます。 条件は各実行後に評価され、条件が<code>true</code>に評価されるまでポーリングが続行されます。 サポートされている演算子は、<code>Equal to</code>、<code>Not equal to</code>、<code>Exists</code>です。 <code>Does not exist</code></p><p>例えば、<code>body.status not equal completed</code>を設定して、API応答がプロセスが完了したことを示すまでポーリングを続けることができます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Repeat Delay]  </td>
      <td>
        <p>実行間の遅延を秒単位で入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL リピート制限]  </td>
      <td>
        <p>API呼び出しを実行する最大回数を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL出力タイプ ]  </td>
      <td>
        <p>モジュールで出力するデータのタイプを選択します。 タイプを選択しない場合、モジュールはタイプを自動的に選択します。</p>
      </td>
    </tr>
  </tbody>
</table>
