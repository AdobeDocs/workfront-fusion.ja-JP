---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: ロックされたシナリオの管理
description: Adobe Workfront Fusion でのロックされたシナリオの管理
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 55%

---

# ロックされたシナリオの管理

場合によっては、Workfront Fusion でシナリオが一時的にロックされることがあります。 ロックされたシナリオは、2～4 時間以内に自動的にロックが解除されます。 シナリオのロックは手動で解除できますが、通常はお勧めしません。

シナリオは、次のような様々な理由でロックされる場合があります。

* Workfront Fusion では、スケジュールされたシナリオの並列処理をサポートしていません。これらのシナリオは、シナリオ実行の開始時にロックされ、完了時にロックが解除されます。実行が中断された場合は、シナリオのロックが解除されない可能性があります。これは、ユーザーが手動で強制的にシナリオを停止した場合や、システムの問題が発生した場合に起こる可能性があります。

* Workfront Fusion エンジニアリングチームは、パフォーマンスの問題やその他の問題が発生するために、シナリオをロックする場合があります。

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


## ロックされたシナリオのロックを解除

ロックされたシナリオは、ロックされた時点から 2～4 時間後にロック解除されます。シナリオの自動ロック解除がスケジュールされている時点より前に、手動でロック解除することもできます。

>[!WARNING]
>
>シナリオを手動でロック解除すると、シナリオの実行でエラーが発生する場合があります。シナリオの設計の一環として、シナリオを手動でロック解除するのは、実行の開始と停止が原因でシナリオがロックされる場合に限ることをお勧めします。その他の状況では、シナリオのロックが自動的に解除されるのを待つことをお勧めします。


ロックされているシナリオを手動でロック解除するには：

1. ロックされたシナリオのシナリオの詳細ページに移動します。
1. 画面の右上隅にある「**[!UICONTROL オプション]**」をクリックします。
1. 「**[!UICONTROL 実行のロックを解除]**」を選択します。
1. 「**[!UICONTROL ロックを解除]**」をクリックします。
   ![ シナリオのロックを解除 ](assets/unlock-scenario.png)
