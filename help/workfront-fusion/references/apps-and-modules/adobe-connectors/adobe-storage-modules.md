---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe Storage モジュール
description: Adobe Workfront Fusion シナリオでは、Adobe Admin Consoleでプロジェクトを作成および管理できます。
author: Becky
feature: Workfront Fusion
exl-id: 78ee905f-4713-44a4-bffb-c64cdb3665c2
TQID: https://experienceleague.adobe.com/sp6gMeEhVxN0QjviLXm9GnI7NSLEp93PnSQkH45zHXI
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1413
ht-degree: 29%

---

# Adobe Storage モジュール

Adobe Workfront Fusionでは、Adobe Admin Consoleでプロジェクトを作成および管理できます。

シナリオの作成手順が必要な場合は、[ シナリオの作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

モジュールについて詳しくは、[モジュール：記事インデックス](/help/workfront-fusion/references/modules/modules-toc.md)の記事を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意の Adobe Workfront Workflow パッケージと任意の Adobe Workfront Automation および Integration パッケージ</p><p>Workfront Ultimate</p><p>Workfront Fusion を追加購入した Workfront Prime および Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>Work またはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## Adobe Storageへの接続の作成

Adobe Storageへの接続を作成するには、FusionだけでなくAdobe Developer Consoleでも設定が必要です。

### Adobe Developer Consoleでのプロジェクトの設定

Adobe Developer ConsoleでプロジェクトにAPIを追加する必要があります。

1. Adobe Developer Consoleでプロジェクトを開きます。
1. 「**プロジェクトに追加**」をクリックし、**API**&#x200B;を選択します。
1. 使用可能なAPIのリストから、**Adobe Cloud PlatformとCollaboration API**&#x200B;を選択します。
1. 認証タイプの選択画面で、**OAuth サーバー間**&#x200B;を選択し、**次へ**&#x200B;をクリックします。
1. 資格情報の名前を追加します。
1. 「**次へ**」をクリックし、「**設定済みAPIを保存**」をクリックします。
1. Workfront Fusionで接続を設定する際に使用する、指定された資格情報を書き留めます。
1. 引き続き[Adobe Admin Consoleでテクニカルアカウントを管理者に設定](#make-your-technical-account-an-admin-in-the-adobe-admin-console)します。

### Adobe Admin Consoleでテクニカルアカウントを管理者にする

Adobe Admin Console ページで、上部のナビゲーションバーの「製品」タブを選択し、「Workfront Fusion」を選択します

1. 組織内のテクニカルアカウントユーザーのメールアドレスを探してコピーします。
1. リストが表示されたら、上部のリンクを選択します。
1. これは、ユーザーが作業する実稼動インスタンスです。
1. 表示されるリストで、「製品プロファイル」タブを選択し、Workfront製品プロファイルリンクの名前をクリックします。

   このリストには、Workfront の実稼動インスタンスに既に割り当てられているすべてのユーザーが含まれます。

1. ユーザーのリストの上にある「**管理者**」タブを選択します。
1. **管理者の追加**&#x200B;を選択します。
1. 製品プロファイル管理者を追加ボックスで、テクニカルアカウントのメールアドレスを入力し、**保存**&#x200B;を選択します。

   テクニカルアカウントが管理者になります。

1. 引き続き[Workfront Fusion](#create-the-connection-in-workfront-fusion)で接続を作成します。

### Workfront Fusionでコネクションを作成する

[!DNL Adobe Storage] モジュールへの接続を作成するには、以下を実行します。

1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

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
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID]を入力します。 これは、[!DNL Adobe Developer Console]のプロジェクトの[!UICONTROL資格情報の詳細] セクションにあります。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、[!DNL Adobe Developer Console]のプロジェクトの[!UICONTROL資格情報の詳細] セクションにあります。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS組織ID]</td>
        <td>Adobe IMS組織IDを入力するか、マッピングします。 これは形式<code> 123abc@AdobeOrg</code>の文字列で、@の前のセクションは16進数です。 この値は、Adobe Admin Consoleの組織のURL パスの一部として、またはユーザー管理の統合用のAdobe.IO コンソールで見つけることができます。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## Adobe ストレージモジュールとそのフィールド

Adobe User Management モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Adobe User Managementの追加フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ESM ストア](#esm-stores)
* [招待状](#invitations)
* [その他](#other)

### ESM ストア

* [ESM ストアの作成](#create-an-esm-store)
* [ESM ストアの削除](#delete-an-esm-store)
* [ESM ストアの破棄](#discard-an-esm-store)
* [ESM ストアの復元](#restore-an-esm-store)

#### ESM ストアの作成

このアクションモジュールでは、ビジネスに不可欠なアセットを整理および管理するために、新しいエンタープライズストレージ管理（ESM）ストアを設定します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロジェクト名</td> 
   <td>新しいプロジェクトの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ESM ストアの削除

このアクションモジュールは、既存のESM ストアとそれに関連するすべてのデータを完全に削除します。 このアクションは取り消せません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストア ID</td> 
   <td>削除するストアのIDを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ESM ストアの破棄

このアクションモジュールは、EMS ストアの削除をマークし、恒久的な削除の前に猶予期間を許可します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストア ID</td> 
   <td>破棄するストアのIDを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ESM ストアの復元

このアクションモジュールは、以前に削除されたESM ストアを復元し、そのデータと設定へのアクセスを復元します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ストア ID</td> 
   <td>復元するストアのIDを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### 招待状

#### ユーザーを招待

このアクションモジュールは、招待を送信して、特定のESM ストアへの新しいユーザーのアクセス権を付与し、コラボレーションとファイル管理を有効にします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe ストレージへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メールアドレス</td> 
   <td>ストアに招待するユーザーの電子メールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td>ユーザーを招待するアセットのIDを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">役割</td> 
   <td>新しく招待されたユーザーがアセットに対して持つ役割を選択します。<ul><li>所有者</li><li>編集者</li><li>ビューア</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">コメントできます</td> 
   <td>ユーザーがアセットにコメントできるようにするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">共有可能</td> 
   <td>ユーザーがアセットを他のユーザーと共有できるようにするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">同意が必要</td> 
   <td>このオプションを有効にすると、ユーザーがアセットで共同作業を行う前に招待を承諾する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">マウントの使用</td> 
   <td>このオプションを有効にすると、リソースへのマウントポイントを招待者に対して作成する必要があります。 このオプションを有効にするには、「同意が必要」オプションを有効にする必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">通知タイプ</td> 
   <td>招待についてユーザーに通知するために使用するAdobe通知タイプを入力またはマッピングします。 これが空のままの場合、通知タイプはアセットのmimetypeに基づきます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">テンプレート名</td> 
   <td>招待メールに使用するテンプレートのAdobe Post Office IDを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ロケール</td> 
   <td>言語コードと国コードの形式でユーザーのロケールを入力します。 <p>例： <code>en-us</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">外部</td> 
   <td>Adobe Invitations Serviceの外部システムを使用して通知を送信する場合は、このオプションをtrueに設定します。 外部通知は、承認が不要な場合にのみサポートされます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセットタイプ</td> 
   <td>アセットのタイプを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メッセージ</td> 
   <td>招待メールに含めるメッセージを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ターゲット URL</td> 
   <td>招待者がアセットの表示に使用できるURLを入力するか、マッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### その他

#### カスタム API 呼び出しの実行

このアクションモジュールは、Adobe Storage APIに対してカスタム HTTP リクエストを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
   <td>Adobe ストレージへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Adobe ストレージへの接続の作成</a>」を参照してください。</td> 
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
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">ヘッダー</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は、認証ヘッダーと x-api-key ヘッダーを自動的に追加します。</p>
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
