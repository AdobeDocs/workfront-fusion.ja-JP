---
title: コネクタのない web サービスに Webhook を設定
description: 現在Workfront Fusion に専用のコネクタがなく、Webhook の送信がサポートされている web サービスの場合は、カスタム Webhook モジュールをインスタントトリガーとして使用して、サービスをシナリオに追加できます。
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 17%

---

# コネクタのない web サービスに Webhook を設定

現在Workfront Fusion に専用のコネクタがなく、Webhook の送信がサポートされている web サービスの場合は、カスタム Webhook モジュールをインスタントトリガーとして使用して、サービスをシナリオに追加できます。 このプロセスは Webhook を受け取ると呼ばれ、接続先のアプリケーション側で設定が必要です。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront プランを選択する：組織がAdobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

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

1. **保存**&#x200B;をクリックします。

1. **アドレスをクリップボードにコピー**、次に「**OK**」をクリックします。

1. Web サービスにログインし、以下の操作を行います。

   1. Web サービスの設定領域で、Webhook を作成します。

      具体的な手順は、アプリケーションによって異なります。 アプリケーションのドキュメントで「Webhook の作成」を検索することをお勧めします。
   1. 手順 3 でコピーしたアドレスをクリップボードに貼り付けます。
   1. Web フックをトリガーするイベントを選択します。

1. シナリオを実行します。

   イベントが発生すると、カスタム Webhook モジュールがトリガーし、シナリオが実行されます。
