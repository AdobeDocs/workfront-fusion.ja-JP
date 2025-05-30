---
content-type: reference
title: シナリオのスケジュール
description: デフォルトでは、シナリオは 15 分ごとに実行されます。アクティブ化されたシナリオを実行するタイミングと頻度を定義することで、これを変更できます。Fusion シナリオは、5 分ごとに実行するようにスケジュールできます。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9b74af0d-e7ff-4bf5-974e-0651d0d51f71
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 79%

---

# シナリオのスケジュール

デフォルトでは、シナリオは 15 分ごとに実行されます。アクティブ化されたシナリオを実行するタイミングと頻度を定義することで、これを変更できます。Fusion シナリオは、5 分ごとに実行するようにスケジュールできます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の [!DNL Workfront Fusion] 管理者である必要があります。</p>
     <p>チームの [!DNL Workfront Fusion] 管理者である必要があります。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] のライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  のライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## シナリオのスケジュール

1. 左側のパネルで「**シナリオ**」タブをクリックします。
1. スケジュールするシナリオを選択します。
1. シナリオの詳細ページの右上隅で、**[!UICONTROL Options]**/**[!UICONTROL Scheduling]** をクリックします

   または

   シナリオのトリガーモジュールの「**[!UICONTROL Scheduling]**」アイコン（時計）をクリックします。

1. 次のフィールドに情報を入力します。

   <table style="table-layout:auto">   
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Run scenario]</td> 
      <td> <p>シナリオを実行する頻度を選択し、間隔を選択します。</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL At regular intervals]</strong> </p> <p>実行間隔（分）を入力します。デフォルト値は 15 分です。</p> </li> 
        <li> <p><strong>[!UICONTROL Once]</strong> </p> <p>シナリオを実行する日時を入力します。<code>MM/DD/YYYY h:mm A</code> の形式を使用します。例：<code>06/25/2019 11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Every day]</strong> </p> <p>シナリオを実行する時間を入力します。<code>h:mm A</code> の形式を使用します。例：<code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Days of the week]</strong> </p> <p>日：シナリオを実行する曜日を選択します。1 つ以上の日を選択できます。</p> <p>時間：選択した日にシナリオを実行する時間を入力します。<code>h:mm A</code> の形式を使用します。例： <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Days of the month]</strong> </p> <p>日：シナリオを実行する日付を選択します。1 つ以上の日を選択できます。</p> <p>時間：選択した日にシナリオを実行する時間を入力します。<code>h:mm A</code> の形式を使用します。例： <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Specified dates]</strong> </p> <p>月：シナリオを実行する月を選択します。1 つ以上の月を選択できます。</p> <p>日：シナリオを実行する日付を選択します。1 つ以上の日を選択できます。</p> <p>時間：選択した日にシナリオを実行する時間を入力します。<code>h:mm A</code> の形式を使用します。例： <code>11:00 PM</code></p> </li> 
       </ul> <p>メモ：シナリオを実行するには、実行の日付が存在する必要があります。例えば、31日にスケジュールされているシナリオは、2月、4月、6月、9月、11月には実行されません。これらの月には 31日がないからです。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Advanced scheduling]</td> 
      <td>シナリオを実行する特定の期間を定義できます。時間間隔、平日、月を指定できます。各間隔に対して、「<strong>[!UICONTROL Add]</strong>」をクリックし、「[!UICONTROL Run scenario]」フィールドの説明に従ってフィールドに入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Start]</td> 
      <td>シナリオの実行を開始する日時を入力します。<code>MM/DD/YYYY h:mm A</code> 形式を使用します。例：<code>06/25/2019 11:00 PM</code></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL End]</td> 
      <td>シナリオの実行を終了する日時を入力します。<code>MM/DD/YYYY h:mm A</code> 形式を使用します。例：<code>06/25/2019 11:00 PM</code></td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL OK]**」をクリックして、スケジュール設定を保存し、シナリオに戻ります。
