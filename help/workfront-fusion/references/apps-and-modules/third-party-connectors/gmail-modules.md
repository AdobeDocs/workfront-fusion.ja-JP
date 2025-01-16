---
title: Gmail モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Gmail を使用するワークフローを自動化でき、また、Gmail を複数のサードパーティのアプリケーションやサービスに接続できます。'
author: Becky
feature: Workfront Fusion
exl-id: 62269eca-c3cf-42fe-a866-fb66d2363b8d
source-git-commit: 0581601a254a9492f4166d78eb0f11868d390f24
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 82%

---

# [!DNL Gmail] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Gmail] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。 モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

[!DNL Gmail] モジュールを使用するには、[!DNL Gmail] アカウントが必要です。

## [!DNL Gmail] を [!DNL Workfront Fusion] に接続 {#connect-gmail-to-workfront-fusion}

* [接続  [!DNL Gmail]  使用  [!DNL Workfront Fusion]  接続  [!DNL Google Workspace]](#connect-gmail-to-workfront-fusion-usingg-suite)
* [ [!DNL gmail.com]  または  [!DNL googlemail].comを使用して  [!DNL Gmail]  を  [!DNL Workfront Fusion]  に接続](#connect-gmail-to-workfront-fusion-using-gmailcom-or-googlemailcom)

### [!DNL  Google Workspace] を使用して [!DNL Gmail] を [!DNL Workfront Fusion] に接続 {#connect-gmail-to-workfront-fusion-using-g-suite}

[!DNL Google Workspace] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、[ 接続の作成 – 基本的な手順 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) を参照してください。

### [!DNL gmail.com] または [!DNL googlemail].com を使用して [!DNL Gmail] を [!DNL Workfront Fusion] に接続 {#connect-gmail-to-workfront-fusion-using-gmail-com-or-googlemail-com}

[!DNL @gmail.com] ユーザーまたは [!DNL @googlemail.com] ユーザーの場合、[!UICONTROL Client ID] および [!UICONTROL Client Secret] を取得するために [the [!DNL Google Cloud Platform]](https://console.developers.google.com/projectselector2/apis/dashboard?supportedpurview=project) で OAuth クライアントを作成する必要があります。

OAuth クライアントを作成し、[!UICONTROL Client ID] と [!UICONTROL Client Secret] ールを取得する手順については、[ カスタム OAuth クライアントを使用したAdobe Workfront Fusion のGoogle サービスへの接続 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md) を参照してください。

## [!DNL Gmail] モジュールとそのフィールド

[!DNL Gmail] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Gmail] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [イテレータ](#iterators)

### トリガー

#### [!UICONTROL Watch emails]

このトリガーモジュールは、処理対象の新しいメールを受信した場合にシナリオを実行します。

このモジュールは、レコードに関連付けられたすべての標準フィールドと、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>監視するメールフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Filter type] </td> 
   <td> <p>メールの監視に使用するフィルタータイプを選択</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Simple filter]</strong> </p> <p>[!UICONTROL Criteria]、[!UICONTROL Sender Email Address]、[!UICONTROL Subject]、[!UICONTROL Search Phrase] の各フィールドに入力します</p> </li> 
     <li> <p> <strong>[!UICONTROL Gmail filter]</strong> </p> <p>[!UICONTROL Query] フィールドに、メールのフィルタリングに使用するクエリを入力します。</p> <p>[!DNL Gmail] フィルターについて詳しくは、<a href="https://support.google.com/mail/answer/7190">[!DNL Gmail] ドキュメントの検索演算子</a>を参照してください。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Criteria]</td> 
   <td>[!UICONTROL all email]、[!UICONTROL only read emails] または [!UICONTROL only unread] のメールを視聴するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sender email address]</td> 
   <td> <p> メールアドレスを入力して、そのアドレスから送信されたメールのみを監視します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject]</td> 
   <td>テキスト文字列を入力して、件名にそのテキスト文字列が含まれるメールのみを監視します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search phrase]</td> 
   <td>テキスト文字列を入力して、メールの任意の場所でそのテキスト文字列を持つメールのみを監視します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mark email message(s) as read when fetched]</td> 
   <td> <p> 取得したメールを既読としてマークするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of results]</td> 
   <td> <p> [!DNL Workfront Fusion] が 1 サイクルの間に連携する結果の最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL Send an email]](#send-an-email)
* [[!UICONTROL Create a draft]](#create-a-draft)
* [[!UICONTROL Mark an email as read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an email as unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an email]](#move-an-email)
* [[!UICONTROL Copy an email]](#copy-an-email)
* [[!UICONTROL Delete an email]](#delete-an-email)
* [[!UICONTROL Modify email labels]](#modify-email-labels)

#### [!UICONTROL Send an email]

このアクションモジュールは、新しいメールを送信します。

メールの受信者を指定します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!DNL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL From]</td> 
   <td> <p>送信者のメールアドレスを入力またはマッピングします。</p> <p>メモ：入力したメールアドレスが正しくない場合は、お使いのアカウントが、自分のアドレスとは異なるアドレスからメールを送信する権限を持っていない可能性があるので、メッセージの送信時にエラーが発生する場合があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To] </td> 
   <td> <p>「<strong>[!UICONTROL Add]</strong>」をクリックし、各受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject] </td> 
   <td> <p>メールの件名を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Content] </td> 
   <td> <p>メールコンテンツ（メッセージ本文）を入力またはマッピングします。HTML タグを使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attachments] </td> 
   <td> <p>「<strong>[!UICONTROL Add]</strong>」をクリックすると、添付ファイルを追加できます。 前のモジュールからファイルをマッピングできます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Copy recipients]</td> 
   <td> <p> 「<strong>[!UICONTROL Add]</strong>」をクリックし、コピー受信者ごとのメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Blind copy recipients]</td> 
   <td> <p> 「<strong>[!UICONTROL Add]</strong>」をクリックし、各ブラインドコピー受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a draft]

このアクションモジュールは、新しいメールの下書きを作成し、指定したフォルダーに追加します。

下書きを作成するフォルダーを指定します。

このモジュールは、メールの下書きの ID と関連するフィールドのほか、この接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>下書きを作成する [!DNL Gmail] フォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To] </td> 
   <td> <p>「<strong>[!UICONTROL Add]</strong>」をクリックし、各受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject] </td> 
   <td> <p>メールの件名を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Content] </td> 
   <td> <p>メールコンテンツ（メッセージ本文）を入力またはマッピングします。HTML タグを使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attachments] </td> 
   <td> <p>「<strong>[!UICONTROL Add]</strong>」をクリックすると、添付ファイルを追加できます。 前のモジュールからファイルをマッピングできます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Copy recipients]</td> 
   <td> <p> 「<strong>[!UICONTROL Add]</strong>」をクリックし、コピー受信者ごとのメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Blind copy recipients]</td> 
   <td> <p> 「<strong>[!UICONTROL Add]</strong>」をクリックし、各ブラインドコピー受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an email as read]

このアクションモジュールは、メールを既読としてマークします。

メールの ID とそのフォルダーを指定します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>メールを格納する [!DNL Gmail] フォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)]</td> 
   <td> <p> メール ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an email as unread]

このアクションモジュールは、メールまたはメールの下書きを未読としてマークします。

メールの ID とそのフォルダーを指定します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>メールを格納する [!DNL Gmail] フォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)] </td> 
   <td> <p>未読としてマークするメールのメール ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an email]

このアクションモジュールは、メールまたはメールの下書きを指定したフォルダーに移動します。

メールのフォルダー、宛先フォルダー、および ID を指定します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>移動するメールを格納する [!DNL Gmail] ソースフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination folder]</td> 
   <td> <p> メールの移動先となる [!DNL Gmail] ターゲットフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)]</td> 
   <td> <p> 移動するメールのメール ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy an email]

このアクションモジュールは、メールまたはメールのドラフトを指定したフォルダーにコピーします。

メールのフォルダー、宛先フォルダー、および ID を指定します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>コピーするメールを含む [!DNL Gmail] ソースフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination folder]</td> 
   <td> <p>ファイルのコピー先となる [!DNL Gmail] ターゲットフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)]</td> 
   <td> <p>コピーするメールのメール ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an email]

このアクションモジュールは、指定したフォルダーからメールまたはメールのドラフトを削除します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL [!DNL Gmail] メッセージ ID]</p> </td> 
   <td> <p>削除する電子メールのメール ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Permanently] </td> 
   <td> <p>モジュールがごみ箱フォルダーに移動するのではなく、メールを恒久的に削除できるようにするには、このオプションを有効にします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modify email labels]

このアクションモジュールは、指定したメールメッセージのラベルを変更します。

モジュールは、メールの ID と関連するフィールドのほか、接続がアクセスするカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>[!DNL Gmail] アカウントの [!DNL Workfront Fusion] への接続手順については、この記事内の<a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">[!DNL Gmail] の [!UICONTROL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL [!DNL Gmail] メッセージ ID]</td> 
   <td> <p> 削除する電子メールのメール ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Labels to add]</p> </td> 
   <td> <p>選択したメールメッセージに追加するラベルを選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Labels to remove]</td> 
   <td> <p> 選択したメールメッセージから削除するラベルを選択またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!UICONTROL Label to add] フィールドと [!UICONTROL Label to remove] フィールドには、ユーザーが作成したラベルのみが読み込まれます。

### イテレータ

#### [!UICONTROL Iterate attachments]

メールの添付ファイルを反復処理できます。各添付ファイルは、モジュールの出力内の個別のバンドルです。詳しくは、[ イテレータモジュール ](/help/workfront-fusion/references/modules/iterator-module.md) を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module] </td> 
   <td> <p>添付ファイルをイテレーションするモジュールを選択します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
