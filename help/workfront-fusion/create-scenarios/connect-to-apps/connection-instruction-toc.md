---
title: 接続の作成
description: 接続は、接続先のアプリまたは web サービスの API で設定された要件に従う必要があります。このため、接続を設定する手順は、アプリや web サービスによって異なります。この記事は、Adobe Workfront Fusion を選択したアプリや web サービスに接続する手順を特定し見つけるのに役立ちます。
author: Becky
feature: Workfront Fusion
exl-id: 281403a6-6f88-4976-8a10-1d0848ef9b35
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 35%

---

# 接続の作成

接続は、接続先のアプリまたは web サービスの API で設定された要件に従う必要があります。このため、接続を設定する手順は、アプリや web サービスによって異なります。この記事は、Adobe Workfront Fusion を選択したアプリや web サービスに接続する手順を特定し見つけるのに役立ちます。

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
   <p>コネクタベース（従来）: Workfront ファミリー以外のアプリケーションに接続するには、作業の自動化と統合のためのWorkfront Fusion が必要です </p>
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

## 設定が不要なアプリまたは web サービスに接続

ほとんどの場合、このモジュールを使用して、追加の情報をほとんど含まない接続を作成することができます。Workfront Fusion で認証が自動的に処理されます。

特別な考慮事項のない接続の作成手順については、[&#x200B; 接続の作成 – 基本手順 &#x200B;](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) を参照してください。

## Adobe アプリまたはサービスへの接続

Adobeのアプリやサービスに接続するには、組織 ID やテクニカルアカウント ID など、Adobe Admin Consoleの情報が必要になる場合があります。

また、Adobe Authenticator モジュールを使用して、1 回の接続で任意のAdobe API に接続することもできます。 これにより、専用の Fusion コネクタがまだないAdobe製品に、より簡単に接続できます。

詳しい手順については、[&#x200B; コネクタの記事 &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-adobe-products) を参照してください。

## [!DNL Microsoft] アプリまたは web サービスに接続

Workfront Fusion のほとんどの [!DNL Microsoft] アプリでは、追加情報がなくても接続を作成できます。

次の状況では、接続を作成するために追加の手順が必要です。

* Microsoft Dynamics 365 モジュールを使用します。

  手順については、[Microsoft Dynamics 365 モジュール &#x200B;](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md) を参照してください。

* HTTP モジュールを使用したMicrosoft Graph API への接続

  手順については、[MS Graph REST API の呼び出し &#x200B;](/help/workfront-fusion/create-scenarios/connect-to-apps/call-the-ms-graph-rest-api.md) を参照してください。

## [!DNL Google] アプリまたは web サービスに接続

[!DNL Google] アプリに接続するプロセスは、使用している [!DNL Google] アカウントの種類によって異なる場合があります。さらに、Workfront Fusion に接続する際に、[!DNL Google] のセキュリティ対策のために追加の設定が必要になる場合があります。

詳しくは、以下を参照してください。

* [カスタム OAuth クライアントを使用して Google Services に Adobe Workfront Fusion を接続](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)
* [更新されたセキュリティ対策を使用して Google Services に Adobe Workfront Fusion を接続](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-google-with-new-security-measures.md)

## 追加の設定が必要なその他のアプリ

一部のアプリやサービスは、Workfront Fusion Connections の基本設定に従いません。 これらのアプリに接続する手順は、当該のアプリの記事で確認できます。

詳しい手順については、[&#x200B; コネクタの記事 &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-third-party-applications) を参照してください。
