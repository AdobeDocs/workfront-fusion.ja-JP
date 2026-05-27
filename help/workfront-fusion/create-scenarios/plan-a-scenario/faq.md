---
title: シナリオ計画に関するよくある質問
description: この記事の情報は、Workfront Fusionでシナリオを作成する際に役立つ可能性があります。
author: Becky
feature: Workfront Fusion
exl-id: 6a1d672d-0bd7-4a3a-b96d-6d8b4c97522d
TQID: https://experienceleague.adobe.com/PQablbYLDlXlY5mc7qMAXMrXnUeeHA6sSc-aMVHa6HY
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 554
ht-degree: 37%

---

# シナリオ計画に関するよくある質問

この記事の情報は、Workfront Fusionでシナリオを作成する際に役立つ可能性があります。

## シナリオとは何ですか？

### 回答

シナリオでは、Adobe Workfront Fusionで実行する一連のステップを定義します。 シナリオごとに、データソース、使用するデータ、データの処理方法を指定します。 Adobe Workfront Fusionでは、シンプルなシナリオや複雑なシナリオを作成し、組織のユースケースに対応することができます。

シナリオについて詳しくは、[シナリオの概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md)を参照してください。

## シナリオで使用できるモジュールの数

### 回答

必要な数のモジュールを 1 つのシナリオで使用できます。 モジュールをルートに分けて、各ルートを流すデータを指定できます。 あるモジュールの出力を別のモジュールへの入力として使用することもできます。

シナリオのモジュール数に制限はありませんが、150を超えるモジュールはシナリオのパフォーマンスに影響を与える可能性があります。

モジュールについて詳しくは、[ モジュールの概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md)を参照してください。

## Workfront Fusionはファイルと連携できますか？

### 回答

はい。 Workfront Fusionでは、ファイルの受信、保存、変換、変換、暗号化を行うことができます。 また、Fusionには、ユーザーがファイルに含まれるデータを効果的かつクリエイティブに作業できるように設計された、幅広い組み込み機能も用意されています。

Fusionでのファイルの操作について詳しくは、[ モジュール間でのファイルのマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-files.md)を参照してください。

## 一部のトリガーではシナリオを即座に実行できます。 「即座」とは何を意味しますか？

### 回答

シナリオは、1時間ごと、5分ごとに指定したスケジュールに従って実行できます。 インスタントトリガー（Web フック）と呼ばれる特別なトリガーがあり、特定のサービスからデータを受け取った直後にシナリオを開始できます。 Fusionは、次のスケジュールされた実行を待たずに、受信したデータを即座に処理します。

ポーリング済みモジュールとインスタントトリガーの違いについて詳しくは、トリガーの概要の「[ モジュール ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)」を参照してください。

## 操作とは何ですか？

### 回答

操作とは、モジュールが実行する任意のタスクです。 例えば、トリガーが実行されたり、アクションがタスクを実行したりするたびに、操作が発生します。

一部のFusion プランは、組織が使用する運用数に基づいています。

操作について詳しくは、[操作](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md)を参照してください。

## データ転送量とは何ですか？

### 回答

データ転送量とは、シナリオを通じて転送されたデータの量を指します。 例えば、Workfrontから100 KBの画像を取得し、その画像をドキュメントストレージプロバイダーにアップロードするシナリオです。 このシナリオで使用されるデータの量は 200KB です。

## 接続とは何ですか？

### 回答

接続とは、Workfront Fusion アカウントと、使用するサードパーティサービスとの間のリンクです。 シナリオの編集時に接続を作成できます。

詳しくは、[接続の概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md)を参照してください。

## アグリゲータとはどのようなものですか？

### 回答

[!UICONTROL アグリゲータ]は、データを 1 つのコレクションに結合するものです。 例えば、ファイルを zip アーカイブに圧縮して、メールの添付ファイルとして送信するなどです。

詳しくは、[[!UICONTROL Aggregator] モジュール ](/help/workfront-fusion/references/modules/aggregator-module.md)を参照してください。

## 複数の添付ファイルを含むメールをWorkfront Fusionで処理するとどうなりますか？

### 回答

[!UICONTROL メール]モジュールの[!UICONTROL 添付ファイルの取得]を使用すると、各添付ファイルは、シナリオ内の残りのモジュールを通じて個別に送信されます。 複数のファイルを一度に受け取る他のアプリでも、同様のモジュールを使用できます。
