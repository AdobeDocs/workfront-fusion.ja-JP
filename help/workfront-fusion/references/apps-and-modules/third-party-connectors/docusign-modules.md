---
title: DocuSign モジュール
description: ' [!DNL Adobe Workfront Fusion DocuSign] モジュールを使用すると、エンベロープのステータスを監視および取得したり、エンベロープを検索および取得したり、ドキュメントをダウンロードして送信し、 [!DNL DocuSign] アカウントにログインしたりできます。'
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2250'
ht-degree: 64%

---

# DocuSign モジュール

Adobe Workfront Fusion [!DNL DocuSign] モジュールを使用すると、封筒のステータスのモニタリングと取得、封筒の検索と取得、[!DNL DocuSign] アカウントにログインするための文書のダウンロードと送信を行うことができます。

シナリオの作成方法については、[&#x200B; シナリオの作成：記事のインデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[&#x200B; モジュール：記事インデックス &#x200B;](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

[!DNL DocuSign] モジュールを使用するには、[!DNL DocuSign] アカウントが必要です。

## DocuSign API 情報

DocuSign コネクタは以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>1.18.11</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL DocuSign] を Workfront Fusion に接続 {#connect-docusign-to-workfront-fusion}

[!DNL DocuSign] モジュールへの接続を作成するには、以下を実行します。

1. 最初の [!DNL DocuSign] モジュールの設定を開始するときは、「[!UICONTROL 接続]」ボックスの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 以下の情報を入力します。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>新しい [!DNL DocuSign] 接続の名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td>実稼動以外の環境の実稼動環境に接続するかどうかを選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>接続するアカウントが実稼動アカウントかデモアカウントかを選択します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL DocuSign] モジュールとそのフィールド

[!DNL DocuSign] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL DocuSign]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[&#x200B; モジュール間で情報をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![&#x200B; マップ切り替え &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)

### トリガー

#### [!UICONTROL エンベロープの監視]

このトリガーモジュールは、エンベロープが送信、配信、署名、完了または拒否されたときにシナリオを開始します。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への Docusign の接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>監視するレコードを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p> 監視するイベントのタイプを選択します。</p> 
    <ul> 
     <li>[!UICONTROL Document completed]</li> 
     <li>[!UICONTROL Document declined]</li> 
     <li>[!UICONTROL Document sent]</li> 
     <li>[!UICONTROL Document signed]</li> 
     <li>[!UICONTROL New document in Inbox]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Outputs]</p> </td> 
   <td> <p>モジュールの出力に含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが操作するレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL &#x200B; カスタムフィールドの追加 &#x200B;]](#add-a-custom-field)
* [[!UICONTROL エンベロープへの受信者の追加]](#add-recipient-to-envelope)
* [[!UICONTROL エンベロープの新規作成]](#create-a-new-envelope)
* [[!UICONTROL カスタム API 呼び出し]](#custom-api-call)
* [[!UICONTROL ドキュメントのダウンロード]](#download-a-document)
* [[!UICONTROL カスタムフィールドの変更]](#modify-custom-field)
* [[!UICONTROL エンベロープを読む]](#read-an-envelope)
* [[!UICONTROL エンベロープの送信]](#send-envelope)
* [[!UICONTROL エンベロープにファイルをアップロード]](#upload-a-file-to-an-envelope)

#### [!UICONTROL &#x200B; カスタムフィールドの追加 &#x200B;]

このアクションモジュールは、カスタムフィールドをドキュメントに追加します

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>カスタムフィールドを追加するドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> カスタムフィールドを追加するドキュメントが含まれるエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>追加する新しいフィールドの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>追加したフィールドを必須フィールドにする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>フィールドを表示する場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>追加したフィールドの値（コンテンツ）を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL エンベロープへの受信者の追加]

このアクションモジュールは、1 人以上の受信者を既存のエンベロープに追加します。エンベロープが既に送信されている場合は、受信者にメールが送信されます。このモジュールは、既に完了しているエンベロープに対しては無効です。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>DocuSign アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Account] </td>
   <td> <p>受信者を追加するエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Envelope ID]</td>
    <td>受信者を追加するエンベロープの ID を選択またはマッピングします。</td>
  </tr> 
  <tr data-mc-conditions="">
    <td role="rowheader">[!UICONTROL Recipient type]</td>
   <td> <p> エンベロープに追加する受信者のタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Agent]</p> </li> 
     <li> <p>[!UICONTROL Carbon copy]</p> </li> 
     <li> <p>[!UICONTROL Certified delivery]</p> </li> 
     <li> <p>[!UICONTROL In-person signer]</p> </li> 
     <li> <p>[!UICONTROL Intermediary]</p> </li> 
     <li> <p>[!UICONTROL Signer]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Email]</td>
   <td> <p>エンベロープに追加する受信者のメールアドレスを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Name]</td>
   <td>エンベロープに追加する受信者の名前を入力またはマッピングします。</td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Routing order]</td>
   <td> <p>受信者のルーティング番号を入力またはマッピングします。ルーティング番号は、受信者がドキュメントを受け取り署名する順序を指定するものです。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Email body]</td>
   <td>受信者に送信するメールの本文（コンテンツ）を入力またはマッピングします。</td> 
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Email subject]</td>
   <td>受信者に送信するメールの件名を入力またはマッピングします。</td> 
  </tr> 
    <td role="rowheader">[!UICONTROL Private message]</td>
   <td> プライベートメッセージを受信者に送信する場合は、メッセージのテキストを入力またはマッピングします。 <p>選択した受信者にのみ、一般メッセージと共にプライベートメッセージも表示されます。プライベートメッセージの長さは 1000 文字までです。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Authentication]</td> 
   <td> <p>受信者の ID の確認に使用する認証メソッドを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL None]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Access code]</strong> </p> <p>アクセスコードを入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Phone]</strong> </p> <p>電話番号を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL SMS]</strong> </p> <p>電話番号を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 新規エンベロープの作成]

このアクションモジュールは、テンプレートから新規エンベロープを作成します。新規エンベロープの ID と、新規エンベロープのステータスを返します。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td>

<td> <p>DocuSign アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> 接続の作成 – 基本的な手順 </a> の記事を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Account] </td>
   <td> <p>ファイルをアップロードするエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template]</td>
   <td> <p> 新規エンベロープを作成するテンプレートを選択します。テンプレートは、選択した [!UICONTROL Account] に基づいて使用できます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL After creation]
   </td> 
   <td> <p>エンベロープをドラフトとして保存するか、署名用に送信するかを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template recipients]</td>
    <td>この封筒に追加する各受信者に対して、[<b> アイテムの追加 </b>] をクリックし、次の詳細を入力します。
    <ul>
    <li><b>アクセスコード</b><p>受信者が封筒にアクセスするために使用するコードを入力またはマップします。<p></li>
    <li><b>メール</b><p>受信者のメールアドレスを入力またはマッピングします。<p></li>
    <li><b>名前</b><p>受信者の名前を入力またはマッピングします。<p></li>
    <li><b>役割名</b><p>受信者の役割名を入力またはマッピングします。<p></li>
    <li><b>ルーティング順序</b><p>受信者のルーティング番号を入力またはマッピングします。ルーティング番号は、受信者がドキュメントを受け取り署名する順序を指定するものです。<p></li>
    </ul>
    </td>
    </tr>
  <tr> 
   <td role="rowheader">
     [!UICONTROL で印刷と署名を許可する &#x200B;]
   </td> 
   <td> <p>受信者がドキュメントを印刷し、紙に署名できるようにするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL の再割り当て許可 &#x200B;]
   </td> 
   <td> <p>受信者がドキュメントを別のユーザーに再割り当てできるようにする場合は、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL 受信者再帰を許可 &#x200B;]
   </td> 
   <td> <p>受信者の再帰を許可するには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL 権限のあるコピー &#x200B;]
   </td> 
   <td> <p>このオプションを有効にすると、この封筒の文書が信頼できるコピーとしてマークされます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL 自動ナビゲーション &#x200B;]
   </td> 
   <td> <p>受信者の自動ナビゲーションを設定するには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL ブランド ID]
   </td> 
   <td> <p>ブランドの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL マークアップ有効 &#x200B;]
   </td> 
   <td> <p>ドキュメントのマークアップを有効にするには、このオプションを有効にします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL 有効期限切れ &#x200B;]
   </td> 
   <td> <p>このオプションを有効にすると、このエンベロープの有効期限が設定されます。 このオプションを有効にする場合、次のフィールドに入力します。<ul><li><b>有効期限</b><p>この封筒が期限切れになるまでの日数を入力またはマップします。</p></li><li><b>期限切れ警告</b><p>リマインダーメールが受信者に送信される、有効期限までの日数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Body]
   </td> 
   <td> <p>このエンベロープに付随する電子メールの本文（コンテンツ）を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Subject]
   </td> 
   <td> <p>この封筒に付随する電子メールの件名を入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カスタム API 呼び出し]

このアクションモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Account]</td> 
   <td>[!DNL DocuSign] API アクセスに使用するアカウントを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>次に対してパスを入力またはマッピングします： <code>https://&lt;BASE_URI>/v2/accounts/&lt;ACCOUNT_ID>.</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> {"Content-type":"application/json"}</code></p> <p>メモ：エラーが発生し、接触チャネルを特定するのが難しい場合は、Workfrontのドキュメントに基づいてヘッダーを変更することを検討してください。 カスタム API 呼び出しで 422 HTTP リクエストエラーが返される場合は、"Content-Type":"text/plain"ヘッダーを使用してみてください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>1 回の実行サイクルで処理する結果の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**例**：エンベロープのリスト

次の API 呼び出しは、[!DNL DocuSign] アカウントの指定された日付からのエンベロープを返します。

**URL**：`/v2.1/accounts/{accountId}/envelopes/`

**メソッド**：`GET`

**クエリ文字列**：

* **キー**：`from_date`

* **値**：`YYYY-MM-DD`

リクエストがアカウント内のエンベロープのステータス変更のチェックを開始する時期を指定します。

![Docusign 設定の例 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)

結果は、モジュールの出力（バンドル／本文／エンベロープの下）にあります。

この例では、6 個のエンベロープが返されました。

![docusign 出力の例 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

>[!ENDSHADEBOX]

#### [!UICONTROL ドキュメントのダウンロード]

このアクションモジュールは、1 つのドキュメントをダウンロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>ダウンロードするドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> ダウンロードするエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Document ID]</p> </td> 
   <td> <p>ダウンロードするドキュメントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Certificate]</td> 
   <td>このオプションを有効にすると、ダウンロードにエンベロープ署名証明書が含まれます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents by User ID]</td> 
   <td>受信者がユーザー ID でドキュメントを取得できるようにするには、このオプションを有効にします。 例えば、ユーザーが異なる表示の 2 つの異なるルーティングオーダーに含まれている場合、このオプションを使用すると、両方のルーティングのすべてのドキュメントが戻されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encrypt]</td> 
   <td>[!DNL DocuSign] アカウントで設定されているすべてのキーマネージャーに対して、レスポンスで返されるPDF バイトを暗号化する場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>言語を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Changes]</td> 
   <td>このオプションを有効にすると、返されるPDFの変更されたフィールドが黄色でハイライト表示され、オプションの署名やイニシャルのアウトラインが赤でハイライト表示されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watermark]</td> 
   <td> <p>透かし機能を有効にするには、このオプションを有効にします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カスタムフィールドの変更]

このアクションモジュールは、フィールド名を使用してカスタムフィールドを変更します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>カスタムフィールドを変更するドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> カスタムフィールドを変更するドキュメントが含まれるエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field ID]</td> 
   <td>変更するフィールドの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>変更するフィールドの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>変更したフィールドを必須フィールドにする場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>フィールドを表示する場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>変更したフィールドの値（コンテンツ）を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL エンベロープの読み取り]

このアクションモジュールは、エンベロープ ID を使用して、[!DNL DocuSign] にあるエンベロープに関する情報を読み取ります。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>情報を読み取るドキュメントを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 情報を読み取るドキュメントを含む封筒の ID を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に表示するプロパティを選択します。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL エンベロープの送信]

このアクションモジュールは、受信者に下書きエンベロープを送信します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>受信者に送信する下書きエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 受信者に送信する下書きエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL エンベロープへのファイルのアップロード]

このモジュールは、指定されたファイルを DocuSign の既存のエンベロープにアップロードします。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL DocuSign] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL DocuSign] の接続 </a> を参照してください。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>ファイルをアップロードするエンベロープを含むアカウントを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> ファイルをアップロードするエンベロープの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>前のモジュールからソースファイルを選択するか、ソースファイルの名前とデータを入力します。</td> 
  </tr> 
 </tbody> 
</table>
