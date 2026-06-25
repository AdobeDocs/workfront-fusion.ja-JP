---
title: カスタム関数を使用したデータのマッピング
description: 項目をマッピングする場合、関数を使用して単純な数式や複雑な数式を作成できます。
author: Becky
feature: Workfront Fusion
exl-id: dc4e697a-a65c-48bc-99de-8e26fbeb7ba7
source-git-commit: cf686d3b04eadfa7aea314bdd995c25cdea370a5
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 15%

---

# カスタム関数を使用したデータのマッピング

Fusionの「関数」エリアでカスタム関数を作成できます。 次に、これらの関数をAdobe App Builder モジュールの形式でシナリオに追加します。

カスタム関数はAdobe App Builderを通じて機能するため、使用するにはAdobe App Builder ライセンスが必要です。

カスタム関数は、ほとんどのシナリオ要素と同様に、チームが所有します。

関数は単純なJavaScript関数です。 関数ロジックに変数または依存関係を含めるには、パッケージを使用します。

パッケージについて詳しくは、[ カスタム関数パッケージの使用](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md)を参照してください。

Workfront Fusionには、シンプルな数式や複雑な数式を作成するための関数も組み込まれています。 これらの関数は、配列、文字列、数値、および以前のモジュールのデータに対する関数など、様々なユースケースをカバーします。

組み込み関数の詳細と手順については、[組み込み関数を使用したアイテムのマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md)を参照してください。

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
   <p><ul><li>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li><li>カスタム関数を使用するには、Adobe App Builder ライセンスが必要です。</ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## カスタム関数の設定

複数のシナリオで使用できるカスタム関数を「関数」領域に作成するか、個々のシナリオ内でカスタム関数を設定できます。

* [複数のシナリオで使用するカスタム関数の作成](#create-a-custom-function-to-use-in-multiple-scenarios)
* [シナリオ内でのカスタム関数の作成](#create-a-custom-function-within-a-scenario)

### 複数のシナリオで使用するカスタム関数の作成

複数のシナリオで使用できるカスタム関数は、Workfront Fusionの「関数」領域で設定します。 関数を設定したら、Adobe App Builder コネクタを使用してシナリオに追加できます。

* [ランタイム環境の初期化](#initialize-your-runtime-environment)
* [「関数」領域にカスタム関数を作成します](#create-a-custom-function-in-the-functions-area)

#### ランタイム環境の初期化

カスタム関数を作成する前に、ランタイム環境を初期化する必要があります。 これは、チームがカスタム機能を持っていない場合にのみ行う必要があります。

>[!IMPORTANT]
>
>初期設定は、Adobe App Builderにアクセスできるユーザー（開発者またはIMS組織内のシステム管理者）のみが実行できます。
>
>初期化が完了すると、初期化が実行されたチームのすべてのユーザーが関数を作成して使用できるようになります。

1. 左側のパネルで「**関数** ![関数アイコン ](assets/functions-icon.png)」タブをクリックします。

   ランタイムをまだ設定していない場合は、「ランタイム環境が設定されていません」というメッセージが表示されます。
1. 「**ランタイムの初期化**」をクリックします。

   しばらくすると、関数リストが表示され、2つのサンプル関数が表示されます。

#### 「関数」領域にカスタム関数を作成します

ランタイム環境を設定したら、カスタム関数の作成を開始できます。

>[!IMPORTANT]
>
>* カスタム関数&#x200B;**はJavaScript関数である必要があります**。
>* カスタム関数&#x200B;**は**&#x200B;でオブジェクトを返す必要があります。
>* カスタム関数を作成した後、次の操作はできません。
>
>   * 名前を変更
>   * デフォルトのパラメーター値の表示

1. 左側のパネルで「**関数** ![関数アイコン ](assets/functions-icon.png)」タブをクリックします。
1. 「**関数を追加**」をクリックします。
1. カスタム関数の名前を入力します。

   後でこの名前を変更することはできません。
1. 関数のコードを入力します。
1. 追加するデフォルトのパラメーター値ごとに、**パラメーターを追加**&#x200B;をクリックし、パラメーター名とデフォルト値を入力します。

   シナリオに関数を追加する際に、デフォルトのパラメーターを上書きできます。
1. 「**保存**」をクリックします。

### シナリオ内でのカスタム関数の作成

シナリオ内でカスタム関数を作成するには、Adobe App Builder コネクタの&#x200B;**カスタムコードブロックの実行** モジュールを使用します。

手順については、[Adobe App Builder モジュール ](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md)を参照してください。

## シナリオへのカスタム関数の追加

シナリオにカスタム関数を追加するには、Adobe App Builder コネクタを使用します。

手順については、[Adobe App Builder モジュール ](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md)を参照してください。
