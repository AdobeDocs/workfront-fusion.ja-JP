---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 基本シナリオへのトリガーモジュールの追加
description: トリガーモジュールを追加して、シナリオが定期的に新しいリクエストを検索し、それらをプロジェクトに変換できるようにする方法を説明します。
author: Becky
feature: Workfront Fusion
exl-id: cd8ac958-b7a6-4536-89d8-c79a2f8940a6
source-git-commit: 3a977d805c10fda7209b0634c6e32e818a980691
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 6%

---

# 基本シナリオへのトリガーモジュールの追加

トリガーモジュールは、シナリオの最初に配置されます。 これらのモジュールは、特定のサービスに変更が加えられると、シナリオの実行を開始します。 変更には、新しいレコードの作成、レコードの削除、レコードの更新などがあります。 シナリオを開始する変更の条件を指定します。

ポーリングモジュールは、設定された時間間隔でサービスを確認し、その時間間隔で発生した変更に関する情報を返します。 何も変更されていない場合、トリガーはシナリオを実行しません。

この例では、15 分ごとに実行されるトリガーモジュールを追加し、特定のキューにリクエストが送信された場合にシナリオを開始します。 次に、シナリオはこれらのリクエストをプロジェクトに変換します。

この例では、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で作成したシナリオを変更します。

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

## 前提条件

この手順を実行する前に、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で説明されているシナリオを作成する必要があります。

## トリガーモジュールの追加と設定

### トリガーモジュールを追加

1. シナリオエディターでシナリオを開きます。
1. 最初の（検索）モジュールを右クリックし、**モジュールを削除** を選択します。

   モジュールが削除され、空白のプレースホルダーが残ります。

1. 空のモジュールをクリックし、アプリのリストから **0}Adobe Workfront} を選択します。**
1. **レコードをウォッチ** を選択します。
1. モジュールで、シナリオ内の残りのモジュールと同じ接続が使用されていることを確認します。
1. レコードタイプ フィールドで、「**イシュー**」を選択します。
1. 「フィルター」フィールドで、「**新しいレコードのみ**」を選択します。
1. 「出力」ボックスで、「`ID`」、「`Name`」および「`Project ID`」を選択します。
1. **OK** をクリックして、モジュール設定を保存します。

   [Choose where to start] （開始位置を選択）ウィンドウが開きます。

1. **今から** を選択します。

### トリガーモジュールのスケジュール設定

1. 「Watch Records」モジュールの時計をクリックします。

   スケジュール設定ウィンドウが開きます。

1. 「シナリオを実行」フィールドで、「一定の間隔で **を選択し** す。

1. 「**OK**」をクリックします。

### 2 つ目のモジュールの更新

最初のモジュールは交換済みなので、2 番目のモジュールは新しい最初のモジュールにマッピングする必要があります。

1. Convert object モジュールを開きます。
1. 「イシュー ID」フィールドで、黒の ID ブロックを削除します。 ブロックは、マッピング元のモジュールが使用できなくなったため、黒になります。
1. 最初のモジュール（レコードをウォッチ）の下にある ID ブロックを選択して、2 番目のモジュールにマッピングします。
1. 「**OK**」をクリックします。

### テストしてアクティブ化

1. Fusion が接続するWorkfront環境に移動して、問題を追加します。
1. シナリオエディターの左下隅にある「**[!UICONTROL 1 回実行]**」をクリックします。
1. 出力を調べて、シナリオが期待どおりに実行されたことを確認します。
1. シナリオが期待どおりに動作していることを確認したら、画面の左下にある **スケジュール** トグルをクリックして **オン** にします。

   これにより、シナリオがアクティブになります。
1. Workfront Fusion で、左下隅付近の **[!UICONTROL 保存]** をクリックして、シナリオの進捗を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。

## リソース

* トリガーモジュールについて詳しくは、「モジュールの概要」の [トリガーモジュール ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) を参照してください。
