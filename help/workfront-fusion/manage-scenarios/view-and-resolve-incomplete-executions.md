---
title: 不完全な実行の表示と解決
description: '[!UICONTROL Incomplete executions] フォルダーには、エラーが原因で正常に完了しなかったシナリオ実行が格納されます。 保存された未完了の実行は、手動または自動で解決できます。'
author: Becky
feature: Workfront Fusion
exl-id: 8891b4d7-a39a-4f14-8521-8c2ca186ca6e
source-git-commit: 3d06958b6f706f4f974230853fb6553232656fd3
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 57%

---

# 不完全な実行の表示と解決

[!UICONTROL Incomplete executions] フォルダーには、エラーが原因で正常に完了しなかったシナリオ実行が格納されます。 保存された未完了の実行は、手動または自動で解決できます。

>[!NOTE]
>
>デフォルトでは、未完了の実行の保存は無効になっています。有効にするには、シナリオの詳細設定で「[!UICONTROL Allow storing incomplete executions]」オプションを有効にします。
>
>シナリオ設定について詳しくは、[ シナリオ設定の指定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。

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

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについては、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 未完了の実行を表示

モジュールの処理中にエラーが発生した場合、新しい未完了の実行が「未完了の実行」フォルダーに追加されます。未完了の実行にはそれぞれ、シナリオのブループリントと、失敗したモジュールにマッピングできるすべてのバンドルが含まれます。不完全な実行のリストは、シナリオの詳細ページの「[!UICONTROL Incomplete Executions]」タブをクリックすると開くことができます。

<!--

![](assets/incomplete-executions-tab-350x102.png)

-->

詳しくは、[ 不完全な実行につながるエラー ](#errors-resulting-into-incomplete-executions) を参照してください。

>[!NOTE]
>
>組織ごとの未解決の未完了の実行フォルダーに対する現在のサイズ制限は 500 MB です。組織がこの制限を超えると、次のエラーが表示される場合があります。
>
>`"There is NOT ENOUGH SPACE to add a bundle to the IEQ. The reason is: Too many incomplete executions."`
>
>詳しくは、「シナリオの設定」の [ データ損失の有効化 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) を参照してください。


## 「不完全な実行」タブからの不完全な実行の解決

新しい未完了の実行が保存された場合、次のように解決できます。

1. 該当するシナリオを開きます。
1. 「**[!UICONTROL Incomplete Executions]**」タブをクリックします。
1. 解決する不完全な実行を見つけて、「解 **[!UICONTROL Details]**」をクリックします。


## 「履歴」タブからの不完全な実行の解決

不完全な実行を解決する前に、すべてのモジュールの操作のログを確認する場合は、[!UICONTROL History] フォルダーで不完全な実行を解決できます。

1. 該当するシナリオを開きます。
1. 「**[!UICONTROL History]**」タブをクリックします。
1. シナリオの失敗した実行を見つけて、「**[!UICONTROL Details]**」をクリックします。
1. モジュールのログを開くと、モジュールのすべての操作が表示されます。
1. 失敗した操作を見つけて、「**[!UICONTROL Resolve]**」をクリックします。

   ![](assets/resolve-btn-350x188.png)

## 未完了の実行に関連するオプション

[!UICONTROL Scenario settings] パネルの次のオプションでは、不完全な実行を保存するかどうかと、どのように保存するかを決定します。

* 未完了の実行の保存を許可
* 順次処理
* データ損失を有効にする

これらのオプションについて詳しくは、[ シナリオ設定の指定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md) を参照してください。

## 未完了の実行になるエラー

未完了の実行が保存される原因となるエラーには、いくつかのカテゴリがあります。次のものが含まれます。

* 不完全なデータや誤ったデータから発生する検証エラー。主に、モジュールを通過するすべてのデータを正常に処理するために予期される項目が欠落していることが原因です。
* 最終的な宛先が使用できなかったことから発生するエラー。一時的または長期的な接続障害（メールまたはリモート FTP サーバーへの接続中など）が原因です。

シナリオの最初のモジュールでエラーが発生した場合、実行は直ちに停止し、未完了の実行は保存されません。

他のモジュールでエラーが発生し、エラーハンドラールートが添付されていない場合は、次のいずれかが発生します。

* エラータイプが `ConnectionError`、`RateLimitError`、`OutOfSpaceError`、または `ModuleTimeoutError` の場合、自動再試行付きの未完了の実行レコードが保存されます。
* エラータイプが `DataError`、`InvalidConfigurationError`、`InvalidAccessTokenError`、`UnexpectedError`、`MaxFileSizeExceededError`、または `MaxResultsExceededError` の場合、自動再試行なしの未完了の実行レコードが保存されます。
* エラータイプが上記以外の場合、実行は失敗します。
