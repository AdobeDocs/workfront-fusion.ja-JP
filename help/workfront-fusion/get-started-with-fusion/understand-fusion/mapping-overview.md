---
title: マッピングの概要
description: マッピングとは、項目に構造化されたモジュールの出力を、別のモジュールの入力フィールドに割り当てるプロセスです。
author: Becky
feature: Workfront Fusion
exl-id: 9208ce20-0757-427a-9669-ce4274d05522
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 14%

---

# マッピングの概要

マッピングとは、モジュールの出力を別のモジュールの入力フィールドに割り当てるプロセスです。

モジュールの操作により、その出力として 0 個、1 個または複数のバンドルが生成されます。バンドルは、1 つ以上の項目で構成されます。

これらの項目は、後のモジュールのフィールドにマッピングできます。

シナリオで前のモジュールから出力された値を挿入できるフィールドをクリックすると、マッピングパネルが表示されます。 ここでは、マッピングする項目を選択できます。 マッピングには、次のうち 1 つ以上を含めることができます。

* 単一の項目
* 複数の項目
* 静的テキスト
* 関数

>[!BEGINSHADEBOX]

**例**:

単一項目

![](assets/map-single.png)

テキストを含む複数の項目

![](assets/map-multiple-with-text.png)

複数の項目とテキストを持つ関数

![](assets/map-formula-with-text.png)


>[!ENDSHADEBOX]


マッピングの手順については、[ データをマッピング：記事インデックス ](/help/workfront-fusion/create-scenarios/map-data/map-data-toc.md) の記事を参照してください。

>[!NOTE]
>
>[!UICONTROL Iterator] と [!UICONTROL Aggregator] の間でラップされたモジュールからの出力は、[!UICONTROL Aggregator] モジュールを超えてアクセスできません。

## マッピングパネル

データをマッピングできるフィールドをクリックすると、マッピングパネルが開きます。

最初のタブ ![](assets/toolbar-icon-functions-you-map-from-other-modules.png) には、他のモジュールからマッピングできる項目が表示されます。

その他のタブには、数式の作成に使用できる関数、演算子、およびキーワードが含まれます。 これらは、処理するデータのタイプに基づいて異なるタブに並べ替えられます。

![](assets/mapping-panel-blank.png)


関数タブについて詳しくは、[ 関数の概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md) を参照してください。

関数を使用した項目のマッピングについて詳しくは、[ 関数を使用した項目のマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md) を参照してください。

## コレクション

項目には、様々なタイプの複数の値を含めることができます。 コレクションタイプの項目です。

コレクションタイプのバンドルは、モジュール出力のバンドルラベルの横にの `(Collection)` 表示されます。

![](assets/collection.png)

ほとんどの場合、コレクション全体を表す項目をマッピングする代わりに、コレクションの要素をマッピングします。

マッピングパネルでコレクションの要素を見つけるには、コレクションの横にある矢印をクリックします。

![](assets/collection-dropdown.png)

コレクションの詳細については、「[ アイテム データ タイプ ](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md)」を参照してください。

コレクションのマッピング手順については、「あるモジュールから別のモジュールへの情報のマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md#map-an-item) の [ 項目のマッピング」を参照してください。

## 配列

項目には、同じタイプの複数の値を含めることができます。 これらは配列型の項目です。

モジュール出力のバンドルラベルの横に、配列タイプのバンドルが `(Array)` と表示されます。

マッピングパネルでは、配列は正方形のブレスレットで表示されます。 配列タイプの項目は、項目のラベルの最後にある角括弧で識別できます。マッピングパネルで特定の配列要素を見つけるには、配列の横にある矢印をクリックします。

![](assets/array.png)

配列および配列要素のマッピングについて詳しくは、[ 配列および配列要素のマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md) を参照してください。
