---
title: Adobe Experience Manager Forms モジュール
description: Adobe Workfront Fusion 用の  [!DNL Adobe Experience Manager Forms] connector を使用すると、アカウント内のイベントに基づいたシナリオの開始、アセットの作成  [!DNL Adobe Experience Manager Forms]  アップロード、更新、フォルダーやアセットのコピーまたは移動をおこなうことができます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: e0d7a655-1353-4d24-83d4-7da73d859a63
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 68%

---

# [!DNL Adobe Experience Manager Forms] モジュール

Adobe Workfront Fusion の [!DNL Adobe Experience Manager Forms] コネクタを使用すると、Webhook を作成することで、[!DNL Adobe Experience Manager Forms] アカウントのイベントに基づいたシナリオを開始できます。

[!DNL Adobe Experience Manager Forms] 内でフォームを設定して、この web フックにフォームを送信できます。

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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

## 前提条件

* このモジュールを使用するには、[!DNL Adobe Experience Manager Forms] アカウントが必要です。

## Adobe Experience Manager Assets API の情報

Adobe Experience Manager Assets コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.2.27</td> 
  </tr>
 </tbody> 
 </table>

## Adobe Experience Manager Forms への接続の作成

[!DNL Adobe Experience Manager Forms] モジュールへの接続を作成するには、以下を実行します。

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
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>サービスアカウントか個人用アカウントかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
        <td>
          <p>アカウントへのアクセスに使用する URL を入力します（最後のスラッシュは除きます）。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL IMS endpoint]</td>
        <td>
          <p><code>https://ims-na1.adobelogin.com</code></p>
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
        <td role="rowheader">[!UICONTROL Org ID]</td>
        <td>[!DNL Adobe] 組織 ID を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>[!DNL Adobe] テクニカルアカウント ID を入力します。これは、[!DNL Adobe Developer Console] の [!UICONTROL Credentials details] セクションで確認できます。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>適切なメタスコープを入力します。       </td>
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

## Adobe Experience Manager Forms モジュールとそのフィールド

現在、Adobe Experience Manager Forms コネクタにあるモジュールは 1 つだけです。

### フォームイベントを監視

このインスタントトリガー（web フック）を使用すると、Adobe Experience Manager フォームで送信アクションが発生したときにシナリオを開始できます。

>[!IMPORTANT]
>
>このモジュールを使用するには、Adobe Experience Manager での設定も必要です。この web フックを設定したら、Adobe Experience Manager を開き、web フックに送信するようにフォームを設定する必要があります。
>
><!--For instructions on the required form configuration, see insert url here-->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p>Web フックの名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager] アカウントをWorkfront Fusion に接続する手順については、<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/aem-forms-modules.md#create-a-connection-to-adobe-experience-manager-forms" class="MCXref xref">[!DNL Adobe Experience Manager Forms]</a> への接続の作成」を参照してください</p> </td> 
  </tr>

このモジュールは web フックを作成し、[!DNL Adobe Experience Manager Forms] のフォーム送信ダイアログに入力できる web フックのアドレスを提供します。
