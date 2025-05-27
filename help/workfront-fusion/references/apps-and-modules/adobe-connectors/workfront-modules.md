---
title: Adobe Workfront モジュール
description: Adobe Workfront Fusion Adobe Workfront コネクタを使用すると、Workfront 内でのプロセスを自動化できます。Workfront Fusion for Work Automation and Integration ライセンスをお持ちの場合は、それを使用してサードパーティのアプリケーションやサービスに接続することもできます。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 93c27cf6-38b0-466c-87bb-926c4817eae7
source-git-commit: 32de8028b8870c9a3b569b87032513318c255171
workflow-type: tm+mt
source-wordcount: '7942'
ht-degree: 56%

---

# Adobe Workfront モジュール

Adobe Workfront Fusion Adobe Workfront コネクタを使用すると、Workfront 内でのプロセスを自動化できます。また、Workfrontを他のアプリケーションやサービスに接続することもできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。 モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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
   <p>レガシー：任意 </p>
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


>[!NOTE]
>
>* 従来のライセンスパッケージ（コネクタに基づく）を使用する場合、サードパーティのアプリやサービスに接続するには、作業自動化および統合用のWorkfront Fusion ライセンスが必要です。 Workfront コネクタは、組織で使用可能なアクティブなアプリの数にはカウントされません。 すべてのシナリオは、Workfront アプリのみを使用する場合でも、組織の合計シナリオ数に対してカウントされます。

+++

## WorkfrontのWorkfront Fusion への接続

Workfront コネクタは、OAuth 2.0 を使用してWorkfrontに接続します。

Workfront アカウントへの接続は、Workfront Fusion モジュール内から直接作成できます。

1. 任意の Adobe Workfront モジュールで、「接続」フィールドの横にある「**追加**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>新しい接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>本番環境と非本番環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Workfront クライアント ID を入力します。 これは、Workfront の設定エリアの OAuth2 アプリケーションエリアにあります。接続している特定のアプリケーションを開いて、クライアント ID を確認します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Workfront クライアントの秘密鍵を入力します。 これは、Workfront の設定エリアの OAuth2 アプリケーションエリアにあります。Workfrontで OAuth2 アプリケーションのクライアント秘密鍵がない場合は、別の秘密鍵を生成できます。 手順については、Workfrontのドキュメントを参照してください。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>これはデフォルト値のままにすることもできますし、Workfront インスタンスの URL に続けて <code>/integrations/oauth2</code> を入力することもできます。 <p>例： <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>ほとんどの場合、この値は <code>origin</code> にしてください。
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

   Workfrontにログインしていない場合は、ログイン画面が表示されます。 ログイン後、接続を許可できます。

>[!NOTE]
>
>* Workfront API への OAuth 2.0 接続は、API キーに依存しなくなりました。
>* Workfront サンドボックス環境への接続を作成するには、その環境で OAuth2 アプリケーションを作成し、接続でそのアプリケーションによって生成されたクライアント ID とクライアントシークレットを使用する必要があります。

## Workfront モジュールとそのフィールド

Workfront Fusion でWorkfront モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のWorkfront フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。


![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* Workfront モジュールに最新のフィールドが表示されない場合は、キャッシュの問題が原因である可能性があります。1 時間待ってから、もう一度試してください。
>* Adobe Workfrontの HTTP 429 ステータスコードは、アクティベート解除の原因ではなく、代わりに、シナリオで短い実行の一時停止をトリガーにする必要があります。

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

<!--
* [Watch Events](#watch-events) 
* [Watch Record](#watch-record) 
* [Watch Field](#watch-field)
-->

+++ **[!UICONTROL イベントを監視]**

このトリガーモジュールは、Workfront で特定のタイプのオブジェクトが追加、更新、または削除された場合に、シナリオをリアルタイムで実行します。

このモジュールは、レコードに関連付けられた標準フィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

1. 「**Web フック**」ボックスの右側にある「**[!UICONTROL 追加]**」をクリックします。

1. 表示される「**[!UICONTROL フックを追加]**」ボックスで Web フックを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Webhook name]</td> 
      <td>Web フックの名前を入力します。</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Connection]</td> 
      <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Record Type]</td> 
      <td>モジュールで監視するWorkfront レコードのタイプを選択します。</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL State]</td> 
      <td>古い状態と新しい状態のどちらを監視するかを選択します。<ul><li><p><b>[!UICONTROL New state]</b></p><p>レコードが指定された値<b>に</b>変化したときにシナリオをトリガーします。</p><p>例えば、状態が [!UICONTROL New State] に設定され、フィルターが [!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress] に設定されている場合、[!UICONTROL Status] が [!UICONTROL In Progress] に変わると、以前のステータスに関係なく、web フックがシナリオをトリガーします。 </p></li><li><p><b>[!UICONTROL Old state]</b></p><p>レコードが指定された値<b>から</b>変化したときにシナリオをトリガーします。</p><p>例えば、状態が [!UICONTROL Old State] に設定され、フィルターが [!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress] に設定されている場合、現在 [!UICONTROL In Progress] である [!UICONTROL Status] が別のステータスに変わると、web フックがシナリオをトリガーします。 </p></li></ul></td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>選択した条件を満たすレコードのみを監視するフィルターを設定できます。</p> <p>各フィルターに対して、フィルターを評価するフィールド、演算子、およびフィルターに許可する値を入力します。AND ルールを追加すると、複数のフィルターを使用できます。</p> <p><b> メモ </b>：既存のWorkfront Webhook ではフィルターを編集できません。 Workfront イベント購読用に異なるフィルターを設定するには、現在の Webhook を削除して、新しい Webhook を作成します。</p> <p>イベントフィルターについて詳しくは、この記事の <a href="#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Workfront &gt; [!UICONTROL Watch Events] モジュールのイベント購読フィルター </a> を参照してください。</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td>Exclude events made by this connection</td> 
      <td>このトリガーモジュールが使用するのと同じコネクターを使用して作成または更新されたイベントを除外するには、このオプションを有効にします。これにより、シナリオが自分自身をトリガーし、無限ループが繰り返されることを防ぐことができます。<p><b> 注意 </b>: 「アサイメント」レコード・タイプには、このオプションは含まれていません。</p></td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Record Origin]</td> 
      <td>
       <p>シナリオで [!UICONTROL New Records Only]、[!UICONTROL Updated Records Only]、[!UICONTROL New and Updated Records]、または [!DNL Deleted Records Only] を監視するかどうかを選択します。</p>
       <p><b> メモ </b>: [!UICONTROL 新規および更新されたレコード &#x200B;] を選択する場合、Webhook の作成により（同じ Webhook アドレスに対して） 2 つのイベント購読が作成されます。</p>
       </td> 
     </tr> 
    </tbody> 
   </table>



   <!--Markdown 0032 placeholder-->

Web フックを作成した後、イベントの送信先エンドポイントのアドレスを表示できます。

詳しくは、Workfront ドキュメントの Event Subscription API の記事の [ イベントペイロードの例 ](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-api#examples-of-event-payloads) を参照してください。

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **[!UICONTROL フィールドを監視]**

このトリガーモジュールは、指定したフィールドが更新されるとシナリオを実行します。モジュールは、指定されたフィールドの古い値と新しい値の両方を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで監視するWorkfront レコードのタイプを選択します。</p> <p>例えば、タスクでレコードフィールドが更新されるたびにシナリオの実行を開始する場合は、[!UICONTROL Task] を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Field]</td> 
   <td>モジュールで更新を監視するフィールドを選択します。これらのフィールドは、Workfront管理者がトラッキング用に設定したフィールドを反映しています。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td>このモジュールの出力バンドルに含めるオブジェクトフィールドを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **[!UICONTROL レコードを監視]**

このトリガーモジュールは、特定のタイプのオブジェクトが追加、更新、またはその両方が行われた場合にシナリオを実行します。このモジュールは、レコードに関連付けられたすべての標準フィールドと、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

出力のモジュールは、各レコードが新規か更新かを示します。

シナリオが前回実行されてから追加および更新されたレコードは、新しいレコードとして返されます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>シナリオで [!UICONTROL New Records Only]、[!UICONTROL Updated Records Only]、または [!UICONTROL New and Updated Records] を監視するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで監視するWorkfront レコードのタイプを選択します。</p> <p>例えば、新しいプロジェクトが作成されるたびにシナリオを開始するには、「[!UICONTROL Project]」を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 参照 &#x200B;]</td> 
   <td> <p>このモジュールの出力バンドルに含める参照フィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含めるコレクションフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Optional Filter]</td> 
   <td> <p>（詳細）API コード文字列を入力して、条件を絞り込む追加のパラメーターまたはコードを定義します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++


### アクション

<!--
* [Convert object](#convert-object) 
* [Create a record (attaching custom forms)](#create-a-record-attaching-custom-forms) 
* [Create a record](#create-a-record) 
* [Custom API Call](#custom-api-call) 
* [Delete Record](#delete-record) 
* [Download Document](#download-document) 
* [Misc Action](#misc-action) 
* [Read a Record](#read-a-record) 
* [Update Record](#update-record) 
* [Upload Document](#upload-document)
-->

+++ **[!UICONTROL オブジェクトの変換]**

このアクションモジュールは、次のいずれかの変換を行います。

* イシューをプロジェクトに変換
* イシューをタスクに変換
* タスクをプロジェクトに変換

>[!NOTE]
>
>2024 年 7 月から、オブジェクトの変換時にカスタムフォームを含めることができます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Object type]</td> 
   <td> <p>変換するオブジェクトのタイプを選択します。これは、変換前のオブジェクトのタイプです。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Convert to]</td> 
   <td>変換先のオブジェクトを選択します。これは、変換後のオブジェクトのタイプです。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL &lt;Object&gt; ID]</td> 
   <td> <p>オブジェクトの ID を入力します。 </p> <p>メモ：オブジェクトの ID を入力する場合は、オブジェクトの名前を入力していき、目的のオブジェクトがリストに表示されたら、それを選択します。そうすると、モジュールが適切な ID をフィールドに入力します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Template ID]</td> 
   <td> <p>プロジェクトに変換する場合は、プロジェクトに使用するテンプレートの ID を選択します。</p> <p>メモ：オブジェクトの ID を入力する場合は、オブジェクトの名前を入力していき、目的のオブジェクトがリストに表示されたら、それを選択します。そうすると、モジュールが適切な ID をフィールドに入力します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Custom forms]</td> 
   <td>新しく変換されたオブジェクトに追加するカスタムフォームを選択し、カスタムフォームのフィールドに値を入力します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Options]</td> 
   <td> <p>オブジェクトの変換時に必要なオプションを有効にします。変換先または変換元のオブジェクトに応じて、オプションを使用できます。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ネイティブ フィールドのコピー &#x200B;]</td> 
   <td> <p>このオプションを有効にすると、元のオブジェクトから新しいオブジェクトにネイティブフィールドがコピーされます。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL カスタム フォームのコピー &#x200B;]</td> 
   <td> <p>このオプションを有効にすると、元のオブジェクトから新しいオブジェクトにネイティブフィールドがコピーされます。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL レコードを作成]**

このアクションモジュールは、Workfrontのプロジェクト、タスク、イシューなどのオブジェクトを作成し、新しいオブジェクトにカスタムフォームを追加できます。 モジュールを使用すると、モジュールで使用可能なオブジェクトのフィールドを選択できます。

レコードの ID を指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

入力フィールドの最小数を指定してください。例えば、イシューを作成する場合は、「プロジェクト ID」フィールドに有効な親プロジェクト ID を指定して、Workfront でイシューの配置先を示す必要があります。マッピングパネルを使用してシナリオ内の別のモジュールからこの情報をマッピングするか、名前を入力してリストから選択し、手動で入力することもできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで作成するWorkfront レコードのタイプを選択します。</p> <p>例えば、プロジェクトを作成する場合は、ドロップダウンリストから「[!UICONTROL プロジェクト &#x200B;]」を選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td> <p>データ入力に使用するフィールドを選択します。これにより、不要なフィールドをスクロールしなくても、これらのフィールドを使用できます。 その後、これらのフィールドにデータを入力またはマッピングできます。</p> <p>カスタムフォームのフィールドの場合は、「<b>[!UICONTROL Attach Custom Form]</b>」フィールドを使用します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Attach Custom Form]</td> 
   <td>新しいオブジェクトに追加するカスタムフォームを選択し、これらのフィールドの値を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

>[!NOTE]
>
>* オブジェクトの ID を入力する際に、オブジェクトの名前を入力し、リストから選択できます。そうすると、モジュールが適切な ID をフィールドに入力します。
>* カスタムフィールドまたは[!UICONTROL メモ]オブジェクト（コメントまたは返信）にテキストを入力する際、「[!UICONTROL メモテキスト]」フィールドで HTML タグを使用して、太字や斜体などのリッチテキストを作成できます。
>

+++

+++ **[!UICONTROL レコードを作成（レガシー）]**

>[!IMPORTANT]
>
>このモジュールは、レコードを作成モジュールに置き換えられました。 新しいシナリオでは、そのモジュールを使用することをお勧めします。
>このモジュールを使用する既存のシナリオは、引き続き期待どおりに機能します。 このモジュールは、2025 年 5 月にモジュールセレクターから削除されます。

このアクションモジュールは、Workfront でプロジェクト、タスク、イシューなどのオブジェクトを作成します。モジュールを使用すると、モジュールで使用可能なオブジェクトのフィールドを選択できます。

レコードの ID を指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

入力フィールドの最小数を指定してください。例えば、イシューを作成する場合は、「プロジェクト ID」フィールドに有効な親プロジェクト ID を指定して、Workfront でイシューの配置先を示す必要があります。マッピングパネルを使用してシナリオ内の別のモジュールからこの情報をマッピングするか、名前を入力してリストから選択し、手動で入力することもできます。

このモジュールでは、オブジェクトを作成する際にカスタムフォームを添付しません。 オブジェクトの作成時にカスタムフォームを添付するには、[!UICONTROL &#x200B; レコードの作成（カスタムフォームの添付） &#x200B;] モジュールを使用します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで作成するWorkfront レコードのタイプを選択します。</p> <p>例えば、プロジェクトを作成する場合は、ドロップダウンリストから「[!UICONTROL プロジェクト &#x200B;]」を選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td>データ入力に使用するフィールドを選択します。これにより、不要なフィールドをスクロールしなくても、これらのフィールドを使用できます。</td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

>[!NOTE]
>
>* オブジェクトの ID を入力する際に、オブジェクトの名前を入力し、リストから選択できます。そうすると、モジュールが適切な ID をフィールドに入力します。
>* カスタムフィールドまたは[!UICONTROL メモ]オブジェクト（コメントまたは返信）にテキストを入力する際、「[!UICONTROL メモテキスト]」フィールドで HTML タグを使用して、太字や斜体などのリッチテキストを作成できます。

+++

+++ **[!UICONTROL カスタム API 呼び出し]**

このアクションモジュールを使用すると、Workfront API に対してカスタム認証呼び出しを行うことができます。 これにより、他のWorkfront モジュールでは実現できないデータフローの自動処理を作成できます。

このモジュールは、次の情報を返します。

* **[!UICONTROL ステータスコード]**（数値）：HTTP リクエストの成功または失敗を示します。これらはインターネット上で検索できる標準コードです。
* **[!UICONTROL ヘッダー]**（オブジェクト）：出力本文に関連しない応答／ステータスコードのより詳細なコンテキスト。応答ヘッダーに表示されるすべてのヘッダーが応答ヘッダーではないので、不要なヘッダーも含まれている可能性があります。

  応答ヘッダーは、モジュールの設定時に選択した HTTP リクエストによって異なります。

* **[!UICONTROL 本文]**（オブジェクト）：モジュールの設定時に選択した HTTP リクエストによっては、データの一部を受け取る場合があります。GET リクエストからのデータなどは、このオブジェクトに含まれます。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p><code> https://&lt;WORKFRONT_DOMAIN&gt;/attask/api/&lt;API_VERSION&gt;/</code> への相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>モジュールで使用するWorkfront API のバージョンを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion の HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。これにより、リクエストのコンテンツタイプが決まります。</p> <p>例：<code> {"Content-type":"application/json"}</code></p> <p>メモ：エラーが発生し、接触チャネルを特定するのが難しい場合は、Workfrontのドキュメントに基づいてヘッダーを変更することを検討してください。 カスタム API 呼び出しで 422 HTTP リクエストエラーが返される場合は、<code>"Content-Type":"text/plain"</code> ヘッダーを使用してみてください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> <p>ヒント：情報は、クエリパラメーターではなく、JSON 本文を使用して送信することをお勧めします。</p> </td> 
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

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **[!UICONTROL レコードを削除]**

このアクションモジュールは、Workfront のプロジェクト、タスクまたはイシューなどのオブジェクトを削除します。

レコードの ID を指定します。

このモジュールは、レコードの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Force delete]</td> 
   <td>このオプションを有効にすると、Workfront UI から削除の確認がリクエストされる場合でも、レコードが確実に削除されます。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 非同期削除 &#x200B;]</td> 
   <td>モジュールを非同期で削除できるようにするには、このオプションを有効にします。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>ID</td> 
   <td> <p>モジュールから削除するレコードの一意のWorkfront ID を入力します。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td>モジュールから削除するWorkfront レコードのタイプを選択します。</td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

>[!NOTE]
>
>操作が同期されずにレコードが削除されない可能性を回避するために、次のシナリオ設定をお勧めします。
>
>1. レコードを同期的に削除します。
>1. レコード削除モジュールにエラー処理を追加し、40 秒のタイムアウトによるエラーを無視します。


+++

+++ **[!UICONTROL ドキュメントのダウンロード]**

このアクションモジュールは、Workfront からドキュメントをダウンロードします。

レコードの ID を指定します。

このモジュールは、ドキュメントの内容、ファイル名、ファイル拡張子、ファイルサイズを返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Document ID]</td> 
   <td> <p>モジュールをダウンロードするドキュメントの一意のWorkfront ID をマッピングするか、手動で入力します。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **[!UICONTROL その他のアクション]**

このアクションモジュールを使用すると、API に対してアクションを実行できます。

>[!NOTE]
>
>2024 年 7 月現在、`convertToProject` のアクションにはフィールド `copyCategories` が含まれています。 `TRUE` に設定すると、すべてのカスタムフォームは、イシューが変換されるプロジェクトに含まれます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>モジュールでやり取りするWorkfront レコードのタイプを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Action]</td> 
   <td> <p>モジュールで実行するアクションを選択します。</p> <p>選択した [!UICONTROL Record Type] と [!UICONTROL Action] に応じて、追加のフィールドに入力する必要がある場合があります。この 2 つの設定の組み合わせによっては、レコード ID しか必要ないものもあれば、追加情報（オブジェクト ID やテンプレート ID など）を必要とするもの（<strong>[!UICONTROL Record Type]</strong> のプロジェクトや <strong>[!UICONTROL Action]</strong> の [!UICONTROL Attach Template] など）もあります。</p><p>一部のアクションで使用できるオプションについては、この記事の <a href="#misc-action-options" class="MCXref xref"> その他のアクションオプション </a> を参照してください。</p> <p>個々のフィールドについて詳しくは、<a href="http://developer.workfront.com/">Workfront 開発者ドキュメント</a>を参照してください。 <p><strong>メモ</strong>：開発者ドキュメントサイトには、API バージョン 14 を通じた情報のみが含まれていますが、API 呼び出しに関する有用な情報がまだ含まれています。 </p> 
    <ol> 
     <li value="1"> <p>Workfront開発者ドキュメントページの左側のナビゲーションからレコードタイプを選択します。 以下のタイプには、独自のページがあります。</p> 
      <ul> 
       <li> <p>[!UICONTROL Projects]</p> </li> 
       <li> <p>[!UICONTROL Tasks]</p> </li> 
       <li> <p>[!UICONTROL Issues]</p> </li> 
       <li> <p>[!UICONTROL Users]</p> </li> 
       <li> <p>[!UICONTROL Documents]</p> </li> 
      </ul> <p>その他のすべてのレコードタイプに対して、<b>[!UICONTROL Other objects and endpoints]</b> を選択し、アルファベット順に並べ替えられたページでレコードタイプを探します。</p> </li> 
     <li value="2"> <p>適切なレコードタイプのページで、アクションを検索（Ctrl + F キーまたは Command + F キー）します。</p> </li> 
     <li value="3"> <p>選択したアクションで使用可能なフィールドの説明を表示します。</p> </li> 
    </ol> <p>メモ：  <p>Workfront [!UICONTROL その他アクション &#x200B;] モジュールを使用してプルーフを作成する場合、ベストプラクティスは、詳細なオプションを使用せずにプルーフを作成し、[!DNL Workfront Proof] SOAP API を使用してプルーフを更新することです。</p><p>Workfront API （このモジュールが使用）を使用したプルーフの作成について詳しくは、<a href="https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/tips-troubleshooting-apis/api-create-proof-options-json" class="MCXref xref">Adobe Workfront API でプルーフを作成する際の詳細プルーフオプションの追加 </a> を参照してください</p> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td>モジュールでやり取りするレコードの一意のWorkfront ID を入力またはマッピングします。<p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p></td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

#### その他のアクションオプション

##### タスク

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>アクション</th> 
   <th>オプション</th> 
  </tr> 
  <tr> 
   <td>コピー</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearConstraints</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>財務データを消去します</p></li>
   <li>clearPermission</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>リマインダ通知をクリアします</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>移動</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearDocuments</li>
   <li>clearConstraints</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>財務データを消去します</p></li>
   <li>clearPermission</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>リマインダ通知をクリアします</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

##### イシュー

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>アクション</th> 
   <th>オプション</th> 
  </tr> 
  <tr> 
   <td>コピー</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearPermission</li>
   <li>clearProgress</li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>タスクに変換</td> 
   <td>
   <ul>
   <li>preserveIssue<p>元の問題を保持し、その解決策をこのタスクに関連付ける</p></li>
   <li>preservePrimaryContact<p>問題のプライマリ連絡先にこのタスクへのアクセスを許可する</p></li>
   <li>preserveCompletionDate<p>問題の予定完了日を変更しない</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>プロジェクトに変換</td> 
   <td>
   <ul>
   <li>preserveIssue<p>元の問題を保持し、その解決策をこのタスクに関連付ける</p></li>
   <li>preservePrimaryContact<p>問題のプライマリ連絡先にこのタスクへのアクセスを許可する</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



##### プロジェクト

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>アクション</th> 
   <th>オプション</th> 
  </tr> 
  <tr> 
   <td>コピー</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>財務データを消去します</p></li>
   <li>clearPermission</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>リマインダ通知をクリアします</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>テンプレートを添付/テンプレートとして保存</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearBillingRates</li>
   <li>clearConstraints</li>
   <li>clearDeliverables<p>目標をクリア</p></li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>財務データを消去します</p></li>
   <li>clearHourTypes</li>
   <li>clearIssueSetup<p>キューのプロパティと問題の設定をクリアします</p></li>
   <li>clearPredecessors</li>
   <li>clearRisks</li>
   <li>clearSharingOptions</li>
   <li>clearTimedNotifications<p>リマインダ通知をクリアします</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



+++

+++ **[!UICONTROL レコードを読み取り]**

このアクションモジュールは、1 つのレコードからデータを取得します。

レコードの ID を指定します。また、モジュールで読み取る関連レコードを指定することもできます。

例えば、モジュールが読み取っているレコードがプロジェクトの場合、プロジェクトのタスクを読み込むように指定できます。

モジュールは、指定した出力フィールドからデータの配列を返します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>

<td>モジュールで読み取るWorkfront オブジェクトタイプを選択します。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>

<td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 出力のカスタム フォーム &#x200B;]</td>
     <td> <p>このモジュールの出力バンドルに含めるカスタムフォームを選択し、出力に含めるカスタムフォームから特定のフィールドを選択します。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>出力に含める参照フィールドを選択します。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>出力に含める参照フィールドを選択します。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>モジュールで読み取るレコードの一意のWorkfront ID を入力します。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **[!UICONTROL レコードの読み取り（レガシー）]**

>[!IMPORTANT]
>
>このモジュールは、レコードを読み取りモジュールに置き換えられました。 新しいシナリオでは、そのモジュールを使用することをお勧めします。
>このモジュールを使用する既存のシナリオは、引き続き期待どおりに機能します。 このモジュールは、2025 年 5 月にモジュールセレクターから削除されます。

このアクションモジュールは、1 つのレコードからデータを取得します。

レコードの ID を指定します。また、モジュールで読み取る関連レコードを指定することもできます。

例えば、モジュールが読み取っているレコードがプロジェクトの場合、プロジェクトのタスクを読み込むように指定できます。

モジュールは、指定した出力フィールドからデータの配列を返します。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>

<td>モジュールで読み取るWorkfront オブジェクトタイプを選択します。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>

<td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>出力に含める参照フィールドを選択します。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>出力に含める参照フィールドを選択します。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>モジュールで読み取るレコードの一意のWorkfront ID を入力します。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **イベントペイロードのバージョンを更新**

Workfrontは最近、イベント購読サービスの新しいバージョンをリリースしました。 新しいバージョンはWorkfront API に対する変更ではなく、イベント購読機能に対する変更です。 このアクションモジュールは、このシナリオで使用されるイベントペイロードのバージョンを更新します。

新しいイベント購読のバージョンについて詳しくは、Workfront ドキュメントの [ イベント購読のバージョン管理 ](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning) を参照してください

ウェビナーの録画など、イベント購読のアップグレード中にWorkfront Fusion シナリオを保持する方法については、[ イベント購読 V2 のアップグレード中に Fusion シナリオを保持する ](https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182) を参照してください。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Version]</td> 
   <td> このペイロードに使用するイベント購読のバージョンを選択します。 </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **レコードを更新**


このアクションモジュールは、プロジェクト、タスク、イシューなどのオブジェクトを更新します。モジュールを使用すると、モジュールで使用可能なオブジェクトのフィールドを選択できます。

レコードの ID を指定します。

このモジュールは、オブジェクトの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>モジュールで更新するレコードの一意のWorkfront ID を入力します。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>モジュールで更新するWorkfront レコードのタイプを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>データ入力に使用するフィールドを選択します。これにより、不要なフィールドをスクロールしなくても、これらのフィールドを使用できます。 その後、これらのフィールドにデータを入力またはマッピングできます。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Attach Custom Form]</td> 
   <td>新しいレコードのフィールド値を指定するカスタムフォームを選択します。 フォームを選択したら、そのフォーム上のフィールドのデータを入力します。<p> このモジュールに添付するフォームのフィールド値を指定するには、「マッピングするフィールド」セクションにカスタムフォーム ID を含めます。</td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

>[!NOTE]
>
> カスタムフィールドまたは[!UICONTROL メモ]オブジェクト（コメントまたは返信）にテキストを入力する際、「[!UICONTROL メモテキスト]」フィールドで HTML タグを使用して、太字や斜体などのリッチテキストを作成できます。


+++

+++ **[!UICONTROL レコードを更新（レガシー）]**

>[!IMPORTANT]
>
>このモジュールは、レコードを更新モジュールに置き換えられました。 新しいシナリオでは、そのモジュールを使用することをお勧めします。
>このモジュールを使用する既存のシナリオは、引き続き期待どおりに機能します。 このモジュールは、2025 年 5 月にモジュールセレクターから削除されます。

このアクションモジュールは、プロジェクト、タスク、イシューなどのオブジェクトを更新します。モジュールを使用すると、モジュールで使用可能なオブジェクトのフィールドを選択できます。

レコードの ID を指定します。

このモジュールは、オブジェクトの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>モジュールで更新するレコードの一意のWorkfront ID を入力します。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>モジュールで更新するWorkfront レコードのタイプを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>データ入力に使用するフィールドを選択します。これにより、不要なフィールドをスクロールしなくても、これらのフィールドを使用できます。 その後、これらのフィールドにデータを入力またはマッピングできます。</td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

>[!NOTE]
>
>* オブジェクトの ID を入力する際に、オブジェクトの名前を入力し、リストから選択できます。そうすると、モジュールが適切な ID をフィールドに入力します。
>* カスタムフィールドまたは[!UICONTROL メモ]オブジェクト（コメントまたは返信）にテキストを入力する際、「[!UICONTROL メモテキスト]」フィールドで HTML タグを使用して、太字や斜体などのリッチテキストを作成できます。

+++

+++ **[!UICONTROL ドキュメントをアップロード]**

このアクションモジュールは、プロジェクト、タスク、イシューなどのWorkfront オブジェクトにドキュメントをアップロードします。 このモジュールは、ドキュメントをチャンク単位でアップロードするので、Workfrontのアップロードプロセスがスムーズになります。

このモジュールは、従来のモジュールよりも大きなファイルを処理でき、Ultimate Workfront パッケージを使用する組織への段階的なロールアウトの一部です。

ドキュメントの場所、アップロードするファイル、およびオプションで新しいファイル名を指定します。

このモジュールは、ドキュメントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>ドキュメントをアップロードするレコードの一意のWorkfront ID を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>モジュールがドキュメントをアップロードするWorkfront レコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>関連レコードのタイプに応じて、フォルダー ID の入力またはマッピングが必要になる場合があります。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

+++ **[!UICONTROL ドキュメントのアップロード（レガシー）]**

このアクションモジュールは、プロジェクト、タスク、イシューなどのWorkfront オブジェクトにドキュメントをアップロードします。 ドキュメント全体を一度にアップロードします。

ドキュメントの場所、アップロードするファイル、およびオプションで新しいファイル名を指定します。

このモジュールは、ドキュメントの ID や関連するフィールドのほか、接続を介してアクセスされるカスタムフィールドと値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>ドキュメントをアップロードするレコードの一意のWorkfront ID を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>モジュールがドキュメントをアップロードするWorkfront レコードのタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>関連レコードのタイプに応じて、フォルダー ID の入力またはマッピングが必要になる場合があります。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

このモジュールを使用できるWorkfront オブジェクトタイプのリストについては、[ 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ ](#workfront-object-types-available-for-each-workfront-module) を参照してください。

+++

### 検索

<!--
* [Read Related Records](#read-related-records) 
* [Search](#search)
-->

+++ **[!UICONTROL 関連レコードを読み取る]**

この検索モジュールは、特定の親オブジェクト内で、指定した検索クエリに一致するレコードを読み取ります。

出力に含めるフィールドを指定します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>読み取る関連レコードの親レコード（Workfront オブジェクト）のタイプを選択します。</p> <p>この記事では、<a href="#object-types-available-for-each-workfront-search-module" class="MCXref xref"> 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ </a> で、このモジュールを使用できるWorkfront オブジェクトタイプのリストを参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Parent Record ID]</td> 
   <td> <p>読み取る関連レコードの親レコードの ID を入力またはマッピングします。</p> <p>ID を取得するには、ブラウザーでWorkfront オブジェクトを開き、URL の末尾にある「ID=」の後のテキストをコピーします。 例：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>モジュールが読み取る子レコードのタイプを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 検索]**

この検索モジュールは、指定した検索クエリに一致するWorkfront内のオブジェクト内のレコードを検索します。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで検索するWorkfront レコードのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL カスタム フォーム リスト &#x200B;]</td> 
   <td> <p>1 つ以上のカスタムフォームを選択します。 これらのカスタムフォームのフィールドは、検索クエリで使用できるようになります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>モジュールが検索条件に一致する最初の結果を取得するか、一致するすべての結果を取得するかを指定するオプションを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria fields]</td> 
   <td> <p>検索条件に使用するフィールドを選択します。これらのフィールドは、検索条件ドロップダウンで使用できるようになります。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>検索するフィールド、クエリで使用する演算子、およびそのフィールドで検索する値を入力します。</p> <p>メモ：検索条件に <code>username </code> を使用しないでください。Workfrontへの API クエリに <code>username </code> を含めると、ユーザーがWorkfrontにログインし、検索が成功しなくなります。</p> <p>メモ：<code>In</code> と <code>NotIn</code> は配列で動作します。入力は配列形式である必要があります。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力に含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>検索に含める参照フィールドを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>検索に追加するコレクションを選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 検索（レガシー）]**

>[!IMPORTANT]
>
>このモジュールは、レコードを検索モジュールに置き換えられました。 新しいシナリオでは、そのモジュールを使用することをお勧めします。
>このモジュールを使用する既存のシナリオは、引き続き期待どおりに機能します。 このモジュールは、2025 年 5 月にモジュールセレクターから削除されます。

この検索モジュールは、指定した検索クエリに一致するWorkfront内のオブジェクト内のレコードを検索します。

この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリケーションをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">WorkfrontをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>モジュールで検索するWorkfront レコードのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>モジュールが検索条件に一致する最初の結果を取得するか、一致するすべての結果を取得するかを指定するオプションを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria fields]</td> 
   <td> <p>検索条件に使用するフィールドを選択します。これらのフィールドは、検索条件ドロップダウンで使用できるようになります。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>検索するフィールド、クエリで使用する演算子、およびそのフィールドで検索する値を入力します。</p> <p>メモ：検索条件に <code>username </code> を使用しないでください。Workfrontへの API クエリに <code>username </code> を含めると、ユーザーがWorkfrontにログインし、検索が成功しなくなります。</p> <p>メモ：<code>In</code> と <code>NotIn</code> は配列で動作します。入力は配列形式である必要があります。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力に含めるフィールドを選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>検索に含める参照フィールドを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>検索に追加するコレクションを選択します。</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--not visible Jan 6, 2025

+++ **[!UICONTROL Search (Legacy)]**

This search module looks for records in an object in Workfront that match the search query you specify.

You can map this information in subsequent modules in the scenario.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to search for.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Select an option to specify whether you want the module to get the first result that matches your search criteria or all the results that match it.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Select the fields that you want to include in the output for this module.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Select any reference fields that you want to include in the search.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Select any collections that you want to add to the search.</td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

+++-->

## 各Workfront モジュールで使用できるWorkfront オブジェクトタイプ

<!-- [Object types available for each Workfront trigger module](#object-types-available-for-each-workfront-trigger-module) 
* [Object types available for each Workfront action module](#object-types-available-for-each-workfront-action-module) 
* [Object types available for each Workfront search module](#object-types-available-for-each-workfront-search-module)-->

+++**各Workfront トリガーモジュールで使用できるオブジェクトタイプ**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col>         
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Watch Record]</th> 
   <th>[!UICONTROL Watch Field]</th> 
   <th>[!UICONTROL Watch Events]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>承認プロセス</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>割り当て</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ベースライン</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 請求記録 </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>請求レート</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>会社</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ダッシュボード</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメント</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメントフォルダー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ドキュメントリクエスト</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ドキュメントのバージョン</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>費用タイプ</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>グループ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時間</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時間タイプ</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>イシュー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>イテレーション</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>担当業務</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ジャーナルエントリ</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>マイルストーン</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>マイルストーンパス</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>メモ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>メモタグ</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ポートフォリオ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プログラム</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プロジェクト</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プロジェクトユーザー</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>プルーフの承認</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>予約済み時間* </td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>レポート</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>リスク</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>リスクタイプ</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ステップ承認者</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>タスク</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>チーム</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>テンプレート</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>テンプレートタスク</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>タイムシート</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ユーザー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>アップデート</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**各Workfront アクションモジュールで使用できるオブジェクトタイプ**

>[!NOTE]
>
>Workfront オブジェクトタイプは設定に含まれていないので、「[!UICONTROL &#x200B; ドキュメントをダウンロード &#x200B;]」モジュールはこのテーブルに含まれていません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Create a record]</th> 
   <th>[!UICONTROL Update a record]</th> 
   <th>[!UICONTROL Delete a record]</th> 
   <th>[!UICONTROL Upload Document]</th> 
   <th>[!UICONTROL Read a record]</th> 
   <th>[!UICONTROL Custom API Call]</th> 
   <th>[!UICONTROL Misc Action]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>承認プロセス</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>割り当て</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ベースライン</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
   <tr> 
   <td>請求記録</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>請求レート</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>会社</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメント</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメントフォルダー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメントのバージョン</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>為替レート</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>費用タイプ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>外部ドキュメント</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>グループ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時間</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時間タイプ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>イシュー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>イテレーション</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>担当業務</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ジャーナルエントリ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>マイルストーン</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>マイルストーンパス</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>メモ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>メモタグ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ポートフォリオ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プログラム</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プロジェクト</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プロジェクトユーザー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>予約済み時間* </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>リスク</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>リスクタイプ</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ステップ承認者</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>タスク</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>チーム</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>テンプレート</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>テンプレートタスク</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>タイムシート</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ユーザー</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>アップデート</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**各Workfront検索モジュールで使用できるオブジェクトタイプ**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Search]</th> 
   <th>[!UICONTROL Read Related Records]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>承認プロセス</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>割り当て</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>請求記録</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>請求レート</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>会社</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメント</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメントフォルダー</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ドキュメントのバージョン</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用タイプ</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>グループ</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時間</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時間タイプ</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>イシュー</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>イテレーション</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>担当業務</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ジャーナルエントリ</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>マイルストーン</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>マイルストーンパス</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>メモ</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>メモタグ</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ポートフォリオ</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プログラム</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>プロジェクト</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>プロジェクトユーザー</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>予約済み時間* </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>リスク</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>リスクタイプ</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ステップ承認者</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>タスク</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>チーム</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>テンプレート</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>テンプレートタスク</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>タイムシート</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ユーザー</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>ユーザーの委任</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

これが期待どおりに機能することを再確認することをお勧めします。

+++

## Workfront / [!UICONTROL Watch Events] モジュールのイベント購読フィルター

>[!NOTE]
>
>* [!UICONTROL イベントの監視]モジュールでは、イベント登録フィルターを使用することを強くお勧めします。
>
>* Workfrontは最近、イベント購読サービスの新しいバージョンをリリースしました。 新しいバージョンはWorkfront API に対する変更ではなく、イベント購読機能に対する変更です。 このアクションモジュールは、このシナリオで使用されるイベントペイロードのバージョンを更新します。
>
>   新しいイベント購読のバージョンについて詳しくは、Workfront ドキュメントの [ イベント購読のバージョン管理 ](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning) を参照してください
>
>   ウェビナーの録画など、イベント購読のアップグレード中にWorkfront Fusion シナリオを保持する方法については、[ イベント購読 V2 アップグレード中の Fusion シナリオの保持（https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182） ] を参照してください。

Workfront [!UICONTROL Watch Events] モジュールは、Workfront API でイベント購読を作成する Webhook に基づくシナリオをトリガーします。 イベント登録は、web フックに送信されるイベントを決定する一連のデータです。例えば、イシューを監視する[!UICONTROL イベントの監視]モジュールを設定した場合、イベント登録はイシューに関連するイベントのみを送信します。

Fusion ユーザーは、イベント登録フィルターを使用して、ユースケースに適したイベント登録を作成できます。例えば、Workfront API でイベント購読を設定して、特定のプロジェクトの問題のみを Webhook に送信し、「[!UICONTROL &#x200B; イベントをウォッチ &#x200B;]」モジュールでそのプロジェクトの問題のみをトリガーできるようにします。 より範囲の狭いトリガーを作成できるので、無関係なトリガーの数が減り、シナリオの設計を改善できます。

これは、Workfront Fusion シナリオでフィルターを設定する場合とは異なります。 イベント登録フィルターを使用しない場合、web フックは、選択されたオブジェクトタイプに関連するすべてのイベントを受信します。これらのイベントのほとんどはシナリオとは無関係と思われるので、シナリオを続行する前に除外する必要があります。

Workfront／イベントの監視フィルターで使用できる演算子は、次のとおりです。

* が次と等しい
* 等しくない
* より大きい
* より小さい
* が次よりも大きいか等しい
* が次よりも小さいか等しい
* が次を含む
* 存在する
   * この演算子には値は必要ありません。また、値フィールドは存在しません。
* が存在しません
   * この演算子には値は必要ありません。また、値フィールドは存在しません。
* 変更済み
   * この演算子には値は必要ありません。また、値フィールドは存在しません。
   * この演算子では、「状態」フィールドを無視します。
   * `Changed` を使用する際は、「**レコード元**」フィールドで「**更新されたイベントのみ**」を選択します。

>[!IMPORTANT]
>
>既存のWorkfront Webhook ではフィルターを編集できません。 Workfront イベント購読用に異なるフィルターを設定するには、現在の Webhook を削除して、新しい Webhook を作成します。

>[!INFO]
>
>**例：** 特定のユーザー Ana に割り当てられた新規イシューを処理するシナリオについて考えます。
>
>### イベント登録フィルターを使用したイベントのフィルタリング（推奨）
>
>イベントフィルターを使用すると、イシューが Ana に割り当てられている場合のシナリオをイシューの作成時にトリガーする web フックを設定できます。Ana の ユーザー IDは、b378489d8f7cd3cee0539260720a84b7 です。
>
>![ イベントフィルター ](/help/workfront-fusion/references/apps-and-modules/assets/event-filter-watch-events-350x277.png)
>
>1 日に 100 件のイシューが作成され、そのうち 2 件のみが Ana に割り当てられている場合、シナリオは 2 回実行されます。
>
>### シナリオ内でのイベントのフィルタリング（非推奨）
>
>Ana に割り当てられたイシューのみを処理するようにイベントをフィルタリングするには、[!UICONTROL イベントを監視]モジュールの後にフィルターを作成できます。
>
>![ イベントフィルターなし ](/help/workfront-fusion/references/apps-and-modules/assets/watch-events-non-event-filter-350x206.png)
>
>1 日に 100 件のイシューが作成され、そのうち 2 件のみが Ana に割り当てられている場合、シナリオは 100 回実行されます。98 回の実行はフィルターで停止しますが、トリガーモジュールは引き続きデータを消費し、すべての実行で操作が実行されます。

Workfront イベント購読について詳しくは、[FAQ - イベント購読 ](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-faq) を参照してください。

Webhook について詳しくは、「Adobe Workfront Fusion の [ インスタントトリガー（Webhook）」を参照してください ](/help/workfront-fusion/references/modules/webhooks-reference.md)

シナリオのフィルターについて詳しくは、[ シナリオへのフィルターの追加 ](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md) を参照してください。
