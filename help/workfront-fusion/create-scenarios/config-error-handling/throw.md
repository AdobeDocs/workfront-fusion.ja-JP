---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: errors
title: スローエラーの回避策を設定
description: 場合によっては、Adobe Workfront Fusion でシナリオの実行を強制的に停止し、その後でロールバックまたはコミットフェーズを実行したり、ルートの処理を停止して必要に応じて不完全な実行をビューのキューに格納し、不完全な実行を解決したりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: 4bf2a6c7-16b2-4545-9adf-be3947a7017d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 25%

---

# エラー回避策 `throw` 設定

場合によっては、シナリオの実行を強制的に停止し、その後にロールバックフェーズまたはコミットフェーズを実行するか、ルートの処理を停止し、必要に応じて不完全な実行のキューに格納することができます。

現在、エラー処理ディレクティブはエラーハンドラールートの範囲外では使用できず、Adobe Workfront Fusion では条件付きでエラーを簡単に発生させる（スローする）モジュールは提供されていません。

次の回避策を使用して、エラー機能 `throw` 模倣できます。

不完全な実行について詳しくは、[Adobe Workfront Fusion での不完全な実行の表示と解決](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)を参照してください。

エラー処理ディレクティブについて詳しくは、[Adobe Workfront Fusion のエラー処理用のディレクティブ &#x200B;](/help/workfront-fusion/references/errors/directives-for-error-handling.md) を参照してください。

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
   <p>現在：Workfront Fusion ライセンス要件なし</p>
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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## `throw` の回避策

条件付きでエラーをスローするには、操作中に意図的に失敗するようにモジュールを設定します。 オプションでエラーをスローするように設定された [!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] モジュールを使用する可能性があります（この場合は `BundleValidationError`）。

![JSON エラー &#x200B;](assets/json-parse-json.png)

その後、エラー処理ディレクティブの 1 つをエラー処理ルートに添付できます。

* **ロールバック**：シナリオ実行を強制的に実行し、ロールバックフェーズを停止して実行します。
* **コミット**：シナリオ実行を強制的に停止し、コミットフェーズを実行します。
* **無視**：ルートの処理を停止します。
* **Break**：ルートの処理を停止し、不完全な実行のキューフォルダーに保存します。

[!DNL Rollback] ディレクティブの使用例を以下に示します。

![&#x200B; ロールバックディレクティブ &#x200B;](assets/rollback-directive.png)
