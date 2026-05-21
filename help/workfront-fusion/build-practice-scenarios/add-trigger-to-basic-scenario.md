---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 基本シナリオへのトリガーモジュールの追加
description: トリガーモジュールを追加して、新しいリクエストを定期的に検索してプロジェクトに変換できるようにする方法を説明します。
author: Becky
feature: Workfront Fusion
exl-id: cd8ac958-b7a6-4536-89d8-c79a2f8940a6
TQID: https://experienceleague.adobe.com/xepLecibr9U6FpQM0neDy15DbFGF55rR6gVYvo644H4
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 600
ht-degree: 22%

---

# 基本シナリオへのトリガーモジュールの追加

トリガーモジュールは、シナリオの最初に配置されます。 これらのモジュールは、特定のサービスに変更があった場合にシナリオの実行を開始します。 変更は、新しいレコードの作成、レコードの削除、レコードの更新などです。 シナリオを開始する変更の基準を指定します。

ポーリングモジュールは、設定された時間間隔でサービスを確認し、その時間間隔で発生した変更に関する情報を返します。 変更がない場合、トリガーはシナリオを実行しません。

この例では、15分ごとに実行されるトリガーモジュールを追加し、リクエストが特定のキューに送信された場合にシナリオを開始します。 その後、シナリオはこれらのリクエストをプロジェクトに変換します。

この例では、[基本シナリオの作成](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)で作成したシナリオを変更します。

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

## 前提条件

この手順に従う前に、[基本シナリオの作成](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)で説明したシナリオを作成する必要があります。

## トリガーモジュールの追加と設定

### トリガーモジュールを追加する

1. シナリオエディターでシナリオを開きます。
1. 最初の（検索）モジュールを右クリックし、**モジュールを削除**&#x200B;を選択します。

   モジュールが削除され、空白のプレースホルダーが残ります。

1. 空白のモジュールをクリックし、アプリケーションのリストから&#x200B;**Adobe Workfront**&#x200B;を選択します。
1. 「**レコードを視聴**」を選択します。
1. モジュールで、シナリオ内の他のモジュールと同じ接続が使用されていることを確認します。
1. 「レコードタイプ」フィールドで、「**問題**」を選択します。
1. 「フィルター」フィールドで、**新規レコードのみ**&#x200B;を選択します。
1. 出力ボックスで、`ID`、`Name`、`Project ID`を選択します。
1. 「**OK**」をクリックして、モジュール設定を保存します。

   「開始する場所を選択」ウィンドウが表示されます。

1. **今から**&#x200B;を選択します。

### トリガーモジュールのスケジュール

1. Watch Records モジュールの時計をクリックします。

   スケジュール設定ウィンドウが開きます。

1. 「シナリオを実行」フィールドで、**一定の間隔で**&#x200B;を選択します。

1. 「**OK**」をクリックします。

### 2つ目のモジュールを更新する

最初のモジュールは置き換えられたため、2番目のモジュールは新しい1番目のモジュールにマッピングする必要があります。

1. オブジェクトを変換モジュールを開きます。
1. 「問題ID」フィールドで、黒いID ブロックを削除します。 ブロックは黒です。これは、マッピング元のモジュールが使用できなくなったためです。
1. 最初のモジュール（監視レコード）の下にあるID ブロックを選択して、2番目のモジュールにマッピングします。
1. 「**OK**」をクリックします。

### 検証と活用

1. Fusionが接続しているWorkfront環境に移動し、問題を追加します。
1. シナリオエディターの左下隅にある「**[!UICONTROL 1 回実行]**」をクリックします。
1. 出力を調べて、シナリオが期待どおりに実行されていることを確認します。
1. シナリオが期待どおりに機能していることを確認したら、画面の左下にある&#x200B;**スケジュール** トグルを&#x200B;**オン**&#x200B;にクリックします。

   これにより、シナリオがアクティブになります。
1. Workfront Fusionで、左下隅付近の&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックして、シナリオの進行状況を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。

## リソース

* トリガーモジュールについて詳しくは、「モジュールの概要」の「[トリガーモジュール &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)」を参照してください。
