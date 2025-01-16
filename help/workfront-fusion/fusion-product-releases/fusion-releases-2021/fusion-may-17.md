---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion リリースアクティビティ：2021年5月17日（PT）の週
description: このページでは、2021年5月17日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 2ea57c69-8db7-4500-9157-e2c2d8c74938
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 100%

---

# Workfront Fusion リリースアクティビティ：2021年5月17日（PT）の週

このページでは、2021年5月17日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。

最近のすべての変更内容のリストについては、[Adobe Workfront Fusion リリースアクティビティ](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)を参照してください。

Workfront Fusion での最近のバグ修正のリストについては、[Workfront メンテナンスアップデート](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=ja)ページで、Workfront Fusion メンテナンスアップデートというラベルが付いたアップデートがあるか確認してください。

## Workfront Fusion シナリオでモジュールをコピーする

Workfront Fusion シナリオの操作を容易にするために、モジュールをコピーして貼り付けることができるようにしました。モジュールまたはモジュールのグループをコピーして、同じシナリオまたは別のシナリオに貼り付けることができるようになりました。モジュールをコピーしても、そのモジュールのフィールド値は保持されます。


## Workfront Fusion シナリオで複数のモジュールを選択する

現在は、シナリオの編集時に、一度に複数のモジュールを選択できます。その後、選択したモジュールに対して一括アクションを実行できます。

* コピー
* 移動
* 削除

モジュールをコピーおよび移動すると、モジュールの値とモジュールを接続するすべての線が保持されます。


## モジュールは未保存の情報を保存するようになりました

シナリオの作成を容易にするために、モジュールがフォーカスされていないときにフィールド値を保持できるようにしました。ここで、保存せずにモジュールの外側をクリックし、そのモジュールに戻ると、フィールドには以前に入力した値が表示されます。モジュールが閉じると、未保存のフィールドがあることを示すインジケーターが表示されます。

## Azure AD コネクタで、新しいレコードと更新されたレコードが別々に処理されるようになりました

新しいレコードと既存のレコードの更新が、別々のモジュールで処理されるようになりました。

* 新しいレコードを監視するには、レコードを監視トリガーモジュールを使用できます。このモジュールは、更新されたレコードを監視しなくなりました。
* 更新されたレコードを取得するには、新しいユーザー/グループデルタの検索モジュールを使用できます。このモジュールは、新しいレコード、更新されたレコード、削除されたレコードを返します。
