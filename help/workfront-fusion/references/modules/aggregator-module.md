---
title: 集計モジュール
description: アグリゲーターモジュールは、複数のデータバンドルを 1 つのバンドルに結合するように設計されたモジュールの一種です。
author: Becky
feature: Workfront Fusion
exl-id: 93cde0d0-4013-463a-b19c-d58180632739
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 11%

---

# [!UICONTROL Aggregator] モジュール

アグリゲータモジュールは、複数のデータバンドルを 1 つのバンドルに結合するモジュールです。

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
   <td> 新規：標準<p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] ライセンス</td> 
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
 </tbody> 
</table>


ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

Adobe Workfront Fusion ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## [!UICONTROL Aggregator] モジュールの概要

[!UICONTROL Aggregator] モジュールを実行すると、次の処理が行われます。

* 単一のソースモジュールの操作からすべてのバンドルを蓄積します。
* 累積されたバンドルごとに 1 つの項目を含む配列を持つ単一のバンドルを出力します。 配列の項目の内容は、特定の [!UICONTROL Aggregator] モジュールとその設定によって異なります。

次の画像は、[!UICONTROL Aggregator] モジュールの一般的な設定を示しています。

![ 配列アグリゲータ ](assets/array-aggregator.png)

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source Module]</p> </td> 
   <td> <p>バンドル集計が開始するモジュール。 ソースモジュールは、通常、一連のバンドルを出力するイテレータまたは検索モジュールです。</p><p>アグリゲータのソースモジュールを設定（およびアグリゲータの設定を閉じる）すると、ソースモジュールとアグリゲータモジュールの間のルートがグレーの領域で囲まれ、集計の開始と終了が明確に表示されます。 
   </p> <p>イテレータについて詳しくは、<a href="/help/workfront-fusion/references/modules/iterator-module.md" class="MCXref xref">[!UICONTROL Iterator] モジュール </a> を参照してください。</p> 
   <p>検索モジュールについて詳しくは、「モジュールの概要」の <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#search-modules" class="MCXref xref"> 検索モジュール </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Target structure type]</p><p>（[!UICONTROL Array aggregator] モジュールにのみ適用）</p> </td> 
   <td> <p> データが集計されるターゲット構造。 デフォルトのオプション [!UICONTROL Custom] を使用すると、[!UICONTROL Array aggregator] の出力バンドルの <code>Array </code>item に集計する項目を選択できます。</p> <p> <img src="assets/output-bundle-array-item.png"> </p> <p>[!UICONTROL Array aggregator] モジュールの後にさらにモジュールを接続し、集約モジュールの設定に戻ると、「[!UICONTROL Target] 構造タイプ」ドロップダウンメニューには、次のモジュールとその「コレクションの配列」タイプのフィールドがすべて含まれます。 <p>この例では、[!DNL Slack] &gt;[!UICONTROL Create a Message] モジュールの [!UICONTROL Attachments] フィールドが、配列アグリゲータ / ターゲット構造タイプ フィールドに表示されます。 </p> <p> <img src="assets/array-aggregator-slack.png"> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Aggregated fields]</td> 
   <td>集計モジュールの出力に含めるフィールド。</td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>「グループ化」フィールドを使用すると、1 つ以上のマッピングされた項目を含む式を定義できます。 集計データは、式の値によってグループに分けられます。 各グループは、キーとデータの配列を含む個別のバンドルとして出力します。 結果をグループ化することで、後続のモジュールでキーをフィルターとして使用できます。</p>
   <p>各バンドルには、次の 2 つの項目が含まれます。</p> 
    <ul> 
     <li><code>Key</code>：グループ化の基準にする値。</li> 
     <li><code>Array</code>:<code>Key</code> 値に対して評価された式の対象となるバンドルからの集計データ。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <p>空の集計後に処理を停止</p> </td> 
   <td> <p>デフォルトでは、[!UICONTROL Aggregator] モジュールは、バンドルが [!UICONTROL Aggregator] モジュールに到達しなかった場合（例えば、バンドルがすべてアグリゲータを含むパスから除外されている場合）でも、集計の結果を出力します。 オプション [!UICONTROL Stop processing after an empty aggregation] が有効になっている場合、[!UICONTROL Aggregator] モジュールは、入力バンドルがないときに出力バンドルを生成しません。 代わりに、フローが停止します。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>ソースモジュールとソースモジュール間のモジュールによって生成されたバンドルは、[!UICONTROL Aggregator] ース [!UICONTROL Aggregator] ジュールによって出力されません。 これらのバンドルは、[!UICONTROL Aggregator] 後のフローのモジュールからアクセスできません。 ソースモジュールと [!UICONTROL Aggregator] モジュールの間で、モジュールによって出力されるバンドルからのデータが必要な場合は、特定の項目を [!UICONTROL Aggregator] モジュールの設定（[!UICONTROL Array aggregator] モジュールの設定の [!UICONTROL Aggregated fields] フィールドなど）に必ず含めてください。


## アグリゲータの動作のシナリオの例

このサンプルシナリオでは、すべてのメール添付ファイルを zip で圧縮し、その ZIP ファイルを [!DNL Dropbox] にアップロードする方法を示します。

![Dropboxアーカイブの例 ](assets/dropbox-archive.png)

以下のシナリオでは、次の方法を示します。

* 最初のモジュールは、受信メールのメールボックスを監視します。 [!UICONTROL Email] >[!UICONTROL Watch emails] トリガーは、項目 `Attachments[]` を含むバンドルを出力します。これは、メールのすべての添付ファイルを含む配列です。

* 2 つ目のモデルは、メールの添付ファイルを反復します。[!UICONTROL Email] >[!UICONTROL Iterate attachments] イテレータは、`Attachments[]` 配列から項目を 1 つずつ取得し、それらを別々のバンドルとしてさらに送信します。

* 3 番目のモジュールはアグリゲータです。 [!UICONTROL Email] >[!UICONTROL Iterate attachments] モジュールによって出力されたバンドルを集計します。 [!UICONTROL Archive] >[!UICONTROL Create an archive aggregator] は、受け取ったすべてのバンドルを蓄積し、ZIP ファイルを含む単一のバンドルを出力します。

* 最後のモジュールは、結果の ZIP ファイルを [!DNL Dropbox] にアップロードします。  [!DNL Dropbox] > [!UICONTROL Upload a file] は、[!UICONTROL Archive] > [!UICONTROL Create an archive] モジュールから ZIP ファイルを取得し、[!DNL Dropbox] にアップロードします。



[!UICONTROL Archive]/[!UICONTROL Create an archive] アグリゲータの設定例を次に示します。

![アーカイブを作成](assets/archive-create-an-archive.png)
