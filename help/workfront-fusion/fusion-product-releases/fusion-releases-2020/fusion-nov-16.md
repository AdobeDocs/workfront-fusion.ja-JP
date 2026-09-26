---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion リリースアクティビティ：2020年11月16日（PT）の週
description: このページでは、2020年11月16日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 69e4a458-fd32-4dcd-be43-19a9467cf678
TQID: 'https://experienceleague.adobe.com/X4pdG9n2rKQCT-BbLrcLseer2dqHx4mAN9rHdrHLyNo'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
    internal-label: Integrations
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
  - id: d968a1bc-9a90-4926-a531-bcf272c32aad
    internal-label: Administration
subfeature_v2:
  - id: a29813d3-f0cc-4b60-9396-13b558370803
    internal-label: Product announcements
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 01689332f97c15b317e686d11a27cb4dc7e2e8bd
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 89%
---
# Workfront Fusion リリースアクティビティ：2020年11月16日（PT）の週

このページでは、2020年11月16日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。

最近のすべての変更内容のリストについては、[Adobe Workfront Fusion リリースアクティビティ](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)を参照してください。

Workfront Fusion での最近のバグ修正のリストについては、[Workfront メンテナンスアップデート](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=ja)ページで、Workfront Fusion メンテナンスアップデートというラベルが付いたアップデートがあるか確認してください。

## Jira Cloud コネクタの更新

Jira Cloud コネクタの使用方法を拡張するために、3 つの新しいモジュールが追加されました。

* スプリントにイシューを追加
* レコードのリスト
* レコードの検索

また、「スプリント」オブジェクトタイプをサポートするように、既存のモジュールも更新しました。 以前は、「スプリント」オブジェクトには、カスタム API呼び出しモジュールからのみアクセスできました。

## シナリオでのマッピングに実行 ID を使用できるようになりました。

シナリオの実行 ID がマッピングパネルで使用できるようになりました。 この ID は、シナリオの特定の実行を表し、メタデータとして使用できます。 例えば、実行 ID は、Fusion が作成するレコードと共に保存できるので、後でどの Fusion の実行がレコードを作成したかを判断できます。 実行 ID は、一般関数の下にあるマッピングパネルにあります。

## Workfront Fusion 2.0 シナリオのキーボードショートカット

シナリオの作成をより便利にするために、キーボードショートカットを追加しました。

* Ctrl/Cmd + Shift + Enter：シナリオの 1 回実行
* Ctrl/Cmd + Shift + S：シナリオの保存

## Office 365 Excel コネクタの更新

Office 365 Excel コネクタの使用方法を拡張するために、新しいモジュールが追加されました。 次の操作が可能になりました。

* ワークブックへの変更からのモジュールのトリガー
* ワークブックの検索またはダウンロード
* ワークシート、ワークシート行、テーブルまたはテーブル行のリスト
* テーブルまたはワークシート行の更新
* テーブルまたはワークシート行の削除
* テーブルのメタデータの取得
* カスタム API 呼び出しの実行

以前使用可能だったモジュールは、アプリ内にまだ存在します。


## Workfront アプリ接続での OAuth 2.0 の使用

OAuth 2.0を使用するようにWorkfront コネクタを更新しました。 このアップデートにより、Workfront アプリの連携を変更しやすくなります。 例えば、接続に関する何か（パスワードなど）が変更された場合、シナリオで個々の接続を更新する必要がなくなりました。 また、OAuth2 には、セキュリティの向上やシングルサインオン（SSO）を使用する機能など、その他のメリットがあります。

現時点では、既存の接続に変更を加える必要はありません。 ただし、OAuth 2.0 のメリットを活用する場合は、既存の接続を再認証できます。
