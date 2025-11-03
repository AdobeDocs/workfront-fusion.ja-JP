---
title: メールモジュール
description: Adobe Workfront Fusion では、複数のサードパーティのアプリケーションやサービスにメールアカウントを接続できます。これにより、IMAP 経由でのメールのダウンロード、SMTP 経由でのメールの送信、新しいドラフトの作成、あるフォルダーから別のフォルダーへのメールの移動とコピー、メールの既読または未読のマーク、メールの削除を行うことができます。
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2491'
ht-degree: 60%

---

# メールモジュール

Adobe Workfront Fusion では、複数のサードパーティのアプリケーションやサービスにメールアカウントを接続できます。これにより、IMAP 経由でのメールのダウンロード、SMTP 経由でのメールの送信、新しいドラフトの作成、あるフォルダーから別のフォルダーへのメールの移動とコピー、メールの既読または未読のマーク、メールの削除を行うことができます。

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

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Workfront Fusion にメールを接続 {#connect-your-email-to-workfront-fusion}

* [Google に接続](#connect-to-google)
* [他のメールサービス （IMAP）への接続](#connect-to-other-email-services-smap)

### [!DNL Google] に接続

[!DNL Google] アカウントへの接続を必要とするメールモジュールを含むシナリオを作成するには、このオプションを使用します。これは、スコープが制限されたアカウントです。

[!DNL Google] アカウントへの接続を、メールモジュール内から直接作成できます。

1. 任意のメールモジュールで、[!UICONTROL 接続]フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 接続タイプとして「**[!DNL Google]**」を選択します。
1. 接続に名前を入力します。
1. （オプション）[!UICONTROL [!DNL Google] クライアント ID] および[!UICONTROL クライアントシークレット]を入力します。
1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

### 他のメールサービス （IMAP）への接続

IMAP 接続を使用すると、メールボックスにリモートからアクセスしたり、メールボックス内のメッセージを読み取ったり、操作したりできます。 IMAP 接続は、ほとんどのメールモジュールで使用されます。

1. 任意のメールモジュールで、[!UICONTROL 接続]フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 接続タイプとして「**[!UICONTROL その他（SMTP）]**」を選択します。
1. 接続の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。
1. リストから&#x200B;**[!UICONTROL メールプロバイダー]**&#x200B;を選択します。メールプロバイダーがリストにない場合は、「その他」を選択します。
1. メールアカウントの **[!UICONTROL ユーザー名]** と **[!UICONTROL パスワード]** を入力します。
1. （条件付き）プロバイダーがリストにない場合は、「**[!UICONTROL SMTP サーバー]**」および「**[!UICONTROL ポート]**」を入力し、**[!UICONTROL セキュア接続（TLS）を使用]**&#x200B;するかどうかを指定します。この情報を見つけるには、メールボックスの「[!UICONTROL ヘルプ]」セクションを確認してください。この情報が不明な場合は、メールサービスプロバイダーにお問い合わせください。
1. 自己署名証明書を使用するには、「**未認証の証明書を拒否**」オプションを有効にし、自己署名証明書をアップロードします。 手順については、[ 自己署名証明書のアップロード ](#upload-a-self-signed-certificate) を参照してください
1. 「**[!UICONTROL 続行]**」をクリックし、接続を作成して、モジュールに戻ります。

#### 自己署名証明書のアップロード

自己署名証明書を追加するには：

1. **抽出** をクリックします。
1. 抽出するファイルのタイプを選択します。
1. または証明書を含むファイルを選択します。
1. ファイルのパスワードを入力します。
1. 「**保存**」をクリックしてファイルを抽出し、モジュール設定に戻ります。

## [!UICONTROL メール]モジュールとそのフィールド

[!UICONTROL  メール ] モジュールを設定すると、Workfront Fusion は以下に示すフィールドを表示します。 これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加のフィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

シナリオの別のモジュールで一部のメールフィールドを使用した場合、それらのメールフィールドには既にデータが含まれている場合があります。詳しくは、メールのヘルプドキュメントを参照してください。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>[!UICONTROL メール ID（UID）]と呼ばれる一意のメール ID は、メールの識別子です。メール ID は、メールの各フォルダーに固有です。

* [トリガー](#triggers)
* [アクション](#actions)
* [イテレータ](#iterators)

### トリガー

#### [!UICONTROL メールを監視]

このトリガーモジュールは、指定された条件に従って処理する新しいメールを受信したときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td> 
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
   <td> <p> 1 つのシナリオの実行サイクルでWorkfront Fusion が返す最大メール数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL メールのコピー]](#copy-an-email)
* [[!UICONTROL 下書きの作成]](#create-a-draft)
* [[!UICONTROL メールの削除]](#delete-an-email)
* [[!UICONTROL メールの取得]](#get-emails)
* [[!UICONTROL メールを既読としてマーク]](#mark-an-email-as-read)
* [[!UICONTROL メールを未読としてマーク]](#mark-an-email-as-unread)
* [[!UICONTROL メールの移動]](#move-an-email)
* [[!UICONTROL メールの送信]](#send-an-email)

#### [!UICONTROL メールのコピー]

このアクションモジュールは、選択したフォルダーにメールまたはドラフトをコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
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
   <td> <p>宛先フォルダーにコピーするメールのメール UID を入力します。</p> <p>[!UICONTROL Email] &gt; [!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用すると、メールのUIDを取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 下書きの作成]

このアクションモジュールは、新しいドラフトを作成し、選択したフォルダーに追加します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
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
   <td> <p>HTML タグを使用してHTML フォーマットで、またはプレーンテキストでメールコンテンツを入力するか、マッピングします。</p> </td> 
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
   <td> <p>Enter or map the email address (and name, if needed) that appears in the [!UICONTROL From] field in the email. </p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code>.</p> <p>Note:  Normally, Workfront Fusion uses the email address that you entered when creating the connection as the sender address. If you enter any other email address, an error may occur when sending a message because your account may not have permission to send emails from a different address than your own. E.g. <code>test@mail.com</code> or "<code>John Bush" test@email.com</code>.</p> </td> 
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

#### [!UICONTROL メールの削除]

このアクションモジュールは、選択したフォルダーからメールまたはドラフトを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>削除するメールを含むフォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>削除するメールのメール UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL メールを検索 ] モジュールを使用して取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>現在開いているメールボックスで [!UICONTROL Deleted] のフラグが設定されているすべてのメッセージを完全に削除するには、このオプションを有効にします。</p> <p>メモ：[!DNL Gmail] では、この動作は [!UICONTROL 設定 ] &gt;[!UICONTROL IMAP アクセスでの POP/IMAP 転送 ] セクションの設定によって駆動されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メールの取得]

このモジュールは、指定された条件に一致するメールを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
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
   <td role="rowheader">[!UICONTROL 受信者の電子メール ]</td> 
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
   <td> <p> 詳細を取得するメールのメール ID（UID）を入力します。</p> <p>Workfront Fusion の [!UICONTROL Watch Email] モジュールまたは [!UICONTROL Search Email] モジュールを使用して、メールのUIDを取得できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Workfront Fusion が 1 つのシナリオ実行サイクルで返す最大メール数。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> 結果が返されない場合でもモジュールの実行を続行する場合は、選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メールを既読としてマーク]

このアクションモジュールは、[!UICONTROL  読み取り ] フラグを設定して、選択されたフォルダー内のメールまたはドラフトを読み取りとしてマークします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>既読としてマークするメールを含むフォルダーを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>既読としてマークするメールの UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL メールを検索 ] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メールを未読としてマーク]

選択したフォルダー内のメールまたは下書きを未読としてマークするには、「未読」フラグを設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>未読としてマークするメールを含んだフォルダーを選択します。 （例：プライマリ）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>未読としてマークするメールの UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL メールを検索 ] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メールの移動]

選択したメールまたは下書きを選択したフォルダーに移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントを [!UICONTROL Workfront Fusion] に接続する方法について詳しくは、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">[!UICONTROL Workfront Fusion] へのメールの接続</a>を参照してください。</p> </td>
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
   <td> <p>宛先フォルダーに移動するメールの UID を入力します。</p> <p>メールのUIDは、メール / メールを監視モジュールまたは [!UICONTROL メールを検索 ] モジュールを使用して取得できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL メールの送信]

新しいメールを送信します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>メールアカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref"> メールを [!UICONTROL Workfront Fusion] に接続する </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save Message after Sending]</td> 
   <td>メールメッセージが送信されると、メールボックスに保存されます。Workfront Fusion を使用して送信されたメールを <i>[!UICONTROL 送信済みメール ]</i> フォルダーまたはメールボックス内の別のフォルダーに保存する場合は、このオプションを有効にします。 一部のメールサービス（[!DNL Gmail] など）では、送信したメッセージが自動的に保存されます。</td> 
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
   <td> <p>メールの [!UICONTROL content] タイプを選択します。</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plaintext]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>「[!UICONTROL Content Type]」フィールドで選択した内容に応じて、HTML タグを使用してHTML 形式で、またはプレーンテキストでメールコンテンツを入力またはマッピングします。</p> </td> 
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
   <td> <p>メールの「[!UICONTROL Sender]」フィールドに表示されるメールアドレスを入力またはマッピングします。</p> <p>ヒント：このフィールドと「送信者」フィールドのどちらを使用するかが不明な場合は、「送信者」フィールドを選択することをお勧めします。</p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code></p> </td> 
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
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>キーを追加します。例えば、[!UICONTROL Sender]、[!UICONTROL Date]、[!UICONTROL To] などです。</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>キーの値を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>メールの「[!UICONTROL From]」フィールドに表示されるメールアドレス（および必要に応じて名前）を入力またはマッピングします。 </p> <p>重要：正しい構文を使用してください（<code>name@email.com</code> または <code>"Name" name@email.com</code>）。</p> <p>注意：通常、Workfront Fusion では接続時に入力したメールアドレスを送信者のアドレスとして使用します。 他のメールアドレスを入力すると、メッセージの送信時にエラーが発生する場合があります。これは、お使いのアカウントに、自身のアドレスとは異なるアドレスからメールを送信する権限がない可能性があるためです。（例：<code>test@mail.com</code> または "<code>John Bush" test@email.com</code>）。</p> </td> 
  </tr> 
 </tbody> 
</table>

### イテレータ

#### [!UICONTROL 添付ファイルの反復]

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
