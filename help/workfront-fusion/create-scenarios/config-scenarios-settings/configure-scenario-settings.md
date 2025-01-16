---
content-type: reference
title: シナリオ設定を指定
description: シナリオ設定パネルで、シナリオに固有の設定を指定できます。
author: Becky
feature: Workfront Fusion
exl-id: 105e3d39-b0ef-4c22-901d-fb4f29e685a9
source-git-commit: 3afa631a44c6dae8b1e6def6f842a9ced9de741e
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 44%

---

# シナリオ設定を指定

シナリオ設定パネルで、シナリオに固有の設定を指定できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の [!DNL Workfront Fusion] 管理者である必要があります。</p>
     <p>チームの [!DNL Workfront Fusion] 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

この表の情報について詳しくは、[Workfront ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## シナリオ設定を開く

1. 左側のパネルで **シナリオ** をクリックします。
1. 目的のシナリオを見つけて、名前をクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. ページの左下隅付近にある歯車アイコンをクリックします。

   ![](assets/scenario-settings-350x221.png)

   表示される [!UICONTROL Scenario settings] パネルで、シナリオの様々な詳細設定を指定できます。
1. 必要に応じて、シナリオ設定を有効または無効にします。 以下の [ シナリオ設定オプション ](#scenario-settings-options) を参照してください。

## シナリオ設定オプション

### [!UICONTROL Sequential processing]

このオプションは、すべての実行を順番に実行します。これは主に Webhook と不完全な実行に関連しています。

順次処理が有効な場合、シナリオの並列実行は無効になります。

**インスタント Webhook**:Webhook トリガーが `instant` として設定され、「順次処理」が有効になっている場合、すべてのインスタント Webhook ペイロードはキューに入り、届いた順に処理されます。 これは、外部システムからのイベントを正確な順序で処理する場合に役立ちます。

>[!NOTE]
>
>次のペイロードが開始される前に各ペイロードが処理されるので、自動処理の遅延が発生します。

**不完全な実行**:「不完全な実行」も有効になっている場合、シナリオの実行中にエラーが発生するとシナリオは一時停止します。 次のいずれかの処理が行われます。

* 「順次処理」オプションが **有効** になっている場合、Workfront Fusion は、すべての不完全な実行が解決されるまで既存のシーケンスの処理を停止します。
* 「順次処理」オプションが **無効** の場合、シナリオはスケジュールに従って引き続き実行され、不完全な実行は繰り返し再試行されます。

  不完全な実行について詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

  >[!NOTE]
  >
  >順番に処理を行うと、シナリオの実行に遅延が生じる場合があります。インスタントシナリオがトリガーされた時、またはスケジュールされたシナリオが実行される時に、キューにまだ未完了の実行がある場合、そのシナリオは、キュー内の前の実行が全て完了してから実行されます。
  >
  >シナリオのユースケースで順番に処理することが必要ない場合は、順番処理のオプションを無効にすることをお勧めします。

  スケジュールの詳細については、[ シナリオのスケジュールの設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。

### データは機密情報

シナリオを実行すると、シナリオ内のモジュールでどのデータが処理されたかに関する情報をデフォルトで表示できます。この情報を保存しない場合は、「[!UICONTROL Data is confidential]」オプションを有効にします。

>[!IMPORTANT]
>
>このオプションを有効にすると、シナリオの実行中に発生する可能性のあるエラーを解決するのが困難になる場合があります。

### [!UICONTROL Allow storing incomplete executions]

このオプションでは、シナリオの実行中にエラーが発生した場合の [!DNL Adobe Workfront Fusion] での処理方法を指定します。このオプションを有効にすると、シナリオは一時停止し、不完全な実行フォルダーに移動します。 これにより、問題を修正し、シナリオが停止した場所から続行できます。このオプションを無効にした場合、シナリオの実行が停止し、ロールバックフェーズが開始します。

不完全な実行について詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

### データ損失を有効にする

このオプションは、空き容量の不足な [!DNL Workfront Fusion] め、不完全な実行のキューにバンドルを保存できない場合に、データの損失を有効にすることに関係しています。 このオプションを有効にすると、シナリオの実行全体で中断が発生しないように、データが失われます。これは、最も優先度が高いものが継続して実行され、入力時の誤りのあるデータがそれほど重要でないシナリオで役立ちます。

その他、シナリオを実行する際に、モジュールで許容される最大サイズを超えるファイルが見つかることがあります。この場合、[!UICONTROL Enable data loss] オプションの設定に従って [!DNL Workfront Fusion] が進行し、警告メッセージが表示されます。

不完全な実行について詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

最大ファイルサイズについて詳しくは、[Fusion パフォーマンスガードレール ](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#files) を参照してください。

警告について詳しくは、「[ エラータイプ ](/help/workfront-fusion/references/errors/error-processing.md)」を参照してください。

### [!UICONTROL Auto commit]

[!UICONTROL Auto commit] の設定はトランザクションに適用され、シナリオの処理方法を定義します。 「自動コミット」オプションがオンの場合、各モジュールのコミットフェーズは、操作フェーズが完了した直後に開始します。「自動コミット」オプションを無効にした場合、すべてのモジュールに対して操作が実行されるまでコミットは行われません（これはデフォルトのモードです）。

### サイクルの最大数

>[!NOTE]
>
>このオプションを表示するには、「**詳細設定を表示**」チェックボックスを有効にする必要があります。


サードパーティのサービスへの接続が中断されるのを防ぎ、1 回のシナリオ実行内にすべてのレコードが確実に処理されるようにする場合は、より多くのサイクルを設定すると便利です。

* ポーリングトリガーで始まるシナリオの場合、この設定で、シナリオの実行中に許可されるサイクルの最大数を定義します。

  ポーリングトリガーについて詳しくは、「モジュールの概要」の [トリガーのポーリング ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#polling-triggers) を参照してください。

* シナリオがインスタントトリガーで開始する場合、設定は無視され、1 回のシナリオの実行中にすべての保留中のイベントが処理されます（1 サイクルにつき 1 つのイベント）。

  インスタント トリガーの詳細については、「モジュールの概要」の [ インスタント トリガー](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers) を参照してください。

* シナリオが（インスタントまたはポーリング）トリガーで始まらない場合は、指定された最大サイクル数が常に実行されます。

>[!BEGINSHADEBOX]

**例：** [!DNL Workfront] > [!UICONTROL Watch record] は発生する新しいイシューを監視し、[!DNL Workfront] >[!UICONTROL Convert object] は新しい要求をプロジェクトに変換して、適切なテンプレートを割り当てます。

![](assets/scenario-settings-ex-1-350x157.png)

[!UICONTROL more cycles] 設定は、シナリオの実行をスケジュールする場合にのみ適用されます。 「[!UICONTROL Run once]」ボタンを使用すると、サイクル設定が考慮されます。

#### サイクルの最大数は 1 に設定されています（デフォルト）

![](assets/max-number-cycles-1-350x201.png)

Workfront/ レコードを監視モジュールの最大サイクル数は `10` に設定されています。
[!DNL Workfront] に 100 件のリクエストが送信され、「最大サイクル数」フィールドが 10 に設定されている場合、1 つのシナリオの実行後、90 個のファイルが未処理のままになります。 次の 10 個のファイルは、スケジュールされた次のシナリオの実行で処理されます。

#### サイクルの最大数を 10 に設定

Workfront/ レコードを監視モジュールの最大サイクル数は `10` に設定されています。

Dropbox フォルダに 100 個のファイルが追加され、[ 最大サイクル数 ] が 10 に設定されている場合は、1 回目のサイクルで 10 個のファイル、2 回目のサイクルで次の 10 個のファイル、3 回目のサイクルで次の 10 個のファイルというように、すべてのファイルが処理されるまで処理されます。

すべてのファイルは、1 回のシナリオ実行の間に処理されます。

シナリオの詳細には、既に実行されたサイクルが表示されます。

![](assets/scenario-detail-350x207.png)

このページについて詳しくは、[ シナリオの詳細 ](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-details.md) を参照してください。

>[!ENDSHADEBOX]

### 連続エラー数

シナリオの実行が無効になる前に連続して実行を試行する最大回数を定義します（`DataError`、`DuplicateDataError` および `ConnectionError` を除く）。

エラーについて詳しくは、「[ エラータイプ ](/help/workfront-fusion/references/errors/error-processing.md)」を参照してください。

>[!NOTE]
>
>シナリオがインスタントトリガーで始まる場合、設定が無視され、最初のエラーが発生するとシナリオは直ちに非アクティブ化されます。
