---
title: HTTP／その他のモジュール
description: ' [!DNL Adobe Workfront Fusion]  HTTP アプリは、Hypertext Transfer Protocol（HTTP）で通信するための様々なモジュールを提供します。HTTP は、World Wide Web のためのデータ通信基盤です。このモジュールを使用すると、web のページやファイルをダウンロードしたり、web フックや API エンドポイントを呼び出したりできます。'
author: Becky
feature: Workfront Fusion
exl-id: 7db97e6e-262d-4be2-823b-423f56a7d886
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 85%

---

# HTTP／その他のモジュール

>[!NOTE]
>
>[!UICONTROL Adobe Workfront Fusion] には [!UICONTROL Adobe Workfront] ライセンスに加えて [!UICONTROL Adobe Workfront Fusion] ライセンスが必要です。

[!DNL Adobe Workfront Fusion] [!UICONTROL HTTP] アプリは、Hypertext Transfer Protocol （HTTP; ハイパーテキスト転送プロトコル）プロトコルに基づく通信用の様々なモジュールを提供します。 HTTP は、World Wide Web のためのデータ通信基盤です。このモジュールを使用すると、web のページやファイルをダウンロードしたり、web フックや API エンドポイントを呼び出したりできます。

モジュールの適切な選択は、アクセスするリソースが使用する認証 / 承認メカニズムによって異なります。次に、モジュールの例を示します。

* リクエストの作成：ユニバーサルモジュールは、主にどのタイプの認証 / 承認をも使用しないリソースを対象としています。
* 基本認証リクエストの作成：[!DNL HTTP] 基本認証（BA）を使用するリソース向け
* OAuth 2.0 リクエストの作成：OAuth 2.0 承認プロトコルを使用するリソース向け
* クライアント証明書認証リクエストの作成：クライアントサイドの証明書を必要とする認証プロトコルを使用しているリソース向け。
* API キー認証リクエストの作成：認証に API キーを使用しているリソース向け

>[!NOTE]
>
>現在専用コネクタがないAdobe製品に接続する場合は、Adobe Authenticator モジュールを使用することをお勧めします。
>
>詳しくは、[Adobe Authenticator モジュール](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md)を参照してください。

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
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>ダウンロードするファイルの URL を入力またはマッピングします。 </p> </td> 
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
