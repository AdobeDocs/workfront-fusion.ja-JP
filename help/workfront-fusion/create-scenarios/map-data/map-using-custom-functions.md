---
title: カスタム関数を使用したデータのマッピング
description: 項目をマッピングする場合、関数を使用して単純な数式や複雑な数式を作成できます。
author: Becky
feature: Workfront Fusion
source-git-commit: 109ea8a6b3c37918110dc930a19ac85ef3e6d764
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 20%

---

# カスタム関数を使用したデータのマッピング

Fusion の関数領域で、カスタム関数を作成できます。 次に、これらの関数を、Adobe App Builder モジュールの形式でシナリオに追加します。

カスタム関数はAdobe App Builderを通じて機能するので、使用する組織のAdobe App Builder ライセンスが必要です。

ほとんどのシナリオ要素と同様、カスタム関数はチームが所有します。

Workfront Fusion には、単純な式や複雑な式を作成できる組み込み関数も含まれています。 これらの関数は、配列、文字列、数値、以前のモジュールのデータの関数など、様々なユースケースに対応しています。

組み込み関数の詳細と手順については、[&#x200B; 組み込み関数を使用した項目のマッピング &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md) を参照してください。

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

カスタム関数は、Workfront Fusion の関数領域で設定されます。 関数を設定したら、Adobe App Builder コネクタを使用して、関数をシナリオに追加できます。

### ランタイム環境の初期化

カスタム関数を作成する前に、ランタイム環境を初期化する必要があります。 これは、チームにカスタム関数がない場合にのみ実行する必要があります。

>[!IMPORTANT]
>
>初期化は、Adobe App Builderにアクセスできるユーザー（開発者または IMS 組織内のシステム管理者）のみが実行できます。
>
>初期化が完了すると、初期化が実行されたチームのすべてのユーザーが関数を作成して使用できるようになります。

1. 左側のパネルで「**関数** ![&#x200B; 関数アイコン &#x200B;](assets/functions-icon.png)」タブをクリックします。

   ランタイムをまだ設定していない場合は、「ランタイム環境が設定されていません」というメッセージが表示されます。
1. **ランタイムの初期化** をクリックします。

   しばらくすると、関数リストが表示され、2 つのサンプル関数が表示されます。

### カスタム関数の作成

ランタイム環境が設定されたら、カスタム関数の作成を開始できます。

>[!IMPORTANT]
>
>* カスタム関数は **必ず** JavaScript関数にする。
>* カスタム関数 **must** は、オブジェクトを返します。
>* カスタム関数を作成した後に、次の操作を実行することはできません。
>
>   * 名前を変更
>   * デフォルトのパラメーター値の表示

1. 左側のパネルで「**関数** ![&#x200B; 関数アイコン &#x200B;](assets/functions-icon.png)」タブをクリックします。
1. **関数を追加** をクリックします。
1. カスタム関数の名前を入力します。

   この名前は後で変更できません。
1. 関数のコードを入力します。
1. 追加する各デフォルトパラメーター値に対して、「**パラメーターを追加** をクリックし、パラメーター名とデフォルト値を入力します。

   関数をシナリオに追加する際に、デフォルトのパラメーターを上書きできます。
1. 「**保存**」をクリックします。

## シナリオへのカスタム関数の追加

シナリオにカスタム関数を追加するには、Adobe App Builder コネクタを使用します。

手順については、[Adobe App Builder モジュール &#x200B;](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md) を参照してください。

