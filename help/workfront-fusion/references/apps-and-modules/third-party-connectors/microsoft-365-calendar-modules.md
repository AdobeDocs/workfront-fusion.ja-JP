---
title: Microsoft Office 365 カレンダー
description: ' [!DNL Adobe Workfront Fusion] シナリオ内では、Microsoft Office 365 カレンダーを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: fdecf740-e735-4569-b1a2-7c25c751ba42
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1962'
ht-degree: 75%

---

# [!DNL Microsoft Office 365 Calendar]

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Microsoft Office 365 Calendar] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

[!DNL Microsoft Office 365 Calendar] モジュールを使用するには、[!DNL Microsoft Office 365 Calendar] アカウントが必要です。

## Microsoft Office 365 カレンダー API に関する情報

Microsoft Office 365 カレンダーコネクタは、次を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v2.0.10</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Office 365 Calendar] サービスを [!DNL Workfront Fusion] に接続

[!DNL Office 365 Calendar] アカウントを [!UICONTROL Workfront Fusion] に接続する方法については、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

## [!DNL Microsoft Office 365 Calendar] モジュールとそのフィールド

[!DNL Microsoft Office 365 Calendar] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Microsoft Office 365 Calendar] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [イベント](#event)
* [カレンダー](#calendar)
* [その他](#other)

### イベント

* [[!UICONTROL イベントを作成]](#create-an-event)
* [[!UICONTROL イベントを削除]](#delete-an-event)
* [[!UICONTROL イベントを取得]](#get-an-event)
* [[!UICONTROL イベントの検索]](#search-events)
* [[!UICONTROL イベントの更新]](#update-an-event)
* [[!UICONTROL イベントの監視]](#watch-events)

#### [!UICONTROL イベントを作成]

このアクションモジュールは、イベントを新規作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>作成したイベントのタイトルを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start date]</td> 
   <td> イベントが開始する時点を、日付と時刻の組み合わせで入力します。<code>{date}T{time}</code> 形式を使用します。例：<code>2017-08-29T04:00:00.0000000</code>。サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End date]</td> 
   <td> イベントが終了する時点を、日付と時間の組み合わせで入力します。<code>{date}T{time}</code> 形式を使用します。例：<code>2017-08-29T04:00:00.0000000</code>。サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder on]</td> 
   <td>このイベントのリマインダーをアクティベートするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder]</td> 
   <td>リマインダーをトリガーするイベントの開始前の分数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>このイベントの重要度を選択します。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sensitivity] </td> 
   <td> <p>このイベントの機密度を選択します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>受信者に「[!UICONTROL Please treat this as Personal]」というメッセージが表示されます。</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>受信者に「[!UICONTROL Please treat this as Private]」というメッセージが表示されます。このイベントは、受信者の受信ボックスルールによって転送またはリダイレクトされません。</p> </li> 
     <li> <p><strong>[!UICONTROL Confidential]</strong> </p> <p>受信者に「[!UICONTROL Please treat this as Confidential]」というメッセージが表示されます。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content type]</td> 
   <td>本文の内容をプレーンテキストにするか、HTMLにするかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td>イベントに関連付けられたメッセージの本文を入力またはマッピングします。HTML 形式またはテキスト形式で指定できます（上記の「[!UICONTROL Body Content Type]」フィールドで指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Location]</td> 
   <td> <p>イベントの場所の詳細を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Response requested]</td> 
   <td>招待者に、イベントへの招待状への返信をリクエストする場合には、「<strong>[!UICONTROL Yes]</strong>」を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show as]</td> 
   <td> <p>カレンダーを表示するユーザーに対してどのようにイベントが表示されるかを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Free]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL Busy]</li> 
     <li>[!UICONTROL Out of office]</li> 
     <li>[!UICONTROL Working elsewhere]</li> 
     <li>[!UICONTROL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attendees]</p> </td> 
   <td> <p>招待する各出席者について、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>出席者の名前を入力またはマップします。</p> </li> 
     <li> <p><strong>[!UICONTROL Email]</strong> </p> <p>出席者のメールアドレスを入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL カテゴリ &#x200B;]</td> 
   <td>イベントをカレンダーに表示するカテゴリごとに、「<b> 項目を追加 </b>」をクリックして、カテゴリを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イベントを削除]

このアクションモジュールは、既存のイベントを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>削除するイベントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イベントを取得]

このアクションモジュールは、指定されたイベントの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>詳細を取得するイベントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イベントの検索]

この検索モジュールは、選択したカレンダーでイベントが作成、アップデート、削除、開始、終了されたときに、イベントの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>イベントを監視するカレンダーが含まれている [!UICONTROL calendar group] を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar]</td> 
   <td> <p>監視する特定のカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>結果をフィルタリングするフィルター条件を設定します。以下のプロパティでフィルタリングできます。</p> 
    <ul> 
     <li>[!UICONTROL Subject]</li> 
     <li>[!UICONTROL Event ID]</li> 
     <li>[!UICONTROL Created Date Time]</li> 
     <li>[!UICONTROL Last Modified Date Time]</li> 
     <li>[!UICONTROL Body Preview]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>結果の並べ替え方法を選択します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Subject]</strong>、昇順または降順</li> 
     <li><strong>[!UICONTROL Created Date Time]</strong>、昇順または降順</li> 
     <li><strong>[!UICONTROL Last Modified Date Time]</strong>、昇順または降順</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>[!DNL Workfront Fusion] が 1 回のシナリオ実行サイクルで返すイベントの最大数を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イベントの更新]

このアクションモジュールは、既存のイベントを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td>更新するイベントの ID を入力、マッピングまたは選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>イベントの新しいタイトルを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start date]</td> 
   <td> イベントが開始する時点を、日付と時刻の組み合わせで入力します。<code>{date}T{time}</code> 形式を使用します。例：<code>2017-08-29T04:00:00.0000000</code>。サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型強制：[!DNL Adobe Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End date]</td> 
   <td> イベントが終了する時点を、日付と時間の組み合わせで入力します。<code>({date}T{time}</code> 形式を使用します。例：<code>2017-08-29T04:00:00.0000000</code>。サポートされる日付と時刻の形式の一覧については、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> での型強制を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder on]</td> 
   <td>このイベントのリマインダーをアクティベートするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder]</td> 
   <td>リマインダーをトリガーするイベントの開始前の分数を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>このイベントの重要度を選択します。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sensitivity] </td> 
   <td> <p>このイベントの機密度を選択します。</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>受信者に「[!UICONTROL Please treat this as Personal]」というメッセージが表示されます。</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>受信者に「[!UICONTROL Please treat this as Private]」というメッセージが表示されます。このイベントは、受信者の受信ボックスルールによって転送またはリダイレクトされません。</p> </li> 
     <li> <p><strong>[!UICONTROL Confidential]</strong> </p> <p>受信者に「[!UICONTROL Please treat this as Confidential]」というメッセージが表示されます。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content type]</td> 
   <td>イベントに関連付けられるメッセージの本文の内容を、プレーンテキストにするか HTML にするかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td>イベントに関連付けられたメッセージの本文を入力またはマッピングします。HTML 形式またはテキスト形式で指定できます（上記の「[!UICONTROL Body Content Type]」フィールドで指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Location]</td> 
   <td> <p>イベントの場所の詳細を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Response requested]</td> 
   <td>招待者に、イベントへの招待状への返信をリクエストする場合には、「<strong>[!UICONTROL Yes]</strong>」を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show as]</td> 
   <td> <p>カレンダーを表示するユーザーに対してどのようにイベントが表示されるかを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Free]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL Busy]</li> 
     <li>[!UICONTROL Out of office]</li> 
     <li>[!UICONTROL Working elsewhere]</li> 
     <li>[!DNL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attendees]</p> </td> 
   <td> <p>イベントの出席者を追加します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>出席者の名前を入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Email]</strong> </p> <p>参加者のメールアドレスを入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>イベントでカレンダーに表示するカテゴリを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL イベントの監視]

このトリガーモジュールは、選択したカレンダーでイベントが作成、アップデート、削除、開始、終了されたときに、イベントの詳細を取得します。

>[!NOTE]
>
>削除された一連のイベントを監視するには、[!UICONTROL イベントを監視]フィールドで[!UICONTROL アップデート時刻別]を選択します。このモジュールは、削除された単一のイベントや、削除された一連のイベントを監視しません。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch events]</td> 
   <td> <p>イベントの監視方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By Created Time]</strong> </p> <p>新しいイベントを監視します。</p> </li> 
     <li> <p><strong>[!UICONTROL By Updated Time]</strong> </p> <p>アップデートされたイベントを監視します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>イベントを監視するカレンダーが含まれている [!UICONTROL calendar group] を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar]</td> 
   <td> <p>監視する特定のカレンダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>件名、イベント ID、本文で結果をフィルタリングするフィルター条件を設定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>[!DNL Workfront Fusion] が 1 回のシナリオ実行サイクルで返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### カレンダー

* [[!UICONTROL カレンダーを作成]](#create-a-calendar)
* [[!UICONTROL カレンダーを削除]](#delete-a-calendar)
* [[!UICONTROL カレンダーを取得]](#get-a-calendar)
* [[!UICONTROL カレンダーをリスト表示]](#list-calendars)
* [[!UICONTROL カレンダーをアップデート]](#update-a-calendar)



#### [!UICONTROL カレンダーを作成]

このアクション モジュールは、Office 365 アカウントに新しいカレンダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar name]</td> 
   <td> <p>新しいカレンダーの名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カレンダーの削除]

このアクションモジュールは、既存のカレンダーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td>削除するカレンダーの[!UICONTROL Calendar] ID を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カレンダーを取得]

このアクションモジュールは、1 つのカレンダーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>詳細を取得するカレンダーの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カレンダーをリスト表示]

この検索モジュールは、認証済みユーザーのカレンダーのすべてのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>リストに表示するカレンダーが含まれている [!UICONTROL calendar group] を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>[!DNL Workfront Fusion] が 1 回のシナリオ実行サイクルで返すカレンダーの最大数を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カレンダーの更新]

このアクションモジュールは、既存のカレンダーを編集します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td>アップデートするカレンダーの[!UICONTROL Calendar ID] を入力します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Calendar name]</td> 
   <td> <p>カレンダーの新しい名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

#### [!UICONTROL API 呼び出しの実行]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://graph.microsoft.com</code> からの相対パスを入力します。例：<code> /v1.0/me/events</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例えば、<code>{"Content-type":"application/json"}</code>。認証ヘッダーは [!DNL Workfront Fusion] によって追加されます。</p> </td> 
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
