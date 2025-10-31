---
title: cURL を使用した HTTP モジュールの追加
description: cURL リクエストをシナリオに貼り付けると、Fusion は cURL リクエストから設定された HTTP モジュールを作成します。
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 4%

---

# cURL を使用した HTTP モジュールの追加

cURL リクエストをシナリオに貼り付けると、Fusion は cURL リクエストから設定された HTTP モジュールを作成します。

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++

## cURL リクエストからの HTTP モジュールの作成


cURL を使用して HTTP モジュールを作成するには：

1. Fusion の外部（テキストエディターなど）で cURL リクエストのテキストを作成します。
1. cURL リクエストをクリップボードにコピーします。
1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. モジュールを作成するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. シナリオエディターの任意の空白を右クリックして、「**貼り付け**」を選択します。

   または

   Ctrl + V （Windows）または Cmd + V （Mac）を押します。


   HTML モジュールが作成されます。
1. モジュールをドラッグして、シナリオに接続します。

## トラブルシューティング

cURL がシナリオに貼り付けられていない場合は、ブラウザー設定を調べ、クリップボードからの貼り付けが有効になっていることを確認します。
