---
title: 一般的な関数
description: Adobe Workfront Fusion マッピングパネルでは、次の一般的な関数を使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 6d4b8801-aa7e-47d4-80b3-aceac10c073f
source-git-commit: 5709c9c0f8efd2c29ff7dbc0391a5b496a467c6a
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 36%

---

# 一般的な関数

## 変数

これらの一般変数を使用して、実行に関する詳細を特定できます。

* `executionID`：このシナリオ実行のID
* `triggerTimestamp`：この実行がトリガーされた時間
* `scenarioID`：現在実行中のシナリオの ID
* `scenarioName`：現在実行中のシナリオの名前
* `operationsConsumed`：シナリオのその時点で使用された操作の数。

## [!UICONTROL GET（オブジェクトまたは配列パス）]

オブジェクトまたは配列の値のパスを返します。 ネストされたオブジェクトにアクセスするには、ドット表記を使用します。 配列内の最初の項目はインデックス 1 です。

>[!BEGINSHADEBOX]

**例：**

* `get( array ; 1 + 1 )`
* `get( array ; 5.raw_name )`
* `get( object ; raw_name )`
* `get( object ; raw_name.sub_raw_name )`

>[!ENDSHADEBOX]

## [!UICONTROL IF（式；値 1；値 2）]

式が true に評価される場合は、`value1` を返します。それ以外の場合は `value2` を返します。

2つ以上の式がtrueと評価された場合にのみ値を返すif ステートメントを作成するには、`and` キーワードを使用します。

`if`文を組み合わせるには、`and`演算子と`or`演算子を使用します。

![と演算子](assets/and-in-if-statement.png)

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

値のリストに対して1つの値（式と呼ばれる）を評価します。最初に一致する値に対応する結果を返します。 `else`値を含めるには、最後の式または値の後に値を追加します。

>[!BEGINSHADEBOX]

**例：**

* `switch( B ; A ; 1 ; B ; 2 ; C ; 3 )`

  戻り値 2

* `switch( C ; A ; 1 ; B ; 2 ; C ; 3 )`

  戻り値 3

* `switch( X ; A ; 1 ; B ; 2 ; C ; 3 ; 4 )`

  戻り値 4

  この関数では、式が適用されない場合に返される値は4です（`else`値）。

>[!ENDSHADEBOX]

## [!UICONTROL omit(object; key1; [key2; ...])]

オブジェクトのキーを省略し、残りのキーを返します。

>[!BEGINSHADEBOX]

**例：**

`omit(` ユーザー `;` パスワード `)`

パスワードを除くユーザー情報のコレクションを返します。

>[!ENDSHADEBOX]

## [!UICONTROL pick(オブジェクト; キー1; [キー2; ...])]

オブジェクトから指定されたキーのみを選択します。

>[!BEGINSHADEBOX]

**例：**

`pick(` ユーザー `;` パスワード `;` メール `)`

ユーザーのパスワードとメールアドレスのみのコレクションを返します。

>[!ENDSHADEBOX]

## mergeCollections （collection1; collection2）

キーと値のペアを組み合わせることで、2つのコレクションを結合します。 両方のコレクションに同じキーが含まれている場合、2番目のコレクションの値は1番目のコレクションの値を上書きします。

### [!UICONTROL isBlank （value） &#x200B;]

値が`null`または空の文字列の場合は`true`を返し、それ以外の場合は`false`を返します。 `ifEmpty`とは異なり、この関数は数値`0`または空白のみの文字列を空白として扱いません。

>[!BEGINSHADEBOX]

**例：**

* `isBlank("")     `

  trueを返します
* `isBlank(null)   `

  trueを返します
* `isBlank("Hello")`

  falseを返します
* `isBlank(0)      `

  falseを返します
* `isBlank(" ")    `

  falseを返します

>[!ENDSHADEBOX]


### [!UICONTROL in （value; value1; value2; ...） &#x200B;]

値が指定された値のいずれかに等しい場合、`true`を返します（厳密な等号、型強制なし）。

>[!BEGINSHADEBOX]

**例：**

* `in("B"; "A"; "B"; "C")`

  trueを返します
* `in("D"; "A"; "B"; "C")`

  falseを返します
* `in(2; 1; 2; 3)        `

  trueを返します
* `in("2"; 1; 2; 3)      `

  falseを返します

>[!ENDSHADEBOX]

### [!UICONTROL ifin （value; value1; value2; ...; trueExpression; falseExpression） &#x200B;]

値が指定された一致値のいずれかに一致する場合は`trueExpression`を返し、それ以外の場合は`falseExpression`を返します。 少なくとも3つの引数（値、一致値、trueExpression + falseExpression）が必要です。

>[!BEGINSHADEBOX]

**例：**

* `ifin("B"; "A"; "B"; "yes"; "no")`

  yesを返します
* `ifin("D"; "A"; "B"; "yes"; "no")`

  返品数no
* `ifin("X"; "X"; "found"; "not found")`

  返品数が見つかりました

>[!ENDSHADEBOX]

### [!UICONTROL case （indexNumber；値1；値2; ...） &#x200B;]

インデックス番号（1 ベース）で指定された位置の値を返します。 インデックスが範囲外であるか、0である場合、`null`を返します。

>[!BEGINSHADEBOX]

**例：**

* `case(1; "Sun"; "Mon"; "Tue")`

  太陽を返します
* `case(2; "Sun"; "Mon"; "Tue")`

  月を返します
* `case(3; "Sun"; "Mon"; "Tue")`

  時間を返します
* `case(5; "a"; "b")           `

  nullを返します

>[!NOTE]
>
>これを使用して、日付から日付名を取得することをお勧めします。
>`case(dayOfWeek(date); "Sun"; "Mon"; "Tue"; "Wed"; "Thu"; "Fri"; "Sat")`

>[!ENDSHADEBOX]

