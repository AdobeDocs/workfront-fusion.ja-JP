---
title: 再試行エラー処理の回避策を設定
description: 失敗の理由がすぐに解決される可能性がある場合は、失敗したモジュールを再実行すると便利な場合があります。
author: Becky
feature: Workfront Fusion
exl-id: 08e19a1a-7ca9-4c79-a165-f200048a5cda
source-git-commit: 0668441df8405610488e3e33658635e4cc7db270
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 7%

---

# エラー処理 `retry` 回避策を設定

失敗の理由がすぐに解決される可能性がある場合は、失敗したモジュールを再実行すると便利な場合があります。

Adobe Workfront Fusion では現在、`retry` のエラー処理ディレクティブを提供していませんが、`retry` の機能を模倣するために、2 つの回避策を使用できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront プランを選択する：組織がAdobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## [!UICONTROL Retry] エラー処理ディレクティブの回避策

Workfront Fusion は現在、`retry` のエラー処理ディレクティブを提供していません。 次のいずれかの回避策を使用して、再試行機能を模倣します。

手順については、[ エラー処理のディレクティブ ](/help/workfront-fusion/references/errors/directives-for-error-handling.md) を参照してください。

* [一時停止ディレクティブの使用](#use-the-break-directive)
* [リピーターの使用モジュール](#use-the-repeater-module)

### 一時停止ディレクティブの使用

一時停止ディレクティブが実行されると、シナリオの実行状態が不完全な実行のキューに保存されます。 この場合、不完全な実行を手動で解決できます。

手順については、[Break ディレクティブで処理されるエラーの解決 ](/help/workfront-fusion/create-scenarios/config-error-handling/resolve-error-from-break-directive.md) を参照してください

不完全な実行の解決手順については、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

#### 欠点

* 最小再試行間隔は 1 分です。
* モジュールで複数のバンドルが処理され、バンドルの処理が失敗した場合、部分実行（エラーの原因となったバンドルのみ）が不完全な実行フォルダーに移動され、[!UICONTROL Break] のディレクティブ設定に従って再試行がスケジュールされます。 ただし、現在の実行は続行され、モジュールは後続のバンドルの処理を続行します。

  不完全な実行フォルダーに保存された実行が正常に解決されるまでシナリオが再び実行されないようにするには、[!UICONTROL Scenario settings] で「[!UICONTROL Sequential processing]」オプションを有効にします。

不完全な実行について詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

### リピーターの使用モジュール

リピーターモジュールの回避策は、より複雑ですが、カスタマイズしやすくなっています。

#### エラーハンドラールートの設定

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. 回避策を追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. **フロー制御** アイコン ![ フロー制御 ](assets/flow-control-icon.png) をクリックし、「**リピータ**」を選択します。
1. リピーターモジュールで、「**[!UICONTROL Repeats]**」フィールドを、シナリオを再試行する最大回数に設定します。
1. 問題が発生する可能性があるモジュールを **[!UICONTROL Repeater]** のモジュールの後に取り付けます。
1. 失敗する可能性があるモジュールにエラーハンドラールートを添付します。

   手順については、「[ エラー処理の追加 ](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) を参照してください。
1. **[!UICONTROL Tools]/[!UICONTROL Sleep]** モジュールをエラーハンドラールートに追加し、その「**[!UICONTROL Delay]**」フィールドを再試行間の秒数に設定します。

1. **[!UICONTROL Tools]/[!UICONTROL Sleep]** モジュールの後に **[!UICONTROL Ignore]** ディレクティブを追加します。
1. [ デフォルトルートの設定 ](#configure-the-default-route) を続行します。

#### デフォルトルートの設定

1. **[!UICONTROL Tools]/[!UICONTROL Set variable]** モジュールを、失敗する可能性があるモジュールの後の別の（エラーハンドラー以外の）ルートに追加し、モジュールの結果を `Result` などの名前の変数に格納するように設定します。

1. **[!UICONTROL Tools]/[!UICONTROL Set variable]** の後に **[!UICONTROL Array aggregator]** モジュールを追加し、その「Source モジュール」フィールドで **[!DNL Repeater]** モジュールを選択します。

1. **[!UICONTROL Tools]/[!UICONTROL Get variable]** モジュールを **[!UICONTROL Array aggregator]** モジュールの後に追加し、`Result` 変数の値をそれにマッピングします。

1. **[!UICONTROL Tools]/[!UICONTROL Get variable]** モジュールを **[!UICONTROL Repeater]** モジュールと失敗する可能性のあるモジュールの間に挿入し、`Result` 変数の値をそれにマッピングします。

1. この **[!UICONTROL Tools]/[!UICONTROL Get variable]** モジュールと失敗する可能性のあるモジュールの間にフィルターを挿入し、`Result` 変数が存在しない場合にのみ続行します。

>[!BEGINSHADEBOX]

**例：**

このサンプルシナリオでは、[!UICONTROL HTTP]/[!UICONTROL Make a request] モジュールは失敗する可能性のあるモジュールを表します。

![](assets/http-make-request.png)

>[!ENDSHADEBOX]

失敗する可能性があるモジュールの結果が複雑すぎて単純な変数に格納できない場合は、データストアを使用して結果を格納および取得できます。 データストアにはレコードが 1 つだけ含まれます。レコードのキーは、例えば `Result` などです。

データストアについて詳しくは、[ データストア ](/help/workfront-fusion/create-scenarios/map-data/data-stores.md) を参照してください。

#### 欠点

* この回避策は、より複雑です。
* この回避策では、さらに多くの操作を使用します。

## リソース

* リピータモジュールとブレイクディレクティブについて詳しくは、[ フロー制御 ](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/flow-control.md) を参照してください。
* Get 変数モジュールについて詳しくは、「[ ツール ](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/tools-modules.md)」を参照してください。
