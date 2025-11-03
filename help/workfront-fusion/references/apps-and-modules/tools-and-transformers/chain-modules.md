---
title: チェーンモジュール
description: これらのモジュールを使用すると、シナリオを連結して、1 つの呼び出しを別の呼び出しにすることができます。
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 21429f94-fe4c-4ccc-a8c0-d7573657fecc
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 2%

---

# チェーンモジュール

チェーンモジュールを使用して、1 つのシナリオを別のシナリオに接続できます。

<!--This article will be about the specific module configuration-->

連鎖シナリオの計画手順は、[ 複数のシナリオを連鎖させる ](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md) を参照してください。


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



## チェーンモジュールとそのフィールド

### トリガー

#### 親からデータを受信

このモジュールは、子シナリオのトリガーモジュールであり、親シナリオの子シナリオを呼び出しモジュールによってトリガーされます。 親シナリオからデータを受け取り、子シナリオで処理できます。

親モジュールからデータを受信を設定するには：

1. 既存のデータ構造を使用するには、「データ構造」フィールドで、シナリオの入力データに使用するデータ構造を選択します。

   または

   シナリオの入力データとして使用する新しいデータ構造を作成するには、「データ構造」フィールドの横にある「**追加** をクリックして、データ構造を作成します。

   データ構造の作成手順については、[ データ構造 ](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md) を参照してください。

1. **OK** をクリックして、モジュールを保存します。

### アクション

#### 子シナリオの呼び出し

このモジュールは、親シナリオ内にあります。 フィールドは、子シナリオの親からデータを受信モジュールで設定されたデータ構造を反映しています。

>[!NOTE]
>
>* 既存の子シナリオを選択するか、このモジュールを通じて新しい子シナリオを作成できます。
>* 子シナリオを作成する際に、データ構造を作成できます。

子を呼び出しシナリオモジュールを設定するには

1. 「子シナリオを呼び出し」モジュールをシナリオに追加します。
1. 既存の子シナリオを使用するには、「チェーン」フィールドで、呼び出す子シナリオを選択します。

   または

   新しい子シナリオを作成するには、「チェーン」フィールドの横にある「追加」をクリックします。 子シナリオは別のウィンドウに表示され、「親からデータを受信」および「親から応答を返す」モジュールが配置されます。

   子シナリオのシナリオモジュールで設定されたフィールドは、子トリガーを呼び出しモジュールに表示されます。

1. 子シナリオに渡す情報を「子シナリオを呼び出す」モジュールに入力するかマッピングします。
1. （条件付き）子シナリオからの応答を待たずに親シナリオの実行を続行する場合は、「**実行して忘れる**」オプションを有効にします。
1. **OK** をクリックして、モジュールを保存します。

>[!NOTE]
>
>このモジュールに新しい子シナリオを作成する場合、子シナリオは別のブラウザーウィンドウで開き、親シナリオと子シナリオの両方を同時に表示して設定できます。

#### 親に返信する

これは子シナリオにあり、選択した構造のデータを親シナリオに送信します。 このデータを、親シナリオの後のモジュールにマッピングできます。

子シナリオに複数のルートがある場合、このモジュールを、他のルートの後で常に実行および実行されるルートに追加することをお勧めします。

レスポンダーを追加モジュールを設定するには：

1. 既存のデータ構造を使用するには、「データ構造」フィールドで、子シナリオが親シナリオに戻すデータに使用するデータ構造を選択します。

   または

   データの新しいデータ構造を作成するには、「データ構造」フィールドの横にある **追加** をクリックして、データ構造を作成します。

   データ構造の作成手順については、[ データ構造 ](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md) を参照してください。

1. **OK** をクリックして、モジュールを保存します。
