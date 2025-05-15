---
title: Adobe Photoshop モジュール
description: Adobe Photoshop モジュールを使用すると、Adobe Photoshop アカウント内のイベントに基づくAdobe Workfront Fusion シナリオの開始、契約書やその他のレコードの作成、読み取りまたは更新、設定した条件を使用したレコードの検索、ドキュメントのアップロードを行うことができます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0e41d1af-af69-4f9b-a5b3-479562254084
source-git-commit: 7f167af0ba1becb603dd8d9f3767101e157a7bdf
workflow-type: tm+mt
source-wordcount: '5379'
ht-degree: 12%

---

# [!DNL Adobe Photoshop] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Adobe Photoshop] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。


シナリオの作成手順については、[ シナリオを作成：記事インデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

[!DNL Adobe Photoshop] コネクタを使用する前に、次の前提条件が満たされていることを確認する必要があります。

* アクティブな [!DNL Adobe Photoshop] アカウントが必要です。
* Firefly Services ライセンスが必要です。
* クライアント ID とクライアント秘密鍵が必要です。 これらはAdobe Developer Consoleから入手できます。

## Adobe Photoshop API の情報

Adobe Photoshop コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://image.adobe.io/pie/psdService</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.12.31</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Adobe Photoshop] への接続の作成

[!DNL Adobe Photoshop] モジュールへの接続を作成するには、以下を実行します。

1. 任意のモジュールで、「接続」ボックスの横にある **[!UICONTROL 追加]** をクリックします。

1. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>JWT 接続を使用するか、サーバー間接続を使用するかを選択します。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>[!UICONTROL Adobe] [!UICONTROL クライアント ID] を入力します。 これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>JWT 接続を使用している場合は、[!DNL Adobe] [!UICONTROL テクニカルアカウント ID] を入力します。 これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>JWT 接続を使用している場合は、[!DNL Adobe] [!UICONTROL 組織 ID] を入力します。 これは、の [!UICONTROL 資格情報 ] の詳細セクションにあります [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>JWT 接続を使用している場合は、資格情報が [!DNL Adobe Developer Console] で作成されたときに生成された秘密鍵を入力します。 </p>
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
              <p>「<b> 保存 </b>」をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Photoshop] モジュールとそのフィールド

[!DNL Adobe Photoshop] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Adobe Photoshop] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [PSDの編集の適用](#apply-psd-edits)
* [画像の自動カラー補正](#auto-color-correct-an-image)
* [画像形式を変換](#convert-image-format)
* [マスクの作成](#create-a-mask)
* [新しいPSDの作成](#create-a-new-psd)
* [テキストレイヤーを編集](#edit-text-layers)
* [テキストレイヤーの編集（従来）](#edit-text-layers-legacy)
* [アクション JSON の実行](#execute-an-action-json)
* [深度ブラーを実行](#execute-depth-blur)
* [Photoshop アクションの実行](#execute-photoshop-actions)
* [製品の切り抜きを実行](#execute-product-crop)
* [レイヤー情報を取得](#get-layer-info)
* [カスタム API 呼び出しの実行](#make-a-custom-api-call)
* [背景を削除](#remove-background)
* [スマートオブジェクトの置換](#replace-a-smart-object)
* [スマートオブジェクトの置換（レガシー）](#replace-a-smart-object-legacy)
* [画像のサイズ変更](#resize-an-image)
* [画像に透かしを付ける](#watermark-an-image)

### PSDの編集の適用

このアクションモジュールは、様々なドキュメントレベルおよびレイヤーレベルの編集を適用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>編集するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> 編集するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）の高さ ]</p>
      </td>
      <td> 画像の高さをピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）の幅 ]</p>
      </td>
      <td> 画像の幅をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント &gt; キャンバス サイズ）上 ]</p>
      </td>
   <td> ドキュメントの左上隅の y 座標をピクセル単位で入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント &gt; キャンバス サイズ）下部 ]</p>
      </td>
   <td> ドキュメントの右下隅の y 座標をピクセル単位で入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント &gt; キャンバス サイズ）左 ]</p>
      </td>
   <td> ドキュメントの左上隅の x 座標をピクセル単位で入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント &gt; キャンバス サイズ）右 ]</p>
      </td>
   <td> ドキュメントの右下隅の x 座標をピクセル単位で入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント） トリミング ]</p>
      </td>
   <td> 「透明ピクセル」を選択すると、画像内の透明なピクセルに基づいてトリミングが行われます。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）既定のフォント ]</p>
      </td>
   <td> ドキュメントのグローバルデフォルトとして使用するフォントの完全な Postscript 名を入力します。 このフォントは、フォントが見つからないテキストレイヤーに使用され、そのレイヤーに特別に提供された他のフォントはありません。 このフォントが見つからない場合は、見つからないフォントの管理で指定したオプションが有効になります。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） フォント ]</p>
      </td>
   <td> ドキュメントに必要なフォントごとに、「項目を追加」をクリックし、フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）不足フォントを管理 ]</p>
      </td>
   <td> ドキュメントに 1 つ以上の不足しているフォントがある場合に実行するアクションを選択します。 <ul><li><code>fail</code>：ジョブは成功せず、ステータスは「失敗」に設定され、ステータスの詳細セクションにエラーの詳細が表示されます。</li><li><code>useDefault</code>：ジョブは成功し、見つからないフォントはすべて ArialMT に置き換えられます。</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）画層 ]</p>
      </td>
   <td> 追加するレイヤーごとに、「項目を追加」をクリックしてレイヤーの詳細を入力します。 <p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_applyPsdEdits/">PSDの編集内容の適用 </a> を参照してください。  </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する編集済みのファイルごとに、[ アイテムの追加 ] をクリックし、この表に示されているストレージ、場所、およびタイプを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。 これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td>ファイルの変換先となるファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） キャンバスにトリミング ]</p>
      </td>
   <td>レンディションをキャンバスサイズにする必要があるかどうかを選択します。 True の場合はレンディションがキャンバスサイズに合わせてトリミングされ、False の場合はレンディションレイヤーのサイズが調整されます</td> 
    </tr>
    </tbody>
</table>

### 画像の自動カラー補正

このアクションモジュールは、指定された画像を自動カラー補正します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>カラー補正するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> カラー補正するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。 これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td>ファイルの変換先となるファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    </tbody>
</table>

### 画像形式を変換

ファイルをJPEG、PNG、PSDまたはTIFFに変換します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>背景を削除するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> 背景を削除するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する変換後のファイルごとに、[ アイテムの追加 ] をクリックし、この表に示されているストレージ、場所、およびタイプを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。 これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td>ファイルの変換先となるファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    </tbody>
</table>

### マスクの作成

このアクションモジュールは、件名の周囲にマスクが適用された PNG ファイルを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>マスクの作成元となるファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> マスクを作成するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>マスクファイルを格納するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> マスク ファイルを格納する場所の URL またはパスを入力またはマップします。 これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL カラースペース ]</p>
      </td>
   <td>出力画像でRGBまたは RGBA カラーを使用するかどうかを選択します。 </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL マスク形式 ]</p>
      </td>
   <td>マスクをソフト（羽毛）にするか 2 進数にするかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 最適化 ]</p>
      </td>
   <td>速度を最適化するには「パフォーマンス」、待機時間を許可するには「バッチ」を選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 後処理 ]</p>
      </td>
   <td>後処理を有効にするかどうかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>デフォルトは 4.0 です</td> 
    </tr> 
    </tbody>
</table>

### 新しいPSDの作成

このアクションモジュールは、オプションのレイヤーを持つ新しいPSDを作成し、レンディションを生成したり、PSDとして保存したりします。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）の高さ ]</p>
      </td>
      <td> 画像の高さをピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）の幅 ]</p>
      </td>
      <td> 画像の幅をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント）解像度 ]</p>
      </td>
   <td> 画像の解像度を 1 インチあたりのピクセル数で入力またはマップします。 72 ～ 300 の間にする必要があります。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント） モード ]</p>
      </td>
   <td> 画像のモードを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント）塗りつぶし ]</p>
      </td>
   <td> 背景レイヤーの塗りつぶしを透明、白、画像の背景色のどれにするかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント）の深度 ]</p>
      </td>
   <td> 画像のビット深度を選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）画層 ]</p>
      </td>
   <td> 追加するレイヤーごとに、「項目を追加」をクリックしてレイヤーの詳細を入力します。 <p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_createPsd/">PSDの作成 </a> を参照してください。  </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） グローバル フォント ]</p>
      </td>
   <td> ドキュメントのグローバルデフォルトとして使用するフォントの完全な Postscript 名を入力します。 このフォントは、フォントが見つからないテキストレイヤーに使用され、そのレイヤーに特別に提供された他のフォントはありません。 このフォントが見つからない場合は、見つからないフォントの管理で指定したオプションが有効になります。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） フォント ]</p>
      </td>
   <td> ドキュメントに必要なフォントごとに、「項目を追加」をクリックし、フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）不足フォントを管理 ]</p>
      </td>
   <td> ドキュメントに 1 つ以上の不足しているフォントがある場合に実行するアクションを選択します。 <ul><li><code>fail</code>：ジョブは成功せず、ステータスは「失敗」に設定され、ステータスの詳細セクションにエラーの詳細が表示されます。</li><li><code>useDefault</code>：ジョブは成功し、見つからないフォントはすべて ArialMT に置き換えられます。</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成するファイルごとに [ アイテムの追加 ] をクリックし、この表に示されているストレージ、場所、およびタイプを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。 これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td>ファイルの変換先となるファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）その他のフィールド ]</td>
      <td>
        <p><p>出力オプションについて詳しくは、Adobe Photoshop ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_createPsd/">PSDの作成 </a> を参照してください。  </p>
      </td>
    </tr>
    </tbody>
</table>

### テキストレイヤーを編集

Photoshop ファイルのテキストレイヤーを編集します。 同じファイル内の複数のレイヤーに対して、個別の編集詳細を入力できます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイルの保存場所 ]</td>
      <td>
        <p>編集するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 不足フォントの管理 ]</td>
      <td>
        <p>ドキュメントに 1 つ以上の不足しているフォントがある場合に実行するアクションを選択します。 フォントが指定されていない場合、モジュールはデフォルトのフォントを使用します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 既定のフォント ]  </td>
      <td>
        <p>ドキュメントのグローバルデフォルトとして使用するフォントの完全な Postscript 名を入力します。 このフォントは、フォントが見つからないテキストレイヤーに使用され、そのレイヤーに特別に提供された他のフォントはありません。 このフォントが見つからない場合は、見つからないフォントの管理で指定したオプションが有効になります。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） フォント ]</p>
      </td>
   <td> フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL レイヤー ]</td>
   <td> <p>編集するテキストレイヤーごとに、「<b> 項目を追加 </b> をクリックして、レイヤーオプションを入力します。<p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_editText/"> テキストの編集 </a> を参照してください。</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 編集したファイルを保存する場所の URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

### テキストレイヤーの編集（従来）

Photoshop ファイルのテキストレイヤーを編集します。

複数のレイヤーを編集するには、「[ テキストレイヤーを編集 ](#edit-text-layers) モジュールを使用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイルの保存場所 ]</td>
      <td>
        <p>編集するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 不足フォントの管理 ]</td>
      <td>
        <p>ドキュメントに 1 つ以上の不足しているフォントがある場合に実行するアクションを選択します。 フォントが指定されていない場合、モジュールはデフォルトのフォントを使用します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 既定のフォント ]  </td>
      <td>
        <p>ドキュメントのグローバルデフォルトとして使用するフォントの完全な Postscript 名を入力します。 このフォントは、フォントが見つからないテキストレイヤーに使用され、そのレイヤーに特別に提供された他のフォントはありません。 このフォントが見つからない場合は、見つからないフォントの管理で指定したオプションが有効になります。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） フォント ]</p>
      </td>
   <td> フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL レイヤー ]</td>
   <td> <p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_editText/"> テキストレイヤーの編集 </a> を参照してください。</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 出力ファイルの保存場所 ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 編集したファイルを保存する場所の URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>


### アクション JSON の実行

このアクションモジュールは、JSON コマンドを使用してPhotoshopのアクションを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>編集するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> 編集するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL アクション JSON]</td>
      <td>
        <p>実行するアクションの JSON コマンドを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL フォント / パターン / ブラシ /追加の画像 ]</td>
      <td>
        <p>このアクションで使用するフォント、パターン、ブラシ、または追加の画像ごとに、[ アイテムの追加 ] をクリックし、アイテムの保存場所とファイルの場所を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL フォント / パターン / ブラシ ファイルの URL]</p>
      </td>
   <td> 使用するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成するファイルごとに、[ アイテムの追加 ] をクリックし、この表に示されているストレージ、場所、タイプ、上書きオプションを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの URL]</p>
      </td>
   <td> 編集したファイルを保存する場所の URL またはパスを入力またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。</p>
      </td>
    </tr>
      </tbody>
</table>

### 深度ブラーを実行

このアクション モジュールは、選択したファイルに対して深度ブラーを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイルの保存場所 ]</td>
      <td>
        <p>編集するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの URL]</p>
      </td>
   <td> 編集したファイルを保存する場所の URL またはパスを入力またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>その他の深度ブラーオプションについて詳しくは、Adobe Photoshop API ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_depthBlur/"> 深度ブラーの実行 </a> を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

### Photoshop アクションの実行

このアクションモジュールは、選択された画像に対してPhotoshopアクションを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイルの保存場所 ]</td>
      <td>
        <p>編集するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL アクション ファイルの保存場所 ]</td>
      <td>
        <p>アクションファイルが格納されるファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL アクション ファイルの URL]</p>
      </td>
   <td> アクションファイルの URL またはパスを入力またはマッピングします。 </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL アクション名 ]</p>
      </td>
   <td> 特定のアクションのみを実行する場合は、ActionSet から再生するアクションを指定できます。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL フォント/パターン/ブラシストレージ ]</td>
      <td>
        <p>使用するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL フォント / パターン / ブラシ ファイルの URL]</p>
      </td>
   <td> 使用するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの URL]</p>
      </td>
   <td> 編集したファイルを保存する場所の URL またはパスを入力またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>その他の深度ブラーオプションについて詳しくは、Adobe Photoshop API ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_depthBlur/"> 深度ブラーの実行 </a> を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

### 製品の切り抜きを実行

このアクションモジュールは、選択した画像に対して製品の切り抜きを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイルの保存場所 ]</td>
      <td>
        <p>切り抜くファイルを格納するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 切り抜くファイルの URL またはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ユニット ]</p>
      </td>
   <td> 高さと幅の調整をピクセル単位またはパーセント単位のどちらで記述するかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> 追加する幅のパディングの量を入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Height]</p>
      </td>
   <td> 追加する高さのパディングの量を入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの URL]</p>
      </td>
   <td> 編集したファイルを保存する場所の URL またはパスを入力またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>その他の深度ブラーオプションについて詳しくは、Adobe Photoshop API ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_depthBlur/"> 深度ブラーの実行 </a> を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

### レイヤー情報を取得

指定したPSD ファイルからレイヤー情報を取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイルの保存場所 ]</td>
      <td>
        <p>画層情報を取得するファイルが格納されているファイル サービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 画層情報を取得するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL サムネール ]</p>
      </td>
   <td> サムネールを表示するファイルのタイプを選択します。 サムネールは、レンダリング可能なレイヤーの小さなプレビューです。</td> 
    </tr>
  </tbody>
</table>

### カスタム API 呼び出しの実行

このアクションモジュールは、Photoshop API へのカスタム呼び出しを行います。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p><code>https://image.adobe.io/pie/psdService</code> からの相対パスを入力します。例： <code>/photoshopActions</code></p>
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
        <p>[!DNL Workfront Fusion] 認証ヘッダーを自動的に追加します。</p>
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
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件文を JSON で使用する場合は、条件文を引用符で囲みます。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

### 背景を削除

このアクションモジュールは、画像の主な被写体を識別し、背景を削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>背景を削除するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> 背景を削除するファイルの URL またはパスを入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL カラースペース ]</p>
      </td>
   <td>出力画像でRGBまたは RGBA カラーを使用するかどうかを選択します。 </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL マスク形式 ]</p>
      </td>
   <td>画像のエッジをソフト（ぼかし）にするか 2 進数にするかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 最適化 ]</p>
      </td>
   <td>速度を最適化するには「パフォーマンス」、待機時間を許可するには「バッチ」を選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 後処理 ]</p>
      </td>
   <td>後処理を有効にするかどうかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>デフォルトは 4.0 です</td> 
    </tr> 
    </tbody>
</table>

### スマートオブジェクトの置換

このアクションモジュールは、PSD レイヤー内のスマートオブジェクトを置き換え、新しいレンディションを生成します。

このモジュールでは、スマートオブジェクト API バージョン 2 を使用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>スマートオブジェクトが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> スマートオブジェクトの URL またはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL レイヤー ]</p>
      </td>
   <td>スマートオブジェクトに追加するレイヤーごとに、「項目を追加」をクリックし、オブジェクトの名前または ID、スマートオブジェクトが格納されているファイルサービス、レイヤーの URL またはパスを入力します。<p>この領域の詳細設定については、Photoshop API ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_replaceSmartObject/"> スマートオブジェクトの置換 </a> を参照してください </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL イメージのサイズ変更を指定 ]</p>
      </td>
   <td> 画像のサイズを変更するかどうかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>モジュールで生成する新規レンディションごとに、「項目を追加」をクリックし、次のフィールドに入力します。 最大 25 個の出力ファイルを持つことができます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td> 編集するファイルのファイル タイプを選択します。 </td> 
    </tr>
     </tbody>
</table>

### スマートオブジェクトの置換（レガシー）

このアクションモジュールは、PSD レイヤー内のスマートオブジェクトを置き換え、新しいレンディションを生成します。

このモジュールでは、従来のバージョンのスマートオブジェクトを使用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （入力） ストレージ ]</td>
      <td>
        <p>スマートオブジェクトが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （入力） ファイルの場所 ]</p>
      </td>
   <td> スマートオブジェクトの URL またはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL レイヤー ]</p>
      </td>
   <td>スマートオブジェクトに追加するレイヤーごとに、「項目を追加」をクリックし、オブジェクトの名前または ID、スマートオブジェクトが格納されているファイルサービス、レイヤーの URL またはパスを入力します。<p>この領域の詳細設定については、Photoshop API ドキュメントの <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop_replaceSmartObject/"> スマートオブジェクトの置換 </a> を参照してください </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>モジュールで生成する新規レンディションごとに、「項目を追加」をクリックし、次のフィールドに入力します。 最大 25 個の出力ファイルを持つことができます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力）の幅 ]</p>
      </td>
   <td> 出力ファイルの幅（ピクセル単位）。 モジュールは、元の縦横比を保持します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tbody>
</table>

### 画像のサイズ変更

同じ縦横比を使用して、画像のサイズを変更します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ストレージ ]</td>
      <td>
        <p>サイズを変更するファイルが格納されているファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ファイルの場所 ]</p>
      </td>
   <td> サイズを変更するファイルの URL またはパスを入力またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する変換後のファイルごとに、[ アイテムの追加 ] をクリックし、ストレージ、場所、およびこの表に示されているその他のオプションを入力します。</p>
      </td>
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL ストレージ ]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ファイルの場所 ]</p>
      </td>
   <td> 新しいファイルが格納される URL またはパスを入力するか、またはマップします。  これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> 出力ファイルの幅（ピクセル単位）。 モジュールは、元の縦横比を保持します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL の最大幅 ]</p>
      </td>
   <td>幅が 0 の場合、サイズを取得するにはを使用した最大値を指定できます。 ドキュメントの幅よりも小さい場合は、最大幅が優先されます。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL キャンバスにトリミング ]</p>
      </td>
   <td>レンディションをキャンバスサイズでトリミングする場合は「はい」、レンディションをレイヤーサイズでトリミングする場合は「いいえ」を選択します。</td> 
    </tr>
    </tbody>
</table>

### 画像に透かしを付ける

このアクションモジュールは、選択した画像に透かしを追加します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続を作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （ベース &gt; 入力） ストレージ ]</td>
      <td>
        <p>透かしを追加するファイルを格納するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （ベース &gt; 入力） ファイルの場所 ]</p>
      </td>
   <td> 透かしを追加するファイルの URL またはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （透かし &gt; 入力） ストレージ ]</td>
      <td>
        <p>追加する透かしを格納するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （透かし &gt; 入力） ストレージ ]</td>
      <td>
        <p>追加する透かしを格納するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし &gt; 境界）の高さ ]</p>
      </td>
   <td>透かしの目的の高さをピクセル単位で入力またはマッピングします。</td> 
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし &gt; 境界）の幅 ]</p>
      </td>
   <td> 透かしの目的の幅をピクセル単位で入力またはマッピングします。 </td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし &gt; 境界）左 ]</p>
      </td>
   <td> 透かしにする画像の左側からの距離をピクセル単位で入力またはマッピングします。</td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし &gt; 境界）の上 ]</p>
      </td>
   <td> 透かしにする画像の上部からの距離をピクセル単位で入力またはマッピングします。</td> 
    </tr>  
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ ]</td>
      <td>
        <p>透かし付けファイルを保存するファイルサービスを選択します。</p><p>Fusion の内部ストレージを選択すると、後のモジュールでファイルを使用できるようになりますが、シナリオ外でファイルを使用できるわけではありません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所 ]</p>
      </td>
   <td> 透かし付きファイルが格納される URL またはパスを入力またはマッピングします。 これは、出力ストレージに Fusion 内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ ]</p>
      </td>
   <td>ファイルの変換先となるファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力）の幅 ]</p>
      </td>
   <td> 出力ファイルの幅（ピクセル単位）。 モジュールは、元の縦横比を保持します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き ]</td>
      <td>
        <p>既に存在する出力ファイルを新しく編集したファイルで上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tbody>
</table>
