---
title: Adobe Target モジュール
description: ' [!DNL Adobe Workfront Fusion] シナリオ内で、 [!DNL Adobe Target], as well as connect it to multiple third-party applications and services. [!DNL Adobe Target]  モジュールを使用するワークフローを自動化すると、レコードの作成、読み取り、更新および削除、特定のタイプのすべてのレコードのリスト作成、指定した条件に基づくレコードの検索または  [!DNL Adobe Target]  API へのカスタム API 呼び出しの実行を行うことができます。'
author: Becky
feature: Workfront Fusion
exl-id: f3c1ed7b-b69b-478a-8240-1a2ab89e11e5
source-git-commit: 899fc717f5107433d6f1aea31c4d079243a85822
workflow-type: tm+mt
source-wordcount: '2259'
ht-degree: 82%

---

# [!DNL Adobe Target] モジュール

[!DNL Adobe Workfront Fusion] シナリオ内で、[!DNL Adobe Target] を使用し、複数のサードパーティのアプリケーションやサービスに接続するワークフローを自動化できます。[!DNL Adobe Target] モジュールを使用すると、レコードの作成、読み取り、更新または削除、特定のタイプのすべてのレコードのリスト作成、指定した条件に基づくレコードの検索または [!DNL Adobe Target] API へのカスタム API 呼び出しの実行を行うことができます。


シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
      <td>
        <p>[!UICONTROL Pro] 以降</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
      <td>
        <p>[!UICONTROL Plan]、[!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td>
      <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>従来のライセンス要件：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration] </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">製品</td>
      <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランをご利用の場合、この記事で説明されている機能を使用するには、組織は [!DNL Adobe Workfront] に加えて [!DNL Adobe Workfront Fusion] も購入する必要があります。[!DNL Workfront Fusion] は、[!DNL Workfront] [!UICONTROL Ultimate] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td>
    </tr>
    </tr>
  </tbody>
</table>


ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## 前提条件

[!DNL Adobe Target] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!DNL Adobe Target] アカウントが必要です。

## Adobe Target API の情報

Adobe Target コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.7.33</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Adobe Target] への接続の作成

>[!IMPORTANT]
>
>2024 年 6 月 3 日（PT）以降に作成された接続では、Adobe Target サーバー間接続が必要になります。
>
>* 既存のサービスアカウント接続は、2025 年 1 月まで引き続き機能します。 サービスアカウント接続は、2024 年 1 月までにAdobe Target サーバー間接続に置き換える必要があります。
>* Adobe Target サーバー間接続を作成するには、組織の開発者である必要があります。 デベロッパーの役割は、Adobe Admin Consoleで設定されます。

[!DNL Adobe Target] モジュールへの接続を作成するには、以下を実行します。

1. 任意のモジュールで、「接続」ボックスの横にある **[!UICONTROL 追加]** をクリックします。

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
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>サービスアカウント接続を作成するか、Adobe Target サーバー間接続を作成するかを選択します。<p><b> 重要 </b>:2024 年 6 月 3 日（PT）以降に作成された接続では、Adobe Target サーバー間接続が必要です。 既存のサービスアカウント接続は、2025 年 1 月まで引き続き機能します。 サービスアカウント接続は、2024 年 1 月までにAdobe Target サーバー間接続に置き換える必要があります。
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!DNL Adobe] クライアント ID を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] クライアントの秘密鍵を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>[!DNL Adobe] テクニカルアカウント ID を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>[!DNL Adobe] 組織 ID を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Tenant]</td>
        <td>
          <p> テナントを見つけるには、[!DNL Adobe Experience Cloud] にログインして、[!DNL Target] を開き、[!DNL Target] カードをクリックします。URL サブドメインで指定されているように、テナント ID の値を使用します。</p>
          <p>例えば、[!DNL Adobe Target] ログイン時に URL が <code>&lt;https://mycompany.experiencecloud.adobe.com/...></code> の場合、テナント ID は「mycompany」になります。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>入力 <code>ent_marketing_sdk</code>       </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>[!DNL Adobe Developer Console] で資格情報が作成された際に生成された秘密鍵を入力します。 </p>
          <p>秘密鍵または証明書を抽出するには：</p>
          <ol>
            <li value="1">
              <p><b>[!UICONTROL Extract]</b> をクリックします。</p>
            </li>
            <li value="2">
              <p>抽出するファイルのタイプを選択します。</p>
            </li>
            <li value="3">
              <p>秘密鍵または証明書を含むファイルを選択します。</p>
            </li>
            <li value="4">
              <p>ファイルのパスワードを入力します。</p>
            </li>
            <li value="5">
              <p><b>[!UICONTROL Save]</b> をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Target] モジュールとそのフィールド

[!DNL Adobe Target] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Target] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)

* [検索](#searches)


### アクション

* [[!UICONTROL レコードを作成]](#create-a-record)

* [[!UICONTROL カスタム API 呼び出しの実行]](#make-a-custom-api-call)

* [[!UICONTROL レコードを削除]](#delete-a-record)

* [[!UICONTROL レコードの読み取り]](#read-a-record)

* [[!UICONTROL レコードを更新]](#update-a-record)


#### [!UICONTROL レコードを作成]

このアクションモジュールは、AB または XT のアクティビティ、オファーまたはオーディエンスを作成します。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続を作成を参照してください。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>
      <p>作成するレコードのタイプを選択します。</p>
      <ul>
        <li>
        <b> プロパティ </b><p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Properties/operation/createProperty"> プロパティの作成 </a> を参照してください。</p>
        </li>
        <li>
        <b> オファーの推奨事項 </b><p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Offers/operation/createOffer"> 新しい recs オファーの作成 </a> を参照してください。</p>
        </li>
        <li>
          <b>[!UICONTROL オファー JSON]</b>
          <p><a href="#offer-fields" class="MCXref xref" >オファーフィールド</a>に進みます。</p>
        </li>
        <li>
          <b>[!UICONTROL オファーコンテンツ ]</b>
          <p><a href="#offer-fields" class="MCXref xref" >オファーフィールド</a>に進みます。</p>
        </li>
        <li>
        <b> 環境 </b><p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Environments/operation/createEnvironment"> 環境の作成 </a> を参照してください。</p>
        </li>
        <li>
          <b>[!UICONTROL オーディエンス ]</b>
          <p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Audiences/operation/createAudience_1_1"> オーディエンスの作成 </a> を参照してください。</p>
        </li>
        <li>
          <b>[!UICONTROL AB アクティビティ ]</b>
          <p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_4_1">AB アクティビティを作成 </a> を参照してください。</p>
        </li>
        <li>
          <b>[!UICONTROL XT アクティビティ ]</b>
          <p><a href="#xt-activity-fields" class="MCXref xref" >XT アクティビティフィールド</a>に進みます。</p>
        </li>
        <li>
          <b>[!UICONTROL AP アクティビティ ]</b>
          <p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_2">AP アクティビティの作成 </a> を参照してください。</p>
        </li>
        <li>
          <b>[!UICONTROL 応答トークン ]</b>
          <p>フィールドについて詳しくは、Adobe Target API ドキュメントの <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Response-tokens/operation/createResponseToken"> 応答トークンの作成 </a> を参照してください。</p>
        </li>
      </ul>
    </td>
  </tr>
</tbody>
</table>

<!--

##### AB Activity fields

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Enter or map a name for this activity. The name can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Options]</td>
      <td>
        <p>For each option that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Option local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the option across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the option. The name must be no more than 250 characters.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Offer ID]</b>
            </p>
          </li>
          <li>
            <p>Select or map the Offer associated with the option.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Mboxes]</td>
      <td>
        <p>For each Mbox that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>For each audience that you want to add to the Mbox, click <b>[!UICONTROL Add item]</b> and select the Audience ID.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the Location. The name must be no more than 250 characters.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selectors]</td>
      <td>
        <p>For each selector that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>For each audience that you want to add to the Mbox, click <b>[!UICONTROL Add item]</b> and select the Audience ID.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Selector]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the Location. The name must be no more than 250 characters.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Experiences]</td>
      <td>
        <p>A list of locations on the page where the content offer is served. A location contains the following:
</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Experience local ID]</b>
            </p>
            <p>Enter or map the ID of the experience</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map the name of the experience
</p>
          </li>
          <li>
            <p><b>[!DNL Audience IDs]</b>
            </p>
            <p>For each audience that you want to see the experience, click <b>[!UICONTROL Add item]</b> and enter the Audience ID.
</p>
          </li>
          <li>
            <p><b>[!UICONTROL Visitor Percentage]</b>
            </p>
            <p>Enter or map the percentage of visitors that is allocated to the experience</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Metrics]</td>
      <td><p>For details on metrics, see <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_4_1">Create AB activity</a> in the Adobe Target API documentation.</p> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Third Party ID]</td>
      <td>Enter or map an ID to identify this activity. You can choose this ID. This ID must not be the same as another activity, and can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts at]</td>
      <td>Enter or map the date and time to start the activity in the format <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends at]</td>
      <td>Enter or map the date and time to end the activity in the format <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>
        <p>Enter or map the state of the activity.</p>
        <ul>
          <li>
            <p>[!UICONTROL Approved]</p>
          </li>
          <li>
            <p>[!UICONTROL Deactivated]</p>
          </li>
          <li>
            <p>[!UICONTROL Paused]</p>
          </li>
          <li>
            <p>[!UICONTROL Saved] </p>
          </li>
          <li>
            <p>[!UICONTROL Deleted]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Priority]</td>
      <td>Enter a number that defines the priority of the activity. Higher numbers have higher priority. This value must be between 0 and 999. The default value is 5.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Auto-allocate traffic]</td>
      <td>
        <p>Enable this option to auto-allocate traffic. Auto-allocating sends more traffic to the more successful experience.</p>
        <p>Select or map the evaluation criteria by which to judge which experience is more successful.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Enter or map the workspace that the activity is associated with</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Property IDs] </td>
      <td>For each property that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and select or map the property's ID.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Reporting audiences]</td>
      <td>
        <p>For each reporting audience that you want to add to the activity, click [!UICONTROL Add item] and enter the following information:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Reporting Audience local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the Reporting Audience across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Audience ID]</b>
            </p>
            <p>Enter or map the Segment to be used in reporting</p>
          </li>
          <li>
            <p><b>[!UICONTROL Metric local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the metric across API requests.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

-->

##### XT アクティビティフィールド

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>このアクティビティの名前を入力またはマッピングします。名前は 250 文字以下にする必要があります。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Options]</td>
      <td>
        <p>アクティビティに追加する各オプションで、<b>[!UICONTROL Add item]</b> をクリックして、次のフィールドに入力します。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Option local ID]</b>
            </p>
            <p>API リクエストをまたいでオプションを追跡するために使用する文字列を入力またはマッピングします。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>オプションの名前を入力またはマッピングします。名前は 250 文字以下にする必要があります。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Offer ID]</b>
            </p>
          </li>
          <li>
            <p>オプションに関連付けられたオファーを選択またはマッピングします。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Locations]</td>
      <td>
        <p>アクティビティに追加する mbox ごとに、<b>[!UICONTROL Add item]</b> をクリックして、次のフィールドに入力します。</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>mbox に追加するオーディエンスごとに、<b>[!UICONTROL Add item]</b> をクリックして、「オーディエンス ID 」を選択します。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>API リクエスト全体で場所を追跡するために使用する文字列を入力またはマッピングします。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>場所の名前を入力またはマッピングします。名前は 250 文字以下にする必要があります。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Experiences]</td>
      <td>
        <p>コンテンツオファーが提供されるページ上の場所のリスト。場所には次の情報が含まれます。
</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Experience Local ID]</b>
            </p>
            <p>エクスペリエンスの ID の入力またはマッピング</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>エクスペリエンスの名前を入力またはマッピング

</p>
          </li>
          <li>
            <p><b>[!DNL Audience IDs]</b>
            </p>
            <p>エクスペリエンスを表示するオーディエンスごとに、<b>[!UICONTROL Add item]</b> をクリックして、オーディエンス ID を入力します。

</p>
          </li>
          <li>
            <p><b>[!UICONTROL Visitor Percentage]</b>
            </p>
            <p>エクスペリエンスに割り当てられる訪問者の割合を入力またはマッピングします</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Metrics]</td>
      <td> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Third Party ID]</td>
      <td>このアクティビティを識別する ID を入力またはマッピングします。この ID を選択できます。この ID は、他のアクティビティと同じにすることはできません。また、250 文字以下にする必要があります。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts at]</td>
      <td>アクティビティを開始する日付と時刻を <code>YYYY-MM-DD hh:mm:ss.z</code> 形式で入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends at]</td>
      <td>アクティビティを終了する日付と時刻を <code>YYYY-MM-DD hh:mm:ss.z</code> 形式で入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>
        <p>アクティビティの状態を入力またはマッピングします。</p>
        <ul>
          <li>
            <p>[!UICONTROL Approved]</p>
          </li>
          <li>
            <p>[!UICONTROL Deactivated]</p>
          </li>
          <li>
            <p>[!UICONTROL Paused]</p>
          </li>
          <li>
            <p>[!UICONTROL Saved] </p>
          </li>
          <li>
            <p>[!UICONTROL Deleted]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Priority]</td>
      <td>アクティビティの優先度を定義する数値を入力します。数値が大きいほど、優先度が高くなります。この値は 0 ～ 999 の範囲で設定する必要があります。デフォルト値は 5 です。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Auto-allocate traffic]</td>
      <td>
        <p>トラフィックを自動配分するには、このオプションを有効にします。自動配分により、より多くのトラフィックがより効果の高いエクスペリエンスに送信されます。</p>
        <p>どのエクスペリエンスがより効果が高いかを判断するための評価基準を選択またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>アクティビティが関連付けられているワークスペースを入力またはマッピングします</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Property IDs] </td>
      <td>アクティビティに追加する各プロパティで、「<b>[!UICONTROL Add item]</b>」をクリックして、プロパティの ID を選択またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Reporting audiences]</td>
      <td>
        <p>アクティビティに追加するレポートオーディエンスごとに、「[!UICONTROL Add item]」をクリックし、次の情報を入力します。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Reporting Audience local ID]</b>
            </p>
            <p>API リクエスト全体でレポートオーディエンスを追跡するために使用する文字列を入力またはマッピングします。</p>
          </li>
          <li>
            <p><b>[!UICONTROL Audience ID]</b>
            </p>
            <p>レポートで使用するセグメントを入力またはマッピングします</p>
          </li>
          <li>
            <p><b>[!UICONTROL Metric local ID]</b>
            </p>
            <p>API リクエスト全体で指標を追跡するために使用する文字列を入力またはマッピングします。</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

##### オファーフィールド

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>このアクティビティの名前を入力またはマッピングします。名前は 250 文字以下にする必要があります。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Content]</td>
      <td>
        <p>ユーザーに表示するオファーのコンテンツを入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>オファーに関連付けられているワークスペースの ID を入力またはマッピングします。空白の場合、オファーはアカウントのデフォルトのワークスペースに関連付けられます。この機能は、[!DNL Target] Premium アカウントのみに適用します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>このオファーが変更された日時を入力またはマッピングします。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--

##### Audience fields

>[!NOTE]
>
>Audiences created through Workfront Fusion can only be edit in Fusion or through the API. They cannot be edited from within Target.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Enter or map a name for this audience. The name can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Description]</td>
      <td>
        <p>Enter or map a description of this audience.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Origin]</td>
      <td>
        <p>Select whether this audience's origin is from Target or from the cloud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Target Rule]</td>
      <td>
        <p>Enable the toggle to make rules AND, that is, all rules must be applied.</p>
        <p>For each rule that you want to apply to the audience, click <b>[!UICONTROL Add item]</b> and enter the JSON of the rule you want to apply. </p>
        <div class="example"><span class="autonumber"><span><b>Example: </b></span></span>
          <p>Example 1:</p>
          <p ><code>&lbrace;</code></p>
                    <p ><code>                "page": "url",</code>
                    </p>
                    <p><code>                "equals":&lbrack;</code>
                    </p>
                    <p ><code>                    "http://www.myhomepage.com/"</code>
                    </p>
                    <p><code>                &rbrack;</code>
                    </p>
                    <p ><code>            &rbrace;,</code>
                    </p>
                    <p>Example 2</p>
                    <p ><code>            &lbrace;</code>
                    </p>
                    <p><code>                "geo": "region",</code>
                    </p>
                    <p><code>                "matches": &lbrack;</code>
                    </p>
                    <p ><code>                    "california"</code>
                    </p>
                    <p ><code>                &rbrack;</code>
                    </p>
                    <p ><code>            &rbrace;</code>
                    </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>Enter or map the ID of the workspace associated with the audience. If left blank, the offer is associated with the default workspace of the account. This functionality applies only to [!DNL Target Premium] accounts.</p>
      </td>
    </tr>
  </tbody>
</table>

-->

#### [!UICONTROL カスタム API 呼び出しの実行]

このモジュールは、[!DNL Adobe Target] API に対してカスタム API 呼び出しを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL [!DNL Target] Base URL]</td>
      <td>[!DNL Target] ベース URL を入力またはマッピングします。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Path]</p>
      </td>
      <td>
        <p>{baseURL}/ に対する相対パスの入力</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] 認証ヘッダーおよび x-api-key ヘッダーを自動的に追加します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>リクエストクエリ文字列を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合は、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

#### [!UICONTROL レコードの削除]

このアクションモジュールは、1 つの AB アクティビティ、XT アクティビティ、オファーまたはオーディエンスを削除します。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続を作成を参照してください。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>削除するレコードのタイプを選択します。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record ID]</td>
    <td>削除するレコードの ID を入力またはマッピングします。</td>
  </tr>
</tbody>
</table>

#### [!UICONTROL レコードの読み取り]

このアクションモジュールは、1 つのアクティビティ、オファー、オーディエンス、プロパティまたはレポートのデータを取得します。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続を作成を参照してください。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>読み取るレコードのタイプを選択します。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record ID]</td>
    <td>読み取るレコードの ID を入力またはマップします。</td>
  </tr>
</tbody>
</table>

#### [!UICONTROL レコードの更新]

このアクションモジュールは、Target のレコードを更新します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>
        <p>更新するレコードのタイプを選択します。</p>
       </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL フィールド名 ]</td>
      <td>更新するフィールドを選択します。 フィールドが下に表示されます。
          <p>フィールドについて詳しくは、<a href="https://developer.adobe.com/target/administer/admin-api/">Adobe Target API ドキュメント </a> を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

### 検索

* [[!UICONTROL レコードの取得]](#get-records)

* [[!UICONTROL 検索]](#search)


#### [!UICONTROL レコードの取得]

この検索モジュールは、選択したタイプのレコードのリストを取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>更新するレコードのタイプを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Sort by]</td>
      <td>並べ替えるフィールドごとに、「<b>[!UICONTROL Add item]</b>」をクリックして、フィールドを選択して、返される結果を昇順または降順のどちらにするかを選択します。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts At]</td>
      <td>
        <p>レコードを取得する最も早い日付を入力します。 </p>
        <p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends At]</td>
      <td>
        <p>レコードを取得する最新の日付を入力します。 </p>
        <p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 検索]

この検索モジュールは、指定した条件に基づいてアクティビティ、オファーまたはオーディエンスを検索します。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>[!DNL Adobe Target] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >[!DNL Adobe Target]</a> への接続を作成を参照してください。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Record type]</td>
    <td>更新するレコードのタイプを選択します。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Sort by]</td>
    <td>並べ替えるフィールドごとに、「<b>[!UICONTROL Add item]</b>」をクリックして、フィールドを選択し、返される結果を昇順または降順のどちらにするかを選択します。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Search criteria]</td>
    <td>設定するルールごとに、フィールド、演算子および値を選択します。「<b>[!UICONTROL Add AND rule]</b>」をクリックして、追加のルールを作成します。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Offset]</td>
    <td>
      <p>モジュールが返す最初の応答の数を入力します。最初に返された応答のオフセットは <code>0</code> です。このフィールドを [!UICONTROL Maximum number of returned results] フィールドと組み合わせて使用し、応答をページ番号付けします。</p>
      <p>例えば、応答の 3 ページ目を表示する際、各ページに 10 件の応答がある場合、[!UICONTROL Offset] を 20 に、[!UICONTROL Maximum number of returned] の結果を 10 に設定します。</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Limit]</td>
    <td>
      <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。このフィールドを [!UICONTROL Offset] フィールドと組み合わせて使用し、応答をページ番号付けします。</p>
      <p>例えば、応答の 3 ページ目を表示する際、各ページに 10 件の応答がある場合、[!UICONTROL Offset] を 20 に、[!UICONTROL Maximum number of returned] の結果を 10 に設定します。</p>
    </td>
  </tr>
</tbody>
</table>
