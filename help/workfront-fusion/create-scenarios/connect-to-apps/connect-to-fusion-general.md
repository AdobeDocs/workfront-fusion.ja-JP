---
title: 接続の作成 - 基本的な手順
description: 多くのAdobe Workfront Fusion コネクタは、接続の作成時にカスタム設定を必要としません。 この記事では、デフォルトの接続作成プロセスについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: bbd1ec27e52127c8814188612a1e8d5cfab0cd25
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 33%

---

# 接続の作成 - 基本的な手順

多くのAdobe Workfront Fusion コネクタは、接続の作成時にカスタム設定を必要としません。 この記事では、デフォルトの接続作成プロセスについて説明します。

>[!NOTE]
>
>
>Adobe Workfront Fusionで、シナリオで使用するweb サービス用のアプリが提供されない場合は、次の記事で説明するように、Workfront Fusion HTTPおよびWebhook モジュールを使用してweb サービスに接続できます。
>
>* [API トークン認証を使用するweb サービスにAdobe Workfront Fusionを接続する](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-wf-web-service-uses-api-token-auth.md)
>* [&#x200B; コネクタを使用しないweb サービスのWebhookの設定](/help/workfront-fusion/create-scenarios/add-modules/receive-a-webhook-from-a-web-service.md)

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

## 接続の作成

特定のアプリケーションへの接続を作成するには、そのアプリケーションのモジュールに属している必要があります。 例えば、Workfrontへの接続を作成するには、Workfront モジュールを使用する必要があります。

Workfront Fusion モジュール内で接続を作成するには：

1. 特定のアプリケーションの任意のモジュールで、[!UICONTROL 接続] ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックして、**[!UICONTROL 接続を作成]** パネルを開きます。
1. （オプション）デフォルトの&#x200B;**[!UICONTROL 接続名]**&#x200B;を変更
1. 「環境」フィールドで、実稼動環境と非実稼動環境のどちらかを選択します。
1. 「タイプ」フィールドで、これがサービスまたは個人アカウントかどうかを選択します。
1. （条件付き）アプリで ID、キー、[!UICONTROL シークレット] などの詳細な接続設定が必要な場合は、その情報を入力します。

   この種類の情報を入力できるフィールドを表示するには、**[!UICONTROL 詳細設定を表示]**&#x200B;をクリックする必要がある場合があります。

1. 「**[!UICONTROL 続行]**」をクリックします。
1. 表示されるログインウィンドウで、アプリにログインするための資格情報を入力します（まだ入力していない場合）。
1. （条件付き） **[!UICONTROL Allow]** ボタンが表示された場合は、コネクタが実行できるアクションを確認し、ボタンをクリックしてアプリをWorkfront Fusionに接続します。

   >[!NOTE]
   >
   >* 「環境」フィールドと「タイプ」フィールドは情報用であり、接続の機能は変更されません。 この情報はFusionの「接続」エリアに表示され、組織内の特定のユースケースに使用する接続を決定できます。
   >* 一部のMicrosoft アプリでは、同じ接続を使用し、個々のユーザー権限に関連付けられています。 したがって、接続を作成する際に、権限の同意画面には、現在のアプリケーションに必要な新しい権限に加えて、このユーザーの接続に以前に付与された権限が表示されます。
   >
   >   例えば、ユーザーがExcel コネクタを介して付与された「テーブルの読み取り」権限を持ち、Outlook コネクタで電子メールを読み取るための接続を作成した場合、権限の同意画面には、既に付与された「テーブルの読み取り」権限と新たに必要な「電子メールの書き込み」権限の両方が表示されます。
