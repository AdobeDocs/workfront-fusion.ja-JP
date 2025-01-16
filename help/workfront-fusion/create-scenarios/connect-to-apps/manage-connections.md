---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: connections-annd-webhooks
title: 接続の管理
description: ほとんどのアプリでは、接続を作成する必要があります。それによって、 [!DNL Adobe Workfront Fusion]  は特定のシナリオの設定に従って、特定のサードパーティサービスと通信できます。
author: Becky
feature: Workfront Fusion
exl-id: 26d7caad-8e12-4f04-ac7c-f71686c90ee6
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 21%

---

# 接続の管理

接続は、Fusion がアプリケーションへのアクセスに使用する認証と権限を表します。 各アプリケーションに 1 つ以上の接続を作成し、複数のモジュールやシナリオで同じ接続を使用できます。

これらの接続は、「接続」領域で管理できます。

接続について詳しくは、[ 接続の概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md) を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 接続の表示と管理

「接続」領域からすべての接続を管理できます。

>[!NOTE]
>
>接続はチームが所有します。 探している接続が見つからない場合は、正しいチームを表示していることを確認してください。
>
>新しいチームを選択するには、左側のナビゲーションでチーム名をクリックし、新しいチームを選択します。

1. 「接続」領域を開くには、左側のナビゲーションで **接続** ![ 接続アイコン ](assets/connections-icon.png) をクリックします。
1. 管理する接続を探し、その接続に対して次の手順を 1 つ以上実行します。
1. （任意）「環境」と「**タイプ**」のドロップダウンをクリックしてオプションを選択することで、環境 **接続タイプ** を割り当てます。
1. （オプション）Workfront Fusion に接続に対して付与された権限を表示するには、その接続の表示アイコン ![ 接続権限を表示 ](assets/view-connection-permissions.png) をクリックします。
1. （オプション）接続の名前を変更するには、接続名をハイライト表示し、新しい名前を入力します。
1. （オプション）接続を再認証するには、「**再認証**」をクリックします。
1. （オプション）接続を削除するには、「**削除**」をクリックし、「**本当ですか？**」をクリックします。
1. （オプション）サービスへの接続が正常に確立されたことを確認するには、「**確認**」をクリックします。

## 接続を更新する

[!DNL Workfront Fusion] は通常、任意のサービスに対するアクセス権を無制限で取得します。一部のアプリケーションでは、一定期間後にアクセス権限を更新する必要があります。 この場合、アクセス権が失効する直前に [!DNL Workfront Fusion] からメールで通知が届きます。

接続を更新するには：

1. 「接続」領域を開くには、左側のナビゲーションで **接続** ![ 接続アイコン ](assets/connections-icon.png) をクリックします。
1. 更新する接続を見つけます。
1. その接続の行で、**[!UICONTROL Connections]** 領域の「**[!UICONTROL Reauthorize]**」ボタンをクリックします。

## リソース

* 環境やタイプなどの接続メタデータについて詳しくは、[ 接続メタデータ ](/help/workfront-fusion/references/connections/connection-metadata.md) を参照してください。
