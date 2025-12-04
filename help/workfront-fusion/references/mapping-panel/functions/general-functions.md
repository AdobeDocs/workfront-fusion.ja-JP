---
title: 一般的な関数
description: Adobe Workfront Fusion マッピングパネルでは、次の一般的な関数を使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 6d4b8801-aa7e-47d4-80b3-aceac10c073f
source-git-commit: f968b9141173725160cea36575ad4e02a09a5e3f
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 47%

---

# 一般的な関数

## 変数

これらの一般変数を使用して、実行に関する詳細を識別できます。

* `executionID`：このシナリオ実行の ID
* `triggerTimestamp`：この実行がトリガーされた時間
* `scenarioID`：現在開いているシナリオの ID
* `operationsConsumed`：シナリオのその時点で使用された操作の数。

## [!UICONTROL GET（オブジェクトまたは配列パス）]

オブジェクトまたは配列の値のパスを返します。ネストされたオブジェクトにアクセスするには、ドット表記を使用します。配列内の最初の項目はインデックス 1 です。

>[!BEGINSHADEBOX]

**例：**

* `get( array ; 1 + 1 )`
* `get( array ; 5.raw_name )`
* `get( object ; raw_name )`
* `get( object ; raw_name.sub_raw_name )`

>[!ENDSHADEBOX]

## [!UICONTROL IF（式；値 1；値 2）]

式が true に評価される場合は、`value1` を返します。それ以外の場合は `value2` を返します。

2 つ以上の式が true と評価された場合にのみ値を返す if ステートメントを作成するには、`and` キーワードを使用します。

`if` ステートメントを組み合わせるには、`and` 演算子と `or` 演算子を使用します。

![and 演算子 &#x200B;](assets/and-in-if-statement.png)

>[!BEGINSHADEBOX]

**例：**

* `if( 1 = 1 ; A ; B )`

  戻り値 A

* `if( 1 = 2 ; A ; B )`

  戻り値 B

* `if( 1 = 2 and 1 = 2 ; A ; B )`

  戻り値 B

>[!ENDSHADEBOX]

## [!UICONTROL ifempty (value1; value2)]

この値が空でない場合は、`value1` を返します。それ以外の場合は、`value2` を返します。

>[!BEGINSHADEBOX]

**例：**

* `ifempty(` `A` `;` `B` )

  戻り値 A

* `ifempty(` `unknown` `;` `B` )

  戻り値 B

* `ifempty(` `""` `;` `B` )

  戻り値 B

>[!ENDSHADEBOX]

## [!UICONTROL switch (expression; value1; result1; [value2; result2; ...]; [else])]

（式と呼ばれる） 1 つの値を値のリストと照合して評価します。最初に一致した値に対応する結果が返されます。 `else` 値を含めるには、最終的な式または値の後に追加します。

>[!BEGINSHADEBOX]

**例：**

* `switch( B ; A ; 1 ; B ; 2 ; C ; 3 )`

  戻り値 2

* `switch( C ; A ; 1 ; B ; 2 ; C ; 3 )`

  戻り値 3

* `switch( X ; A ; 1 ; B ; 2 ; C ; 3 ; 4 )`

  戻り値 4

  この関数では、4 は式が適用されない場合に返される値（`else` 値）です。

>[!ENDSHADEBOX]

## [!UICONTROL omit(object; key1; [key2; ...])]

オブジェクトのキーを省略し、残りのキーを返します。

>[!BEGINSHADEBOX]

**例：**

`omit(` ユーザー `;` パスワード `)`

パスワードを除くユーザーの情報のコレクションを返します。

>[!ENDSHADEBOX]

## [!UICONTROL pick(オブジェクト; キー1; [キー2; ...])]

オブジェクトから指定されたキーのみを選択します。

>[!BEGINSHADEBOX]

**例：**

`pick(` ユーザー `;` パスワード `;` メール `)`

ユーザーのパスワードとメールアドレスのみのコレクションを返します。

>[!ENDSHADEBOX]

## mergeCollections （collection1; collection2）

2 つのコレクションのキーと値のペアを組み合わせて、それらのコレクションを結合します。 両方のコレクションに同じキーが含まれている場合、2 番目のコレクションの値が最初のコレクションの値を上書きします。
