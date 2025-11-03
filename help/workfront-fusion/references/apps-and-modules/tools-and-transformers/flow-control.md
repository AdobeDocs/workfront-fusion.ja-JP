---
title: フロー制御
description: シナリオを作成または編集する際、シナリオ内でのデータの流れを制御する設定を行うことができます。
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 64%

---

# フロー制御

シナリオを作成または編集する際、シナリオ内でのデータの流れを制御する設定を行うことができます。

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



## リピーター

[!UICONTROL リピーター]モジュールを使用すると、タスクを指定した回数繰り返すことができます。[!UICONTROL リピーター]モジュールは、次々にバンドルを生成します。


<table>
    <tr>
        <td>[!UICONTROL 初期値 ]</td>
        <td>モジュールの最初のイテレーションに含める値を入力またはマッピングします。 デフォルト値は 1 です。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 繰り返し ]</td>
        <td>モジュールが繰り返す回数を入力またはマッピングします。この数は、0 以上 10,000 以下である必要があります。</td>
    </tr>
    <tr>
        <td>[!UICONTROL ステップ ]</td>
        <td>これは、モジュールが値を増加させる数値です。 デフォルト値は 1 です。</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

例えば、[!UICONTROL リピーター]モジュールを使用して「こんにちは 1」、「こんにちは 2」などの件名のメールを 5 通送信するには、**[!UICONTROL メール]／[!UICONTROL 自分にメール]**&#x200B;モジュールを[!UICONTROL リピーター]モジュールに接続します。

1. 画面下部の [!UICONTROL  フロー制御 ] アイコン ![ フロー制御アイコン ](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) をクリックし、表示されるメニューで **[!UICONTROL リピータ]** をクリックします。
1. [!UICONTROL  リピーター ] モジュールをクリックし、表示されたボックスで **[!UICONTROL 自動接続]** をクリックします。

   リピーターのモジュールが開きます。

1. 「**[!UICONTROL 繰り返し]**」フィールドに、モジュールで生成する繰り返し（出力されたバンドル）の数を入力します。

   この例では、5 と入力します。

   ![ リピーター ](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   アイテムの値は、繰り返されるごとに、**[!UICONTROL ステップ]**&#x200B;フィールドで指定したこの数ずつ増加します。この値は、**[!UICONTROL 詳細設定を表示]**&#x200B;を選択すると表示できます。この数値は、デフォルトでは 1 です。

1. 「**[!UICONTROL OK]**」をクリックして、**[!UICONTROL フロー制御]**&#x200B;ボックスを閉じます。

1. [!UICONTROL リピーター]モジュールに接続されているアプリまたはサービスモジュールをクリックします。
1. 表示されるボックスに、繰り返す情報を入力します。

   ここでのメールの例では、[!UICONTROL 件名]ボックスに「こんにちは」と入力し、リピーターモジュールから `i` をマッピングします。

   ![ リピーター ](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)



>[!NOTE]
>
>繰り返し回数は、プログラミングのループとは異なり、`i` の値によって決まるわけではありません。モジュールは、[!UICONTROL 繰り返し]フィールドに指定された回数だけ繰り返します。値 `i` は [!DNL repeater] モジュールのイテレーションごとに変化し、後のモジュールにマッピングできます。ここでの例では、`i` の値を「こんにちは」メッセージにマッピングすると、「こんにちは 1」、「こんにちは 2」などのメッセージが表示されます。

>[!ENDSHADEBOX]

## [!UICONTROL イテレーター]

[!UICONTROL イテレーター]は、配列を一連のバンドルに変換する特別なタイプのモジュールです。配列の各項目は、[!UICONTROL イテレーター]モジュールの出力では個別のバンドルになります。詳しくは、[ イテレータモジュール ](/help/workfront-fusion/references/modules/iterator-module.md) を参照してください。

## 配列アグリゲーター

配列アグリゲーターは、複数のバンドルを 1 つのバンドルに結合できる特別なタイプのモジュールです。詳しくは、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

## [!UICONTROL ルーター]

[!UICONTROL ルーター]モジュールを使用すると、フローを複数のルートに分岐し、データを各ルートで別々に処理できます。[!UICONTROL ルーター]モジュールはバンドルを受け取ると、ルートが[!UICONTROL ルーター]モジュールに接続された順序で、接続されている各ルートにバンドルを転送します。詳しくは、[Adobe Workfront Fusion のルーターモジュール ](/help/workfront-fusion/create-scenarios/add-modules/router-module.md) を参照してください。

## ディレクティブ

エラー処理ディレクティブを使用すると、シナリオがエラーにどのように反応するかを制御できます。

エラー処理ディレクティブについて詳しくは、「[ エラー処理用のディレクティブ ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)」を参照してください。

