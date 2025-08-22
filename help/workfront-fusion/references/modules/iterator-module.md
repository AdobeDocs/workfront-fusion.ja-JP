---
title: Iterator モジュール
description: イテレータモジュールは、配列を一連のバンドルに変換する特別なタイプのモジュールです。各配列項目は、別々のバンドルとして出力されます。
author: Becky
feature: Workfront Fusion
exl-id: 43d39955-3dd7-453d-8eb0-3253a768e114
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 24%

---

# [!UICONTROL Iterator] モジュール

[!UICONTROL &#x200B; イテレータ &#x200B;] は、配列を一連のバンドルに変換するモジュールの一種です。 各配列項目は、別々のバンドルとして出力されます。

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
   <td> 新規：標準<p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] ライセンス</td> 
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


ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、Workfront 管理者にお問い合わせください。

Adobe Workfront Fusion ライセンスについては、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## [!UICONTROL イテレータ]モジュールの設定

一般的な Iterator モジュールには、[!UICONTROL &#x200B; 配列 &#x200B;] フィールドという単一のフィールドがあります。 このフィールドには、別々のバンドルに変換または分割される配列が含まれています。

![ イテレータの設定 ](assets/set-up-iterator.jpg)

その他のコネクタには、そのイテレータに固有のイテレータモジュールを含めることができます。 これらにはSource モジュールフィールドが含まれ、反復したい配列を出力するモジュールを選択できます。

![ 特殊なイテレータ ](assets/specialized-iterators.jpg)

詳しくは、[ モジュールの設定 ](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md) を参照してください。

>[!BEGINSHADEBOX]

**例：**

* 以下のシナリオは、添付ファイル付きのメールを取得し、その添付ファイルを選択した [!DNL Dropbox] フォルダーに 1 つのファイルとして保存する方法を示しています。

  メールには、添付ファイルの配列を含めることができます。最初のモジュールの後の [!UICONTROL Iterator] モジュールを使用すると、シナリオで各添付ファイルを個別に処理できます。 [!UICONTROL イテレータ]モジュールは、添付ファイルの配列を 1 つのバンドルに分割します。1 つの添付ファイルを含む各バンドルは、選択した [!DNL Dropbox] フォルダーに一度に 1 つずつ保存されます。Iterator モジュールの [!UICONTROL &#x200B; 配列 &#x200B;] フィールドには、`Attachments` 配列を含める必要があります。

  ![Attachments 配列 ](assets/attachments-array.jpg)

>[!ENDSHADEBOX]


## トラブルシューティング

### 問題：マッピングパネルの [!UICONTROL Iterator] モジュールの下にマッピング可能な項目が表示されない

[!UICONTROL Iterator] モジュールに配列の項目の構造に関する情報がない場合、[!UICONTROL Iterator] モジュールに続くモジュールのマッピングパネルには、[!UICONTROL Iterator] モジュールの下に 2 つの項目（`Total number of bundles` と `Bundle order position`）のみが表示されます。

![ マッピングパネルが表示されない ](assets/mapping-panel-doesnt-display.png)

これは、各モジュールが、出力する項目に関する情報を提供する責任を負い、これらの項目が後続のモジュールのマッピングパネルで適切に表示されるようにするためです。 ただし、モジュールによっては、この情報を提供できないことがあります。 例えば、データ構造が見つからない [!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] や [!UICONTROL Webhook]/[!UICONTROL &#x200B; カスタム Webhook] モジュールでは、情報が提供されません。

#### ソリューション

解決策は、シナリオを手動で実行することです。 これにより、モジュールは出力を作成します。 その後、Fusion は、この出力の形式をシナリオの新しいモジュールに適用できます。

例えば、シナリオにデータ構造のない [!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] モジュールが含まれているとします。

![JSON を解析](assets/json-parse-json.png)

この JSON モジュールに接続された [!UICONTROL Iterator] モジュールは、モジュールの出力を [!UICONTROL Iterator] モジュールのセットアップパネルの配列フィールドにマップできません。

![ イテレータモジュールを接続する ](assets/connect-iterator-module.png)

これを解決するには：

シナリオエディターでシナリオを手動で開始する

>[!NOTE]
>
>シナリオ全体が実行されないようにするには、次の操作を行います。
>
>* [!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] モジュールの後のモジュールのリンクを解除して、フローがさらに進行しないようにします。
>  &#x200B;>   または
>* [!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] モジュールを右クリックし、コンテキストメニューから **[!UICONTROL このモジュールのみを実行]** を選択して、[!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] モジュールのみを実行します。

[!UICONTROL JSON]/[!UICONTROL JSON を解析 &#x200B;] が実行されると、イテレータモジュールを含む後続のすべてのモジュールに出力に関する情報を提供できます。 イテレータの設定のマッピングパネルには、次の項目が表示されます。

![ マッピングパネルに項目が表示される ](assets/mapping-panel-displays-items.png)

さらに、[!UICONTROL Iterator] モジュールの後に接続されたモジュールのマッピングパネルには、配列に含まれる項目が表示されます。

![ 配列に含まれる項目 ](assets/items-contained-in-array.png)
