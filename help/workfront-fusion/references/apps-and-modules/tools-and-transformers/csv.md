---
title: CSV
description: Adobe Workfront Fusion CSV モジュールを使用すると、CSV ファイルを作成し、受け取ったテキスト値またはファイルから CSV テキストを解析できます。
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
TQID: https://experienceleague.adobe.com/IhvuQxLno-vVgIWarBZG-EFSeu8shwQpZmce7PRBVQs
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 941
ht-degree: 56%

---

# CSV

Adobe Workfront Fusion [!UICONTROL CSV] モジュールを使用すると、CSV ファイルを作成し、受信したテキスト値またはファイルからCSV テキストを解析できます。

これはトランスであるため、これらのモジュールは接続を必要としません。

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



## [!UICONTROL CSV を作成]

[!UICONTROL CSV を作成]アグリゲータを使用すると、受け取ったテキスト値から CSV テキストを作成できます。

アグリゲーターについて詳しくは、[&#x200B; アグリゲーターモジュール &#x200B;](/help/workfront-fusion/references/modules/aggregator-module.md)を参照してください。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>CSVの作成に使用するフィールドを出力するモジュールを選択します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Aggregated Fields]</td>
        <td>集計するフィールドを、使用可能なフィールドのリストから選択します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Include headers in the first row]</td>
        <td>結果にヘッダーを含める場合は、このオプションを選択します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Group by]</td>
        <td>結果をグループ化するフィルターを入力します。 例えば、日付を入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Stop processing after an empty aggregation]</td>
        <td>結果がない場合にシナリオを停止するには、このオプションを選択します。</td>
    </tr>
</table>

## [!UICONTROL CSV を作成（詳細）]

[!UICONTROL CSV を作成（詳細）]アグリゲータを使用すると、受け取ったテキスト値から CSV テキストを作成できます。 結果の CSV ファイルで CSV 列を定義するデータ構造を使用しています。 定義が完了すると、列は CSV モジュール設定のフィールドとして表示され、シナリオの後のモジュールにマッピングできます。

アグリゲーターについて詳しくは、[&#x200B; アグリゲーターモジュール &#x200B;](/help/workfront-fusion/references/modules/aggregator-module.md)を参照してください。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
        <td>CSVの作成に使用するフィールドを出力するモジュールを選択します。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>必要な方法でフィールドを集計するデータ構造を選択します。 データ構造を定義した後、項目を対応するフィールドにマッピングできます。</p> <p>詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref"> データ構造</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include headers in the first row] </td> 
   <td>結果にヘッダーを含める場合は、このオプションを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by] </td> 
   <td>結果をグループ化するフィルターを入力します。 例えば、日付を入力します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation] </td> 
   <td>結果がない場合にシナリオを停止するには、このオプションを選択します。 </td> 
  </tr> 
 </tbody> 
</table>


>[!BEGINSHADEBOX]

**例**：

この例では、「フルネーム」と「電子メール」という2つの列を持つCSV ファイルにGoogleの連絡先をエクスポートする方法を示します。 [!UICONTROL Google連絡先] > [!UICONTROL &#x200B; グループ &#x200B;] モジュールから連絡先を取得する出力バンドルの構造は、次のとおりです。 電子メールアドレスは、<code>[!UICONTROL 電子メール []]内に保存されます</code> item。コレクションの配列で、各コレクションには2つのアイテムが含まれています：<code>Label</code> および<code> メール</code>.
![変形](/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png)

シンプルな[!DNL Create CSV] モジュールには、バンドルの最上位の項目に対応するチェックボックスのリストが表示されます。 <code>氏名を選択しようとすると</code> と<code> メール</code> itemsの場合、[!UICONTROL Create CSV] モジュールは次の出力を生成しますが、これは目的とは異なる場合があります。

```
"emails","fullName"
"[object Object]","Shon Winer"
"[object Object]","Lizeth Fulmore"
"[object Object]","Hilario Gullatt"
"[object Object]","Abby Eisenbarth"
```

項目<code>Full Nameのため</code> はシンプルなタイプのテキストで、期待どおりに書き出されます。 アイテム <code>の電子メール</code>は、複雑なタイプのコレクションの配列で、[ オブジェクトオブジェクト ]として書き出されます。これは、コレクションと配列がデフォルトでテキストに変換される方法です。

詳しくは、[項目データタイプ](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md)を参照してください。


<code> メールのコンテンツを書き出すには </code><code>電子メール []の最初のコレクションのアイテム</code> 代わりに、[!UICONTROL Create CSV （advanced） &#x200B;] モジュールを使用する必要があります。 このモジュールを使用すると、CSV ファイルの個々の列を定義し、ネストされた列を含むアイテムをそれにマッピングできます。

1. モジュール [!UICONTROL Create CSV （advanced） &#x200B;]をシナリオに挿入します。
1. 「[!UICONTROL &#x200B; データ構造]」フィールドの横にある「<strong>[!UICONTROL 追加]</strong>」ボタンをクリックして、新しいデータ構造を作成します。
1. データ構造の名前を入力し、<strong>[!UICONTROL 項目を追加]</strong>をクリックして個々の列を追加します。 「フルネーム」と「電子メール」の2つの列を書き出すと、結果のデータ構造は次のようになります。

   ![Google連絡先出力](/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png)

1. データ構造を定義すると、各列に対応するフィールドが[!UICONTROL Create CSV （advanced） &#x200B;] モジュールの設定に表示されるので、項目をマッピングできます。 <code>[!UICONTROL 電子メール []]の最初の項目を取得</code> アイテム <code>の配列とマッピングの電子メール </code>フィールド/列に電子メール：

   ![CSV詳細モジュールの作成](/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png)

1. シナリオを実行します。 アイテム <code> メール [1]のため：メール</code> 「メール」列にマッピングされたメールは、単純なタイプのテキストで、正しく書き出されます。

```
"Full Name","Email"
"Shon Winer","Shon@Winer.com"
"Lizeth Fulmore","Lizeth@Fulmore.com"
"Hilario Gullatt","Hilario@Gullatt.com"
"Abby Eisenbarth","Abby@Eisenbarth.com"
```

>[!ENDSHADEBOX]

## [!UICONTROL CSV の解析]

[!UICONTROL CSV を解析]変換サービスを使用すると、受け取ったテキスト値またはファイルから CSV テキストを解析できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of columns]</td> 
   <td>CSV ファイルの列数を指定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV contains headers]</td> 
   <td> <p>CSV テキストの最初の行がヘッダーの場合は、このオプションを選択します。</p> <p>メモ：このモジュールでは、ヘッダーを使用して出力の列にラベルを付けません。 このフィールドは、ヘッダーが出力データに含まれないようにします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL delimiterType]</td> 
   <td> <p>CSV ファイルの区切り文字を選択します。 区切り文字は、値の区切りまたはフィールド間の境界を示すテキスト文字です。</p> 
    <ul> 
     <li>[!UICONTROL Comma]</li> 
     <li>[!UICONTROL Tab]</li> 
     <li> <p>[!UICONTROL Other]</p> <p>[!UICONTROL Other] を選択した場合は、値を区切るために CSV ファイルで使用する区切り文字を入力します。 正確に 1 文字を入力する必要があります。<br></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Preserve quotes inside unquoted field]</td> 
   <td>引用符を保持するには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV]</td> 
   <td>解析する CSV ファイルを入力またはマッピングします。<p>メモ： <p>データが（通常はファイルから）バイナリ形式で取得される場合は、「toString()」関数を使用してバイナリデータを [!UICONTROL String] に変換する必要があります。</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png"></p></p></td> 
  </tr> 
 </tbody> 
</table>
