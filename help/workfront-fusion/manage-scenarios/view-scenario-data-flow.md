---
title: シナリオでのデータフローの表示
description: 実行中のシナリオを見て、データのフローを確認できます。
author: Becky
feature: Workfront Fusion
exl-id: 24eeb1d3-b5a7-4486-8d0b-0a43eb154e8e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 13%

---

# 実行中のシナリオでのデータフローの表示

実行中のシナリオを見て、データのフローを確認できます。

シナリオが実行されている間、アクティブなモジュールは、モジュールの周りにリングが成長してマークされます。 リングは、モジュールが実行中であることを示すだけで、進行状況は示しません。 すばやく実行されるモジュールには、リングの一部しか表示されない場合があります。

![Ring around module](assets/ring-around-module.png)

モジュールが実行されると、出力インジケーターが表示されます。

![ 出力インジケーター ](assets/data-flow-output.png)

モジュールが複数のバンドルを処理する場合、処理されたバンドルごとにリングが表示され、出力インジケータは出力されたバンドルごとにカウントされます。

シナリオデータフローについて詳しくは、[ シナリオ実行フロー ](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md) を参照してください。

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
   <td> <p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 実行中のシナリオでのデータフローの表示

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. データフローを表示するシナリオを選択します。
1. シナリオが実行されていない場合は、アクティブにするか、「**1 回実行**」をクリックしてシナリオの実行を開始します。
1. 実行履歴パネルの「現在実行中」セクションで、表示する実行を選択します。

![ 現在実行中 ](assets/currently-running.png)
