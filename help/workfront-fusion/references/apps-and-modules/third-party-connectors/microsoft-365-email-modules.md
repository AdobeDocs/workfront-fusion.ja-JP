---
title: Microsoft Office 365 メール
description: Adobe Workfront Fusion のシナリオでは、Microsoft Office 365 メールを使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 5d4072ba-c598-4347-a42f-c59c7add0a1b
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2921'
ht-degree: 43%

---

# [!DNL Microsoft Office 365 Email] モジュール

Adobe Workfront Fusion のシナリオでは、[!UICONTROL Microsoft Office 365 Email] を使用するワークフローを自動化できるほか、複数のサードパーティ製アプリケーションやサービスに接続することもできます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

[!DNL Microsoft Office 365 Email] モジュールを使用するには、[!DNL Microsoft Office 365 Email] アカウントが必要です。

## Microsoft Office 365 のメール API に関する情報

Microsoft Office 365 メールコネクタでは、次を使用します。

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
   <td>v2.6.5</td> 
  </tr>
 </tbody> 
 </table>

## Workfront Fusion への [!DNL Office 365 Email] サービスの接続

[!DNL Office 365 Email] アカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、[[!UICONTROL Adobe Workfront Fusion] への接続の作成 - 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

>[!NOTE]
>
>一部のMicrosoft アプリは、同じ接続を使用し、これは個々のユーザー権限に関連付けられています。 そのため、接続を作成すると、権限同意画面に、現在のアプリケーションに必要な新しい権限に加え、このユーザーの接続に以前に付与された権限が表示されます。
>
>例えば、ユーザーが Excel コネクタを使用して「テーブルの読み取り」権限を付与され、Outlook コネクタにメールを読み取るための接続を作成した場合、権限の同意画面には、既に付与されている「テーブルの読み取り」権限と、新しく必要な「メールの書き込み」権限の両方が表示されます。

## [!DNL Microsoft Office 365 Email] モジュールとそのフィールド

[!DNL Microsoft Office 365 Email] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Microsoft Office 365 Email]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [メッセージ](#message)
* [ドラフトメッセージ](#draft-message)
* [添付ファイル](#attachment)
* [その他](#other)

### メッセージ

* [[!UICONTROL &#x200B; メッセージの作成と送信（レガシー） &#x200B;]](#create-and-send-a-message)
* [[!UICONTROL メッセージの削除]](#delete-a-message)
* [[!UICONTROL メッセージの取得]](#get-a-message)
* [[!UICONTROL メッセージの移動]](#move-a-message)
* [[!UICONTROL メッセージの検索]](#search-messages)
* [[!UICONTROL メッセージの監視]](#watch-messages)



#### [!UICONTROL &#x200B; メッセージの作成と送信（レガシー） &#x200B;]

このアクションモジュールは、メールメッセージを作成して送信します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>メッセージの件名行を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>メールのメッセージ本文テキストを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>メールの重要度を次の中から選択します。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>メールの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>メールのコピーの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>他の受信者が名前やメールアドレスを表示できないようにメールのコピーを送信する受信者ごとに、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>メールに追加する各添付ファイルに対して、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source ファイル &#x200B;]</strong> </p> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet Message Headers]</td> 
   <td> <p>メールに追加するヘッダーごとに、「<b> 項目を追加 </b>」をクリックして次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>ヘッダーの名前を入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>ヘッダーの値を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの削除]

既存のメールメッセージを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> 削除するメッセージの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの取得]

このアクションモジュールは、特定のメッセージのメタデータを取得します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> メタデータを取得するメッセージの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get MIME contents]</td> 
   <td>メッセージの MIME コンテンツに関するデータを取得するには、このオプションを有効にします。[!UICONTROL MIME] コンテンツには、画像、オーディオ、ビデオまたはその他のファイルタイプが含まれる可能性があります。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの移動]

このアクション モジュールは、メールボックス内の選択されたフォルダーに電子メール メッセージを移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> 別のフォルダーに移動するメッセージの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mail Folder] </td> 
   <td> <p>メッセージを移動するフォルダーの ID を選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの検索]

特定の条件に基づいてメッセージを検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Mail Folder]</td> 
   <td> <p>検索するメッセージを含んだフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>検索クエリを入力します。検索クエリの記述方法については、[!DNL Microsoft] サポート記事の「<a href="https://support.microsoft.com/ja-jp/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=ja-jp&rs=ja-jp&ad=jp">[!DNL Outlook.com]</a> でメールや連絡先を検索する」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>結果の並べ替え方法を選択します。</p> 
    <ul> 
     <li>[!UICONTROL Subject (Ascending or descending)]</li> 
     <li>[!UICONTROL Created Date Time (Ascending or descending)]</li> 
     <li>[!UICONTROL Last Modified Date Time (Ascending or descending)]</li> 
     <li>[!UICONTROL Received Date Time (Ascending or descending)]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Workfront Fusion が 1 つのシナリオ実行サイクルで返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの監視]

このトリガーモジュールは、新しいメールメッセージが送信または受信されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Watch Messages]</p> </td> 
   <td> <p>監視するメッセージを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Only Unread]</li> 
     <li>[!UICONTROL Only read]</li> 
     <li>[!UICONTROL All]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mail Folder]</td> 
   <td> <p>監視するメッセージが含まれているフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>検索クエリを入力します。モジュールは、このクエリに一致するメッセージを返します。 検索クエリの作成方法について詳しくは、[!DNL Microsoft]サポート記事の<a href="https://support.microsoft.com/ja-jp/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=ja-jp&rs=ja-jp&ad=jp">[!DNL Outlook.com]</a> でメールと人物を検索を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Workfront Fusion が 1 つのシナリオ実行サイクルで返すメッセージの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### ドラフトメッセージ

* [ドラフトメッセージの作成](#create-a-draft-message)
* [ドラフトメッセージの送信](#send-a-draft-message)
* [メッセージを更新](#update-a-message)

#### [!UICONTROL ドラフトメッセージの作成]

このアクションモジュールは、新しいメールメッセージをドラフトとして作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>メッセージの件名行を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body Content Type]</td> 
   <td>メッセージの本文の内容を HTML にするかテキストにするかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>メールのメッセージ本文テキストを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>メールの重要度を次の中から選択します。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>メールの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>メールのコピーの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>他の受信者が名前やメールアドレスを表示できないようにメールのコピーを送信する受信者ごとに、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>メールに追加する各添付ファイルに対して、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source ファイル &#x200B;]</strong> </p> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ドラフトメッセージの送信]

このアクションモジュールは、現在ドラフトになっているメールメッセージを送信します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Draft Message ID]</td> 
   <td> <p> 送信するドラフトのメッセージ ID を選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの更新]

このアクションモジュールは、既存のメッセージを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a message ID]</td> 
   <td> <p>更新するメッセージを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter Manually]</strong> </p> <p>メッセージ ID を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新するメッセージを含むフォルダーを選択し、メッセージを選択します</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>メッセージの件名行を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>メールのメッセージ本文テキストを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>メールの重要度を次の中から選択します。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>メールの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>メールのコピーの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>他の受信者が名前やメールアドレスを表示できないようにメールのコピーを送信する受信者ごとに、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>メールに追加する各添付ファイルに対して、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source ファイル &#x200B;]</strong> </p> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark it as Read]</td> 
   <td>このオプションを有効にすると、更新されたメッセージが既読としてマークされます。</td> 
  </tr> 
 </tbody> 
</table>

### 添付ファイル

* [[!UICONTROL 添付ファイルのダウンロード]](#download-an-attachment)
* [[!UICONTROL 添付ファイルをリスト]](#list-attachments)

#### [!UICONTROL 添付ファイルのダウンロード]

このモジュールは、指定された添付ファイルをダウンロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> ダウンロードする添付ファイルを含むメッセージの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment ID]</td> 
   <td> <p>ダウンロードする添付ファイルの ID を入力またはマッピングします。 添付リストモジュールを使用すると、このアイデアを見つけることができます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 添付ファイルをリスト]

このモジュールは、指定されたメッセージに属する添付ファイルのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> 添付ファイルを取得するメッセージの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが返す添付ファイルの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

* [[!UICONTROL 添付ファイルの追加]](#add-an-attachment)
* [メッセージの作成と送信](#create-and-send-a-message)
* [[!UICONTROL API 呼び出しの実行]](#make-an-api-call)

#### [!UICONTROL 添付ファイルの追加]

このモジュールは、メッセージにサイズの大きい添付ファイルを追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> 添付ファイルを追加するメッセージの ID を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールからファイルを選択するか、ソースファイルの名前とデータをマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メッセージの作成と送信]

このアクションモジュールは、メールメッセージを作成して送信します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>メッセージの件名行を入力またはマッピングします。</p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>メールのメッセージ本文テキストを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>メールの重要度を次の中から選択します。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>メールの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>メールのコピーの送信先の受信者ごとに、「<b> 項目を追加 </b>」をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>他の受信者が名前やメールアドレスを表示できないようにメールのコピーを送信する受信者ごとに、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>連絡先のメールアドレスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>連絡先の名前を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>メールに追加する各添付ファイルに対して、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source ファイル &#x200B;]</strong> </p> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet Message Headers]</td> 
   <td> <p>メールのメッセージヘッダーを追加します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>ヘッダーの名前を入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>ヘッダーの値を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL 送信元メールアドレス &#x200B;]</td> 
   <td> <p> 共有メールアドレスを使用するには、ここにアドレスを入力します。 このモジュールに使用される接続で使用される資格情報を持つユーザーは、共有フォルダーにアクセスできる必要があります。<p>接続所有者自身のメールアドレスを使用する場合は、このフィールドを空白のままにします。</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL API 呼び出しの実行]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Office 365] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://graph.microsoft.com</code> からの相対パスを入力します。例：<code> /v1.0/me/messages</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例えば、<code>{"Content-type":"application/json"}</code>。Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>
