---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe User Management モジュール
description: シナリオ  [!DNL Adobe Workfront Fusion]  は、Adobeアカウントのユーザーを管理するワークフローを自動化できます。
author: Becky
feature: Workfront Fusion
exl-id: e8fe8ec4-4b00-4c9a-81a5-acb2039b153b
source-git-commit: 640fec2de63ad59ba89fae5373f85b8147d8dac0
workflow-type: tm+mt
source-wordcount: '2323'
ht-degree: 13%

---

# Adobe User Management モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、Adobeアカウントのユーザーを管理するワークフローを自動化できます。

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
   <p>レガシーライセンス要件：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration], [!UICONTROL [!DNL Workfront Fusion] for Work Automation]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] の [!DNL Adobe Workfront] プランがある場合、この記事で説明する機能を使用するには、組織で [!DNL Adobe Workfront Fusion] の購入 [!DNL Adobe Workfront] 必要です。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## Adobe User Management への接続の作成

[!DNL Adobe User Management] モジュールへの接続を作成するには、以下を実行します。

1. 「接続」ボックスの横にある「**[!UICONTROL Add]**」をクリックします。

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
          <p>この接続の名前を入力します。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID] を入力します。 これは、の [!UICONTROL Credentials] 細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、の [!UICONTROL Credentials] 細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS Organization ID]</td>
        <td>[!DNL Adobe] IMS 資格情報を入力します。 組織の一意の ID。 これは、A495E53@AdobeOrgの形式の文字列で、@の前のプレフィックスは 16 進数です。 この値は、Admin Consoleの組織の URL パスの一部として、または User Management 統合の adobe.io コンソールで確認できます。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Additional scopes]</td>
        <td>追加する追加の範囲ごとに、「<b> 項目を追加 </b>」をクリックして範囲を入力します。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL Continue]**」をクリックして接続を保存し、モジュールに戻ります。



## Adobe User Management モジュールとそのフィールド

Workfront Fusion でAdobe User Management モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のAdobeUser Management フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [検索](#searches)
* [ユーザーアクション](#user-actions)
* [ユーザーグループのアクション](#user-group-actions)
* [その他](#other)

### 検索

* [ユーザーグループと製品プロファイルの取得](#get-user-groups-and-product-profiles)
* [ユーザー情報の取得](#get-user-information)
* [ユーザーグループまたは製品プロファイルのユーザーの取得](#get-users-in-a-user-group-or-product-profile)
* [組織内のユーザーの取得](#get-users-in-an-organization)

#### ユーザーグループと製品プロファイルの取得

この検索モジュールは、組織内のすべてのユーザーグループと製品プロファイルのリストを、グループとプロファイルの詳細と共に取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザー情報の取得

この検索モジュールは、組織内の 1 人のユーザーについて、メールアドレスで識別される詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メールアドレス</td> 
   <td>詳細を返すユーザーのメールアドレスを入力またはマッピングします。 AdobeID、Enterprise およびメールフェデレーションのユーザーの場合、これはドメインを含む完全なメールアドレスである必要があります。 どの場合でも、パラメーターでは大文字と小文字が区別されません。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループまたは製品プロファイルのユーザーの取得

この検索モジュールは、指定したユーザーグループまたは製品プロファイルのすべてのユーザーのリストと、ユーザーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>ユーザーグループ、製品プロファイル名または管理グループ。 管理者グループの場合、名前は <code>_org_admin</code>、<code>_deployment_admin</code>、<code>_support_admin</code> のいずれかの固定グループ、またはグループ固有の管理者グループにできます。 これらは、グループ名のプレフィックス（<code>_admin_groupName</code>、<code>_product_admin_productName</code>、<code>_developer_groupName</code> など）で識別されます。 グループが存在しても管理者グループが存在しない場合は、空のリストが返されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ダイレクトのみ</td> 
   <td>返されるユーザー構造のグループフィールドに、そのユーザーが直接メンバーとなっている製品プロファイルのみを含めるかどうかを指定します。 false の場合、特定の製品プロファイルの使用権限が直接（ユーザー割り当てによって）付与されるか、間接的（製品プロファイルに割り当てられているユーザーを含むユーザーグループによって）付与されるかに関係なく、ユーザーを含むすべてのグループ（ユーザーグループ、製品プロファイル、管理者グループ）を返します。 true の場合、ユーザーを含むすべてのユーザーグループと管理者グループを返しますが、ユーザーが明示的にエンタイトルメントを割り当てられている製品プロファイルのみを返します。 ユーザーは、製品プロファイルの直接および間接のメンバーになることができます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループを除外</td> 
   <td>応答で、各ユーザーに対して groups 配列を返さないかどうかを指定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ステータス</td> 
   <td>このオプションは、製品プロファイルにのみ適用されます。 「アクティブ」を選択すると、製品に対してプロビジョニング済みでアクティブなライセンスを持つユーザーがリストされます。 「非アクティブ」を選択すると、製品プロファイルに追加されたが、アクティブなライセンスを持たないユーザーが一覧表示されます。 空白のままにすると、モジュールは使用権限のステータスに関係なく、すべてのメンバーユーザーを返します。
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 組織内のユーザーの取得

この検索モジュールは、接続に関連付けられた組織のすべてのユーザーを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### ユーザーアクション

* [ユーザーをグループのメンバーとして追加する](#add-a-user-as-a-member-of-a-group)
* [ユーザーの作成](#create-a-user)
* [グループからのユーザーの削除](#remove-a-user-from-groups)
* [ユーザーの更新](#update-a-user)

#### ユーザーをグループのメンバーとして追加する

このアクションモジュールは、指定された 1 つ以上のグループのメンバーとしてユーザーを追加します。 このモジュールでは、ユーザーを最大 4 つのグループに追加できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>グループに追加するユーザーを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>メールアドレス以外の Federated ID の場合、ユーザーが属するドメインを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ</td> 
   <td>ユーザーを追加するグループごとに、「<b> 項目を追加 </b> をクリックし、グループを入力またはマッピングします。 最大 4 つのグループを入力できます。少なくとも 1 つのグループを入力する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>true を選択すると、同じ名前の Enterprise またはFederated IDが存在する場合でも、ユーザー ID は既存のAdobe IDを参照するように解釈されます。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーの作成

このアクションモジュールは、組織に新しいユーザーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID タイプ</td> 
   <td>Adobe ID、Enterprise IDまたはFederated IDのいずれでユーザーを作成するかを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ログイン</td> 
   <td>Federated IDを持つユーザーを作成する場合は、ログインの種類を選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メール</td> 
   <td>新規ユーザーのメールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>ドメインベースのログインを持つFederated IDを持つユーザーを作成する場合は、ドメインを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>ドメインベースのログインでFederated IDを持つユーザーを作成する場合は、新しいユーザーが表すユーザーを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名</td> 
   <td>ユーザーの名を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名前 (姓)</td> 
   <td>ユーザーの姓を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">国</td> 
   <td>2 文字の ISO 国コードを入力またはマッピングします。 これは、ユーザーの作成後に変更することはできません。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オプション</td> 
   <td>ユーザーが既に組織内に存在する場合に実行するアクションを選択します。 オプションが選択されておらず、ユーザーが既に存在する場合、モジュールはエラーを返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>True の場合、Enterprise またはFederated IDが同じ名前で存在していても、ユーザー ID は既存のAdobe IDを参照するように解釈されます。</td> 
  </tr> 
 </tbody> 
</table>

#### グループからのユーザーの削除

このアクションモジュールは、指定されたグループからユーザーのメンバーシップを削除します。 ユーザーは一度に 4 つまでグループから削除できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>グループから削除するユーザーを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>メールアドレス以外の Federated ID の場合、ユーザーが属するドメインを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ</td> 
   <td>ユーザーを削除するグループごとに、「<b> 項目を追加 </b>」をクリックし、グループを入力またはマッピングします。 最大 4 つのグループを入力できます。少なくとも 1 つのグループを入力する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>true を選択すると、同じ名前の Enterprise またはFederated IDが存在する場合でも、ユーザー ID は既存のAdobe IDを参照するように解釈されます。</td> 
  </tr> 
 </tbody> 
</table>



#### ユーザーの更新

このアクションモジュールは、既存のユーザーを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>更新するユーザーの ID を入力またはマッピングします。 これは、ユーザーのメールアドレスです（例：） <code>user@example.com</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>メールアドレス以外のFederated IDでユーザーをアップデートする場合、ユーザーを識別するために、ユーザーが属するドメインを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メール</td> 
   <td>ユーザーの新しいメールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名</td> 
   <td>ユーザーの名を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名前 (姓)</td> 
   <td>ユーザーの姓を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### ユーザーグループのアクション

* [ユーザーグループのメンバーシップの追加](#add-memberships-for-a-user-group)
* [ユーザーグループの作成](#create-a-user-group)
* [ユーザーグループの削除](#delete-a-user-group)
* [ユーザーグループのメンバーシップの削除](#remove-memberships-for-a-user-group)
* [ユーザーグループの更新](#update-a-user-group)

#### ユーザーグループのメンバーシップの追加

このアクションモジュールは、ユーザーと製品プロファイルをユーザーグループに追加します。 ユーザーグループに追加されたユーザーには、ユーザーグループ内のすべての製品プロファイルに対する使用権限が付与されます。 製品プロファイルを追加すると、そのプロファイルの使用権限がユーザーグループのユーザーに付与されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>ユーザーまたはプロファイルを削除するグループの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>追加するユーザーごとに「<b> ユーザーを追加 </b>」をクリックし、ユーザーのメールアドレスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロファイル</td> 
   <td>グループに追加するプロファイルごとに、「<b> ユーザーを追加 </b> をクリックして、プロファイル名を入力します</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループの作成

このアクションモジュールは、新しいユーザーグループを作成します。 指定した名前のグループが既に存在する場合、モジュールは既存のグループを更新できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>新規ユーザーグループの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td>新規ユーザーグループの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オプション</td> 
   <td>ユーザーグループが既に組織に存在する場合に実行するアクションを選択します。 オプションが選択されておらず、ユーザーグループが既に存在する場合、モジュールはエラーを返します。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループの削除

既存のユーザーグループを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>削除するグループの名前を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループのメンバーシップの削除

このアクションモジュールは、ユーザーグループからユーザーまたはプロファイルを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>ユーザーまたはプロファイルを削除するグループの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>削除するユーザーごとに「<b> ユーザーを追加 </b>」をクリックし、ユーザーのメールアドレスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロファイル</td> 
   <td>グループから削除するプロファイルごとに、「<b> ユーザーを追加 </b>」をクリックしてプロファイル名を入力します</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>true の場合、Enterprise またはFederated IDが同じ名前で存在していても、ユーザー ID は既存のAdobe IDを参照するように解釈されます。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループの更新

既存のユーザーグループを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">元のグループ名</td> 
   <td>更新するグループの現在の名前を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">新しいグループ名</td> 
   <td>グループに割り当てる新しい名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">元のグループ名</td> 
   <td>更新したグループの説明を入力またはマッピングします。</td> 
  </tr> 
 </tbody>

### その他

このアクションモジュールは、AdobeUser Management API へのカスタム呼び出しを行います。

#### カスタム API 呼び出しの実行

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe User Management への接続を作成する手順については、この記事の <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Management への接続の作成 </a> を参照してください。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>相対パスを入力します <code>https://usermanagement.adobe.io/v2/usermanagement/</code></p>
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
