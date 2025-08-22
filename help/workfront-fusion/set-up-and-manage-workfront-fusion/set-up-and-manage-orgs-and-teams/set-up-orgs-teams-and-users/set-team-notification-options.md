---
title: チーム通知オプションの設定
description: メール通知オプションは、チームレベルで設定されます。
author: Becky
feature: Workfront Fusion
exl-id: 570a09fc-01a9-4952-8a2b-8bfdd86d0bd8
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 40%

---

# チーム通知オプションの設定

Adobe統合シェルを使用している組織では、Adobe通知エリアを通じて通知を受け取ります。

組織がAdobe統合シェルに移行されていない場合は、チームが受け取る通知を選択できます。 通知はチームレベルで設定されます。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の Workfront Fusion 管理者である必要があります。</p>
     <p>チームのWorkfront Fusion 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 通知オプションの設定

組織がAdobe統合シェル上にない場合は、Fusion で直接通知を設定できます。

メール通知オプションは、チームレベルで設定されます。

1. 左側のナビゲーションパネルで、「**[!UICONTROL チーム]**」をクリック
1. 「**[!UICONTROL 通知オプション]**」タブを選択します。
1. チームが受け取る通知を有効にします。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">「[!UICONTROL Warning in scenario run]」</td> 
      <td> <p>シナリオの実行で警告が発生した場合にメールを受信</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Errors in scenario run]</td> 
      <td>シナリオ実行でエラーが発生した場合に、メールを受け取ります。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Scenario deactivation]</p> </td> 
      <td><p>シナリオが非アクティブ化された場合、メールを受信します。</p><p>場合によっては、Workfront Fusion エンジニアリングチームがシナリオのアクティベートを解除することがあります。これは、シナリオがパフォーマンスやその他の問題を引き起こすためです。 このような場合、Workfront Fusion で通知は受け取りません。 </p></td>

</tr>
</tbody>
</table>

通知オプションに対する変更は、自動的に保存されます。
