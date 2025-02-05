---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 関数を使用した基本シナリオのプロジェクトの更新
description: Workfrontで作業項目を更新する関数を追加する方法について説明します。
author: Becky
feature: Workfront Fusion
exl-id: aa082ac8-48e8-4569-880e-024dd77feaa1
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 7%

---

# 関数を使用した基本シナリオのプロジェクトの更新

Workfront作業項目の更新は、Workfront Fusion の一般的なユースケースです。 この例では、関数を使用して、プロジェクトの名前を大文字に変更します。

Fusion には、データに対して条件付きロジックを変換および実行できる多くのタイプの関数が含まれています。 関数の使用について詳しくは、「[ 関数の概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md)」を参照してください。

この例では、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で作成したシナリオを変更します。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

この手順を実行する前に、[ 基本シナリオの作成 ](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) で説明されているシナリオを作成する必要があります。

## 関数を使用したプロジェクトの更新

### シナリオにレコードを更新モジュールを追加します

1. シナリオエディターでシナリオを開きます。
1. 2 つ目のモジュールの右側にある部分的な円にポインタを合わせ、「**[!UICONTROL Add another module]**」をクリックします。
1. アプリケーションのリストから「[!DNL Adobe Workfront]」を選択し、モジュール **[!UICONTROL Update Record]** を選択します。
1. ID フィールドで、オブジェクトを変換モジュールの下にある ID ブロックを選択します。 これは、そのモジュールによって出力されたプロジェクトの ID です。

   ![Convert オブジェクトからの ID](assets/id-convert-object.png)

1. 更新するオブジェクトはプロジェクトなので、「レコードタイプ」フィールドで「プロジェクト」を選択します。
1. マッピングするフィールドを選択エリアで、「名前」を選択します。

   名前フィールドが開きます。
1. [ 名前の更新用に関数をマッピング ](#map-the-function-for-the-name-update) を続行します。

### 名前の更新用に関数をマッピング

このシナリオで要求がプロジェクトに変換されると、プロジェクトの名前は要求と同じになります。 ここでの関数は、その名前を受け取り、その中のすべての文字を大文字にします。

1. 「**名前** フィールドをクリックします。

   マッピングパネルが開きます。
1. マッピングパネルで「**テキスト関数とバイナリ関数** アイコンをクリックします。 ![ テキスト関数アイコン ](assets/toolbar-icon-text&binary-functions.png)
1. 関数 **upper** を選択します。

   関数は、必要な入力の書式を含め、「名前」フィールドに表示されます。

   この例では、プロジェクトの変換元のイシューの名前が入力されます。

1. カーソルを括弧の間に移動します。これは、入力が行われる場所だからです。
1. マッピングパネルで「**モジュール出力**」アイコンをクリックします。 ![ モジュール出力アイコン ](assets/toolbar-icon-functions-you-map-from-other-modules.png)
1. 最初のモジュールによって出力された名前ブロックを選択します。

   名前ブロックが関数に表示されます。

   ![ 関数内の名前ブロック ](assets/map-name.png)

1. **OK** をクリックして、モジュール設定を保存します。

### テストしてアクティブ化

1. 画面の左下にある「**1 回実行**」をクリックして、シナリオをテストします。
1. 出力を調べて、シナリオが期待どおりに実行されたことを確認します。
1. シナリオが期待どおりに動作していることを確認したら、画面の左下にある **スケジュール** トグルをクリックして **オン** にします。

   これにより、シナリオがアクティブになります。 アクティブなシナリオは、トリガーモジュールで設定したスケジュールに従って実行されます。
1. [!DNL Workfront Fusion] では、左下隅付近の **[!UICONTROL Save]** をクリックして、シナリオの進捗を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。

## リソース

* [関数を使用した項目のマッピング](/help//workfront-fusion/create-scenarios/map-data/map-using-functions.md)
