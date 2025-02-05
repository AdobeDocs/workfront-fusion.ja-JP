---
title: フロー制御
description: シナリオを作成または編集する際、シナリオ内でのデータの流れを制御する設定を行うことができます。
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: 5a95b2c191d4e6d8750dc57a47923f416612b4a9
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 36%

---

# フロー制御

シナリオを作成または編集する際、シナリオ内でのデータの流れを制御する設定を行うことができます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>Workfront Fusion のライセンス要件はありません。</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## リピーター

[!UICONTROL Repeater] モジュールを使用すると、タスクを指定した回数繰り返すことができます。 [!UICONTROL Repeater] モジュールは、バンドルを順番に生成します。


<table>
    <tr>
        <td>[!UICONTROL Initial value]</td>
        <td>モジュールの最初のイテレーションに含める値を入力またはマッピングします。 デフォルト値は 1 です。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Repeats]</td>
        <td>モジュールが繰り返す回数を入力またはマッピングします。この数は、0 以上 10,000 以下である必要があります。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Step]</td>
        <td>これは、モジュールが値を増加させる数値です。 デフォルト値は 1 です。</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

例えば、[!UICONTROL Repeater] モジュールを使用して、**[!UICONTROL Email]>[!UICONTROL Send me an email]** モジュールを [!UICONTROL Repeater] モジュールに接続することで、「Hello 1」、「Hello 2」などの件名が入った 5 通のメールを送信できます。

1. 画面下部の [!UICONTROL Flow Control] アイコン ![ フロー制御アイコン ](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) をクリックし、表示されるメニューで「**[!UICONTROL Repeater]**」をクリックします。
1. [!UICONTROL Repeater] モジュールをクリックし、表示されるボックスで **[!UICONTROL Connect automatically]** をクリックします。

   リピーターのモジュールが開きます。

1. 「**[!UICONTROL Repeats]**」フィールドに、モジュールで生成する繰り返し回数（出力されたバンドル）を入力します。

   この例では、5 と入力します。

   ![ リピーター ](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   項目の値は、**[!UICONTROL Step]** フィールドで指定されたこの値だけ繰り返し増加します。この値は、**[!UICONTROL Show advanced settings]** を選択すると表示できます。 この数値は、デフォルトでは 1 です。

1. 「**[!UICONTROL OK]**」をクリックして、**[!UICONTROL Flow Control]** ールボックスを閉じます。

1. [!UICONTROL Repeater] モジュールに接続されているアプリまたはサービスモジュールをクリックします。
1. 表示されるボックスに、繰り返す情報を入力します。

   このメールの例では、[!UICONTROL Subject] ールボックスに「Hello」と入力し、リピーターのモジュールから `i` をマッピングします。

   ![ リピーター ](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)



>[!NOTE]
>
>繰り返し回数は、プログラミングのループとは異なり、`i` の値によって決まるわけではありません。モジュールは、「[!UICONTROL Repeats]」フィールドに示された回数を繰り返します。 値 `i` は [!DNL repeater] モジュールのイテレーションごとに変化し、後のモジュールにマッピングできます。ここでの例では、`i` の値を「こんにちは」メッセージにマッピングすると、「こんにちは 1」、「こんにちは 2」などのメッセージが表示されます。

>[!ENDSHADEBOX]

## [!UICONTROL Iterator]

[!UICONTROL Iterator] は、配列を一連のバンドルに変換する特別なタイプのモジュールです。 各配列項目は、[!UICONTROL Iterator] モジュール出力では個別のバンドルになります。 詳しくは、[ イテレータモジュール ](/help/workfront-fusion/references/modules/iterator-module.md) を参照してください。

## 配列アグリゲーター

配列アグリゲーターは、複数のバンドルを 1 つのバンドルに結合できる特別なタイプのモジュールです。詳しくは、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

## [!UICONTROL Router]

[!UICONTROL Router] モジュールを使用すると、フローを複数のルートに分岐し、各ルート内のデータを異なる方法で処理できます。 [!UICONTROL Router] モジュールは、バンドルを受け取ると、ルートが [!UICONTROL Router] モジュールにアタッチされた順序で、接続された各ルートに転送します。 詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md) のルーターモジュールを参照してください。

## ディレクティブ

エラー処理ディレクティブを使用すると、シナリオがエラーにどのように反応するかを制御できます。

エラー処理ディレクティブについて詳しくは、「[ エラー処理用のディレクティブ ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)」を参照してください。

