---
content-type: reference
title: エラー処理のディレクティブ
description: この記事では、Adobe Workfront Fusion のシナリオでエラー処理に使用できるディレクティブについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: d7b0141f-d99d-4ab7-a60f-ed552a76f05d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 32%

---

# エラー処理のディレクティブ

エラー処理ディレクティブを使用すると、シナリオでエラーが発生したときの動作を選択できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> 新規：標準<p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] ライセンス</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>


ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、Workfront 管理者にお問い合わせください。

Adobe Workfront Fusion のライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。Adobe Workfront Fusion

+++

## エラー処理のディレクティブ

Workfront Fusion では、次のエラー処理ディレクティブを使用できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>ロールバック</p> <p> <img src="assets/rollback.png"> </p> </td> 
   <td> <ul><li><p>シナリオの実行は直ちに停止します。</li><li>ロールバックフェーズは、すべてのモジュールで開始され、すべてのモジュールを初期状態に戻します。 </li><li>後続のモジュールは処理されません。</p></li><li> <p>ほとんどの場合、シナリオは、「シナリオ設定」で指定した連続エラー数の後で非アクティブ化されます。 詳しくは、<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors" class="MCXref xref">連続エラー回数</a>を参照してください。</p> </li><li><p>シナリオの実行ステータスは「エラー」とマークされます。</p></li></ul> <p><b> メモ </b>：これは、モジュールにエラーハンドラールートが添付されておらず、シナリオ設定 <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions" class="MCXref xref"> で [ 不完全な実行の保存を許可 </a> 不完全な実行の保存を許可 ] 設定がオフの場合のデフォルトの動作です。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>コミット</p> <p> <img src="assets/commit.png"> </p> </td> 
   <td> <ul><li><p>シナリオの実行は直ちに停止します。</li><li>すべてのモジュールでコミットフェーズが開始されます。 </li><li>後続のモジュールは処理されません。</p></li><li> <p>未処理のバンドルはすべて無視されます。</p> </li><li><p>シナリオの実行ステータスは「成功」とマークされます。 </p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>再開</p> <p> <img src="assets/resume.png"> </p> </td> 
   <td> <ul><li><p>エラーが発生したモジュールに代替出力が指定され、提供されます。</p> </li><li><p>後続のモジュールが処理されます。</p></li><li> <p>シナリオの実行ステータスは「成功」とマークされます。</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>無視</p> <p> <img src="assets/ignore.png"> </p> </td> 
   <td><ul><li> <p>エラーは無視されます。</li><li> 後続のモジュールは処理されません。</p> </li><li><p>未処理のバンドルがある場合、シナリオの実行は通常どおり続行されます。</p> </li><li><p>シナリオの実行ステータスは「成功」とマークされます。</p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>一時停止</p> <p> <img src="assets/break.png"> </p> </td> 
   <td><ul><li> <p>シナリオの実行状態は、不完全な実行のキューに保存されます。このキューでは、エラーを手動で解決できます。 詳しくは、<a href="/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md" class="MCXref xref"> 不完全な実行の表示と解決 </a> を参照してください。</p> <p>ただし、いくつかの例外があります。詳しくは、「シナリオの設定 <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow" class="MCXref xref"> の記事の「不完全な実行の保存を許可する </a> を参照してください </a>。</p></li><li> <p>後続のモジュールは処理されません。</p></li><li> <p>未処理のバンドルがある場合、シナリオの実行は通常どおり続行されます。</p> </li><li><p>「[!UICONTROL Automatically complete execution]」オプションが無効になっている場合、シナリオの実行ステータスは「警告」とマークされます。</p></li></ul> <p>詳細については、この記事の <a href="#break" class="MCXref xref">[!UICONTROL Break]</a> セクションを参照してください</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>再試行</p> <p> <img src="assets/retry.png"> </p> </td> 
   <td> <p>場合によっては、失敗の理由が時間の経過と共に過ぎる可能性がある場合に、失敗したモジュールを再実行すると便利です。</p> <p>現在、Workfront Fusion では Retry ディレクティブは提供されていませんが、機能を模倣するために、いくつかの回避策を使用できます。詳しくは、「<a href="/help/workfront-fusion/create-scenarios/config-error-handling/retry.md" class="MCXref xref"> エラー処理の再試行 </a>」を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* エラー処理命令は、エラー処理ルートの外部では使用できません。
>* Workfront Fusion では現在、条件付きでエラーを簡単に発生させるスローモジュールは提供していませんが、回避策を採用してその機能を模倣することができます。
>
>  詳しくは、「[&#x200B; エラー回避策 `throw` 設定 &#x200B;](/help/workfront-fusion/create-scenarios/config-error-handling/throw.md) を参照してください。

## リソース

* ロールバックとロールバック フェーズについては、「シナリオの実行、サイクル、およびフェーズ」の記事の [&#x200B; ロールバック &#x200B;](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) を参照してください。
* コミットフェーズについては、「シナリオの実行、サイクル、フェーズ」の記事の [&#x200B; コミット &#x200B;](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#commit) を参照してください。
