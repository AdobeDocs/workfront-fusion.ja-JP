---
title: Microsoft SQL Server モジュール
description: ' [!DNL Adobe Workfront Fusion]  を使用して Microsoft SQL Server に接続することができます。'
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 67%

---

# [!DNL Microsoft SQL Server] モジュール

[!DNL Adobe Workfront Fusion] を使用して [!UICONTROL Microsoft SQL Server] に接続できます。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。



## [!DNL Microsoft SQL Server] サービスを [!DNL Workfront Fusion] に接続

[!DNL Microsoft SQL Server] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

## [!DNL Microsoft SQL Server] モジュールの使用

ストアドプロシージャを使用して、カスタムロジックをデータベースサーバー上で直接実行できます。[!DNL Adobe Workfront Fusion] はレコードセットと入力／出力パラメーターのインターフェイスを動的に読み込み、各パラメーターまたは値を個別にマッピングできます。シナリオの設定を開始する前に、データベースに接続するために使用するアカウントに、`INFORMATION_SCHEMA.ROUTINES` および `INFORMATION_SCHEMA.PARAMETERS` ビューへの読み取りアクセス権があることを確認してください。

[!DNL Fusion] が [!DNL SQL server] の宛先へ接続を確立するとき、[!DNL Fusion] ユーザーはホスト（サーバーがホストされているドメイン名または IP アドレス）とポートを識別します。[!DNL Fusion] は、使用可能な任意のホストおよびポートに接続できます。

[!DNL Workfront Fusion] で使用される特定の IP アドレスに関する情報について詳しくは、[アクセス用の IP アドレス [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)を参照してください

ストアドプロシージャの作成について詳しくは、[!DNL Microsoft SQL Server] ドキュメントを参照してください。

>[!NOTE]
>
>[!DNL Workfront Fusion] では、複数のレコードセットをサポートしていません。最初の処理のみが処理されます。

## エラー [!UICONTROL ER_LOCK_WAIT_TIMEOUT: Lock wait timeout exceeded; try restarting transaction] のトラブルシューティング

このエラーは、複数のモジュールを使用して同じデータを変更する場合に発生します。SQL トランザクションが原因です。

SQL モジュールが実行されると、トランザクションが開始されます。シナリオが完全に実行された後に、トランザクションが完了します。

別のモジュールが同じデータにアクセスしようとした場合は、前のトランザクションが終了するまで待つ必要があります。シナリオの終了後に最初のトランザクションが完了するので、2 番目のトランザクションは開始できません。

### 解決策：

自動コミットをオンにします。自動コミットは、モジュールの実行が完了した直後にすべてのトランザクションを完了（コミット）します。

1. 画面の下部にある「[!UICONTROL Scenario settings]」アイコン ![](/help/workfront-fusion/references/apps-and-modules/assets/scenario-settings-icon.png) をクリックします。
1. 「**[!UICONTROL Auto commit]**」チェックボックスをクリックします。
1. 「**[!UICONTROL OK]**」をクリックして、シナリオ設定を保存します。
