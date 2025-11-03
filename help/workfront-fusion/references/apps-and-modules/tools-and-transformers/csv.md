---
title: CSV
description: Adobe Workfront Fusion CSV モジュールを使用すると、CSV ファイルを作成し、受け取ったテキスト値またはファイルから CSV テキストを解析できます。
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 47%

---

# CSV

Adobe Workfront Fusion [!UICONTROL CSV] モジュールを使用すると、CSV ファイルを作成し、受信したテキスト値やファイルから CSV テキストを解析できます。

これはトランスなので、これらのモジュールには接続は必要ありません。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++



## [!UICONTROL CSV を作成]

[!UICONTROL CSV を作成]アグリゲータを使用すると、受け取ったテキスト値から CSV テキストを作成できます。

アグリゲータの詳細については、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>CSV の作成に使用するフィールドを出力するモジュールを選択します。</td>
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
        <td>結果をグループ化するフィルターを入力します。例えば、日付を入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Stop processing after an empty aggregation]</td>
        <td>結果がない場合にシナリオを停止するには、このオプションを選択します。</td>
    </tr>
</table>

## [!UICONTROL CSV を作成（詳細）]

[!UICONTROL CSV を作成（詳細）]アグリゲータを使用すると、受け取ったテキスト値から CSV テキストを作成できます。結果の CSV ファイルで CSV 列を定義するデータ構造を使用しています。定義が完了すると、列は CSV モジュール設定のフィールドとして表示され、シナリオの後のモジュールにマッピングできます。

アグリゲータの詳細については、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
        <td>CSV の作成に使用するフィールドを出力するモジュールを選択します。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>必要な方法でフィールドを集計するデータ構造を選択します。データ構造を定義した後、項目を対応するフィールドにマッピングできます。</p> <p>詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref"> データ構造 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include headers in the first row] </td> 
   <td>結果にヘッダーを含める場合は、このオプションを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by] </td> 
   <td>結果をグループ化するフィルターを入力します。例えば、日付を入力します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation] </td> 
   <td>結果がない場合にシナリオを停止するには、このオプションを選択します。 </td> 
  </tr> 
 </tbody> 
</table>


>[!BEGINSHADEBOX]

**例**：

この例では、「Full Name」と「Email」という 2 つの列を持つ CSV ファイルにGoogleの連絡先を書き出す方法を示しています。 [!UICONTROL Googleの連絡先 ] / [!UICONTROL  グループから連絡先を取得 ] モジュールの出力バンドルは、次の構造になっています。 メールアドレスは、<code>[!UICONTROL  メール []] 内に保存されます</code> item はコレクションの配列で、各コレクションには 2 つの項目が含まれています。<code>Label</code> と <code> メール</code>.
![ 変換 ](/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png)

シンプルな [!DNL Create CSV] モジュールは、バンドルの最上位レベルの項目に対応するチェックボックスのリストを提供します。 <code>Full name</code> と <code> メール</code> [!UICONTROL CSV を作成 ] モジュールでは、要求とは異なる次のような出力が生成されます。

```
"emails","fullName"
"[object Object]","Shon Winer"
"[object Object]","Lizeth Fulmore"
"[object Object]","Hilario Gullatt"
"[object Object]","Abby Eisenbarth"
```

項目 <code>Full Name</code> は単純なタイプ Text であり、期待どおりに書き出されます。 項目 <code> メール</code>はコレクションの複合型の配列であり、[object オブジェクト ] として書き出されます。このオブジェクトは、コレクションと配列がデフォルトでテキストに変換される方法です。

詳細については、「[ アイテム データ タイプ ](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md)」を参照してください。


<code>E メールのコンテンツをエクスポートするには </code><code>Emails[] の最初のコレクションの項目</code> 代わりに、配列 [!UICONTROL CSV を作成（詳細） ] モジュールを使用する必要があります。 このモジュールを使用すると、CSV ファイルの個々の列を定義し、ネストされた列を含め、それらの列に項目をマッピングできます。

1. モジュール [!UICONTROL CSV を作成（詳細） ] をシナリオに挿入します。
1. 「<strong>[!UICONTROL  データ構造 ]</strong>」フィールドの横にある「[!UICONTROL  追加 ]」ボタンをクリックして、新しいデータ構造を作成します。
1. データ構造の名前を入力し、「<strong>[!UICONTROL  項目を追加 ]</strong>」をクリックして個々の列を追加します。 「Full Name」と「Email」の 2 つの列を書き出すには、結果のデータ構造は次のようになります。

   ![Google連絡先の出力 ](/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png)

1. データ構造を定義すると、個々の列に対応するフィールドが [!UICONTROL CSV を作成（詳細） ] モジュールの設定に表示され、項目をマッピングできます。 <code>[!UICONTROL  メール []] の最初の項目を取得</code> 配列とその項目のマッピング <code> メール </code>フィールド/列の「電子メール」に対して、次の操作を行います。

   ![CSV 詳細モジュールの作成 ](/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png)

1. シナリオを実行します。項目 <code>Emails[1]:Email のため</code> 列「メール」にマッピングされたは単純なタイプのテキストであり、正しく書き出されます。

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
   <td> <p>CSV テキストの最初の行がヘッダーの場合は、このオプションを選択します。</p> <p>メモ：このモジュールでは、ヘッダーを使用して出力の列にラベルを付けません。このフィールドは、ヘッダーが出力データに含まれないようにします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL delimiterType]</td> 
   <td> <p>CSV ファイルの区切り文字を選択します。区切り文字は、値の区切りまたはフィールド間の境界を示すテキスト文字です。</p> 
    <ul> 
     <li>[!UICONTROL Comma]</li> 
     <li>[!UICONTROL Tab]</li> 
     <li> <p>[!UICONTROL Other]</p> <p>[!UICONTROL Other] を選択した場合は、値を区切るために CSV ファイルで使用する区切り文字を入力します。正確に 1 文字を入力する必要があります。<br></p> </li> 
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
