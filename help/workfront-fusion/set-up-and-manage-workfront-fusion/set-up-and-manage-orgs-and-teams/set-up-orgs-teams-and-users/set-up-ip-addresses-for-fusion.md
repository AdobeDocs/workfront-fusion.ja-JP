---
title: 許可リストに加える組織の Fusion の IP アドレスの設定
description: Fusion は、web 通信に特定の IP アドレスとドメインを使用します。 組織で Workfront を使用するには、これらを組織の許可リストに追加する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 406dd45c-0863-4270-a80e-c1c115e0b367
source-git-commit: 59d739093c88238af7a7e97499fd0c7d7cf6053a
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 49%

---

# 許可リストに加える組織の Fusion の IP アドレスの設定

Adobe Workfront Fusion は組織のネットワークと通信するので、その通信を許可するように組織のファイアウォールを設定する必要があります。 ファイアウォールは、組織のネットワークをインターネットから分離することによって機能する、非常に効果的なセキュリティ対策です。これにより、選択したデータとネットワークトラフィックのみが組織のネットワークに出入りできるようになります。ファイアウォールは、データの送受信を行うサイトに基づいて、データを許可またはブロックします。Fusion 管理者は、Fusion との間で送信されるデータが組織のファイアウォールを通過できるようにする必要があります。

これは、基本的に、ファイアウォールを介したデータの送受信が「許可」されているサイトの「リスト」である許可リストを通じて実現されます。サイトは、次の 2 つの方法のいずれかで識別できます。

* **IP アドレス**：52.31.132.175 などの一連の数値
* **ドメイン**:URL の一部（`www.thisdomain.com` の `thisdomain` など）

Fusion は、web 通信に特定の IP アドレスとドメインを使用します。 組織で Workfront を使用するには、これらを組織の許可リストに追加する必要があります。

通常、ネットワークは許可リスト管理者が設定します。 組織のネットワーク管理者と協力して、ファイアウォールでこれらの IP アドレスが許可されていることを確認します。ネットワーク管理者が誰であるかわからない場合は、組織の IT 部門が正しい方向を示してくれます。

>[!IMPORTANT]
>
>Fusion 管理者は、これらの IP アドレスとドメインが組織の許可リストに追加されていることを確認する必要があります。 これは、自分で追加しない場合でも当てはまります。Fusion で組織の許可リストを設定できません。

すべての Fusion IP アドレスとドメインを許可リストに追加することも、Fusion クラスターを見つけて、そのクラスターの IP アドレスとドメインのみを追加することもできます。

## すべての Fusion IP アドレスとドメインの追加

次の IP アドレスを許可リストに追加します。

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

## クラスターにのみ Fusion の IP アドレスとドメインを追加

### データセンターの特定

IP アドレスは、データが格納されている場所によって異なります。

URL を使用して Fusion にアクセスすると、URL を調べてデータセンターを見つけることができます。

| URL | データセンター |
| --- | --- |
| `https://app.workfrontfusion.com` | US データセンター |
| `https://app-eu.workfrontfusion.com` | EU データセンター |
| `https://app-az.workfrontfusion.com` | Azure クラスター |

`experience.adobe.com` から Fusion にアクセスする場合は、ブラウザーの「ネットワーク」タブを確認して、データセンターを特定できます。

| URL | データセンター |
| --- | --- |
| `https://fusion.adobe.com` への呼び出し | US データセンター |
| `https://eu.fusion.adobe.com` への呼び出し | EU データセンター |
| `https://az.fusion.adobe.com` への呼び出し | Azure クラスター |

### データセンターの IP アドレスとドメインの追加

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] EU Datacenter</td> 
   <td> 
    <ul> 
     <li>52.30.133.50</li> 
     <li>54.220.93.204</li> 
     <li>34.254.76.122</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront] US Datacenter</p> </td> 
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
   <td role="rowheader">[!DNL Adobe Workfront Fusion] Microsoft Azure クラスター上</td> 
   <td> 
    <ul> 
     <li>20.36.133.48/28</li> 
     <li>20.81.156.240/28</li> 
     <li>172.172.84.48/28</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

また、組織でアウトバウンドネットワークフィルタリングを使用している場合は、次のドメインを許可リストに追加して、システムからWorkfront Fusion にアクセスできるようにします。 これらは Webhook に使用されます

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] EU Datacenter</td> 
   <td> <p> hook.app-eu.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront] US Datacenter</p> </td> 
   <td> <p>hook.app.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront Fusion] Microsoft Azure クラスター上</p> </td> 
   <td> <p>hook.app-az.workfrontfusion.com </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>アウトバウンドネットワークフィルタリングはまれです。対応するために許可リストを更新する必要があるかどうかをネットワーク管理者に確認してください。
