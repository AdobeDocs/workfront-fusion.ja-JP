---
title: ワーカープール
description: ワーカープールとは、1つ以上の特定の組織専用のWorkfront Fusion処理リソースの量です。 Fusionの操作と処理はすべて、組織に割り当てられたワーカープールのコンテキスト内で行われます。
author: Becky
feature: Workfront Fusion
exl-id: 8bf508a8-d1f9-455f-af89-62f688289137
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: b800142d824927e5765eed50a831731e6b5d9925
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 19%
---
# ワーカープール

ワーカープールとは、特定の組織専用のWorkfront Fusion処理リソースの量です。 Fusionの操作と処理はすべて、組織に割り当てられたワーカープールのコンテキスト内で行われます。

ワーカープールを使用すると、シナリオをより効率的に実行でき、Fusion処理能力を他の組織と競合する可能性がなくなります。

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## ワーカープールの概要

ワーカープールは、シナリオ実行を並行して処理する方法です。 各ワーカープールは次の場所に関連付けられます。

* 多くの労働者。
* 実行キュー。

シナリオが実行されると、ワーカープールの実行キューに渡されます。 プール内のワーカーは、実行プールからタスクを継続的に取得し、並行して処理します。

実行キューの深さが増し、すべての既存のワーカーが使用されている場合、Workfront Fusionは、ワーカーを追加することでプールを自動的にスケーリングします。 この拡張は動的でイベント駆動型です。つまり、キャパシティは、自社や組織がアクションを起こさずに、リアルタイムの負荷に基づいて正確または契約します。

Workfront Fusion チームは、プールの使用状況とスケーリングの動作を継続的にモニタリングし、しきい値やパターンを確認して、使用状況の増加に合わせてパフォーマンスの一貫性を確保できます。

## ワーカープールの名前の変更

組織の所有者と管理者は、組織に割り当てられたワーカープールの名前を変更できます。 各プールには、デフォルトでシステム生成の名前が表示されます。 プールに`Marketing EU`や`High-volume integrations`などのカスタム名を付け、必要なときにいつでも変更できます。

プールの名前を変更すると、そのプールのラベル付け方法のみが変更されます。 シナリオ、実行、およびプール容量は影響を受けません。 新しい名前は、プールにシナリオを割り当てる場合など、プールが表示される場所に表示されます。

>[!NOTE]
>
>「**[!UICONTROL ワーカープール]**」タブは、複数のワーカープールが組織に割り当てられている場合にのみ表示されます。 組織に単一のワーカープールがある場合、または共有プールを使用している場合は、「」タブは表示されません。

ワーカープールの名前を変更するには：

1. 左側のナビゲーションで、**組織の概要**&#x200B;をクリックします
1. ページの上部にある「**[!UICONTROL ワーカープール]**」タブをクリックします。

   このタブには各プールが一覧表示され、割り当てられているシナリオの数が表示されます。

1. 名前を変更するプールの横にある&#x200B;**[!UICONTROL 名前変更]**&#x200B;をクリックします。
1. 開いたパネルで、新しい名前を入力します。
1. 「**保存**」をクリックします。
