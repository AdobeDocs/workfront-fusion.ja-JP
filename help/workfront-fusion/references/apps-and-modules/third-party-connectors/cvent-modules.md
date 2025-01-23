---
title: Cvent モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Cvent を使用するワークフローを自動化したり、複数のサードパーティアプリケーションおよびサービスに接続したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: b7e16180-1db8-4aff-bb7b-69ca98194b00
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 84%

---

# [!DNL Cvent] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Cvent] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

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
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## 前提条件

[!DNL Cvent] モジュールを使用するには、[!DNL Cvent] アカウントが必要です。

## Cvent API 情報

Cvent コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> V200611.ASMX </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.7.14</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Cvent] を [!DNL Adobe Workfront Fusion] に接続 {#connect-cvent-to-adobe-workfront-fusion}

>[!NOTE]
>
>[!DNL Cvent] モジュールは、[!UICONTROL SOAP] API を介して動作します。 [!DNL Cvent] への接続を作成するには、次の点を確認する必要があります。
>
>* [!DNL Cvent] API[!UICONTROL SOAP] アクセスできます。
>* [!DNL Workfront Fusion] IP アドレスが組織の許可リストに追加されている。
>
>  許可リストに加える [!DNL Workfront Fusion] の IP アドレスのリストについては、組織の [Fusion の IP アドレスの設定」を参照してください ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)


[!DNL Cvent] アカウントへの接続を、[!DNL Cvent] モジュール内から直接作成できます。

1. 任意の [!DNL Cvent] モジュールで、[!UICONTROL Connection] フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 接続する地域を選択します。

   * [!UICONTROL North America]
   * [!UICONTROL Europe]
   * [!UICONTROL Sandbox]

1. 「**[!UICONTROL Continue]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL Cvent] モジュールとそのフィールド

[!DNL Cvent] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Cvent] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [アクション](#actions)
* [検索](#searches)

### アクション

* [[!UICONTROL Custom API Call]](#create-meeting-request)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Register Invitee]](#register-invitee)
* [[!UICONTROL Add Invitee]](#add-invitee)
* [[!UICONTROL Delete Contact]](#delete-contact)
* [[!UICONTROL Update Contact]](#update-contact)
* [[!UICONTROL Create meeting request]](#create-meeting-request)

#### [!UICONTROL Custom API Call]

このアクションモジュールでは、[!DNL Cvent] API への認証済みのカスタム呼び出しを実行できます。これにより、他の [!DNL Cvent] モジュールでは不可能なデータフロー自動処理を作成できます。

このモジュールを設定する際には、次のフィールドが表示されます。

このモジュールは、ステータスコードと共に API 呼び出しのヘッダーと本文を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] への [!DNL Adobe Workfront Fusion]</a> の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">操作</td> 
   td&gt; <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">本文（XML）</td> 
   <td> <p>API 呼び出しの本文を入力またはマッピングします。XML のみを含める必要があります。モジュールには、認証ヘッダーが自動的に含まれます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

このアクションモジュールは、特定のレコードに関する情報を読み取ります。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td>読み取るレコードの項目タイプを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact] / [!UICONTROL Event] / [!UICONTROL Invitee ID]</td> 
   <td> <p>読み取る項目の ID を入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>モジュールの出力に含めるフィールドを選択します。フィールドは、選択した項目タイプに基づいて使用できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Register Invitee]

このアクションモジュールでは、イベントの招待者を登録できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Adobe Workfront Fusion]</a> への [!DNL Cvent] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>招待者 ID</p> </td> 
   <td> <p>イベントに登録する招待者の ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">イベント ID</td> 
   <td> <p>招待者を登録するイベントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Invitee]

このアクションモジュールでは、連絡先をイベントに招待できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>イベントに追加する連絡先の ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>連絡先を追加するイベントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Contact]

このアクションモジュールでは、Cvent 内の 1 つの連絡先を削除できます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact ID]</td> 
   <td> <p>削除する連絡先の ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update Contact]

このアクションモジュールは、ID を使用して既存の連絡先を更新します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>更新する連絡先の ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>情報を入力するフィールドを選択し、それらのフィールドに必要な値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> <p>情報を入力するフィールドを選択し、それらのフィールドに必要な値を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create meeting request]

このアクションモジュールは、お客様のアカウントに会議出席リクエストを追加します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Form ID]</p> </td> 
   <td> <p>新しい会議出席リクエストの作成に使用するフォームの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Meeting Request Fields]</td> 
   <td> <p>情報を入力する会議出席リクエストフィールドを選択し、それらのフィールドに必要な値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Request Fields]</td> 
   <td> <p>情報を入力するイベントリクエストフィールドを選択し、それらのフィールドに必要な値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL RFP Request Fields]</td> 
   <td> <p>情報を入力する提案フィールドのリクエストを選択し、それらのフィールドに必要な値を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 検索

#### [!UICONTROL List records]

この検索モジュールは、特定のタイプのすべてのレコードに関する情報を取得します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>[!DNL Cvent] アカウントを [!DNL Workfront Fusion] に接続する方法については、この記事の<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">[!DNL Cvent] を [!DNL Adobe Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td> <p>リストに表示するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p>[!DNL Cvent] アカウントからのすべてのイベント</p> </li> 
     <li> <p>イベントのすべてのセッション</p> </li> 
     <li> <p>イベントのすべての招待者</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>招待者またはセッションをリストする場合は、招待者またはセッションが関連付けられているイベントの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
