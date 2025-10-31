---
title: 不完全な実行の表示と解決
description: 「[!UICONTROL 未完了の実行]」フォルダーには、エラーが原因で正常に終了されなかったシナリオの実行が保存されます。保存された未完了の実行は、手動または自動で解決できます。
author: Becky
feature: Workfront Fusion
exl-id: 8891b4d7-a39a-4f14-8521-8c2ca186ca6e
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 65%

---

# 不完全な実行の表示と解決

「[!UICONTROL 未完了の実行]」フォルダーには、エラーが原因で正常に終了されなかったシナリオの実行が保存されます。保存された未完了の実行は、手動または自動で解決できます。

>[!NOTE]
>
>デフォルトでは、未完了の実行の保存は無効になっています。有効にするには、シナリオの詳細設定で「[!UICONTROL 未完了の実行の保存を許可]」オプションを有効にします。
>
>シナリオ設定について詳しくは、[&#x200B; シナリオ設定の指定 &#x200B;](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。

## 記事全体を対象としたハイライト表示されたプレビュー {#highlighted-preview-article-level}

<span class="preview">このページの情報は、まだ一般に提供されていない機能を指します。サンドボックスプレビュー環境でのみ使用できます。</span>##不完全な実行の表示

モジュールの処理中にエラーが発生した場合、新しい未完了の実行が「未完了の実行」フォルダーに追加されます。未完了の実行にはそれぞれ、シナリオのブループリントと、失敗したモジュールにマッピングできるすべてのバンドルが含まれます。不完全な実行のリストを開くには、シナリオの詳細ページの「[!UICONTROL &#x200B; 不完全な実行 &#x200B;]」タブをクリックします。

<!--

![Incomplete executions tab](assets/incomplete-executions-tab-350x102.png)

-->

詳しくは、[&#x200B; 不完全な実行につながるエラー &#x200B;](#errors-resulting-into-incomplete-executions) を参照してください。

>[!NOTE]
>
>シナリオごとの未解決の不完全な実行フォルダーの現在のサイズ制限は 10 MB です。 シナリオがこの制限を超えると、次のエラーが発生する場合があります。
>
>`DLQ limit per scenario has been exceeded`
>
>未解決の不完全な実行はすべて、チームが合計 500 MB に制限されます。
>
>詳しくは、「シナリオの設定」の [&#x200B; データ損失の有効化 &#x200B;](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) を参照してください。


## 「不完全な実行」タブからの不完全な実行の解決

新しい未完了の実行が保存された場合、次のように解決できます。

1. 該当するシナリオを開きます。
1. 「**[!UICONTROL 未完了の実行]**」タブをクリックします。
1. 解決したい不完全な実行を見つけて、「**[!UICONTROL 詳細]**」をクリックします。
1. モジュールのログを開くと、モジュールのすべての操作が表示されます。
1. 失敗した操作を見つけ、「**[!UICONTROL 解決]**」をクリックします。

   ![&#x200B; 解決ボタン &#x200B;](assets/resolve-btn-350x188.png)



## 「履歴」タブからの不完全な実行の解決

未完了の実行を解決しようとする前に、すべてのモジュールの操作のログを確認したい場合は、「[!UICONTROL 履歴]」フォルダーから未完了の実行を解決できます。

1. 該当するシナリオを開きます。
1. 「**[!UICONTROL 履歴]**」タブをクリックします。
1. シナリオの失敗した実行を見つけ、「**[!UICONTROL 詳細]**」をクリックします。
1. モジュールのログを開くと、モジュールのすべての操作が表示されます。
1. 失敗した操作を見つけ、「**[!UICONTROL 解決]**」をクリックします。

   ![&#x200B; 解決ボタン &#x200B;](assets/resolve-btn-350x188.png)

## 未完了の実行に関連するオプション

[!UICONTROL シナリオ設定]パネルの次のオプションは、未完了の実行を保存するかどうかと、その方法を決定します。

* 未完了の実行の保存を許可
* 順次処理
* データ損失を有効にする

これらのオプションについて詳しくは、[&#x200B; シナリオ設定の指定 &#x200B;](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。

## 未完了の実行になるエラー

未完了の実行が保存される原因となるエラーには、いくつかのカテゴリがあります。次のものが含まれます。

* 不完全なデータや誤ったデータから発生する検証エラー。主に、モジュールを通過するすべてのデータを正常に処理するために予期される項目が欠落していることが原因です。
* 最終的な宛先が使用できなかったことから発生するエラー。一時的または長期的な接続障害（メールまたはリモート FTP サーバーへの接続中など）が原因です。

シナリオの最初のモジュールでエラーが発生した場合、実行は直ちに停止し、未完了の実行は保存されません。

他のモジュールでエラーが発生し、エラーハンドラールートが添付されていない場合は、次のいずれかが発生します。

* 自動再試行付きの不完全な実行レコードは、次のエラータイプで保存されます。

   * `ConnectionError`
   * `RateLimitError`
   * `OutOfSpaceError`
   * `ModuleTimeoutError`

* 自動再試行を使用しない不完全な実行レコードは、次のエラータイプで保存されます。

   * `DataError`
   * `InvalidConfigurationError`
   * `InvalidAccessTokenError`
   * `UnexpectedError`
   * `MaxFileSizeExceededError`
   * `MaxResultsExceededError`

* エラータイプが上記以外の場合、実行は失敗します。
