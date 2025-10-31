---
title: コネクタのない web サービスに Webhook を設定
description: 現在Workfront Fusion に専用のコネクタがなく、Webhook の送信がサポートされている web サービスの場合は、カスタム Webhook モジュールをインスタントトリガーとして使用して、サービスをシナリオに追加できます。
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 12%

---

# コネクタのない web サービスに Webhook を設定

現在Workfront Fusion に専用のコネクタがなく、Webhook の送信がサポートされている web サービスの場合は、カスタム Webhook モジュールをインスタントトリガーとして使用して、サービスをシナリオに追加できます。 このプロセスは Webhook を受け取ると呼ばれ、接続先のアプリケーション側で設定が必要です。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++

## Web フックを受信

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. Webhook を追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. **Webhook/カスタム Webhook** モジュールを追加し、シナリオを開始します。
1. Webhook フィールドの横にある「**追加**」をクリックします。
1. 表示されるボックスに **Webhook 名** を入力します
1. （オプション） Webhook を設定します。

   手順については、[Webhook](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md) を参照してください。

1. 「**保存**」をクリックします。

1. **アドレスをクリップボードにコピー**、次に「**OK**」をクリックします。

1. Web サービスにログインし、以下の操作を行います。

   1. Web サービスの設定領域で、Webhook を作成します。

      具体的な手順は、アプリケーションによって異なります。 アプリケーションのドキュメントで「Webhook の作成」を検索することをお勧めします。
   1. 手順 3 でコピーしたアドレスをクリップボードに貼り付けます。
   1. Web フックをトリガーするイベントを選択します。

1. シナリオを実行します。

   イベントが発生すると、カスタム Webhook モジュールがトリガーし、シナリオが実行されます。
