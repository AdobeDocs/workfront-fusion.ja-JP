---
title: Workfront Fusion でのナビゲート
description: Fusion を開くと、アクションに関する多くのオプションが表示されます。この記事は、ここから移動する場所を理解するのに役立ちます。
author: Becky
feature: Workfront Fusion
exl-id: 427ec131-d68d-4401-b620-998d3d5162da
source-git-commit: 3c726c1df589785719c0f141fbd5bc17194cc218
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 94%

---

# Adobe Workfront Fusion でのナビゲート

左側のナビゲーションパネルを使用して、Adobe Workfront Fusion の様々な領域を移動できます。ここでは、Fusion の主な領域をすべて見つけて、ある領域から別の領域にすばやく移動できます。

この記事では、これらの領域を紹介し、各領域の詳細情報へのリンクを提供します。

| 領域 | 説明 | 詳しくは、次を参照してください。 |
| --- | --- | --- |
| 組織の概要<br> ![組織アイコン](assets/org-icon.png) | ここでは、Fusion 組織に関する情報を確認できます。この組織のシナリオで実行された操作の数と、アクティブなシナリオのリストを表示できます。また、この組織のチーム、ユーザー、環境のリストを表示することもできます。<br>現在選択されている組織は、このアイコンの上に表示されます。 | [組織とチーム](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md) |
| チームの概要<br> ![チームアイコン](assets/team-icon.png) | ここでは、このチームのシナリオで実行された操作の数やアクティブなシナリオのリストなど、Fusion チームに関する情報を確認できます。また、このチームのユーザーを表示および管理することもできます。チームを表示する際に、このページの上部にあるドロップダウンから別のチームを選択できます。<br>現在選択されているチームは、このアイコンの上に表示されます。<br>チームの概要またはこの記事にリストされているチームセクションを表示するには、チームを作成する必要がある場合があります。 | [組織とチーム](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md) |
| シナリオ<br> ![シナリオアイコン](assets/scenarios-icon.png) | Fusion のシナリオは、自動ワークフローを表します。例えば、あるシナリオでは、受信する Workfront リクエストを監視してプロジェクトに変換し、別のシナリオでは、画像を生成してドキュメントプロバイダーにアップロードし、Workfront に承認タスクを追加するといった処理を行います。Fusion での作業のほとんどは、シナリオの設定と管理です。シナリオ領域では、チームのシナリオのリストを表示および整理したり、表示または変更する個々のシナリオを選択したり、新しいシナリオの作成を開始したりできます。 | [シナリオの概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md) |
| テンプレート<br> ![テンプレートアイコン](assets/templates-icon.png) | テンプレートは、独自のユースケース用に設定できる事前構築済みシナリオです。ここでは、Workfront Fusion が提供するパブリックシナリオと、チームが作成したテンプレートを確認できます。 | [テンプレートの作成と管理：記事インデックス](/help/workfront-fusion/create-and-manage-templates/create-manage-templates-toc.md) |
| 接続<br> ![接続アイコン](assets/connections-icon.png) | 接続には、Fusion が他のアプリケーションとやり取りするログイン資格情報と権限が含まれます。特定のアプリケーション用の特定の資格情報セットと権限セットを持つ接続を作成してから、その接続をシナリオで使用します。その後、シナリオは、これらの資格情報と権限を持つユーザーが使用できるレコードやその他のデータにアクセスして変更できます。1 つのアプリケーションに対して複数の接続を作成し、複数のシナリオで接続を使用できます。接続領域では、チームによって設定された接続のリストを表示および管理できます。 | [接続の概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md) |
| Webhook<br> ![Webhook アイコン](assets/webhooks-icon.png) | Webhook は、アプリケーションの変更を監視し、その変更に基づいてシナリオを開始します。例えば、特定の Workfront プロジェクトに問題が送信された際にシナリオを開始するように Webhook を設定できます。Webhook 領域には、チームで設定された Webhook のリストと、それらが使用されているシナリオが表示されます。 | [インスタントトリガー（Webhook）](/help/workfront-fusion/references/modules/webhooks-reference.md) |
| キー<br> ![キーアイコン](assets/keys-icon.png) | 公開鍵と秘密鍵は、データの暗号化と復号化に使用されます。公開鍵は配布でき、公開鍵を持つすべてのユーザーがデータを暗号化できますが、復号化できるのは秘密鍵のみです。同様に、同様に、秘密鍵を持つユーザーは、公開鍵を持つ誰もが復号化できるデータを暗号化できます。キー領域では、チームが所有するキーを表示および管理できます。 | [キー](/help/workfront-fusion/references/modules/keys.md) |
| データストア<br> ![データストアアイコン](assets/data-store-icon.png) | データストアは、シナリオの外部に存在する小さなデータベースです。データストアを使用すると、シナリオ間またはシナリオの別々の実行間でデータを転送できます。データストア領域では、チームが所有するデータストアを表示および管理できます。 | [データストア](/help/workfront-fusion/create-scenarios/map-data/data-stores.md) |
| データ構造<br> ![データ構造アイコン](assets/data-structure-icon.png) | データ構造は、Fusion に転送されるデータの形式を記述し、JSON、XML、CSV などの形式をシリアル化したり解析したりするのに一般的に使用されます。データ構造では、チームが所有するデータ構造を表示および管理できます。 | [データ構造](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md) |
| 関数 <br> ![ 関数アイコン ](assets/functions-icon.png) | カスタム関数は、データを操作および変換するシナリオに追加できるJavaScript関数です。 <br> カスタム関数を作成して使用するには、Adobe App Builderのライセンスが必要です。 | [ カスタム関数を使用したデータのマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md) |

>[!NOTE]
>
>「チーム」ヘッダーの下のすべての領域は、個々のチームが所有します。別のチームに属するページ（別のチームのシナリオページなど）を表示するには、ページの上部にある「チーム」ドロップダウンをクリックして、別のチームを選択します。

