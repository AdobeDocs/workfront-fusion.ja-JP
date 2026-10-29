---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 関数を使用した基本シナリオのプロジェクトの更新
description: Workfrontで作業項目を更新する関数を追加する方法を説明します。
author: Becky
feature: Workfront Fusion
exl-id: aa082ac8-48e8-4569-880e-024dd77feaa1
TQID: https://experienceleague.adobe.com/F0kYjSMVgit8t-gPAR4U7O-1v8Qxy7UxSRK6uYxKItg
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
    internal-label: Integrations
source-git-commit: 4cd8b43e9ce9a16aca16397ce140cdd2467bf7d4
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 12%
---
# 関数を使用した基本シナリオのプロジェクトの更新

Workfront作業項目の更新は、Workfront Fusionの一般的な使用例です。 この例では、関数を使用して、プロジェクトの名前を大文字に変更します。

Fusionには、データに対して条件付きロジックを変換および実行できる多くのタイプの関数が含まれています。 関数の使用について詳しくは、[関数の概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md)を参照してください。

この例では、[基本シナリオの作成](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)で作成したシナリオを変更します。

>[!NOTE]
>
>Workfront Fusionは、シナリオエディターを新しいエクスペリエンスに移行中です。 この移行中は、従来のエクスペリエンスと新しいエクスペリエンスの両方を利用でき、いつでも切り替えることができます。 新しいエクスペリエンスを使用することをお勧めします。 詳しくは、シナリオエディターの記事「[新しいエクスペリエンスと従来のエクスペリエンス &#x200B;](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)」を参照してください。

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

## 関数を使用して、新しいエクスペリエンスのプロジェクトを更新する（推奨）

* [「レコードを更新」モジュールをシナリオに追加します](#add-the-update-a-record-module-to-your-scenario)
* [名前の更新のための関数のマッピング](#map-the-function-for-the-name-update)
* [検証と活用](#test-and-activate)

### 「レコードを更新」モジュールをシナリオに追加します

1. シナリオエディターでシナリオを開きます。
1. 2番目のモジュールの右端にカーソルを合わせ、表示されたら「**[!UICONTROL 別のモジュールを追加]**」をクリックします。
1. アプリケーションのリストから「Adobe Workfront」を選択し、「**[!UICONTROL レコードを更新]**」モジュールを選択します。
1. 「ID」フィールドで、オブジェクトを変換モジュールの下にあるID ブロックを選択します。 これは、そのモジュールによって出力されたプロジェクトのIDです。

   ![&#x200B; レコードモジュールの更新](assets/new-mapped-update-record.png)でマッピングされたID

1. 更新するオブジェクトがプロジェクトであるため、「レコードタイプ」フィールドで「プロジェクト」を選択します。
1. 「マップするフィールドを選択」領域で、「名前」を選択します。

   「名前」フィールドが開きます。
1. 続行[名前update](#map-the-function-for-the-name-update)の関数のマッピングを行います。

### 名前の更新のための関数のマッピング

このシナリオでリクエストをプロジェクトに変換する場合、プロジェクトの名前はリクエストと同じです。 ここでの関数は、その名前を取得し、その中のすべての文字を大文字にします。

1. 「**名前**」フィールドをクリックします。

   マッピングパネルが開きます。
1. マッピングパネルで、**テキスト関数とバイナリ関数** アイコンをクリックします。 ![&#x200B; テキスト関数アイコン &#x200B;](assets/new-text-binary-function.png)
1. 関数&#x200B;**upper**&#x200B;を選択します。

   関数は、「名前」フィールドに表示されます。これには、想定される入力の書式が含まれます。

   この例の入力は、プロジェクトが変換されたイシューの名前です。

1. 入力が行われる場所なので、括弧の間にカーソルを移動します。
1. マッピングパネルで、**モジュール出力** アイコンをクリックします。 ![&#x200B; モジュール出力アイコン &#x200B;](assets/new-module-output-icon.png)
1. 最初のモジュールによって出力された名前ブロックを選択します。

   名前ブロックが関数に表示されます。

   ![関数](assets/new-mapped-name-block.png)の名前ブロック

1. 「**OK**」をクリックして、モジュール設定を保存します。

### 検証と活用

1. 「**[!UICONTROL 1回実行]**」アイコンをクリックして、シナリオをテストします。

   「1回実行」は、新しいエクスペリエンスではアイコンのみです。 アイコンにカーソルを合わせると、**[!UICONTROL 1回実行]**&#x200B;のツールヒントが表示されます。

   ![&#x200B; シナリオボタンを実行](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/run-once-new.png)

1. 出力を調べて、シナリオが期待どおりに実行されていることを確認します。
1. シナリオが期待どおりに機能していることを確認したら、**スケジュール**&#x200B;切り替え&#x200B;**オン**&#x200B;をクリックします。

   これにより、シナリオがアクティブになります。 アクティブなシナリオは、トリガーモジュールで設定されたスケジュールに従って実行されます。

   ![&#x200B; スケジュール設定の切り替え](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/scheduling-new.png)

1. コントロール領域の&#x200B;**保存** アイコン ![保存アイコン &#x200B;](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/save-icon-new.png)をクリックして、シナリオの進行状況を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。 シナリオをトリガーするには、Workfront アカウントで新しいイシューを作成する必要がある場合があります。

## 関数を使用して、クラシックエクスペリエンスのプロジェクトを更新する

* [「レコードを更新」モジュールをシナリオに追加します（クラシック）](#add-the-update-a-record-module-to-your-scenario-classic)
* [名前の更新（クラシック）の関数をマッピング](#map-the-function-for-the-name-update-classic)
* [テストとアクティブ化（クラシック）](#test-and-activate-classic)

### 「レコードを更新」モジュールをシナリオに追加します（クラシック）

1. シナリオエディターでシナリオを開きます。
1. 2番目のモジュールの右側にある部分円にカーソルを合わせ、**[!UICONTROL 別のモジュールを追加]**&#x200B;をクリックします。
1. アプリケーションのリストから「Adobe Workfront」を選択し、「**[!UICONTROL レコードを更新]**」モジュールを選択します。
1. 「ID」フィールドで、オブジェクトを変換モジュールの下にあるID ブロックを選択します。 これは、そのモジュールによって出力されたプロジェクトのIDです。

   Convert オブジェクトからの![ID](assets/id-convert-object.png)

1. 更新するオブジェクトがプロジェクトであるため、「レコードタイプ」フィールドで「プロジェクト」を選択します。
1. 「マップするフィールドを選択」領域で、「名前」を選択します。

   「名前」フィールドが開きます。
1. [引き続き、名前の更新（Classic） &#x200B;](#map-the-function-for-the-name-update-classic)の関数をマッピングします。

### 名前の更新（クラシック）の関数をマッピング

このシナリオでリクエストをプロジェクトに変換する場合、プロジェクトの名前はリクエストと同じです。 ここでの関数は、その名前を取得し、その中のすべての文字を大文字にします。

1. 「**名前**」フィールドをクリックします。

   マッピングパネルが開きます。
1. マッピングパネルで、**テキスト関数とバイナリ関数** アイコンをクリックします。 ![&#x200B; テキスト関数アイコン &#x200B;](assets/toolbar-icon-text-binary-functions.png)
1. 関数&#x200B;**upper**&#x200B;を選択します。

   関数は、「名前」フィールドに表示されます。これには、想定される入力の書式が含まれます。

   この例の入力は、プロジェクトが変換されたイシューの名前です。

1. 入力が行われる場所なので、括弧の間にカーソルを移動します。
1. マッピングパネルで、**モジュール出力** アイコンをクリックします。 ![&#x200B; モジュール出力アイコン &#x200B;](assets/toolbar-icon-functions-you-map-from-other-modules.png)
1. 最初のモジュールによって出力された名前ブロックを選択します。

   名前ブロックが関数に表示されます。

   ![関数](assets/map-name.png)の名前ブロック

1. 「**OK**」をクリックして、モジュール設定を保存します。

### テストとアクティブ化（クラシック）

1. 画面の左下隅にある「**1回実行**」をクリックして、シナリオをテストします。
1. 出力を調べて、シナリオが期待どおりに実行されていることを確認します。
1. シナリオが期待どおりに機能していることを確認したら、画面の左下にある&#x200B;**スケジュール** トグルを&#x200B;**オン**&#x200B;にクリックします。

   これにより、シナリオがアクティブになります。 アクティブなシナリオは、トリガーモジュールで設定されたスケジュールに従って実行されます。
1. Workfront Fusionで、左下隅付近の&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックして、シナリオの進行状況を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。 シナリオをトリガーするには、Workfront アカウントで新しいイシューを作成する必要がある場合があります。

## リソース

* [組み込み関数を使用したアイテムのマッピング](/help//workfront-fusion/create-scenarios/map-data/map-using-functions.md)
