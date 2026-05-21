---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion リリースアクティビティ：2021年5月3日（PT）の週
description: このページでは、2021年5月3日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 8858fc79-5eda-4938-9bb5-c05be38f02bc
TQID: https://experienceleague.adobe.com/GZ5W-9Q1Y9M-cCVN1CupZVs8GuQPy4Dusifz-5sxJm8
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 273
ht-degree: 100%

---

# Workfront Fusion リリースアクティビティ：2021年5月3日（PT）の週

このページでは、2021年5月3日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。

最近のすべての変更内容のリストについては、[Adobe Workfront Fusion リリースアクティビティ](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)を参照してください。

Workfront Fusion での最近のバグ修正のリストについては、[Workfront メンテナンスアップデート](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=ja)ページで、Workfront Fusion メンテナンスアップデートというラベルが付いたアップデートがあるか確認してください。

## Salesforce コネクターで SOQL を使用した検索が可能に

Salesforce／レコードを検索モジュールに、SOQL（Salesforce Object Query Language）を使用して検索するオプションが追加されました。 また、以前利用可能なオプション（SOSL および単純検索）を使用して検索することもできます。

## Azure DevOps コネクタの新しい接続タイプに必要なスコープの数が減少

セキュリティを強化するために、Workfront Fusion Azure DevOps コネクタに新しいコネクタータイプが追加されました。 Azure DevOps モジュールで接続を作成する際に、次の 2 種類の接続から選択できます。

* Azure DevOps

  この新しい接続タイプでは、スコープは Workfront Fusion で特に必要なスコープに制限されます。

* Azure DevOps（すべてのスコープをリクエスト）

  これはレガシーの接続タイプで、Azure DevOps への接続で使用可能なすべてのスコープをリクエストします。

Azure DevOps を使用するすべての新しいシナリオで、Azure DevOps 接続タイプを使用することをお勧めします。 また、既存のシナリオで Azure DevOps モジュールを変更して、新しい接続タイプを使用することをお勧めします。 レガシー Azure DevOps（すべてのスコープをリクエスト）接続タイプは、近い将来非推奨となります。
