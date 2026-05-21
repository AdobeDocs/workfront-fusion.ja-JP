---
title: ドキュメントのアクセス要件
description: Adobe Workfront Fusionのドキュメントのハウツー記事には、その手順に必要なアクセスと権限の要件を説明する表が含まれています。 このアクセス要件テーブルでは、Fusionで特定のアクションを実行できるかどうか、または実行できない理由を理解できます。 この記事では、アクセス要件表の各要素について説明し、トラブルシューティングのヒントや、より詳細な情報へのリンクを示します。
author: Becky
feature: System Setup and Administration
role: Admin
exl-id: 823aa376-fbfe-4750-82dc-4f34224c1a48
TQID: https://experienceleague.adobe.com/DtdOS-HFHhcq5lm8LTtc9gdVGgDwtg9tfh9shZPwNDs
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: d968a1bc-9a90-4926-a531-bcf272c32aad
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 694
ht-degree: 48%

---

# ドキュメントのアクセス要件

Adobe Workfront Fusionのドキュメントのハウツー記事には、その手順に必要なアクセスと権限の要件を説明する表が含まれています。 このアクセス要件テーブルでは、Fusionで特定のアクションを実行できるかどうか、または実行できない理由を理解できます。 この記事では、アクセス要件表の各要素について説明し、トラブルシューティングのヒントや、より詳細な情報へのリンクを示します。

その記事のアクセス要件表に行がない場合、そのアクションに対するそのタイプの要件はありません。

一部の行には、「新規」と「現在」というラベルの付いた情報が含まれています。 これは、Workfront が新しい価格設定のパッケージモデルに移行中であり、新規モデルの下で運用している組織もあれば、現行モデルを引き続き使用している組織もあるからです。 自分の組織で使用しているモデルを確認するには、Workfront 管理者にお問い合わせください。 詳細と情報へのリンクについては、この記事の[アクセス要件表](#the-access-requirements-table)の節を参照してください。

>[!NOTE]
>
>この表のいずれかのフィールドの適用方法について質問がある場合は、Workfront Fusion管理者にお問い合わせください。

## アクセス要件表

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> Adobe Workfrontのパッケージとは、組織が購入した機能セットを指します。 Fusion機能のほとんどは、すべてのプランで利用できますが、Ultimate Workfront パッケージを持つ組織のみが利用できる例外もあります。 
   <ul><li>お客様の組織が使用しているAdobe Workfront パッケージ（新しいパッケージモデルまたは現在のパッケージモデルのいずれの場合も含む）については、Workfront管理者にお問い合わせください。</li>
   <li>Workfront管理者が組織のWorkfront パッケージを見つける方法について詳しくは、「ファイアウォールの概要」の「<a href="https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/get-started-administration/firewall-overview#view-your-organization-s-cluster-and-workfront-package">組織のクラスターとWorkfront プランを表示</a>」を参照してください。</li><li>新しいWorkfront パッケージについて詳しくは、<a href="https://business.adobe.com/products/workfront/pricing.html">Adobe Workfrontの価格とパッケージ </a>を参照してください。</li></ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> Adobe Workfront ライセンスとは、割り当てられたライセンスに含まれている Workfront 機能のセットを指します。 例えば、作業アイテムを完了とマークする機能と時間を記録する機能を含むライセンスを持っているユーザーもいれば、アセットの承認またはリクエストの送信のみが可能なライセンスを持っているユーザーもいます。 <p> 
   <ul>
   <li>割り当てられているライセンスを確認するには、Workfront 管理者にお問い合わせください。</li>
   <li>Adobe Workfront は、新しい価格設定のパッケージモデルに移行しつつあります。 ライセンスについては、以下を参照してください。
   <ul>
   <li>新規：<a href="https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/access-levels/licenses-overview">新しいライセンスの概要</a></li>
   <li>現在：<a href="https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/legacy-access-levels/wf-licenses">ライセンスの概要</a></li></ul></li>
   <li>正しいアクセスレベルがあるにも関わらずアクセスできない場合は、アクセスレベルにその他の制限が設定されていないか Workfront 管理者にお問い合わせください。 Workfront管理者がアクセス レベルを変更する方法について詳しくは、<a href="https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/configure-access/create-modify-access-levels" class="MCXref xref"> カスタム アクセス レベルの作成と変更</a>を参照してください。
   </ul>
      </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>場合によっては、Workfrontに加えてFusionを購入する必要があります。 組織にUltimate Workfront パッケージがある場合は、Fusionが含まれています。
  <tr> 
   <td role="rowheader">アクセスレベル</td> 
   <td> アクセスレベルは、Fusionで実行できるアクションに対する一連の権限です。 例えば、一部のアクションは、Fusion管理者のみが実行できます。 
   </tr>
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>Adobe Workfront Fusion には、Workfront とは別のライセンスモデルがあります。 
   <ul><li>現在：現在のライセンスモデルは、実行された操作の数に基づいており、組織が実行できるアクションに制限はありません。 </li>
   <li>レガシ：従来のライセンスは、シナリオがサードパーティのアプリケーションに接続できるかどうか、またはシナリオが Workfront 自動処理にのみ使用されるかどうかに基づきます。 </li>
   </ul>
   Fusion ライセンスについて詳しくは、<a href="/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md" class="MCXref xref">Workfront Fusion ライセンス</a>を参照してください。
   </td> 
  </tr> 
 </tbody> 
</table>
