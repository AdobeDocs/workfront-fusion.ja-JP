---
title: SharePoint モジュール
description: Adobe Workfront Fusionでは、Microsoft SharePoint Onlineを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
TQID: 'https://experienceleague.adobe.com/WmECfdPt-a3l2-WT9LMX2HB-7-p-BLIO4F2i3OAc7D0'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
    internal-label: APIs
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: be0cf391e02e3f8c2547494aeac0de5b7296c85d
workflow-type: tm+mt
source-wordcount: '5814'
ht-degree: 39%
---
# Microsoft SharePoint Online モジュール

Adobe Workfront Fusionでは、Microsoft SharePoint Onlineを使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成手順について詳しくは、[シナリオの作成：記事のインデックス](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

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
   <p>オペレーションベース：オペレーションベースのライセンスを持つ組織で使用できます</p>
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

## 前提条件

Microsoft SharePoint Online モジュールを使用するには、Microsoft SharePoint Online アカウントが必要です。

## SharePoint APIについて

SharePoint コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.14.2</td> 
  </tr>
 </tbody> 
 </table>

## Microsoft SharePoint OnlineとWorkfront Fusionの連携 {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [ [!DNL Microsoft]  アカウントを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [詳細設定を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)
* [証明書認証を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-certificate-authorization)
* [サービスプリンシパルを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-service-principal)

### [!DNL Microsoft] アカウントを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する

+++ 展開すると、Microsoft アカウントを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する手順が表示されます。

[!DNL Microsoft] アカウントを使用して、Microsoft SharePoint Onlineへの接続を作成できます。 [!DNL Sharepoint] アカウントをWorkfront Fusionに接続する手順については、[Adobe Workfront Fusionへの接続の作成 – 基本手順](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)を参照してください。

+++

### 詳細設定を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する

+++ 詳細な設定を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する手順を表示します。

接続に資格情報を含めるには、「詳細設定を表示」オプションを有効にします。 このタイプの接続には、クライアント ID、クライアント秘密鍵、およびテナント IDが必要です。

1. 任意のSharePoint モジュールで、Connection フィールドの近くの&#x200B;**[!UICONTROL Add]**&#x200B;をクリックして、**[!UICONTROL Create a connection]** ボックスを開きます。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection type]</p> </td> 
      <td>クライアントの資格情報を使用するには、<b>Microsoft 365 Email</b>を選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>接続に名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client ID]</p> </td> 
      <td>接続先のSharePoint アプリのクライアント IDを入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client secret]</p> </td> 
      <td>接続先のSharePoint アプリのクライアントシークレットを入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL テナント ID]</p> </td> 
      <td>接続先のSharePoint アプリのテナント IDを入力します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

+++

### 証明書認証を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する

+++ 展開すると、証明書認証を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する手順が表示されます。

証明書認証を使用して、SharePointに接続できます。

>[!IMPORTANT]
>
>証明書の認証を使用するには、まずMicrosoft Entraでアプリを作成し、そこに証明書をアップロードする必要があります。
>
>手順については、Microsoft ドキュメントの「[Microsoft Entra証明書ベースの認証に対する証明機関の設定方法](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-configure-certificate-authorities)」を参照してください。

1. 任意のSharePoint モジュールで、Connection フィールドの近くの&#x200B;**[!UICONTROL Add]**&#x200B;をクリックして、**[!UICONTROL Create a connection]** ボックスを開きます。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection type]</p> </td> 
      <td>証明書認証を使用するには、<b>Microsoft SharePoint Online （証明書認証） </b>を選択します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>接続に名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Client ID]</p> </td> 
      <td>接続先のSharePoint アプリのクライアント IDを入力します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Thumbprint]</p> </td> 
      <td>接続先のSharePoint アプリのサムプリントを入力します。</td> 
     </tr> 
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>資格情報がMicrosoftで作成されたときに生成された証明書または秘密鍵を入力します。 </p>
          <p>秘密鍵または証明書を抽出するには：</p>
          <ol>
            <li>
              <p><b>[!UICONTROL Extract]</b> をクリックします。</p>
            </li>
            <li>
            <p>証明書を抽出するか、秘密鍵を抽出するかを選択します。</li>
            <li>
              <p>抽出するファイルのタイプを選択します。</p>
            </li>
            <li>
              <p>秘密鍵または証明書を含むファイルを選択します。</p>
            </li>
            <li>
              <p>ファイルのパスワードを入力します。</p>
            </li>
            <li>
              <p><b>[!UICONTROL Save]</b> をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody> 
   </table>

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

+++

### サービスプリンシパルを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する

+++ サービスプリンシパルを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続する手順を表示するには、を展開します。

個人アカウントの代わりにサービスプリンシパル（アプリケーション API接続）を使用する接続を作成できます。 これは、接続を特定のユーザーではなく、アプリケーションまたはサービス IDとして実行したい場合に便利です。例えば、そのユーザーが会社を辞めたり、パスワードを変更したりしても、統合が壊れることはありません。

>[!IMPORTANT]
>
>この接続タイプは、[API呼び出しを作成](#make-an-api-call) モジュールでのみ使用できます。 その他のSharePoint モジュールには、この記事で説明したその他の種類の接続が必要です。

* [サービスプリンシパルを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続するための前提条件](#prerequisites-to-connecting-microsoft-sharepoint-online-to-workfront-fusion-using-a-service-principal)
* [Microsoft Entra IDでアプリ登録を作成する](#create-the-app-registration-in-microsoft-entra-id)
* [クライアントシークレットの作成](#create-a-client-secret)
* [API権限の付与](#grant-api-permissions)
* [接続の詳細を収集](#collect-your-connection-details)
* [接続の作成](#create-the-connection)

#### サービスプリンシパルを使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続するための前提条件

アプリを登録して権限を付与するには、Microsoft Entra IDで&#x200B;**グローバル管理者**、**アプリケーション管理者**、または&#x200B;**特権ロール管理者**&#x200B;のアクセス権が必要です。 このアクセス権をお持ちでない場合は、IT チームまたはID チームの誰かに、これらの手順を完了するように依頼してください。

引き続き[Microsoft Entra ID](#create-the-app-registration-in-microsoft-entra-id)でアプリ登録を作成します。

#### Microsoft Entra ID （サービスプリンシパル）でのアプリ登録の作成

1. [!DNL Microsoft Entra]管理センターにログインします。
1. **[!UICONTROL アプリ登録]** > **[!UICONTROL 新規登録]**&#x200B;に移動します。
1. アプリに明確で認識可能な名前を付けます。 例：`Make - SharePoint Integration`
1. **[!UICONTROL リダイレクト URI]**&#x200B;を空白のままにします。 この接続には、ブラウザーを介してログインするユーザーは含まれません。
1. **[!UICONTROL 登録]**&#x200B;を選択します。
1. 引き続き[ クライアントシークレットの作成](#create-a-client-secret)を続行します。

#### クライアントシークレットの作成（サービスプリンシパル）

1. 新しいアプリの登録で、**[!UICONTROL 証明書とシークレット]**&#x200B;に移動します。
1. **[!UICONTROL 新しいクライアントシークレット]**&#x200B;を選択し、説明を追加して、有効期限を選択します。
1. 「**[!UICONTROL 追加]**」を選択します。
1. 秘密鍵の&#x200B;**[!UICONTROL 値]**&#x200B;をすぐにコピーします。 1回だけ表示されます。 コピーする前に移動する場合は、新しいコピーを作成する必要があります。
1. 引き続き[API権限の付与](#grant-api-permissions)を続行します。

#### API権限の付与（サービスプリンシパル）

1. アプリ登録で、**[!UICONTROL API権限]**&#x200B;に移動します。
1. 「**[!UICONTROL 権限を追加]**」を選択し、「**[!UICONTROL Microsoft Graph]**」を選択します。
1. **[!UICONTROL アプリケーション権限]**&#x200B;を選択します。
1. API呼び出しに必要な権限または権限を選択し、**[!UICONTROL 権限を追加]**&#x200B;を選択します。
1. 「**[!UICONTROL 組織に管理者の同意を付与する]**」を選択し、確認します。
1. 引き続き[接続の詳細を収集](#collect-your-connection-details)してください。

#### 接続の詳細を収集する（サービスプリンシパル）

アプリ登録の&#x200B;**[!UICONTROL 概要]** ページから、次の値に注意してください。 モジュールで接続を作成する際に、これらの項目を入力します。

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader">[!UICONTROL テナント ID]</td>
   <td>概要ページで、<b> ディレクトリ （テナント） ID</b>というラベルが付いています。</td>
  </tr>
  <tr>
   <td role="rowheader">[!UICONTROL Client ID]</td>
   <td>概要ページに「<b> アプリケーション （クライアント） ID</b>」というラベルが付いています。</td>
  </tr>
  <tr>
   <td role="rowheader">[!UICONTROL Client Secret]</td>
   <td><a href="#create-a-client-secret" class="MCXref xref">でコピーした値は、クライアントシークレットを作成</a>します。</td>
  </tr>
 </tbody>
</table>

引き続き[接続を作成](#create-the-connection)します。

#### 接続の作成（サービスプリンシパル）

1. [!UICONTROL API呼び出しを行う] モジュールで、接続フィールドの近くの&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックして、**[!UICONTROL 接続を作成]** ボックスを開きます。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 「[!UICONTROL 接続タイプ ]」フィールドで、「**[!UICONTROL サービスプリンシパル]**」を選択します。
1. 以下の情報を入力します。

   * [!UICONTROL  テナント ID]
   * [!UICONTROL クライアント ID]
   * [!UICONTROL クライアント秘密鍵]

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

   すべてが正しく設定されていれば、接続は正常に検証されます。

+++

### 連合コネクションを使用してMicrosoft SharePoint OnlineをAdobe Workfront Fusionに接続します

+++ フェデレーション接続を使用してMicrosoft SharePoint OnlineをAdobe Workfront Fusionに接続する手順を表示するには、こちらを参照してください。

フェデレーション接続は、クライアントシークレットを使用しない場合を除き、サービスプリンシパル接続と同様に機能します。
秘密鍵を保存する代わりに、Microsoft Entra IDに、Workfront Fusionが1つの特定の接続に対して問題を発生させるトークンを信頼するように指示します。 接続が実行されると、Fusionは短時間のみ有効なID証明を表示し、Microsoft Entra IDはアクセストークンを返します。 クライアントのシークレットはないので、有効期限が切れるものも、ローテーションや保存のためのシークレットもありません。

>[!NOTE]
>
>この接続を設定するには、Microsoft Entra管理センターに2回訪問する必要があります。 最初にアプリを登録してから、Workfront Fusionで接続を作成し、次にMicrosoft Entra IDに戻ってフェデレーション資格情報を追加します。 これは、フェデレーション資格情報によって1つの特定の接続が識別され、その識別子は接続が作成されるまで存在しないためです。

* [フェデレーション接続を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続するための前提条件](#prerequisites-to-connecting-microsoft-sharepoint-online-to-workfront-fusion-using-a-federated-connection)
* [Microsoft Entra ID （Federated Connection）でのアプリ登録の作成](#create-the-app-registration-in-microsoft-entra-id-federated-connection)
* [API権限の付与（フェデレーション接続）](#grant-api-permissions-federated-connection)
* [接続の詳細を収集する（フェデレーション接続）](#collect-your-connection-details-federated-connection)
* [Workfront Fusion （フェデレーションコネクション）でのコネクションの作成](#create-the-connection-in-workfront-fusion-federated-connection)
* [Microsoft Entra IDにフェデレーション資格情報を追加する（フェデレーション接続）](#add-the-federated-credential-in-microsoft-entra-id-federated-connection)
* [接続の確認（フェデレーション接続）](#verify-the-connection-federated-connection)
* [トラブルシューティング](#troubleshooting)

#### フェデレーション接続を使用してMicrosoft SharePoint OnlineをWorkfront Fusionに接続するための前提条件

アプリを登録し、権限を付与し、フェデレーション資格情報を追加するには、Microsoft Entra IDのグローバル管理者、アプリケーション管理者、または特権ロール管理者のアクセス権が必要です。 このアクセス権をお持ちでない場合は、IT チームまたはID チームの誰かに、これらの手順を完了するように依頼してください。

#### Microsoft Entra ID （Federated Connection）でのアプリ登録の作成

1. Microsoft Entra管理センターにログインします。
1. アプリ登録/新規登録に移動します。
1. アプリに明確で認識可能な名前を付けます。 例：`Workfront Fusion SharePoint Integration`
1. リダイレクト URIを空白のままにします。 この接続には、ブラウザーを介してログインするユーザーは含まれません。
1. **登録**を選択します。
クライアントシークレットを作成しないでください。 フェデレーション接続では1つは使用されません。
1. 引き続きAPI権限を付与します。


#### API権限の付与（フェデレーション接続）

1. アプリ登録で、**API権限**&#x200B;に移動します。
1. 「**権限を追加**」を選択し、「**Microsoft Graph**」を選択します。
1. **アプリケーション権限**&#x200B;を選択します。
1. API呼び出しに必要な権限または権限を選択し、**権限を追加**&#x200B;を選択します。
1. 組織に対して&#x200B;**管理者の同意を付与**&#x200B;を選択し、確認します。
1. 引き続き[接続の詳細を収集](#collect-your-connection-details-federated-connection)してください。


#### 接続の詳細を収集する（フェデレーション接続）

1. アプリ登録の概要ページで、次の値に注意してください。 モジュールで接続を作成する際に、これらの項目を入力します。

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL テナント ID]</td>
      <td>概要ページで、<b> ディレクトリ （テナント） ID</b>というラベルが付いています。</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Client ID]</td>
      <td>概要ページに「<b> アプリケーション （クライアント） ID</b>」というラベルが付いています。</td>
     </tr>
    </tbody>
   </table>

1. 引き続き[Workfront Fusion](#create-the-connection-in-workfront-fusion-federated-connection)で接続を作成します。

#### Workfront Fusion （フェデレーションコネクション）でのコネクションの作成

1. 「API呼び出しを作成」モジュールで、「接続」フィールドの近くにある「b」をクリックして、「接続を作成」ボックスを開きます。
1. （Federated connection）をクリックします。
1. 「接続タイプ」フィールドで、フェデレーション接続タイプを選択します。
1. 以下の情報を入力します。

   * テナント ID
   * クライアント ID

1. 「**作成**」を選択します。
Workfront Fusionには3つの値が表示されます。 次の手順で使用します。

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL イシュア ]</td>
      <td>常に<code>https://oidc.automations.adobe.com</code>。</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Subject]</td>
      <td>この1つの接続を識別します。 <code>fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964</code>のようです。 作成する接続ごとに異なります。</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Audience]</td>
      <td>常に<code>api://AzureADTokenExchange</code>。</td>
     </tr>
    </tbody>
   </table>


1. このパネルを開いたままにして、**件名**&#x200B;の値をコピーします。

   >[!NOTE]
   >
   >パネルを閉じたり、「キャンセル」を選択したりしないでください。 残りの手順を完了するまで、接続は完了しません。 パネルを閉じた場合は、新しい接続が新しい件名を受信するので、接続を削除して再度開始する必要があります。


1. 引き続き[Microsoft Entra ID](#add-the-federated-credential-in-microsoft-entra-id-federated-connection)でフェデレーション資格情報を追加します。

#### Microsoft Entra IDにフェデレーション資格情報を追加する（フェデレーション接続）

この手順は、クライアントシークレットに代わるものです。 これは、Microsoft Entra IDに対して、Workfront Fusionがこの1つの接続に対して発行するトークンを受け入れるように指示します。

1. 新しいブラウザータブで、Microsoft Entra管理センターに戻り、アプリ登録を開きます。
1. **証明書と秘密鍵** > **Federated credentials**&#x200B;に移動します。
1. 「**資格情報を追加**」を選択します。
1. フェデレーション資格情報シナリオで、**その他の発行者**&#x200B;を選択します。
1. 以下の情報を入力します。

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[!UICONTROL イシュア ]</td>
      <td><code>https://oidc.automations.adobe.com</code>.</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Subject IDENTIFIER]</td>
      <td>Workfront Fusionからコピーした被写体。 スペースを追加せずに、正確にペーストします。</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>後で見つけられるように、この接続を識別する名前。 例：<code>workfront-fusion-connection-28964</code></td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Audience]</td>
      <td><code>api://AzureADTokenExchange</code>. これは通常、あなたのために記入されます。 デフォルト値のままにします。</td>
     </tr>
    </tbody>
   </table>

1. 「**追加**」を選択します。
1. 引き続き[接続の確認](#verify-the-connection-federated-connection)を行います。


#### 接続の確認（フェデレーション接続）

1. Workfront Fusion ブラウザータブに戻ります。接続パネルはまだ開いています。
2. 「**保存**」を選択します。

   * すべてが正しく設定されている場合、接続は正常に検証され、モジュールの設定を続行できます。
   * 検証に失敗した場合、パネルは開いたままになり、エラーが表示されます。 Microsoft Entra IDの問題を修正し、「保存」をもう一度選択します。 接続を再作成する必要はなく、被写体は変更されません。


#### トラブルシューティング


<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader">接続が無効なクライアントまたは無効な要求エラーで検証に失敗します</td>
   <td>Microsoft Entra IDは、トークンとフェデレーション資格情報を一致させることができませんでした。 イシュアが末尾にスラッシュを含まない正確な<code>https://oidc.automations.adobe.com</code>であること、および件名IDがWorkfront Fusionに表示されている件名と同じ文字の場合であることを確認してください。 別の接続からコピーされた被写体が最も一般的な原因です。</td>
  </tr>
  <tr>
   <td role="rowheader">接続は検証されますが、API呼び出しは403を返します</td>
   <td>IDは信頼されますが、アプリには呼び出しに必要なMicrosoft Graph権限がありません。 「API権限の付与」、「必要なアプリケーション権限の追加」、「管理者の同意の付与」に戻ります。</td>
  </tr>
  <tr>
   <td role="rowheader">別のフェデレーション資格情報を追加することはできません</td>
   <td>そのアプリ登録のフェデレーション資格情報が20件の上限に達しました。 追加のアプリを登録し、そのアプリに対してさらに接続を作成します。</td>
  </tr>
 </tbody>
</table>

+++

## Microsoft SharePointのモジュールとそのフィールド

Microsoft SharePoint Online モジュールを設定すると、Workfront Fusionに次のフィールドが表示されます。 また、アプリやサービスのアクセスレベルなどの要因に応じて、Microsoft SharePoint Onlineの追加フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ドライブ項目](#drive-item)
* [項目](#item)
* [リスト](#list)
* [ページ（ベータ版）](#page-beta)
* [サイト](#site)
* [その他](#other)

### ドライブ項目

* [ファイルを作成](#create-a-file)
* [ファイルの作成（レガシー）](#create-a-file-legacy)
* [フォルダーの作成](#create-a-folder)
* [ファイルの取得](#get-a-file)
* [フォルダーを取得](#get-a-folder)
* [フォルダーまたはファイルの更新](#update-a-folder-or-a-file)
* [フォルダー項目の監視](#watch-folder-items)

#### ファイルを作成

このモジュールは、SharePointでファイルを作成します。 このモジュールは、ファイルを作成（レガシー）モジュールよりもパフォーマンスが優れています。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>変更を取得するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>ファイルを作成する場所の<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>および<strong>[!UICONTROL フォルダーID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>ファイルを作成する場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file] </td>
      <td><p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p></td>
  </tr>  </tbody> 
</table>



#### ファイルの作成（レガシー）

このモジュールは、SharePointでファイルを作成します。

パフォーマンスを向上させるには、[ ファイルを作成](#create-a-file) モジュールを使用することをお勧めします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>変更を取得するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>ファイルを作成する場所の<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>および<strong>[!UICONTROL フォルダーID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>ファイルを作成する場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
      <td><p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p></td>
  </tr>  </tbody> 
</table>

#### フォルダーの作成

このアクションモジュールは、SharePoint に新しいフォルダーを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>作成するフォルダーの場所を識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>フォルダーを作成する場所の<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>および<strong>[!UICONTROL フォルダーID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>フォルダーを作成する場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder name]</td> 
   <td>新しいフォルダーの名前を入力またはマッピングします。</td> 
  </tr>
  </tbody> 
</table>

#### ファイルの取得

このアクションモジュールは、指定された SharePoint ファイルを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>取得するファイルの<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL ファイル ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>ファイルの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### フォルダーを取得

このモジュールは、指定されたフォルダーに関する詳細を取得しました

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter サイト、ドライブ、およびファイル ID]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>取得するフォルダーの<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL フォルダーのパス ]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>フォルダーの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### フォルダーまたはファイルの更新

このアクションモジュールは、フォルダーまたはファイルのメタデータを更新します

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter サイト、ドライブ、およびファイル ID]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>取得するフォルダーまたはファイルの<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL フォルダーまたはアイテム ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>フォルダーの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  </tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>更新する各メタデータフィールドについて、<b>項目を追加</b>をクリックし、フィールドのパスと値を入力します。</td> 
  <tr>
</tbody> 
</table>

#### フォルダー項目の監視

このトリガーモジュールは、選択したフォルダー内の項目が更新されると、シナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>取得するファイルの場所を特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに、<strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL List ID]</strong> および<strong>[!UICONTROL folder ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するフォルダーの場所を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>1回のシナリオ実行サイクルでWorkfront Fusionが返す項目の最大数を入力します。</td> 
  <tr>
  </tr>
</tbody> 
</table>

### 項目

* [[!UICONTROL 項目をコピー]](#copy-an-item)
* [[!UICONTROL 項目の作成]](#create-an-item)
* [[!UICONTROL 項目の削除]](#delete-an-item)
* [[!UICONTROL 項目の取得]](#get-an-item)
* [詳細を取得](#get-details)
* [[!UICONTROL 項目のリスト]](#list-items)
* [[!UICONTROL 項目を移動]](#move-an-item)
* [[!UICONTROL 項目を更新]](#update-an-item)
* [[!UICONTROL 項目の監視]（予定）](#watch-items-scheduled)


#### [!UICONTROL 項目をコピー]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">サイト ID、ドライブ ID およびフォルダー ID の入力</td> 
   <td> <p>コピーする項目を含むサイトとドライブを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>コピーするアイテムの<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL ドライブ ID]</strong>および<strong>[!UICONTROL アイテム ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>「項目タイプ」フィールドで、フィールドを移動するかフォルダーを移動するかを選択します。  コピーする項目を含むサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> 項目のコピー先となるフォルダーの ID を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>項目の新しいコピーの名前を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目の作成]

このアクションモジュールは、SharePoint リストに新しい項目を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Create an Item]</td> 
   <td> <p>サイトの特定方法を選択し、項目を作成する場所を指定します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>項目を作成する<strong>[!UICONTROL サイト ID]</strong>と<strong>[!UICONTROL リスト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の作成先となるリストが含まれているサイトを選択したあと、そのリストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>新しい項目に設定する各フィールドについて、「<b>項目を追加</b>」をクリックし、フィールドのキー（フィールドを識別する）と、そのフィールドに新しい項目が持つ値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目の削除]

このアクションモジュールは、SharePoint リスト内の既存の項目を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>削除する項目を含んだサイトおよびリストを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>削除するアイテムの<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL アイテム ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>削除する項目が含まれているサイトを選択し、リストを選択したあと、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Item]

このアクションモジュールは、指定された項目のデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get an Item]</td> 
   <td> <p>取得する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>データを返す項目の<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL アイテム ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の取得元のリストが含まれるサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 詳細を取得

このモジュールは、指定されたURLから項目の詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Web URL</td> 
   <td> 詳細を取得する項目のURLを入力またはマッピングします。 </td> 
  </tr> 
</tbody> 
</table>

#### [!UICONTROL 項目をリスト]

このアクションモジュールは、指定されたリスト内のすべての項目のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Items]</td> 
   <td> <p>項目を取得するリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>項目をリストするリストの<strong>[!UICONTROL サイト ID]</strong>と<strong>[!UICONTROL リスト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>項目の取得元のリストが含まれるサイトを選択し、リストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返す項目の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目を移動]

このアクションモジュールは、SharePoint リスト内の既存の項目をコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">サイト ID、ドライブ ID およびフォルダー ID の入力</td> 
   <td> <p>移動する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>移動する項目の<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL アイテム ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>「項目タイプ」フィールドで、フィールドを移動するかフォルダーを移動するかを選択します。 コピーする項目を含むサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> 項目の移動先フォルダーの ID を入力またはマッピングします。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>移動した項目の名前を入力またはマッピングします。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目を更新]

このアクションモジュールは、SharePoint リスト内の既存の項目を更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>更新する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>更新する項目の<strong>[!UICONTROL サイト ID]</strong>、<strong>[!UICONTROL リスト ID]</strong>および<strong>[!UICONTROL アイテム ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新する項目が含まれるサイトを選択し、リストを選択して、項目を選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>新しい項目に対して更新する各フィールドについて、<b>項目を追加</b>をクリックし、フィールドのキー（フィールドを識別する）と、そのフィールドに対して項目が持つ新しい値を入力します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 項目を監視]（予定）

このトリガーモジュールは、項目が作成または変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>作成時刻（新しい項目）または変更時刻（更新された項目）のどちらでリストを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>監視するサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>監視する<strong>[!UICONTROL サイト ID]</strong>と<strong>[!UICONTROL リスト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するサイトを選択し、リストを選択します。 これらのドロップダウンは、後続のサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返す項目の最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### リスト

* [[!UICONTROL リストを作成]](#create-a-list)
* [[!UICONTROL リストを取得]](#get-a-list)
* [[!UICONTROL リストをリスト]](#list-lists)
* [[!UICONTROL リストを監視]](#watch-lists)

#### [!UICONTROL リストを作成]

このアクションモジュールは、SharePoint に新しいリストを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Site ID を入力]</td> 
   <td> <p>リストを作成するサイトを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>リストを作成する <strong>[!UICONTROL Site ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>リストを作成するサイトを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display Name]</td> 
   <td>新しいリストの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>新しいリストの説明を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Add Columns]</td> 
   <td>新しいリストに設定する各列について、<b>項目</b>を追加をクリックし、フィールドに<strong>[!UICONTROL Name]</strong>を入力し、新しい列に含める値の<strong>[!UICONTROL Type]</strong>を選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストを取得]

このアクションモジュールは、指定されたリストのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a List]</td> 
   <td> <p>取得する項目を含むサイトとリストを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>返す<strong>[!UICONTROL サイト ID]</strong>と<strong> リスト ID</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するリストが含まれるサイトを選択し、リストを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストを一覧表示]

このアクションモジュールは、指定したサイト内のすべての項目のリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Lists]</td> 
   <td> <p>リストを取得するサイトを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>返すリストを含む<strong>[!UICONTROL サイト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するリストが含まれているサイトを選択します。 ドロップダウンは、フォローしているサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すリストの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL リストを監視]

このトリガーモジュールは、リストの作成または変更時にシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>作成時刻（新しい項目）または変更時刻（更新された項目）のどちらでリストを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイト IDを入力]</td> 
   <td> <p>リストを監視するサイトを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>リストを監視する<strong>[!UICONTROL サイト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するサイトを選択します。 ドロップダウンは、ユーザーがフォローしているサイトのみを取得します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すリストの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### ページ（ベータ版）

>[!NOTE]
>
>[!DNL Microsoft Graph] のバージョン `beta` の API は変更される場合があります。 実稼動アプリケーションでのこれらの API の使用はサポートされていません。

* [ページを取得](#get-a-page)
* [リストページ](#list-pages)
* [ページを公開](#publish-a-page)
* [ページを見る](#watch-pages)

#### [!UICONTROL ページを取得]

このアクションモジュールは、指定されたページのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Page]</td> 
   <td> <p>取得するページを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> および <strong>[!UICONTROL Page ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するページを含むサイトを選択し、ページを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### リストページ

このモジュールは、すべてのページのリストを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL リスト ページ ]</td> 
   <td> <p>リストするページを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>リストするページを含むサイトの<strong>[!UICONTROL サイト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>リストするページを含むサイトを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクル中にモジュールが返す最大ページ数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### ページを公開

このアクションモジュールは、選択したページの最新バージョンを公開します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ページを公開]</td> 
   <td> <p>公開するページを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> および <strong>[!UICONTROL Page ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>公開するページを含むサイトを選択してから、ページを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### ページを見る

このトリガーモジュールは、指定したサイトでページが変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL サイト IDを入力]</td> 
   <td> <p>リストするページを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>監視するページを含むサイトの<strong>[!UICONTROL サイト ID]</strong>を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>監視するページを含むサイトを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオ実行サイクル中にモジュールが返す最大ページ数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### サイト

* [[!UICONTROL サイトを取得]](#get-a-site)
* [[!UICONTROL サイトを検索]](#search-sites)

#### [!UICONTROL サイトを取得]

このアクションモジュールは、指定されたサイトのデータを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Site]</td> 
   <td> <p>取得するページを識別する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p><strong>[!UICONTROL Site ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>取得するサイトを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL サイトを検索]

このアクションモジュールは、指定したパラメーターでサイトを検索します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword of Display Name]</td> 
   <td> <p>サイトを検索する検索語を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すサイトの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### その他

* [変更を取得](#get-changes)
* [API 呼び出しを実行](#make-an-api-call)
* [イベントを監視する](#watch-events)

#### 変更を取得

このモジュールは、SharePoint フォルダーで行われた追加、更新、および削除を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>更新する項目を含むサイトとドライブを特定する方法を選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>表示されるフィールドに、<strong>[!UICONTROL Site ID]</strong>、<strong>[!UICONTROL Drive ID]</strong>、<strong>[!UICONTROL Folder ID]</strong> を入力またはマッピングします。</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>更新する項目が含まれるサイトを選択し、ドライブを選択して、フォルダーを選択します。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> トークンは、モジュールが変更の取得を開始する時点を識別します。  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL API 呼び出しの実行]

このモジュールでは、カスタム API 呼び出しを実行できます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Microsoft SharePoint Online アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Microsoft SharePoint OnlineをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p><code>https://graph.microsoft.com</code> からの相対パスを入力します。 例：<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。 例えば、<code>{"Content-type":"application/json"}</code>。 Workfront Fusion は認証ヘッダーを追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>API 呼び出しで送信するデータのタイプを選択します。</td> 
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

#### イベントを監視する

このインスタントトリガーモジュールは、SharePoint で項目が追加、更新、または削除されたときにシナリオを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
  <!--
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to Workfront Fusion, see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
-->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>既存のWebhookを選択するか、「追加」をクリックして接続を入力し、新しいWebhookを作成します。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
