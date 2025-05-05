---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe ストレージモジュール
description: シナリオでは、Adobe Admin Console [!DNL Adobe Workfront Fusion]  プロジェクトを作成および管理できます。
author: Becky
feature: Workfront Fusion
exl-id: 78ee905f-4713-44a4-bffb-c64cdb3665c2
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 19%

---

# Adobe ストレージモジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、Adobe Admin Consoleでプロジェクトを作成および管理できます。

シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

## Adobe ストレージへの接続の作成

Adobe ストレージへの接続を作成するには、Adobe Developer Consoleと Fusion で何らかの設定が必要です。

### Adobe Developer Consoleでのプロジェクトの設定

Adobe Developer Consoleで API をプロジェクトに追加する必要があります。

1. Adobe Developer Consoleでプロジェクトを開きます。
1. 「**プロジェクトに追加**」をクリックし、「**API**」を選択します。
1. 使用可能な API のリストから、「**Adobe Cloud Platform とCollaboration API**」を選択します。
1. 認証タイプを選択画面で「**OAuth サーバー間**」を選択し、「**次へ**」をクリックします。
1. 資格情報の名前を追加します。
1. 「**次へ**」をクリックし、「**設定済み API を保存**」をクリックします。
1. 提供された資格情報をメモします。この資格情報は、Workfront Fusion で接続を設定する際に使用します。
1. [ テクニカルアカウントをAdobe Admin Consoleの管理者に設定 ](#make-your-technical-account-an-admin-in-the-adobe-admin-console) に進みます。

### テクニカルアカウントをAdobe Admin Consoleの管理者にします

Adobe Admin Consoleページで、上部のナビゲーションバーの「製品」タブを選択し、「Workfront Fusion」を選択します。

1. を見つけて、組織のテクニカルアカウントユーザーのメールアドレスをコピーします。
1. リストが表示された場合は、上部のリンクを選択します。
1. これは、ユーザーが作業する実稼動インスタンスです。
1. 表示されるリストで、「製品プロファイル」タブを選択し、Workfront製品プロファイル リンクの名前をクリックします。

   このリストには、Workfront の実稼動インスタンスに既に割り当てられているすべてのユーザーが含まれます。

1. ユーザーのリストの上にある「**管理者**」タブを選択します。
1. **管理者の追加**&#x200B;を選択します。
1. 「製品プロファイル管理者を追加」ボックスに、テクニカルアカウントのメールアドレスを入力し、「**保存**」を選択します。

   テクニカルアカウントは管理者になります。

1. [Workfront Fusion での接続の作成 ](#create-the-connection-in-workfront-fusion) を続行します。

### Workfront Fusion での接続の作成

[!DNL Adobe Storage] モジュールへの接続を作成するには、以下を実行します。

1. 任意のモジュールで、「接続」ボックスの横にある **[!UICONTROL 追加]** をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>「<code>Server to server</code>」を選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
        </tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Adobe] [!UICONTROL クライアント ID] を入力します。 これは、[!DNL Adobe Developer Console] のプロジェクトの [!UICONTROL 資格情報の詳細 &#x200B;] セクションにあります。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、[!DNL Adobe Developer Console] のプロジェクトの [!UICONTROL 資格情報の詳細 &#x200B;] セクションにあります。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS 組織 ID]</td>
        <td>Adobe IMS組織 ID を入力またはマッピングします。 これは <code> 123abc@AdobeOrg</code> という形式の文字列で、@の前のセクションは 16 進数です。 この値は、Adobe Admin Consoleまたは User Management 統合用のAdobe.IO コンソールで、組織の URL パスの一部として見つけることができます。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## Adobe ストレージモジュールとそのフィールド

Adobe User Management モジュールを設定する場合、Workfront Fusion は以下に示すフィールドを表示します。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のAdobe User Management フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ESM ストア](#esm-stores)
* [招待状](#invitations)
* [その他](#other)

### ESM ストア

* [ESM ストアの作成](#create-an-esm-store)
* [ESM ストアの削除](#delete-an-esm-store)
* [ESM ストアを破棄する](#discard-an-esm-store)
* [ESM ストアのリストア](#restore-an-esm-store)

#### ESM ストアの作成

このアクション・モジュールは、ビジネス・クリティカルなアセットを整理および管理するための新しい ESM （エンタープライズ・ストレージ管理）ストアを設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロジェクト名</td> 
   <td>新しいプロジェクトの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ESM ストアの削除

このアクション モジュールは、既存の ESM ストアと、それに関連するすべてのデータを完全に削除します。 この操作は元に戻すことができません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストア ID</td> 
   <td>削除するストアの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ESM ストアを破棄する

このアクション・モジュールは、EMS ストアを削除の対象としてマークし、永続的な削除の前に猶予期間を設けることができます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストア ID</td> 
   <td>破棄するストアの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ESM ストアのリストア

このアクション・モジュールは、以前に削除された ESM ストアをリカバリし、そのデータと構成へのアクセスをリストアします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストア ID</td> 
   <td>復元するストアの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### 招待状

#### ユーザーを招待

このアクション・モジュールは、特定の ESM ストアへの新しいユーザー・アクセス権を付与する招待状を送信し、コラボレーションとファイル管理を可能にします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メールアドレス</td> 
   <td>ストアに招待するユーザーのメールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td>ユーザーを招待するアセットの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">役割</td> 
   <td>新しく招待されたユーザーに割り当てるアセットの役割を選択します。<ul><li>所有者</li><li>編集者</li><li>ビューア</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">コメントできます</td> 
   <td>このオプションを有効にすると、ユーザーがアセットにコメントできるようになります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">共有可能</td> 
   <td>ユーザーが他のユーザーとアセットを共有できるようにするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">承諾が必要です</td> 
   <td>ユーザーがアセットに関する共同作業を行う前に招待を受け入れる必要がある場合は、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">マウントを使用</td> 
   <td>招待者に対してリソースへのマウントポイントを作成する必要がある場合は、このオプションを有効にします。 このオプションを有効にするには、「許可が必要」オプションを有効にする必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">通知タイプ</td> 
   <td>招待状についてユーザーに通知するために使用するAdobe通知タイプを入力またはマッピングします。 これを空のままにすると、通知タイプはアセットの mimetype に基づきます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">テンプレート名</td> 
   <td>招待メールに使用するテンプレートの Adobe 郵便局 ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ロケール</td> 
   <td>ユーザーのロケールを言語コードおよび国コードの形式で入力します。 <p>例： <code>en-us</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">外部</td> 
   <td>Adobe Invitations Service の外部システムを使用して通知を送信する場合は、このオプションを true に設定します。 外部通知は、受け入れが不要な場合にのみサポートされます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセットタイプ</td> 
   <td>アセットのタイプを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メッセージ</td> 
   <td>招待メールに含めるメッセージを入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ターゲット URL</td> 
   <td>招待者がアセットを表示するために使用できる URL を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### その他

#### カスタム API 呼び出しの実行

このアクションモジュールは、Adobe ストレージ API に対してカスタム HTTP リクエストを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
   <td>Adobe ストレージへの接続を作成する方法については、この記事の <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成 </a> を参照してください。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>相対パスを入力します <code>https://ccprojects.adobe.io/api/v3/.</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>メソッド</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">ヘッダー</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] 認証ヘッダーおよび x-api-key ヘッダーを自動的に追加します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">クエリ文字列  </td>
      <td>
        <p>リクエストクエリ文字列を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">本文</td>
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>
