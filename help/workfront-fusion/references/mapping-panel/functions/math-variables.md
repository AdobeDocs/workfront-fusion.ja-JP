---
title: 数学変数
description: 以下の数学変数が [!DNL Adobe Workfront Fusion mapping] パネルで使用できます。
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
TQID: https://experienceleague.adobe.com/7vPwofVyFGdTGAXXuqbP5mmpPgSEK0JqimFqWu-UlJU
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 52
ht-degree: 90%

---

# 数学変数

## pi

数学記号$\pi$を表します。

## [!UICONTROL ランダム]

[`0`、`1`]（`1`ではなく`0`を含む）の範囲内の浮動小数点を持つ擬似乱数を返します。

次の式を使用して、[`min`、`max`]（`min` および `max`の両方を含む）の範囲内に整数の擬似乱数を生成します。

![Random](assets/math-variable-random-350x61.png)

```
floor(random * (1.max - 1.min + 1)) + 1.min
```
