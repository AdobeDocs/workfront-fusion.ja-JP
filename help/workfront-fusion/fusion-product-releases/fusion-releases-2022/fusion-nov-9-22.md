---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion リリースアクティビティ：2022年11月7日（PT）の週
description: このページでは、2022年11月7日（PT）の週に Adobe Workfront Fusion で行なわれたすべての機能強化について説明します。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 9d58abd0-1fe7-43c8-a1ea-2fadea738590
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 100%

---

# Workfront Fusion リリースアクティビティ：2022年11月7日（PT）の週

**Web フックキューの最適化**

Fusion の web フックキューは、このリリースで最適化されました。web フックを受け入れるサービスは、キューや他のプロセスから分離されました。この変更により、Fusion で web フックキューをより迅速かつ一貫性のある速度で処理できるようになりました。

この変更の実装時に、キューに加えられた web フックイベントに対して予想されるログ処理時間をより良く理解できました。Fusion の web フックビューアーページは 1 分以内になることが予想されます。

現在キューに入れられている web フックイベントを表示するには、左側のナビゲーションで web フックに移動します。分子に数字が入った「トラック」アイコンは、その web フックのキューイベントを示します。「トラック」アイコンをクリックして、キュー内のイベントを表示します。


**未使用の web フックは、非アクティブ化または削除されます**

Workfront Fusion での未使用の web フックの処理方法の一部を変更しました。次のどちらかに該当する場合、web フックは自動的に無効化されます。

* Web フックが 6 日以上どのシナリオにも接続されていない
* Web フックが、非アクティブなシナリオ（非アクティブになってから 30 日を超えたシナリオ）でのみ使用される。

非アクティブ化された web フックは、いかなるシナリオにも接続されておらず、非アクティブ状態となって 30 日が経過した場合、自動的に削除され、登録解除されます。
