---
title: Workfront Fusion のリースアクティビティ：2021年9月13日（PT）の週
description: Workfront Fusion のリースアクティビティ：2021年9月13日（PT）の週
author: Luke
draft: Probably
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: bc72bb8b-25d9-488f-a1f0-89d4f41a7e76
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 100%

---

# Workfront Fusion リリースアクティビティ：2021年9月13日（PT）の週

このページでは、2021年9月23日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。

最近のすべての変更内容のリストについては、[Adobe Workfront Fusion リリースアクティビティ](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)を参照してください。

Workfront Fusion での最近のバグ修正のリストについては、[Workfront メンテナンスアップデート](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=ja)ページで、Workfront Fusion メンテナンスアップデートというラベルが付いたアップデートがあるか確認してください。

## Workfront Fusion シナリオ実行履歴のフィルターと並べ替え

特定のシナリオ実行を見つけやすくするために、シナリオ実行履歴の他のフィールドでフィルタリングできるようになりました。既存のフィルターに加えて、次のようにフィルタリングできるようになりました。

* 実行期間
* 操作の数
* データ転送量
* アクションタイプ（実行または更新）

以前は、実行履歴でフィルタリングできるのは開始時刻またはステータスのみでした。

また、シナリオ実行履歴の並べ替えもできるようになりました。次の値で並べ替えることができます。

* 実行開始時間
* 実行ステータス
* 実行期間
* 操作の数
* データ転送量


## Fusion 内のヘルプリンクから特定の記事にアクセスできるようになりました。

必要な情報を容易に検索できるように、Fusion 内のヘルプリンクを更新し、作業中の Fusion エリアに関する記事に直接アクセスできるようにしました。

Fusion の任意のエリアでヘルプアイコンをクリックすると、そのエリアに関する記事にアクセスできます。例えば、シナリオ設定パネルのヘルプリンクは、シナリオ設定パネルを説明する記事に、Workfront モジュールのヘルプリンクは Workfront モジュールの設定方法を説明する記事にリンクされます。また、説明テキスト内でハイライト表示されたリンクをクリックすると、サポートされる日付と時刻の形式のリストなど、説明テキストに関連する記事が表示されます。

以前は、Fusion 内のヘルプリンクから Workfront Fusion のドキュメントを開き、目的のトピックを検索していました。

## シナリオ実行履歴に詳細がある場合のみ、「詳細」ボタンが表示される

シナリオ実行テーブルでより明確にするために、詳細がある実行に対してのみ「詳細」ボタンを表示するようにしました。実行の詳細がアーカイブされたかどうかを一目で確認できるようになりました。「詳細」ボタンの機能に変更はありません。

以前は、すべての実行に「詳細」ボタンが表示されていたので、ユーザーが「詳細」をクリックしても、詳細が表示されないことがありました。


## SDL Managed Translation コネクターのタイムアウトが 120 秒に増加

SDL Managed Translation コネクターのタイムアウトを低減するために、タイムアウト時間を 120 秒に増やしました。

以前は、SDL Managed Translation は Workfront Fusion のタイムアウトガードレールである 40 秒に従っていました。
