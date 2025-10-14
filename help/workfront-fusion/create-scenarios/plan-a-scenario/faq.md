---
title: シナリオプランニングに関するよくある質問
description: この記事は、Workfront Fusion でシナリオの作成を開始する際に役立つ場合があります。
author: Becky
feature: Workfront Fusion
exl-id: 6a1d672d-0bd7-4a3a-b96d-6d8b4c97522d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 33%

---

# シナリオプランニングに関するよくある質問

この記事は、Workfront Fusion でシナリオの作成を開始する際に役立つ場合があります。

## シナリオとは何ですか？

### 回答

シナリオは、Adobe Workfront Fusion で実行される一連の手順を定義します。 シナリオごとに、データソース、使用するデータ、データの処理方法を指定します。 Fusion を使用すると、シンプルなシナリオや複雑なシナリオを作成して、組織のユースケースに対応できます。

シナリオについて詳しくは、[&#x200B; シナリオの概要 &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md) を参照してください。

## シナリオでは何個のモジュールを使用できますか？

### 回答

必要な数のモジュールを 1 つのシナリオで使用できます。モジュールをルートに分けて、各ルートを流れるデータを指定できます。 また、あるモジュールの出力を別のモジュールへの入力として使用することもできます。

シナリオ内のモジュール数に制限はありませんが、150 を超えるモジュールがシナリオのパフォーマンスに影響を与える可能性があります。

モジュールについて詳しくは、[&#x200B; モジュールの概要 &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md) を参照してください。

## Workfront Fusion はファイルで動作しますか？

### 回答

はい。Workfront Fusion は、ファイルの受信、保存、変換、変換および暗号化を行うことができます。 Fusion には、ファイルに含まれるデータを効率的かつクリエイティブに操作できるように設計された様々な組み込み機能も用意されています。

Fusion でのファイルの操作について詳しくは、「[&#x200B; モジュール間でのファイルのマッピング &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-files.md)」を参照してください。

## 一部のトリガーではシナリオを即座に実行できます。「即座」とは何を意味しますか？

### 回答

シナリオは、指定したスケジュールに従って、1 時間ごと、5 分ごとなど、一定の間隔で実行できます。 インスタントトリガー（Web フック）と呼ばれる特別なトリガーがあり、特定のサービスからデータを受け取った直後にシナリオを開始できます。Fusion は、次にスケジュールされた実行を待たずに、受信したデータを直ちに処理します。

ポーリングされたモジュールとインスタント トリガーの違いについて詳しくは、「モジュールの概要」の [0&rbrace;トリガー モジュール」を参照してください。](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)

## 操作とは何ですか？

### 回答

操作とは、モジュールが実行する任意のタスクです。例えば、トリガーが実行されたり、アクションがタスクを実行したりするたびに、操作が発生します。

一部の Fusion プランは、組織が使用する操作数に基づいています。

操作について詳しくは、「[&#x200B; 操作 &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md)」を参照してください。

## データ転送量とは何ですか？

### 回答

データ転送量とは、シナリオを通じて転送されたデータの量を指します。例えば、Workfrontから 100 KB の画像を取得し、その画像をドキュメントストレージプロバイダーにアップロードするシナリオがあります。 このシナリオで使用されるデータの量は 200KB です。

## 接続とは何ですか？

### 回答

接続とは、Workfront Fusion アカウントと、使用するサードパーティのサービスとのリンクです。 接続は、シナリオの編集時に作成できます。

詳しくは、[&#x200B; 接続の概要 &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md) を参照してください。

## アグリゲータとはどのようなものですか？

### 回答

[!UICONTROL アグリゲータ]は、データを 1 つのコレクションに結合するものです。例えば、ファイルを zip アーカイブに圧縮して、メールの添付ファイルとして送信するなどです。

詳しくは、[[!UICONTROL Aggregator] モジュール &#x200B;](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

## Workfront Fusion で複数の添付ファイルを含むメールを処理するとどうなりますか？

### 回答

[!UICONTROL メール]モジュールの[!UICONTROL 添付ファイルの取得]を使用すると、各添付ファイルは、シナリオ内の残りのモジュールを通じて個別に送信されます。複数のファイルを一度に受け取る他のアプリでも、同様のモジュールを使用できます。
