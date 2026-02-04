---
title: ドキュメントのアクセス要件
description: Adobe Workfront Fusion ドキュメントのハウツー記事には、その手順に必要なアクセス権と権限の要件について説明した表が含まれています。 このアクセス要件の表を使用すると、Fusion で特定のアクションを実行できるかどうか、または実行できない理由を理解できます。 この記事では、アクセス要件表の各要素について説明し、トラブルシューティングのヒントや、より詳細な情報へのリンクを示します。
author: Becky
feature: System Setup and Administration
role: Admin
exl-id: 823aa376-fbfe-4750-82dc-4f34224c1a48
source-git-commit: 05c75c0e125a4f3f657049d7e57bbc94cc5e4d67
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 56%

---

# ドキュメントのアクセス要件

Adobe Workfront Fusion ドキュメントのハウツー記事には、その手順に必要なアクセス権と権限の要件について説明した表が含まれています。 このアクセス要件の表を使用すると、Fusion で特定のアクションを実行できるかどうか、または実行できない理由を理解できます。 この記事では、アクセス要件表の各要素について説明し、トラブルシューティングのヒントや、より詳細な情報へのリンクを示します。

その記事のアクセス要件表に行がない場合、そのアクションに対するそのタイプの要件はありません。

一部の行には、「新規」と「現在」というラベルの付いた情報が含まれています。これは、Workfront が新しい価格設定のパッケージモデルに移行中であり、新規モデルの下で運用している組織もあれば、現行モデルを引き続き使用している組織もあるからです。自分の組織で使用しているモデルを確認するには、Workfront 管理者にお問い合わせください。詳細と情報へのリンクについては、この記事の[アクセス要件表](#the-access-requirements-table)の節を参照してください。

>[!NOTE]
>
>この表のフィールドの適用方法について不明な点がある場合は、Workfront Fusion 管理者にお問い合わせください。

## アクセス要件表

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> Adobe Workfront パッケージとは、組織が購入した一連の機能を指します。 Fusion のほとんどの機能はすべてのプランで使用できますが、一部の例外はUltimate Workfront パッケージを使用する組織でのみ使用できます。 
   <ul><li>組織が使用しているAdobe Workfront パッケージ（新しいパッケージモデルか現在のパッケージモデルかなど）を確認するには、Workfront管理者に問い合わせてください。</li>
   <li>Workfront管理者が組織のWorkfront パッケージを見つける方法については、Workfront ドキュメントの <a href="https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/get-started-administration/firewall-overview#view-your-organization-s-cluster-and-workfront-plan"> 組織のクラスターとWorkfrontのプランの表示 </a> を参照してください。</li><li>新しいWorkfront パッケージについて詳しくは、<a href="https://business.adobe.com/jp/products/workfront/pricing.html">Adobe Workfrontの価格とパッケージ </a> を参照してください。</li></ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> Adobe Workfront ライセンスとは、割り当てられたライセンスに含まれている Workfront 機能のセットを指します。例えば、作業アイテムを完了とマークする機能と時間を記録する機能を含むライセンスを持っているユーザーもいれば、アセットの承認またはリクエストの送信のみが可能なライセンスを持っているユーザーもいます。 <p> 
   <ul>
   <li>割り当てられているライセンスを確認するには、Workfront 管理者にお問い合わせください。</li>
   <li>Adobe Workfront は、新しい価格設定のパッケージモデルに移行しつつあります。ライセンスについては、以下を参照してください。
   <ul>
   <li>新規：<a href="https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/add-users/access-levels/licenses-overview">新しいライセンスの概要</a></li>
   <li>現在：<a href="https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/add-users/legacy-access-levels/wf-licenses">ライセンスの概要</a></li></ul></li>
   <li>正しいアクセスレベルがあるにも関わらずアクセスできない場合は、アクセスレベルにその他の制限が設定されていないか Workfront 管理者にお問い合わせください。Workfront 管理者がアクセスレベルを変更する方法について詳しくは、<a href="https://experienceleague.adobe.com/ja/docs/workfront/using/administration-and-setup/get-started-administration/firewall-overview#view-your-organization-s-cluster-and-workfront-plan" class="MCXref xref">カスタムアクセスレベルの作成または変更</a>を参照してください。
   </ul>
      </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>場合によっては、Workfrontに加えて Fusion を購入する必要があります。 組織がUltimate Workfront パッケージを持っている場合、Fusion は含まれています。
  <tr> 
   <td role="rowheader">アクセスレベル</td> 
   <td> アクセスレベルとは、Fusion で実行できるアクションの権限のセットです。 例えば、一部のアクションは Fusion 管理者のみが実行できます。 
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
