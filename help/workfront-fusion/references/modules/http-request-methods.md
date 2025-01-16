---
title: HTTP リクエストメソッド
description: モジュールで API 呼び出しを設定する場合、HTTP リクエストメソッドを選択する必要があります。 この記事では、使用可能な方法と、それぞれの方法を選択する理由について説明します。
author: Becky
feature: Workfront Fusion
exl-id: 481131c9-356a-4c62-a653-d6bba9be5be8
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 3%

---

# HTTP リクエストメソッド

モジュールで API 呼び出しを設定する場合、HTTP リクエストメソッドを選択する必要があります。 この記事では、使用可能な方法と、それぞれの方法を選択する理由について説明します。

## HTTP メソッド

次のいずれかの HTTP メソッドを使用します。

* **[!UICONTROL GET]**：パラメーターに基づいて web サーバーからデータを取得します。 [!UICONTROL GET] は、指定されたリソースの表現をリクエストし、成功した場合は、リクエストされたコンテンツを含む [!UICONTROL 200 OK] 応答メッセージを受け取ります。
* **[!UICONTROL POST]**：パラメーターに基づいて web サーバーにデータを送信します。 [!UICONTROL POST] リクエストには、ファイルのアップロードなどのアクションが含まれます。 複数の [!UICONTROL POST] を使用すると、1 つの [!UICONTROL POST] とは異なる結果になる可能性があるので、意図せずに複数の [!UICONTROL POST] を送信する場合は注意が必要です。リクエストが成功した場合は、[!UICONTROL 200 OK] の応答 [!UICONTROL POST] ッセージが表示されます。
* **[!UICONTROL PUT]**：パラメーターに基づいて、web サーバー内の場所にデータを送信します。 [!UICONTROL PUT] リクエストには、ファイルのアップロードなどのアクションが含まれます。 [!UICONTROL PUT] と [!UICONTROL POST] の違いは、PUTのべき等であるということです。つまり、1 回の [!UICONTROL PUT] が成功した場合の結果は、多くの同一の [!UICONTROL PUT] と同じになります。PUTが成功すると、200 件の応答メッセージ（通常は 201 件または 204 件）が表示されます。
* **[!UICONTROL PATCH]**: （一部の API 呼び出しモジュールでは使用できません）パラメーターに基づいて、web サーバー上のリソースに部分変更を適用します。 [!UICONTROL PATCH] はべき等ではありません。つまり、複数の [!UICONTROL PATCH] の結果として、意図しない結果が生じる可能性があります。 リクエストが成功した場合は、200 件の応答 [!UICONTROL PATCH] ッセージ（通常は 204 件）が返されます。
* **[!UICONTROL DELETE]**：パラメーターに基づいて、指定されたリソースを web サーバーから削除します（リソースが存在する場合）。 リクエストが成功した場合は、200 OK の [!UICONTROL DELETE] ッセージが返されます。
