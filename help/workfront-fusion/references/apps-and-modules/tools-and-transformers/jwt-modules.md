---
title: JWT モジュール
description: ' [!DNL Adobe Workfront Fusion] [!UICONTROL JWT] アプリには、指定されたアルゴリズムに基づいて JWT トークンを作成するモジュールが用意されています。'
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 7%

---

# [!UICONTROL JWT] モジュール

[!DNL Adobe Workfront Fusion] [!UICONTROL JWT] アプリには、指定されたアルゴリズムに基づいて JWT トークンを作成するモジュールが用意されています。

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
   <p>Workfront Fusion ライセンス要件なし</p>
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

## JWT API 情報

JWT コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
   <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.1.5</td> 
  </tr>
 </tbody> 
 </table>

## JWT モジュールとそのフィールド

### JWT を生成

このモジュールは、選択したアルゴリズムに基づいて JWT を生成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL アルゴリズム &#x200B;]</td> 
   <td> <p>JWT の生成に使用するアルゴリズムを選択します。</p> <ul>
   <li><b>HS256</b>: SHA-256 ハッシュ アルゴリズムを使用する HMAC</li>
   <li><b>HS384</b>: SHA-384 ハッシュ アルゴリズムを使用する HMAC</li>
   <li><b>HS512</b>: SHA-512 ハッシュ アルゴリズムを使用する HMAC</li>
   <li><b>RS256</b>: SHA-256 ハッシュ アルゴリズムを使用する RSASSA-PKCS1-v1_5</li>
   <li><b>RS384</b>: SHA-384 ハッシュアルゴリズムを使用する RSASSA-PKCS1-v1_5</li>
   <li><b>RS512</b>: SHA-512 ハッシュ アルゴリズムを使用する RSASSA-PKCS1-v1_5</li>
   <li><b>PS256</b>: SHA-256 ハッシュ アルゴリズムを使用する RSASSA-PSS （ノード ^6.12.0 または &gt;=8.0.0 のみ）</li>
   <li><b>PS384</b>: SHA-384 ハッシュ アルゴリズムを使用する RSASSA-PSS （ノード ^6.12.0 または &gt;=8.0.0 のみ）</li>
   <li><b>PS512</b>: SHA-512 ハッシュ アルゴリズムを使用する RSASSA-PSS （ノード ^6.12.0 または &gt;=8.0.0 のみ）</li>
   <li><b>ES256</b>: P-256 曲線と SHA-256 ハッシュアルゴリズムを使用した ECDSA</li>
   <li><b>ES384</b>: P-384 曲線と SHA-384 ハッシュアルゴリズムを使用した ECDSA</li>
   <li><b>ES512</b>: P-521 曲線と SHA-512 ハッシュ アルゴリズムを使用した ECDSA</li>
   </ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ペイロード &#x200B;] </td> 
   <td> <p>追加するペイロード項目ごとに、「<b> 項目を追加 </b>」をクリックし、項目のキーと値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Options] </td> 
   <td> <p>追加するオプション項目ごとに、<b> 項目を追加 </b> をクリックし、項目のキーと値を入力します。</p> <p>次のキーを使用できます。
   <ul>
   <li><b>algorithm</b>: （デフォルト：RS256）</li>
   <li><b>expiresIn</b>：秒単位または時間間隔（2 日、10 時間、7d など）を表す文字列で表されます。 数値は秒数として解釈されます。 文字列を使用する場合は、時間単位（日、時間など）を必ず指定します。指定しない場合は、ミリ秒単位がデフォルトで使用されます（120 は 120 ミリ秒に等しくなります）。</li>
   <li><b>notBefore</b>：秒数または時間間隔（2 日、10 時間、7d など）を表す文字列で表されます。 数値は秒数として解釈されます。 文字列を使用する場合は、時間単位（日、時間など）を必ず指定します。指定しない場合は、ミリ秒単位がデフォルトで使用されます（120 は 120 ミリ秒に等しくなります）。
</li>
   <li><b>対象読者</b></li>
   <li><b>発行者</b></li>
   <li><b>jwtid</b></li>
   <li><b>件名</b></li>
   <li><b>noTimestamp</b></li>
   <li><b>ヘッダー</b></li>
   <li><b>keyid</b></li>
   <li><b>mutatePayload</b>:<code>true</code> の場合、sign 関数はペイロードオブジェクトを直接変更します。 これは、クレームが適用された後で、トークンにエンコードされる前に、ペイロードへの生の参照が必要な場合に役立ちます。</li>
   <li><b>allowInsecureKeySizes</b>:<code>true</code> の場合、モジュラスが 2048 未満の秘密鍵を RSA に使用できます。</li>
   <li><b>allowInvalidAsymmetricKeyTypes</b>:<code>true</code> の場合は、指定されたアルゴリズムに一致しない非対称キーを許可します。 このオプションは後方互換性のみを目的としているので、使用しないでください。</li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>
