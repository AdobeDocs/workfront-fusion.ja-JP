---
title: HTTP／その他のモジュール
description: ' [!DNL Adobe Workfront Fusion]  HTTP アプリは、Hypertext Transfer Protocol（HTTP）で通信するための様々なモジュールを提供します。HTTP は、World Wide Web のためのデータ通信基盤です。このモジュールを使用すると、web のページやファイルをダウンロードしたり、web フックや API エンドポイントを呼び出したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 7db97e6e-262d-4be2-823b-423f56a7d886
source-git-commit: a7ee3e751b75523c4da62cea71e59a63f98b95e0
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 58%

---

# HTTP／その他のモジュール

[!DNL Adobe Workfront Fusion] [!UICONTROL HTTP] アプリは、Hypertext Transfer Protocol （HTTP; ハイパーテキスト転送プロトコル）プロトコルに基づく通信用の様々なモジュールを提供します。 HTTP は、World Wide Web のためのデータ通信基盤です。このモジュールを使用すると、web のページやファイルをダウンロードしたり、web フックや API エンドポイントを呼び出したりできます。

モジュールの適切な選択は、アクセスするリソースが使用する認証 / 承認メカニズムによって異なります。次に、モジュールの例を示します。

* **リクエストを行う**：主に、あらゆるタイプの認証または承認を使用していないリソースを対象としています
* **基本認証リクエストの作成**:[!DNL HTTP] 基本認証（BA）を使用するリソースの場合
* **OAuth 2.0 リクエストの作成**:OAuth 2.0 認証プロトコルを使用するリソースの場合
* **クライアント証明書認証リクエストの作成**: クライアント側の証明書を必要とする認証プロトコルを使用するリソースの場合
* **API キー認証リクエストの作成**：認証用に API キーを使用するリソースの場合

>[!NOTE]
>
>現在専用コネクタがないAdobe製品に接続する場合は、Adobe Authenticator モジュールを使用することをお勧めします。
>
>詳しくは、[Adobe Authenticator モジュール](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md)を参照してください。

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
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
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

## リクエストモジュール

特定のリクエストモジュールの手順については、次の記事を参照してください。

* [[!UICONTROL HTTP] > [!UICONTROL Make a request] モジュール](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make a Basic Authorization request] モジュール](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-basic-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0 request] モジュール](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make a Client Certificate Authorization request] モジュール](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-client-cert-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make an API Key Authorization request]](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-api-key-auth-request.md)

## その他のアクションモジュール

* [[!UICONTROL Get a File]](#get-a-file)
* [[!UICONTROL Resolve a target URL]](#resolve-a-target-url)

### [!UICONTROL Get a File]

このアクションモジュールでは、指定した URL からファイルをダウンロードします。ファイルがダウンロードされたら、シナリオ内の他のモジュールを使用して、ファイルをさらに処理（ファイルデータをマッピング）できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx )] </td> 
   <td> <p>エラー処理を設定するには、このオプションを使用します。</p> <p>詳しくは、<a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> でのエラー処理を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>ダウンロードするファイルの URL を入力またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules] </td> 
   <td> <p>このサイトの Cookie を他のモジュールで使用できるようにする場合は、このオプションを有効にします。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Resolve a target URL]

このアクションモジュールは、HTTP リダイレクトの連鎖を解決し、ターゲット URL を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>[!DNL bit.ly] URL などの解決する URL を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method] </td> 
   <td> <p>[!UICONTROL HEAD] メソッドと [!UICONTROL GET] メソッドのどちらを使用するかを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

## イテレータモジュール

### [!UICONTROL Retrieve headers]

このモジュールは、指定された HTTP モジュールの各ヘッダー（名前と値）を個別のバンドルで返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> ヘッダーの取得元のモジュールを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

## JSON Web トークン（JWT）の生成

組み込みの関数のヘルプを使用して JWT トークンを生成できます。

ヘッダー:

![JWT ヘッダー ](/help/workfront-fusion/references/apps-and-modules/assets/jwt-header-350x19.png)

コピーおよび貼り付けのコード：

```
{{replace(replace(replace(base64("{""alg"":""HS256"",""typ"":""JWT""}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

ペイロード：

![JWT ペイロード ](/help/workfront-fusion/references/apps-and-modules/assets/jwt-payload-350x17.png)

コピーおよび貼り付けのコード：

```
{{replace(replace(replace(base64("{""iss"":""key"",""exp"":" + (timestamp + 60) + "}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

トークン：

![JWT トークン ](/help/workfront-fusion/references/apps-and-modules/assets/jwt-token-350x15.png)

コピーおよび貼り付けのコード：

```
{{1.value}}.{{2.value}}.{{replace(replace(replace(sha256(1.value + "." + 2.value; "base64"; "secret"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```
