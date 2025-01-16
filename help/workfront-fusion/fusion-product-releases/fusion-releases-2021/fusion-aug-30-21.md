---
title: Workfront Fusion リリースアクティビティ：2021年8月30日（PT）の週
description: Workfront Fusion リリースアクティビティ：2021年8月30日（PT）の週
author: Luke
draft: Probably
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: cac11147-5b3d-477b-869b-e255528c4bec
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---

# Workfront Fusion リリースアクティビティ：2021年8月30日（PT）の週

このページでは、2021年8月30日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。

最近のすべての変更内容のリストについては、[Adobe Workfront Fusion リリースアクティビティ](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)を参照してください。

Workfront Fusion での最近のバグ修正のリストについては、[Workfront メンテナンスアップデート](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=ja)ページで、Workfront Fusion メンテナンスアップデートというラベルが付いたアップデートがあるか確認してください。

## Workfront／イベント監視モジュールをトリガーするイベントをフィルタリングする

1. Workfront／イベント監視モジュールをトリガーにするイベント用のカスタムフィルターを設定する

   不要なシナリオの実行数を減らすために、Workfront／レコード監視モジュールを更新し、イベントのフィルタリングを有効にしました。Webhook を作成する際にフィルターを設定できるようになりました。これにより、イベントが特定の条件を満たす場合にのみ、トリガーが発生します。

   イベントフィルターは、現在、次の操作を提供しています。

   * 等しい：イベントがフィルターの条件に一致する場合にのみシナリオをトリガーします。例えば、イベントが特定のプロジェクトで発生した場合にのみシナリオをトリガーするフィルターを設定できます。
   * 等しくない：イベントがフィルターの条件に一致しない場合にのみシナリオをトリガーします。例えば、イベントが発生したイシューのステータスが「クローズ」でない場合にのみシナリオをトリガーするフィルターを作成できます。

   以前は、記録を監視モジュールではすべての記録を取得していました。ユーザーは、シナリオの後半でフィルターを設定することでのみ、フィルタリングできました。

   イベントのフィルタリングを活用するには、イベント監視モジュールで新しい Web フックを作成します。現在、この機能を含めるために既存の Web フックを編集することはできません。既存のシナリオに対して、イベントフィルターを使用して新しい Web フックを作成することを強くお勧めします。

1. 現在の接続でトリガーされたイベントを除外します。

   Web フックを Workfront／イベント監視モジュール用に簡単に設定できるように、最も一般的なイベントフィルターが組み込まれました。Web フックには、イベント監視モジュールに指定された接続を使用してモジュールによって行われた変更を除外するオプションが追加されました。つまり、このフィルターを有効にすると、その接続に関連付けられた Workfront ユーザーが行った変更では、シナリオをトリガーできなくなります。

   以前は、このフィルターは使用できませんでした。したがって、Workfront モジュールに加えられた変更により、それらのモジュールを含むシナリオがトリガーされやすくなり、シナリオが無限ループで自動的にトリガーされる可能性がありました。
