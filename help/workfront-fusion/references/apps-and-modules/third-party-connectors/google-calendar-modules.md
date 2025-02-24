---
title: Google カレンダーモジュール
description: ' [!DNL Adobe Workfront Fusion] シナリオでは、Google Calendar を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 6e514204-cd8e-4f30-bbbb-b8fbe48fc670
source-git-commit: 160e503adeca5404e18fd0cba9f475fee8510a48
workflow-type: tm+mt
source-wordcount: '2315'
ht-degree: 59%

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


* [トリガー](#triggers)
* [アクション](#actions)
* [イテレータ](#iterators)

### トリガー

* [イベントを監視する](#watch-events)
* [イベントを視聴（インスタント）](#watch-events-instant)

#### イベントを監視する

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
   <td>[!UICONTROL Watch]</td> 
   <td> <p>新しいイベントのみを視聴するか、新しいイベントとすべての変更を視聴するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show deleted events]</td> 
   <td> <p>削除されたイベントを含めるには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query] </td> 
   <td> <p>結果を返すテキストを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of events]</td> 
   <td> <p> 1 回のサイクル中に [!DNL Workfront Fusion] が処理する結果の最大数（シナリオ実行あたりの繰り返し数）を設定します。値が大きすぎると、指定されたサードパーティサービス側で接続が中断される可能性があります（タイムアウト）。[!DNL Workfront Fusion] はこれに影響しません。より小さい値を設定し、最大サイクル数としてより大きい値を定義するか、シナリオをより頻繁に実行することをお勧めします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### イベントを視聴（インスタント）

このトリガーモジュールは、メールフックを使用して、イベントへの招待者として使用できるメールアドレスを作成します。 モジュールは、メールアドレスの招待先のイベントに基づいてシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Mailhook] </td> 
   <td> <p>このモジュールに使用するメールフックを選択します。 新しいメールフックを作成するには、「<b> 追加 </b>」をクリックして、メールフックに使用する接続を入力します。</p><p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of events]</td> 
   <td> <p> 1 回のサイクル中に [!DNL Workfront Fusion] が処理する結果の最大数（シナリオ実行あたりの繰り返し数）を設定します。値が大きすぎると、指定されたサードパーティサービス側で接続が中断される可能性があります（タイムアウト）。[!DNL Workfront Fusion] はこれに影響しません。より小さい値を設定し、最大サイクル数としてより大きい値を定義するか、シナリオをより頻繁に実行することをお勧めします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [カレンダーの作成](#create-a-calendar)
* [イベントの作成](#create-an-event)
* [イベントの削除](#delete-an-event)
* [イベントの取得](#get-events)
* [イベントの更新](#update-an-event)

#### カレンダーの作成

このアクションモジュールは、アカウントに関連付けられたカレンダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Google Calendar] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe [!DNL Workfront Fusion] への接続の作成 - 基本手順</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Color] </td> 
   <td> <p>カレンダーに関連付ける色を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar name] </td> 
   <td> <p>新しいカレンダーの名前を入力またはマップします。</p> </td> 
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
   <td>[!UICONTROL Calendar]</td> 
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
   <td> <p>イベントの開始日時を入力またはマッピングします。 </p> <p>サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> イベントの終了日時を入力またはマッピングします。 </p> <p>サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
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
   <td> <p>イベントのリマインダーを追加します。追加するリマインダーごとに、「<b> 項目を追加 </b>」をクリックし、リマインダーを受信する方法を選択して、リマインダーを受信するイベントまでの時間（分単位）を定義します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attendees]</td> 
   <td>出席者をイベントに追加します。各出席者について、「<b> 出席者を追加 </b>」をクリックし、名前とメールアドレスを入力またはマッピングします。</td> 
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
   <td>[!UICONTROL Calendar]</td> 
   <td> <p>削除するイベントを含むカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID]</td> 
   <td> <p> 前に作成した削除対象の [!DNL Google Calendar] イベントの ID を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get events]

このモジュールは、指定した条件に基づいて、選択したカレンダー内のイベントに関する情報を取得します。

カレンダーと検索のパラメーターを指定します。

モジュールは、イベントの ID と関連フィールド、および接続がアクセスするカスタムフィールドと値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

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
   <td>[!UICONTROL Calendar]</td> 
   <td> <p>イベントを取得するカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p> イベントが開始する日付を入力またはマッピングします。また、このモジュールは、この日付より前に開始し、入力された開始日にまだ発生しているイベントを取得します。 </p> <p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> イベントが終了する日付を入力またはマッピングします。 </p> <p> サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
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
   <td>[!UICONTROL Mazimum number of returned events]</td> 
   <td> <p>[!DNL Workfront Fusion] が 1 回の実行サイクルで返すイベントの数の上限を設定します。</p> </td> 
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
  </tr>   <tr> 
   <td>[!UICONTROL Event name]</td> 
   <td> <p> イベントの名前を入力またはマッピングします。 </p> <p>注意：「[!UICONTROL Create an event]」フィールドで「[!UICONTROL Quick add]」を選択した場合は、イベントの日時を含めて、その日時のイベント [!DNL Workfront Fusion] 作成できます。 例：<code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>。[!UICONTROL Quick add] を選択してもイベント名に日時を含めない場合、イベントは現在の時刻から作成され、1 時間続きます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL All day event]</td> 
   <td>イベントが終日イベントの場合は、このオプションを有効にします（開始時刻と終了時刻が不要）。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p>イベントの開始日時を入力またはマッピングします。 </p> <p>サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> イベントの終了日時を入力またはマッピングします。 </p> <p>サポートされる日付形式のリストについては、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
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
   <td> <p>イベントのリマインダーを追加します。追加するリマインダーごとに、「<b> 項目を追加 </b>」をクリックし、リマインダーを受信する方法を選択して、リマインダーを受信するイベントまでの時間（分単位）を定義します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attendees]</td> 
   <td>出席者をイベントに追加します。各出席者について、「<b> 出席者を追加 </b>」をクリックし、名前とメールアドレスを入力またはマッピングします。</td> 
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

### イテレータ

#### 添付ファイルの反復

このアクションモジュールは、イベントへの添付ファイルを反復処理し、各添付ファイルを個別のバンドルとして出力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module] </td> 
   <td> このシナリオで、反復する添付ファイルを含んだイベントを出力するモジュールを選択します。 </td> 
  </tr> 
 </tbody> 
</table>

#### 出席者の反復

このアクションモジュールは、イベントの出席者を繰り返し処理し、各出席者を別々のバンドルに出力します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module] </td> 
   <td> 反復する出席者を含むイベントを出力する、このシナリオのモジュールを選択します。 </td> 
  </tr> 
 </tbody> 
</table>





## イベント前のシナリオのトリガー

標準の [!DNL Google Calendar] メールリマインダーと [!UICONTROL Webhooks] >[!UICONTROL Custom mailhook] モジュールを使用して、イベントの指定時間前にシナリオをトリガーできます。

1. [!UICONTROL Google Calendar]/[!UICONTROL Update an event] モジュールを使用して、イベントにリマインダー用のメールを追加します。

   ![ イベント前のトリガーシナリオ ](/help/workfront-fusion/references/apps-and-modules/assets/trigger-scen-before-event-350x209.png)

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

      ![ 確認コード ](/help/workfront-fusion/references/apps-and-modules/assets/confirmation-code-350x252.png)

   1. Gmail で、編集ボックスに確認コードを貼り付けて、次の&#x200B;**[!UICONTROL Verify]** をクリックします。

      ![ コードを貼り付け ](/help/workfront-fusion/references/apps-and-modules/assets/paste-code-350x46.png)

   1. 「**[!UICONTROL Filters and Blocked Addresses]**」タブを開きます。
   1. **[!UICONTROL Create a new filter]** をクリックします。
   1. `     calendar-notification@google.com` からのすべてのメールのフィルターを設定し、&#x200B;**[!UICONTROL Create a filter]** をクリックします。
   1. 「**[!UICONTROL Forward it to]**」を選択し、リストから mailhook のメールアドレスを選択します。
   1. 「**[!UICONTROL Create filter]**」をクリックして、フィルターを作成します。

1. （オプション） [!DNL Workfront Fusion] では、[!UICONTROL Text parser]/[!UICONTROL Match pattern] モジュールを [!UICONTROL Webhooks]/[!UICONTROL Custom mailhook] モジュールの後に追加して、メールのHTML コードを解析し、必要な情報を取得します。

   例えば、モジュールを次のように設定して、イベントの ID を取得できます。

   *パターン*：`<meta itemprop="eventId/googleCalendar" content="(?<evenitID>.*?)"/>`

   *テキスト*:[!UICONTROL Webhooks] >[!UICONTROL Custom mailhook] モジュールから出力された `HTML content` 項目。
