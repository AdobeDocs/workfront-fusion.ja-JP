---
title: Adobe Workfront Fusion の HTTP モジュールでの相互 TLS の使用
description: Adobe Workfront Fusion HTTP モジュールで相互 TLS を使用すると、情報トランザクションの両側で相手の ID を検証できます。
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 88%

---

# [!DNL Adobe Workfront Fusion] の HTTP モジュールでの相互 TLS の使用

>[!NOTE]
>
>Adobe Workfront Fusion には、Adobe Workfront ライセンスに加えて [!DNL Adobe Workfront Fusion] ライセンスが必要です。

## 相互 TLS の概要

インターネットを介してデータを送信する場合は、データを正しい場所に送信すること、データを正しい場所から受信すること、データを対象の受信者のみが読み取れるようにすることが重要です。TLS が有効な場合、クライアント（情報をリクエストするコンピューター）は証明書を使用して、サーバー（情報を提供するコンピューター）の ID を検証します。これにより、安全な HTTP 接続が可能になります。

相互 TLS を使用すると、この ID 確認が両方の方法で実行できます。サーバーが証明書を送信してクライアントに ID を確認すると、クライアントの証明書もリクエストします。これにより、サーバーが誤用の原因となる情報をサイトやユーザーに送信しなくなります。

>[!INFO]
>
>**例：**
>
>* **TLS**：ユーザーがブラウザーに「MyGreatBank.com」と入力する際に、銀行情報を誤って使用したり販売したりするような web サイトではなく、確実に My Great Bank に移動することを望みます。また、自分の銀行口座情報が暗号化されていることを確認したいと考えています。
>
>   ブラウザー（クライアント）が MyGreatBank.com （サーバー）に接続すると、TLS では、ID を検証するために MyGreatBank.com から証明書を必要とします。証明書は [!DNL DigiCert] または [!DNL Thawte] のような認証局によって提供されます。ブラウザーは認証局を信頼するので、接続を許可します。
>
>* **相互 TLS**：MySoftware.com は、MyGreatBank.com API からの情報を必要とするソフトウェアクライアントです。MyGreatBank では、信頼できるクライアントだけがサーバーに接続できます。したがって、MyGreatBank.com の ID を確認する通常の TLS に加えて、TLS／認証局プロセスは MySoftware.com からのリクエストも検証します。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td> 
   <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td> 
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明する機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront] を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

&#42;ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

&#42;&#42;[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## [!DNL Workfront Fusion] 公開証明書の提供


HTTP リクエストを使用して web サービスに接続する場合、通常、web サービスには [!DNL Workfront Fusion] 検証用の公開証明書が必要です。これにより、web サービスは、証明書が web サービスの許可リストに載っていることを確認する方法として、HTTP リクエストで提示された証明書とファイル上の証明書を比較できるようになります。

[!DNL Adobe Workfront Fusion] 公開証明書を web サービスにアップロードする手順について詳しくは、web サービスのドキュメントを参照してください。

>[!NOTE]
>
>証明書に加えて、その他の情報も提供する必要がある場合があります。Web サービスに必要な情報について詳しくは、web サービスの API ドキュメントを参照してください。

次のリンクを使用して、Workfront Fusion の公開証明書をダウンロードできます。

### 2023 年 4 月 23 日（PT）から 2024 年 5 月 7 日（PT）の証明書

>[!IMPORTANT]
>
>* これらの [!DNL Workfront Fusion] 公開証明書の有効期限は 2025年5月7日（PT）です。有効期限が切れたら、新しい証明書を web サービスにアップロードする必要があります。次の操作をお勧めします。
>
>   * 有効期限をメモしておき、自分で証明書を web サービスにアップロードするようにリマインダーを設定します。
>   * 新しい証明書を簡単に見つけるには、このページをブックマークします。
>
>* これらは非ワイルドカードの mTLS 証明書です。

* [ [!DNL Workfront Fusion]  証明書 2023 をダウンロード](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem)
* [ [!DNL Workfront Fusion]  EU 証明書 2023 をダウンロード](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem)

  EU での使用

<!--

### Certificates for November 14, 2022 - July 15, 2023

>[!IMPORTANT]
>
>* These [!DNL Workfront Fusion] public certificates expire on July 15, 2023.
>* These are wildcard mTLS certificates.

* [Download [!DNL Workfront Fusion] Certificate 2023](https://cdn.experience.workfront.com/Documentation/Workfront+Fusion+2.0+public+certificates/app_workfrontfusion_com-jul-15-2023+updated.cer)
* [Download [!DNL Workfront Fusion] EU Certificate 2023](https://cdn.experience.workfront.com/Documentation/Workfront+Fusion/app-eu_workfrontfusion_com-jul-15-2023.cer)

   For use in the EU 

   -->

## [!DNL Workfront Fusion] HTTP モジュールでの相互 TLS の有効化 

すべての [!DNL Workfront Fusion] [!UICONTROL HTTP] リクエストモジュールには、相互 TLS を有効にするオプションがあります。

[!UICONTROL HTTP] リクエストモジュールで相互 TLS を有効にする手順は次のとおりです。

1. シナリオに [!UICONTROL HTTP] リクエストモジュールを追加します。
1. モジュールの設定を開始します。

   <!--For instructions on configuring an [!UICONTROL HTTP] request module, see the appropriate article under [[!UICONTROL Universal connectors] modules](/help/workfront-fusion/references/apps-and-modules/universal-connectors/).-->

1. モジュールの下部付近にある **[!UICONTROL Show advanced settings]** を有効にします。
1. **[!UICONTROL Use Mutual TLS]** を有効にします。
