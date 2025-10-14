---
title: cURL を使用した HTTP モジュールの追加
description: cURL リクエストをシナリオに貼り付けると、Fusion は cURL リクエストから設定された HTTP モジュールを作成します。
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 11%

---

# cURL を使用した HTTP モジュールの追加

cURL リクエストをシナリオに貼り付けると、Fusion は cURL リクエストから設定された HTTP モジュールを作成します。

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
   <td> <p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

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
