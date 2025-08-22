---
title: Microsoft SQL Server モジュール
description: Adobe Workfront Fusion を使用してMicrosoft SQL Server に接続できます。
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 48%

---

# [!DNL Microsoft SQL Server] モジュール

Adobe Workfront Fusion を使用して [!UICONTROL Microsoft SQL Server] に接続できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Workfront Fusion への [!DNL Microsoft SQL Server] サービスの接続

[!DNL Microsoft SQL Server] アカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

## [!DNL Microsoft SQL Server] モジュールの使用

ストアドプロシージャを使用して、カスタムロジックをデータベースサーバー上で直接実行できます。Adobe Workfront Fusion は、入力/出力パラメーターとレコードセットのインターフェイスを動的に読み込むので、各パラメーターまたは値を個別にマッピングできます。 シナリオの設定を開始する前に、データベースに接続するために使用するアカウントに、`INFORMATION_SCHEMA.ROUTINES` および `INFORMATION_SCHEMA.PARAMETERS` ビューへの読み取りアクセス権があることを確認してください。

[!DNL Fusion] が [!DNL SQL server] の宛先へ接続を確立するとき、[!DNL Fusion] ユーザーはホスト（サーバーがホストされているドメイン名または IP アドレス）とポートを識別します。[!DNL Fusion] は、使用可能な任意のホストおよびポートに接続できます。

Adobe Workfront Fusion で使用される特定の IP アドレスについて詳しくは、「Workfront Fusion にアクセスするための IP アドレス [ を参照してください ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)

ストアドプロシージャの作成について詳しくは、[!DNL Microsoft SQL Server] ドキュメントを参照してください。

>[!NOTE]
>
>Workfront Fusion は、複数のレコードセットをサポートしていません。 最初の処理のみが処理されます。

## エラーのトラブルシューティング [!UICONTROL ER_LOCK_WAIT_TIMEOUT：ロック待機タイムアウトを超えました。トランザクションを再起動してください]

このエラーは、複数のモジュールを使用して同じデータを変更する場合に発生します。SQL トランザクションが原因です。

SQL モジュールが実行されると、トランザクションが開始されます。シナリオが完全に実行された後に、トランザクションが完了します。

別のモジュールが同じデータにアクセスしようとした場合は、前のトランザクションが終了するまで待つ必要があります。シナリオの終了後に最初のトランザクションが完了するので、2 番目のトランザクションは開始できません。

### 解決策：

自動コミットをオンにします。自動コミットは、モジュールの実行が完了した直後にすべてのトランザクションを完了（コミット）します。

1. 画面下部の [!UICONTROL &#x200B; シナリオ設定 &#x200B;] アイコン ![ シナリオ設定アイコン ](/help/workfront-fusion/references/apps-and-modules/assets/scenario-settings-icon.png) をクリックします。
1. **[!UICONTROL 自動コミット]**&#x200B;チェックボックスをクリックします。
1. 「**[!UICONTROL OK]**」をクリックして、シナリオ設定を保存します。
