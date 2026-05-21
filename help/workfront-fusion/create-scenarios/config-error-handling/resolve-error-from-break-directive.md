---
title: Break ディレクティブによって処理されたエラーの解決
description: エラーの原因が迅速に解決される可能性がある場合は、エラーが発生したモジュールを再実行すると便利な場合があります。
author: Becky
feature: Workfront Fusion
exl-id: d568942c-2cd5-430c-bdbf-e1496da25b50
TQID: https://experienceleague.adobe.com/2Gw-2VZoILhCB-96exxTRry7S5mgOetJ-lkl-APgypI
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 67%

---

# Break ディレクティブによって処理されたエラーの解決

Break ディレクティブによってエラーが処理されると、不完全な実行フォルダーにレコードが作成されます。 このレコードには、シナリオの実行の状態と共に、前のモジュールのデータが格納されます。 レコードは、エラーが発生したモジュールを参照し、モジュールが入力として受信したデータに関する情報を含みます。 エラーの原因となるデータのバンドルごとに、別々のレコードが作成されます。

詳細については、[不完全な実行を表示して解決する](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)を参照してください。

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

## Break ディレクティブによって発生したエラーを解決する

シナリオを更新し（必要に応じて）1 回実行することで、手動でエラーを解決できます。

シナリオを再実行することで、未完了の実行を自動的に処理するようにシナリオを設定することもできます。 未完了の実行を処理するようにモジュールを設定するには、次の手順に従います。

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 回避策を追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. **フローコントロール** アイコン ![&#x200B; フローコントロール &#x200B;](assets/flow-control-icon.png)をクリックし、**ブレーク**&#x200B;を選択します。
1. Break モジュール内で、[!UICONTROL **自動的に実行を完了する**]&#x200B;オプションを有効にします。
1. **試行回数**&#x200B;フィールドに、モジュールが実行を再試行する最大回数を入力またはマッピングします

   この数は 1 ～ 100 の範囲で指定する必要があります。
1. **試行間隔**&#x200B;フィールドに、各再試行の間隔の分数を入力またはマッピングします。

このオプションを有効にすると、エラーが発生した場合、試行間隔フィールドで指定された時間後に未完了の実行が取得され、元の入力データで実行されます。 この処理は、エラーなしでモジュールの実行が完了するか、指定された試行回数に達するまで繰り返されます。

>[!NOTE]
>
>最初の再試行が失敗した場合、再試行の間隔は再試行のたびに飛躍的に長くなります。


「自動完了」実行オプションが有効になっている場合、ブレークエラーハンドラーの自動再試行が問題を自動的に処理するため、シナリオ実行は「成功」とマークされます。 この場合、ユーザには、実行が失敗したことについてのメールは届きません。

「自動実行を完了」オプションがオフになっている場合、実行は「警告」としてマークされます。

実行が「未完了の実行」の下に保存されている場合は例外があり、一部のエラータイプでは、シナリオの実行の自動再試行はできません。

## リソース

詳しくは、「シナリオ設定の構成」の「[不完全な実行の保存を許可する](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions)」を参照してください。
