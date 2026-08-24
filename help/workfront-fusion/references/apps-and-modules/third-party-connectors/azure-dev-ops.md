---
title: Azure DevOps モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Azure DevOps] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion
exl-id: c0919a9a-ce99-485c-9627-45353741f6d8
TQID: https://experienceleague.adobe.com/RFI6MFgF-C1Cnn0bvjOLVf3qahyRblEp4dtypNrxqzE
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 0b7298ce53bf59695ce52cb46cb8d25b6ede5fc8
workflow-type: tm+mt
source-wordcount: 2645
ht-degree: 57%

---

# [!DNL Azure DevOps] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Azure DevOps] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

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

[!DNL Azure DevOps] モジュールを使用するには、[!DNL Azure] DevOps アカウントが必要です。

## [!DNL Azure DevOps] API情報

Azure DevOps コネクタでは、次の機能が使用されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v5.1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.29.33</td> 
  </tr>
 </tbody> 
</table>

## [!DNL Azure DevOps] を Workfront Fusion に接続 {#connect-azure-devops-to-workfront-fusion}

* [EntraAppを使用してAzure DevOpsをWorkfront Fusionに接続する](#connect-azure-devops-to-workfront-fusion-using-entraapp)
* [サービスプリンシパルを使用してAzure DevOpsをWorkfront Fusionに接続する](#connect-azure-devops-to-workfront-fusion-using-a-service-principal)

### EntraAppを使用してAzure DevOpsをWorkfront Fusionに接続する

1. [!DNL Azure DevOps] モジュールをシナリオに追加します。
1. 「[!UICONTROL 接続]」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 「[!UICONTROL 接続タイプ ]」フィールドで、使用する接続タイプを選択します。

   >[!NOTE]
   >
   >[!UICONTROL [!DNL Azure DevOps] （EntraApp） ]を使用すると、接続のすべてのスコープをリクエストできます。

1. 次のフィールドに入力します。

   <table style="table-layout:auto">
      <tr>
            <td>[!UICONTROL Connection name]</td>
            <td>作成する接続の名前を入力します。</td>
      </tr>
      <tr>
            <td>[!UICONTROL Organization]</td>
            <td>[!DNL Azure DevOps] アプリケーションを作成した組織の名前を入力します。</td>
      </tr>
      <tr>
            <td>[!UICONTROL App ID]</td>
            <td>接続先のDevOps アプリケーションのIDを入力します。</td>
      </tr>
      <tr>
            <td>[!UICONTROL Client Secret]</td>
            <td>接続先のDevOps アプリケーションのクライアントシークレットを入力します。</td>
      </tr>
      <tr>
            <td>[!UICONTROLすべてのスコープをリクエスト ]</td>
            <td>[!DNL Azure DevOps] （EntraApp）接続タイプを使用している場合は、このオプションを有効にして、接続のすべてのスコープを要求します。</td>
      </tr>
   </table>

1. Azure DevOps アプリ IDまたはクライアントシークレットを入力するには、<b>詳細設定を表示</b>をクリックし、開いているフィールドに入力します。
1. 「**[!UICONTROL 続行]**」をクリックして接続の設定を終了し、シナリオの作成を続けます。

### サービスプリンシパルを使用してAzure DevOpsをWorkfront Fusionに接続する

個人アカウントの代わりにサービスプリンシパル（アプリケーション API接続）を使用する接続を作成できます。 これは、接続を特定のユーザーではなく、アプリケーションまたはサービス IDとして実行する場合に便利です。 これは、例えば、その人が会社を辞めたり、パスワードを変更したりしても、統合が壊れないことで役立つ可能性があります。

この接続タイプは、すべてのAzure DevOps モジュールで使用できます。

>[!NOTE]
>
>サービスプリンシパル認証は、すべてのAzure DevOps機能をサポートしているわけではありません。 ユーザーライセンスの管理など、少数の管理者レベルのアクションでは、引き続き個人用アカウント接続が必要です。 作業項目、ボード、リポジトリ、またはパイプラインに対してのみ必要な場合は、サービスプリンシパル認証を使用します。

* [サービスプリンシパルを使用してAzure DevOpsをWorkfront Fusionに接続するための前提条件](#prerequisites-to-connecting-azure-devops-to-workfront-fusion-using-a-service-principal)
* [Microsoft Entra IDでアプリ登録を作成する](#create-the-app-registration-in-microsoft-entra-id)
* [クライアントシークレットの作成](#create-a-client-secret)
* [接続の詳細を収集](#collect-your-connection-details)
* [Azure DevOps組織にサービスプリンシパルを追加します](#add-the-service-principal-to-your-azure-devops-organization)
* [接続の作成](#create-the-connection)

#### サービスプリンシパルを使用してAzure DevOpsをWorkfront Fusionに接続するための前提条件

この接続を作成するには、次のものが必要です。

* **グローバル管理者**&#x200B;または&#x200B;**アプリケーション管理者**&#x200B;がMicrosoft Entra IDでアクセスし、アプリを登録します。 このアクセス権をお持ちでない場合は、IT チームまたはID チームの誰かにその手順を完了するように依頼してください。
* **Project Collection Administrator**&#x200B;は、Azure DevOps組織でアクセスし、サービスプリンシパルをメンバーとして追加します。 これは、多くの場合、Microsoft Entra IDを管理する人とは異なる人物です。
* Azure DevOps組織の名前。 AzureのDevOps URL: `dev.azure.com/<your organization name>`で確認できます。

#### Microsoft Entra IDでアプリ登録を作成する

1. [!DNL Microsoft Entra]管理センターにログインします。
1. **[!UICONTROL アプリ登録]** > **[!UICONTROL 新規登録]**&#x200B;に移動します。
1. アプリに明確で認識可能な名前を付けます。 例：`Workfront Fusion Azure DevOps Integration`
1. **[!UICONTROL リダイレクト URI]**&#x200B;を空白のままにします。 この接続には、ブラウザーを介したログインは含まれません。
1. **[!UICONTROL 登録]**&#x200B;を選択します。
1. 引き続き[ クライアントシークレットの作成](#create-a-client-secret)を続行します。

#### クライアントシークレットの作成

1. 新しいアプリの登録で、**[!UICONTROL 証明書とシークレット]**&#x200B;に移動します。
1. **[!UICONTROL 新しいクライアントシークレット]**&#x200B;を選択し、説明を追加して、有効期限を選択します。
1. 「**[!UICONTROL 追加]**」を選択します。
1. 秘密鍵の&#x200B;**[!UICONTROL 値]**&#x200B;をすぐにコピーします。 1回だけ表示されます。 コピーする前に移動する場合は、新しいコピーを作成する必要があります。
1. 引き続き[接続の詳細を収集](#collect-your-connection-details)してください。

#### 接続の詳細を収集

1. アプリ登録の&#x200B;**[!UICONTROL 概要]** ページから、次の値に注意してください。 モジュールで接続を作成する際に、これらの項目を入力します。

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
     <tr>
      <td role="rowheader">[!UICONTROL Organization]</td>
      <td>Azure DevOps組織名。 例えば、URLが<code>dev.azure.com/yourorg</code>の場合は、<code>yourorg</code>と入力します。</td>
     </tr>
    </tbody>
   </table>

   >[!NOTE]
   >
   >アプリ登録の&#x200B;**API権限**&#x200B;領域をスキップできます。 そこにAzure DevOpsを追加した場合、**委任された権限**&#x200B;のみが使用できます。 **アプリケーション権限**&#x200B;がグレー表示されます。 Azure DevOpsでは、この方法でのアクセス許可はサポートされていないため、これは予想されます。 代わりに、次のパートでAzure DevOps内で直接アクセスが許可されます。

1. 引き続き[Azure DevOps組織にサービスプリンシパルを追加](#add-the-service-principal-to-your-azure-devops-organization)。

#### Azure DevOps組織にサービスプリンシパルを追加します

Microsoft Entra IDにアプリを登録すると、そのIDのみが作成されます。 Azure DevOps データへのアクセス権はまだアプリに付与されません。 この手順により、そのアクセス権が付与されます。

1. Azure DevOps組織（`dev.azure.com/<your organization name>`）にログインします。
1. 左下の「**[!UICONTROL 組織の設定]**」を選択し、「**[!UICONTROL ユーザー]**」を選択します。
1. 「**[!UICONTROL ユーザーを追加]**」を選択します。
1. 検索ボックスで、アプリの表示名（アプリ登録時に指定した名前）で検索します。 クライアント IDで検索しないでください。
1. アクセスレベルを選択します。

   * **[!UICONTROL Basic]**&#x200B;は、通常、作業項目、ボード、リポジトリの読み取りと書き込みに十分です。
   * ワークフローで、セットアップの一環としてアジャイル、スクラム、カスタムテンプレートなどの利用可能なプロセスを参照する必要がある場合は、代わりに&#x200B;**[!UICONTROL プロジェクトコレクション管理者]** グループにサービスプリンシパルを追加します。 より幅広いレベルのアクセス権を持つため、その機能が必要な場合にのみ許可してください。

1. 組織の通常のアクセス方法に従って、必要な特定のプロジェクトまたはプロジェクトにサービスプリンシパルを割り当てます。
1. 「**[!UICONTROL 追加]**」を選択します。
1. 引き続き[接続を作成](#create-the-connection)します。

#### 接続の作成

1. モジュールの接続設定画面で、**[!UICONTROL サービスプリンシパル]**&#x200B;接続タイプを選択します。
1. 以下の情報を入力します。

   * [!UICONTROL  テナント ID]
   * [!UICONTROL クライアント ID]
   * [!UICONTROL クライアント秘密鍵]
   * [!UICONTROL 組織]

1. 接続を保存します。

   すべてが正しく設定されていれば、接続は正常に検証されます。

## [!UICONTROL Azure DevOps] モジュールとそのフィールド

[!DNL Azure DevOps] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Azure DevOps]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

#### [!UICONTROL 作業項目の監視]

このインスタントトリガーモジュールは、[!UICONTROL Azure DevOps] でレコードが追加、更新または削除されたときにシナリオを実行します。

このモジュールは、レコードに関連付けられた標準フィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>モジュールの web フックを選択または追加します。</p> <p>トリガーモジュールのWebhookについて詳しくは、<a href="/help/workfront-fusion/references/modules/webhooks-reference.md" class="MCXref xref"> インスタントトリガー（webhook） </a>を参照してください。</p> <p>Web フックの作成方法については、<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Web フック</a>を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [レコードの作成](#create-a-record)
* [カスタム API 呼び出し](#custom-api-call)
* [添付ファイルのダウンロード](#download-an-attachment)
* [作業項目のリンク](#link-work-items)
* [レコードの読み取り](#read-record)
* [作業項目の更新](#update-a-work-item)
* [[!UICONTROL 添付ファイルをアップロード]](#upload-an-attachment)

#### [!UICONTROL レコードの作成]

このアクションモジュールは、新しいプロジェクトまたは作業アイテムを作成します。

モジュールは、新しく作成された作業アイテムのオブジェクト ID、または新しく作成されたプロジェクトの URL とステータスコードを出力します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>作業アイテムを作成するか、プロジェクトを作成するかを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Project]</strong> </p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Name]</strong>：新しいプロジェクトの名前を入力するか、マップします。</p> </li> 
       <li> <p><strong>[!UICONTROL Description]</strong>：新しいプロジェクトの説明を入力またはマッピングします。 </p> </li> 
       <li> <p><strong>[!UICONTROL Visibility]</strong>：プロジェクトを公開または非公開にするかを選択します。 ユーザーが非公開プロジェクトとやり取りするには、組織にサインインし、プロジェクトへのアクセス権を付与されている必要があります。 公開プロジェクトは、組織にサインインしていないユーザーに表示されます。</p> </li> 
       <li> <p><strong>[!UICONTROL Version control]</strong>：プロジェクトでバージョン管理に[!DNL Git]または[!UICONTROL Team Foundation Version Control (TFCV)]を使用するかどうかを選択します。</p> </li> 
       <li> <p><strong>[!UICONTROL Work item process]</strong>：プロジェクトに使用する作業プロセスを選択します。 [!UICONTROL Basic]、[!UICONTROL Scrum]、[!UICONTROL Capability Maturity Model Integration (CMMI)]、[!UICONTROL Agile]を選択できます。</p> <p>[!DNL Azure DevOps] プロセスについて詳しくは、[!DNL Azure DevOps] ドキュメントの<a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/choose-process?view=azure-devops&amp;tabs=basic-process"> デフォルトプロセスとプロセステンプレート </a>を参照してください。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Work item]</strong> </p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Project]</strong>：作業アイテムを作成するプロジェクトを選択します。</p> </li> 
       <li> <p><strong>[!UICONTROL Work item type]</strong>：作成する作業アイテムのタイプを選択します。</p> </li> 
       <li> <p><strong>[!UICONTROLその他のフィールド ]</strong>：これらのフィールドに、特定のプロパティに対して作業項目に含める値を入力します。 使用可能なフィールドは、作業アイテムのタイプによって異なります。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL カスタム API 呼び出し]

このアクションモジュールは、[!DNL Azure DevOps] API に対して認証済みのカスタム呼び出しを実行します。 これにより、他の [!DNL Azure DevOps] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントへの接続に使用するベース URL を選択またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Relative URL]</td> 
   <td> <p>この API 呼び出しの接続先となる相対 URL を入力します。</p> <p><b>例：</b><code>{organization}/_apis[/{area}]/{resource}</code> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>この API 呼び出しの接続先となる [!DNL Azure DevOps] API のバージョンを選択またはマッピングします。 バージョンが選択されていない場合、Workfront Fusionは[!DNL Azure DevOps] API バージョン 5.1に接続します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>API 呼び出しのクエリを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"name":"something-urgent"}</code></p> </td> 
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

#### [!UICONTROL 添付ファイルのダウンロード]

このアクションモジュールは、添付ファイルをダウンロードします。

このモジュールは、添付ファイルのファイルコンテンツを返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment URL]</td> 
   <td> <p>ダウンロードする添付ファイルの URL を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 作業アイテムをリンク]

このアクションモジュールは、2 つの作業アイテムをリンクし、それらの間の関係を定義します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td>別の作業アイテムをリンクするメイン作業アイテムの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Linked work item ID]</td> 
   <td>メインの作業アイテムにリンクする作業アイテムの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Link Type]</td> 
   <td> <p>リンクする作業アイテム間の関係を定義します。</p> <p>詳細については、[!UICONTROL Azure DevOps] ドキュメントの「<a href="https://docs.microsoft.com/en-us/azure/devops/boards/queries/link-type-reference?view=azure-devops"> リンクタイプのリファレンスガイド </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment]</td> 
   <td>コメントのテキストを入力またはマッピングします。 これは、リンクの根拠や意図を説明するのに役立ちます。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの読み取り]

このアクションモジュールは、[!DNL Azure DevOps] の単一レコードからデータを読み取ります。

レコードの ID を指定します。

このモジュールは、レコードの ID および関連するフィールドと共に、接続を介してアクセスされるカスタムフィールドとその値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>プロジェクトを読み取るか作業アイテムを読み取るかを選択</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL プロジェクト ]</strong>：読み込むプロジェクトを選択します。</p> </li> 
     <li> <p><strong>[!UICONTROL Work item]</strong>：読み取る作業アイテムを含むプロジェクトを選択し、作業アイテムのタイプを選択します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>このモジュールの出力バンドルに含める情報を選択します。 使用可能なフィールドは、作業アイテムのタイプによって異なります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>読み取るレコードの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 作業アイテムを更新]

このアクションモジュールは、ID を使用して既存の作業アイテムを更新します。

このモジュールは、更新された作業アイテムの ID を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td>更新する作業アイテムを含むプロジェクトを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work Item Type]</td> 
   <td> <p>更新する作業アイテムのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other Fields]</td> 
   <td>これらの各フィールドに、特定のプロパティに対して作業アイテムに与える値を入力します。 使用可能なフィールドは、作業アイテムのタイプによって異なります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td>更新する作業アイテムの ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 添付ファイルをアップロード]

このアクションモジュールは、ファイルをアップロードし、作業アイテムに添付します。

モジュールは、添付ファイルの添付ファイル ID とダウンロード URL を返します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project] </td> 
   <td> <p>添付ファイルをアップロードするプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td> <p>添付ファイルをアップロードする作業アイテムの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment]</td> 
   <td>アップロードされた添付ファイルに追加するコメントのテキストを入力します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file] </td> 
   <td>前のモジュールからソースファイルを選択するか、ソースファイルの名前と内容を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### 検索

#### [!UICONTROL 作業アイテムのリスト]

このアクションモジュールは、[!DNL Azure DevOps] プロジェクトの特定のタイプのすべての作業アイテムを取得します。

このモジュールは、主な作業アイテムの ID と関連するフィールドのほか、接続でアクセスするカスタムフィールドと値を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Azure DevOps] アカウントをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Workfront Fusionに[!DNL Azure DevOps]を接続する]</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td>作業アイテムを取得するプロジェクトを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item type]</td> 
   <td> <p>取得する作業アイテムのタイプを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>モジュールの出力に表示するプロパティを選択します。 使用可能なフィールドは、取得する作業アイテムのタイプによって異なります。 1 つ以上のプロパティを選択する必要があります。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>1回の実行サイクルでWorkfront Fusionが返す作業項目の最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
