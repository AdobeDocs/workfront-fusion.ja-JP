---
title: モジュールのアーカイブ
description: ' [!DNL Adobe Workfront Fusion]  シナリオの場合、zip 形式のファイルなどのアーカイブを複数のサードパーティのアプリケーションやサービスに接続できます。例えば、次のシナリオを設定できます。'
author: Becky
feature: Workfront Fusion
exl-id: 4b5ff3d5-601c-4119-ad70-3612ad5ba1ab
source-git-commit: 640aae1f4b7563545d7f9aa3f801671aa3d45fca
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 84%

---

# [!UICONTROL アーカイブ]モジュール

[!DNL Adobe Workfront Fusion] シナリオの場合、zip 形式のファイルなどのアーカイブをシナリオで使用して、自動化または統合で使用できます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。 モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## [!UICONTROL アーカイブ]モジュールとそのフィールド

[!UICONTROL アーカイブ]モジュールの設定時に、[!DNL Workfront Fusion] には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!UICONTROL アーカイブ]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [アグリゲーター](#aggregators)
* [変換サービス](#transformers)

## アクション

### [!UICONTROL アーカイブを抽出]

このアクションモジュールは、指定したファイルをアーカイブから抽出します。

このモジュールは、ファイルの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>  <p>前のモジュールからソースファイルを選択するか、ソースデータをマッピングします。</p></p>  </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例：**&#x200B;定義された [!DNL Dropbox] フォルダー（アーカイブなど）から ZIP ファイルを取得し、[!UICONTROL アーカイブ]モジュールを使用して抽出し、[!UICONTROL メール]または [!DNL Gmail] モジュールを使用して、抽出したファイルを目的のメールアドレスに添付ファイルとして送信します。

![Dropboxの例 ](/help/workfront-fusion/references/apps-and-modules/assets/example-dropbox-350x134.png)

>[!ENDSHADEBOX]

## アグリゲーター

### [!UICONTROL アーカイブを作成]

この集計モジュールは、必要なファイルを [!UICONTROL ZIP]、GZIP または [!UICONTROL TAR] アーカイブに追加します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module]</td> 
   <td> <p> ファイルの取得元のモジュールを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type] </td> 
   <td> <p>[!UICONTROL ZIP]、GZIP、または [!UICONTROL TAR] アーカイブにファイルを追加するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>アーカイブに追加するコメントを入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Group by]</td> 
   <td> <p>集約出力をグループ化する式を定義します。この式には、1 つ以上のマッピングされた項目を含めることができます。集約されたデータは、この式の値を使用してグループに分割されます。各グループは、キー（評価された式）と値（集約されたテキスト）を持つ個別のバンドルとして出力されます。キーを後続のモジュールのフィルターとして使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>結果がない場合にシナリオを停止するには、このオプションを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Archive name]</td> 
   <td> <p> 作成したアーカイブの名前を入力します。拡張機能は追加しないでください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例：**[!DNL Gmail]／[!UICONTROL メールを監視]モジュールを使用して受信メールを見ます。メールを受け取ると、添付ファイルは個々のバンドルに反復され、[!DNL ZIP] ファイルにアーカイブされて、定義された Dropbox フォルダーに保存されます。

![Gmail の例 ](/help/workfront-fusion/references/apps-and-modules/assets/example-gmail-350x102.png)

>[!ENDSHADEBOX]

## 変換サービス

* [[!UICONTROL デフレート]](#deflate)
* [[!UICONTROL インフレート]](#inflate)

### [!UICONTROL デフレート]

この変換モジュールは、デフレーションアルゴリズムを使用してバイナリデータを圧縮します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data] </td> 
   <td> <p>deflate 関数を使用して、圧縮するデータを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL インフレート]

この変換モジュールは、インフレーションアルゴリズムを用いてバイナリデータを解凍します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data] </td> 
   <td> <p>インフレート関数を使用して、インフレートするデータを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
