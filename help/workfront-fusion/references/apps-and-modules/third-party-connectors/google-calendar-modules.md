---
title: Google カレンダーモジュール
description: ' [!DNL Adobe Workfront Fusion] シナリオでは、Google Calendar を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 6e514204-cd8e-4f30-bbbb-b8fbe48fc670
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '3306'
ht-degree: 83%

---

# [!DNL Google Calendar] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!UICONTROL Google Calendar] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## 前提条件

[!DNL Google Calendar] モジュールを使用するには、[!DNL Google] アカウントが必要です。

## Google カレンダー API 情報

Google カレンダーコネクタは以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://www.googleapis.com/calendar/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v5.4.5</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Calendar] モジュールとそのフィールド

[!DNL Google Calendar] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Google Calendar] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [イベント](#events)
* [カレンダー](#calendars)
* [アクセス制御ルール](#access-control-rules)
* [イテレーター（廃止）](#iterators-deprecated)
* [その他](#other)

### イベント

* [[!UICONTROL Watch events]](#watch-events)
* [[!UICONTROL Search events]](#search-events)
* [[!UICONTROL Get an event]](#get-an-event)
* [[!UICONTROL Create an event]](#create-an-event)
* [[!UICONTROL Update an event]](#update-an-event)
* [[!UICONTROL Delete an event]](#delete-an-event)


#### [!UICONTROL Watch events]

このトリガーモジュールは、指定したカレンダーで新しいイベントが追加、更新、削除、開始、または終了された場合に、シナリオを実行します。このモジュールは、レコードに関連付けられたすべての標準フィールドと、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar] </td> 
   <td> <p>モジュールを使用するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch Events]</td> 
   <td> <p>イベントを「作成日」、「更新日」、「開始日」、「終了日」のどれで監視するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show deleted events]</td> 
   <td> <p>削除されたイベントを含めるには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query] </td> 
   <td> <p>検索するテキストを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p> 1 回のサイクル中に [!DNL Workfront Fusion] が処理する結果の最大数（シナリオ実行あたりの繰り返し数）を設定します。値が大きすぎると、指定されたサードパーティサービス側で接続が中断される可能性があります（タイムアウト）。[!DNL Workfront Fusion] はこれに影響しません。より小さい値を設定し、最大サイクル数としてより大きい値を定義するか、シナリオをより頻繁に実行することをお勧めします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search events]

このアクションモジュールは、選択したカレンダー内のイベントを検索します。

カレンダーと検索のパラメーターを指定します。

このモジュールは、イベントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>[!DNL Google Calendar] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>検索するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p> イベントが開始する日付を入力またはマッピングします。また、このモジュールは、この日付より前に開始し、入力された開始日にまだ発生しているイベントを取得します。 </p> <p>サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> イベントが終了する日付を入力またはマッピングします。 </p> <p> サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Single events]</td> 
   <td> <p> このオプションを有効にすると、繰り返しイベントが単一のインスタンスとして処理されます。例えば、週次ミーティングがあり、このオプションが有効な場合、モジュールは各週のミーティングを個別のイベントとして返します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>検索する検索語を入力またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td> <p>結果で返されるイベントの順序を選択します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Start Time]</strong>：開始日時（昇順）で並べ替えます。 これは、単一のイベントに対するクエリ時にのみ使用できます。</li> 
     <li><strong>[!UICONTROL Updated Time]</strong>：最終変更時間で並べ替えます（昇順）。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すイベントの数の上限を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an event]

このアクションモジュールは、指定されたカレンダー内の 1 つのイベントのメタデータを返します。

カレンダーとイベントを指定します。

このモジュールは、イベントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>取得するイベントが含まれるカレンダーの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID] </td> 
   <td> <p>取得する既存の [!DNL Google Calendar] イベントのイベント ID を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an event]

このアクションモジュールは、イベントを作成します。

イベントのカレンダーとパラメーターを指定します。

このモジュールは、イベントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>[!DNL Google Calendar] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create an Event]</td> 
   <td> <p>イベントの作成方法を選択します。</p> 
    <ul> 
     <li><b>[!UICONTROL In Detail]</b><p>このオプションを使用すると、イベントの詳細を設定できます。<br></p></li> 
     <li><b>[!UICONTROL Quickly]</b><p>必要なのは、カレンダーを選択し、イベントの名前を入力することだけです。名前に時間や場所の詳細を含めると、[!DNL Google Calendar] がその場所と時間にイベントをスケジュールします。</p></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>イベントを表示するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Color]</td> 
   <td>イベントがカレンダーに表示する色を選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event name]</td> 
   <td> <p> イベントの名前を入力またはマッピングします。 </p> <p>注意：「[!UICONTROL Create an event]」フィールドで「[!UICONTROL Quick add]」を選択した場合は、イベントの日時を含めて、その日時のイベント [!DNL Workfront Fusion] 作成できます。 例：<code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>。[!UICONTROL Quick add] を選択してもイベント名に日時を含めない場合、イベントは現在の時刻から作成され、1 時間続きます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL All day event]</td> 
   <td>イベントが終日イベントの場合は、このオプションを有効にします（開始時刻と終了時刻が不要）。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p>これが終日イベントの場合は、イベントの開始日を入力します。 </p> <p>サポートされる日付形式のリストについては、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> これが終日イベントの場合は、イベントの終了日を入力します。 </p> <p>サポートされる日付形式のリストについては、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>イベントの説明を入力またはマッピングします。このフィールドでは HTML がサポートされています。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Location]</td> 
   <td>イベントの場所をテキスト形式で入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use the default reminder settings for this event]</td> 
   <td>デフォルトのリマインダー設定を使用するには、このオプションを有効にします。[!UICONTROL Reminder] フィールドでカスタムリマインダーを設定した場合、この値は「いいえ」に設定されます。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Reminder] </td> 
   <td> <p>イベントのリマインダーを追加します。各リマインダーについて、リマインダーを設定するメソッドを選択し、リマインダーを設定するイベントまでの時間（分単位）を定義します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attendees]</td> 
   <td>出席者をイベントに追加します。出席者ごとに、名前とメールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show me as]</td> 
   <td>カレンダーを表示している人に、このイベント中に「忙しい」として表示するか「利用可能」として表示するかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Visibility] </td> 
   <td> <p>このイベントの表示を選択します。 </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Default]</b></p> <p>イベントには、カレンダー設定で設定した表示設定が含まれます。</p> </li> 
     <li> <p><b>[!UICONTROL Public]</b></p> <p>カレンダーを共有している人は誰でも、このイベントを表示できます。</p> </li> 
     <li> <p><b>[!UICONTROL Private]</b></p> <p>出席者のみがこのイベントを表示できます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notification about the event creation]</td> 
   <td> <p>新しいイベントの作成に関する通知をすべてのゲストに送信するか、[!DNL Google Calendar] を使用していないゲストに送信するか、または誰にも送信しないかを選択します。</p> <p>ヒント：[!UICONTROL None] オプションは、移行のユースケースにのみ使用することをお勧めします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Guests can modify the event]</td> 
   <td> <p>ゲストがこのイベントを変更できるようにする場合は、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Recurrence]</td> 
   <td>このイベントに適用する繰り返しルールを追加します。各ルールには、繰り返しイベントの [!UICONTROL RRULE]、[!UICONTROL EXRULE]、[!UICONTROL RDATE]、[!UICONTROL EXDATE] 行のリストが必要です。 このフィールドでは、[!UICONTROL DTSTART] 行と [!UICONTROL DTEND] 行は使用できません。イベントの開始時刻と終了時刻は、「開始」フィールドと「終了」フィールドで指定します。 このフィールドは、単一のイベントまたは繰り返しイベントのインスタンスでは省略されます。詳しくは、<a href="https://tools.ietf.org/html/rfc5545#section-3.8.5">RFC5545</a> を参照してください。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an event]

このアクションモジュールでは、既存のイベントを変更できます。

カレンダーとイベント ID を指定します。

このモジュールは、イベントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar] </td> 
   <td> <p>作業するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID] </td> 
   <td> <p>前に作成した更新対象の [!DNL Google Calendar] イベントの ID を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

目的のフィールドに新しい値を入力することで、イベント情報を更新できます。個々のフィールドについて詳しくは、[[!UICONTROL Create an event]](#create-an-event) を参照してください。

#### [!UICONTROL Delete an event]

このアクションモジュールでは、イベントを削除します。

カレンダーとイベント ID を指定します。

このモジュールは、イベントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>削除するイベントを含むカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID]</td> 
   <td> <p> 前に作成した削除対象の [!DNL Google Calendar] イベントの ID を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notification about the event deletion]</td> 
   <td>イベントの削除に関する通知をすべてのゲストに送信するか、[!DNL Google Calendar] を使用しないすべてのゲストに送信するか、または誰にも送信しないかを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### カレンダー

* [[!UICONTROL List calendars]](#list-calendars)
* [[!UICONTROL Get a calendar]](#get-a-calendar)
* [[!UICONTROL Create a calendar]](#create-a-calendar)
* [[!UICONTROL Update a calendar]](#update-a-calendar)
* [[!UICONTROL Delete a calendar]](#delete-a-calendar)
* [[!UICONTROL Clear a calendar]](#clear-a-calendar)

#### [!UICONTROL List calendars]

このアクションモジュールは、ユーザーのカレンダーリストのカレンダーを返します。

このモジュールは、カレンダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Minimum access role]</td> 
   <td> <p>ユーザーの最小アクセス役割を選択します。モジュールは、この最小アクセス役割に基づいてカレンダーを返します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Free Busy Reader]</strong>：ユーザーは空き時間情報を読み取ることができます。 </li> 
     <li><strong>[!UICONTROL Owner]</strong>：ユーザーはイベントの読み取りと変更、制御リストへのアクセスを行うことができます。 </li> 
     <li><strong>[!UICONTROL Reader]</strong>：ユーザーはプライベートでないイベントを読み取ることができます。 </li> 
     <li><strong>[!UICONTROL Writer]</strong>：ユーザーはイベントの読み取りと変更を行うことができます。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show hidden calendars]</td> 
   <td>モジュールが返すリストに非表示のカレンダーを含めるには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すカレンダーの数の上限を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a calendar]

このアクションモジュールは、カレンダーを取得します。

取得するカレンダーの ID を指定します。

このモジュールは、レコードの ID および関連するフィールドと共に、接続を介してアクセスされるカスタムフィールドとその値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>取得するカレンダーを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a calendar]

このアクションモジュールは、新しいカレンダーを作成します。

カレンダーの名前を指定します。

このモジュールは、カレンダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar name]</td> 
   <td> <p> 新しいカレンダーの名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a calendar]

このアクションモジュールは、カレンダーを更新します。

更新するカレンダーの ID を指定します。

このモジュールは、カレンダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>更新するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar name]</td> 
   <td> <p> カレンダーの新しい名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a calendar]

このアクションモジュールは、カレンダーを削除します。

削除するカレンダーの ID を指定します。

このモジュールは、カレンダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>削除するカレンダーの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clear a calendar]

このアクションモジュールは、アカウントのプライマリカレンダーからすべてのイベントを削除します。

消去するカレンダーを含むアカウントへの接続を指定します。

このモジュールは、カレンダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクセス制御ルール

* [[!UICONTROL List access control rules]](#list-access-control-rules)
* [[!UICONTROL Get an access control rule]](#get-an-access-control-rule)
* [[!UICONTROL Create an access control rule]](#create-an-access-control-rule)
* [[!UICONTROL Update an access control rule]](#update-an-access-control-rule)
* [[!UICONTROL Delete an access control rule]](#delete-an-access-control-rule)

#### [!UICONTROL List access control rules]

このアクションモジュールは、カレンダーのアクセス制御リストのルールを返します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>取得するアクセス制御ルールを含むカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>[!DNL Workfront Fusion] が 1 回の実行サイクルで返す結果数の上限を設定します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an access control rule]

このアクションモジュールは、アクセス制御ルールのメタデータを返します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>取得するアクセス制御ルールを含むカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Access control rule ID]</td> 
   <td>取得するアクセス制御ルールを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an access control rule]

このアクションモジュールは、新しいアクセス制御ルールを作成します。

カレンダーの名前を指定します。

このモジュールは、アクセス制御ルールと関連するフィールドの ID と、接続がアクセスするカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>アクセス制御ルールを作成するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Role]</td> 
   <td> <p>アクセスルールに割り当てる役割を選択します。 </p> 
    <ul> 
     <li><strong>[!UICONTROL Free Busy Reader]</strong>：ユーザーは空き時間情報を読み取ることができます。 </li> 
     <li><strong>[!UICONTROL Owner]</strong>：ユーザーはイベントの読み取りと変更、制御リストへのアクセスを行うことができます。 </li> 
     <li><strong>[!UICONTROL Reader]</strong>：ユーザーはプライベートでないイベントを読み取ることができます。 </li> 
     <li><strong>[!UICONTROL Writer]</strong>：ユーザーはイベントの読み取りと変更を行うことができます。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type]</td> 
   <td> <p>スコープのタイプを選択します。 </p> 
    <ul> 
     <li><strong>[!UICONTROL Default]</strong>：パブリックスコープ。 これはデフォルト値です。 </li> 
     <li><strong>[!UICONTROL User]</strong>：範囲を 1 人のユーザーに制限します。 </li> 
     <li><strong>[!UICONTROL Group]</strong>：範囲をグループに制限します。 </li> 
     <li><strong>[!UICONTROL Domain]</strong>：範囲をドメインに制限します。 </li> 
    </ul> <p>注意：[!UICONTROL Default] ーザーまたはパブリックに付与される権限の範囲は、認証済みまたは未認証の任意のユーザーに適用されます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value]</td> 
   <td>範囲のタイプに応じて、ユーザーまたはグループのメールアドレス、またはドメインの名前を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notifications]</td> 
   <td> <p>アクセスの変更に関する通知を送信するには、このオプションを有効にします。 </p> <p>メモ：アクセスの削除に関する通知はありません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an access control rule]

このアクションモジュールは、アクセス制御ルールを更新します。

カレンダーの名前を指定します。

このモジュールは、アクセス制御ルールと関連するフィールドの ID と、接続がアクセスするカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>更新するアクセス制御ルールを含むカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Access control rule ID]</td> 
   <td>更新するアクセス制御ルールを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Role]</td> 
   <td> <p>アクセスルールに割り当てる役割を選択します。 </p> 
    <ul> 
     <li><strong>[!UICONTROL None]</strong>：この役割からのアクセスはできません。</li> 
     <li><strong>[!UICONTROL Free Busy Reader]</strong>：ユーザーは空き時間情報を読み取ることができます。 </li> 
     <li><strong>[!UICONTROL Owner]</strong>：ユーザーはイベントの読み取りと変更、制御リストへのアクセスを行うことができます。 </li> 
     <li><strong>[!UICONTROL Reader]</strong>：ユーザーはプライベートでないイベントを読み取ることができます。 </li> 
     <li><strong>[!UICONTROL Writer]</strong>：ユーザーはイベントの読み取りと変更を行うことができます。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notifications]</td> 
   <td> <p>アクセスの変更に関する通知を送信するには、このオプションを有効にします。 </p> <p>メモ：アクセスの削除に関する通知はありません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an access control rule]

このアクションモジュールは、アクセス制御ルールを削除します。

カレンダーの名前を指定します。

このモジュールは、アクセス制御ルールと関連するフィールドの ID と、接続がアクセスするカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>削除するアクセス制御ルールを含むカレンダーの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Access control rule ID]</td> 
   <td>削除するアクセス制御ルールの ID を選択またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### イテレーター（廃止）

[!UICONTROL iterate attachments] モジュールと [!UICONTROL iterate attendees] モジュールは非推奨（廃止予定）になりました。 添付ファイルまたは出席者を繰り返し処理するには、[!UICONTROL Flow Control]/[!UICONTROL Iterator] モジュールを使用します。 詳しくは、[Iterator モジュール ](/help/workfront-fusion/references/modules/iterator-module.md) を参照してください

### その他

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Get Free/Busy Information]](#get-freebusy-information)

#### [!UICONTROL Make an API Call]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td><code>https://www.googleapis.com/calendar</code> からの相対パスを入力します。例： <code>/v3/users/me/calendarList</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>標準の JSON オブジェクトの形式でリクエストのヘッダーを追加します（例：<code>{"Content-type":"application/json"}</code>）。認証ヘッダーは [!DNL Workfront Fusion] によって追加されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：   <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Free/Busy Information]

このアクションモジュールは、一連のカレンダーの空き時間情報を返します。

このモジュールは、カレンダーの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>[!DNL Google Calendar] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Minimum time]</td> 
   <td> <p> 情報を取得する間隔の開始点を入力します。</p> <p> サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum time]</td> 
   <td> <p> 情報を取得する間隔の終了点を入力します。 </p> <p>サポートされる日付と時刻の形式の一覧について詳しくは、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendars]</td> 
   <td> <p>情報を取得する各カレンダーで、「<strong>追加</strong>」をクリックして、カレンダー ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

## イベント前のシナリオのトリガー

標準の [!DNL Google Calendar] メールリマインダーと [!UICONTROL Webhooks] >[!UICONTROL Custom mailhook] モジュールを使用して、イベントの指定時間前にシナリオをトリガーできます。

1. [!UICONTROL Google Calendar]/[!UICONTROL Update an event] モジュールを使用して、イベントにリマインダー用のメールを追加します。

   ![](/help/workfront-fusion/references/apps-and-modules/assets/trigger-scen-before-event-350x209.png)

1. [!UICONTROL Webhooks]/[!UICONTROL Custom mailhook] モジュールから始まる新しいシナリオを作成します。

   1. メールフックのメールアドレスをコピーします。
   1. シナリオを保存し、実行します。

1. [!DNL Gmail] で、[!DNL Google Calendar] メールリマインダーをメールフックのメールアドレスにリダイレクトします。

   1. **[!UICONTROL [!DNL Gmail] settings]** を開けなさい。
   1. 「**[!UICONTROL Forwarding and POP/IMAP]**」タブを開きます。
   1. 「**[!UICONTROL Add a forwarding address].**」をクリックします。
   1. コピーしたメールフックのメールアドレスを貼り付け、&#x200B;**[!UICONTROL Next]** をクリックし、ポップアップウィンドウで **[!UICONTROL Proceed]** キーを押して確認し、「**[!UICONTROL OK]**」をクリックします。

   1. [!DNL Workfront Fusion] で、新しいシナリオに切り替えると、確認メールを受信して実行が完了します。
   1. モジュールの上のバブルをクリックして、モジュールの出力を調べます。
   1. `Text` 項目を展開して、確認コードをコピーします。

      ![](/help/workfront-fusion/references/apps-and-modules/assets/confirmation-code-350x252.png)

   1. Gmail で、編集ボックスに確認コードを貼り付けて、次の&#x200B;**[!UICONTROL Verify]** をクリックします。

      ![](/help/workfront-fusion/references/apps-and-modules/assets/paste-code-350x46.png)

   1. 「**[!UICONTROL Filters and Blocked Addresses]**」タブを開きます。
   1. **[!UICONTROL Create a new filter]** をクリックします。
   1. `     calendar-notification@google.com` からのすべてのメールのフィルターを設定し、&#x200B;**[!UICONTROL Create a filter]** をクリックします。
   1. 「**[!UICONTROL Forward it to]**」を選択し、リストから mailhook のメールアドレスを選択します。
   1. 「**[!UICONTROL Create filter]**」をクリックして、フィルターを作成します。

1. （オプション） [!DNL Workfront Fusion] では、[!UICONTROL Text parser]/[!UICONTROL Match pattern] モジュールを [!UICONTROL Webhooks]/[!UICONTROL Custom mailhook] モジュールの後に追加して、メールのHTMLコードを解析し、必要な情報を取得します。

   例えば、モジュールを次のように設定して、イベントの ID を取得できます。

   *パターン*：`<meta itemprop="eventId/googleCalendar" content="(?<evenitID>.*?)"/>`

   *テキスト*:[!UICONTROL Webhooks] >[!UICONTROL Custom mailhook] モジュールから出力された `HTML content` 項目。
