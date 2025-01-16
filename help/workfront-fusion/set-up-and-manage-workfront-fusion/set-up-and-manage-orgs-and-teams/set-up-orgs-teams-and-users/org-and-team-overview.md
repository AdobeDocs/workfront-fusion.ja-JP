---
title: Fusion 組織とチームの概要
description: Adobe Workfront Fusion の組織とチームの機能を使用すると、企業は Fusion 内のシナリオや他の機能へのアクセスを制御できます。
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 45%

---

# [!DNL Adobe Workfront Fusion] 組織とチームの概要

[!DNL Adobe Workfront Fusion] の組織とチーム機能を使用すると、企業は Fusion 内のシナリオや他の機能へのアクセスを制御できます。

組織は、Adobe Workfront Fusion の最大のエンティティです。 例えば、Fusion 組織は、会社全体の Fusion アカウントを表す場合があります。

チームは組織内の小さなグループで、シナリオ、接続、テンプレートなどの Fusion リソースを共有します。

## 組織

[!DNL Workfront Fusion] ユーザーは組織に属しています。

ユーザーは、チームに追加される前に、組織に追加される必要があります。

### 組織の役割

ユーザーには、組織内で次のいずれかの役割があります。

* **[!UICONTROL Owner]**：所有者は、組織で使用可能なすべての権限を持っています。
* **[!UICONTROL Admin]**：管理者は、組織のチームとユーザーを作成および管理したり、テンプレートを承認したりできます。
* **[!UICONTROL Member]**: メンバーは [!DNL Workfront Fusion] を使用できますが、組織を変更することはできません。
* **[!UICONTROL Accountant]**：会計士は、組織ダッシュボードでライセンス情報を表示できますが、アクションは実行できません。
* **[!UICONTROL App Developer]**：この役割の機能は現在利用できません。近い将来に利用できるようになります。 現時点では、この役割にユーザーを割り当てることはお勧めしません。

各組織の役割でユーザーが使用できる特定のアクションについて詳しくは、[組織とチームの役割](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)を参照してください。

## チーム

チームとは、特定のリソースへのアクセスを共有するユーザーのグループです。これらのリソースには以下が含まれます。

* シナリオ
* 接続
* Web フック
* キー
* データストア
* データ構造
* メール通知設定

>[!NOTE]
>
>チームはリソースを共有するので、チームのメンバーを 1 人だけにすると便利な場合があります。 例えば、トレーニングのユーザーは、個人の [!DNL Workfront] アカウントへの接続を作成できます。チームメンバーは個々の [!DNL Workfront] アカウントに接続することもできます。 この場合、ユーザーをトレーニングチームの唯一のメンバーすることをお勧めします。

組織には必要な数のチームが含まれ、ユーザーは 1 つ以上のチームに属する場合があります。

ユーザーは、左側のナビゲーションパネルにあるドロップダウンリストからチームを選択できます。ユーザー自身が属するチームのみが表示されます。チームを選択すると、ユーザーはそのチームのリソースにアクセスできます。

### チームの役割

ユーザーは、各チームで次の役割のいずれかを持ちます。

* **[!UICONTROL Team Admin]**：管理者は、チームメンバーの役割を追加、削除、変更できます。 また、他のチームの役割が実行できるアクションを実行することもできます。
* **[!UICONTROL Team Member]**: チームメンバーの役割を使用すると、ユーザーはシナリオを作成および実行できます。
* **[!UICONTROL Team Monitoring]**: [!UICONTROL monitoring] の役割を持つユーザーはシナリオの実行情報にアクセスできますが、シナリオをデザインしたり、「アクティブ」ステータスを変更したりすることはできません。
* **[!UICONTROL Team Operator]**:[!UICONTROL operator] の役割を持つユーザーは、実行データを表示し、シナリオの「アクティブ」ステータスを変更できます。
* **[!UICONTROL Team Restricted Member]**：この役割の機能は現在利用できません。近い将来に利用できるようになります。 現時点では、この役割にユーザーを割り当てることはお勧めしません。

各チームの役割でユーザーが使用できる特定のアクションについて詳しくは、[組織とチームの役割](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)を参照してください。
