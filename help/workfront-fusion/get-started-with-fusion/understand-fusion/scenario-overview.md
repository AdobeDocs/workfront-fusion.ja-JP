---
title: シナリオの概要
description: Adobe Workfront Fusion を使用するには、Adobe Workfront ライセンスに加えて、Adobe Workfront Fusion ライセンスが必要です。
author: Becky
feature: Workfront Fusion
exl-id: de81ad4c-27e5-4b6c-acf0-f01a8c85922e
source-git-commit: 34dad92019ca855f40698d3f3795788698c1cece
workflow-type: ht
source-wordcount: '704'
ht-degree: 100%

---

# シナリオの概要

Adobe Workfront Fusion の役割は、プロセスを自動化して、ユーザーが通常のタスクに多くの時間を費やさなくてもいいようにすることです。これは、アプリ内やサービス内、およびそれらの間でアクションをリンクし、データを自動的に転送および変換するシナリオを作成することで機能します。作成するシナリオは、アプリまたはサービス内のデータを監視し、そのデータを処理して必要な結果を提供します。

シナリオは、アプリ内でのデータの変換方法や、アプリと web サービスの間でのデータの転送方法を示す、一連のモジュールで構成されます。

## シナリオ要素の概要

シナリオは様々な要素で構成されています。これらの要素の用語を理解すると、ドキュメントを簡単に使用できるようになります。

* [シナリオ](#scenario)
* [トリガー](#trigger)
* [モジュール](#module)
* [ルート](#route)
* [シナリオセグメント](#scenario-segment)
* [コネクター](#connector)

### シナリオ

**シナリオ**&#x200B;は、データの移動と操作を目的にユーザーが作成した一連の自動ステップです。「シナリオ」という用語は、関連する一連のステップ全体を指します。

![シナリオ](assets/entire-scenario-scenario.png)

### トリガー

シナリオは&#x200B;**トリガー**&#x200B;によって開始されます。トリガーは、新しいデータおよび更新されたデータを監視し、モジュールで設定された特定の条件が適用されるとシナリオを開始します。トリガーは、スケジュール（ポーリング）に従って、またはデータの変更が発生した場合（インスタント）にシナリオを開始するように設定できます。

![トリガー](assets/scenario-trigger.png)

### モジュール

トリガーの後に、多数の&#x200B;**モジュール**&#x200B;が続きます。モジュールは、特定のアクションを実行するシナリオの 1 つの手順を表します。モジュールは、シナリオを作成するのに設定され、連結されています。

![モジュール](assets/scenario-module.png)

### ルート

シナリオは、**ルート**&#x200B;に分割できます。ルートとは、特定のデータバンドルに使用される場合とされない場合がある、シナリオのセクションです。ルートは、ルーターモジュールとフィルターを使用して設定されます。

![ルート](assets/scenario-route.png)

### シナリオセグメント

シナリオセグメントは、同じアプリケーションに接続される一連の連続したモジュールで構成される 1 つのシナリオの 1 つのセクションです。シナリオセグメントは、多くの場合、アプリケーションの短いワークフローを表します。

![シナリオセグメント](assets/scenario-segment.png)

### コネクター

コネクターは、特定のアプリケーション向けのモジュールのセットです。Workfront Fusion には、Workfront、Salesforce、Jira など多くの一般的な作業アプリケーションへのコネクターや、任意の web サービスに使用できる汎用コネクターが用意されています。

![コネクター](assets/scenario-connectors.png)

## 例

次のセクションを展開すると、シナリオの例とその説明が表示されます。

+++**Adobe Workfront 内のプロセスの自動化**

Workfront Fusion では、Workfront 内で単純または複雑なワークフローを自動化して時間を節約し、プロセスを一貫して実行できます。

この例では、指定したフィールドが Workfront のタスクまたはイシューで変更されるとシナリオがトリガーされます。トリガーされると、シナリオは関連プロジェクトの情報を取得し、プロジェクトの特定の役割に割り当てられたユーザーに合わせて更新を作成します。

![テンプレートの例](assets/fusion-template-example.png)

+++

+++**Workfront を別のアプリまたは web サービスに接続**

>[!NOTE]
>
>組織で従来のライセンスモデルを使用する場合、他のアプリケーションに接続するには、Workfront Fusion for Work Automation および Integration のライセンスが必要です。

Workfront Fusion は、他のアプリケーションや web サービスに接続できます。他のアプリケーションからデータへのアクセス、およびデータの読み込み、処理、書き出しを行うことができ、データを相互に統合したり、Workfront と統合したりすることができます。

多くのアプリケーションには専用の Workfront Fusion コネクターがあります。アクセスするアプリケーションに専用コネクターがない場合は、Workfront Fusion の HTTP または SOAP モジュールを使用して、その API を介してアプリケーションに接続できます。

この例では、ユーザーが [!DNL Excel] スプレッドシートに追加されるとシナリオがトリガーされます。シナリオでは、ユーザーが Workfront に存在するかどうかがチェックされます。存在しない場合は Workfront でユーザーが作成され、その Workfront ユーザー ID がスプレッドシートに追加されます。

![統合の例](assets/fusion-integration-example.png)

専用コネクターのリストについて詳しくは、[Fusion アプリケーションとそのモジュールの参照：記事のインデックス](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)を参照してください。


>[!IMPORTANT]
>
>Adobe Workfront Fusion は、ほぼすべての web サービスに接続できます。使用するアプリに専用の Workfront Fusion コネクターがない場合は、ユニバーサルコネクターを使用してアプリまたはサービスに接続できます。
>
>ユニバーサルコネクターのリストについて詳しくは、[ユニバーサルコネクター](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)を参照してください。

+++

## 参照

* Adobe Workfront Fusion で使用される用語について詳しくは、[Adobe Workfront Fusion 用語集](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md)を参照してください。
* 練習シナリオの作成を開始方法について詳しくは、[基本シナリオの作成](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)を参照してください。
* シナリオの作成と管理について詳しくは、以下にリストされている記事を参照してください。
   * [シナリオの作成](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)
   * [シナリオの管理](/help/workfront-fusion/manage-scenarios/manage-scenarios-toc.md)
