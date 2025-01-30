---
title: 数学変数
description: 以下の数学変数が [!DNL Adobe Workfront Fusion mapping] パネルで使用できます。
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 76%

---

# 数学変数

## 円周率

数学記号$\pi$を表します。

## [!UICONTROL random]

[`0`、`1`]（`1`ではなく`0`を含む）の範囲内の浮動小数点を持つ擬似乱数を返します。

次の式を使用して、[`min`、`max`]（`min` および `max`の両方を含む）の範囲内に整数の擬似乱数を生成します。

![ ランダム ](assets/math-variable-random-350x61.png)

```
floor(random * (1.max - 1.min + 1)) + 1.min
```
