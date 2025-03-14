---
title: 接続の作成 – 基本的な手順
description: 多数の [!DNL Adobe Workfront Fusion] コネクタでは、接続を作成するときにカスタム設定は必要ありません。この記事では、デフォルトの接続作成プロセスについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 37%

---

# 接続の作成 – 基本的な手順

[!DNL Adobe Workfront Fusion] コネクタの多くは、接続を作成するときにカスタム設定を必要としません。 この記事では、デフォルトの接続作成プロセスについて説明します。

>[!NOTE]
>
>
>Adobe Workfront Fusion で、シナリオで使用する web サービスのアプリが提供されない場合は、以下の記事で説明されているように、HTTP モジュールと Webhook モジュール [!DNL Workfront Fusion] 使用して web サービスに接続できます。
>
>* [API トークン認証を使用する web サービスにAdobe Workfront Fusion を接続する ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-wf-web-service-uses-api-token-auth.md)
>* [ コネクタを使用しない web サービスの Webhook の設定 ](/help/workfront-fusion/create-scenarios/add-modules/receive-a-webhook-from-a-web-service.md)

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront プランを選択する：組織がAdobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 接続の作成

[!DNL Workfront Fusion] モジュール内で接続を作成するには、以下を実行します。

1. [!UICONTROL 接続]ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックして、**[!UICONTROL 接続の作成]**&#x200B;パネルを開きます。
1. （オプション）デフォルトの&#x200B;**[!UICONTROL 接続名]**&#x200B;を変更
1. 「環境」フィールドで、実稼動環境か非実稼動環境かを選択します。 この情報は、Fusion の「接続」領域に表示されます。
1. 「タイプ」フィールドで、サービスか個人アカウントかを選択します。 この情報は、Fusion の「接続」領域に表示されます。
1. （条件付き）アプリで ID、キー、[!UICONTROL シークレット] などの詳細な接続設定が必要な場合は、その情報を入力します。

   この種の情報を入力できるフィールドを表示するには、**[!UICONTROL 詳細設定を表示]**&#x200B;をクリックする必要がある場合があります。

1. 「**[!UICONTROL 続行]**」をクリックします。
1. 表示されるログインウィンドウで、アプリにログインするための資格情報を入力します（まだ入力していない場合）。
1. （条件付き）「**[!UICONTROL 許可]**」ボタンが表示された場合、コネクタが実行できるアクションを調べてから、ボタンをクリックしてアプリを [!DNL Workfront Fusion] に接続します。

   >[!NOTE]
   >
   >一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
   >
   >例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。
