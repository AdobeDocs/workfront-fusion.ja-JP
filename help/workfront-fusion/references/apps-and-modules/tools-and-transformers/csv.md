---
title: CSV
description: Adobe Workfront Fusion CSV モジュールを使用すると、CSV ファイルを作成し、受け取ったテキスト値またはファイルから CSV テキストを解析できます。
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 69%

---

# CSV

[!DNL Adobe Workfront Fusion] [!UICONTROL CSV] モジュールを使用すると、CSV ファイルを作成し、受信したテキスト値またはファイルから CSV テキストを解析できます。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration], [!UICONTROL [!DNL Workfront Fusion] for Work Automation]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## [!UICONTROL Create CSV]

[!UICONTROL Create CSV] アグリゲータを使用すると、受信したテキスト値から csv テキストを作成できます。

アグリゲータの詳細については、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>必要なフィールドの集計に使用するモジュールを選択します。</td>
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

## [!UICONTROL Create CSV (advanced)]

[!UICONTROL Create CSV (advanced)] アグリゲータを使用すると、受信したテキスト値から CSV テキストを作成できます。 結果の CSV ファイルで CSV 列を定義するデータ構造を使用しています。定義が完了すると、列は CSV モジュール設定のフィールドとして表示され、シナリオの後のモジュールにマッピングできます。

アグリゲータについて詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/modules/aggregator-module.md) のアグリゲータモジュールを参照してください。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td>必要なフィールドを集計するために使用するアプリモジュールを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>必要な方法でフィールドを集計するデータ構造を選択します。データ構造を定義した後、項目を対応するフィールドにマッピングできます。</p> <p>詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> のデータ構造を参照してください。</p> </td> 
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


<p>Google の連絡先を、「姓名」と「メール」の 2 つの列を持つ CSV ファイルにエクスポートするとします。[!UICONTROL Google Contacts] &gt;[!UICONTROL Get contacts from a group] モジュールからの出力バンドルの構造は次のとおりです。 メールアドレスは、コレクションの配列である <code>[!UICONTROL Emails[]]</code> 項目内に格納され、各コレクションには <code>Label</code> および <code>Email</code> の 2 つの項目が含まれます。</p>
<p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png" style="width: 350;height: 546;"> </p>
<p>シンプルな [!DNL Create CSV] モジュールを使用する場合、バンドルの最上位項目に対応するチェックボックスのリストが提供されます。<code>Full name</code> と <code>Emails</code> の項目にチェックマークを付けようとすると、[!UICONTROL Create CSV] モジュールは次のような出力を生成しますが、これはおそらく目的とは異なります。</p>
<p>"emails","fullName"</p>
<p>"[object Object]","Shon Winer"</p>
<p>"[object Object]","Lizeth Fulmore"</p>
<p>"[object Object]","Hilario Gullatt"</p>
<p>"[object Object]","Abby Eisenbarth"</p>
<p>項目 <code>Full Name</code> は単純なタイプのテキストであるため、正常にエクスポートされます。しかし項目 <code>Emails</code> は複雑なタイプのコレクションの配列であるため、[object Object] としてエクスポートされます。これは、コレクションと配列がデフォルトでテキストに変換される方法です。詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Adobe Workfront Fusion の項目のデータ型</a>を参照してください。</p>
<p>代わりに、<code>Emails[]</code> 配列の最初のコレクションの <code>Email </code> 項目のコンテンツを書き出すには、[!UICONTROL Create CSV (advanced)] モジュールを使用する必要があります。 このモジュールを使用すると、CSV ファイルの個々の列を定義し、ネストされた列を含む項目をそれらの列にマッピングできます。</p>
<ol>
<li value="1">モジュール [!UICONTROL Create CSV (advanced)] をシナリオに挿入し、設定を開きます。</li>
<li value="2">[!UICONTROL Data structure] フィールドの横にある「<strong>[!UICONTROL Add]</strong>」ボタンをクリックして、新しいデータ構造を作成します。</li>
<li value="3"> <p>データ構造の名前を入力し、「<strong>[!UICONTROL Add item]</strong>」ボタンをクリックして個々の列を追加します。 「フルネーム」と「メール」の 2 つの列をエクスポートする場合、結果のデータ構造は次のようになります。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png" style="width: 350;height: 524;"> </p> </li>
<li value="4"> <p>データ構造を正常に定義したら、個々の列に対応するフィールドが [!UICONTROL Create CSV (advanced)] モジュールの設定に表示されるので、項目をマッピングできます。 <code>[!UICONTROL Emails[]]</code> 配列から最初の項目を取得し、その項目 <code>Email </code> を「メール」フィールド（列）にマッピングします。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png" style="width: 350;height: 308;"> </p> </li>
<li value="5"> <p>シナリオを実行します。「メール」列にマッピングされた <code>Emails[1]: Email</code> 項目は単純なタイプのテキストであるため、正常にエクスポートされるようになりました。</p> <p>"Full Name","Email"</p> <p>"Shon Winer","Shon@Winer.com"</p> <p>"Lizeth Fulmore","Lizeth@Fulmore.com"</p> <p>"Hilario Gullatt","Hilario@Gullatt.com"</p> <p>"Abby Eisenbarth","Abby@Eisenbarth.com"</p> </li>
</ol>
</div>

## [!UICONTROL Parse CSV]

[!UICONTROL Parse CSV] トランスフォーマーを使用すると、受信したテキスト値やファイルから CSV テキストを解析できます。

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
     <li> <p>[!UICONTROL Other]</p> <p>「[!UICONTROL Other]」を選択した場合は、CSV ファイルで値の区切りに使用する区切り文字を入力します。 正確に 1 文字を入力する必要があります。<br></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Preserve quotes inside unquoted field]</td> 
   <td>引用符を保持するには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV]</td> 
   <td>解析する CSV ファイルを入力またはマッピングします。<p>メモ： <p>データがバイナリ形式（通常はファイルから）の場合、「toString （）」関数を使用してバイナリデータを [!UICONTROL String] に変換する必要があります。</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png" style="width: 350;height: 123;"></p></p></td> 
  </tr> 
 </tbody> 
</table>
