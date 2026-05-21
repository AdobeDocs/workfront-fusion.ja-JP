---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: errors
title: スローエラーの回避策の設定
description: 場合によっては、Adobe Workfront Fusion でシナリオの実行を強制的に停止し、その後でロールバックまたはコミットフェーズを実行したり、ルートの処理を停止して必要に応じて不完全な実行をビューのキューに格納し、不完全な実行を解決したりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: 4bf2a6c7-16b2-4545-9adf-be3947a7017d
TQID: https://experienceleague.adobe.com/zdEDHRJhIt8dc4Ql835IDypV-CM3YRT5w41mjGDVpSE
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 43%

---

# `throw` エラー回避策の設定

場合によっては、シナリオ実行の後にロールバックまたはコミット フェーズを強制的に停止したり、ルートの処理を停止して、オプションで不完全な実行のキューに保存したりすることができます。

現在、エラー処理ディレクティブはエラーハンドラールートの範囲外で使用することはできず、Adobe Workfront Fusionには、条件付きでエラーを簡単に生成（スロー）できるモジュールは用意されていません。

次の回避策を使用して、`throw` エラー機能を模倣できます。

不完全な実行について詳しくは、[Adobe Workfront Fusion での不完全な実行の表示と解決](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)を参照してください。

エラー処理ディレクティブについて詳しくは、[Adobe Workfront Fusionでのエラー処理に関するディレクティブ &#x200B;](/help/workfront-fusion/references/errors/directives-for-error-handling.md)を参照してください。

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

## `throw`の回避策

条件付きでエラーをスローするには、モジュールを設定して、その操作中に意図的に失敗するようにします。 1つの可能性として、[!UICONTROL JSON] > [!UICONTROL JSON]を解析モジュールを使用し、オプションでエラーをスローするように設定します（この場合は`BundleValidationError`）。

![JSON エラー](assets/json-parse-json.png)

次に、エラー処理ルートにエラー処理ディレクティブのいずれかを添付できます。

* **ロールバック**: シナリオの実行を強制的に停止し、ロールバック フェーズを実行します。
* **コミット**: シナリオ実行を強制的に停止し、コミット フェーズを実行します。
* **無視**：ルートの処理を停止します。
* **Break**: ルートの処理を停止し、不完全な実行フォルダーのキューに保存します。

[!DNL Rollback] ディレクティブの使用例を以下に示します。

![&#x200B; ロールバック ディレクティブ &#x200B;](assets/rollback-directive.png)
