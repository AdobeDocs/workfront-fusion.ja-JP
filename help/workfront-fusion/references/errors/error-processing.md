---
content-type: reference
title: エラータイプ
description: シナリオ実行中にエラーが発生する場合があります。 この問題は通常、サービスへの接続に失敗したためにサービスが使用できない場合や、検証に失敗した場合に発生します。 この記事では、発生する可能性のある一般的なエラーについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: abf5f844-d13b-416e-a8b8-2d4ee1786262
TQID: https://experienceleague.adobe.com/t5chLg0xd7CSUyitvH-NCc-YUbMAEXu111sU497Uspc
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: d968a1bc-9a90-4926-a531-bcf272c32aad
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1214
ht-degree: 35%

---

# エラータイプ

シナリオ実行中にエラーが発生する場合があります。 これは通常、サービスへの接続に失敗してサービスが利用できない場合、または検証が失敗した場合に発生します。

Adobe Workfront Fusionでは、いくつかの基本的なエラータイプが区別されます。 エラーのタイプによって、Fusion シナリオの次のアクションが決まります。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意の Adobe Workfront Workflow パッケージと任意の Adobe Workfront Automation および Integration パッケージ</p><p>Workfront Ultimate</p><p>Workfront Fusion を追加購入した Workfront Prime および Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>Work またはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 接続エラー

`ConnectionError`

接続エラーは、最も一般的なエラーの1つです。 これらは通常、過負荷、メンテナンス、または停止など、さまざまな理由でサードパーティサービスが利用できないことが原因です。 このエラーのデフォルトの処理は、どのモジュールでエラーが発生したかによって異なります。

* 最初のモジュールでエラーが発生した場合、シナリオの実行は警告メッセージとともに終了します。 その後、Workfront Fusionは、時間の間隔を増やしながらシナリオを繰り返し実行しようとします。 すべての試行が失敗した場合、Workfront Fusionはシナリオを無効にします。
* 接続エラーが最初のモジュール以外のモジュールで発生した場合、後続の手順は、シナリオの詳細設定の「不完全な実行の保存を許可」オプションに依存します。

   * このオプションが有効になっている場合、シナリオの実行は[!UICONTROL 不完全な実行] フォルダーに移動されます。このフォルダーでは、Workfront Fusionが繰り返し時間を増やしながらシナリオを再実行しようとします。 すべての試行が失敗した場合、不完全な実行フォルダーに実行が残り、ユーザーが手動で解決するのを待ちます。

     不完全な実行について詳しくは、[不完全な実行の表示と解決](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)を参照してください。
   * このオプションが無効になっている場合、シナリオの実行はエラーで終了し、ロールバックフェーズに移ります。 その後、Workfront Fusionは、時間の間隔を増やしながらシナリオを繰り返し実行しようとします。 すべての試行が失敗した場合、Workfront Fusionはシナリオを無効にします。

  不完全な実行の保存を許可する設定について詳しくは、「シナリオ設定の構成」の「[不完全な実行の保存を許可する](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions)」を参照してください。

### 時間間隔の増加

エラーが発生した場合の試行間隔を長くするためのアルゴリズムは、指数的バックオフと呼ばれます。 時間間隔を増加させるには、次のように設定します。

1. 10 分
1. 1 時間
1. 3 時間
1. 12 時間
1. 24 時間

時間間隔を長くすると、頻繁に実行されるシナリオが、繰り返し失敗する試行に対して操作を使用するのを防ぐことができます。

>[!BEGINSHADEBOX]

**例：**

シナリオには、[!DNL Google Sheets] トリガーの[!UICONTROL 行を監視]が含まれています。 Workfront Fusionがシナリオを開始する際のメンテナンスにより、[!DNL Google Sheets]は30分間利用できないため、新しい行を取得できません。 シナリオは停止し、10 分後に再試行します。 [!DNL Google Sheets]はまだ利用できないため、Workfront Fusionは新しい行に関する情報を取得できません。 次回のシナリオの実行は、1 時間後にスケジュールされます。 [!DNL Google Sheets] はこの時点で再び使用可能になり、シナリオは正常に実行されます。

>[!ENDSHADEBOX]

## データエラー

`DataError`

アイテムが誤ってマッピングされ、Workfront Fusion側またはサードパーティサービス側で実行された検証に合格しない場合、データエラーが生成されます。

このエラーが発生した場合、モジュールが失敗した場所までのシナリオは、不完全な実行フォルダーに移動され、問題のトラブルシューティングを行うことができます。 ただし、シナリオは停止せず、そのスケジュールに従って実行し続けます。 データエラーが表示されたときにシナリオの実行を停止するには、シナリオ設定パネルの「順番に処理」オプションを有効にします。

シナリオ設定で「[!UICONTROL 不完全な実行を保存することを許可する]」オプションを有効にしていない場合、シナリオの実行はエラーで終了し、ロールバックが実行されます。

## 重複データエラー

`DuplicateDataError`

Workfront Fusionが、重複データを許可しないサービスに同じバンドルを2回挿入しようとすると、重複データエラーが生成されます。 このエラーが発生した場合、Workfront Fusionはデータエラーと同じように処理を進めます。

詳しくは、この記事の「[&#x200B; データエラー](#data-error)」を参照してください。


## 無効なアクセストークンエラー

`InvalidAccessTokenError`

Workfront Fusionがサードパーティサービスで登録されたアカウントにアクセスできない場合、無効なアクセストークンのエラーが発生します。 これは通常、特定のサービスの管理でWorkfront Fusionのアクセス権を取り消すと発生しますが、そのサービスを使用するシナリオはスケジュールに従って実行され続けます。

このエラーが発生すると、シナリオの実行はすぐに停止します。 エラーが発生したモジュールから始まるシナリオの残りの部分は、不完全な実行フォルダーに移動します。

## レート制限エラー

`RateLimitError`

特定のサービスによって設定された制限を超えると、レート制限エラーが生成されます。 このエラーが発生した場合、Workfront FusionはConnection Errorと同じように処理を進めます。

詳しくは、この記事の「[接続エラー](#connection-error)」を参照してください。

## 不完全なデータエラー

`IncompleteDataError`

不完全なデータエラーは、トリガーでのみ発生します。 トリガーが特定のサービスから必要なデータをダウンロードできなかった場合に、このエラーが生成されます。

シナリオが `IncompleteDataError` で終了した場合、それ以降の動作は「[!UICONTROL 連続エラーの最大数]」の設定によって変わります。

詳しくは、「シナリオ設定の構成」の「[連続エラーの数](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors)」を参照してください。

>[!BEGINSHADEBOX]

**例：**

シナリオでは、ドキュメントを監視するように設定されたWorkfront トリガー [!UICONTROL 監視レコード &#x200B;]があります。 このシナリオは、長時間のビデオなどの大きなドキュメントのアップロード中に実行されます。 [!UICONTROL Workfront Fusion] は、Workfront へのアップロードが続いている間にビデオをダウンロードしようとするため、シナリオは `IncompleteDataError` で終了します。

>[!ENDSHADEBOX]

## ランタイムエラー

`RuntimeError`

シナリオの実行中に発生し、これらのエラータイプのいずれでもないエラーは、`RunTimeError`として報告されます。

シナリオが`RuntimeError`で終了した場合、その後の動作は[!UICONTROL 連続エラーの最大数]設定に依存します。

詳しくは、「シナリオ設定の構成」の「[連続エラーの数](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors)」を参照してください。


>[!NOTE]
>
>シナリオがインスタントトリガーで始まり、このエラーが発生した場合、[!UICONTROL 連続エラーの最大数]の設定は無視され、シナリオはすぐにディアクティベートされます。
>詳しくは、「トリガーの概要」の「[&#x200B; インスタント モジュール &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers)」を参照してください。

## 不整合エラー

`InconsistencyError`

コミット フェーズまたはロールバック フェーズでこれらのエラーのいずれかが発生した場合、シナリオは非一貫性エラーで終了します。

このエラーがシナリオに表示された場合、シナリオの実行は直ちに停止します。

## 警告

シナリオの実行中に、問題を知らせる警告が表示される場合があります。 警告を表示しても、シナリオが正常に完了することはありません。

例えば、許可される最大ファイルサイズを超え、[!UICONTROL &#x200B; データ損失を有効にする] オプションが無効になっている場合、警告が表示される場合があります。

## リソース

マッピングについて詳しくは、[&#x200B; マッピングの概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md)を参照してください。

不完全な実行について詳しくは、[不完全な実行の表示と解決](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)を参照してください。

シナリオ設定パネルについて詳しくは、[&#x200B; シナリオ設定の設定](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md)を参照してください。

スケジュールについて詳しくは、[&#x200B; シナリオのスケジュール &#x200B;](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)を参照してください。

シナリオフェーズについて詳しくは、[&#x200B; シナリオ実行、サイクルおよびフェーズ &#x200B;](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md)を参照してください。

データ損失を有効にするオプションについて詳しくは、「シナリオ設定の構成」の「[&#x200B; データ損失を有効にする](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss)」を参照してください。
