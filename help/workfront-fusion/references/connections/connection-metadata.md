---
title: 接続メタデータ
description: Fusion ではメタデータを使用して接続の重要な属性を識別します。
author: Becky
feature: Workfront Fusion
exl-id: b41fbe8c-30fa-49d0-8a24-3535642b97ae
TQID: https://experienceleague.adobe.com/95OLgw45L7WeFuTtNYYD1lVYf916pkSNVVw0O8eZ9y8
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 289
ht-degree: 55%

---

# 接続メタデータ

Fusion ではメタデータを使用して接続の重要な属性を識別します。

接続メタデータは、新しい接続を作成する際に設定できます。 これらの属性は、接続の設定に使用するのと同じダイアログボックスに表示されます。

![接続メタデータ](assets/connection-metadata-setup.png)

Fusion ユーザーは、接続エリアから接続を表示および編集できます。 左側のナビゲーションで「接続」をクリックすると、接続エリアにアクセスできます。

左側のナビゲーションの![接続領域](assets/connections-in-left-nav.png)

<!--![Connection metadata in Connections area](assets/connections-area-metadata.png)-->

## 環境タイプ

Fusion 接続は、実稼動システムと非実稼動システムの両方で使用できます。 接続が接続する環境のタイプをマークできるため、実稼動環境の保護に役立ちます。

環境タイプは、他の接続メタデータと同様に、情報提供のみを目的として使用されます。 ユーザーは、この属性を正確に設定し、シナリオで正しい環境との接続を使用する責任があります。

## 認証タイプ

Fusion 接続は、サービスアカウントと個人アカウントの両方に使用できます。 Fusion としてシナリオが自動化される場合、サービスアカウントが認証に使用されます。 個人アカウントは、特定の人物に基づく認証です。 どの認証タイプを使用するかは、シナリオの要件によって異なります。 自動化されたユーザーアクションには、個人アカウントを使用する必要があります。 たとえば、Fusion シナリオで特定の人物による承認を自動化する場合、その人物の認証タイプを使用する必要があります。 それ以外の場合、FusionはFusionとして機能し、タイプはサービスアカウントである必要があります。

認証タイプは、他の接続メタデータと同様に、情報提供のみを目的として使用されます。 ユーザーは、この属性を正確に設定し、シナリオで正しいタイプの接続を使用する責任があります。

認証タイプについて詳しくは、アドビの認証ガイドの[認証](https://developer.adobe.com/developer-console/docs/guides/authentication/)を参照してください。

## リソース

* 接続メタデータの管理方法については、[接続の管理](/help/workfront-fusion/create-scenarios/connect-to-apps/manage-connections.md)を参照してください。
