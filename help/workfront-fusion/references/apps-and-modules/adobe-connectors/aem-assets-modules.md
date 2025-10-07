---
title: Adobe Experience Manager Assets モジュール
description: Adobe Workfront Fusion のAdobe Experience Manager Assets コネクタを使用すると、アセットの作成、アップロード、更新、フォルダーやアセットのコピーや移動を行うことができます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: 190c35629f1fc1e07eef4110f3f4f771af1065fb
workflow-type: tm+mt
source-wordcount: '3727'
ht-degree: 22%

---

# Adobe Experience Manager Assets モジュール

Adobe Workfront Fusion のAdobe Experience Manager Assets コネクタを使用すると、アセットの作成、アップロード、更新、フォルダーやアセットのコピーや移動を行うことができます。

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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

* これらのモジュールを使用するには、Adobe Experience Manager Assets アカウントが必要です。
* Adobe Developer コンソールでサーバー間フローを設定する必要があります。

  Adobe Developer コンソールでサーバー間フローを設定する手順については、[ サーバーサイド API のアクセストークンの生成 ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow) を参照してください。
* Adobe Experience Manager テクニカルアカウントには、書き込み権限が必要です。

  Adobe Experience Manager テクニカルアカウントに書き込み権限を追加する手順については、Adobe Experience Manager ドキュメントの [ サービス資格情報 ](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) を参照してください。

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

## Adobe Experience Manager AssetsのWorkfront Fusion への接続 {#connect-adobe-experience-manager-assets-to-workfront-fusion}

Adobe Experience Manager Assets モジュールの接続を作成するには：

1. 「接続」ボックスの横にある「追加」をクリックします。

2. 作成する接続のタイプを選択します。

   * **AEM Assetsas a Cloud Service**

     この設定には、Adobe Admin Consoleからの情報が必要です。

   * **AEM Assets Basic （Adobe Managed Services）**

     この設定には、ユーザー名とパスワードが必要です。

3. 作成する接続のタイプのフィールドに入力します。

   AEM Assets as a Cloud Serviceについては、[AEM Assets as a Cloud Serviceの接続の設定 ](#configure-the-connection-for-aem-assets-as-a-cloud-service) を参照してください。

   AEM Assets Basic （Adobe Managed Services）については、[AEM Assets Basic の接続の設定 ](#configure-the-connection-for-aemassets-basic-adobe-managed-services) を参照してください。

4. 「**続行**」をクリックして接続を保存し、モジュールに戻ります。


### AEM Assets as a Cloud Serviceの接続の設定

>[!NOTE]
>
>* これらのフィールドの情報は、Adobe Developer Consoleでのサーバー間フローの設定の一環として生成されます。 これらの値は、設定の一環として生成されるサービス資格情報 JSON ファイルに含まれています。
>
>   Adobe Developer Consoleでサーバー間フローを設定する手順については、[ サーバーサイド API のアクセストークンの生成 ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow) を参照してください。
>
>* Adobe Experience Manager テクニカルアカウントには、書き込み権限が必要です。
>
>   Adobe Experience Manager テクニカルアカウントに書き込み権限を追加する手順については、Adobe Experience Manager ドキュメントの [ サービス資格情報 ](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) を参照してください。


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">接続名</td>
                  <td>
                      <p>この接続の名前を入力します。</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">末尾にスラッシュを付けないインスタンス URL</td>
                  <td>Adobe Experience Manager インスタンスの URL を入力します。 URL の末尾にスラッシュ <code>/</code> を含めないでください。</td>
              </tr>
              <tr>
                  <td role="rowheader">アカウントの詳細入力オプション</td>
                  <td>アカウントの詳細を説明する JSON を提供するか、詳細を手動で入力するかを選択します。</td>
              </tr>
              <tr>
                  <td role="rowheader">JSON 形式のテクニカルアカウント詳細</td>
                  <td>JSON を指定する場合は、アカウントの詳細を説明する JSON を入力または貼り付けます。</td>
              </tr>
              <tr>
                  <td role="rowheader">クライアント ID</td>
                  <td>詳細を手動で入力する場合は、サーバー間セットアップで生成されたクライアント ID を入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">クライアントシークレット</td>
                  <td>詳細を手動で入力する場合は、サーバー間セットアップで生成されたクライアント秘密鍵を入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">テクニカルアカウント ID</td>
                  <td>詳細を手動で入力する場合は、テクニカルアカウントの ID を入力します。 これは、クライアント資格情報 JSON ファイルの「id」フィールドです。</td>
              </tr>
              <tr>
                  <td role="rowheader">組織 ID</td>
                  <td class="">詳細を手動で入力する場合は、組織の ID を入力します。 これは、クライアント資格情報 JSON ファイルの「組織」フィールドです。</td>
              </tr>
              <tr>
                  <td role="rowheader">Meta範囲</td>
                  <td>サーバー間セットアップで生成されたMeta スコープを入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">秘密鍵</td>
                  <td>サーバー間セットアップで生成された秘密鍵を入力します。 秘密鍵を抽出するには、「抽出」をクリックしてから、抽出するファイルとファイルのパスワードを入力します。</td>
              </tr>
              <tr>
                  <td role="rowheader">認証 URL</td>
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
                <td role="rowheader">接続名</td>
                <td>
                    <p>この接続の名前を入力します。</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">末尾にスラッシュを付けないインスタンス URL</td>
                <td>Adobe Experience Manager インスタンスの URL を入力します。 URL の末尾にスラッシュ <code>/</code> を含めないでください。</td>
            </tr>
            <tr>
                <td role="rowheader">ユーザー名</td>
                <td>この接続で使用するAEM Assets アカウントのユーザー名を入力します。</td>
            </tr>
            <tr>
                <td role="rowheader">パスワード</td>
                <td>この接続で使用するAEM Assets アカウントのパスワードを入力します。</td>
            </tr>
        </tbody>
    </table>


## Adobe Experience Manager Assets モジュールとそのフィールド

Workfront Fusion でAdobe Experience Manager Assets モジュールを設定する場合、以下に示すフィールドが表示されます。 これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加のAdobe Experience Manager Assets フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ファイル操作](#files-operations)
* [その他](#other)
* [Assets（オーサー API）](#assets-author-api)
* [イベント （Author API）](#events-author-api)
* [メタデータ （Author API）](#metadata-author-api)
* [インポート （Author API）](#import-author-api)
* [関係（Author API）](#relations-author-api)
* [フォルダー（Folders API）](#folders-folders-api)

### ファイル操作

* [アップロードの完了](#complete-upload)
* [事前署名済みストレージの取得](#get-presigned-storage)
* [アップロードの開始](#initiate-upload)
* [アセットのアップロード](#upload-an-asset)

#### アップロードの完了

このアクションモジュールは、ファイルのすべての部分がアップロードされた後に、開始されたアップロードを完了します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ファイル名</td> 
   <td> <p>アップロードしたファイルの名前を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アップロードトークン</td> 
   <td>開始で指定されたとおりに、バイナリのアップロードトークンを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">MIME タイプ</td> 
   <td>完成したファイルの MIME タイプを入力またはマップします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">完全な URI</td> 
   <td>ファイルの完全な URI を入力またはマップします。</td> 
  </tr> 
 </tbody> 
</table>


#### 事前署名済みストレージの取得

このアクションモジュールは、直接の資格情報を必要とせずに、AEMからファイルを安全にアップロードまたはダウンロードするための一時的な事前署名済み URL を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">参照タイプ</td> 
   <td> <p>アセットをパスで検索するか、ID で検索するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット</td> 
   <td>アセットへのパスを選択します。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UDID</td> 
   <td>アセットの UDID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### アップロードの開始

このアクションモジュールはアップロードを開始します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">宛先</td> 
   <td> <p>ファイルをアップロードするフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ファイル名</td> 
   <td> <p>アップロードしたファイルの名前を入力またはマッピング</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">最大ファイル サイズ</td> 
   <td>アップロードしたファイルのサイズをバイト単位で入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>


#### アセットのアップロード

このアクションモジュールは、Adobe Experience Manager Assets アカウントにアセットをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">宛先</td> 
   <td> <p>アセットをアップロードするフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Source ファイル</td> 
   <td>ソースファイルの名前とデータを入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

### その他


* [フォルダーまたはアセットのコピー](#copy-a-folder-or-asset)
* [レコードを作成](#create-a-record)
* [フォルダー、アセットまたはレンディションの削除](#delete-a-folder-asset-or-rendition)
* [フォルダーリストの取得](#get-a-folder-listing)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [フォルダーまたはアセットの移動](#move-a-folder-or-asset)
* [レコードの更新](#update-a-record)



#### フォルダーまたはアセットのコピー

このアクションモジュールは、フォルダーまたはアセットをAdobe Experience Manager Assets アカウントの別の場所にコピーします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>フォルダーとアセットのどちらをコピーするかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フォルダー/アセット</td> 
   <td>コピーするフォルダーまたはアセットを選択するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">宛先のパス</td> 
   <td>新しいフォルダーまたはアセットの場所へのパスを選択するか、マッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">コピーしたフォルダー/アセットの名前</td> 
   <td>新しいフォルダーまたはアセットの名前を入力します。Adobe Experience Manager Assetsに表示されるフォルダー名は、元の名前と同じです。 ここで入力した名前は、新しいフォルダーまたはアセットの URL に表示されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">子をコピー</td> 
   <td>フォルダーをコピーする場合、フォルダー内のサブフォルダーまたはアセットをコピーするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>コピー先のフォルダーまたはアセットと同じ名前を持つ出力先のフォルダーまたはアセットを上書きするには、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>



#### レコードを作成

このアクションモジュールでは、フォルダーまたはアセットのコメントを作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">オブジェクトタイプ</td> 
   <td> <p>アセットに対してフォルダーとコメントのどちらを作成するかを選択します。</p> 
    <ul> 
     <li> <p>フォルダー</p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p>名前</p> <p>フォルダーの名前を入力します。この名前はファイルパスに含まれるので、スペースや他の文字を含めることはできません。 </p> </li> 
       <li> <p>タイトル</p> <p>名前の代わりに表示できるフォルダーのタイトルを入力します。</p> </li> 
      </ul> </li> 
     <li> <p>アセットコメント</p> <p>次のフィールドに入力します。</p> 
      <ul> 
       <li> <p>アセットの選択</p> <p>コメントを追加するアセットの ID を選択またはマッピングします。</p> </li> 
       <li> <p>コメント</p> <p>コメントのテキストを入力します。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### フォルダー、アセットまたはレンディションの削除

このアクションモジュールは、フォルダー、アセットまたはレンディションを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>フォルダー、アセット、レンディションのどれを削除するかを選択します。</p> 
    <ul> 
     <li> <p>フォルダー</p> <p>パス内のフォルダーを選択して、削除するフォルダーを選択します。</p> </li> 
     <li> <p>アセット</p> <p>パス内のフォルダーを選択してアセットを選択した後、削除するアセットを選択します。</p> </li> 
     <li> <p>レンディション</p> <p>パス内のフォルダーを選択して、レンディションを選択します。</p> <p>レンディションの名前を入力またはマッピングします。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### フォルダーリストの取得

このアクションモジュールは、既存のフォルダーとその子エンティティ（フォルダーまたはアセット）の表現を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フォルダー</td> 
   <td>取得するフォルダーを選択またはマッピングします。サブフォルダーをパスに追加するには、プラスアイコンをクリックし、サブフォルダーを選択します。</td> 
  </tr> 
 </tbody> 
</table>

#### カスタム API 呼び出しの実行

このアクションモジュールは、Adobe Experience Manager Assets API に対してカスタム API 呼び出しを行います。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>URL</p> </td> 
   <td> <p>Adobe Experience Managerのベース URL を基準とした相対パスを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>メソッド</p> </td> 
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP リクエストメソッド </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ヘッダー</td> 
   <td> <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p> <p>例： <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion は、認証ヘッダーを自動的に追加します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">クエリ文字列</td> 
   <td> <p>リクエストクエリ文字列を入力します。各キーと値のペアについて、「<b> 項目を追加 </b>」をクリックし、キーと値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">本文</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### フォルダーまたはアセットの移動

このアクションモジュールは、指定されたパスのアセットまたはフォルダーを新しい場所に移動します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>フォルダーを移動するかアセットを移動するかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フォルダー/アセット</td> 
   <td>移動するフォルダーまたはアセットを選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">宛先のパス</td> 
   <td>フォルダーまたはアセットの移動先を選択またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">移動したフォルダー/アセットの名前</td> 
   <td>移動後のフォルダーまたはアセットの新しい名前を入力します。Adobe Experience Manager Assetsに表示されるフォルダー名は、元の名前と同じです。 ここで入力した名前は、移動後のフォルダーまたはアセットの URL に表示されます。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">上書き</td> 
   <td>宛先の場所にある、移動するフォルダーまたはアセットと同じ名前のフォルダーまたはアセットを上書きする場合は、このオプションを有効にします。</td> 
  </tr> 
 </tbody> 
</table>

#### レコードの更新

このアクションモジュールは、既存のレコードを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td> <p>アセットのメタデータとアセットのレンディションのどちらを削除するかを選択します。</p> 
    <ul> 
     <li> <p>アセットメタデータ</p> 
      <ul> 
       <li> <p>メタデータを更新するアセットを選択します。</p> </li> 
       <li> <p>アセットの新しいタイトルを入力します。</p> </li> 
      </ul> </li> 
     <li> <p>アセットレンディション</p> 
      <ul> 
       <li> <p>レンディションを更新するアセットを選択します。</p> </li> 
       <li> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Assets（オーサー API）

* [アセットを削除](#delete-asset)
* [ジョブステータスの取得](#get-job-status)

#### アセットを削除

このアクションモジュールは、ID によって 1 つのアセットを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>削除するアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">力</td> 
   <td>このオプションを有効にすると、アセットが参照されている場合でも、アセットが強制的に削除されます。</td> 
  </tr> 
 </tbody> 
</table>

#### ジョブステータスの取得

このアクションモジュールは、非同期ジョブの現在のステータスを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ジョブ ID</td> 
   <td> <p>ステータスを取得するジョブの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### イベント （Author API）

#### イベントを監視する

このトリガーモジュールは、AEM Assetsでイベントが発生するとシナリオを開始します。

モジュールには、Webhook という 1 つのフィールドが含まれています。 これらのイベントに使用する既存の Webhook を選択するか、新しく作成します。

新しい Webhook を作成するには：

1. Webhook フィールドの横にある「**追加**」をクリックします。
1. 次のフィールドに入力します。

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">Webhook 名</td>
        <td>この Webhook の名前を入力します。</td>
       </tr>
       <tr>
         <td role="rowheader">接続</td>
        <td>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</td>
       </tr>
     </tbody>
   </table>

1. 「保存」をクリックして Webhook を保存し、モジュールに戻ります。


### メタデータ （Author API）

* [アセットメタデータの取得](#get-asset-metadata)
* [アセットメタデータの更新](#update-asset-metadata)

#### アセットメタデータの取得

このアクションモジュールは、指定されたアセットに関するメタデータを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>メタデータを取得するアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### アセットメタデータの更新

このアクションモジュールは、指定されたアセットのメタデータを更新します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>メタデータを更新するアセットの ID を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アップデート</td> 
   <td> <p>更新するメタデータ項目ごとに、「<b> 項目を追加 </b>」をクリックし、操作を選択します。 「項目を追加」ボックスのその他のフィールドは、選択した操作によって異なります。</p> </td> 
  </tr> 
 </tbody> 
</table>


### インポート （Author API）

* [インポートジョブの結果を取得](#get-import-job-results)
* [インポートジョブステータスの取得](#get-import-job-status)
* [URL からのアセットのアップロード](#upload-an-asset-from-a-url)

#### インポートジョブの結果を取得

このアクションモジュールは、指定されたインポートジョブの結果を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">インポートジョブ ID</td> 
   <td> <p>結果を取得するジョブの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### インポートジョブステータスの取得

このアクションモジュールは、指定されたインポートジョブのステータスを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">インポートジョブ ID</td> 
   <td> <p>ステータスを取得するジョブの ID を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### URL からのアセットのアップロード

このアクションモジュールは、指定された URL からファイルを読み込んで、新しいアセットをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">タイトル</td> 
   <td> <p>アセットのタイトルを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">説明</td> 
   <td> <p>アセットの説明を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">件名</td> 
   <td> <p>アセットの件名を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">作成者</td> 
   <td> <p>アセットの作成者を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">有効期限</td> 
   <td> <p>アセットの有効期限を入力またはマッピングします。</p><p>サポートされる日付と時刻の形式の一覧については、「<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref"> 型強制 </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">カスタムメタデータ</td> 
   <td> <p>アセットに追加するカスタムメタデータの項目ごとに、「<b> 項目を追加 </b>」をクリックし、メタデータの名前と値を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フォルダーパスまたは ID</td> 
   <td> <p>宛先フォルダーをパスと ID のどちらで指定するかを選択し、パスを選択するか、ID を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">インポートするファイル</td> 
   <td> <p>インポートするファイルごとに、[<b> アイテムの追加 &lt;/&gt;] をクリックし、ファイルの詳細を入力します。<code>Title</code> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"></td> 
   <td> <p></p> </td> 
  </tr> 
 </tbody> 
</table>

### 関係（Author API）

* [アセット関係の作成](#create-asset-relations)
* [アセット関係を削除](#create-asset-relations)
* [アセット関係タイプの取得](#get-asset-relation-types)
* [アセット関係の取得](#get-asset-relations)

#### アセット関係の作成

このアクションモジュールは、選択したアセットの新しいアセット関係を作成します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>他のアセットを関連付ける ID アセットを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">関連アセット</td> 
   <td> <p>選択したアセットに関連付けるアセットごとに、「<b> 項目を追加 </b> をクリックして、アセットの ID と関係タイプを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### アセット関係を削除

このアクションモジュールは、アセットのアセット関係を削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>関係を削除する ID アセットを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">関連アセット</td> 
   <td> <p>削除するリレーションのタイプを入力またはマップします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">削除する関連アセットの特定の ID を指定</td> 
   <td> <p>1 つの特定の関係を削除する場合は、このチェックボックスをオンにします。 このボックスがチェックされていない場合、選択したタイプのすべてのリレーションが削除されます。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">関連アセット ID</td> 
   <td> <p>特定のリレーションを削除する場合は、削除するリレーションの ID を入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### アセット関係タイプの取得

このモジュールは、指定されたアセットに存在するアセット関係タイプのリストを表示します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>関係タイプをリストする ID アセットを入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### アセット関係の取得

このモジュールは、指定されたアセットのアセット関係をリストします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">アセット ID</td> 
   <td> <p>関係をリストする ID アセットを入力またはマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">関係タイプ</td> 
   <td> <p>リレーションをリストするリレーションの種類をカンマで区切ったリストを入力またはマップします。</p> </td> 
  </tr> 
 </tbody> 
</table>



### フォルダー（Folders API）

* [フォルダーの作成](#create-folders)
* [ID によるフォルダーの削除](#delete-a-folder-by-id)
* [パスによるフォルダーの削除](#delete-folders-by-path)
* [フォルダーのジョブ結果の取得](#get-folders-job-results)
* [フォルダーのジョブステータスの取得](#get-folders-job-status)
* [フォルダーのリスト](#list-folders)

#### フォルダーの作成

Adobe Experience Manager Assetsに新しいフォルダーを作成します。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">作成するフォルダー</td> 
   <td> <p>作成するフォルダーごとに、「<b> 項目を追加 </b>」をクリックし、次の情報を入力します。</p>
   <ul>
   <li><b>新しいフォルダーの場所</b><p>新しいフォルダーを作成する場所のパスを選択します。</p></li>
       <li> <b>名前</b> <p>フォルダーの名前を入力します。この名前はファイルパスに含まれるので、スペースや他の文字を含めることはできません。 </p> </li> 
       <li> <b>タイトル</b> <p>名前の代わりに表示できるフォルダーのタイトルを入力します。</p> </li> 
   </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### ID によるフォルダーの削除

指定された ID を持つAdobe Experience Manager Assets フォルダーが削除されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フォルダー ID</td> 
   <td> 削除するフォルダーの ID を入力またはマッピングします。</td>
  </tr> 
 <tr> 
   <td role="rowheader">サブフォルダーの削除</td> 
   <td> フォルダーとそのすべてのサブフォルダーを削除するには、このオプションを有効にします。</td>
  </tr> 
 <tr> 
   <td role="rowheader">力</td> 
   <td> このオプションを有効にすると、フォルダーが参照されている場合でも、フォルダーが強制的に削除されます。</td>
  </tr> 
 </tbody> 
</table>

#### パスによるフォルダーの削除

指定されたパスにあるAdobe Experience Manager Assets フォルダーを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">フォルダーパス</td> 
   <td>削除するフォルダーごとに「<b> 項目を追加 </b>」をクリックし、フォルダーのパスを選択します。</td>
  </tr> 
 <tr> 
   <td role="rowheader">サブフォルダーの削除</td> 
   <td> フォルダーとそのすべてのサブフォルダーを削除するには、このオプションを有効にします。</td>
  </tr> 
 <tr> 
   <td role="rowheader">力</td> 
   <td> このオプションを有効にすると、アセットが参照されている場合でも、アセットが強制的に削除されます。</td>
  </tr> 
 </tbody> 
</table>

#### フォルダーのジョブ結果の取得

このモジュールは、Adobe Experience Manager Assets folder API によって作成された非同期ジョブの結果を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ジョブ ID</td> 
   <td> 結果を取得するジョブの ID を入力またはマッピングします。</td>
  </tr> 
 </tbody> 
</table>

#### フォルダーのジョブステータスの取得

このモジュールは、Adobe Experience Manager Assets folder API によって作成された非同期ジョブのステータスを取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ジョブ ID</td> 
   <td> ステータスを取得するジョブの ID を入力またはマッピングします。</td>
  </tr> 
 </tbody> 
</table>


#### フォルダーのリスト

このモジュールは、指定したフォルダーのサブフォルダーを一覧表示します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>Adobe Experience Manager Assets アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager AssetsをWorkfront Fusion に接続 </a> を参照してください。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">フォルダーパスまたは ID</td> 
   <td> <p>宛先フォルダーをパスと ID のどちらで指定するかを選択し、パスを選択するか、ID を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
i! I added a lot of modules to the AEM Assets connector and we need new documentation for them. The connector is available in the QA environment. Heres the added modules and a brief description of them, more info about them can be found in the Assets Author Api docs and the Folders Api docs. Im not fully confident that i kept all the best practices for naming things :sweat_smile:, i hope you can take a look at that as well. Let me know if theres anything i can tell about the modules and thanks again in advance!
Author API
Assets
Delete Asset
Deletes an asset when provided an Asset ID, There is a force parameter that when toggled will delete the folder regardless if it's referenced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get assets job status
Given an assets job ID will return the state that the job is currently in (PROCESSING, COMPLETED, etc.)
Events
AEM Assets events
The costumer can create a web hook in this module and register it in the Adobe admin console
Metadata
Get asset metadata
Given asset ID returns assets metadata.
Update asset metadata
Given asset ID, there are 6 patch operations that can be done with the metadata. The operations are visible in the module as well as the documentation.
Import
Get import job results
Given Job ID returns it's result.
Get import job status
Given Job ID returns its status.
Upload an asset from url
Takes global metadata which applies to all the assets and local ones which apply individually.In both it is also possible to specify custom metadata.
Also takes the folder path or folder ID to place the assets there and url-s of the assets.
Relations
Create asset relation
Given asset ID and a list of related asset ID as well as the relation types creates those relationships.
Delete asset relations
Given asset ID and relation type deletes all relations of that type. Can also specify a related asset to target only that.
 there is a checkbox that is checked by default and when unchecked reveals a field where the user can specify the related user ID.
Get asset relation types
Given asset ID returns all the relation types that the asset has.
Get asset relations
Given asset ID returns all relations. Can also specify a specific type of relation.
Folders API
Create folders
Given a list of folders with their path, name, title, creates them.
Delete a folder by ID
Given Folder ID deletes the folder. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Delete folders by path
Given a list of paths, deletes everything in them. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get folders job results
Given job ID returns its result.
Get folders job status
Given job ID returns its status.
List Folders
List folders under the given folder. In the module you can choose the root folder either by ID or by Path.
-->

