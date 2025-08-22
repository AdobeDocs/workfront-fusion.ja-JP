---
title: トリガーモジュールの開始場所を選択
description: 一部のトリガーモジュールでは、バンドルの取得を開始する最初のバンドルを選択できます。
author: Becky
feature: Workfront Fusion
exl-id: 83628fa5-82e2-4f67-bfed-70a4c3c19f7f
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 46%

---

# トリガーモジュールの開始場所を選択

一部のトリガーモジュールでは、バンドルの取得を開始する最初のバンドルを選択できます。

また、すべてのバンドルを取得するか、特定の日付以降のバンドルのみを取得するかを指定することもできます。

トリガーモジュールの詳細については、「モジュールの概要」の [トリガーモジュール ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) を参照してください。

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

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## トリガーモジュールの開始場所を選択

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. トリガーの開始位置を指定するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. トリガーモジュールを設定して保存します。

   または

   トリガーモジュールのアイコンを右クリックし、「**開始する場所を選択**」を選択します。

   ![ 開始場所を選択 ](assets/choose-where-to-start.png)

1. 表示される&#x200B;**[!UICONTROL 開始場所を選択]**&#x200B;ボックスでオプションを選択します。

   表示されるオプションは、特定のサービスの可能性に応じて異なります。含まれる可能性のあるものは、次のとおりです。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody>
    <tr>
    <td>[!UICONTROL From now on]（デフォルト）</td>
    <td>このオプションを選択した後に追加または更新されたすべてのバンドルを取得します（設定による）</td>
    </tr>
     <tr>
    <td>[!UICONTROL 特定の日付以降の]</td>
    <td>指定した日時以降に（設定に応じて）追加または更新されたすべてのバンドルを取得します</td>
      </tr>
      <tr>
    <td>[!UICONTROL All]</td>
    <td>使用可能なすべてのバンドルを取得します</td>
     </tr>
      <tr>
    <td>[!UICONTROL 手動で選択 &#x200B;]</td>
    <td>バンドルの取得を開始する最初のバンドルを選択できます</td>
     </tr>
     </tbody>
   </table>
