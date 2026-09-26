---
title: ストレージの初期化
description: ユーザーが初めてストレージに移動すると、チームの代わりにAdobe Storageへの安全な接続を作成する初期化画面が表示されます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 01689332f97c15b317e686d11a27cb4dc7e2e8bd
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%
---
# Workfront Fusionでのストレージの初期化

Adobe クラウドストレージ内のリポジトリ、フォルダー、ファイルを表示するには、事前にFusion ストレージ領域を初期化する必要があります。

ストレージの概要については、[&#x200B; ストレージの概要](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md)を参照してください。

## ストレージの初期化

1. Workfront Fusionで、左側のナビゲーションで「**ストレージ**」をクリックします。
1. 「**ストレージの初期化**」をクリックします。

Fusionは、チームの代理としてAdobe Storageへの安全な接続を自動的に作成します。

接続が確立されると、Fusionはチームのストレージリポジトリを読み込みます。

## 初期化のトラブルシューティング

| メッセージ | 理由 | ユーザーの役割 |
| -------- | -------- | ------------------------ |
| **アクセス制限** | Adobe IMSがオンボーディングされていません。 | IMS オンボーディングを完了するには、組織の管理者にお問い合わせください。 |
| **組織の不一致** | ユーザーは、Fusionで選択した組織とは異なるAdobe組織にログインしています。 | ログアウトしてから、正しいAdobe IMS組織で再度ログインします。 |
| **アクセスが拒否されました** | ユーザーのアカウントに必要な権限がないか、Adobe ストレージが組織で使用できません。 | 組織の管理者とアカウントの権限を確認します。 解決後、**再試行**&#x200B;をクリックします。 |
| **ストレージが見つかりません** | 接続が確立されましたが、リポジトリが見つかりませんでした。 | Adobe ストレージが組織用にプロビジョニングされていることを確認します。 検証後、**ストレージを読み込み**&#x200B;をクリックして再試行してください。 |
