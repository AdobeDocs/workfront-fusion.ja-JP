---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: カスタム UI拡張機能：記事インデックス
description: Workfront Fusionのカスタム拡張機能
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 3%

---


# カスタム UI拡張機能：記事インデックス

Fusionのインターフェイス内に独自のweb UIを表示できます。 拡張機能と呼ばれる小さなweb アプリを作成し、それをAdobeに公開すると、Fusionのナビゲーションにボタンとして表示されます。 ユーザーがクリックすると、UIがFusionのメイン領域に読み込まれ、ログインしているユーザー、作業している組織やチームなどの情報が自動的に受け取られます。

この節では、Adobe App Builderまたはフロントエンドフレームワークの経験を前提とせずに、プロセス全体を順を追って説明します。 また、必要なコードと、そのコードの説明も含まれています。

## このガイドを使用するタイミング

Fusionにカスタム画面またはツールを追加する場合は、このガイドを使用します。 エキスパートである必要はありません。 コマンドをターミナルにコピーし、いくつかのテキストファイルを編集することに慣れている必要があります。

カスタム UI拡張機能を作成するには、Adobe IDとAdobe組織へのアクセス（Fusionへのログインに使用するのと同じ種類のアクセス）が必要です。

## 構築するもの

このガイドの最後には、次のことが含まれます。

1. 無料のAdobe **App Builder** プロジェクト。 ここに拡張機能が格納されています。
1. カスタム UIをレンダリングする小さなweb アプリ。
1. そのweb アプリがFusionの拡張ポイントのいずれかに接続され、Fusion ナビゲーションに表示されます。
1. 現在のユーザー、組織、チームなどのライブコンテキストを読み取り、ユーザーが組織またはチームを切り替えたときに反応するUI。
1. 拡張機能が公開され、組織内の他のユーザーが拡張機能を参照できるようになりました。

<!--

## How it works, in one picture

```
  Fusion (the "Host")                         Your extension (the "Guest")
  ───────────────────────────────                         ──────────────────────────────
  Left navigation                             A web app hosted by Adobe
   └── Organization                            (App Builder + UI Extensibility)
       └── [Your extension button]  ── click ──▶ Fusion opens your UI in an iframe
                                              and sends it live context:
                                               * signed-in user
                                               * active organization
                                               * active team
                                               * Adobe IMS identifiers
```

Fusion is the **host**. Your extension is the **guest**. They run in separate browser frames and talk to each other through Adobe's **UI Extensibility SDK** (no custom networking required on your side).

-->

## 目次

最初にページを順番に読み上げます。 後で、必要なものに直接ジャンプできます。

| # | ページ | 内容 |
| --- | ------ | ---------------- |
| 1 | [概要と主要な概念](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md) | 語彙、アーキテクチャ、および各Fusion拡張ポイントの目的。 |
| 2 | [ ツールとAdobe アカウントを設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md) | Node.js、Adobe I/O CLI、ログイン、Adobe Developer Consoleでのプロジェクトの作成。 |
| 3 | [ プロジェクトを作成し、Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)用に設定します | `aio` コマンドラインを使用して、汎用App Builder プロジェクトを生成します（製品固有のテンプレートではありません）。 次に、プロジェクトをFusion拡張機能ポイントに指定し、ウィジェットを登録します。 |
| 5 | [UIを作成](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md) | カスタム画面をレンダリングし、Fusionで接続（「ハンドシェイク」）を完了します。 |
| 6 | [Fusion コンテキスト参照](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md) | Adobe Workfront Fusionを使用すれば、それらのデータをもとに変更を加える必要がなくなります。 |
| 7 | [拡張機能を公開](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md) | 拡張機能のビルド、デプロイ、Fusionでの表示。 |
| 8 | [トラブルシューティング](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md) | 最も一般的なエラーの修正。 |
| 9 | [ デモのチュートリアル ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-09-demo-walkthrough.md) | 1つのリニアなコピーペースト スクリプト：汎用Experience Cloud Shell テンプレートのscaffold→Fusionにリターゲティング→、Fusionで実行され→ステージングにデプロイします。 ライブデモに最適です。 |
| 10 | [WorkfrontおよびFusion APIの呼び出し](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md) | ランタイムアクションプロキシを使用して、ブラウザーのCORSを押さずに拡張機能からバックエンド APIを呼び出します。 `require-adobe-auth`、Fusion v3 ヘッダー、および作業済みの例について説明します。 |

## 可用性に関するメモ

Fusionは現在、次の拡張ポイントを公開しています。

* `fusion/nav-organization/1` – 「**組織**」セクションに表示されます。
* `fusion/nav-team/1` – 「**チーム**」セクションに表示されます。

これらの1つに対して公開する前に、拡張機能ポイントをAdobeにオンボーディングする必要があります。 拡張機能ポイントが「存在しません」と表示され、公開手順が失敗した場合は、[ トラブルシューティング ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)を参照してください。

## Adobeの公式ドキュメント

このガイドはFusionに特化しています。 基礎となるプラットフォームの場合、規範的な参照は次のとおりです。

* [UI拡張機能の概要](https://developer.adobe.com/uix/docs/)
* [UI拡張機能の開発フロー](https://developer.adobe.com/uix/docs/guides/development-flow/)
* [UI拡張機能の管理（公開/承認/取り消し）](https://developer.adobe.com/uix/docs/guides/publication/)
* [Adobe App Builder入門](https://developer.adobe.com/app-builder/docs/getting_started/)
