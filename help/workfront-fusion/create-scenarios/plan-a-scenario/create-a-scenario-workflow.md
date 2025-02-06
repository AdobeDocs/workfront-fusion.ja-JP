---
title: シナリオ作成のワークフロー
description: この一般的なワークフローに従って、シナリオを作成します
author: Becky
feature: Workfront Fusion
exl-id: 49f8edd7-e29a-4ead-9134-a9f0d1cc244d
source-git-commit: c34adf455ce01da52c321d3f997a58f8251d97bf
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 19%

---

# シナリオ作成のワークフロー

シナリオは、組織のニーズに合わせて構築され、ユースケースに対応するアプリケーションとモジュールが用意されています。 ただし、シナリオの作成は、ユースケースに関係なく、同じ基本ワークフローに従います。 この記事では、シナリオを作成する基本的なプロセスについて説明します。


* [シナリオの作成と命名](#create-and-name-the-scenario)
* [最初のモジュールを追加して設定](#configure-the-first-module)
* [接続の作成](#create-connections)
* [追加モジュールの追加と設定](#add-and-configure-additional-modules)
* [モジュール間のデータのマッピング](#map-data-between-modules)
* [ルーティングの設定](#configure-routing)
* [エラー処理の設定](#configure-error-handling)
* [シナリオ設定を指定](#onfigure-scenario-settings)
* [テストと改訂](#test-and-revise)
* [シナリオをアクティベート](#activate-the-scenario)

キーボードショートカット



## シナリオの作成と命名

1. [!DNL Workfront Fusion] アカウントにログインします。
1. 左側 **[!UICONTROL Scenarios]** パネルで ![ シナリオアイコン ](assets/scenarios-icon.png) をクリックします。

   >[!NOTE]
   >
   >左側のナビゲーションパネルまたはアイコンが表示されない場合は、メニュー ![メニュー](assets/main-menu-icon-left-nav.png) アイコンをクリックします。

1. （オプション） [!UICONTROL **フォルダー**] パネルで、「**[!UICONTROL Add folder]**」アイコン ![ フォルダーアイコンを追加 ](assets/add-folder-icon.png) をクリックし、最初のフォルダーの「練習シナリオ」のような名前を入力します。

1. （オプション）フォルダーを開き、ページの右上隅にある「**[!UICONTROL Create a new scenario]**」をクリックします。

1. 左上隅の **[!UICONTROL New scenario]** プレースホルダー名を選択し、「練習シナリオ 1」などの名前を入力します。

   ![ シナリオに名前を付ける ](assets/name-the-scenario.png)

1. 以下の [ 最初のモジュールを接続 ](#2-connect-the-first-module) に進みます。

## 最初のモジュールを追加して設定

シナリオの最初のモジュールはトリガーモジュールで、特定の条件が満たされるとシナリオを開始します。

シナリオに最初のモジュールを追加する方法については、「シナリオにモジュールを追加する」の [ 最初のモジュールをシナリオに追加する ](/help/workfront-fusion/create-scenarios/add-modules/add-a-module-basic.md#add-the-first-module-to-a-scenario) を参照してください。

モジュールの設定手順については、[ モジュールの設定 ](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md) を参照してください

## 接続の作成

モジュールを設定する場合、接続を入力または作成する必要があります。 モジュールは、この接続と、その接続に含まれる権限を使用して、アプリケーション内の日付にアクセスします。

接続の作成方法に関する基本的な手順については、[ 接続の作成 – 基本的な手順 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) を参照してください。

Google、Microsoft、または専用コネクタのないアプリケーションに関する特定のユースケースについては、[ アプリケーションへの接続：記事インデックス ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-apps-toc.md) の他の記事を参照してください。

## 追加モジュールの追加と設定

追加モジュールの追加と設定を続けます。

モジュールを追加する方法については、「[ モジュールを追加：記事インデックス ](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md)」にリストされている記事を参照してください。

## モジュール間のデータのマッピング

以前のモジュールからの出力を、後続のモジュールへの入力として使用できます。 例えば、あるモジュールでWorkfront プロジェクトを作成し、後続のモジュールでそのモジュールにドキュメントをアップロードできます。

手順については、[ マップ データ：記事インデックス ](/help/workfront-fusion/create-scenarios/map-data/map-data-toc.md) の記事を参照してください。

## ルーティングの設定

ルーティングを使用すると、シナリオでデータ値に基づいて様々なアクションを実行できます。

手順については、[ ルーターモジュールの追加とルートの設定 ](/help/workfront-fusion/create-scenarios/add-modules/router-module.md) を参照してください。

## エラー処理の設定

エラー処理を使用すると、シナリオをエラーから回復できます。 様々なエラー状況でのシナリオの反応方法を選択できます。

手順については、「[ エラー処理の追加 ](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) を参照してください。

## シナリオ設定を指定

シナリオのスケジュール設定、メモの作成、データの保存方法の決定など、シナリオ全体の設定を指定できます。

手順については、[ シナリオ設定の指定：記事インデックス ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/config-scenario-settings-toc.md) の記事を参照してください。

## テストと改訂

シナリオをテストすると、シナリオが意図したとおりに動作しているかどうかを判断できます。 その後、結果に基づいてシナリオを修正し、再テストできます。

1. シナリオエディターの左下にある「**[!UICONTROL Run once]**」をクリックします。
1. シナリオの実行が完了したら、各モジュールの上にある実行インスペクターのバブルをクリックして、情報の入力とそのモジュールの出力を確認します。

   * シナリオ実行情報の読み取りに関する一般的な情報については、[ シナリオ実行フロー ](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md) を参照してください。
   * 処理されたバンドルについて詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md) でのシナリオの実行、サイクル、フェーズを参照してください。

1. [!DNL Workfront Fusion] では、左下隅付近 **[!UICONTROL Save]** ある ![ 保存アイコン ](assets/save-icon.png) をクリックして、シナリオの進捗を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。

## シナリオをアクティベート

この例のシナリオにはトリガーモジュールがありません。これが実際のデータに使用するシナリオの場合は、トリガーモジュールから始まり、最後にアクティブ化します。シナリオをアクティベートすると、デフォルトでは 15 分ごとに実行されます。これは、実行するタイミングと頻度を定義することで変更できます。

シナリオのアクティブ化の詳細については、[ シナリオのアクティブ化または非アクティブ化 ](/help/workfront-fusion/manage-scenarios/activate-deactivate-scenarios.md) を参照してください。

スケジュールについては、[ シナリオのスケジュール ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。

## Workfront Fusion のシナリオのキーボードショートカット

シナリオの作成または編集時に、以下のキーボードショートカットを使用できます。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <thead> 
  <tr> 
   <th> <p>アクション</p> </th> 
   <th>[!DNL Windows]</th> 
   <th> <p>[!DNL MacOS]</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save] </td> 
   <td>Ctrl + Shift + S</td> 
   <td>Cmd + Shift + S</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Run Once]</td> 
   <td>Ctrl + Shift + Enter</td> 
   <td>Cmd + Shift + Enter </span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Open the DevTool]</td> 
   <td>F12</td> 
   <td>Ctrl + Fn + F12</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select multiple modules]</td> 
   <td>Shift + ドラッグ</td> 
   <td>Shift キーを押しながらドラッグ </span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy]</td> 
   <td>Ctrl+C</td> 
   <td>Cmd+C</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Paste]</td> 
   <td>Ctrl+V</td> 
   <td>Cmd+V</span> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">cURL をシナリオに貼り付けて、HTTP モジュールを作成します</td> 
   <td colspan="2">cURL をコピーし、シナリオエディターの任意の場所に貼り付けます。<p>詳しくは、<a href="/help/workfront-fusion/create-scenarios/add-modules/use-curl-create-http.md">cURL を使用した HTTP モジュールの追加 </a> を参照してください。</td> 
  </tr> 
 </tbody> 
</table>





