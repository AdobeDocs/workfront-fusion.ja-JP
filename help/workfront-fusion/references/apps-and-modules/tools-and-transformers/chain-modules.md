---
title: チェーンモジュール
description: これらのモジュールを使用することで、シナリオを連鎖させ、一方を他方に呼び出すことができます。
author: Becky
feature: Workfront Fusion
exl-id: 21429f94-fe4c-4ccc-a8c0-d7573657fecc
TQID: https://experienceleague.adobe.com/AlHUrliXikCc3OVHiBTjLNQFndCf5qLzOLuBvnDTUfA
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 625
ht-degree: 15%

---

# チェーンモジュール

>[!NOTE]
>
>この機能は現在Betaにあります。

チェーンモジュールを使用すると、1つのシナリオを別のシナリオに接続できます。

<!--This article will be about the specific module configuration-->

連鎖シナリオの計画の手順については、[複数のシナリオを連鎖させる](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)を参照してください。


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



## チェーンモジュールとそのフィールド

### トリガー

#### 親からのデータの受信

このモジュールは、子シナリオのトリガーモジュールであり、親シナリオの子シナリオモジュールの呼び出しによってトリガーされます。 親シナリオからデータを受け取り、子シナリオで処理できます。

親モジュールからデータを受信を設定するには：

1. 既存のデータ構造を使用するには、データ構造フィールドで、シナリオの入力データに使用するデータ構造を選択します。

   または

   シナリオの入力データとして使用する新しいデータ構造を作成するには、「データ構造」フィールドの横にある「**追加**」をクリックし、データ構造を作成します。

   データ構造の作成手順については、[ データ構造](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)を参照してください。

1. 「**OK**」をクリックして、モジュールを保存します。

### アクション

#### 子シナリオの呼び出し

このモジュールは親シナリオにあります。 フィールドには、子シナリオの「親モジュールからデータを受信」モジュールで設定されたデータ構造が反映されます。

>[!NOTE]
>
>* 既存の子シナリオを選択するか、このモジュールを使用して新しい子シナリオを作成できます。
>* 子シナリオを作成する際に、データ構造を作成できます。

子シナリオモジュールの呼び出しを設定するには

1. シナリオに「子シナリオモジュールを呼び出す」モジュールを追加します。
1. 既存の子シナリオを使用するには、「チェーン」フィールドで、呼び出す子シナリオを選択します。

   または

   新しい子シナリオを作成するには、「チェーン」フィールドの横にある「追加」をクリックします。 子シナリオは別のウィンドウに表示され、親モジュールからのデータの受信と親モジュールからの応答の返しが配置されます。

   子シナリオのトリガーモジュールで設定されたフィールドは、子シナリオモジュールの呼び出しに表示されます。

1. 子シナリオに渡す情報を子シナリオモジュールに入力またはマッピングします。
1. （条件付き）子シナリオからの応答を待たずに親シナリオの実行を続行する場合は、**火と忘れ** オプションを有効にします。
1. 「**OK**」をクリックして、モジュールを保存します。

>[!NOTE]
>
>このモジュールに新しい子シナリオを作成すると、子シナリオが別のブラウザーウィンドウで開き、親シナリオと子シナリオの両方を同時に表示して設定できます。

#### 親に応答を返す

これは子シナリオにあり、選択した構造のデータを親シナリオに送信します。 このデータは、親シナリオの後のモジュールにマッピングできます。

子シナリオに複数のルートがある場合は、常に他のルートの後で実行されるルートにこのモジュールを追加することをお勧めします。

レスポンダーを追加モジュールを設定するには：

1. 既存のデータ構造を使用するには、データ構造フィールドで、子シナリオが親シナリオに返すデータに使用されるデータ構造を選択します。

   または

   データの新しいデータ構造を作成するには、「データ構造」フィールドの横にある「**追加**」をクリックし、データ構造を作成します。

   データ構造の作成手順については、[ データ構造](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)を参照してください。

1. 「**OK**」をクリックして、モジュールを保存します。
