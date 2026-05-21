---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: ロックされたシナリオの管理
description: Adobe Workfront Fusionでロックされたシナリオを管理する
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
TQID: https://experienceleague.adobe.com/1eVGWr4SwutYzNmCKB62CCWbQ6ExdXtpjC5BORh-kxo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 77%

---

# ロックされたシナリオの管理

場合によっては、Workfront Fusionで一時的にシナリオがロックされることがあります。 ロックされたシナリオは、2～4時間以内に自動的にロック解除されます。 シナリオのロックを手動で解除できますが、一般的にはお勧めしません。

シナリオは、次のような理由でロックされる可能性があります。

* Workfront Fusion では、スケジュールされたシナリオの並列処理をサポートしていません。 これらのシナリオは、シナリオ実行の開始時にロックされ、完了時にロックが解除されます。 実行が中断された場合は、シナリオのロックが解除されない可能性があります。 これは、ユーザーが手動で強制的にシナリオを停止した場合や、システムの問題が発生した場合に起こる可能性があります。

* Workfront Fusion エンジニアリングチームは、パフォーマンスやその他の問題を引き起こしているシナリオをロックする場合があります。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## ロックされたシナリオのロックを解除

ロックされたシナリオは、ロックされた時点から 2～4 時間後にロック解除されます。 シナリオの自動ロック解除がスケジュールされている時点より前に、手動でロック解除することもできます。

>[!WARNING]
>
>シナリオを手動でロック解除すると、シナリオの実行でエラーが発生する場合があります。 シナリオの設計の一環として、シナリオを手動でロック解除するのは、実行の開始と停止が原因でシナリオがロックされる場合に限ることをお勧めします。 その他の状況では、シナリオのロックが自動的に解除されるのを待つことをお勧めします。


ロックされたシナリオのロックを手動で解除するには：

1. ロックされたシナリオのシナリオの詳細ページに移動します。
1. 画面の右上隅にある「**[!UICONTROL オプション]**」をクリックします。
1. 「**[!UICONTROL 実行のロックを解除]**」を選択します。
1. 「**[!UICONTROL ロックを解除]**」をクリックします。
   ![&#x200B; シナリオのロック解除](assets/unlock-scenario.png)
