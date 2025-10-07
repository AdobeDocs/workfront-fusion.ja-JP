---
title: モジュールを新しいバージョンに更新する
description: Workfront Fusion が接続するアプリケーションは新しいバージョンをアップデートまたはリリースする可能性があるので、Fusion がそれらのアプリケーションのアップデートされたモジュールをリリースする必要が生じる場合があります。
author: Becky
feature: Workfront Fusion
exl-id: b7f07fa5-9d81-48b3-b0ce-7a18b3b44508
source-git-commit: d0d9d7cdad993ecceaa0abf0ac69e9a9abd78b69
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 13%

---

# モジュールの新しいバージョンへのアップグレード

Workfront Fusion が接続するアプリケーションは新しいバージョンをアップデートまたはリリースする可能性があるので、Fusion がそれらのアプリケーションのアップデートされたモジュールをリリースする必要が生じる場合があります。

シナリオでモジュールに緑色の「アップグレードモジュール」アイコンが表示された場合、Workfront Fusion はそのモジュールの新しいバージョンをリリースしました。

![&#x200B; 更新アイコン &#x200B;](assets/update-indicator-workfront.png)

新しいシナリオを作成しなくても、モジュールを更新できます。

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Workfront モジュールの新しいバージョンへのアップグレード

1. 新しいバージョンにアップグレードするモジュールの **アップグレードモジュール** アイコン ![&#x200B; アップグレードアイコン &#x200B;](assets/upgrade-icon.png) をクリックします。
   ![&#x200B; 更新アイコン &#x200B;](assets/update-indicator-workfront.png)
1. 以下のうちのいずれかを選択します。

   * このモジュールを交換する新しいモジュールを選択する（モジュールをアップグレードする代わりに）には、**新規を選択** をクリックし、[Workfront以外のモジュールを新しいバージョンにアップグレード &#x200B;](#upgrade-a-non-workfront-module-to-a-new-version) の説明に従って作業を進めます。
   * モジュールの構成を維持したまま、このモジュールのみをアップグレードするには、[**アップグレード**] をクリックします。
   * シナリオに含まれるすべてのWorkfront モジュールをアップグレードするには、「**すべてアップグレード**」をクリックします。

1. シナリオを保存します。

>[!NOTE]
>
>Workfront モジュールをアップグレードしている場合は、モジュールを開いて、モジュールの設定を確認することをお勧めします。

## Workfront以外のモジュールを新しいバージョンにアップグレードする

1. 新しいバージョンにアップグレードするモジュールの **アップグレードモジュール** アイコン ![&#x200B; アップグレードアイコン &#x200B;](assets/upgrade-icon.png) をクリックします。
   ![&#x200B; 更新アイコン &#x200B;](assets/update-indicator.png)
1. **新規を選択** をクリックします。
1. 前のモジュールと置き換えるモジュールを選択します。
1. 既存のモジュールと同じ設定でモジュールを設定します。
1. 既存のモジュールと同じ場所にあるシナリオに新しいモジュールを接続します。
1. 古いモジュールを削除します。
1. シナリオを保存します。
