---
title: シナリオへのフィルターの追加
description: 場合によっては、特定の条件を満たすバンドルのみで作業する必要があります。フィルターを使用すると、そのようなバンドルを選択できます。
author: Becky
feature: Workfront Fusion
exl-id: b507dca0-0e85-4ab7-8310-b6e6bcb7ae12
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 30%

---

# シナリオへのフィルターの追加

場合によっては、特定の条件を満たすバンドルのみで作業する必要があります。フィルターを使用すると、そのようなバンドルを選択できます。

例えば、Workfrontの「[!UICONTROL  レコードをウォッチ ]」トリガーを使用して、特定のユーザーに割り当てられたタスクのみを取り込むシナリオを作成できます。

2 つのモジュール間にフィルターを追加すると、前のモジュールから受け取ったバンドルが特定のフィルター条件を満たしているかどうかを確認できます。

* 満たしている場合、バンドルはシナリオ内の次のモジュールに渡されます。
* 満たしていない場合、バンドルの処理は終了します。

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

+++##前提条件

両方のモジュールをシナリオに追加した後で、それらの間にフィルターを追加する必要があります。

## 2 つのモジュール間にフィルターを追加します。

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. フィルターを追加するモジュールの間にあるレンチアイコン ![ レンチアイコン ](assets/wrench-icon.png) をクリックし、「**フィルターを設定** を選択します。
1. 表示されたボックスに、フィルターの **[!UICONTROL ラベル]** を入力します。
1. フィルター **[!UICONTROL 条件]** を定義します。

   最初のフィールドにフィルターの基準にするフィールド、演算子、（必要に応じて）フィールドと比較する値を入力します。

   >[!TIP]
   >
   >マッピングパネルからフィルターフィールドに値を入力できます
   >マッピングについて詳しくは、「[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)」を参照してください。

   例えば、フィルターで XML で終わるAdobe Workfront内のファイルを渡す場合は、最初のボックスにと **[!UICONTROL ファイル名]** を入力します。2 番目のボックスに「.**[!UICONTROL xml]**」と入力します。それらの間のドロップダウンメニューで、「**[!UICONTROL 次で終わる（大文字と小文字を区別しない）]**」を選択します。このフィルターは、最初のモジュール（Workfront）からの受信バンドルに適用されます。XML ファイルを含むバンドルのみが次のモジュールに渡されます。

   ![ フィルターの設定 ](assets/set-up-filter-box.png)

1. **[!DNL OK]** をクリックします。

## フィルターをコピー

現在、シナリオエディターには、フィルターをコピーする機能が含まれています。

>[!NOTE]
>
>フィルターのどちらかの側のモジュールをコピーすると、フィルターもコピーされます。
>
>モジュールのコピーについて詳しくは、[Adobe Workfront Fusion でのモジュールまたはシナリオのコピー ](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md) を参照してください。

モジュールをコピーせずにフィルターをコピーするには、Fusion 開発ツールを使用できます

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. 画面の下部にある開発ツールアイコン ![ 開発ツールアイコン ](assets/debugger-icon.png) をクリックして、Fusion 開発ツールを開きます。

   開発ツールアイコンが表示されない場合、開発ツールを開く手順については [ シナリオのデバッグ ](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) を参照してください。

1. 左側のバーにある **[!UICONTROL ツール]** アイコン ![ 開発ツールツール ](assets/devtools-tools-icon.png) をクリックします。

1. 「**[!UICONTROL フィルターをコピー]**」をクリックし、右側のパネルの&#x200B;**[!UICONTROL フィルターをコピー]**&#x200B;ツールを次のように設定します。

   1. コピーするフィルターの直後に **[!UICONTROL 0}Source モジュール } をモジュールとして設定します。]**
   1. **[!UICONTROL ターゲットモジュール]** を、フィルターを直接配置するモジュールとして設定します。

1. 「**[!UICONTROL 実行]**」をクリックします。
