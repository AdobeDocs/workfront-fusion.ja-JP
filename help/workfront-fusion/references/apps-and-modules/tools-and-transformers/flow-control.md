---
title: フロー制御
description: シナリオを作成または編集する際、シナリオ内でのデータの流れを制御する設定を行うことができます。
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: ce2f13866fef97b5687991dfcf5d9579a5e539e4
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 50%

---

# フロー制御

シナリオを作成または編集する際、シナリオ内でのデータの流れを制御する設定を行うことができます。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration], [!UICONTROL [!DNL Workfront Fusion] for Work Automation]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## リピーター

[!UICONTROL Repeater] モジュールを使用すると、タスクを指定した回数繰り返すことができます。 [!UICONTROL Repeater] モジュールは、バンドルを順番に生成します。

例えば、[!UICONTROL Repeater] モジュールを使用して、**[!UICONTROL Email]>[!UICONTROL Send me an email]** モジュールを [!UICONTROL Repeater] モジュールに接続することで、「Hello 1」、「Hello 2」などの件名が入った 5 通のメールを送信できます。

[!UICONTROL Repeater] モジュールを使用するには：

1. 画面の下部に ![](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) る [!UICONTROL Flow Control] アイコンをクリックし、表示されるメニューで「**[!UICONTROL Repeater]**」をクリックします。
1. [!UICONTROL Repeater] バンドルをクリックしてから、表示されるボックスで **[!UICONTROL Connect automatically]** をクリックします。
1. 表示される [!UICONTROL Flow Control] ボックスに、繰り返し（出力されたバンドル）の数を **[!UICONTROL Repeats]** ボックスに入力します。

   ここでのメールの例では、「5」と入力します。

   ![](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   項目の値は、**[!UICONTROL Step]** フィールドで指定されたこの値だけ繰り返し増加します。この値は、**[!UICONTROL Show advanced settings]** を選択すると表示できます。 この数値は、デフォルトでは 1 です。

1. 「**[!UICONTROL OK]**」をクリックして、**[!UICONTROL Flow Control]** ールボックスを閉じます。

1. [!UICONTROL Repeater] モジュールに接続されているアプリまたはサービスモジュールをクリックします。
1. 表示されるボックスに、繰り返す情報を入力します。

   このメールの例では、[!UICONTROL Subject] ールボックスに「Hello」と入力し、リピーターのモジュールから `i` をマッピングします。

   ![](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)

| 項目 | 説明 |
|---|---|
| [!UICONTROL Initial value] | 最初の繰り返しでモジュールが `i` として設定する数値を入力またはマッピングします。デフォルト値は 1 です。 |
| [!UICONTROL Repeats] | モジュールが繰り返す回数を入力またはマッピングします。この数は、0 以上 10,000 以下である必要があります。 |
| [!UICONTROL Step] | モジュールは、`i` の値を、この数だけ増分します。デフォルト値は 1 です。 |

{style="table-layout:auto"}

>[!NOTE]
>
>繰り返し回数は、プログラミングのループとは異なり、`i` の値によって決まるわけではありません。モジュールは、「[!UICONTROL Repeats]」フィールドに示された回数を繰り返します。 値 `i` は [!DNL repeater] モジュールのイテレーションごとに変化し、後のモジュールにマッピングできます。ここでの例では、`i` の値を「こんにちは」メッセージにマッピングすると、「こんにちは 1」、「こんにちは 2」などのメッセージが表示されます。

## [!UICONTROL Iterator]

[!UICONTROL Iterator] は、配列を一連のバンドルに変換する特別なタイプのモジュールです。 各配列項目は、[!UICONTROL Iterator] モジュール出力では個別のバンドルになります。 詳しくは、[ イテレータモジュール ](/help/workfront-fusion/references/modules/iterator-module.md) を参照してください。

## 配列アグリゲーター

配列アグリゲーターは、複数のバンドルを 1 つのバンドルに結合できる特別なタイプのモジュールです。詳しくは、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

## [!UICONTROL Router]

[!UICONTROL Router] モジュールを使用すると、フローを複数のルートに分岐し、各ルート内のデータを異なる方法で処理できます。 [!UICONTROL Router] モジュールは、バンドルを受け取ると、ルートが [!UICONTROL Router] モジュールにアタッチされた順序で、接続された各ルートに転送します。 詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md) のルーターモジュールを参照してください。

<!--
<div>
<h2>Directives</h2>
<p>The error handling directives allow you to control how your scenario reacts to errors. For more information, see <a href="/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md" class="MCXref xref">Advanced error handling in Adobe Workfront Fusion</a> and <a href="/help/workfront-fusion/references/errors/directives-for-error-handling.md" class="MCXref xref">Directives for error handling in Adobe Workfront Fusion</a>.</p>
</div>
-->
