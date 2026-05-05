---
title: 数学関数
description: 次の数式は、Adobe Workfront Fusion マッピングパネルで使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
source-git-commit: e11e581c092ebba343a0f2d6943ecbe4d0fe4c87
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 62%

---

# 数学関数

## [!UICONTROL average ([値の配列]）average (1;[値2], ...)]

特定の配列内の数値の平均値、または個別に入力された数値の平均値を返します。

## [!UICONTROL ceil (数値)]

指定された数値以上の最小の整数を返します。

>[!BEGINSHADEBOX]

**例：**

* `ceil(` `1.2` `)`

  戻り値 2

* `ceil(` `4` `)`

  戻り値 4

>[!ENDSHADEBOX]

## [!UICONTROL floor (数値)]

指定された数値以下の最大の整数を返します。

>[!BEGINSHADEBOX]

**例：**

* `floor(` `1.2` `)`

  戻り値 1

* `floor(` `1.9` `)`

  戻り値 1

* `floor(` `4` `)`

  戻り値 4

>[!ENDSHADEBOX]

## [!UICONTROL max ([値の配列])、max (値1;値2; ...)]

指定された配列内の最大の数値、または個別に入力された数値の中で最大の数値を返します。

## [!UICONTROL min ([値の配列])、min (value1; value2;...)]

指定された配列内の最小の数値、または個別に入力された数値の中で最小の数値を返します。

## [!UICONTROL round (数値)]

数値を最も近い整数に丸めます。

>[!BEGINSHADEBOX]

**例：**

* `round(` `1.2` `)`

  戻り値 1

* `round(` `1.5` `)`

  戻り値 2

* `round(` `1.7` `)`

  戻り値 2

* `round(` `2` `)`

  戻り値 2

>[!ENDSHADEBOX]

## [!UICONTROL sum ([値の配列])、sum (値 1; 値 2; ...)]

指定された配列内の値の合計、または個別に入力された数値の合計を返します。

## [!UICONTROL parseNumber (数値; 小数点区切り記号)]

数値を含む文字列を解析し、数値を返します。 例えば、parseNumber (1 756,456;,) のように指定します。

## [!UICONTROL formatNumber (数値; 小数点以下桁数; [小数点区切り記号]; [桁区切り記号])]

要求された形式で数値を返します。 デフォルトでは、小数点はカンマ（,）で、桁区切り記号はピリオド（.）です。

>[!BEGINSHADEBOX]

**例：**

`formatNumber( 123456789 ; 3 ; , ; . )`

戻り値 123.456.789,000

>[!ENDSHADEBOX]

### [!UICONTROL abs （number） ]

[!BADGE 新規！]{type=Informative}

数値の絶対値を返します。

>[!BEGINSHADEBOX]

**例：**

* `abs(-3.14)`

  3.14を返します
* `abs(3.14)`

  3.14を返します


### [!UICONTROL div （number1; number2; ...） ]

[!BADGE 新規！]{type=Informative}

すべての数値を指定された順序で除算します。

>[!BEGINSHADEBOX]

**例：**

* `div(10; 2)`

  返品5
* `div(100; 5; 4)`

  返品5


### [!UICONTROL ln （number） ]

[!BADGE 新規！]{type=Informative}

数値の自然対数を返します。


>[!BEGINSHADEBOX]

**例：**

* `ln(1)`

  0を返します
* `ln(2.718281828)`

  戻り値 1


### [!UICONTROL log （number1; number2） ]

[!BADGE 新規！]{type=Informative}

`number2`の対数をベース `number1`に返します。

>[!BEGINSHADEBOX]

**例：**

* `log(10; 100)`

  戻り値 2
* `log(2; 8)`

  戻り値 3


### [!UICONTROL number （string） ]

[!BADGE 新規！]{type=Informative}

文字列を数値に変換します。

>[!BEGINSHADEBOX]

**例：**

* `number("3.14")`

  3.14を返します
* `number("42")`

  42を返します


### [!UICONTROL power （number; power） ]

[!BADGE 新規！]{type=Informative}

指定された電力に引き上げられた数値を返します。

>[!BEGINSHADEBOX]

**例：**

* `power(2; 3)`

  返品数8
* `power(4; 0.5)`

  戻り値 2


### [!UICONTROL prod （number1; number2; ...） ]

[!BADGE 新規！]{type=Informative}

指定されたすべての数値を乗算します。

>[!BEGINSHADEBOX]

**例：**

* `prod(2; 3; 4)`

  24を返します
* `prod(5; 5)`

  25を返します


### [!UICONTROL sortAscNum （number1; number2; ...） ]

[!BADGE 新規！]{type=Informative}

指定された数値を昇順に並べ替えて返します。

>[!BEGINSHADEBOX]

**例：**

* `sortAscNum(3; 1; 2)`

  \[1, 2, 3]を返します
* `sortAscNum(5; 3; 4)`

  \[3, 4, 5]を返します


### [!UICONTROL sortDescNum （number1; number2; ...） ]

[!BADGE 新規！]{type=Informative}

指定された数値を降順に並べ替えて返します。

>[!BEGINSHADEBOX]

**例：**

* `sortDescNum(3; 1; 2)`

  \[3, 2, 1]を返します
* `sortDescNum(5; 3; 4)`

  \[5, 4, 3]を返します


### [!UICONTROL sqrt （number） ]

[!BADGE 新規！]{type=Informative}

数値の平方根を返します。

>[!BEGINSHADEBOX]

**例：**

* `sqrt(9)`

  戻り値 3
* `sqrt(4)`

  戻り値 2


### [!UICONTROL sub （number1; number2; ...） ]

[!BADGE 新規！]{type=Informative}

指定した順序のすべての数値を減算します。

>[!BEGINSHADEBOX]

**例：**

* `sub(10; 3; 2)`

  返品5
* `sub(20; 5)`

  15を返します
