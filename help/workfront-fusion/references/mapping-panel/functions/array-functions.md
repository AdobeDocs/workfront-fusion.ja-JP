---
title: 配列関数
description: 次の配列関数は、Adobe Workfront Fusion マッピングパネルで使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 16c3915c-add1-4aab-a0e1-75fc590c42a6
source-git-commit: 9b61a3b18df1f755cc7ccc28889564e4bcb6cda0
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 86%

---

# 配列関数

## [!UICONTROL join (array; separator)]

各項目間に指定された区切り記号を使用して、配列のすべての項目を文字列に連結します。

## [!UICONTROL length (array)]

配列内の項目の数を返します。

## [!UICONTROL keys (object)]

指定されたオブジェクトまたは配列のプロパティの配列を返します。

## [!UICONTROL slice (array; start; [end])]

選択された項目のみを含む新しい配列を返します。

## [!UICONTROL merge (array1; array2; ...)]

1 つまたは複数の配列を 1 つの配列に結合します。

## [!UICONTROL contains (array; value)]

配列に値が含まれているかどうかを確認します。

## [!UICONTROL remove (array; value1; value2; ...)]

配列のパラメーターに指定された値を削除します。この関数は、テキストまたは数値のプリミティブ配列に対してのみ有効です。

## [!UICONTROL add (array; value1; value2; ...)]

パラメーターで指定された値を配列に追加し、その配列を返します。

## [!UICONTROL map (complex array; key;[フィルタリング用キー];[フィルタリングに使用可能な値])]

複素配列の値を含むプリミティブ配列を返します。この関数を使用すると、値をフィルターできます。キーには変数名を使用します。

>[!BEGINSHADEBOX]

**例：**

* `map(Emails[];email)`

  メールを含むプリミティブ配列を返します

* `map(Emails[];email;label;work)`

  work と等しいラベルを持つメールを含むプリミティブ配列を返します

>[!ENDSHADEBOX]

詳しくは、「[ 配列または配列要素のマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md)」を参照してください。

## shuffle

## [!UICONTROL sort (array; [order]; [key])]

配列の値を並べ替えます。`order` パラメーターの有効な値は次のとおりです。

* `asc`

  （デフォルト）ー 昇順：番号タイプの場合は 1、2、3、...。A、B、C、a、b、c、...テキスト型の場合

* `desc`

  降順：番号型の場合は　...、3、2、1。テキスト型の場合は ...、c、b、a、C、B、A。

* `asc ci`

  大文字と小文字を区別しない昇順：テキスト型の場合は A、a、B、b、C、c、...。

* `desc ci`

  大文字と小文字を区別しない降順：テキスト型の場合は ...、C、c、B、b、A、a。

`key` パラメーターを使用して、複雑なオブジェクト内のプロパティにアクセスします。

キーには変数名を使用します。

ネストされたプロパティにアクセスするには、ドット表記を使用します。

配列内の最初の項目はインデックス 1 です。

>[!BEGINSHADEBOX]

**例：**

* `sort(Contacts[];name)`

  連絡先の配列を「名前」プロパティによってデフォルトの昇順で並べ替えます。

* `sort(Contacts[];desc;name)`

  連絡先の配列を「名前」プロパティで降順に並べ替えます

* `sort(Contacts[];asc ci;name)`

  連絡先の配列を「名前」プロパティによって大文字と小文字を区別しない昇順で並べ替えます。

* `sort(Emails[];sender.name)`

  メールの配列を「sender.name」プロパティで並べ替えます。

>[!ENDSHADEBOX]

## [!UICONTROL reverse (array)]

配列の最初の要素が最後の要素になり、2 番目の要素が最後から 2 番目の要素になります。

## [!UICONTROL flatten (array)]

すべてのサブ配列要素が再帰的に連結された新しい配列を、指定された深さまで作成します。

## [!UICONTROL distinct (array; [key])]

配列内の重複を削除します。複雑なオブジェクト内のプロパティにアクセスするには、「[!UICONTROL キー]」引数を使用します。ネストされたプロパティにアクセスするには、ドット表記を使用します。配列内の最初の項目はインデックス 1 です。

>[!BEGINSHADEBOX]

**例：**`distinct(Contacts[];name)`

「名前」プロパティを比較して、連絡先の配列内の重複を削除します。

>[!ENDSHADEBOX]

## toCollection

* この関数は、キーと値のペアを含む配列を受け取り、コレクションに変換します。 関数には、次の 3 つの引数があります。

* （配列）キーと値のペアを含む
* （string）キーとして使用するフィールドの名前
* （string）値として使用するフィールド名

>[!BEGINSHADEBOX]

例：

指定された配列：

```
[{"name":"Bob", "age":22}, {"name":"Tim", "age":23}]
```

および引数

```
{{toCollection(6.array; "name"; "age")}}
```

関数の戻り値

```
{
    "Bob": 22,
    "Tim": 23
}
```

>[!ENDSHADEBOX]

## toArray

この関数は、コレクションをキーと値のペアの配列に変換します。

>[!BEGINSHADEBOX]

**例：**

コレクションがあるとします

`{ key1: "value1", key2: "value2:}`

関数

`toArray({ key1: "value1", key2: "value2:})`

キーと値のペアの配列を返します

`[{ key1: "value1"}, { key2: "value2"}]`

>[!ENDSHADEBOX]

## [!UICONTROL arrayDifference [array1, array2, mode]]

2 つの配列の差を返します。

`mode` パラメーターに次のいずれかの値を入力します。

* `classic`：`array2` に存在しない `array1` のすべての要素を含む新しい配列を返します。

* `symmetric`：両方の配列に共通ではない要素の配列を返します。

  つまり、この関数は、`array2` に存在しない`array1` のすべての要素と、`array1` に存在しない `array2` のすべての要素を含む配列を返します。

>[!BEGINSHADEBOX]

**例：**

次の配列があるとします。

```
myArray = [1,2,3,4,5]
```

```
yourArray = [3,4,5,6,7]
```

* `arrayDifference [myArray, yourArray, classic]`

  `[1,2]` を返します

* `arrayDifference [yourArray, myArray, classic]`

  `[6,7]` を返します

* `arrayDifference [myArray, yourArray, symmetric]`

  `[1,2,6,7]` を返します

>[!ENDSHADEBOX]

## 重複排除

## キーワード

## emptyarray
