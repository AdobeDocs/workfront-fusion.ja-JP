---
title: インスタントトリガー（Webhook）
description: 多くのサービスでは、サービスで特定の変更が発生した場合に即座に通知を受け取る Web フックが用意されています。これらの通知を処理するには、インスタントトリガーを使用することをお勧めします。この記事では、Adobe Workfront Fusion でのインスタントトリガーの使用と機能について説明します。
author: Becky
feature: Workfront Fusion
exl-id: 5bfda2b2-dc1c-4ff6-9236-b480bfda2e58
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 28%

---

# インスタントトリガー（Webhook）

多くのサービスでは、サービス内で特定の変更（イベント）が発生したときに即座に通知を配信する Webhook を提供しています。 これらのイベントを処理するには、インスタント トリガーを使用することをお勧めします。 インスタントトリガーは、特定のコネクタのモジュールのリストに `Instant` タグを表示します。

![今すぐ](assets/instant.png)

>[!TIP]
>
>コネクタのモジュールのリストをチェックして、インスタントトリガーがあるかどうかを確認したり、[Fusion アプリケーションとそのモジュールのリファレンス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md) にあるコネクタのドキュメントを確認したりできます。
>
>Adobe Workfrontのインスタントトリガーのドキュメントについては、Workfront モジュールの記事の [&#128279;](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#triggers)0&rbrace;トリガー&rbrace; を参照してください。

コネクタに Webhook が含まれていない場合は、次のいずれかを実行できます。

* Webhook モジュールを使用してカスタム Webhook を作成します。
詳しくは、[Web フック](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)を参照してください。
* ポーリングトリガーを使用して、サービスを定期的にポーリングします。
詳しくは、[ シナリオのスケジュール設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください

Workfront Fusion の web フックの概要ビデオについて詳しくは、次を参照してください。

* [Web フックの概要](https://video.tv.adobe.com/v/3427025/){target=_blank}
* [Web フック（中級）](https://video.tv.adobe.com/v/3427030/){target=_blank}

## インスタントトリガーをスケジュールする

インスタント トリガーを構成すると、実行時に選択するように求められます。

![ スケジュール設定 ](assets/schedule-setting.png)

サービスから新しいイベントを受け取るとすぐにシナリオを実行する [!DNL Workfront Fusion] 合は、「`Immediately`」を選択します。 これらのイベントは直ちにキューに送信され、データを受信するのと同じ順序で、シナリオで 1 つずつ処理されます。

シナリオを実行すると、キューで待機している保留中のイベントの合計数がカウントされ、保留中のイベントがあるサイクルと同じ数のサイクルがシナリオで実行され、サイクルごとに 1 つのイベントが処理されます。

サイクルについて詳しくは、[ シナリオの実行、サイクル、フェーズ ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md) を参照してください。

>[!NOTE]
>
>* サイクルは、シナリオ実行とは異なります。1 つのシナリオ実行に複数のサイクルを含めることができます。
>* 実行するようにスケジュールされたインスタント・トリガーを使用してシナリオを実行する場合は、次の例外 `Immediately` 適用されます。
>
>     * 2 回の実行の間隔は、料金プランに基づく最小の間隔の対象ではありません。
>
>       例えば、シナリオの実行が完了すると、Web フックのキューが再度チェックされます。保留中の Web フックがある場合は、シナリオが直ちに再実行され、保留中の Web フックがすべて再度処理されます。
>   
>     * 「最大サイクル数」シナリオ設定は無視され、100 に設定されます。これは、単一のシナリオ実行時に（サイクルあたり 1 イベントの割合で） 100 個を超える保留中の Webhook が処理されないことを意味します。
>


[!UICONTROL Immediately] 以外のスケジュール設定を使用する場合、シナリオは指定した間隔で実行されます。 この間隔のキューには複数の Webhook が収集されるので、[!UICONTROL Maximum number of cycles] オプションをデフォルトの 1 より大きい値に設定して、1 回のシナリオ実行でより多くの Webhook を処理することをお勧めします。

1. シナリオの下部にある [!UICONTROL Scenario settings] アイコン ![ シナリオ設定アイコン ](assets/scenario-settings-icon.png) をクリックします。
1. 表示される **[!UICONTROL Scenario settings]** パネルで、「**[!UICONTROL Max number of cycles]**」フィールドに数値を入力し、シナリオを実行するたびに実行するキューのイベント数を指定します。

キューに残っているイベントは、次回シナリオを実行するときに、「最大サイクル数」フィールドで設定された数まで処理されます。

## Webhook ガードレール

Workfront Fusion では、パフォーマンスを高めるために、Webhook 用に次のガードレールが用意されています。

### レート制限

現在のレート制限は、1 秒あたり 5 Web フックです。制限を超えた場合は、`429` のステータスコードが返されます。

### 非アクティブな Web フックの有効期限

120 時間を超えてどのシナリオにも割り当てられていない Web フックは削除されます。

### Web フックペイロード

[!DNL Workfront Fusion] は、30 日間、Web フックペイロードを保存します。Webhook ペイロードの作成後 30 日以上にアクセスすると、[!UICONTROL `Failed to read file from storage.`] というエラーが発生する

### エラー処理

インスタントトリガーでシナリオにエラーが発生した場合は、次のようになります。

* シナリオが [!UICONTROL Immediately] 実行に設定されると、直ちに停止します。
* シナリオがスケジュールどおりに実行されるように設定されている場合に、3 回失敗（3 回のエラー）すると停止します。

シナリオの実行中にエラーが発生した場合、そのイベントはインスタントトリガーのロールバックフェーズでキューに戻されます。 このような場合は、シナリオを修正して再実行できます。

詳細については、「シナリオの実行、サイクル、およびフェーズ」の記事の [ ロールバック ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) を参照してください。

シナリオに Web フックの応答モジュールがある場合、エラーは Web フックの応答に送信されます。Webhook 応答モジュールは常に最後に実行されます（シナリオ設定の「[!UICONTROL Auto commit]」オプションが有効になっていない場合）。

詳しくは、Webhook の記事の [Webhook への応答 ](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md#responding-to-webhooks) を参照してください。

### Webhook の無効化

次のいずれかに該当する場合、Web フックは自動的に非アクティブ化されます。

* Web フックが 6 日以上どのシナリオにも接続されていない
* Web フックが、非アクティブなシナリオ（非アクティブになってから 30 日を超えたシナリオ）でのみ使用される。

非アクティブ化された Webhook は、シナリオに接続されていない場合や、30 日以上非アクティブ化されている場合、自動的に削除され登録解除されます。

## カスタム Web フック

独自の Web フックを作成できます。詳しくは、[Web フック](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)を参照してください。

## リソース

サイクルについて詳しくは、[ シナリオの実行、サイクル、フェーズ ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md) を参照してください。
