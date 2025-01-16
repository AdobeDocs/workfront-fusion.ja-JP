---
content-type: reference
title: エラータイプ
description: シナリオ実行中にエラーが発生する場合があります。この問題は通常、サービスへの接続に失敗したためにサービスが使用できない場合や、検証に失敗した場合に発生します。この記事では、発生する可能性のある一般的なエラーについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: abf5f844-d13b-416e-a8b8-2d4ee1786262
source-git-commit: d618d5c4b2306a3b940af7e402f93ced988095a3
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 40%

---

# エラータイプ

シナリオ実行中にエラーが発生する場合があります。これは通常、サービスへの接続エラーが原因でサービスが利用できなくなった場合や、検証に失敗した場合に発生します。

[!DNL Adobe Workfront Fusion] は、いくつかの基本的なエラータイプを区別します。エラーのタイプによって、Fusion シナリオの次のアクションが決まります。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> 新規：標準<p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] ライセンス</td> 
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
 </tbody> 
</table>


ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

Adobe Workfront Fusion ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 接続エラー

`ConnectionError`

接続エラーは、最も一般的なエラーの 1 つです。 通常は、過負荷、メンテナンス、停止など、様々な理由でサードパーティのサービスが利用できないことが原因で発生します。 このエラーのデフォルトの処理は、エラーが発生したモジュールによって異なります。

* 最初のモジュールでエラーが発生した場合、シナリオの実行は警告メッセージとともに終了します。その後、[!DNL Workfront Fusion] は時間間隔を増やしながら、繰り返しシナリオを再実行しようとします。すべての試行が失敗した場合、[!DNL Workfront Fusion] はシナリオを非アクティブ化します。
* 接続エラーが最初のモジュール以外のモジュールで発生した場合、以降の手順は、シナリオの詳細設定の「不完全な実行の保存を許可」オプションによって異なります。

   * このオプションを有効にした場合、シナリオの実行は [!UICONTROL Incomplete executions] フォルダーに移動され、[!DNL Workfront Fusion] では一定の時間間隔で繰り返しシナリオの再実行が試みられます。 すべての試行が失敗した場合、不完全な実行フォルダーに実行が残り、ユーザーが手動で解決するのを待ちます。

     不完全な実行について詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。
   * このオプションが無効になっている場合、シナリオの実行はエラーで終了し、ロールバックフェーズに移ります。その後、[!DNL Workfront Fusion] は時間間隔を増やしながら、繰り返しシナリオを再実行しようとします。すべての試行が失敗した場合、[!DNL Workfront Fusion] はシナリオを非アクティブ化します。

  不完全な実行の保存を許可する設定について詳しくは、「シナリオの設定」の [ 不完全な実行の保存を許可する ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions) を参照してください。

### 時間間隔の増加

エラーが発生した場合に試行の間隔を増やすためのアルゴリズムは、指数バックオフと呼ばれます。 時間間隔を増加させるには、次のように設定します。

1. 10 分
1. 1 時間
1. 3 時間
1. 12 時間
1. 24 時間

時間間隔を増やすと、頻繁に実行するシナリオで繰り返し失敗する試行に対する操作が使用されるのを防ぐことができます。

>[!BEGINSHADEBOX]

**例：**

シナリオには、[!DNL Google Sheets] のトリガー[!UICONTROL Watch Rows] が含まれます。 [!DNL Workfront Fusion] が起動したとき、[!DNL Google Sheets] はメンテナンスのため 30 分間使用できません。そのため、新しい行を取得できません。シナリオは停止し、10 分後に再試行します。[!DNL Google Sheets] がまだ使用できないため、[!DNL Workfront Fusion] は新しい行に関する情報をまだ取得できません。次回のシナリオの実行は、1 時間後にスケジュールされます。[!DNL Google Sheets] はこの時点で再び使用可能になり、シナリオは正常に実行されます。

>[!ENDSHADEBOX]

## データエラー

`DataError`

項目が誤ってマッピングされ、サー [!DNL Workfront Fusion] パーティ側またはサードパーティサービス側で実行された検証に合格しない場合に、データエラーが生成されます。

このエラーが発生した場合、シナリオは（モジュールが失敗した場所まで）不完全な実行フォルダーに移動され、問題のトラブルシューティングを行うことができます。 ただし、シナリオは停止せず、スケジュールに従って引き続き実行されます。 データエラーが表示されたときにシナリオの実行を停止するには、シナリオ設定パネルの「順番に処理」オプションを有効にします。

シナリオ設定で「[!UICONTROL Allow storing incomplete executions]」オプションを有効にしていない場合、シナリオの実行はエラーで終了し、ロールバックが実行されます。

## 重複データエラー

`DuplicateDataError`

重複するデータを許可しないサービスに対して、[!DNL Workfront Fusion] が同じバンドルを 2 回挿入しようとすると、重複データエラーが生成されます。このエラーが発生した場合、[!DNL Workfront Fusion] はデータエラーの場合と同じ方法で処理します。

詳しくは、この記事の [ データエラー ](#data-error) を参照してください。


## 無効なアクセストークンエラー

`InvalidAccessTokenError`

サードパーティのサービスで登録されているアカウントに [!DNL Workfront Fusion] がアクセスできない場合に、無効なアクセストークンエラーが生成されます。これは、通常、特定のサービスの管理で [!DNL Workfront Fusion] のアクセス権を取り消したときに、そのサービスを使用するシナリオがスケジュールに従って実行され続ける場合に発生します。

このエラーが発生した場合、シナリオの実行は直ちに停止します。 エラーが発生したモジュール以降のシナリオは、不完全な実行フォルダーに移動します。

## レート制限エラー

`RateLimitError`

特定のサービスによって設定された制限を超えると、レート制限エラーが生成されます。このエラーが発生した場合、[!DNL Workfront Fusion] は接続エラーの場合と同様に処理を進めます。

詳しくは、この記事の [ 接続エラー ](#connection-error) を参照してください。

## 不完全なデータエラー

`IncompleteDataError`

不完全なデータエラーは、トリガーでのみ発生します。トリガーが特定のサービスから必要なデータをダウンロードできなかった場合に、このエラーが生成されます。

シナリオが `IncompleteDataError` で終了した場合、その後の動作は [!UICONTROL Max number of consecutive errors] の設定によって異なります。

詳しくは、「シナリオの設定」の記事の [ 連続エラー数 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors) を参照してください。

>[!BEGINSHADEBOX]

**例：**

シナリオには、ドキュメントを監視する [!DNL Workfront] トリガー[!UICONTROL Watch Record] が設定されています。 このシナリオは、長時間のビデオなどの大きなドキュメントのアップロード中に実行されます。Workfrontへのアップロード中に [!UICONTROL Workfront Fusion] がビデオのダウンロードを試みるので、シナリオは `IncompleteDataError` で終了します。

>[!ENDSHADEBOX]

## 実行時エラー

`RuntimeError`

シナリオの実行中に発生し、これらのエラータイプに該当しないエラーは `RunTimeError` としてレポートされます。

シナリオが `RuntimeError` で終了した場合、その後の動作は [!UICONTROL Max number of consecutive errors] の設定によって異なります。

詳しくは、「シナリオの設定」の記事の [ 連続エラー数 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors) を参照してください。


>[!NOTE]
>
>シナリオがインスタントトリガーで始まり、このエラーが発生した場合、[!UICONTROL Max number of consecutive errors] の設定は無視され、シナリオは直ちに非アクティブ化されます。
>詳細については、「モジュールの概要」の「[ インスタント トリガー](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers)」を参照してください。

## 不整合エラー

`InconsistencyError`

コミットまたはロールバック・フェーズ中にこれらのエラーが発生した場合、シナリオは不整合エラーで終了します。

このエラーがシナリオに表示された場合、シナリオの実行は直ちに停止します。

## 警告

シナリオの実行中に、問題を知らせる警告が表示される場合があります。警告を表示しても、シナリオは正常に完了します。

例えば、許可されている最大ファイルサイズを超え、[!UICONTROL Enable data loss] オプションが無効の場合は、警告が表示されることがあります。

## リソース

マッピングについて詳しくは、[ マッピングの概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md) を参照してください。

不完全な実行について詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

シナリオ設定パネルについて詳しくは、[ シナリオ設定の指定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。

スケジュールについては、[ シナリオのスケジュール ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。

シナリオフェーズについては、[ シナリオの実行、サイクル、フェーズ ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md) を参照してください。

「データの損失を有効にする」オプションについて詳しくは、「シナリオ設定の指定」の [ データの損失を有効にする ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) を参照してください。
