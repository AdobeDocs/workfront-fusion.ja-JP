---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: connections-annd-webhooks
title: 接続の管理
description: ほとんどのアプリでは、接続を作成する必要があります。それによって、Adobe Workfront Fusion は特定のシナリオの設定に従って、特定のサードパーティサービスと通信できます。
author: Becky
feature: Workfront Fusion
exl-id: 26d7caad-8e12-4f04-ac7c-f71686c90ee6
TQID: https://experienceleague.adobe.com/P-zEd2tJCk9-uzE1xW6COpTCdFJiIq4NwGRLDdpCSVU
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 586
ht-degree: 29%

---

# 接続の管理

接続は、Fusion がアプリケーションへのアクセスに使用する認証と権限を表します。 アプリケーションごとに1つ以上の接続を作成でき、複数のモジュールまたはシナリオで同じ接続を使用できます。

これらの接続は、「接続」エリアで管理できます。

接続について詳しくは、[接続の概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md)を参照してください。

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

## 接続の表示と管理

「接続」エリアからすべての接続を管理できます。

>[!NOTE]
>
>接続はチームが所有します。 探している接続が見つからない場合は、正しいチームを表示していることを確認してください。
>
>新しいチームを選択するには、左側のナビゲーションでチーム名をクリックし、新しいチームを選択します。

1. 「接続」領域を開くには、左側のナビゲーションで「**接続** ![接続」アイコン &#x200B;](assets/connections-icon.png)」をクリックします。
1. 管理する接続を見つけ、その接続の行で次の1つ以上の手順を実行します。
1. （オプション）環境と接続タイプを割り当てるには、**環境**&#x200B;および&#x200B;**タイプ** ドロップダウンをクリックし、オプションを選択します。
1. （オプション）接続に対してWorkfront Fusionに付与された権限を表示するには、表示アイコン ![接続の権限を表示](assets/view-connection-permissions.png)をクリックします。
1. （オプション）接続の名前を変更するには、接続名を強調表示し、新しい名前を入力します。
1. （オプション）接続を再認証するには、接続の横にあるチェックボックスをオンにし、画面下部にある「**再認証**」をクリックします。
1. （オプション）接続を削除するには、接続の横にあるチェックボックスをオンにし、画面下部の&#x200B;**削除**&#x200B;をクリックしてから、**本当か**&#x200B;をクリックします。
1. （オプション）サービスへの接続が正常に確立されたことを確認するには、接続の横にあるチェックボックスをオンにし、画面下部の「**確認**」をクリックします。
1. （オプション）この接続を使用するアクティブなシナリオを表示するには、接続の横にあるチェックボックスをオンにし、**アクティブなシナリオを取得**&#x200B;をクリックします。 次に、「アクティブなシナリオ」リストのシナリオをクリックして、そのシナリオに移動できます。

## 接続を更新する

Workfront Fusionは通常、特定のサービスに対するアクセス権を無制限に取得します。 一部のアプリケーションでは、一定期間が経過した後にアクセス権限を更新する必要があります。 このような場合、アクセス権が失効する直前に、Workfront Fusionからメールで通知が送信されます。

接続を更新するには：

1. 「接続」領域を開くには、左側のナビゲーションで「**接続** ![接続」アイコン &#x200B;](assets/connections-icon.png)」をクリックします。
1. 更新する接続を探します。
1. その接続の行で、接続の横にあるチェックボックスをオンにし、画面下部の「**再認証**」をクリックします。

## リソース

* 環境やタイプなどの接続メタデータについて詳しくは、[接続メタデータ &#x200B;](/help/workfront-fusion/references/connections/connection-metadata.md)を参照してください。
