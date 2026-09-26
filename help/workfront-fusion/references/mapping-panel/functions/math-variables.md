---
title: 数学変数
description: 次の数式変数は、[!DNL Adobe Workfront Fusion mapping] パネルで使用できます。
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
TQID: 'https://experienceleague.adobe.com/7vPwofVyFGdTGAXXuqbP5mmpPgSEK0JqimFqWu-UlJU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 01689332f97c15b317e686d11a27cb4dc7e2e8bd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 73%
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
