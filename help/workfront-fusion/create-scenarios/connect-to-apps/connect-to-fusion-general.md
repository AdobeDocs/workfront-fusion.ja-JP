---
title: 接続の作成 – 基本的な手順
description: Adobe Workfront Fusion コネクタの多くは、接続作成時にカスタム設定を必要としません。 この記事では、デフォルトの接続作成プロセスについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 14%

---

# 接続の作成 – 基本的な手順

Adobe Workfront Fusion コネクタの多くは、接続作成時にカスタム設定を必要としません。 この記事では、デフォルトの接続作成プロセスについて説明します。

>[!NOTE]
>
>
>Adobe Workfront Fusion で、シナリオで使用する web サービスのアプリが提供されない場合は、次の記事で説明されているように、Workfront Fusion HTTP および Webhook モジュールを使用して web サービスに接続できます。
>
>* [API トークン認証を使用する web サービスにAdobe Workfront Fusion を接続する ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-wf-web-service-uses-api-token-auth.md)
>* [ コネクタを使用しない web サービスの Webhook の設定 ](/help/workfront-fusion/create-scenarios/add-modules/receive-a-webhook-from-a-web-service.md)

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）: Workfront ファミリー以外のアプリケーションに接続するには、作業の自動化と統合のためのWorkfront Fusion が必要です </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 接続の作成

特定のアプリケーションへの接続を作成するには、そのアプリケーションのモジュールに参加している必要があります。 例えば、Workfrontへの接続を作成するには、Workfront モジュールに参加している必要があります。

Workfront Fusion モジュール内に接続を作成するには：

1. 特定のアプリケーションの任意のモジュールで、「**[!UICONTROL 接続]**」ボックスの横にある [!UICONTROL  追加 ] をクリックして、**[!UICONTROL 接続を作成]** パネルを開きます。
1. （オプション）デフォルトの&#x200B;**[!UICONTROL 接続名]**&#x200B;を変更
1. 「環境」フィールドで、実稼動環境か非実稼動環境かを選択します。
1. 「タイプ」フィールドで、サービスか個人アカウントかを選択します。
1. （条件付き）アプリで ID、キー、[!UICONTROL シークレット] などの詳細な接続設定が必要な場合は、その情報を入力します。

   必要に応じて、「**[!UICONTROL 詳細設定を表示]**」をクリックして、このような情報を入力できるフィールドを表示します。

1. 「**[!UICONTROL 続行]**」をクリックします。
1. 表示されるログインウィンドウで、アプリにログインするための資格情報を入力します（まだ入力していない場合）。
1. （条件付き） **[!UICONTROL 許可]** ボタンが表示された場合は、コネクタが実行できるアクションを確認し、ボタンをクリックしてアプリをWorkfront Fusion に接続します。

   >[!NOTE]
   >
   >* 「環境」フィールドと「タイプ」フィールドは情報提供のみを目的としており、接続の機能は変更しません。 この情報は、Fusion の「接続」領域に表示され、組織の特定のユースケースに対してどの接続を使用するかを決定できます。
   >* 一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
   >
   >   例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。
