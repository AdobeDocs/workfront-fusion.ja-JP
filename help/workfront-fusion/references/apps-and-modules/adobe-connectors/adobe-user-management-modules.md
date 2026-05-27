---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe User Management モジュール
description: Adobe Workfront Fusionでは、Adobe アカウントのユーザーを管理するワークフローを自動化できます。
author: Becky
feature: Workfront Fusion
exl-id: e8fe8ec4-4b00-4c9a-81a5-acb2039b153b
TQID: https://experienceleague.adobe.com/Z8KIPMacTfdO2BJtbczdW3Tsrbb-MTB1rgY60FdPgps
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 2385
ht-degree: 19%

---

# Adobe User Management モジュール

Adobe Workfront Fusionでは、Adobe アカウントのユーザーを管理するワークフローを自動化できます。

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

## Adobe User Managementへの接続の作成

[!DNL Adobe User Management] モジュールへの接続を作成するには、以下を実行します。

1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

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
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID]を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS組織ID]</td>
        <td>[!DNL Adobe] IMS資格情報を入力します。 組織の一意のID。 これはA495E53@AdobeOrgという形式の文字列で、@の前の接頭辞は16進数です。 この値は、Admin Consoleの組織のURL パスの一部として、またはUser Management統合用のadobe.io コンソールで見つけることができます。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL追加スコープ ]</td>
        <td>追加するスコープごとに、<b>項目を追加</b>をクリックし、スコープを入力します。</td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。



## Adobe ユーザー管理モジュールとそのフィールド

Adobe User Management モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Adobe User Managementの追加フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [検索](#searches)
* [ユーザーアクション](#user-actions)
* [ユーザーグループ アクション](#user-group-actions)
* [その他](#other)

### 検索

* [ユーザーグループと製品プロファイルの取得](#get-user-groups-and-product-profiles)
* [ユーザー情報の取得](#get-user-information)
* [ユーザーグループまたは製品プロファイルでのユーザーの取得](#get-users-in-a-user-group-or-product-profile)
* [組織内のユーザーの取得](#get-users-in-an-organization)

#### ユーザーグループと製品プロファイルの取得

この検索モジュールは、組織内のすべてのユーザーグループと製品プロファイルのリスト、およびグループとプロファイルに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザー情報の取得

この検索モジュールは、組織内の1人のユーザーの詳細を取得します。ユーザーのメールアドレスで識別されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メールアドレス</td> 
   <td>詳細を返すユーザーの電子メールアドレスを入力またはマッピングします。 Adobe ID、エンタープライズ版およびメール配信ユーザーの場合、これはドメインを含む完全なメールアドレスである必要があります。 すべての場合、パラメーターでは大文字と小文字が区別されません。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループまたは製品プロファイルでのユーザーの取得

この検索モジュールは、指定されたユーザーグループまたは製品プロファイルのすべてのユーザーのリストと、ユーザーに関する詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>ユーザーグループ、製品プロファイル名または管理グループ。 管理者グループの場合、名前は固定グループ <code>_org_admin</code>、<code>_deployment_admin</code>、<code>_support_admin</code>のいずれかまたはグループ固有の管理者グループにすることができます。 これらは、<code>_admin_groupName</code>、<code>_product_admin_productName</code>、<code>_developer_groupName</code>など、グループ名の接頭辞で識別されます。 グループが存在するが管理者グループが存在しない場合は、空のリストが返されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ダイレクトのみ</td> 
   <td>返されるユーザー構造内の「グループ」フィールドに、そのユーザーが直接メンバーである製品プロファイルのみを含めるかどうかを指定します。 falseの場合、特定の製品プロファイルの使用権限が直接（ユーザー割り当て経由）または間接的（製品プロファイルに割り当てられているユーザーを含むユーザーグループ経由）に関係なく、ユーザーを含むすべてのグループ（ユーザーグループ、製品プロファイルおよび管理者グループ）が返されます。 trueの場合、は、ユーザーを含むすべてのユーザーグループと管理者グループを返しますが、ユーザーに明示的に使用権限が割り当てられている製品プロファイルのみが返されます。 ユーザーは、製品プロファイルの直接メンバーと間接メンバーの両方にすることができます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループを除外</td> 
   <td>応答が個々のユーザーごとに返されるグループ配列を除外するかどうかを指定します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ステータス</td> 
   <td>このオプションは、製品プロファイルにのみ適用されます。 「アクティブ」を選択すると、製品にプロビジョニングされ、アクティブなライセンスを持つユーザーが一覧表示されます。 「非アクティブ」を選択すると、製品プロファイルに追加されたが、アクティブなライセンスを持たないユーザーが一覧表示されます。 空白のままにすると、モジュールは、使用権限のステータスに関係なく、すべてのメンバーユーザーを返します。
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### 組織内のユーザーの取得

この検索モジュールは、接続に関連付けられている組織のすべてのユーザーを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">返される結果の最大数</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### ユーザーアクション

* [ユーザーをグループのメンバーとして追加](#add-a-user-as-a-member-of-a-group)
* [ユーザーの作成](#create-a-user)
* [グループからのユーザーの削除](#remove-a-user-from-groups)
* [ユーザーの更新](#update-a-user)

#### ユーザーをグループのメンバーとして追加

このアクションモジュールは、指定したグループまたはグループのメンバーとしてユーザーを追加します。 このモジュールは、ユーザーを最大4つのグループに追加できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>グループに追加するユーザーを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>メールアドレス以外のフェデレーション IDの場合は、ユーザーが属するドメインを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ</td> 
   <td>ユーザーを追加する各グループについて、<b>項目を追加</b>をクリックし、グループを入力またはマッピングします。 最大4つのグループを入力でき、少なくとも1つのグループを入力する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>EnterpriseまたはFederated IDが同じ名前で存在する場合でも、既存のAdobe IDを参照するようにユーザーIDが解釈されるようにするには、trueを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーの作成

このアクションモジュールは、組織内に新しいユーザーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID タイプ</td> 
   <td>Adobe ID、Enterprise ID、またはFederated IDを使用してユーザーを作成するかどうかを選択します。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ログイン</td> 
   <td>Federated IDでユーザーを作成する場合は、ログインタイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メール</td> 
   <td>新規ユーザーのメールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>Federated IDでドメインベースのログインを使用してユーザーを作成する場合は、ドメインを入力するかマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>ドメインベースのログインを持つFederated IDを使用してユーザーを作成する場合は、新しいユーザーが表すユーザーを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名</td> 
   <td>ユーザーの名前を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">姓</td> 
   <td>ユーザーの姓を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">国</td> 
   <td>2文字のISO国コードを入力またはマッピングします。 これは、ユーザーの作成後に変更することはできません。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オプション</td> 
   <td>ユーザーが既に組織内に存在する場合に実行するアクションを選択します。 オプションが選択されておらず、ユーザーが既に存在する場合、モジュールはエラーを返します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>trueの場合、EnterpriseまたはFederated IDが同じ名前で存在する場合でも、ユーザーIDは既存のAdobe IDを参照するように解釈されます。</td> 
  </tr> 
 </tbody> 
</table>

#### グループからのユーザーの削除

このアクションモジュールは、指定されたグループからユーザーのメンバーシップを削除します。 一度に最大4つのグループからユーザーを削除できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>グループから削除するユーザーを入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>メールアドレス以外のフェデレーション IDの場合は、ユーザーが属するドメインを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ</td> 
   <td>ユーザーを削除するグループごとに、<b>項目を追加</b>をクリックし、グループを入力またはマッピングします。 最大4つのグループを入力でき、少なくとも1つのグループを入力する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>EnterpriseまたはFederated IDが同じ名前で存在する場合でも、既存のAdobe IDを参照するようにユーザーIDが解釈されるようにするには、trueを選択します。</td> 
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
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>更新するユーザーのIDを入力またはマッピングします。 これはユーザーのメールアドレスです。例えば <code>user@example.com</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">ドメイン</td> 
   <td>電子メールアドレスではないFederated IDを使用してユーザーを更新する場合は、ユーザーを識別するために、ユーザーが属するドメインを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">メール</td> 
   <td>ユーザーの新しい電子メールアドレスを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名</td> 
   <td>ユーザーの名前を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">姓</td> 
   <td>ユーザーの姓を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### ユーザーグループ アクション

* [ユーザーグループのメンバーシップの追加](#add-memberships-for-a-user-group)
* [ユーザーグループの作成](#create-a-user-group)
* [ユーザーグループの削除](#delete-a-user-group)
* [ユーザーグループのメンバーシップの削除](#remove-memberships-for-a-user-group)
* [ユーザーグループの更新](#update-a-user-group)

#### ユーザーグループのメンバーシップの追加

このアクションモジュールは、ユーザーと製品プロファイルをユーザーグループに追加します。 ユーザーグループに追加されたユーザーは、ユーザーグループ内のすべての製品プロファイルに対する使用権限を取得します。 製品プロファイルを追加すると、ユーザーグループ内のユーザーにそのプロファイルの使用権限が付与されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>ユーザーまたはプロファイルを削除するグループの名前を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>追加するユーザーごとに、<b> ユーザーを追加</b>をクリックし、ユーザーの電子メールアドレスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロファイル</td> 
   <td>グループに追加する各プロファイルについて、<b> ユーザーを追加</b>をクリックし、プロファイル名を入力します</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループの作成

このアクションモジュールは、新しいユーザーグループを作成します。 指定された名前のグループが既に存在する場合、モジュールは既存のグループを更新できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>新しいユーザーグループの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td>新しいユーザーグループの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">オプション</td> 
   <td>ユーザーグループが既に組織内に存在する場合に実行するアクションを選択します。 オプションが選択されておらず、ユーザーグループが既に存在する場合、モジュールはエラーを返します。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループの削除

このアクションモジュールは、既存のユーザーグループを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>削除するグループの名前を入力するか、マッピングします。</td> 
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
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">グループ名</td> 
   <td>ユーザーまたはプロファイルを削除するグループの名前を入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ユーザー</td> 
   <td>削除するユーザーごとに、<b> ユーザーを追加</b>をクリックし、ユーザーの電子メールアドレスを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロファイル</td> 
   <td>グループから削除する各プロファイルについて、<b> ユーザーを追加</b>をクリックし、プロファイル名を入力します</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe IDの使用</td> 
   <td>trueの場合、EnterpriseまたはFederated IDが同じ名前で存在する場合でも、ユーザーIDは既存のAdobe IDを参照するように解釈されます。</td> 
  </tr> 
 </tbody> 
</table>

#### ユーザーグループの更新

このアクションモジュールは、既存のユーザーグループを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">元のグループ名</td> 
   <td>更新するグループの現在の名前を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">新しいグループ名</td> 
   <td>グループに含める新しい名前を入力するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">元のグループ名</td> 
   <td>グループの更新された説明を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
 </table>

### その他


#### カスタム API 呼び出しの実行

このアクションモジュールは、Adobe User Management APIをカスタム呼び出します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">接続</td>
      <td>Adobe User Managementへの接続の作成手順については、この記事の「<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Adobe User Managementへの接続の作成</a>」を参照してください。</td> 
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
