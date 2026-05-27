---
title: Microsoft SQL Server モジュール
description: Adobe Workfront Fusionを使用して、Microsoft SQL Serverに接続できます。
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
TQID: https://experienceleague.adobe.com/etKUNkjJF0UreB6qI-ckU0tOF96RY6Yey1ADVcpOWfo
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 531
ht-degree: 66%

---

# [!DNL Microsoft SQL Server] モジュール

Adobe Workfront Fusionを使用して[!UICONTROL Microsoft SQL Server]に接続できます。

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
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
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

## Workfront Fusionへの[!DNL Microsoft SQL Server] サービスの接続

[!DNL Microsoft SQL Server] アカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリでは、同じ接続を使用し、個々のユーザー権限に関連付けられています。 したがって、接続を作成する際に、権限の同意画面には、現在のアプリケーションに必要な新しい権限に加えて、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーがExcel コネクタを介して付与された「テーブルの読み取り」権限を持ち、Outlook コネクタで電子メールを読み取るための接続を作成した場合、権限の同意画面には、既に付与された「テーブルの読み取り」権限と新たに必要な「電子メールの書き込み」権限の両方が表示されます。

## [!DNL Microsoft SQL Server] モジュールの使用

ストアドプロシージャを使用して、カスタムロジックをデータベースサーバー上で直接実行できます。 Adobe Workfront Fusionでは、入力/出力パラメーターとレコードセットのインターフェイスが動的に読み込まれるため、各パラメーターや値を個別にマッピングできます。 シナリオの設定を開始する前に、データベースに接続するために使用するアカウントに、`INFORMATION_SCHEMA.ROUTINES` および `INFORMATION_SCHEMA.PARAMETERS` ビューへの読み取りアクセス権があることを確認してください。

[!DNL Fusion] が [!DNL SQL server] の宛先へ接続を確立するとき、[!DNL Fusion] ユーザーはホスト（サーバーがホストされているドメイン名または IP アドレス）とポートを識別します。 [!DNL Fusion] は、使用可能な任意のホストおよびポートに接続できます。

Workfront Fusionで使用される特定のIP アドレスについて詳しくは、[Adobe Workfront Fusionへのアクセス用のIP アドレス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)を参照してください

ストアドプロシージャの作成について詳しくは、[!DNL Microsoft SQL Server] ドキュメントを参照してください。

>[!NOTE]
>
>Workfront Fusionでは、複数のレコードセットはサポートされていません。 最初の処理のみが処理されます。

## エラーのトラブルシューティング [!UICONTROL ER_LOCK_WAIT_TIMEOUT：ロック待機タイムアウトを超えました。トランザクションを再起動してください]

このエラーは、複数のモジュールを使用して同じデータを変更する場合に発生します。 SQL トランザクションが原因です。

SQL モジュールが実行されると、トランザクションが開始されます。 シナリオが完全に実行された後に、トランザクションが完了します。

別のモジュールが同じデータにアクセスしようとした場合は、前のトランザクションが終了するまで待つ必要があります。 シナリオの終了後に最初のトランザクションが完了するので、2 番目のトランザクションは開始できません。

### 解決策：

自動コミットをオンにします。 自動コミットは、モジュールの実行が完了した直後にすべてのトランザクションを完了（コミット）します。

1. 画面下部の[!UICONTROL  シナリオ設定] アイコン ![ シナリオ設定アイコン ](/help/workfront-fusion/references/apps-and-modules/assets/scenario-settings-icon.png)をクリックします。
1. **[!UICONTROL 自動コミット]**&#x200B;チェックボックスをクリックします。
1. 「**[!UICONTROL OK]**」をクリックして、シナリオ設定を保存します。
