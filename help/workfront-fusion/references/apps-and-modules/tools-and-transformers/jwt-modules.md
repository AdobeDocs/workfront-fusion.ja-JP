---
title: JWT モジュール
description: Adobe Workfront Fusion [!UICONTROL JWT] アプリには、指定されたアルゴリズムに基づいてJWT トークンを作成するモジュールが用意されています。
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
TQID: https://experienceleague.adobe.com/90zhDiLzi34ES2MPE-hg26mmSHZ-XQIgZJIFeW4vwy4
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 528
ht-degree: 18%

---

# [!UICONTROL JWT] モジュール

Adobe Workfront Fusion [!UICONTROL JWT] アプリには、指定されたアルゴリズムに基づいてJWT トークンを作成するモジュールが用意されています。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++



## JWT API情報

JWT コネクタでは、次の機能を使用します。

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

### JWTを生成

このモジュールは、選択したアルゴリズムに基づいてJWTを生成します。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL アルゴリズム &#x200B;]</td> 
   <td> <p>JWTを生成するアルゴリズムを選択します。</p> <ul>
   <li><b>HS256</b>: SHA-256 ハッシュアルゴリズムを使用するHMAC</li>
   <li><b>HS384</b>: SHA-384 ハッシュアルゴリズムを使用するHMAC</li>
   <li><b>HS512</b>: SHA-512 ハッシュアルゴリズムを使用するHMAC</li>
   <li><b>RS256</b>: SHA-256 ハッシュアルゴリズムを使用したRSASSA-PKCS1-v1_5</li>
   <li><b>RS384</b>: SHA-384 ハッシュアルゴリズムを使用したRSASSA-PKCS1-v1_5</li>
   <li><b>RS512</b>: SHA-512 ハッシュアルゴリズムを使用したRSASSA-PKCS1-v1_5</li>
   <li><b>PS256</b>: SHA-256 ハッシュアルゴリズムを使用するRSASSA-PSS （ノード ^6.12.0または&gt;=8.0.0のみ）</li>
   <li><b>PS384</b>: SHA-384 ハッシュアルゴリズムを使用するRSASSA-PSS （ノード ^6.12.0または&gt;=8.0.0のみ）</li>
   <li><b>PS512</b>: SHA-512 ハッシュアルゴリズムを使用するRSASSA-PSS （ノード ^6.12.0または&gt;=8.0.0のみ）</li>
   <li><b>ES256</b>: P-256曲線とSHA-256 ハッシュアルゴリズムを使用するECDSA</li>
   <li><b>ES384</b>: P-384曲線とSHA-384 ハッシュアルゴリズムを使用するECDSA</li>
   <li><b>ES512</b>: P-521曲線とSHA-512 ハッシュアルゴリズムを使用するECDSA</li>
   </ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ペイロード &#x200B;] </td> 
   <td> <p>追加するペイロード項目ごとに、<b>項目を追加</b>をクリックし、項目のキーと値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Options] </td> 
   <td> <p>追加する各オプション項目について、<b>項目を追加</b>をクリックし、項目のキーと値を入力します。</p> <p>次のキーを使用できます。
   <ul>
   <li><b>algorithm</b>: （デフォルト：RS256）</li>
   <li><b>expiresIn</b>：秒単位または時間スパンを表す文字列（例：2日間、10時間、7d）で表されます。 数値は秒数として解釈されます。 文字列を使用する場合は、時間単位（日、時間など）を必ず指定してください。それ以外の場合は、ミリ秒単位がデフォルトで使用されます（120は120 ミリ秒に等しくなります）。</li>
   <li><b>notBefore</b>：秒単位または時間スパンを表す文字列（例：2日間、10時間、7d）で表されます。 数値は秒数として解釈されます。 文字列を使用する場合は、時間単位（日、時間など）を必ず指定してください。それ以外の場合は、ミリ秒単位がデフォルトで使用されます（120は120 ミリ秒に等しくなります）。
</li>
   <li><b>オーディエンス</b></li>
   <li><b>イシュア</b></li>
   <li><b>jwtid</b></li>
   <li><b>件名</b></li>
   <li><b>noTimestamp</b></li>
   <li><b>ヘッダー</b></li>
   <li><b>keyid</b></li>
   <li><b>mutatePayload</b>: <code>true</code>の場合、sign関数はペイロードオブジェクトを直接変更します。 これは、要求が適用された後、トークンにエンコードされる前にペイロードへの未加工の参照が必要な場合に便利です。</li>
   <li><b>allowInsecureKeySizes</b>: <code>true</code>の場合、モジュラスが2048未満の秘密鍵をRSAに使用できます。</li>
   <li><b>allowInvalidAsymmetricKeyTypes</b>: <code>true</code>の場合、指定されたアルゴリズムと一致しない非対称キーを許可します。 このオプションは下位互換性のためだけに意図されており、避けるべきです。</li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>
