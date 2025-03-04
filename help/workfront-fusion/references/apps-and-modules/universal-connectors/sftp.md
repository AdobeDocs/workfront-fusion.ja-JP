---
title: SFTP モジュール
description: ' [!DNL Adobe Workfront Fusion SFTP]  モジュールを使用すると、選択したフォルダーやサブフォルダー内のファイルの変更を監視したり、新しいファイルを目的のフォルダーにアップロードしたり、フォルダー内の既存のファイルを変更または削除したり、ファイルの権限を変更したりすることができます。'
author: Becky
feature: Workfront Fusion
exl-id: bde3cbda-8a19-4d9f-b970-f56d73a1f8dd
source-git-commit: 4f97980dce7c8df47ab73d51537d4700ac34dedf
workflow-type: tm+mt
source-wordcount: '2077'
ht-degree: 82%

---

# SFTP モジュール

[!DNL Adobe Workfront Fusion] SFTP モジュールを使用すると、モジュールを使用すると、選択したフォルダーやサブフォルダー内のファイルの変更を監視したり、新しいファイルを目的のフォルダーにアップロードしたり、フォルダー内の既存のファイルを変更または削除したり、ファイルの権限を変更したりすることができます。

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

[!DNL Workfront Fusion] で SFTP を使用するには、SFTP アカウント（[!DNL GoDaddy] web ホスティングなど）が必要です。

## SFTP を [!DNL Workfront Fusion] に接続 {#connect-sftp-to-workfront-fusion}

SFTP アカウントを [!DNL Workfront Fusion] に接続するには、ターゲットホストと SFTP 資格情報（ユーザー名とパスワード、ユーザー名とキー）を指定する接続を作成する必要があります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection name]</td> 
   <td> <p> SFTP 接続の名前を入力します。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Environment]</td>
    <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Type]</td>
    <td>サービスアカウントに接続するか、個人アカウントに接続するかを選択します。</td>
  </tr>
  <tr>
   <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
   <td> <p>接続する SFTP サーバーのホスト名を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Port] </td> 
   <td> <p>SFTP サーバーポートを入力します。例：22。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Auth type]</p> </td> 
   <td> <p>SFTP サーバーへの接続に使用する認証メソッドを選択します。</p> 
    <ul> 
     <li><strong>[!UICONTROL User name and password]</strong>：資格情報を入力します。</li> 
     <li> <p><strong>[!UICONTROL User name and key]</strong>：ユーザー名と秘密鍵／証明書を入力します。</p> <p>秘密鍵をアップロードしてクライアント側の認証を使用するか、自己署名証明書を使用して TLS を使用する場合には、自分の証明書（P12 または PFX ファイル）をアップロードします。クライアント側の証明書認証を使用している場合は、ここに CA 証明書を入力できます。</p> <p>[!DNL Workfront Fusion] ここで指定したデータ（ファイル、パスワード）を保持または保存しません。ファイルとパスワードは、秘密鍵や証明書を抽出する場合にのみ使用します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL キー交換アルゴリズム ] </td> 
   <td> <p>キー交換用の一連のアルゴリズムを入力できます。 モジュールは、追加された順序に基づいてアルゴリズムの優先順位を設定します。 追加するアルゴリズムごとに「<b> 項目を追加 </b>」をクリックし、アルゴリズムを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 暗号 ] </td> 
   <td> <p>キー交換用の暗号のセットを入力できます。 モジュールは、追加された順序に基づいて暗号の優先順位を設定します。 追加する暗号ごとに [<b> 項目の追加 </b>] をクリックし、暗号を選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

接続情報を入力したら、「**[!UICONTROL 続行]**」をクリックして接続を確立します。

## [!UICONTROL SFTP] モジュールとそのフィールド

[!UICONTROL SFTP] モジュールを設定すると、[!DNL Workfront Fusion] には以下のフィールドが表示されます。これらと共に、アプリやサービスのアクセスレベルなどの要因に応じて、追加の [!UICONTROL SFTP] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### トリガー

* [フォルダー内のファイルの監視](#watch-files-in-a-folder)
* [フォルダー内のサブフォルダーの監視](#watch-subfolders-in-a-folder)

#### [!UICONTROL フォルダー内のファイルを監視]

特定のフォルダー内でファイルが作成または変更された場合に、詳細を含むファイルを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事にある <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>監視するフォルダーを入力します。 <code>/home/user/</code> などの絶対パスを指定するか、ログインしたユーザーの特定のフォルダーを指す相対パス（など）を指定できます <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>バッファサイズ [B]</td> 
   <td> <p> バッファサイズをバイト単位で入力します。この値は、サーバーから転送されるチャンクのサイズを定義します。値が高すぎると、サーバーで問題が発生したり、ファイルが破損したりする場合があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> 各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダ内のサブフォルダーの監視]

特定のフォルダー内でフォルダーが作成または変更された場合に、詳細を含むフォルダーを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事にある <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>監視するフォルダーを入力またはマッピングします。ここでは、<code>/home/user/</code> などの絶対パスを指定できます。また、次のように、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [フォルダーを作成](#create-a-folderr)
* [ファイルの削除](#delete-a-file)
* [フォルダーの削除](#delete-a-folder)
* [ファイルの取得](#get-a-file)
* [ファイルを取得](#get-files)
* [フォルダーのコンテンツのリスト化](#list-a-folders-content)
* [ファイルの移動](#move-a-file)
* [ファイル名の変更](#rename-a-file)
* [ファイル権限の更新](#update-file-permissions)
* [ファイルのアップロード](#upload-a-file)

#### [!UICONTROL フォルダーを作成]

指定された場所に新しいフォルダーを作成します。

>[!NOTE]
>
>フォルダーが既に存在する場合はエラーが返されます。フローを中断せずに続行するには、エラーハンドラールートをモジュールに接続してエラーを検出し、[!UICONTROL 再開]ディレクティブを適用します。エラーハンドラールートのアタッチについて詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) でのエラー処理を参照してください。エラーハンドラールートについて詳しくは、[ [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md) でのエラー処理用のディレクティブを参照してください。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事にある <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>新しいフォルダーの保存場所として既存のフォルダーを指定します。ここでは、<code>/home/user/file.txt</code> などの絶対パスを指定できます。または、<code>./</code> など、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name]</td> 
   <td> <p> フォルダー名を入力します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>必要なフォルダー権限を設定します。chmod パラメーターを使用します。例えば、<code>777</code> や <code>-rwxrwxrwx</code> です。</p> <p>これらの権限は、パターンに一致する必要があります <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>chmod について詳しくは、<a href="https://ss64.com/bash/chmod.html?lang=ja">chmod のドキュメント </a> を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを削除]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 削除するファイルのパスを入力します。ここでは、<code>/home/user/file.txt</code> などの絶対パスを指定できます。または、<code>./file.txt</code> など、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーを削除]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントの [!DNL Workfront Fusion] への接続について詳しくは、この記事内の <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">SFTP の [!DNL Workfront Fusion]</a> への接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Folder Path]</td> 
   <td> <p> 削除するフォルダーへのパスを指定します。例えば、<code>/home/user/</code> のように、絶対パスを指定できます。また、次のように、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。 <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを取得]

このモジュールでは、ファイルのデータなど、ファイルの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントの [!DNL Workfront Fusion] への接続手順については、この記事の<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> バッファサイズをバイト単位で入力します。この値は、サーバーから転送されるチャンクのサイズを定義します。値が高すぎると、サーバーで問題が発生したり、ファイルが破損したりする場合があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path] </td> 
   <td> <p>ファイルにパスを入力します。ここでは、<code>/home/user/file.txt</code> などの絶対パスを指定できます。または、<code>./file.txt</code> など、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL  ファイルを取得 ]

このモジュールは、指定されたフォルダーからファイルを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントの [!DNL Workfront Fusion] への接続手順については、この記事の<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> バッファサイズをバイト単位で入力します。この値は、サーバーから転送されるチャンクのサイズを定義します。値が高すぎると、サーバーで問題が発生したり、ファイルが破損したりする場合があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>リストするファイルまたはフォルダーを含むフォルダーを入力またはマッピングします。ここでは、<code>/home/user/</code> などの絶対パスを指定できます。また、次のように、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>検索語を入力またはマッピングします。例えば、ファイル拡張子が .txt のファイルを検索する場合は、「<code>.txt</code>」と入力します。検索するファイルの名前を入力またはマッピングすることもできます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> ファイル名、サイズ、最終アクセス日、最終変更日のどれで結果を並べ替えるかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order]</td> 
   <td> <p> 昇順と降順のどちらで結果を返すかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>結果が返されない場合にこのモジュールがシナリオを停止しないようにするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL フォルダーのコンテンツのリスト]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事にある <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>ファイル、フォルダ、またはその両方を取得するかどうかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>リストするファイルまたはフォルダーを含むフォルダーを入力またはマッピングします。ここでは、<code>/home/user/</code> などの絶対パスを指定できます。また、次のように、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>検索語を入力またはマッピングします。例えば、ファイル拡張子が .txt のファイルを検索する場合は、「<code>.txt</code>」と入力します。検索するファイルの名前を入力またはマッピングすることもできます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> ファイル名、サイズ、最終アクセス日、最終変更日のどれで結果を並べ替えるかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order] </td> 
   <td> <p>昇順と降順のどちらで結果を返すかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>結果が返されない場合にこのモジュールがシナリオを停止しないようにするには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルの移動]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 移動するファイルのパスを入力します。ここでは、<code>/home/user/file.txt</code> などの絶対パスを指定できます。また、<code>./file.txt</code> など、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New Folder]</td> 
   <td> <p> ファイルの新しい場所へのパスを入力します。ここでは、<code>/home/user/</code> などの絶対パスを指定できます。また、次のように、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。 <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイル名の変更]

ファイル名を変更します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 名前を変更するファイルのパスを入力します。ここでは、<code>/home/user/file.txt</code> などの絶対パスを指定できます。または、<code>./file.txt</code> など、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New file name]</td> 
   <td> <p> ファイル拡張子を含む、ファイルの新しい名前を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイル権限の更新]

ファイルの権限は変更することができます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 移動するファイルのパスを入力します。ここでは、<code>/home/user/file.txt</code> などの絶対パスを指定できます。または、<code>./file.txt</code> など、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>必要なファイル権限を設定します。chmod パラメーターを使用します。例えば、<code>777</code> や <code>-rwxrwxrwx</code> です。</p> <p>これらの権限は、パターンに一致する必要があります <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>chmod について詳しくは、<a href="https://ss64.com/bash/chmod.html?lang=ja">chmod のドキュメント </a> を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルのアップロード]

このモジュールでは、SFTP サーバーにファイルをアップロードできます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>SFTP アカウントを [!DNL Workfront Fusion] に接続する手順については、この記事にある <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">[!DNL Workfront Fusion]</a> への SFTP の接続を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>ファイルの保存場所として、既存のフォルダーを指定します。ここでは、<code>/home/user/</code> などの絶対パスを指定できます。また、次のように、ログインしたユーザーの特定のフォルダーを指す相対パスを指定できます。 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source File]</td> 
   <td> <p> 以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>ファイルまたはフォルダーに必要な権限を設定します。chmod パラメーターを使用します。例えば、<code>777</code> や <code>-rwxrwxrwx</code> です。</p> <p>これらの権限は、パターンに一致する必要があります <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>chmod について詳しくは、<a href="https://ss64.com/bash/chmod.html?lang=ja">chmod のドキュメント </a> を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>
