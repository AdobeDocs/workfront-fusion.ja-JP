---
title: Adobe Acrobat Sign モジュール
description: ' [!DNL Adobe Acrobat Sign]  モジュールを使用すると、 [!DNL Adobe] Acrobat Sign アカウント内のイベントに基づくAdobe Workfront Fusion シナリオの開始、契約書やその他のレコードの作成、読み取り、更新、設定した条件を使用したレコードの検索、ドキュメントのアップロードを行うことができます。'
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0ef9d40e-8ad6-434e-8fa0-076920ff29ea
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '6790'
ht-degree: 92%

---

# [!DNL Adobe Acrobat Sign] モジュール

[!DNL Adobe Acrobat Sign] モジュールを使用すると、[!DNL Adobe Acrobat Sign] アカウント内のイベントに基づくAdobe Workfront Fusion シナリオの開始、契約書やその他のレコードの作成、読み取り、更新、設定した条件を使用したレコードの検索、ドキュメントのアップロードを行うことができます。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront プラン*</td>
  <td> <p>[!UICONTROL Pro] 以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン*</td>
   <td> <p>[!UICONTROL Plan]、[!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：Workfront Fusion のライセンス要件はありません。</p>
   <p>または</p>
   <p>従来のライセンス要件：[!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td>  
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] Adobe Workfront プランがある場合、この記事に記載されている機能を使用するには、Adobe Workfront Fusion とAdobe Workfrontを購入する必要があります。 Workfront Fusion は、[!UICONTROL Ultimate] Workfront プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事に記載されている機能を使用するには、Adobe Workfront Fusion とAdobe Workfrontを購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、Workfront 管理者にお問い合わせください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

## [!DNL Adobe Acrobat Sign] API 情報

Adobe Acrobat Sign コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v6 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.35.1</td> 
  </tr>
 </tbody> 
</table>


## [!DNL Adobe Acrobat Sign] コネクタ使用の推奨事項

[!DNL Adobe Sign] アプリを使用すると、[!DNL Fusion] での電子サインビジネスプロセスを、はるかに簡単かつ強力に自動化できます。

[!DNL Adobe Sign] の新規ユーザーは、契約の更新に関する制約の一部に十分注意する必要があります。契約は、通常、開始後は変更されません。[!DNL Adobe Sign] の新規ユーザーには、契約作成モジュールを使用して新しい契約を作成することに重点を置くようお勧めします。これにより、[!DNL Fusion] の自動化が容易になり、[!DNL Adobe Sign] とより効率的に連携できるようになります。

[!DNL Adobe Sign] の契約では、フィールドを処理する必要があります。これを行うオプションはいくつかありますが、最も簡単で一般的な方法は、一時的なドキュメントをアップロードし、そのドキュメントを契約書にマッピングすることです。

![Adobe Sign の推奨事項 ](/help/workfront-fusion/references/apps-and-modules/assets/adobe-sign-recommendations-350x168.png)

## [!DNL Adobe Acrobat Sign] モジュールとそのフィールド

[!DNL Adobe Acrobat Sign] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Acrobat Sign]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

<!--
* [Watch for agreements](#watch-for-agreements) 
* [Watch for events](#watch-for-events)
-->

+++ **[!UICONTROL 契約を監視]**

このトリガーモジュールは、契約が作成または更新されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
<td>[!DNL Adobe Acrobat Sign] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</td>  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>新しいレコードや更新されたレコード、またはその両方のどれを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type] </td> 
   <td>監視するレコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Find text]</td> 
   <td> <p>検索する用語を入力します。このモジュールは、これらの用語をフィールド値として含むレコードを返します。</p> <p>[!DNL Adobe Acrobat Sign] でのフィールドの検索について詳しくは、<a href="https://helpx.adobe.com/jp/sign/using/adobesign-search-users-agreements.html#HowSearchWorks">Adobe Sign での「テキスト検索の仕組み」- 仕組み</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned agreements]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL イベントの監視]**

このトリガーモジュールは、選択したイベントが発生したときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td>使用する web フックを選択するか、「<b>[!UICONTROL Add]</b>」をクリックして次のフィールドに入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p>Web フックの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scopes]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Account]</p> </li> 
     <li> <p>[!UICONTROL Group]</p> </li> 
     <li> <p>[!UICONTROL User]</p> </li> 
     <li> <p>[!UICONTROL Resource]</p> <p>「[!UICONTROL Resource]」を選択した場合は、リソース ID とリソースタイプを入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource level]</td> 
   <td> <p>監視するリソースのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Agreements]</p> </li> 
     <li> <p>[!UICONTROL Widgets]</p> </li> 
     <li> <p>[!UICONTROL Megasigns]</p> </li> 
     <li> <p>[!UICONTROL Library Documents]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook subscription events]</td> 
   <td>モジュールで監視する [!DNL Adobe Sign] イベントを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application display name]</td> 
   <td>Web フックの作成に使用するアプリケーションの表示名。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application name]</td> 
   <td>Web フックの作成に使用するアプリケーションの表示名。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Problem notification emails]</td> 
   <td> <p>この設定は、管理者アカウントに対してのみ機能します。</p> <p>問題通知メールの送信先とするメールアドレスごとに、「<b>[!UICONTROL Add]</b>」をクリックしてメールアドレスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement conditional parameters]</td> 
   <td>条件付きパラメーターを追加する場合は、パラメーターを追加するレコードタイプで「<b>[!UICONTROL Yes]</b>」を選択し、有効にするパラメーターで「<b>[!UICONTROL Yes]</b>」をクリックします。</td> 
  </tr> 
 </tbody> 
</table>

+++

### アクション

<!--
* [Create a record](#create-a-record) 
* [Create an agreement](#create-an-agreement) 
* [Create related records](#create-related-records) 
* [Custom API Call](#custom-api-call) 
* [List records](#list-records) 
* [Read a record](#read-a-record) 
* [Read related records](#read-related-records) 
* [Update a record](#update-a-record) 
* [Update related record](#update-related-record) 
* [Upload document](#upload-document)
-->

+++ **[!UICONTROL レコードを作成]**

このアクションモジュールは、選択したタイプの新しいレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL Adobe Acrobat Sign] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例： <code>{"Content-type":"application/json"}</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>作成するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Group]</b> </p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> </li> 
     <li> <p><b>[!UICONTROL Web form]（[!UICONTROL Widget]）</b> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group info]</td> 
   <td> <p>グループの [!UICONTROL Name] と [!UICONTROL ID] を入力またはマッピングし、このグループがアカウントのデフォルトのグループであるかどうかを表示します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Library document info]</td> 
   <td> <p>次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Files to send]</b> </p> <p>追加するそれぞれのファイルに対して、「<b>[!UICONTROL Add item]</b>」をクリックし、フィールドに入力します。</p> 
      <ul> 
       <li><b>[!UICONTROL Transient document ID]</b> <p>一時的なドキュメントの ID の入力</p> </li> 
       <li> <p><b>[!UICONTROL URL file transfer]</b> </p> <p>次のフィールドに入力します。</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>元のファイルの MIME タイプを入力します。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプ <code>text/html</code> のファイルは、MIME タイプ <code>image/jpeg</code> のファイルとは異なる方法でブラウザーで処理されます。</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>ファイルの名前を入力します。</p> </li> 
         <li> <p><b>[!UICONTROL URL]</b> </p> <p>送信するファイルの URL を入力します。</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Notarize]</b> </p> <p>このドキュメントを公証する必要があるかどうかを選択します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Library template name]</b> </p> <p>ライブラリテンプレートの名前を入力またはマッピング</p> </li> 
     <li> <p><b>[!UICONTROL Sharing mode]</b> </p> <p>ライブラリドキュメントへのアクセス権を持つユーザーを指定します。</p> </li> 
     <li> <p><b>[!UICONTROL Library document state]</b> </p> <p>ドキュメントがオーサリング状態かアクティブ状態かを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Library template type]</b> </p> <p>使用するライブラリテンプレートタイプごとに、「<b>[!UICONTROL Add item]</b>」をクリックし、テンプレートタイプを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Last event date]</b> </p> <p>ライブラリドキュメントでイベントが発生した最後の日付を入力します。</p> <p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </li> 
     <li> <p><b>[!UICONTROL Library document status]</b> </p> <p>ライブラリドキュメントのステータスを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User info]</td> 
   <td> <p>次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Email]</b> </p> <p>ユーザーのメールアドレスを入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Is account admin]</b> </p> <p>作成したユーザーがアカウント管理者の場合は、このオプションを確認します。</p> </li> 
     <li> <p><b>[!UICONTROL User ID]</b> </p> <p>ユーザーの一意の ID を入力</p> </li> 
     <li> <p><b>[!UICONTROL Account ID]</b> </p> <p>このユーザーに関連付けられた [!DNL Adobe Acrobat Sign] アカウントの一意の ID を入力します。</p> </li> 
     <li> <p><b>[!UICONTROL First name]</b> </p> <p>ユーザーの名前（名）を入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Last name]</b> </p> <p>ユーザーの名前（姓）を入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Company]</b> </p> <p>ユーザーの会社の名前を入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Initials]</b> </p> <p>ユーザーのイニシャルを入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>ユーザーのロケールを入力します。これによって、UI の言語が決まります。 </p> </li> 
     <li> <p><b>[!UICONTROL Phone]</b> </p> <p>ユーザーの電話番号を入力します。</p> </li> 
     <li> <p><b>プライマリグループ ID</b> </p> <p>新しいユーザーを追加するグループを入力します。何も入力しなかった場合、ユーザーはアカウントのデフォルトのグループに追加されます。</p> </li> 
     <li> <p><b>[!UICONTROL Job title]</b> </p> <p>ユーザーの職位を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Web form info]</td> 
   <td> <p>次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL File info]</b> </p> <p>Web フォームに追加するファイルごとに、「追加」をクリックし、以下のフィールドに入力します。</p> 
      <ul> 
       <li> <p>[!UICONTROL File type]</p> <p>[!UICONTROL Document]</p> </li> 
       <li> <p>[!UICONTROL Transient document]</p> </li> 
       <li> <p>[!UICONTROL URL file info]</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form name]</b> </p> <p>Web フォームの名前を入力します。この名前は、メールや web サイトなどの場所で web フォームを識別するために使用されます。</p> </li> 
     <li> <p><b>[!UICONTROL Web form state]</b> </p> <p>Web フォームを新規作成するステートを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Web form participant set info]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>参加者セットに追加する各メンバーに対して、「<b>[!UICONTROL Add item]</b>」をクリックします。 </p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>このオプションは空白のままにします。</p> </li> 
         <li> <p><b>[!UICONTROL Security option]</b> </p> <p>このユーザーを認証するセキュリティオプションを追加する場合は、「<b>[!UICONTROL Yes]</b>」、セキュリティオプションの順に選択し、必要なフィールドに入力します。</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Role]</b> </p> <p>役割を選択します。この参加者セットのすべてのメンバーは、その役割を共有します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form additional participant sets info]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>参加者セットに追加する各メンバーに対して、「<b>[!UICONTROL Add item]</b>」をクリックします。</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>このオプションは空白のままにします。</p> </li> 
         <li> <p><b>[!UICONTROL Security option]</b> </p> <p>このユーザーを認証するセキュリティオプションを追加する場合は、「<b>[!UICONTROL Yes]</b>」、セキュリティオプションの順に選択し、必要なフィールドに入力します。</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Role]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Web form participant ID]</b> </p> <p>Web フォーム参加者の ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Order]</b> </p> <p>この参加者セットが web フォームを操作する順序を指定します。例えば、順序値が 1 の参加者グループが最初に進む必要があり、2 の参加者グループが次に進む、のように続きます。注文番号は 1 から始まり、連続している必要があります。 </p> </li> 
       <li> <p><b>[!UICONTROL Provider participant set info]</b> </p> <p>参加者が不明な場合は、プロバイダーが参加者の詳細を提供する必要があるかどうかを入力し、不明な参加者に必要な詳細を含むメッセージを入力します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Authentication failure info]</b> </p> <p>ユーザーに失敗ページまたはエラーページを示す場合は、「<b>[!UICONTROL Yes]</b>」を選択して次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL URL]</b> </p> <p>エラーページの URL を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Deframe]</b> </p> <p>Web フォーム内にエラーページを表示する場合は、このオプションを有効にします。</p> </li> 
       <li> <p><b>[!UICONTROL Delay]</b> </p> <p>ユーザーがエラーページにリダイレクトされるまでの遅延時間（秒）を入力します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL CC info]</b> </p> <p>Web フォームに対する最終契約が署名されたときにメールを受け取るメールアドレスごとに、「<b>[!UICONTROL Add item]</b>」をクリックしてメールアドレスを入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Completion info]</b> </p> <p style="font-style: normal;">ユーザーに成功ページを示す場合は、「<b>[!UICONTROL Yes]</b>」を選択して次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL URL]</b> </p> <p>成功ページの URL を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Deframe]</b> </p> <p>成功ページを web フォーム内に表示する場合は、このオプションを有効にします。</p> </li> 
       <li> <p><b>[!UICONTROL Delay]</b> </p> <p>ユーザーが成功ページにリダイレクトされるまでの遅延時間（秒）を入力します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Group ID]</b> </p> <p>Web フォームが属するグループの ID を入力します。何も入力しなかった場合、web フォームはアカウントユーザーのプライマリグループに属します。</p> </li> 
     <li> <p><b>[!UICONTROL Last event date]</b> </p> <p>Web フォーム上で最後のイベントが発生した日付を入力します。<code>yyyy-MM-dd'T'HH:mm:ssZ</code> の形式を使用します。</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>ユーザーのロケールを入力します。これによって、UI の言語が決まります。 </p> </li> 
     <li> <p><b>[!UICONTROL Security option]</b> </p> <p>ドキュメントの保護に使用するパスワードを入力します。このパスワードは、各関係者に個別に伝える必要があります。</p> </li> 
     <li> <p><b>[!UICONTROL Vaulting info]</b> </p> <p>アカウントがドキュメント保管用に設定され、契約ごとに有効にするオプションが設定されている場合、このオプションを有効にしてこの契約を保管できます。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 契約を作成]**

このアクションモジュールは、契約を作成し、署名用に送信し、契約 ID を返します。

>[!NOTE]
>
>ドキュメントをアップロードして一時的なドキュメントとして署名し、[!UICONTROL 契約を作成]モジュールの[!UICONTROL 送信するファイル]フィールドにマッピングすることをお勧めします。例については、この記事の「ドキュメントをアップロード」を参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
<td>[!DNL Adobe Acrobat Sign] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</td>  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。例： <code>{"Content-type":"application/json"}</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Files to send]</td> 
   <td> <p>契約に含める項目ごとに、「<b>[!UICONTROL Add Item]</b>」をクリックして次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL File Type]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Document]</b> </p> <p>次のフィールドに入力します。</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Created date]</b> </p> <p>ドキュメントが作成された日付を <code>yyyy-MM-dd'T'HH:mm:ssZ</code> 形式で入力またはマッピングします。例えば、<code>2016-02-25T18:46:19Z</code> は協定世界時（UTC）を表します。</p> </li> 
         <li> <p><b>[!UICONTROL ID]</b> </p> <p>ドキュメントの ID を入力またはマッピングします。</p> </li> 
         <li> <p><b>[!UICONTROL Label]</b> </p> <p>ファイルの一意のラベルを入力またはマッピングします。カスタムワークフローの場合、これはワークフロー定義内の対応するファイル要素にファイルをマッピングします。これは、カスタムワークフロー契約書作成リクエストの場合に指定する必要があります。</p> </li> 
         <li> <p><b>[!UICONTROL Number of pages]</b> </p> <p>ドキュメント内のページ数を入力またはマッピングします。</p> </li> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>元のファイルの MIME タイプを入力またはマッピングします。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプ <code>text/html</code> のファイルは、MIME タイプ <code>image/jpeg</code> のファイルとは異なる方法でブラウザーで処理されます。</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>ドキュメントの名前を入力またはマッピングします。<br></p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Library document ID]</b> </p> <p>ライブラリドキュメントの ID を入力</p> </li> 
       <li> <p><b>[!UICONTROL Transient document ID]</b> </p> <p>一時的なドキュメントの ID の入力</p> </li> 
       <li> <p><b>[!UICONTROL URL file transfer]</b> </p> <p>次のフィールドに入力します。</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>元のファイルの MIME タイプを入力します。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプ <code>text/html</code> のファイルは、MIME タイプ <code>image/jpeg</code> のファイルとは異なる方法でブラウザーで処理されます。</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>ファイルの名前を入力します。</p> </li> 
         <li> <p><b>[!UICONTROL URL]</b> </p> <p>送信するファイルの URL を入力します。</p> </li> 
        </ul> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>ファイルのラベルを入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Notarize]</b> </p> <p>ファイルを認証する必要があることを示すには、このオプションを有効にします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement name]</td> 
   <td>新しい契約の名前を入力します。この名前は、メールや Web サイト内などで契約を識別するために使用されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Participant sets info]</td> 
   <td> <p>追加する参加者セットに対して、「<b>[!UICONTROL Add item]</b>」をクリックして、次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Members]</b> </p> <p>参加者セットに追加する各ユーザーに対して、「<b>[!UICONTROL Add item]</b>」をクリックして、ユーザーのメールアドレスを入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Order]</b> </p> <p>この参加者セットが契約に署名する順序を指定します。例えば、注文値が 1 の参加者グループは最初に署名し、2 は次に署名する必要があります。注文番号は 1 から始まり、連続している必要があります。 </p> </li> 
     <li> <p><b>[!UICONTROL Role]</b> </p> <p>この参加者セットの役割を選択します。セット内のすべての参加者がこの役割を受け取ります。</p> </li> 
     <li> <p><b>[!UICONTROL ID]</b> </p> <p>この参加者セットの ID を入力またはマッピングします。</p> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>参加者セットの一意のラベルを入力またはマッピングします。カスタムワークフローの場合、参加者セットで指定されたラベルを、カスタムワークフローの参加ステップにマッピングする必要があります。</p> </li> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>参加者セットの名前を入力します。この名前は、契約内で一意である必要があります。</p> </li> 
     <li> <p><b>[!UICONTROL Private message]</b> </p> <p>この参加者セットのメッセージを入力またはマッピングします。セット内のすべての参加者がこのメッセージを受け取ります。</p> </li> 
     <li> <p><b>[!UICONTROL Visible pages]</b> </p> <p>この契約でドキュメントの表示制限が有効な場合は、この参加者セットに表示するファイルを指定します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Signature type]</td> 
   <td> <p>契約に必要な署名のタイプを選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL E-sign]</b> </p> <p>契約に電子サインが必要です。</p> </li> 
     <li> <p><b>[!UICONTROL Written]</b> </p> <p>契約は手動で署名する必要があり、署名された契約をスキャンおよびアップロードする必要があります。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td> <p>この契約の状態を選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Authoring]</b> </p> <p>この契約にフィールドを編集または追加することができます。</p> </li> 
     <li> <p><b>[!UICONTROL Draft]</b> </p> <p>この契約は、送信する前に段階的に作成できます。</p> </li> 
     <li> <p><b>[!UICONTROL In Process]</b> </p> <p>この契約は直ちに送信されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CCs]</td> 
   <td> <p>関係者など、署名する必要のない人に対して、この契約を送信できます。署名プロセスの開始時にメールを受信し、最終署名を受信するときにも別のメールを受信します。また、契約書の PDF コピーも受け取ります。 </p> <p>この契約を CC 送信する担当者ごとに、「<b>[!UICONTROL Add item]</b>」をクリックして次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Email]</b> </p> <p>契約の CC 送信先のメールアドレスを入力またはマッピングします。</p> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>ワークフローの説明に示すように、このメールアドレスのラベルを入力またはマッピングします。</p> </li> 
     <li> <p><b>[!UICONTROL Visible pages]</b> </p> </li> 
     <li> <p>この契約でドキュメントの表示制限が有効な場合は、この参加者セットに表示するファイルを指定します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email option]</td> 
   <td> <p>メールのタイプごとに、そのタイプのメールをすべての参加者に送信するか、まったく送信しないかを選択します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Completion emails]</b> </p> <p>この契約が完了、キャンセル、期限切れまたは却下されたときにメールを送信します。</p> </li> 
     <li> <p><b>[!UICONTROL In-Flight emails]</b> </p> <p>この契約がデリゲートされたとき、または置き換えられたときに、メールを送信します。</p> </li> 
     <li> <p><b>[!UICONTROL Agreement initiation emails]</b> </p> <p>この契約が作成されたとき、または契約に対するアクションがリクエストされたときに、メールを送信します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td> <p>この契約の ID を入力またはマッピングします。契約の作成時にこれを指定すると、それを使用して後のモジュールまたはクエリで契約を検索することができます。</p> <p>メモ：外部 ID の値は API を通じてすべての参加者に表示されるので、機密トークンを含めるために使用しないでください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Merge field info]</td> 
   <td> <p>デフォルト値を設定する契約の各フィールドについて、「<b>[!UICONTROL Add item]</b>」をクリックしてデフォルト値とフィールド名を入力します。</p> <p>この値は、編集可能フィールドの署名者に表示されます。読み取り専用フィールドの場合、指定された値は署名プロセス中に編集できません。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Notary info]</td> 
   <td> <p>次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Appointment]</b> </p> <p>この契約を公証する予定として提案された日時を入力またはマッピングします。</p> </li> 
     <li> <p><b>[!UICONTROL Note]</b> </p> <p>公証人セッションに関する追加メモを入力またはマッピングします。</p> </li> 
     <li> <p><b>[!UICONTROL Payment]</b> </p> <p>公証人に対する支払いを署名者が行うか、契約の送信者が行うかを選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Notary Type]</b> </p> <p>公証人のタイプの選択</p> 
      <ul> 
       <li> <p>[!UICONTROL Provider notary]</p> <p>公証人は公証人機関によって指定されます。</p> </li> 
       <li> <p>[!UICONTROL BYON notary]</p> <p>公証人は顧客が指定します。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Post sign option]</td> 
   <td> <p>契約の署名後に署名者を成功ページに誘導するかどうかを選択します。「<b>[!UICONTROL Yes]</b>」を選択した場合は、以下のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Redirect delay]</b> </p> <p>署名者が成功ページにリダイレクトされるまでの秒数を入力またはマッピングします。この値が 0 より大きい場合、最初に標準の [!DNL Adobe Sign] の成功メッセージが表示され、そのしばらく後に所定の成功ページにリダイレクトされます。</p> </li> 
     <li> <p><b>[!UICONTROL Redirect URL]</b> </p> <p>署名プロセスが正常に完了した後にユーザーに表示される、一般にアクセス可能な URL を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Security option]</td> 
   <td> <p>PDF ドキュメントの保護に使用するセカンダリパスワードを入力またはマッピングします。 </p> <p>重要：[!DNL Adobe Sign] ではこのパスワードを共有しないので、関係者に別途伝える必要があります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Vaulting info]</td> 
   <td>アカウントがドキュメント保管用に設定され、契約ごとに有効にするオプションが設定されている場合、このオプションを有効にしてこの契約を保管できます。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 関連レコードを作成]**

このアクションモジュールは、選択したモジュールにリンクされたレコードを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>作成したレコードを関連付ける、元のレコードのレコードタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement]／[!UICONTROL Library document]/[!UICONTROL User]／[!UICONTROL Widget ID]</td> 
   <td>作成したレコードを関連付けるオブジェクトの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement related field]</td> 
   <td> <p>作成する関連フィールドのタイプを選択します</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Form fields]</b> </p> <p>作成するフィールドが含まれるテンプレートのテンプレート ID を入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Reminders]</b> </p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Recipient participant ID]</b> </p> <p>リマインダーを受け取る参加者ごとに、「[!UICONTROL Add item]」をクリックして、参加者の ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Status]</b> </p> <p>新しいレコードの場合、ステータスは「[!UICONTROL Active]」である必要があります。</p> </li> 
       <li> <p><b>[!UICONTROL First reminder delay]</b> </p> <p>最初のリマインダーを送信するまでの遅延時間を時間単位で入力します。許可される最小値は 1 時間で、最大値は契約の作成時間と有効期限の時間単位の差を超えることはできません。この遅延を設定しない場合、最初のリマインダーは頻度に基づいて行われます。</p> </li> 
       <li> <p><b>[!UICONTROL Reminder frequency]</b> </p> <p>リマインダーを送信する頻度を設定します。頻度を指定しない場合、リマインダーは 1 回だけ送信されます。</p> </li> 
       <li> <p><b>[!UICONTROL Last sent date]</b> </p> <p>このフィールドはシステムによって設定されます。</p> </li> 
       <li> <p><b>[!UICONTROL Next sent date]</b> </p> <p>このフィールドは空白にするか、[!UICONTROL ONCE]に設定する必要があります。</p> </li> 
       <li> <p><b>[!UICONTROL Note]</b> </p> <p>リマインダーに含めるメモを入力します。参加が必要な理由を参加者に伝えるのに役立ちます。</p> </li> 
       <li> <p><b>[!UICONTROL Start reminder counter from]</b> </p> <p>リマインダーを送信するタイミングを、使用可能になった時点で契約が作成されるタイミングに基づいて選択します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Signer identity report]</b> </p> <p>PDF ドキュメントの保護に使用するパスワードを入力します。</p> </li> 
     <li> <p><b>[!UICONTROL Views]</b> </p> <p>次のフィールドを入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>作成するビューの名前を選択します。</p> </li> 
       <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、返された URL にユーザーが自動的にログインします。</p> </li> 
       <li> <p><b>[!UICONTROL Frame Parent]</b> </p> <p>返された URL を iFrame で表示する親ドメイン URL のコンマ区切りのリストを入力またはマッピングします。空白の場合、[!DNL Adobe Acrobat Sign] ページを iFrame で表示できません。</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>ビューを作成する言語を入力します。 </p> </li> 
       <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ナビゲーションのヘッダーやフッターを含めずに埋め込みページを表示します。</p> </li> 
       <li> <p><b>[!UICONTROL Can edit files]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ファイルを追加または削除してファイルのアップロードセクションを編集できます。これはアクセス制御メカニズムではありません。デフォルト値は「[!UICONTROL Yes]」です。</p> </li> 
       <li> <p><b>[!UICONTROL Library document]</b> </p> <p>ライブラリドキュメントのリンクを表示する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。デフォルト値は「[!UICONTROL Yes]」です。</p> </li> 
       <li> <p><b>[!UICONTROL Local file]</b> </p> <p>ローカルファイルのアップロードボタンを表示する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。デフォルト値は「[!UICONTROL Yes]」です。</p> </li> 
       <li> <p><b>[!UICONTROL Web connectors]</b> </p> <p>Web ソースのドキュメントを添付するリンクを表示する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。デフォルトは「Yes」です。</p> </li> 
       <li> <p><b>[!UICONTROL Is preview selected]</b> </p> <p>作成ページをオーサリングモードに設定する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Member share]</b> </p> <p>契約を共有するメンバーごとに「<b>[!UICONTROL Add item]</b>」をクリックし、メンバーのメールアドレスと、そのメンバーへのメッセージを入力します。</p> </li> 
     <li> <p>[!UICONTROL Delegate participant set]</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Participant set ID]</b> </p> <p>参加者セットの ID を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>追加するメンバーごとに「[!UICONTROL Add item]」をクリックし、そのメンバーのメールアドレスと電話番号を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Private message]</b> </p> <p>メッセージを入力します。このメッセージは、参加者セットのすべてのメンバーが受け取ります。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Library view info]</td> 
   <td> <p>次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>ライブラリテンプレートの名前を入力します。この名前はメールや web サイトで使用されます。</p> </li> 
     <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、返された URL にユーザーが自動的にログインします。</p> </li> 
     <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>返された URL を iFrame で表示する親ドメイン URL のコンマ区切りのリストを入力またはマッピングします。空白の場合、[!DNL Adobe Acrobat Sign] ページを iFrame で表示できません。</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>ビューを作成する言語を入力します。 </p> </li> 
     <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ナビゲーションのヘッダーやフッターを含めずに埋め込みページを表示します。</p> </li> 
     <li> <p><b>[!UICONTROL Send view configuration]</b> </p> <p>[!UICONTROL Send] ビューを設定する場合は、「<b>[!UICONTROL Yes]</b>」を選択して、次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Agreement name]</b> </p> <p>作成ページでライブラリドキュメントの契約名を入力またはマッピングします。</p> </li> 
       <li> <p><b>[!UICONTROL Can edit files]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ファイルを追加または削除してファイルのアップロードセクションを編集できます。これはアクセス制御メカニズムではありません。デフォルト値は「[!UICONTROL Yes]」です。</p> </li> 
       <li> <p><b>[!UICONTROL Local file]</b> </p> <p>ライブラリドキュメントのリンクを表示する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。デフォルト値は「[!UICONTROL Yes]」です。</p> </li> 
       <li> <p><b>[!UICONTROL Web connectors]</b> </p> <p>Web ソースのドキュメントを添付するリンクを表示する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。デフォルト値は「[!UICONTROL Yes]」です。</p> </li> 
       <li> <p><b>プレビューを選択済み</b> </p> <p>作成ページをオーサリングモードに設定する場合は、「<b>[!UICONTROL Yes]</b>」を選択します。</p> </li> 
      </ul> <p> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User view info]</td> 
   <td> <p>次のフィールドに入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>リクエストされるユーザービューの名前を選択します。</p> </li> 
     <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ユーザーが自動的にログインします。資格情報が必要な場合は、「<b>[!UICONTROL No]</b>」を選択します。デフォルト値は「[!UICONTROL No]」です。</p> </li> 
     <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>返された URL を iFrame で表示する親ドメイン URL のコンマ区切りのリストを入力またはマッピングします。空白の場合、[!DNL Adobe Acrobat Sign] ページを iFrame で表示できません。</p> </li> 
     <li> <p><b>クロムフラグなし</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ナビゲーションのヘッダーやフッターを含めずに埋め込みページを表示します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Widget related fields]</td> 
   <td> <p>作成する関連レコードを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Views]</p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>リクエストされる web フォームビューの名前を選択します。</p> </li> 
       <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ユーザーが自動的にログインします。資格情報が必要な場合は、「<b>[!UICONTROL No]</b>」を選択します。デフォルト値は「[!UICONTROL No]」です。</p> </li> 
       <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>返された URL を iFrame で表示する親ドメイン URL のコンマ区切りのリストを入力またはマッピングします。空白の場合、[!DNL Adobe Acrobat Sign] ページを iFrame で表示できません。</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>ビューを作成する言語を入力します。 </p> </li> 
       <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択すると、ナビゲーションのヘッダーやフッターを含めずに埋め込みページを表示します。</p> </li> 
       <li> <p>[!UICONTROL Personalized signing view configuration]</p> <p>パーソナライズした署名ビューを設定する場合は、「<b>[!UICONTROL Yes]</b>」を選択して次のフィールドに入力します。</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>新しく作成された web フォームを受け取るユーザーのメールアドレスを入力します。</p> </li> 
         <li> <p><b>[!UICONTROL Comment]</b> </p> <p>API 呼び出し元が署名者の ID を確立する方法を説明するコメントを入力します。この情報は、[!DNL Adobe Acrobat Sign] 監査証跡に表示されます。</p> </li> 
         <li> <p><b>[!UICONTROL Expiration]</b> </p> <p>この web フォームのパーソナライズ機能の有効期限を入力します。 </p> <p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override=""> 型強制 </a>」を参照してください。</p> </li> 
         <li> <p><b>[!UICONTROL Reusable]</b> </p> <p>対象の署名者が複数回フォームに署名できるようにする場合は、「<b>[!UICONTROL Yes]</b>」を選択します。</p> </li> 
        </ul> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Member share]</b> </p> <p>契約を共有するメンバーごとに「<b>[!UICONTROL Add item]</b>」をクリックし、メンバーのメールアドレスと、そのメンバーへのメッセージを入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL カスタム API 呼び出し]**
このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>相対パスを入力します <code>https://api.[region].adobesign.com/api/rest/v6/</code></p> <p>メモ：使用可能なエンドポイントの一覧については、[!DNL Adobe Sign] API リファレンスを参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>リクエストクエリ文字列を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a transient document]</td> 
   <td> <p>一時的なドキュメントをアップロードする場合は、アップロードするドキュメントのソースファイルを入力します。</p> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL レコードをリスト]**

このアクションモジュールは、アカウントがアクセスできる選択したタイプのすべてのレコードをリスト表示します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>関連レコードを取得するレコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td> <p>ユーザーのロケールを入力します。これによって、UI の言語が決まります。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td>返信する契約に使用する外部 ID（[!DNL Adobe Acrobat Sign] 以外で割り当てられた ID）を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group ID]</td> 
   <td>リストするレコードに関連付けられたグループの ID を入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show hidden (records)]</td> 
   <td>結果に非表示のレコードを含める場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Cursor]／[!UICONTROL Start index]</td> 
   <td> <p>モジュールが返す最初のレコードの数を入力します。 </p> <p>メモ：このフィールドは、ページネーション用に [!UICONTROL Maximum number of returned records] フィールドと組み合わせることができます。例えば、[!UICONTROL Maximum number of returned events] が 100 で、[!UICONTROL Start index] が 101 の場合、モジュールは 101～200 個のレコード、または結果の 2 ページ目を返します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned records]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> <p>メモ：このフィールドは、ページネーション用に [!UICONTROL Cursor] フィールドまたは [!UICONTROL Start Index] フィールドと組み合わせることができます。例えば、[!UICONTROL Maximum number of returned events] が 100 で、[!UICONTROL Start index] が 101 の場合、モジュールは 101～200 個のレコード、または結果の 2 ページ目を返します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent domain URLs]</td> 
   <td> <p>返された URL を iFrame で表示する親ドメイン URL のコンマ区切りのリストを入力またはマッピングします。空白の場合、[!DNL Adobe Acrobat Sign] ページを iFrame で表示できません。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL レコードを読み取り]**

このアクションモジュールは、1 つのレコードから情報を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>関連レコードを取得するレコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
   <td>取得するレコードの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 関連レコードを読み取り]**

1 つのレコードに関する追加情報を読み取ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>関連レコードを取得するレコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]（例：[!UICONTROL Account ID]）</td> 
   <td>関連レコードを取得するレコードの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td>レコードタイプおよび関連するフィールドに基づいて、特定のフィールドに情報を入力します。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL レコードを更新]**

このアクションモジュールは、[!DNL Adobe Acrobat Sign] 内の 1 つのレコードを更新します。

>[!IMPORTANT]
>
>* ベストプラクティスとして、契約に大幅な変更が予想される場合は、既存の契約を更新するのではなく、契約を新規作成することをお勧めします。
>* 一部の更新には、必須フィールドが含まれています。更新を設定する際は、すべての必須フィールドに必ず入力してください。Workfront Fusion モジュールでは、必須フィールドは太字で表示されます。
>



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID] </td> 
   <td>更新するレコードの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>更新するレコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td> <p>レコードタイプおよび関連するフィールドに基づいて、特定のフィールドに情報を入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Agreement]</b> </p> <p>ベストプラクティスとして、契約に大幅な変更が予想される場合は、既存の契約を更新するのではなく、契約を新規作成することをお勧めします。</p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> <p>更新するフィールドを選択し、選択したフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Status]</b> </p> <p>ライブラリドキュメントの新しいステータスを選択します。</p> </li> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>ライブラリテンプレートの名前を入力またはマッピング</p> </li> 
       <li> <p><b>[!UICONTROL Sharing mode]</b> </p> <p>ライブラリドキュメントへのアクセス権を持つユーザーを指定します。</p> </li> 
       <li> <p><b>[!UICONTROL Library template type]</b> </p> <p>使用するライブラリテンプレートタイプごとに、「<b>[!UICONTROL Add item]</b>」をクリックし、テンプレートタイプを選択します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> <p>更新するフィールドを選択し、選択したフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL First name]</b> </p> <p>ユーザーの名前（名）を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Last name]</b> </p> <p>ユーザーの名前（姓）を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Company]</b> </p> <p>ユーザーの会社の名前を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Phone]</b> </p> <p>ユーザーの電話番号を入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Primary group ID]</b> </p> <p>新しいユーザーを追加するグループを入力します。何も入力しなかった場合、ユーザーはアカウントのデフォルトのグループに追加されます。</p> </li> 
       <li> <p><b>[!UICONTROL Job title]</b> </p> <p>ユーザーの職位を入力します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form]（[!UICONTROL widget]）</b> </p> <p>レコードタイプおよび関連するフィールドに基づいて、特定のフィールドに情報を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 関連レコードを更新]**

このアクションモジュールは、特定のオブジェクトに関連するレコードを更新します。

>[!IMPORTANT]
>
>* ベストプラクティスとして、契約に大幅な変更が予想される場合は、既存の契約を更新するのではなく、契約を新規作成することをお勧めします。
>* 一部の更新には、必須フィールドが含まれています。更新を設定する際は、すべての必須フィールドに必ず入力してください。Workfront Fusion モジュールでは、必須フィールドは太字で表示されます。
>



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>関連するフィールドが関連付けられているレコードのレコードタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement]／[!UICONTROL Library document]/[!UICONTROL User]／[!UICONTROL Widget ID]</td> 
   <td>作成したレコードを関連付けるオブジェクトの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td> <p>レコードタイプおよび関連するフィールドに基づいて、特定のフィールドに情報を入力します。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Agreement]</b> </p> <p>ベストプラクティスとして、契約に大幅な変更が予想される場合は、既存の契約を更新するのではなく、契約を新規作成することをお勧めします。</p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> <p>更新するフィールドを選択し、選択したフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL State]</b> </p> <p>ライブラリドキュメントの新しいステータスを選択します。</p> </li> 
       <li> <p><b>[!UICONTROL Note]</b> </p> <p>メモのテキストを入力またはマッピングします。</p> </li> 
       <li> <p><b>[!UICONTROL Visibility]</b> </p> <p>ライブラリドキュメントを表示するか、非表示にするかを選択します。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> <p>更新するフィールドを選択し、選択したフィールドに入力します。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Group info list]</b> </p> <p>次のフィールドに入力します。</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Status]</b> </p> <p>ユーザーの新しいステータスを選択します。</p> </li> 
         <li> <p><b>[!UICONTROL ID]</b> </p> <p>グループの一意の ID を入力</p> </li> 
         <li> <p><b>[!UICONTROL Is group admin]</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択して、このユーザーをグループ管理者にします。</p> </li> 
         <li> <p><b>プライマリグループです</b> </p> <p>「<b>[!UICONTROL Yes]</b>」を選択して、このグループをユーザーのプライマリグループにアップデートします。</p> </li> 
         <li> <p><b>[!UICONTROL Created date]</b> </p> <p>グループの作成日を入力します。</p> <p>サポートされる日付と時刻の形式のリストについては、<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">[!UICONTROL Adobe Workfront Fusion] での型強制</a>を参照してください。</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>グループの名前を入力またはマッピングします。</p> </li> 
         <li> <p><b>[!UICONTROL Library document creation visible]</b> </p> <p>これらの設定は、ユーザーがライブラリドキュメントを作成できるかどうかを決定します</p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>許可</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>グループまたはアカウントからグループ設定を継承</p> </li> 
          </ul> </li> 
         <li> <p><b>[!UICONTROL Send restricted to workflows]</b> </p> <p>これらの設定は、ユーザーがワークフローを使用してのみ契約を作成できるかどうかを決定します。</p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>許可</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>グループまたはアカウントからグループ設定を継承</p> </li> 
          </ul> </li> 
         <li> <p><b>[!UICONTROL User can send]</b> </p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>許可</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>グループまたはアカウントからグループ設定を継承</p> </li> 
          </ul> </li> 
        </ul> </li> 
      </ul> 
      <ul> 
       <li> <p><b>[!UICONTROL State]</b> </p> <p>ユーザーの新しい状態を選択し、ユーザーをアクティブ化または非アクティブ化する理由に関するコメントを入力します。</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>ユーザーのロケールを入力します。これによって、UI の言語が決まります。 </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form]（[!UICONTROL widget]）</b> </p> <p>レコードタイプおよび関連するフィールドに基づいて、特定のフィールドに情報を入力します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL ドキュメントをアップロード]**

一時的なドキュメントをアップロードします。一時的なドキュメントは、アップロード後 7 日間使用できます。

>[!NOTE]
>
>ドキュメントをアップロードして一時的なドキュメントとして署名し、そのドキュメントを契約を作成モジュールの「送信するファイル」フィールドにマッピングすることをお勧めします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
   <td>アップデートするレコードの ID を入力またはマッピング</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME type]</td> 
   <td>元のファイルの MIME タイプを入力します。多目的インターネットメール拡張（MIME）タイプは、ソフトウェアがインターネットで共有される様々なタイプのデータを識別できるラベルです。Web サーバーおよびブラウザーは、MIME タイプを使用して、ファイルに対して何を実行するかを決定します。例えば、MIME タイプ <code>text/html</code> のファイルは、MIME タイプ <code>image/jpeg</code> のファイルとは異なる方法でブラウザーで処理されます。</td> 
  </tr> 
 </tbody> 
</table>

**例：**&#x200B;このワークフローでは、署名するドキュメント（以前 Workfront からダウンロードしたもの）は、一時的なドキュメントとしてアップロードされます。

（/help/workfront-fusion/references/apps-and-modules/assets/sign-example-1-350x308.png）

[!UICONTROL ドキュメントをアップロード]モジュールは、後のモジュールで参照できる [!DNL Adobe Acrobat Sign] ID をドキュメントに与えます。契約が作成されると、アップロードされたドキュメントの ID が「[!UICONTROL 送信するファイル]」フィールドに含まれます。

![Sign の例 ](/help/workfront-fusion/references/apps-and-modules/assets/sign-example-2-350x356.png)

+++

### 検索

+++ **[!UICONTROL 契約を検索]**

この検索モジュールは、指定した基準に基づいて契約を検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Acrobat Sign] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text filter]</td> 
   <td> <p>契約メタデータ内のテキストを検索します。 </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Find text]</b> </p> <p>契約メタデータで検索するテキストを入力します。各単語は、別々のテキスト項目として扱われます。 </p> </li> 
     <li> <p><b>[!UICONTROL Find text in]</b> </p> <p>テキストを検索するメタデータフィールドを選択します。何も選択しない場合、モジュールはすべてのメタデータを検索します。</p> </li> 
    </ul> <p>モジュールは、選択したフィールドに入力されたテキストを含む契約を返します。例：「春のキャンペーン」を入力し、「タイトル」オプションと「メモ」オプションを選択すると、「タイトル」または「メモ」に「春」または「キャンペーン」という単語を含む契約が返されます。</p> <p>[!DNL Adobe Acrobat Sign] でのフィールドの検索について詳しくは、<a href="https://helpx.adobe.com/jp/sign/using/adobesign-search-users-agreements.html#HowSearchWorks">[!DNL Adobe Sign]検索 - 仕組み</a>内の「テキスト検索の仕組み」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created date]</td> 
   <td>日付を選択します。このモジュールは、作成された日付がこの条件と一致するレコードのみを返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiration date]</td> 
   <td>日付を選択します。このモジュールは、有効期限がこの条件と一致するレコードのみを返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL Modified date]</p> </td> 
   <td>日付を選択します。このモジュールは、変更された日付がこの条件と一致するレコードのみを返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td> <p> 外部 ID は、契約に送信者が割り当てた ID で、どの形式でもかまいませんが、通常は「&lt;groupID&gt;:&lt;ID&gt;」です。</p> <p>追加する外部 ID ごとに「<b>[!UICONTROL Add]</b>」をクリックし、外部 ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group ID]</td> 
   <td> <p>グループ ID は、グループの作成時に割り当てられた識別子です。</p> <p>追加する外部 ID ごとに「<b>[!UICONTROL Add]</b>」をクリックし、外部 ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>これは、特定の契約に割り当てられた ID です。 </p> <p>追加する外部 ID ごとに「<b>[!UICONTROL Add]</b>」をクリックし、外部 ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent ID]</td> 
   <td> <p>これは、契約の親オブジェクトに割り当てられた ID です。 </p> <p>追加する外部 ID ごとに「<b>[!UICONTROL Add]</b>」をクリックし、外部 ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Participant email]</td> 
   <td> <p>参加者のメールアドレスです。 </p> <p>追加する外部 ID ごとに「<b>[!UICONTROL Add]</b>」をクリックし、外部 ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Role]</td> 
   <td>返された結果に含める役割を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td>モジュールで結果を並べ替える場合は、結果の並べ替えに使用するフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort order]</td> 
   <td>モジュールで結果を並べ替える場合は、昇順と降順のどちらで並べ替えるかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status]</td> 
   <td>返された結果に含めるステータスを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>返された結果に含める契約タイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subtypes]</td> 
   <td>返された結果に含める契約サブタイプを選択します。ライブラリテンプレート契約にのみ、サブタイプが含まれます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User ID]</td> 
   <td> <p>契約を共有するユーザーのユーザー ID です。</p> <p>追加するユーザー ID ごとに「<b>[!UICONTROL Add]</b>」をクリックし、ユーザー ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>返された結果に含める表示レベルを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start index]</td> 
   <td> <p>返す最初の結果の位置を入力します。これを [!UICONTROL maximum returned results] と組み合わせて、結果にページ番号を付けます。</p> <p>例：一度に 100 個の結果を返す場合は、100 と入力して 100～200 個の結果を返します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++
