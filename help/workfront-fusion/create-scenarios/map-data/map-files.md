---
title: モジュール間でのファイルのマッピング
description: 一部のモジュールには、ファイルを処理する機能があります。 これらのモジュールは、さらなる処理のために送信される出力ファイルを返すことも、処理のためにファイルを渡すことを要求することもできます。 これらのモジュールが連携してファイルを処理できるようにするには、相互にマッピングする必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 25c632f4-169e-4d3c-989a-f57b398bd3f0
TQID: https://experienceleague.adobe.com/DVCy-0qCEuwZJqbGQPd3Pu9erVaX1wosPUWEtTFLkq4
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 412
ht-degree: 46%

---

# モジュール間でのファイルのマッピング

一部のモジュールはファイルを処理できます。 これらのモジュールは、さらに処理するために送信する出力ファイルを返すか、処理のためにファイルを渡す必要があります。 ファイルをマッピングできるため、あるモジュールによって出力されたファイルを別のモジュールで処理できます。

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

## ソースモジュールからターゲットモジュールへのファイルのマッピング

モジュールは、次の2つの情報を必要とするファイルを処理できます。

* ファイル名
* ファイルコンテンツ（データ）

以前のモジュールがファイルを出力した場合は、ソースモジュールを選択し、そのモジュールによって出力されたファイルの名前とデータがターゲットモジュールにマッピングされます。

この名前とデータを手動で入力したり、以前のモジュールからマッピングしたりすることもできます。 これは、例えばファイル名を変更する場合に便利です。

>[!NOTE]
>
>URL からファイルを処理する必要がある場合、`HTTP > Get a File` モジュールを使用して URL からファイルをダウンロードし、そのファイルを `HTTP > Get a File` モジュールからシナリオ内の目的のモジュールのフィールドにマッピングすることをお勧めします。
>
>![ マップファイル ](assets/map-source-file.png)

ファイルをマッピングするには：

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. ファイルをマッピングするシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. マッピング先のターゲットモジュールで、**Source ファイル**&#x200B;領域を見つけます。
1. 前のモジュールで出力されたファイルをマッピングするには、ファイルを出力するモジュールを選択します。

   ![Workfront ダウンロード ドキュメント ](assets/wf-download-document.png)

1. 名前とデータを手動でマッピングするには、「マップ」を選択し、ファイル名とデータを入力またはマッピングします。

   ![ マップオプションを使用](assets/use-the-map-option.png)

1. モジュールの設定を続行するか、**OK**&#x200B;をクリックします。
