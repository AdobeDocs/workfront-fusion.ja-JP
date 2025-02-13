---
title: Adobe I/Oイベントモジュール
description: Adobe I/Oイベントモジュールを使用すると、Adobeアプリケーションのイベントに基づいてAdobe Workfront Fusion シナリオを開始できます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: b2229f3e-a2a7-4b07-8ead-a37d193c2ec7
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 38%

---

# Adobe I/Oイベントモジュール

Adobe I/Oイベントモジュールを使用すると、専用のAdobe Workfront Fusion コネクタがないAdobeアカウントとサービスのイベントに基づいてWorkfront Fusion シナリオを開始できます。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront プラン*</td> 
   <td> <p>Pro 以上</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン*</td> 
   <td> <p>プラン、作業</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td> <p>Workfront Fusion for Work Automation and Integration </p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>この記事で説明する機能を使用するには、Adobe Workfront Fusion と Adobe Workfront を購入する必要があります。</td> 
  </tr> 
 </tbody> 
</table>

&#42;保有するプラン、ライセンスタイプ、アクセス権を確認するには、Workfront 管理者に問い合わせてください。

&#42;&#42;Adobe Workfront Fusion ライセンスについては、[Adobe Workfront Fusion ライセンスを参照してください ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)

## 前提条件

Adobe I/Oイベントコネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* 有効なAdobeアカウントが必要です。

## Adobe I/Oイベント API の情報

Adobe I/Oイベントコネクタは、次を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://api.adobe.io/events</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.6.7</td> 
  </tr>
 </tbody> 
 </table>

## Adobe I/Oイベントへの接続の作成

Adobe I/Oイベントモジュールの接続を作成するには：

1. 「接続」ボックスの横にある「追加」をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">接続名</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">タイプ</td>
        <td>
          <p>サービス アカウントに接続するか、個人アカウントに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">追加範囲</td>
        <td>追加の範囲を追加するには、「<b> 項目を追加 </b>」をクリックして範囲を入力します。</td>
      </tr>
      <tr>
        <td role="rowheader">クライアント ID</td>
        <td>Adobeクライアント ID を入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションにあります</td>
      </tr>
      <tr>
        <td role="rowheader">クライアントシークレット</td>
        <td>Adobeクライアントの秘密鍵を入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションにあります</td>
      </tr>
      </tr>
        <tr>
        <td role="rowheader">消費者組織 ID</td>
        <td>消費者組織 ID を入力します。 これは、プロジェクトの資格情報 URL で確認できます。 <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">資格情報 ID</td>
        <td>認証情報 ID を入力します。 これは、プロジェクトの資格情報 URL で確認できます。 <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">IMS 組織 ID</td>
        <td>Adobe組織 ID を入力します。 これは、Adobe Developer Consoleの「資格情報の詳細」セクションにあります</td>
      </tr>
        <tr>
        <td role="rowheader">プロジェクト ID</td>
        <td>プロジェクト ID を入力します。 これは、プロジェクトの資格情報 URL で確認できます。 <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">WORKSPACE ID</td>
        <td>プロジェクトのWorkspace ID を表示するには、Adobe Developer Consoleのプロジェクトの概要ページからプロジェクトの詳細をダウンロードします。 </td>
      </tr>
    </tbody>
    </table>

1. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。

## Adobe I/Oイベントモジュールとそのフィールド

[!DNL Adobe I/O Events] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe I/O Events] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

#### イベント登録の作成

このアクションモジュールは、Webhook を使用してイベントの説明を作成します。 ここで Webhook を設定できます。 既存の Webhook を使用している場合、このモジュールのフィールドは読み取り専用です。

Webhook を作成するには：

1. Webhook フィールドの横にある「**追加**」をクリックします。
1. 次のフィールドに入力します。

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[!UICONTROL Webhook name]</td>
        <td>この Webhook の名前を入力します。</td>
       </tr>
       <tr>
         <td role="rowheader">[!UICONTROL Connection]</td>
        <td>[!DNL Adobe I/O Events] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >[!DNL Adobe I/O Events]</a> への接続を作成を参照してください。</td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Webhook description]
         </td>
         <td>
           この Webhook の説明を入力します。
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Event provider]
         </td>
         <td>
           イベントを作成する製品またはアカウントを選択します。
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Event type]
         </td>
         <td>
           Webhook で監視するイベントを選択します。 これらのイベントが発生すると、シナリオはトリガーします。
         </td>
       </tr>
     </tbody>
   </table>

1. 「保存」をクリックして Webhook を保存し、モジュールに戻ります。

### アクション

#### ジャーナルからすべてのイベントを取得

この検索モジュールは、登録のすべてのイベントをジャーナルから取得します。

<table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[!UICONTROL Connection]</td>
        <td>[!DNL Adobe I/O Events] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >[!DNL Adobe I/O Events]</a> への接続を作成を参照してください。</td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Registration ID]
         </td>
         <td>
           イベントを取得する登録を選択します。
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Maximum number of returned records]
         </td>
         <td>
              各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。 
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Return events that occur after]
         </td>
         <td>
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Seek]
         </td>
         <td>
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Latest]
         </td>
         <td>
         最新のイベントを返すには、このオプションを有効にします。
         </td>
       </tr>
     </tbody>
   </table>

#### カスタム API 呼び出しの実行

このアクションモジュールは、[!DNL Adobe I/O Events] API に対してカスタム API 呼び出しを行います。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
        <td>[!DNL Adobe I/O Events] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >[!DNL Adobe I/O Events]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Path]</p>
      </td>
      <td>
        <p>相対パスを入力します <code>https://api.adobe.io/events</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
      <td>
  <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p>  
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は、認証ヘッダーと x-api-key ヘッダーを自動的に追加します。</p>
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

### 検索

#### プロバイダー ID とイベント ID の取得

この検索モジュールは、指定されたプロバイダーおよびイベントのAdobe I/Oイベント ID を取得します。

<table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[!UICONTROL Connection]</td>
        <td>[!DNL Adobe I/O Events] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >[!DNL Adobe I/O Events]</a> への接続を作成を参照してください。</td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Event provider]
         </td>
         <td>
           ID を取得するプロバイダーを選択します。
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [!UICONTROL Event type]
         </td>
         <td>
              ID を提供するイベントを選択します。 イベントは、イベントプロバイダーに基づいて使用できます。 
         </td>
       </tr>
     </tbody>
   </table>

<!--

Watch Events

This trigger module starts a scenario when an event occurs in the chosen Adobe product or service.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">Webhook</td> 
   <td><p>Select the webhook that you want to use for this trigger, or add a new webhook. </p><p>To add a new webhook, <ol><li>Click <b>Add</b> next to the webhook field.</li><li>Enter the following: <ul><li>A name for the webhook</li><li>The connection that you want to use for this webhook</li><li>The source of the events you want to watch</li></ul></li><li>Click <b>Save</b> to save the webhook and return to the module. </td> 
   </tr> 
   </tbody> 
</table>

-->
