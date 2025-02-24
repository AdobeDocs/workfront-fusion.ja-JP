---
title: XML
description: XML アプリを使用すると、XML／Parse XML モジュールを介して XML 形式のテキストを解析し、バンドルに変換して、他のモジュールでデータの使用が可能になります。XML／Create XML モジュールを使用して、バンドルを XML 形式のテキストに変換することもできます。
author: Becky
feature: Workfront Fusion
exl-id: ab323361-cd04-4dcc-ab02-0fb468334fdb
source-git-commit: 5351c2386ed6f2d030df1df01fcf9ea0de7d813f
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 55%

---

# XML

[!UICONTROL XML] アプリを使用すると、[!UICONTROL XML]/[!UICONTROL Parse XML] モジュールを介して XML 形式のテキストを解析し、バンドルに変換して、他のモジュールでデータを使用できるようになります。 また、[!UICONTROL XML] / [!UICONTROL Create XML] モジュールを使用して、バンドルを XML 形式のテキストに変換できます

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
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>Workfront Fusion のライセンス要件はありません。</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## XML を作成

[!UICONTROL XML]/[!UICONTROL Create XML] モジュールは、バンドルを XML 形式のテキストに変換します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Data structure]</p> </td> 
   <td> <p>データ構造は、結果の XML の構造を記述します。作成する XML のサンプルがある場合は、それを使用してデータ構造を生成できます。</p> 
    <ol> 
     <li value="1"><strong>[!UICONTROL Add]</strong> ボタンをクリックします。</li> 
     <li value="2"><strong>[!UICONTROL Generator]</strong> ボタンをクリックします。</li> 
     <li value="3">XML サンプルをコピーして、「サンプルデータ」フィールドに貼り付けます。</li> 
     <li value="4"><strong>[!UICONTROL Save]</strong> ボタンをクリックします。</li> 
     <li value="5">データ構造が正常に生成されたことを確認します。</li> 
     <li value="6">「<strong>[!UICONTROL Save]</strong>」をクリックして、データ構造を保存します。</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Root element name]</td> 
   <td>XML のルート要素の名前を入力します。デフォルト値は <code>root</code> です。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Doctype SYSTEM ID]</td> 
   <td><code>!DOCTYPE SYSTEM</code> の宣言で使用するファイル名を入力してください</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Doctype PUBLIC ID]</td> 
   <td><code>!DOCTYPE PUBLIC</code> の宣言で使用するファイル名を入力してください</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Strip Xml Declaration]</td> 
   <td>XML 宣言 <code>&lt;?xml ... ?&gt;</code> と <code>&lt;!DOCTYPE ... &gt;</code> を削除し、XML ルート要素とその内容だけを残すには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例：**

一般的なユースケースは、[!DNL Google] スプレッドシートを XML に変換することです。

1. [!DNL Google Sheets]/[!UICONTROL Select rows] モジュールをシナリオに配置して、データを取得します。 [!DNL Google] スプレッドシートから行を取得するモジュールを設定します。テスト目的で&#x200B;**[!UICONTROL Maximum number of returned rows]** を小さい数に、1 より大きい数に設定します（例：3）。 [!DNL Google Sheets] モジュールを右クリックして「**[!UICONTROL Run this module only]**」を選択し、実行します。 モジュールの出力を確認します。
1. [!UICONTROL Array Aggregator] モジュールを [!DNL Google Sheets] モジュールの後に接続します。 モジュールの設定で、「**[!UICONTROL Source node]**」フィールドの [!DNL Google Sheets] モジュールを選択します。 その他のフィールドは、現時点ではそのままにしておきます。
1. [!UICONTROL XML]/[!UICONTROL Create XML] モジュールを [!UICONTROL Array Aggregator] モジュールの後に接続します。

   モジュールの設定には、XML 出力の構造を記述したデータ構造が必要です。「**[!UICONTROL Add]**」ボタンをクリックして、データ構造の設定を開きます。 このデータ構造を作成する最も簡単な方法は、XML サンプルから自動的に生成することです。

1. 「**[!UICONTROL Generator]**」ボタンをクリックし、XML サンプルを「[!UICONTROL Sample data]」フィールドに貼り付けます。

   ![ サンプルデータフィールド ](/help/workfront-fusion/references/apps-and-modules/assets/sample-data-field-350x146.png)

1. **[!UICONTROL Save]** をクリックします。

   これで、データ構造の「仕様」フィールドに、生成された構造が含まれます。
1. データ構造の名前をより具体的な名前に変更し、「**[!UICONTROL Save]**」をクリックします。

   ルート配列属性に対応するフィールドは、JSON モジュールの設定で、マッピング可能なフィールドとして表示されます。
1. フィールドの横にある「**[!UICONTROL Map]**」ボタンをクリックし、[!UICONTROL Array aggregator] 出力の `Array[]` の項目をフィールドにマッピングします。
1. 「**[!UICONTROL OK]**」をクリックして、XML モジュールの設定を閉じます。
1. [!UICONTROL Array Aggregator] モジュールの設定を開きます。 **[!UICONTROL Target structure]** を「カスタム」から、親 XML 要素に対応する XML モジュールのフィールドに変更します。[!DNL Google Sheets] モジュールの項目を適切なフィールドにマッピングします。
1. 「**[!UICONTROL OK]**」をクリックして、配列アグリゲータモジュールの設定を閉じます。
1. シナリオを実行します。

   XML モジュールは、正しい XML ファイルを出力します。

1. [!DNL Google Sheets] モジュールの設定を開き、[!UICONTROL Maximum number of returned rows] 数をスプレッドシートの行数より大きくして、すべてのデータを処理します。

   結果の XML は [!DNL Dropbox] に保存したり、メールで添付ファイルとして送信したり、FTP 経由でサーバーにアップロードしたりできます。

>[!ENDSHADEBOX]

### XML 属性の追加

複雑なノード（他のノードを含むノード）に属性を追加する場合は、カスタムデータ構造内の複雑なメモに対して、`_attributes` という名前のコレクションを追加する必要があります。このコレクションはノード属性にマッピングされます。属性をテキストノードに追加する場合（例：`<node attr="1">abc</node>`）、カスタムデータ構造内のこのノードに、属性のコレクション `_attributes` とノード値のテキストプロパティ `_value` を追加する必要があります。

```
{
   "name": "node",
   "type": "collection",
   "spec": [
      {
         "name": "_attributes",
         "type": "collection"
         "spec": [
            {
               "name": "attr1",
               "type": "text"
            }
         ]
      },
      {
         "name": "_value",
         "type": "text"
      }
   ]
}
```

## [!UICONTROL Parse XML]

[!UICONTROL XML]/[!UICONTROL Parse XML] モジュールは、XML 形式のテキストを解析し、XML から抽出されたすべての情報を含む単一のバンドルを出力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Data structure]</p> </td> 
   <td> <p>データ構造は、XML の構造を記述し、以下のモジュールのマッピングパネルでモジュールの出力を使用できるようにします。</p> <p>解析する XML のサンプルがある場合は、それを使用してデータ構造を生成できます。</p> 
    <ol> 
     <li value="1"><strong>[!UICONTROL Add]</strong> ボタンをクリックします。</li> 
     <li value="2"><strong>[!UICONTROL Generator]</strong> ボタンをクリックします。</li> 
     <li value="3">XML サンプルをコピーして、「<strong>[!UICONTROL Sample data]</strong>」フィールドに貼り付けます。</li> 
     <li value="4"><strong>[!UICONTROL Save]</strong> をクリックします。</li> 
     <li value="5">データ構造が正常に生成されたことを確認します。</li> 
     <li value="6"> <p>「<strong>[!UICONTROL Save]</strong>」ボタンをクリックして、データ構造を保存します。</p> <p>手順 2～5 をスキップして、空のデータ構造を指定できます。データ構造が空の場合、モジュールが少なくとも 1 回実行されるまで、モジュールの出力はマッピングパネルで使用できません。</p> </li> 
    </ol> <p>詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref"> データ構造 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Preserve numbers as text]</td> 
   <td>数値をテキスト（文字列）値として保持するには、このオプションを有効にします。それ以外の場合、数値は数値にキャストされます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL XML]</p> </td> 
   <td> <p>解析する XML 形式のテキストを入力またはマップします。</p> <p>数式を使用する場合は、その結果の値の型が [!UICONTROL Text] のデータ型であることを確認してください。 </p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/if-you-use-a-formula-350x164.png" style="width: 350;height: 164;"> </p> <p>結果の値の型が [!UICONTROL Buffer] （バイナリ データ）の場合は、<code>toString()</code> 関数を使用してテキスト データ型に変換します。 詳細については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a> および <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref"> 項目データ型 </a>」を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例：**

XML ファイルを URL からダウンロードしてコンテンツを解析するには：

1. 新しいシナリオを開始します。
1. [!UICONTROL HTTP]/[!UICONTROL Get a file] モジュールを追加します。
1. モジュールの設定を開き、次のように設定します。

   **URL**：XML ファイルの URL（例：`https://siftrss.com/f/rqLy05ayMBJ`）

   ![XML ファイルの URL の例 ](/help/workfront-fusion/references/apps-and-modules/assets/url-of-xml-file-350x184.png)

1. 「**[!UICONTROL OK]**」をクリックして、モジュールの設定を保存して閉じます。
1. [!UICONTROL XML]/[!UICONTROL Parse XML] モジュールを追加し、[!UICONTROL HTTP]/[!UICONTROL Get a file] モジュールの後に接続して、次のように設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Data structure]</td> 
      <td> 
       <ol> 
        <li value="1"><strong>[!UICONTROL Add]</strong> ボタンをクリックします。</li> 
        <li value="2"><strong>[!UICONTROL Generator]</strong> ボタンをクリックします。</li> 
        <li value="3">Web ブラウザーで、新しいタブまたはウィンドウを開きます。</li> 
        <li value="4">3 番目の手順で使用した URL をアドレスバーに入れ、XML ファイルを取得します。</li> 
        <li value="5">すべての XML テキストを選択し、クリップボードにコピーします。</li> 
        <li value="6">タブまたはウィンドウを閉じて、シナリオに戻ります。</li> 
        <li value="7">コピーした XML テキストを「サンプルデータ」フィールドに貼り付けます。</li> 
        <li value="8"><strong>[!UICONTROL Save]</strong> をクリックします。</li> 
        <li value="9">データ構造が正常に生成されたことを確認します。</li> 
        <li value="10">「<strong>[!UICONTROL Save]</strong>」をクリックして、データ構造を保存します。</li> 
       </ol> <p>手順 2～9 をスキップして、空のデータ構造を指定できます。データ構造が空の場合、モジュールが少なくとも 1 回実行されるまで、モジュールの出力はマッピングパネルで使用できません。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL XML]</td> 
      <td> <p>[!UICONTROL HTTP]/[!UICONTROL Get a file] モジュールの出力から <code>Data </code>item をフィールドにマッピングします。 <code>toString()</code> 関数を使用して、[!UICONTROL Buffer] （バイナリデータ）型から [!UICONTROL Text] データ型に値を変換します。</p> <p>式のコードをコピーしてフィールドに貼り付けることができます。 <code>&#123;&#123;toString(1.data)&#125;&#125;</code></p> <p>バッファとテキストのデータ型の詳細については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref"> アイテム データ型 </a>」を参照してください。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/paste-formula-code-350x99.png"> </p> </td> 
     </tr> 
    </tbody> 
   </table>

>[!ENDSHADEBOX]

### [!UICONTROL Parsing XML attributes]

デフォルトでは、[!UICONTROL XML] / [!UICONTROL Parse XML] モジュールは、属性を、これらの属性を持つノードの子として、特別なコレクション `_attributes` に配置します。 ノードがテキストノードで、そのノードに属性が含まれている場合、属性の `_attributes` とノードのテキストコンテンツの `_value` の 2 つの特別なプロパティが追加されます。

>[!BEGINSHADEBOX]

**例：**&#x200B;この XML：

```
<root attr="1">
<node attr="ABC">Hello, World</node>
</root>
```

は次のバンドルに変換されます。

![XML はバンドルに変換されました ](/help/workfront-fusion/references/apps-and-modules/assets/xml-converted-to-bundle.png)

>[!ENDSHADEBOX]

## トラブルシューティング：[!UICONTROL Parse XML] モジュールからデータをマッピングできない

データ構造が正しく定義されていることを確認します。または、空のデータ構造を使用し、モジュールを少なくとも 1 回実行して XML 入力を処理することもできます。
