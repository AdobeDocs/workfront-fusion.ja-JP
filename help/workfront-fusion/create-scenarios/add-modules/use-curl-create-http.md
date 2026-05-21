---
title: cURL を使用した HTTP モジュールの追加
description: シナリオにcURL リクエストを貼り付けることができ、FusionはcURL リクエストから設定されたHTTP モジュールを作成します。
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
TQID: https://experienceleague.adobe.com/vPAMsVLVV7C3ykPPXgbMgDTosd0M3hYKYVL-OFszXqw
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 269
ht-degree: 39%

---

# cURL を使用した HTTP モジュールの追加

シナリオにcURL リクエストを貼り付けることができ、FusionはcURL リクエストから設定されたHTTP モジュールを作成します。

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

## cURL リクエストからHTTP モジュールを作成する


cURLを使用してHTTP モジュールを作成するには：

1. テキストエディターなど、Fusion以外でcURL リクエストのテキストを作成します。
1. cURL リクエストをクリップボードにコピーします。
1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. モジュールを作成するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. シナリオエディターの任意の空白を右クリックし、**貼り付け**&#x200B;を選択します。

   または

   Ctrl + V キー（Windows）またはCmd + V キー（Mac）を押します。


   HTML モジュールが作成されます。
1. モジュールをドラッグして、シナリオに接続します。

## トラブルシューティング

cURLがシナリオにペーストされていない場合は、ブラウザーの設定を確認して、クリップボードからのペーストが有効になっていることを確認します。
