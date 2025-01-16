---
title: 数学関数
description: 次の数式は、Adobe Workfront Fusion マッピングパネルで使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 97%

---

# 数学関数

## [!UICONTROL average ([array of values]) average(value1; [value2], ...)]

特定の配列内の数値の平均値、または個別に入力された数値の平均値を返します。

## [!UICONTROL ceil (number)]

指定された数値以上の最小の整数を返します。

>[!BEGINSHADEBOX]

**例：**

* `ceil(` `1.2` `)`

  戻り値 2

* `ceil(` `4` `)`

  戻り値 4

>[!ENDSHADEBOX]

## [!UICONTROL floor (number)]

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

## [!UICONTROL max ([array of values]), max(value1;value2; ...)]

指定された配列内の最大の数値、または個別に入力された数値の中で最大の数値を返します。

## [!UICONTROL min ([array of values]), min(value1; value2; ...)]

指定された配列内の最小の数値、または個別に入力された数値の中で最小の数値を返します。

## [!UICONTROL round (number)]

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

## [!UICONTROL sum ([array of values]), sum(value1; value2; ...)]

指定された配列内の値の合計、または個別に入力された数値の合計を返します。

## [!UICONTROL parseNumber (number; decimal separator)]

数値を含む文字列を解析し、数値を返します。例えば、parseNumber (1 756,456;,) のように指定します。

## [!UICONTROL formatNumber (number; decimalPOINTS; [decimalSeparator]; [thousandsSeparator])]

要求された形式で数値を返します。デフォルトでは、小数点はカンマ（,）で、三桁ごとの区切り文字はピリオド（.）です。

>[!BEGINSHADEBOX]

**例：**

`formatNumber( 123456789 ; 3 ; , ; . )`

戻り値 123.456.789,000

>[!ENDSHADEBOX]
