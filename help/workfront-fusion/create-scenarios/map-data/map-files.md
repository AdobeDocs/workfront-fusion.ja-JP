---
title: モジュール間でのファイルのマッピング
description: 一部のモジュールには、ファイルを処理する機能があります。これらのモジュールは、さらなる処理のために送信される出力ファイルを返すことも、処理のためにファイルを渡すことを要求することもできます。これらのモジュールが連携してファイルを処理できるようにするには、相互にマッピングする必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 25c632f4-169e-4d3c-989a-f57b398bd3f0
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 25%

---

# モジュール間でのファイルのマッピング

一部のモジュールはファイルを処理できます。 これらのモジュールは、さらなる処理のために送信される出力ファイルを返すか、または処理のためにファイルを渡す必要があります。 ファイルをマッピングできるので、あるモジュールが出力したファイルを別のモジュールで処理できます。

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

## ソースモジュールからターゲットモジュールへのファイルのマッピング

モジュールは、次の 2 つの情報を必要とするファイルを処理できます。

* ファイル名
* ファイルコンテンツ（データ）

以前のモジュールがファイルを出力する場合は、ソースモジュールを選択すると、そのモジュールが出力するファイルの名前とデータがターゲットモジュールにマッピングされます。

また、この名前とデータを手動で入力するか、以前のモジュールからマッピングすることもできます。 これは、例えばファイル名を変更する場合に便利です。

>[!NOTE]
>
>URL からファイルを処理する必要がある場合、`HTTP > Get a File` モジュールを使用して URL からファイルをダウンロードし、そのファイルを `HTTP > Get a File` モジュールからシナリオ内の目的のモジュールのフィールドにマッピングすることをお勧めします。
>
>![ マップファイル ](assets/map-source-file.png)

ファイルをマッピングするには：

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. ファイルをマッピングするシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. マッピング先のターゲットであるターゲットモジュールで、**Source ファイル** 領域を見つけます。
1. 以前のモジュールで出力されたファイルをマッピングするには、ファイルを出力するモジュールを選択します。

   ![Workfront ダウンロード ドキュメント ](assets/wf-download-document.png)

1. 名前とデータを手動でマップするには、「マップ」を選択してから、ファイルの名前とデータを入力またはマップします。

   ![ マップオプションを使用 ](assets/use-the-map-option.png)

1. モジュールの設定を続行するか、[**OK**] をクリックします。
