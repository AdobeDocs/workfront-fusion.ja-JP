---
title: FTP モジュール
description: FTP モジュールを使用すると、選択したフォルダー内のファイルの変更を監視したり、新しいファイルを目的のフォルダーにアップロードしたり、フォルダー内に既に存在するファイルを変更または削除したりできます。
author: Becky
feature: Workfront Fusion
exl-id: 1e14f778-ab8c-421f-a4b4-c57be66c7cad
source-git-commit: c5e9c643c828e5556e386a5f46e1d17680b7d4e9
workflow-type: tm+mt
source-wordcount: '1328'
ht-degree: 93%

---

# FTP モジュール

FTP モジュールを使用すると、選択したフォルダー内のファイルの変更を監視したり、新しいファイルを目的のフォルダーにアップロードしたり、フォルダー内に既に存在するファイルを変更または削除したりできます。

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
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
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

FTP モジュールを使用するには、FTP アカウントが必要です。

## FTP モジュールでの接続の作成 {#create-a-connection}

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection name]</td> 
   <td> <p> FTP 接続の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Host] </td> 
   <td> <p>FTP サーバーのホスト名を入力します。例： <code>myftp123.server.com</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Port] </td> 
   <td> <p>FTP サーバーのポート番号を入力します。例： <code>21</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL User name] </td> 
   <td> <p>FTP アカウントのユーザー名を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Password] </td> 
   <td> <p>FTP アカウントのパスワードを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>セキュア接続 (TLS) を使用</p> </td> 
   <td> <p>セキュア接続を使用するかどうかを選択します。</p> <p style="font-weight: bold;">[!UICONTROL No]</p> <p>接続は保護されていません。</p> <p style="font-weight: bold;">[!UICONTROL Explicit encryption or Implicit encryption]</p> <p>接続は SSL を使用して保護されています。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Reject unauthorized certificates]</p> </td> 
   <td> <p>FTP サーバー証明書を検証するには、このオプションを有効にします。検証に失敗した場合、接続は作成されません。検証に合格するには、証明書が次のいずれかの条件を満たしている必要があります。</p> 
    <ul> 
     <li>ルート<a href="https://en.wikipedia.org/wiki/Certificate_authority">認証局</a>で署名されていること</li> 
     <li>中間認証局で署名されていること（詳しくは、<a href="https://knowledge.digicert.com/solution/SO16297.html">How Certificate Chains Work</a> などを参照してください）。この場合は、すべての中間証明書を FTP サーバーにインストールする必要があります。</li> 
     <li>「[!UICONTROL Self-signed certificate]」フィールドで指定されている自己署名証明書であること（下記を参照）</li> </ul>

このオプションが無効になっている場合、FTP サーバー証明書は検証されません。このオプションを無効にすると接続が安全でなくなり、重大なセキュリティリスクが生じるので、このオプションを無効にしないことを強くお勧めします。</td>
</tr> 
  <tr> 
   <td> <p>[!UICONTROL Self-signed certificate]</p> </td> 
   <td> <p>「<b>[!UICONTROL Extract]</b>」ボタンをクリックして、アップロードダイアログを開きます。</p> <p>自己署名証明書で TLS を使用するには、証明書をアップロードします。[!DNL Workfront Fusion] では、ファイルやパスワードなど、ユーザーが提供したデータを保持または保存することはありません。ファイルとパスワードは、証明書を抽出するためにのみ使用されます。</p> </td> 
  </tr> 
 </tbody> 
</table>

## FTP モジュールとそのフィールド

* [トリガー](#triggers)
* [アクション](#actions)

### トリガー

#### [!UICONTROL ファイルの監視]

[!UICONTROL ファイルの監視]は、FTP の唯一のトリガーモジュールです。選択されたフォルダーのファイルコンテンツを監視します。指定したフォルダーに新しいファイルが挿入されると、トリガーが実行されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>FTP アカウントへの接続を確立する手順については、この記事の <a href="#create-a-connection" class="MCXref xref">FTP モジュールでの[!UICONTROL Create a connection]</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>監視するフォルダーを選択します。</p> <p><b>メモ：</b>許可されるフォルダはシナリオごとに 1 つだけです。サブフォルダーは無視されます。</p> <p><b>ヒント：</b> 複数のフォルダーを把握しておくには、フォルダーごとに独立したシナリオを作成します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files] </td> 
   <td> <p>1 回のサイクル中に [!DNL Workfront Fusion] が処理する結果の最大数を設定します。値が大きすぎると、指定されたサードパーティサービス側で接続が中断される可能性があります（タイムアウト）。[!DNL Workfront Fusion] はこれに影響しません。より小さい値を設定し、最大サイクル数としてより大きい値を定義するか、シナリオをより頻繁に実行することをお勧めします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL 権限の変更]](#change-permissions)
* [[!UICONTROL フォルダーの作成]](#create-a-folder)
* [[!UICONTROL ファイルの削除]](#delete-a-file)
* [[!UICONTROL フォルダーの削除]](#delete-a-folder)
* [[!UICONTROL ファイルの取得]](#get-a-file)
* [[!UICONTROL フォルダー内のファイルのリスト]](#list-of-files-in-a-folder)
* [[!UICONTROL ファイルまたはフォルダーの移動]](#move-a-file-or-folder)
* [ファイルの[!UICONTROL アップロード]](#upload-a-file)

#### [!UICONTROL 権限の変更]

このアクションモジュールは、ファイルまたはフォルダーの権限設定を変更します。

<table style="width: 100%;" class="TableStyle-TableStyle-List-options-in-steps" cellspacing="0">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1" />
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2" />
   <tbody>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">FTP アカウントへの接続を確立する手順については、この記事の <a href="#Create" class="MCXref xref" >FTP モジュールでの[!UICONTROL Create a connection]</a>を参照してください。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-MediumGray" role="rowheader">[!UICONTROL Change permission settings of]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-MediumGray">
               <p>ファイルまたはフォルダーの設定を変更するかどうかを選択します。</p>
            </td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL File path]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">フォルダーまたはファイルのファイルパスを入力するかマッピングします。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-MediumGray" role="rowheader">[!UICONTROL Permissions]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-MediumGray">
               <p>必要なファイルまたはフォルダー権限を設定します。chmod パラメーターを使用します。例：<code>777 </code>または <code>-rwxrwxrwx</code>。</p>
               <p>権限は、<code> /(.?([r-][w-][x-]){3})|[0-7]{3,4}/</code> というパターンと一致する必要があります。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL フォルダーの作成]

このアクションモジュールは、新規フォルダーを作成します。

<table style="width: 100%;" class="TableStyle-TableStyle-List-options-in-steps" cellspacing="0">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1" />
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2" />
   <tbody>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">FTP アカウントへの接続を確立する手順については、この記事の <a href="#Create" class="MCXref xref" >FTP モジュールでの[!UICONTROL Create a connection]</a>を参照してください。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-MediumGray" role="rowheader">[!UICONTROL Folder path]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-MediumGray">新しいフォルダーのファイルパスを入力するかマッピングします。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-LightGray" role="rowheader">[!UICONTROL New folder name]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-LightGray">
               <p>新しいフォルダーの名前を入力またはマッピングします。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL ファイルの削除]

指定されたフォルダーからファイルを削除します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">FTP アカウントへの接続を確立する手順については、この記事の <a href="#Create" class="MCXref xref" >FTP モジュールでの[!UICONTROL Create a connection]</a>を参照してください。</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>ファイルを削除する FTP フォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td> <p> ファイル名拡張子を含むファイル名を入力します。例： <code>[!DNL image].png</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーの削除]

このアクションモジュールは、指定されたフォルダーを完全に削除します。

<table style="width: 100%;" class="TableStyle-TableStyle-HeaderRow" cellspacing="15">
   <col style="width: 301px;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <col style="width: 50%;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <tbody>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-LightGray" style="font-weight: bold;">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-LightGray">FTP アカウントへの接続を確立する手順については、この記事の <a href="#Create" class="MCXref xref" >FTP モジュールでの[!UICONTROL Create a connection]</a>を参照してください。</td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-MediumGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyB-Column1-MediumGray" style="font-weight: bold;">[!UICONTROL Folder]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyA-Column1-MediumGray">
               <p>ファイルを削除する FTP フォルダーを選択します。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL ファイルの取得]

さらに処理できるファイル（例：[!DNL Dropbox] にアップロードできるファイル）を FTP サーバーから取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>FTP アカウントへの接続を確立する手順については、この記事の <a href="#creating-the-ftp-connection" class="MCXref xref">FTP 接続の作成</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File path]</td> 
   <td> <p> 取得するファイルのパスを入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダー内のファイルのリスト]

ファイルやフォルダーの情報を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>FTP アカウントへの接続を確立する手順については、この記事の <a href="#creating-the-ftp-connection" class="MCXref xref">FTP 接続の作成</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>検索場所となる FTPフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>ファイルまたはフォルダーあるいはその両方に関する情報を取得するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>検索語句を入力します。検索語句が入力されていない場合は、指定したフォルダーからすべてのファイルとフォルダーが取得されます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> このモジュールで取得されるファイルの最大数を設定します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルまたはフォルダーの移動]

このアクションモジュールは、ファイルまたはフォルダーを別の場所に移動します。

<table style="width: 100%;" class="TableStyle-TableStyle-HeaderRow" cellspacing="15">
   <col style="width: 301px;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <col style="width: 50%;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <tbody>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-LightGray" style="font-weight: bold;">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-LightGray">FTP アカウントへの接続を確立する手順については、この記事の <a href="#Create" class="MCXref xref" >FTP モジュールでの[!UICONTROL Create a connection]</a>を参照してください。</td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-MediumGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-MediumGray" style="font-weight: bold;">[!UICONTROL Old file path]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-MediumGray">
               <p>ファイルの移動元のパスを入力します。例：<code>/folder1/document.txt</code></p>
            </td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyB-Column1-LightGray" style="font-weight: bold;">[!UICONTROL New file path]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyA-Column1-LightGray">
               <p>ファイルの移動先のパスを入力します。例：<code>/folder2/document.txt</code></p>
            </td>
         </tr>
   </tbody>
</table>


#### [!UICONTROL ファイルのアップロード]

FTP サーバーにファイルをアップロードします。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>FTP アカウントへの接続を確立する手順については、この記事の <a href="#creating-the-ftp-connection" class="MCXref xref">FTP 接続の作成</a>を参照してください。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>ファイルのアップロード先となる FTP フォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file] </td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Append to an already existing file]</td> 
   <td> <p>このオプションが有効で、ファイルが FTP サーバー上に既に存在する場合は、ファイルの内容が既存のファイルに追加されます。このオプションが有効になっていない場合は、ファイルの内容が上書きされます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create folders if don't exist] </td> 
   <td> <p>このオプションが有効で、「フォルダー」フィールドに入力したフォルダーが FTP サーバー上に存在しない場合は、モジュールがフォルダーを作成します。</p> </td> 
  </tr> 
 </tbody> 
</table>

## トラブルシューティング {#troubleshooting}

接続の作成中またはモジュールの操作中に FTP アプリで問題が発生した場合は、一般的な FTP クライアントのいずれかを使用して、同じ操作（接続の作成やフォルダー内のファイルの一覧表示など）を実行してみてください。。その FTP クライアントでも同じ問題が発生する場合は、FTP サーバーの設定ミスが原因である可能性があります。
