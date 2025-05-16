---
title: Adobe Experience Manager Assets モジュール
description: ' [!DNL Adobe Workfront Fusion] 用の  [!DNL Adobe Experience Manager Assets] connector を使用すると、アセットの作成、アップロード、更新、フォルダーやアセットのコピーや移動を行うことができます。'
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: 40470e5d2183f690ad65f5e1170f78c37dee8603
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 75%

---

# [!DNL Adobe Experience Manager Assets] モジュール

[!DNL Adobe Workfront Fusion] 用の [!DNL Adobe Experience Manager Assets] コネクタを使用すると、アセットの作成、アップロード、更新、フォルダーやアセットのコピーや移動を行うことができます。

Adobe Experience Manager Assets コネクタの概要ビデオについては、以下を参照してください。

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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
   <p>従来のバージョン：自動化と統合のためのWorkfront Fusion </p>
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

## 前提条件

* これらのモジュールを使用するには、[!DNL Adobe Experience Manager Assets] アカウントが必要です。
* [!UICONTROL サーバー間]のフローを [!DNL Adobe Developer console] に設定する必要があります。

  [!UICONTROL サーバー間]のフローを [!DNL Adobe Developer console] で設定する手順については、[サーバー側 API のアクセストークンの生成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=ja#the-server-to-server-flow)を参照してください。
* Adobe Experience Manager テクニカルアカウントには、書き込み権限が必要です。

  Adobe Experience Manager テクニカルアカウントに書き込み権限を追加する手順については、Adobe Experience Manager ドキュメントの [ サービス資格情報 ](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) を参照してください。

## Adobe Experience Manager Assets API の情報

Adobe Experience Manager Assets コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.8.61</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Adobe Experience Manager Assets] を [!DNL Workfront Fusion] に接続 {#connect-adobe-experience-manager-assets-to-workfront-fusion}

[!DNL Adobe Experience Manager Assets] モジュールへの接続を作成するには、以下を実行します。

1. [!UICONTROL 接続]ボックスの横にある「[!UICONTROL 追加]」をクリックします。

2. 作成する接続のタイプを選択します。

   * **[!DNL AEM Assets as a Cloud Service]**

     この設定には、[!DNL Adobe Admin Console] からの情報が必要です。

   * **[!DNL AEM Assets Basic] ([!DNL Adobe Managed Services])**

     この設定には、ユーザー名とパスワードが必要です。

3. 作成する接続のタイプのフィールドに入力します。

   [!DNL AEM Assets as a Cloud Service] の場合、[接続の設定対象 [!DNL AEM Assets as a Cloud Service]](#configure-the-connection-for-aem-assets-as-a-cloud-service)を参照してください。

   [!UICONTROL AEM Assets Basic]（[!DNL Adobe Managed Services]）の場合は、[[!UICONTROL AEM Assets Basic 用の接続の設定対象]](#configure-the-connection-for-aemassets-basic-adobe-managed-services)を参照してください。

4. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。


### [!DNL AEM Assets as a Cloud Service] 用の接続の設定対象

>[!NOTE]
>
>* これらのフィールドの情報は、[!DNL Adobe Developer Console] で[!UICONTROL サーバー間]のフローを設定の一環として生成されます。これらの値は、設定の一環として生成されるサービス資格情報 JSON ファイルに含まれています。
>
>   [!UICONTROL サーバー間]のフローを [!UICONTROL Adobe Developer Console] で設定する手順については、[サーバー側 API のアクセストークンの生成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=ja#the-server-to-server-flow)参照してください。
>
>* Adobe Experience Manager テクニカルアカウントには、書き込み権限が必要です。
>
>   Adobe Experience Manager テクニカルアカウントに書き込み権限を追加する手順については、Adobe Experience Manager ドキュメントの [ サービス資格情報 ](https://experienceleague.adobe.com/ja/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) を参照してください。


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">[!UICONTROL Connection name]</td>
                  <td>
                      <p>この接続の名前を入力します。</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
                  <td>[!DNL Adobe Experience Manager] インスタンスの URL を入力します。URL の末尾にスラッシュ <code>/</code> を含めないでください。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL アカウントの詳細入力オプション &#x200B;]</td>
                  <td>アカウントの詳細を説明する JSON を提供するか、詳細を手動で入力するかを選択します。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL テクニカルアカウントの詳細（JSON 形式） &#x200B;]</td>
                  <td>JSON を指定する場合は、アカウントの詳細を説明する JSON を入力または貼り付けます。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Client ID]</td>
                  <td>詳細を手動で入力する場合は、[!UICONTROL サーバー間 &#x200B;] 設定で生成されたクライアント ID を入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Client Secret]</td>
                  <td>詳細を手動で入力する場合は、[!UICONTROL サーバー間 &#x200B;] 設定で生成されたクライアントの秘密鍵を入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Technical account ID]</td>
                  <td>詳細を手動で入力する場合は、テクニカルアカウントの ID を入力します。 これは、クライアント資格情報 JSON ファイルの「[!UICONTROL id]」フィールドです。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Org ID]</td>
                  <td class="">詳細を手動で入力する場合は、組織の ID を入力します。 これは、クライアント資格情報 JSON ファイルの「[!UICONTROL org]」フィールドです。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Meta Scopes]</td>
                  <td>[!UICONTROL Server-to-server] 設定で生成したメタスコープを入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Private key]</td>
                  <td>[!UICONTROL Server-to-server] 設定で生成された秘密鍵を入力します。秘密鍵を抽出するには、「[!UICONTROL Extract]」をクリックし、抽出するファイルとファイルのパスワードを入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Authentication URL]</td>
                  <td>このアカウントの認証 URL を入力してください。</td>
              </tr>
          </tbody>
      </table>


### AEM Assets Basic （Adobe Managed Services）の接続の設定

<table style="table-layout:auto"> 
        <col/>
        <col />
        <tbody>
            <tr>
                <td role="rowheader">[!UICONTROL Connection name]</td>
                <td>
                    <p>この接続の名前を入力します。</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
                <td>[!DNL Adobe Experience Manager] インスタンスの URL を入力します。URL の末尾にスラッシュ <code>/</code> を含めないでください。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Username]</td>
                <td>この接続で使用する [!DNL AEM Assets] アカウントのゆーざー名を入力します。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Password]</td>
                <td>この接続で使用する [!DNL AEM Assets] アカウントのパスワードを入力します。</td>
            </tr>
        </tbody>
    </table>


## [!DNL Adobe Experience Manager Assets] モジュールとそのフィールド

[!DNL Adobe Experience Manager Essentials] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Experience Manager Essentials] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [フォルダーまたはアセットのコピー](#copy-a-folder-or-asset)
* [レコードを作成](#create-a-record)
* [フォルダー、アセットまたはレンディションの削除](#delete-a-folder-asset-or-rendition)
* [フォルダーリストの取得](#get-a-folder-listing)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [フォルダーまたはアセットの移動](#move-a-folder-or-asset)
* [レコードの更新](#update-a-record)
* [アセットのアップロード](#upload-an-asset)

### [!UICONTROL フォルダーまたはアセットのコピー]

このアクションモジュールは、フォルダーまたはアセットをAdobe Experience Manager Assets アカウントの別の場所にコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Adobe Experience Manager Assets] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>フォルダーとアセットのどちらをコピーするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]／[!UICONTROL Asset]</td> 
   <td>コピーするフォルダーまたはアセットを選択するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination path]</td> 
   <td>新しいフォルダーまたはアセットの場所へのパスを選択するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of copied folder] / [!UICONTROL asset]</td> 
   <td>新しいフォルダーまたはアセットの名前を入力します。[!DNL Adobe Experience Manager Assets] に表示されるフォルダー名は元の名前と同じです。ここで入力した名前は、新しいフォルダーまたはアセットの URL に表示されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy children]</td> 
   <td>フォルダーをコピーする場合、フォルダー内のサブフォルダーまたはアセットをコピーするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>コピー先のフォルダーまたはアセットと同じ名前を持つ出力先のフォルダーまたはアセットを上書きするには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL レコードを作成]

このアクションモジュールでは、フォルダーまたはアセットのコメントを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Adobe Experience Manager Assets] への [!DNL Workfront Fusion]</a> の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object type]</td> 
   <td> <p>アセットに対してフォルダーとコメントのどちらを作成するかを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Folder]</p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p>[!UICONTROL Name]</p> <p>フォルダーの名前を入力します。この名前はファイルパスに含まれるので、スペースや他の文字を含めることはできません。 </p> </li> 
       <li> <p>[!UICONTROL Title]</p> <p>名前の代わりに表示できるフォルダーのタイトルを入力します。</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL Asset comment]</p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p>[!UICONTROL Asset selection]</p> <p>コメントを追加するアセットの ID を選択またはマッピングします。</p> </li> 
       <li> <p>[!UICONTROL Comment]</p> <p>コメントのテキストを入力します。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL &#x200B; フォルダー、アセットまたはレンディションの削除 &#x200B;]

このアクションモジュールは、フォルダー、アセットまたはレンディションを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Adobe Experience Manager Assets] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>フォルダー、アセット、レンディションのどれを削除するかを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Folder]</p> <p>パス内のフォルダーを選択して、削除するフォルダーを選択します。</p> </li> 
     <li> <p>[!UICONTROL Asset] </p> <p>パス内のフォルダーを選択してアセットを選択した後、削除するアセットを選択します。</p> </li> 
     <li> <p>[!UICONTROL Rendition]</p> <p>パス内のフォルダーを選択して、レンディションを選択します。</p> <p>レンディションの名前を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL フォルダーの一覧を取得]

このアクションモジュールは、既存のフォルダーとその子エンティティ（フォルダーまたはアセット）の表現を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Adobe Experience Manager Assets] を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>取得するフォルダーを選択またはマッピングします。サブフォルダーをパスに追加するには、プラスアイコンをクリックし、サブフォルダーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL カスタム API 呼び出しの実行]

このモジュールは、[!DNL Adobe Experience Manager Assets] API に対してカスタム API 呼び出しを実行します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事内の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Adobe Experience Manager Assets]を [!DNL Workfront Fusion]</a> に接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>[!DNL Adobe Experience Manager] ベース URL に対する相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>リクエストクエリ文字列を入力します。キーと値のペアごとに、「<b>[!UICONTROL Add item]</b>」をクリックし、[!UICONTROL Key]と[!UICONTROL Value]を入力します。</p> </td> 
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

### [!UICONTROL フォルダーまたはアセットの移動]

このアクションモジュールは、指定されたパスのアセットまたはフォルダーを新しい場所に移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Adobe Experience Manager Assets] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>フォルダーを移動するかアセットを移動するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]／[!UICONTROL Asset]</td> 
   <td>移動するフォルダーまたはアセットを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination path]</td> 
   <td>フォルダーまたはアセットの移動先を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of moved folder]／[!UICONTROL asset]</td> 
   <td>移動後のフォルダーまたはアセットの新しい名前を入力します。[!DNL Adobe Experience Manager Assets] に表示されるフォルダー名は元の名前と同じです。ここで入力した名前は、移動後のフォルダーまたはアセットの URL に表示されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>宛先の場所にある、移動するフォルダーまたはアセットと同じ名前のフォルダーまたはアセットを上書きする場合は、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL レコードを更新]

このアクションモジュールは、既存のレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Adobe Experience Manager Assets] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>アセットのメタデータとアセットのレンディションのどちらを削除するかを選択します。</p> 
    <ul> 
     <li> <p>[!UICONTROL Asset metadata]</p> 
      <ul> 
       <li> <p>メタデータを更新するアセットを選択します。</p> </li> 
       <li> <p>アセットの新しいタイトルを入力します。</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL Asset rendition]</p> 
      <ul> 
       <li> <p>レンディションを更新するアセットを選択します。</p> </li> 
       <li> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL アセットのアップロード]

このアクションモジュールは、アセットを [!DNL Adobe Experience Manager Assets] アカウントにアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Adobe Experience Manager Assets] アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事で <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への [!DNL Adobe Experience Manager Assets] の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination]</td> 
   <td> <p>アセットをアップロードするフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>ソースファイルの名前とデータを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>
