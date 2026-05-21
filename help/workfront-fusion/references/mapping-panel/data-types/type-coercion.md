---
title: 型強制
description: このドキュメントでは、予期しないデータ形式で値を受け取った場合のAdobe Workfront Fusionの動作について説明します。
author: Becky
feature: Workfront Fusion
exl-id: a8bdd36d-c01f-4019-a3ea-fb185101500e
TQID: https://experienceleague.adobe.com/rqDQTI-IuOW95TbguHt-F2-4lugdaOfJf-7dcwXk5ZE
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 709
ht-degree: 60%

---

# 型強制

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">Adobe Workfront プラン*</td> 
   <td> <p>[!DNL Pro] またはそれ以降</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン*</td> 
   <td> <p>[!UICONTROL Plan]、[!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：Workfront Fusionのライセンスは必要ありません。</p>
   <p>または</p>
   <p>従来のライセンス要件：[!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select]または[!UICONTROL Prime] Adobe Workfront プランをお持ちの場合、この記事で説明する機能を使用するには、Adobe Workfront FusionとAdobe Workfrontを購入する必要があります。 Workfront Fusionは、[!UICONTROL Ultimate] Workfront プランに含まれています。</p>
   <p>または</p>
   <p>レガシー製品の要件：この記事で説明する機能を使用するには、Adobe Workfront FusionとAdobe Workfrontを購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、Workfront 管理者にお問い合わせください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

### 型強制

このドキュメントでは、予期しないデータ形式で値を受け取った場合のAdobe Workfront Fusionの動作について説明します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>予測</th> 
   <th>受信</th> 
   <th> <p>説明</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>配列 </td> 
   <td>配列 </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>配列 </td> 
   <td>その他 </td> 
   <td> <p>受け取った値が配列型でない場合、Workfront Fusionは配列を作成し、最初の（そして唯一の）要素が受け取った値になります。</p> </td> 
  </tr> 
  <tr> 
   <td>ブール値 </td> 
   <td>ブール値 </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>ブール値 </td> 
   <td>数値 </td> 
   <td> <p>値が 0 の場合でも、値は論理値 Yes に変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>ブール値 </td> 
   <td>テキスト </td> 
   <td> <p>値が false の場合、または値が空の場合は、論理値 No に変換されます。 そうでない場合は、論理値 Yes に変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>ブール値 </td> 
   <td>その他 </td> 
   <td> <p>受け取った値が存在する（null でない）場合、値は論理値 Yes に変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>バッファー </td> 
   <td>バッファー </td> 
   <td> <p>コードページが期待どおりの場合にのみ、値は変更されずに渡されます。 コードページが異なる場合、Workfront Fusionは、受信した値を要求されたコードページに変換しようとします。 この変換がサポートされていない場合、Workfront Fusionは検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>バッファー </td> 
   <td>ブール値 </td> 
   <td> <p>値はテキストに変換され（true または false）、前述の手順に従ってバイナリデータに変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>バッファー </td> 
   <td>日付 </td> 
   <td> <p>値は ISO 8601 テキストに変換され、その後、テキストへの変換の手順に従ってバイナリデータに変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>バッファー </td> 
   <td>数値 </td> 
   <td> <p>値はテキストに変換され、上記の手順に従ってバイナリデータに変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>バッファー </td> 
   <td>テキスト </td> 
   <td> <p>値はバイナリデータに変換され、想定どおりにエンコードされます。 想定されたエンコーディングが指定されていない場合は、utf8 エンコーディングが使用されます。</p> </td> 
  </tr> 
  <tr> 
   <td>バッファー </td> 
   <td>その他 </td> 
   <td> <p>Workfront Fusionが検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>コレクション </td> 
   <td>コレクション </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>コレクション </td> 
   <td>その他 </td> 
   <td> <p>Workfront Fusionが検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>日付 </td> 
   <td>日付 </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>日付 </td> 
   <td>テキスト </td> 
   <td> <p>Workfront Fusionは、テキストを日付に変換しようとします。 変換が失敗した場合は、検証エラーが返されます。 日付には、日、月、年を含める必要があります。 日付には、時間とタイムゾーンを含めることができます。 デフォルトのタイムゾーンは設定に基づいています。 例：</p> <p><code>2016-06-20T17:26:44.356Z</code> </p> <p><code>2016-06-20 19:26:44 GMT+02:00</code> </p> <p><code>2016-06-20 19:26+0200</code> </p> <p><code>2016-06-20 17:26:44</code> </p> <p><code>2016-06-20</code> </p> <p><code>2016/06/20 17:26:44</code> </p> <p><code>2016/06/20 19:26:44+02:00</code> </p> <p><code>2016/06/20 17:26</code> </p> <p><code>2016/06/20 5:26 PM</code> </p> <p><code>2016/06/20</code> </p> <p><code>06/20/2016 17:26:44</code> </p> <p><code>06/20/2016 19:26:44+02:00</code> </p> <p><code>06/20/2016 17:26</code> </p> <p><code>06/20/2016 5:26 PM</code> </p> <p><code>06/20/2016</code> </p> <p><code>20.6.2016 17:26:44</code> </p> <p><code>20.6.2016 19:26:44+02:00</code> </p> <p><code>20.6.2016 17:26</code> </p> <p><code>20.6.2016</code> </p> </td> 
  </tr> 
  <tr> 
   <td>date </td> 
   <td>その他 </td> 
   <td> <p>Workfront Fusionが検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>数値 </td> 
   <td>数値 </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>数値 </td> 
   <td>テキスト </td> 
   <td> <p>Workfront Fusionは、テキストを数値に変換しようとします。 変換が失敗した場合は、検証エラーが返されます。</p> </td> 
  </tr> 
  <tr> 
   <td>数値 </td> 
   <td>その他 </td> 
   <td> <p>Workfront Fusionが検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>テキスト </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>配列 </td> 
   <td> <p>指定された配列がテキストへの変換をサポートしている場合、値が変換されます。 そうでない場合、Workfront Fusionは検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>ブール値 </td> 
   <td> <p>値はテキストに変換されます（true または false）。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>バッファー </td> 
   <td> <p>バイナリデータに対してテキストエンコーディングが指定されている場合、値はテキストに変換されます。 そうでない場合、Workfront Fusionは検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>日付 </td> 
   <td> <p>値が ISO 8601 テキストに変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>数値 </td> 
   <td> <p>値がテキストに変換されます。</p> </td> 
  </tr> 
  <tr> 
   <td>テキスト </td> 
   <td>その他 </td> 
   <td> <p>Workfront Fusionが検証エラーを返します。</p> </td> 
  </tr> 
  <tr> 
   <td>時間 </td> 
   <td>時間 </td> 
   <td> <p>値は変更されずに引き渡されます。</p> </td> 
  </tr> 
  <tr> 
   <td>時間 </td> 
   <td>テキスト </td> 
   <td> <p>Workfront Fusionは、時間を<code>hours:minutes:seconds</code>形式に変換しようとします。 変換が失敗した場合は、検証エラーが返されます。</p> </td> 
  </tr> 
  <tr> 
   <td>時間 </td> 
   <td>その他 </td> 
   <td> <p>Workfront Fusionが検証エラーを返します。</p> </td> 
  </tr> 
 </tbody> 
</table>
