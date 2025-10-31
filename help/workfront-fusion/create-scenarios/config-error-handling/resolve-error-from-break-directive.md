---
title: 一時停止ディレクティブで処理されたエラーを解決します
description: 失敗の理由がすぐに解決される可能性がある場合は、失敗したモジュールを再実行すると便利な場合があります。
author: Becky
feature: Workfront Fusion
exl-id: d568942c-2cd5-430c-bdbf-e1496da25b50
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 49%

---

# 一時停止ディレクティブで処理されたエラーを解決します

エラーが一時停止ディレクティブで処理されると、レコードが不完全な実行フォルダーに作成されます。 このレコードには、シナリオの実行の状態と共に、前のモジュールのデータが格納されます。レコードは、エラーが発生したモジュールを参照し、モジュールが入力として受信したデータに関する情報を含みます。 エラーの原因となるデータのバンドルごとに、別々のレコードが作成されます。

詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++

## Break ディレクティブによって発生したエラーを解決する

シナリオを更新し（必要に応じて）1 回実行することで、手動でエラーを解決できます。

シナリオを再実行することで、未完了の実行を自動的に処理するようにシナリオを設定することもできます。未完了の実行を処理するようにモジュールを設定するには、次の手順に従います。

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 回避策を追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. **フロー制御** アイコン ![ フロー制御 ](assets/flow-control-icon.png) をクリックし、「**中断**」を選択します。
1. Break モジュール内で、[!UICONTROL **自動的に実行を完了する**]&#x200B;オプションを有効にします。
1. **試行回数**&#x200B;フィールドに、モジュールが実行を再試行する最大回数を入力またはマッピングします

   この数は 1 ～ 100 の範囲で指定する必要があります。
1. **試行間隔**&#x200B;フィールドに、各再試行の間隔の分数を入力またはマッピングします。

このオプションを有効にすると、エラーが発生した場合、]試行間隔[!UICONTROL フィールドで指定された時間後に未完了の実行が回収され、元の入力データで実行されます。この処理は、エラーなしでモジュールの実行が完了するか、指定された試行回数に達するまで繰り返されます。

>[!NOTE]
>
>最初の再試行が失敗した場合、再試行の間隔は再試行のたびに飛躍的に長くなります。


「実行を自動的に完了」オプションが有効な場合、シナリオの実行は「成功」とマークされます。これは、中断エラーハンドラーの自動再試行が問題を自動的に処理しているからです。 この場合、ユーザには、実行が失敗したことについてのメールは届きません。

「実行を自動的に完了」オプションがオフの場合、実行は「警告」とマークされます。

実行が「未完了の実行」の下に保存されている場合は例外があり、一部のエラータイプでは、シナリオの実行の自動再試行はできません。

## リソース

詳しくは、「シナリオの設定」の [ 不完全な実行の保存を許可する ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions) を参照してください。
