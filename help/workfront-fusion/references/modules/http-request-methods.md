---
title: HTTP リクエストメソッド
description: モジュールでAPI呼び出しを設定する場合は、HTTP リクエストメソッドを選択する必要があります。 この記事では、使用可能な方法と、それぞれの方法を選択する理由について説明します。
author: Becky
feature: Workfront Fusion
exl-id: 481131c9-356a-4c62-a653-d6bba9be5be8
TQID: https://experienceleague.adobe.com/Z11y3dk6PtoN11Gja8S2ZyJlTJZNZfXfcPPrNJWvbRk
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 55%

---

# HTTP リクエストメソッド

モジュールでAPI呼び出しを設定する場合は、HTTP リクエストメソッドを選択する必要があります。 この記事では、使用可能な方法と、それぞれの方法を選択する理由について説明します。

## HTTP メソッド

次のいずれかの HTTP メソッドを使用します。

* **[!UICONTROL GET]**：パラメーターに基づいて web サーバーからデータを取得します。 [!UICONTROL GET] は、指定されたリソースの表現をリクエストし、成功した場合は、リクエストされたコンテンツを含む [!UICONTROL 200 OK] 応答メッセージを受け取ります。
* **[!UICONTROL POST]**：パラメーターに基づいて web サーバーにデータを送信します。 [!UICONTROL POST] リクエストには、ファイルのアップロードなどのアクションが含まれます。 複数の[!UICONTROL POST]sは、単一の[!UICONTROL POST]とは異なる結果になる可能性があるため、複数の[!UICONTROL POST]を誤って送信する場合には注意が必要です。 [!UICONTROL POST]が成功した場合、[!UICONTROL 200 OK]の応答メッセージが表示されます。
* **[!UICONTROL PUT]**：パラメーターに基づいて web サーバー内の場所にデータを送信します。 [!UICONTROL PUT] リクエストには、ファイルのアップロードなどのアクションが含まれます。 [!UICONTROL PUT]と[!UICONTROL POST]の違いは、PUTが等電位であることです。つまり、1回のPUT[!UICONTROL PUT]が成功した結果は、同一の多くの[!UICONTROL PUT]と同じです。 PUTが成功すると、200の応答メッセージ（通常は201または204）が表示されます。
* **[!UICONTROL PATCH]**：（一部の API 呼び出しモジュールでは使用不可）パラメーターに基づいて web サーバー上のリソースに部分的な変更を適用します。 [!UICONTROL PATCH] はべき等ではなく、複数の [!UICONTROL PATCH] の結果は意図しない影響をもたらす可能性があります。 [!UICONTROL PATCH] が成功した場合は、200 応答メッセージ（通常は 204）を受け取ります。
* **[!UICONTROL DELETE]**：パラメーター（リソースが存在する場合）に基づいて、指定したリソースを web サーバーから削除します。 [!UICONTROL DELETE] が成功した場合は、200 OK メッセージを受け取ります。
