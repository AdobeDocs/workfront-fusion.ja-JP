---
title: 組織の許可リストの Fusion 用の IP アドレスの設定
description: Fusionは、web通信に特定のIP アドレスとドメインを使用します。 組織で Workfront を使用するには、これらを組織の許可リストに追加する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 406dd45c-0863-4270-a80e-c1c115e0b367
TQID: https://experienceleague.adobe.com/-ogVZgc8Jan8jmPV-l8PzajHzJrZ1np6dS-h7OAYY10
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 569
ht-degree: 54%

---

# 組織の許可リストの Fusion 用の IP アドレスの設定

Adobe Workfront Fusionは組織のネットワークと通信するため、組織のファイアウォールはその通信を許可するように設定する必要があります。 ファイアウォールは、組織のネットワークをインターネットから分離することによって機能する、非常に効果的なセキュリティ対策です。 これにより、選択したデータとネットワークトラフィックのみが組織のネットワークに出入りできるようになります。 ファイアウォールは、データの送受信を行うサイトに基づいて、データを許可またはブロックします。 Fusion管理者は、Fusionとの間で送信されるデータが組織のファイアウォールを通過できることを確認する必要があります。

これは、基本的に、ファイアウォールを介したデータの送受信が「許可」されているサイトの「リスト」である許可リストを通じて実現されます。 サイトは、次の 2 つの方法のいずれかで識別できます。

* **IP アドレス**: 52.31.132.175などの一連の数値
* **ドメイン**: `www.thisdomain.com`の`thisdomain`など、URLの一部

Fusionは、web通信に特定のIP アドレスとドメインを使用します。 組織で Workfront を使用するには、これらを組織の許可リストに追加する必要があります。

通常、ネットワーク管理者は許可リスト管理者によって設定されます。 組織のネットワーク管理者と協力して、ファイアウォールでこれらの IP アドレスが許可されていることを確認します。 ネットワーク管理者が誰であるかわからない場合は、組織の IT 部門が正しい方向を示してくれます。

>[!IMPORTANT]
>
>Fusion管理者は、これらのIP アドレスとドメインが組織の契約許可リストに追加されていることを確認する必要があります。 これは、自分で追加しない場合でも当てはまります。 Fusionで組織のを設定できません。

すべてのFusion IP アドレスとドメインをPhoenix許可リストに追加するか、Fusion クラスターを見つけて、そのクラスターのIP アドレスとドメインのみを追加できます。

## すべてのFusion IP アドレスとドメインを追加する

次のIP アドレスを契約許可リストに追加します。

* 52.30.133.50
* 54.220.93.204
* 34.254.76.122
* 54.244.142.219
* 52.39.217.230
* 44.241.82.96
* 100.20.126.137
* 34.223.32.4
* 52.39.176.220
* 20.36.133.48/28
* 20.81.156.240/28
* 172.172.84.48/28

また、組織がアウトバウンドネットワークフィルタリングを使用している場合は、次のドメインを許可リストに追加して、システムが Workfront Fusion にアクセスできるようにします。

* hook.app.workfrontfusion.com
* hook.app-eu.workfrontfusion.com
* hook.app-az.workfrontfusion.com

## クラスターのFusion IP アドレスとドメインのみを追加する

### データセンターの特定

IP アドレスは、データが保存される場所によって異なります。

URLを介してFusionにアクセスする場合は、URLを調べてデータセンターを見つけることができます。

| URL | Datacenter |
| --- | --- |
| `https://app.workfrontfusion.com` | 米国データセンター |
| `https://app-eu.workfrontfusion.com` | EU データセンター |
| `https://app-az.workfrontfusion.com` | Azureクラスター |

`experience.adobe.com`経由でFusionにアクセスする場合は、ブラウザーの「ネットワーク」タブを確認して、データセンターを特定できます。

| URL | Datacenter |
| --- | --- |
| `https://fusion.adobe.com`への呼び出し | 米国データセンター |
| `https://eu.fusion.adobe.com`への呼び出し | EU データセンター |
| `https://az.fusion.adobe.com`への呼び出し | Azureクラスター |

### データセンターのIP アドレスとドメインの追加

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront EU Datacenter</td> 
   <td> 
    <ul> 
     <li>52.30.133.50</li> 
     <li>54.220.93.204</li> 
     <li>34.254.76.122</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Adobe Workfront US Datacenter</p> </td> 
   <td> 
    <ul> 
     <li>54.244.142.219</li> 
     <li>52.39.217.230</li> 
     <li>44.241.82.96</li>
     <li>100.20.126.137</li>
     <li>34.223.32.4</li>
     <li>52.39.176.220</li>
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Microsoft Azure クラスター上のAdobe Workfront Fusion</td> 
   <td> 
    <ul> 
     <li>20.36.133.48/28</li> 
     <li>20.81.156.240/28</li> 
     <li>172.172.84.48/28</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

また、組織がアウトバウンドネットワークフィルタリングを使用している場合は、次のドメインを許可リストに追加して、システムが Workfront Fusion にアクセスできるようにします。 これらはwebhookに使用されます

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront EU Datacenter</td> 
   <td> <p> hook.app-eu.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Adobe Workfront US Datacenter</p> </td> 
   <td> <p>hook.app.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Microsoft Azure クラスター上のAdobe Workfront Fusion</p> </td> 
   <td> <p>hook.app-az.workfrontfusion.com </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>アウトバウンドネットワークフィルタリングはまれです。 対応するために許可リストを更新する必要があるかどうかをネットワーク管理者に確認してください。
