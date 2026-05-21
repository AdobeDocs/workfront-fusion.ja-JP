---
title: Adobe Workfront Fusion の HTTP モジュールでの相互 TLS の使用
description: Adobe Workfront Fusion HTTP モジュールで相互 TLS を使用すると、情報トランザクションの両側で相手の ID を検証できます。
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
TQID: https://experienceleague.adobe.com/L-0fyqwvahM--LXM15no9APxcFNkAsoYqHwAqO1bAno
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 902
ht-degree: 66%

---

# Adobe Workfront Fusion の HTTP モジュールでの相互 TLS の使用

## 相互 TLS の概要

インターネットを介してデータを送信する場合は、データを正しい場所に送信すること、データを正しい場所から受信すること、データを対象の受信者のみが読み取れるようにすることが重要です。 TLS が有効な場合、クライアント（情報をリクエストするコンピューター）は証明書を使用して、サーバー（情報を提供するコンピューター）の ID を検証します。 これにより、安全な HTTP 接続が可能になります。

相互 TLS を使用すると、この ID 確認が両方の方法で実行できます。 サーバーが証明書を送信してクライアントに ID を確認すると、クライアントの証明書もリクエストします。 これにより、サーバーが誤用の原因となる情報をサイトやユーザーに送信しなくなります。

>[!INFO]
>
>**例：**
>
>* **TLS**：ユーザーがブラウザーに「MyGreatBank.com」と入力する際に、銀行情報を誤って使用したり販売したりするような web サイトではなく、確実に My Great Bank に移動することを望みます。 また、自分の銀行口座情報が暗号化されていることを確認したいと考えています。
>
>   ブラウザー（クライアント）が MyGreatBank.com （サーバー）に接続すると、TLS では、ID を検証するために MyGreatBank.com から証明書を必要とします。 証明書は [!DNL DigiCert] または [!DNL Thawte] のような認証局によって提供されます。 ブラウザーは認証局を信頼するので、接続を許可します。
>
>* **相互 TLS**：MySoftware.com は、MyGreatBank.com API からの情報を必要とするソフトウェアクライアントです。 MyGreatBank では、信頼できるクライアントだけがサーバーに接続できます。 したがって、MyGreatBank.com の ID を確認する通常の TLS に加えて、TLS／認証局プロセスは MySoftware.com からのリクエストも検証します。

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

## Workfront Fusion公開証明書の提供

HTTP リクエストを使用してweb サービスに接続する場合、web サービスは通常、検証用にWorkfront Fusionの公開証明書を必要とします。 これにより、web サービスは、証明書が web サービスの許可リストに載っていることを確認する方法として、HTTP リクエストで提示された証明書とファイル上の証明書を比較できるようになります。

Adobe Workfront Fusion公開証明書をweb サービスにアップロードする方法については、web サービスのドキュメントを参照してください。

>[!NOTE]
>
>証明書に加えて、その他の情報も提供する必要がある場合があります。 Web サービスに必要な情報について詳しくは、web サービスの API ドキュメントを参照してください。

次のリンクを使用して、Workfront Fusionの公開証明書をダウンロードできます。 データセンターを見つけるには、組織の「FusionのIP アドレスの設定」の記事の「[ データセンターの特定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)」を参照してください。

### 2026年の証明書

>[!IMPORTANT]
>
>* これらのWorkfront Fusion公開証明書の有効期限は、クラスターによって異なります。 以下のグラフを確認して、有効期限が切れるタイミングを確認してください。 有効期限が切れた後、新しい証明書をWeb サービスにアップロードする必要があります。 次の操作をお勧めします。
>
>   * 有効期限をメモしておき、自分で証明書を web サービスにアップロードするようにリマインダーを設定します。
>   * 新しい証明書を簡単に見つけるには、このページをブックマークします。
>
>* これらは非ワイルドカードの mTLS 証明書です。

| Datacenter | ダウンロードリンク | 日付は有効です |
| --- | --- | --- |
| US AWS Datacenter | [Workfront Fusion US証明書2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-us-mtls-certificate-2026.pem)をダウンロード | 2026年1月29日～2027年3月2日 |
| US Azure クラスター | [Workfront Fusion US Azure Certificate 2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-az-mtls-certificate.pem)をダウンロード | 2025年9月21日～2026年10月23日 |
| EU AWS データセンター | [Workfront Fusion EU証明書2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-eu-mtls-certificate-2026.pem)をダウンロード | 2026年1月29日～2027年3月2日 |
| EUAzureクラスター | [Workfront Fusion EU Azure証明書2026](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2026-certs/fusion-prod-eu-az-mtls-certificate-2026.pem)をダウンロード | 2026年2月4日～2027年3月8日 |

### 2025年の証明書

>[!IMPORTANT]
>
>* 上記の2026年の証明書をインストールすることをお勧めします。
>* これらのWorkfront Fusion公開証明書の有効期限は、**2026年4月4日** （米国およびEU）または&#x200B;**2025年11月25日** （Azure）です。 有効期限が切れたら、新しい証明書を web サービスにアップロードする必要があります。 次の操作をお勧めします。
>
>   * 有効期限をメモしておき、自分で証明書を web サービスにアップロードするようにリマインダーを設定します。
>   * 新しい証明書を簡単に見つけるには、このページをブックマークします。
>
>* これらは非ワイルドカードの mTLS 証明書です。

| Datacenter | ダウンロードリンク | 日付は有効です |
| --- | --- | --- |
| US Datacenter | [Workfront Fusion US証明書2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-us-mtls-certificate.pem)をダウンロード | 2025年3月3日～2026年4月4日 |
| EU Datacenter | [Workfront Fusion EU証明書2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-eu-mtls-certificate.pem)のダウンロード | 2025年3月3日～2026年4月4日 |
| Azure クラスター | [Workfront Fusion Azure証明書のダウンロード 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-az-mtls-certificate.pem) | 2024年10月24日～2025年11月25日 |

<!--

### Certificates for 2024

>[!IMPORTANT]
>
>* We recommend installing the certificates for 2025, available above.
>* These Workfront Fusion public certificates expire on **May 7, 2025**. After yours expires you will need to upload a new certificate to the web service. We recommend that you:
>
>   * Make note of the expiration date and set a reminder for yourself to upload the certificate to your web service.
>   * Bookmark this page to easily find the new certificates.
>
>* These are non-wildcard mTLS certificates.

| Datacenter | Download link | Dates valid |
|---|---|---|
| US Datacenter | [Download Workfront Fusion Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |
| EU Datacenter | [Download Workfront Fusion EU Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |

-->

## Workfront Fusion HTTP モジュールでの相互TLSの有効化

すべてのWorkfront Fusion [!UICONTROL HTTP] リクエストモジュールには、相互TLSを有効にするオプションがあります。

[!UICONTROL HTTP] リクエストモジュール内で相互 TLS を有効にするには：

1. [!UICONTROL HTTP] リクエストモジュールをシナリオに追加します。
1. モジュールの設定を開始します。

   [!UICONTROL HTTP] リクエストモジュールの設定方法については、[ ユニバーサルコネクタ ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)の下にある適切な記事を参照してください。

1. モジュールの下部付近にある「**[!UICONTROL 詳細設定を表示]**」を有効にします。
1. 「**[!UICONTROL 相互 TLS を使用]**」を有効にします。
