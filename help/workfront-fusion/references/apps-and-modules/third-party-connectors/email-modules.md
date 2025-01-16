---
title: メールモジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、メールアカウントを複数のサードパーティアプリケーションやサービスに接続できます。これにより、IMAP 経由でメールをダウンロードしたり、SMTP 経由でメールを送信したり、新しい下書きを作成したり、フォルダー間でメールを移動およびコピーしたり、メールを既読または未読としてマークしたり、メールを削除したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2103'
ht-degree: 70%

---

# メールモジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、メールアカウントを複数のサードパーティアプリケーションやサービスに接続できます。これにより、IMAP 経由でメールをダウンロードしたり、SMTP 経由でメールを送信したり、新しい下書きを作成したり、フォルダー間でメールを移動およびコピーしたり、メールを既読または未読としてマークしたり、メールを削除したりすることができます。

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

[!DNL Adobe Workfront Fusion] のライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  のライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## Workfront Fusion にメールを接続 {#connect-your-email-to-workfront-fusion}

* [Google に接続](#connect-to-google)
* [他のメールサービス（SMAP）に接続](#connect-to-other-email-services-smap)

### [!DNL Google] に接続

[!DNL Google] アカウントへの接続を必要とするメールモジュールを含むシナリオを作成するには、このオプションを使用します。これは、スコープが制限されたアカウントです。

[!DNL Google] アカウントへの接続を、メールモジュール内から直接作成できます。

1. 任意の電子メールモジュールで、「[!UICONTROL Connection]」フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続タイプとして「**[!DNL Google]**」を選択します。
1. 接続に名前を入力します。
1. （任意） [!UICONTROL [!DNL Google] Client ID] と [!UICONTROL Client Secret] を入力します。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

### 他のメールサービス（SMAP）に接続

SMAP 接続を使用すると、メールボックスにリモートでアクセスし、メールボックス内のメッセージを読み取ったり操作したりできます。SMAP 接続は、ほとんどのメールモジュールで使用されます。

1. 任意の電子メールモジュールで、「[!UICONTROL Connection]」フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続タイプとして「**[!UICONTROL Others (SMTP)]**」を選択します。
1. 接続の **[!UICONTROL Name]** を入力します。
1. リストから **[!UICONTROL Email provider]** を選択します。 メールプロバイダーがリストにない場合は、「その他」を選択します。
1. **[!UICONTROL Email address]**、**[!UICONTROL Your full name]**、**[!UICONTROL User name]**、**[!UICONTROL Password]** を入力します。
1. （条件付き）プロバイダーがリストに含まれていない場合は、**[!UICONTROL SMTP server]** と **[!UICONTROL Port]** を入力し、**[!UICONTROL Use a secure connection (TLS)]** 用するかどうかを指定します。 この情報を見つけるには、メールボックスの [!UICONTROL Help] セクションを確認してください。 この情報が不明な場合は、メールサービスプロバイダーにお問い合わせください。
1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

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

指定された条件に従って処理するために、新しいメールを受け取ったときにトリガーされます。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Recipient Email Address]</td> 
   <td> <p> 監視するメールの受信者のメールアドレスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>監視するメールの件名を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>キーワードを入力して、特定のフレーズを含むメールのみを監視します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched]</td> 
   <td> <p>詳細を取得した後、未読のメールを既読としてマークするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> 1 回のシナリオ実行サイクルで [!DNL Workfront Fusion] が返す必要のある最大メール数。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Send an Email]](#send-an-email)
* [[!UICONTROL Create a Draft]](#create-a-draft)
* [[!UICONTROL Mark an Email as Read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an Email as Unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an Email]](#move-an-email)
* [[!UICONTROL Copy an Email]](#copy-an-email)
* [[!UICONTROL Delete an Email]](#delete-an-email)
* [[!UICONTROL Get Emails]](#get-emails)

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
   <td> <p>添付ファイルの追加：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>ファイル名を入力します。例えば、sample.doc のように指定します。</p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>添付ファイルをアップロードするフォルダーのパスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>添付ファイル（画像）をコンテンツに挿入する [!UICONTROL content ID] を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>このメールのコピーを送信する 1 つ以上のメールアドレスを入力またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> メールアドレスをメールに表示せずに、このメールのコピーを送信する 1 つ以上のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>メールの [!UICONTROL From] フィールドに表示されるメールアドレス（必要に応じて名前も）を入力またはマッピングします。 </p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code>）。</p> <p>メモ：通常は、[!DNL Workfront Fusion] は、接続を作成する際に入力したメールアドレスを送信者のアドレスとして使用します。他のメールアドレスを入力すると、メッセージの送信時にエラーが発生する場合があります。これは、お使いのアカウントに、自身のアドレスとは異なるアドレスからメールを送信する権限がない可能性があるためです。（例：<code>test@mail.com</code> または "<code>John Bush" test@email.com</code>）。</p> </td> 
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
 </tbody> 
</table>

#### [!UICONTROL Create a Draft]

選択したフォルダーに新しいドラフトを作成して追加します。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Content Type]</p> </td> 
   <td> <p>メールのコンテンツタイプを選択します。</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plain Text]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>「[!UICONTROL Content Type]」フィールドで選択した内容に応じて、HTMLタグを使用してHTMLフォーマットで、またはプレーンテキストでメールコンテンツを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>添付ファイルの追加：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>ファイル名を入力します。例えば、sample.doc のように指定します。</p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>添付ファイルをアップロードするフォルダーのパスを入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>コンテンツ ID を入力して、添付ファイル（画像）をコンテンツに挿入します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>このメールのコピーを送信する 1 つ以上のメールアドレスを入力またはマッピングします。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> メールアドレスをメールに表示せずに、このメールのコピーを送信する 1 つ以上のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>メールの [!UICONTROL From] フィールドに表示されるメールアドレス（必要に応じて名前も）を入力またはマッピングします。 </p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code>）。</p> <p>メモ：通常は、[!DNL Workfront Fusion] は、接続を作成する際に入力したメールアドレスを送信者のアドレスとして使用します。他のメールアドレスを入力すると、メッセージの送信時にエラーが発生する場合があります。これは、お使いのアカウントに、自身のアドレスとは異なるアドレスからメールを送信する権限がない可能性があるためです。（例：<code>test@mail.com</code> または "<code>John Bush" test@email.com</code>）。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>メールの [!UICONTROL Sender] フィールドに表示されるメールアドレスを入力またはマッピングします。</p> <p>ヒント：このフィールドと「送信者」フィールドのどちらを使用するかが不明な場合は、「送信者」フィールドを選択することをお勧めします。</p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> このメールへの返信を「[!UICONTROL from]」アドレスとは異なるアドレスに送信したい場合は、このメールへの返信を送信するメールアドレスを入力します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> 特定のメールに返信する場合は、返信先のメールの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>スレッド内のすべての返信のメッセージ ID を入力します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>メールの優先度を選択します。</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>ヘッダーを追加します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>キーを追加します。例えば、「送信者」、「日付」、「宛先」などです。</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>キーの値を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Read]

[!UICONTROL Read] フラグを設定して、選択したフォルダー内のメールまたはドラフトを既読としてマークします。

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
   <td>既読としてマークするメールのフォルダーを選択します。（例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>既読としてマークするメールの UID を入力します。</p> <p>[!UICONTROL Email]/[!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
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
   <td>未読としてマークするメールのフォルダーを選択します。（例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>未読としてマークするメールの UID を入力します。</p> <p>[!UICONTROL Email]/[!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
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
   <td>移動元のメールを含むフォルダーを選択します。（例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> メールを追加するフォルダーを選択します。（例： ワーク）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>宛先フォルダーに移動するメールの UID を入力します。</p> <p>[!UICONTROL Email]/[!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy an Email]

選択したフォルダーにメールまたは下書きをコピーします。

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

#### [!UICONTROL Delete an Email]

選択したフォルダーからメールまたはドラフトを削除します。

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
   <td>削除するメールのフォルダーを選択します。（例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>削除するメールのメール UID を入力します。</p> <p>[!UICONTROL Email]/[!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>現在開いているメールボックスで [!UICONTROL Deleted] としてフラグ付けされたすべてのメッセージをモジュールが完全に削除できるようにするには、このオプションを有効にします。</p> <p>メモ：[!DNL Gmail] では、この動作は [!UICONTROL Settings] &gt;[!UICONTROL Forwarding POP/IMAP in IMAP access] セクションの設定によって駆動されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Emails]

指定された条件に一致するメールを返します。

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
   <td role="rowheader">[!UICONTROL Recipient Email Address]</td> 
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
   <td> <p>キーワードを入力またはマッピングして、特定の語句を含むメールのみを取得します。</p> </td> 
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
