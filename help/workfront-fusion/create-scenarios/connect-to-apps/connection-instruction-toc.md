---
title: 接続の作成
description: 接続は、接続先のアプリまたは web サービスの API で設定された要件に従う必要があります。 このため、接続を設定する手順は、アプリや web サービスによって異なります。 この記事では、Adobe Workfront Fusionを選択したアプリまたはweb サービスに接続するための手順を特定し、見つけるのに役立ちます。
author: Becky
feature: Workfront Fusion
exl-id: 281403a6-6f88-4976-8a10-1d0848ef9b35
TQID: https://experienceleague.adobe.com/qjxlwSzWy6FmnASQrhjVKe8A4VyBpw0aBHkNwgQpo3A
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 53%

---

# 接続の作成

接続は、接続先のアプリまたは web サービスの API で設定された要件に従う必要があります。 このため、接続を設定する手順は、アプリや web サービスによって異なります。 この記事では、Adobe Workfront Fusionを選択したアプリまたはweb サービスに接続するための手順を特定し、見つけるのに役立ちます。

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
   <p>コネクターベース（レガシー）: Workfront以外のアプリケーションに接続するには、作業の自動化と統合用のWorkfront Fusionが必要です </p>
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

## 設定が不要なアプリまたは web サービスに接続

ほとんどの場合、このモジュールを使用して、追加の情報をほとんど含まない接続を作成することができます。 Workfront Fusionが認証を自動的に処理します。

特別な考慮事項のない接続を作成する手順については、[接続の作成 – 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

## Adobe アプリまたはサービスへの接続

Adobe アプリまたはサービスに接続するには、組織IDやテクニカルアカウント IDなど、Adobe Admin Consoleの情報が必要になる場合があります。

また、Adobe Authenticator モジュールを使用して、1つの接続を使用して任意のAdobe APIに接続することもできます。 これにより、専用のFusion コネクタを持たないAdobe製品に簡単に接続できます。

具体的な手順については、[&#x200B; コネクタの記事](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-adobe-products)を参照してください。

## [!DNL Microsoft] アプリまたは web サービスに接続

Workfront Fusionのほとんどの[!DNL Microsoft] アプリでは、追加情報なしで接続を作成できます。

次の状況では、接続を作成する際に追加の手順が必要です。

* Microsoft Dynamics 365 モジュールの使用。

  手順については、[Microsoft Dynamics 365 modules](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md)を参照してください。

* HTTP モジュールを使用したMicrosoft Graph APIへの接続

  手順については、[MS Graph REST APIの呼び出し](/help/workfront-fusion/create-scenarios/connect-to-apps/call-the-ms-graph-rest-api.md)を参照してください。

## [!DNL Google] アプリまたは web サービスに接続

[!DNL Google] アプリに接続するプロセスは、使用している [!DNL Google] アカウントの種類によって異なる場合があります。 さらに、[!DNL Google]個のセキュリティ対策を行う場合、Workfront Fusionに接続する際に追加の設定が必要になる場合があります。

詳しくは、以下を参照してください。

* [カスタム OAuth クライアントを使用して Google Services に Adobe Workfront Fusion を接続](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)
* [更新されたセキュリティ対策を使用して Google Services に Adobe Workfront Fusion を接続](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-google-with-new-security-measures.md)

## 追加の設定が必要なその他のアプリ

一部のアプリやサービスは、Workfront Fusion接続の基本設定に従っていません。 これらのアプリに接続する手順は、当該のアプリの記事で確認できます。

具体的な手順については、[&#x200B; コネクタの記事](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-third-party-applications)を参照してください。
