---
title: 日付および時間関数
description: Adobe Workfront Fusion マッピングパネルでは、以下の日付関数および時間関数を使用できます。
author: Becky
feature: Workfront Fusion
exl-id: 92813dac-4bf0-4681-9b71-7bd2e92a89a4
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1879'
ht-degree: 90%

---

# 日付および時間関数

## 変数

### now

現在の時刻を YYYY-MM-DD-hh:mm:ss 形式で取得します。

### タイムスタンプ

現在の時刻を UNIX タイムスタンプとして取得します。

## 関数

### [!UICONTROL addSeconds（date; number）]

指定された秒数を日付に追加した結果として、新しい日付を返します。秒数を減算するには、負の数を入力します。

>[!BEGINSHADEBOX]

**例：**

* `addSeconds(2016-12-08T15:55:57.536Z;2)`

  2016-12-08T15:55:59.536Z を返します。

* `addSeconds(2016-12-08T15:55:57.536Z;-2)`

  2016-12-08T15:55:55.536Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL addMinutes（date; number）] {#addminutes-date-number}

指定された分数を日付に追加した結果として、新しい日付を返します。分数を減算するには、負の数を入力します。

>[!BEGINSHADEBOX]

**例：**

* `addMinutes(2016-12-08T15:55:57.536Z;2)`

  2016-12-08T15:57:57.536Z を返します。

* `addMinutes(2016-12-08T15:55:57.536Z;-2)`

  2016-12-08T15:53:57.536Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL addHours（date; number）] {#addhours-date-number}

指定した時間数を日付に追加した結果として、新しい日付を返します。時間数を減算するには、負の数を入力します。

>[!BEGINSHADEBOX]

**例：**

* `addHours(2016-12-08T15:55:57.536Z; 2)`

  2016-12-08T17:55:57.536Z を返します。

* `addHours(2016-12-08T15:55:57.536Z;-2)`

  2016-12-08T13:55:57.536Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL addDays (date; number)] {#adddays-date-number}

指定した日数を日付に加算した結果を新しい日付として返します。日数を減算するには、負の数を入力します。

>[!BEGINSHADEBOX]

**例：**

* `addDays(2016-12-08T15:55:57.536Z;2)`

  戻り値：2016-12-10T15:55:57.536Z

* `addDays(2016-12-08T15:55:57.536Z;-2)`

  戻り値：2016-12-6T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addMonths（date, number）]

指定された月数を日付に追加した結果として、新しい日付を返します。月数を減算するには、負の数を入力します。

>[!BEGINSHADEBOX]

**例：**

* `addMonths(2016-08-08T15:55:57.536Z;2)`

  2016-10-08T15:55:57.536Z を返します。

* `addMonths(2016-08-08T15:55:57.536Z;-2)`

  2016-06-08T15:55:57.536Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL addYears（date; number）]

指定された年数を日付に追加した結果として、新しい日付を返します。年数を減算するには、負の数を入力します。

>[!BEGINSHADEBOX]

**例：**

* `addYears(2016-08-08T15:55:57.536Z;2)`

  2018-08-08T15:55:57.536Z を返します。

* `addYears(2016-12-08T15:55:57.536Z; -2)`

  2014-08-08T15:55:57.536Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL setSecond（date; number）]

この関数は、パラメーターで指定された秒数を持つ新しい日付を返します。

0 ～ 59 の数値を指定します。数値がその範囲外にある場合、この関数は、前の分（負の数の場合）または後続の分（正の数の場合）からの秒数を返します。

範囲外の数値を指定する必要がある場合は、上記の [addSeconds（date; number）](#addseconds-date-number)の節の説明に従って、[!UICONTROL addSeconds] を使用することをお勧めします。

>[!BEGINSHADEBOX]

**例：**

* `setSecond(2015-10-07T11:36:39.138Z;10)`

  2015-10-07T11:36:10.138Z を返します。

* `setSecond(2015-10-07T11:36:39.138Z; 61)`

  2015-10-07T11:37:01.138Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL setMinute（date; number）]

この関数は、パラメーターで指定された分数を持つ新しい日付を返します。

0 ～ 59 の数値を指定します。数値がその範囲外にある場合、この関数は、前の時間（負の数の場合）または後続の時間（正の数の場合）の分数を返します。

範囲外の数値を指定する必要がある場合は、上記の [addMinutes（date; number）](#addminutes-date-number)の説明に従って、addMinutes を使用することをお勧めします。

>[!BEGINSHADEBOX]

**例：**

* `setMinute(2015-10-07T11:36:39.138Z;10)`

  2015-10-07T11:10:39.138Z を返します。

* `setMinute(2015-10-07T11:36:39.138Z;61)`

  2015-10-07T12:01:39.138Z を返します。

>[!ENDSHADEBOX]

### [!UICONTROL setHour（date; number）]

この関数は、パラメーターで指定された時間数を持つ新しい日付を返します。

0 ～ 23 の数値を指定します。数値がこの範囲外にある場合、この関数は、前日（負の数の場合）または翌日（正の数の場合）の時間数を返します。

範囲外の数値を指定する必要がある場合は、上記の [addHours（date; number）](#addhours-date-number)の説明に従って、addHours を使用することをお勧めします。

>[!BEGINSHADEBOX]

**例：**

* `setHour(2015-08-07T11:36:39.138Z;6)`

  戻り値：2015-08-07T06:36:39.138Z

* `setHour(2015-08-07T11:36:39.138;-6)`

  戻り値：2015-08-06T18:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setDay (date; number/name of the day in English)]

この関数は、パラメーターで指定された日の新しい日付を返します。

この関数を使用して曜日を設定できます。日曜日は 1、土曜日は 7 と指定します。1～7 の数値を指定した場合、結果の日付は現在の（日曜日から土曜日）週の範囲内になります。この数値がその範囲外の場合、前の週（負の数の場合）または次の週（正の数の場合）の日を返します。

範囲外の数値を指定する必要がある場合は、前述の addDays を使用することをお勧めします（[addDays (date; number)](#adddays-date-number) を参照）。

>[!BEGINSHADEBOX]

**例：**

* `setDay(2018-06-27T11:36:39.138Z;Monday)`

  戻り値：2018-06-25T11:36:39.138Z

* `setDay(2018-06-27T11:36:39.138Z;1)`

  戻り値：2018-06-24T11:36:39.138Z

* `setDay(2018-06-27T11:36:39.138Z;7)`

  戻り値：2018-06-30T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setDate (date; number)]

この関数は、パラメーターで指定された月日の新しい日付を返します。

1～31 の数値を指定します。この範囲外の数値の場合、前の月（負の数の場合）または次の月（正の数の場合）の日を返します。

>[!BEGINSHADEBOX]

**例：**

* `setDate(2015-08-07T11:36:39.138Z;5)`

  戻り値：2015-08-05T11:36:39.138Z

* `setDate(2015-08-07T11:36:39.138Z;32)`

  戻り値：2015-09-01T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setMonth (date; number/name of the month in English)]

この関数は、パラメーターで指定された月の新しい日付を返します。

1～12 の数値を指定します。この範囲外の数値の場合、前の年（負の数の場合）または次の年（正の数の場合）の月を返します。

>[!BEGINSHADEBOX]

**例：**

* `setMonth(2015-08-07T11:36:39.138Z;5)`

  戻り値：2015-05-07T11:36:39.138Z

* `setMonth(2015-08-07T11:36:39.138Z;17)`

  戻り値：2016-05-07T11:36:39.138Z

* `setMonth(2015-08-07T11:36:39.138Z;january)`

  戻り値：2015-01-07T12:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setYear (date; number)]

パラメーターで指定された年の新しい日付を返します。

>[!BEGINSHADEBOX]

**例：**

* `setYear(2015-08-07T11:36:39.138Z;2017)`

  戻り値：2017-08-07T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL formatDate（date; format; [timezone]）]

この関数は、`12-10-2021 20:30` などの日付値を `Dec 10, 2021 8:30 PM` などのテキスト値として書式設定する場合に使用します。

これは、例えば同じシナリオで 1 つのアプリまたは web サービスの日付形式を、接続されているアプリまたは web サービスの日付形式に変更する必要がある場合に便利です。

詳細については、「[ アイテム データの種類 ](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md)」の「日付とテキスト」を参照してください。

#### パラメーター

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>パラメーター</th> 
   <th>想定されるデータタイプ* </th> 
   <th>機能</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL date] </td> 
   <td>日付 </td> 
   <td> <p>日付値をテキスト値に変換します。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL format] </td> 
   <td>テキスト </td> 
   <td> <p>日付や時刻の書式設定トークンを使用して形式を指定できます。詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md" class="MCXref xref"> 日付および時刻のフォーマット設定のトークン </a> を参照してください。</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span><code>DD.MM.YYYY HH:mm</code> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL timezone] </td> 
   <td>テキスト </td> 
   <td> <p>（オプション）変換で使用されるタイムゾーンを指定できます。 </p> <p>認識されるタイムゾーンのリストについては、Wikipedia の <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">tz データベースのタイムゾーンのリスト</a>にある「TZ database name」列を参照してください。この列にリスト表示されている値のみが、関数により有効なタイムゾーンとして認識されます。その他の値は無視され、プロファイルで指定したシナリオタイムゾーンが代わりに使用されます。 </p> <p>このパラメーターを省略した場合、プロファイル設定で指定されたシナリオタイムゾーンが適用されます。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span><code>Europe/Prague</code>、 <code>UTC</code></p> </td> 
  </tr> 
 </tbody> 
</table>

異なるタイプを指定した場合、型強制が適用されます。詳細については、「[ 型強制 ](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md)」を参照してください。

#### 戻り値とタイプ

`formatDate` 関数は、指定された形式とタイムゾーンに従って、指定された日付値のテキスト表現を返します。データタイプはテキストです。

>[!BEGINSHADEBOX]

**例：**&#x200B;シナリオと web タイムゾーンは、これらの例ではどちらも `Europe/Prague` に設定されています。

![ 日時関数の例 ](assets/date&time-functions-examples-350x61.png)

* `formatDate(1. Date created;MM/DD/YYYY)`

  戻り値：10/01/2018

* `formatDate(1. Date created; YYYY-MM-DD hh:mm A)`

  2018-10-01 09:32 AM を返します。

* `formatDate(1. Date created;DD.MM.YYYY HH:mm;UTC)`

  01.10.2018 07:32 を返します。

* `formatDate(now;DD.MM.YYYY HH:mm)`

  19.03.2019 15:30 を返します

>[!ENDSHADEBOX]

### [!UICONTROL parseDate（テキスト、フォーマット、[タイムゾーン]）]

日付を表すテキスト値（`12-10-2019 20:30` または `Aug 18, 2019 10:00 AM`）の場合、この関数を使用して、日付値（バイナリマシンが読み取り可能な表現）に変換（解析）する必要があります。詳細については、「[ アイテム データの種類 ](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md)」の「日付とテキスト」を参照してください。

#### パラメーター

2 番目の列は、期待されるタイプを示します。異なるタイプを指定した場合、型強制が適用されます。詳細については、「[ 型強制 ](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md)」を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>パラメーター</th> 
   <th>想定されるデータタイプ* </th> 
   <th>機能</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL text] </td> 
   <td>テキスト </td> 
   <td> <p>日付値をテキスト値に変換します。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL format] </td> 
   <td>テキスト </td> 
   <td> <p>日付や時刻の書式設定トークンを使用して形式を指定できます。詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md" class="MCXref xref"> 日付および時刻のフォーマット設定のトークン </a> を参照してください。</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span><code>DD.MM.YYYY HH:mm</code> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL timezone] </td> 
   <td>テキスト </td> 
   <td> <p>（オプション）変換で使用されるタイムゾーンを指定できます。 </p> <p>認識されるタイムゾーンのリストについては、Wikipedia の <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">tz データベースのタイムゾーンのリスト</a>にある「TZ database name」列を参照してください。この列にリスト表示されている値のみが、関数により有効なタイムゾーンとして認識されます。その他の値は無視され、プロファイルで指定したシナリオタイムゾーンが代わりに使用されます。 </p> <p>このパラメーターを省略した場合、プロファイル設定で指定されたシナリオタイムゾーンが適用されます。</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>例：</b></span></span><code>Europe/Prague</code>、 <code>UTC</code></p> </td> 
  </tr> 
 </tbody> 
</table>

異なるタイプを指定した場合、型強制が適用されます。詳細については、「[ 型強制 ](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md)」を参照してください。

#### 戻り値とタイプ

この関数は、指定した形式とタイムゾーンに従って、テキスト文字列を日付に変換します。値のデータタイプは日付です。

>[!BEGINSHADEBOX]

**例：** 次の例では、返される日付値は ISO 8601 に従って表されますが、結果のデータタイプは日付です。

* `parseDate(2016-12-28;YYYY-MM-DD)`

  戻り値：2016-12-28T00:00:00.000Z

* `parseDate(2016-12-28 16:03;YYYY-MM-DD HH:mm)`

  戻り値：2016-12-28T16:03:00.000Z

* `parseDate(2016-12-28 04:03 pm; YYYY-MM-DD hh:mm a)`

  戻り値：2016-12-28T16:03:06.000Z

* `parseDate(1482940986;X)`

  戻り値：2016-12-28T16:03:06.000Z

>[!ENDSHADEBOX]

### [!UICONTROL dateDifference (Date1; Date2; Unit)]

2 つの日付の差を表す数値を、指定された単位で返します。

Date1 から Date2 が減算されます。

`unit` パラメーターには、次のいずれかの時刻値を使用します。

* milliseconds
* 秒
* 分
* 時間
* days
* 週
* 月

単位が指定されていない場合、この関数は差をミリ秒単位で返します。

>[!BEGINSHADEBOX]

**例：**

* `dateDifference(2021-05-11T18:10:00.000Z;2021-05-11T18:00:00.000Z)`

  戻り値：`600,000`

* `dateDifference(2021-05-11T18:10:00.000Z;2021-05-11T18:00:00.000Z;hours)`

  `4` を返します

* `dateDifference2021-06-11T18:10:00.000Z;2021-05-11T18:00:00.000Z;months)`

  戻り値：`1`

>[!ENDSHADEBOX]

### その他の例

#### 月の n 番目の曜日の計算方法

この節では、月の n 番目の曜日の取得方法を説明する [!DNL Exceljet] web ページのWorkfront Fusion に適応しました。

月の n 番目の曜日（例：最初の火曜日、3 番目の金曜日など）に対応する日付を計算する必要がある場合、次の数式を使用できます。

![n 日目を計算 ](assets/date&time-functions-calc-nth-day-350x31.png)

```
{{addDays(setDate(1.date; 1); 1.n * 7 - formatDate(addDays(setDate(1.date; 1); "-" + 1.dow); "E"))}}
```

数式には、次の項目が含まれます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><code>1.n</code> </td> 
   <td> <p> n 番目の曜日：</p> 
    <ul> 
     <li><code>1</code> 第 1 火曜日</li> 
     <li><code>2</code> 第 2 火曜日</li> 
     <li><code>3</code> 第 3 火曜日など</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>2.dow</code> </td> 
   <td> <p> 曜日：</p> 
    <ul> 
     <li><code>1</code> 月曜日</li> 
     <li><code>2</code> 火曜日</li> 
     <li><code>3</code> 水曜日</li> 
     <li><code>4</code> 木曜日</li> 
     <li><code>5</code> 金曜日</li> 
     <li><code>6</code> 土曜日</li> 
     <li><code>7</code> 日曜日</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>1.date</code> </td> 
   <td> <p> 日付によって月が決まります。現在の月の n 番目の曜日を計算するには、<code>now</code> 変数を使用します。</p> </td> 
  </tr> 
 </tbody> 
</table>

例えば、第 2 水曜日ごとに 1 つの特定のケースのみを計算する場合は、`1.n` および `2.dow` の項目を計算式内で対応する数値に置き換えることができます。現在の月の第 2 水曜日には、次の値を使用します。

* `1.n` = `2`
* `1.dow` = `3`
* `1.date` = `now`

![N 日目の変数値 ](assets/nth-day-variable-value-350x33.png)

#### 説明：

* `setDate(now;1)` は、現在の月の最初の曜日を返します
* `formatDate(....;E)` は、曜日を返します（1、2、...6）

### 日付間の日数の計算方法

例えば、次の式を使用できます。

![ 日付間の日数の計算 ](assets/calculate-days-between-dates-350x68.png)

```
{{round((2.value - 1.value) / 1000 / 60 / 60 / 24)}}
```

>[!NOTE]
>
>* `D1` および `D2` の値は、日付タイプの値です。文字列タイプの値（例：20.10.2018）の場合、`parseDate()` 関数を使用して、日付タイプの値に変換します。
>
>* `round()` 関数は、いずれかの日付がサマータイム期間内に該当し、その他の日付がサマータイム期間外の場合に使用されます。この場合、時間の差は 1 時間少ないか多いかです。整数以外の結果を得るには、24 で割ります。サマータイムで 1 時間失います。百分率が発生しないように、数値を丸めて平均化します。

#### 月の最終日／ミリ秒の計算方法

日付範囲を指定する場合、例えば、検索モジュールで、範囲が前月の全体にわたりクローズした間隔（両方の制限ポイントを含む間隔）の場合、月の最終日を計算する必要があります。

2019-09-01 ≤ D ≤ 2019-09-30

次の数式は、前月の最終日の計算方法の 1 つを示しています。

![ 先月の最終日 ](assets/last-day-prev-month.png)

```
{{addDays(setDate(now; 1); -1)}}
```

場合によっては、月の最後日だけでなく、文字どおり最後のミリ秒も計算する必要があります。

2019-09-01T00:00:00.000Z ≤ D ≤ 2019-09-30T23:59:59.999Z

この数式は、前月の直近ミリ秒を計算する方法の 1 つを示します。

![ 先月の最後のミリ秒 ](assets/last-millisecond-prev-month-350x45.png)

```
{{parseDate(parseDate(formatDate(now; "YYYYMM01"); "YYYYMMDD"; "UTC") - 1; "x")}}
```

タイムゾーン設定を使用するのに結果が必要な場合は、UTC 引数を省略します。

![UTC を省略 ](assets/omit-utc-argument-350x45.png)

`{{parseDate(parseDate(formatDate(now; "YYYYMM01"); "YYYYMMDD") - 1; "x")}}`

ただし、次のように、翌月の最初の日を指定し、「次よりも小さいか等しい」演算子を「次よりも小さい」に置き換えて、代わりに半開間隔（その制限ポイントを除く間隔）を使用することをお勧めします。

`2019-09-01 ≤ D < 2019-10-01`

`2019-09-01T00:00:00.000Z ≤ D < 2019-10-01T00:00:00.000Z`
