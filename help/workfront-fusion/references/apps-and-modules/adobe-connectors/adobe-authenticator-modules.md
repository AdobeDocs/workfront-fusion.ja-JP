---
title: Adobe Authenticator モジュール
description: Adobe Authenticator モジュールを使用すると、1 つの接続を使用して、API で任意のAdobe製品に接続できます。
author: Becky
feature: Workfront Fusion
exl-id: af4da661-eeee-4033-a2bb-a2196e446a3d
source-git-commit: 983ce043afbcc44ee8af2dfcd46738f170a2b257
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 30%

---

# Adobe Authenticator モジュール

Adobe Authenticator モジュールでは、1 回の接続を使用して任意のAdobe API に接続できます。 これにより、専用の Fusion コネクタがまだないAdobe製品に、より簡単に接続できます。

HTTP モジュールより有利な点は、専用のアプリのように接続を作成できることです。

使用可能なAdobe API のリストについては、[Adobe API](https://developer.adobe.com/apis) を参照してください。 割り当てられている API のみを使用できる場合があります。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

* モジュールを接続するAdobe製品へのアクセス権が必要です。
* Adobe Developer Consoleにアクセスできる必要があります。
* Adobe Developer Consoleに、モジュールの接続先となる API を含むプロジェクトがある必要があります。 実行できる操作：

   * API を使用して新しいプロジェクトを作成します。

     または
   * API を既存のプロジェクトに追加します。

  Adobeでの API のプロジェクトへの作成または追加については、Adobe Developer Console ドキュメントの [ プロジェクトの作成 ](https://developer.adobe.com/dep/guides/dev-console/create-project/) を参照してください。

## Adobe Authenticator API の情報

Adobe Authenticator コネクタでは、以下を使用します。

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

Adobe Authenticator接続は、Adobe Developer Console上の 1 つのプロジェクトに接続します。 複数のAdobe API に同じ接続を使用するには、API を同じプロジェクトに追加して、そのプロジェクトへの接続を作成します。

個別のプロジェクトに対して個別の接続を作成できますが、接続を使用して、その接続で指定されたプロジェクトにない API にアクセスすることはできません。

>[!IMPORTANT]
>
>Adobe Authenticator コネクタでは、OAuth サーバー間接続を使用するか、サービスアカウント（JWT）接続を使用するかを選択できます。 Adobeでは、JWT 資格情報を廃止しました。この資格情報は 2025 年 1 月 1 日（PT）以降、機能しなくなります。 **したがって、OAuth 接続を作成することを強くお勧めします。**
>
>これらの接続の詳細については、Adobe ドキュメントの [ サーバーからサーバーへの認証 ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/) を参照してください

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
          <p>OAuth サーバー間接続を作成するか、サービスアカウント（JWT）接続を作成するかを選択します。 OAuth 接続を作成することを強くお勧めします。</p>
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
        <td>OAuth 接続を選択した場合は、この接続に必要なスコープを入力します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>JWT 接続を選択した場合は、[!DNL Adobe] テクニカルアカウント ID を入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>JWT 接続を選択した場合は、[!DNL Adobe] 組織 ID を入力します。 これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>JWT 接続を選択した場合、この接続に必要なメタ範囲を入力します。 </td>
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
        <td>この認証を許可するベース URL を追加する必要があります。 シナリオの後半で「カスタム API 呼び出しを行う」モジュールを使用する場合、選択した URL への相対パスを追加します。 ここに URL を入力すると、カスタム API 呼び出しを行うモジュールが何に接続できるかを制御でき、セキュリティが強化されます。<p>認証サーバーに追加するベース URL ごとに、「<b> 項目を追加 </b>」をクリックしてベース URL を入力します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>標準のAdobe IMS認証 URL <code>https://ims-na1.adobelogin.com</code> を使用する場合は、この値を空白のままにします。 認証にAdobe IMSを使用しない場合は、認証に使用する URL を入力します。</td>
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## モジュール

* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [カスタム API 呼び出しの実行（レガシー）](#make-a-custom-api-call-legacy)

### カスタム API 呼び出しの実行

このアクションモジュールを使用すると、任意のAdobe API を呼び出すことができます。 テキストのみの本文ではなく、大きなファイルをサポートします。

このモジュールは、2024 年 11 月 14 日（PT）に使用可能になりました。 この日付より前に設定されたAdobe Authenticator/カスタム API 呼び出しを行では、大きなファイルを処理せず、カスタム API 呼び出しを行う（レガシー） モジュールと見なされるようになりました。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Adobe Authenticator モジュールへの接続を作成する手順については、この記事の <a href="#create-a-connection" class="MCXref xref" > 接続の作成 </a> を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>接続先の API ポイントのベース URL を入力します。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>ベース URL に対する相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p>
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
   <td> この API リクエストの本文タイプを選択：
   <ul>
   <li>生</li>
   <li>application/x-www-form-urlencoded</li>
   <li>multipart/form-data</li>
   </ul>
      </td>
      </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 出力タイプ ]  </td>
      <td>
        <p>モジュールが出力するデータのタイプを選択します。 タイプを選択しない場合、モジュールは自動的にタイプを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

### カスタム API 呼び出しの実行（レガシー）

このアクションモジュールを使用すると、任意のAdobe API を呼び出すことができます。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Adobe Authenticator モジュールへの接続を作成する手順については、この記事の <a href="#create-a-connection" class="MCXref xref" > 接続の作成 </a> を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>接続先の API ポイントのベース URL を入力します。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>ベース URL に対する相対パスを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p>
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
