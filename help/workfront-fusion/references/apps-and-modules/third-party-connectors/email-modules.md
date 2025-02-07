---
title: メールモジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、メールアカウントを複数のサードパーティアプリケーションやサービスに接続できます。これにより、IMAP 経由でメールをダウンロードしたり、SMTP 経由でメールを送信したり、新しい下書きを作成したり、フォルダー間でメールを移動およびコピーしたり、メールを既読または未読としてマークしたり、メールを削除したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: add63edf94cc430113bf2cfd0c389cca04aa92f8
workflow-type: tm+mt
source-wordcount: '2023'
ht-degree: 49%

---

# メールモジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、メールアカウントを複数のサードパーティアプリケーションやサービスに接続できます。これにより、IMAP 経由でメールをダウンロードしたり、SMTP 経由でメールを送信したり、新しい下書きを作成したり、フォルダー間でメールを移動およびコピーしたり、メールを既読または未読としてマークしたり、メールを削除したりすることができます。

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
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
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

[!DNL Adobe Workfront Fusion] のライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  のライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## Workfront Fusion にメールを接続 {#connect-your-email-to-workfront-fusion}

* [Google に接続](#connect-to-google)
* [他のメールサービス （IMAP）への接続](#connect-to-other-email-services-smap)

### [!DNL Google] に接続

[!DNL Google] アカウントへの接続を必要とするメールモジュールを含むシナリオを作成するには、このオプションを使用します。これは、スコープが制限されたアカウントです。

[!DNL Google] アカウントへの接続を、メールモジュール内から直接作成できます。

1. 任意の電子メールモジュールで、「[!UICONTROL Connection]」フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続タイプとして「**[!DNL Google]**」を選択します。
1. 接続に名前を入力します。
1. （任意） [!UICONTROL [!DNL Google] Client ID] と [!UICONTROL Client Secret] を入力します。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

### 他のメールサービス （IMAP）への接続

IMAP 接続を使用すると、メールボックスにリモートからアクセスしたり、メールボックス内のメッセージを読み取ったり、操作したりできます。 IMAP 接続は、ほとんどのメールモジュールで使用されます。

1. 任意の電子メールモジュールで、「[!UICONTROL Connection]」フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続タイプとして「**[!UICONTROL Others (SMTP)]**」を選択します。
1. 接続の **[!UICONTROL Name]** を入力します。
1. リストから **[!UICONTROL Email provider]** を選択します。 メールプロバイダーがリストにない場合は、「その他」を選択します。
1. **[!UICONTROL User name]** と、メールアカウントの **[!UICONTROL Password]** を入力します。
1. （条件付き）プロバイダーがリストに含まれていない場合は、**[!UICONTROL SMTP server]** と **[!UICONTROL Port]** を入力し、**[!UICONTROL Use a secure connection (TLS)]** 用するかどうかを指定します。 この情報を見つけるには、メールボックスの [!UICONTROL Help] セクションを確認してください。 この情報が不明な場合は、メールサービスプロバイダーにお問い合わせください。
1. 自己署名証明書を使用するには、「**未認証の証明書を拒否**」オプションを有効にし、自己署名証明書をアップロードします。 手順については、[ 自己署名証明書のアップロード ](#upload-a-self-signed-certificate) を参照してください
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

#### 自己署名証明書のアップロード

自己署名証明書を追加するには：

1. **抽出** をクリックします。
1. 抽出するファイルのタイプを選択します。
1. または証明書を含むファイルを選択します。
1. ファイルのパスワードを入力します。
1. 「**保存**」をクリックしてファイルを抽出し、モジュール設定に戻ります。

## [!UICONTROL Email] モジュールとそのフィールド

[!UICONTROL Email] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加のフィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

シナリオの別のモジュールで一部のメールフィールドを使用した場合、それらのメールフィールドには既にデータが含まれている場合があります。詳しくは、メールのヘルプドキュメントを参照してください。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>一意の電子メール ID （&#39;[!UICONTROL Email ID (UID)]&#39;と呼ばれます）は、電子メールの識別子です。 メール ID は、メールの各フォルダーに固有です。

* [トリガー](#triggers)
* [アクション](#actions)
* [イテレータ](#iterators)

### トリガー

#### [!UICONTROL Watch Emails]

このトリガーモジュールは、指定された条件に従って処理する新しいメールを受信したときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] </td> 
   <td> <p>監視するメールを含むフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Criteria]</p> </td> 
   <td> <p>メールを監視する条件を選択します。</p> 
    <ul> 
     <li>[!UICONTROL All Emails]</li> 
     <li>[!UICONTROL Only Read Emails]</li> 
     <li>[!UICONTROL Only Unread Emails]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sender Email Address] </td> 
   <td> <p>監視するメールの送信者のメールアドレスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>監視するメールの件名を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>キーワードを含むメールのみを監視するには、キーワードを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched]</td> 
   <td> <p>詳細を取得した後、未読のメールを既読としてマークするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> 1 つのシナリオの実行サイクルで返され [!DNL Workfront Fusion] メールの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Copy an Email]](#copy-an-email)
* [[!UICONTROL Create a Draft]](#create-a-draft)
* [[!UICONTROL Delete an Email]](#delete-an-email)
* [[!UICONTROL Get Emails]](#get-emails)
* [[!UICONTROL Mark an Email as Read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an Email as Unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an Email]](#move-an-email)
* [[!UICONTROL Send an Email]](#send-an-email)

#### [!UICONTROL Copy an Email]

このアクションモジュールは、選択したフォルダーにメールまたはドラフトをコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>メールのコピー元のフォルダーを選択します。（例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> メールのコピー先のフォルダーを選択します。（例： ワーク）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>宛先フォルダーにコピーするメールのメール UID を入力します。</p> <p>[!UICONTROL Email]/[!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Draft]

このアクションモジュールは、新しいドラフトを作成し、選択したフォルダーに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>ドラフトメールを作成するフォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL To] </td> 
   <td> <p>メールの送信先となるメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>メールの件名行を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>HTMLタグを使用してHTMLフォーマットで、またはプレーンテキストでメールコンテンツを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>追加する添付ファイルごとに、「<b> 項目を追加 </b> をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>拡張子を含むファイル名を入力します。 </p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>添付ファイルをアップロードするフォルダーのパスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>コンテンツ ID を入力して、添付ファイル（画像）をコンテンツに挿入します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>この電子メールのコピーを送信する電子メールアドレスごとに、<b> 項目を追加 </b> をクリックして、電子メールアドレスを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> メールアドレスを入力せずに、このメールアドレスのコピーを送信するメールアドレスごとに、「<b> 項目を追加 </b>」をクリックしてメールアドレスを入力します。</p> </td> 
  </tr> 
  <!--<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Enter or map the email address (and name, if needed) that appears in the [!UICONTROL From] field in the email. </p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code>.</p> <p>Note:  Normally, [!DNL Workfront Fusion] uses the email address that you entered when creating the connection as the sender address. If you enter any other email address, an error may occur when sending a message because your account may not have permission to send emails from a different address than your own. E.g. <code>test@mail.com</code> or "<code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Enter or map the email address that appears in the [!UICONTROL Sender] field in the email.</p> <p>Tip:  If you are unsure whether to use this field or the From field, we recommend choosing the From field.</p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> If you want replies to this email sent to a different address than the "[!UICONTROL from]" address, enter the email address where you want replies to this email sent.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> If you are replying to a specific email, enter or map the ID of the email you are replying to.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Enter the message IDs of all the replies in the thread.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Select the priority of the email:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Add the headers:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Add the key. For example, Sender, Date, To, and so on.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Enter the value for the key.</p> </li> 
    </ul> </td> 
  </tr> -->
 </tbody> 
</table>

#### [!UICONTROL Delete an Email]

このアクションモジュールは、選択したフォルダーからメールまたはドラフトを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>削除するメールを含むフォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>削除するメールのメール UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL Search Email] モジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>現在開いているメールボックスで [!UICONTROL Deleted] のフラグが設定されたすべてのメッセージを完全に削除するには、このオプションを有効にします。</p> <p>メモ：[!DNL Gmail] では、この動作は [!UICONTROL Settings] &gt;[!UICONTROL Forwarding POP/IMAP in IMAP access] セクションの設定によって駆動されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Emails]

このモジュールは、指定された条件に一致するメールを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] </td> 
   <td> <p>取得するメールを含むフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched] </td> 
   <td> <p>詳細を取得した後、未読のメールを既読としてマークするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Criteria]</p> </td> 
   <td> <p>メールを取得する条件を選択します。</p> 
    <ul> 
     <li>[!UICONTROL All Emails]</li> 
     <li>[!UICONTROL Only Read Emails]</li> 
     <li>[!UICONTROL Only Unread Emails]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sender Email Address] </td> 
   <td> <p>メールを取得する送信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Recipient Email]</td> 
   <td> <p> メールを取得する受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From date] </td> 
   <td> <p>指定した日付以降に処理されるメールを取得する日付を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Before date]</td> 
   <td> <p> 指定した日付以前に処理されたメールを取得する日付を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>取得するメールの件名を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>キーワードを入力またはマッピングすると、そのキーワードを含むメールのみを取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email ID (UID)]</td> 
   <td> <p> 詳細を取得するメールのメール ID（UID）を入力します。</p> <p>[!DNL Workfront Fusion] の [!UICONTROL  Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> 1 回のシナリオ実行サイクルで [!DNL Workfront Fusion] が返す必要のある最大メール数。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> 結果が返されない場合でもモジュールの実行を続行する場合は、選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Read]

このアクションモジュールは、[!UICONTROL Read] フラグを設定することにより、選択されたフォルダー内のメールまたはドラフトに既読のマークを付けます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>既読としてマークするメールを含むフォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>既読としてマークするメールの UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL Search Email] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Unread]

選択したフォルダー内のメールまたは下書きを未読としてマークするには、「未読」フラグを設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>未読としてマークするメールを含んだフォルダーを選択します。 （例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>未読としてマークするメールの UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL Search Email] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an Email]

選択したメールまたは下書きを選択したフォルダーに移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>移動するメールが含まれているフォルダーを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> メールを追加するフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>宛先フォルダーに移動するメールの UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL Search Email] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send an Email]

新しいメールを送信します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion]</a> へのメールの接続」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save Message after Sending]</td> 
   <td>メールメッセージが送信されると、メールボックスに保存されます。[!DNL Workfront Fusion] を使用して送信された電子メールをメールボックスの <i>[!UICONTROL Sent mail]</i> フォルダーまたは別のフォルダーに保存する場合は、このオプションを有効にします。 一部のメールサービス（[!DNL Gmail] など）では、送信したメッセージが自動的に保存されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL To] </td> 
   <td> <p>メールの送信先のメールアドレスを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>メールの件名行を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Content Type]</p> </td> 
   <td> <p>メールの [!UICONTROL content] のタイプを選択します。</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plaintext]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>「[!UICONTROL Content Type]」フィールドで選択した内容に応じて、HTMLタグを使用してHTMLフォーマットで、またはプレーンテキストでメールコンテンツを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>追加する添付ファイルごとに、「<b> 項目を追加 </b> をクリックして、次の情報を入力します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>拡張子を含むファイル名を入力します。 </p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>添付ファイルをアップロードするフォルダーのパスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>コンテンツ ID を入力して、添付ファイル（画像）をコンテンツに挿入します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>この電子メールのコピーを送信する電子メールアドレスごとに、<b> 項目を追加 </b> をクリックして、電子メールアドレスを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> メールアドレスを入力せずに、このメールアドレスのコピーを送信するメールアドレスごとに、「<b> 項目を追加 </b>」をクリックしてメールアドレスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>メールの [!UICONTROL Sender] フィールドに表示されるメールアドレスを入力またはマッピングします。</p> <p>ヒント：このフィールドと「送信者」フィールドのどちらを使用するかが不明な場合は、「送信者」フィールドを選択することをお勧めします。</p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> このメールに対する返信を「送信者」アドレスとは別のアドレスに送信する場合は、このメールに対する返信先のメールアドレスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> 特定のメールに返信する場合は、返信先のメールの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>スレッド内のすべての返信のメッセージ ID を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>メールの優先度を選択します。</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>ヘッダーを追加します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>キーを追加します。例えば、[!UICONTROL Sender]、[!UICONTROL Date]、[!UICONTROL To] など。</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>キーの値を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>メールの [!UICONTROL From] フィールドに表示されるメールアドレス（必要に応じて名前も）を入力またはマッピングします。 </p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code>）。</p> <p>メモ：通常は、[!DNL Workfront Fusion] は、接続を作成する際に入力したメールアドレスを送信者のアドレスとして使用します。他のメールアドレスを入力すると、メッセージの送信時にエラーが発生する場合があります。これは、お使いのアカウントに、自身のアドレスとは異なるアドレスからメールを送信する権限がない可能性があるためです。（例：<code>test@mail.com</code> または "<code>John Bush" test@email.com</code>）。</p> </td> 
  </tr> 
 </tbody> 
</table>

### イテレータ

#### [!UICONTROL Iterate Attachments]

受け取った添付ファイルを 1 つずつ繰り返します。

メールイテレーターモジュールを使用すると、メールの添付ファイルを個別に管理できます。例えば、メールを監視して添付ファイル付きのメールを繰り返し処理し、アラートを受け取るように設定できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module]</td> 
   <td> <p>繰り返し処理を行う添付ファイルが含まれるメールを出力するモジュールを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

イテレータについて詳しくは、[ イテレータモジュール ](/help/workfront-fusion/references/modules/iterator-module.md) を参照してください。
