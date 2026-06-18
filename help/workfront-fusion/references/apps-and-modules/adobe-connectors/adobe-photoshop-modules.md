---
title: Adobe Photoshop モジュール
description: Adobe Photoshop モジュールを使用すると、Adobe Photoshop アカウント内のイベントに基づいてAdobe Workfront Fusion シナリオを開始したり、契約書やその他のレコードを作成、読み取り、更新したり、設定した条件を使用してレコードを検索したり、ドキュメントをアップロードしたりできます。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0e41d1af-af69-4f9b-a5b3-479562254084
TQID: https://experienceleague.adobe.com/RratZmko93V0LMxJ6qTy6cNvRqgPNvNgHTflRngE6BI
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: ce3fb5604ac4ed85af1bcc51143732499dfb0404
workflow-type: tm+mt
source-wordcount: 7285
ht-degree: 13%

---

# [!DNL Adobe Photoshop] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Adobe Photoshop] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。

シナリオの作成手順が必要な場合は、[&#x200B; シナリオの作成：記事インデックス &#x200B;](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)の記事を参照してください。

モジュールについて詳しくは、[モジュール：記事インデックス](/help/workfront-fusion/references/modules/modules-toc.md)の記事を参照してください。

>[!IMPORTANT]
>
>Adobe Photoshopでは、FusionがPhotoshopでアクションを実行するために使用するAPIの一部の要素が廃止されました。
>
>**したがって、既存のPhotoshop モジュールの一部は、2026年7月30日を過ぎると機能しません。**
>
>これらのモジュールを使用するシナリオを、できるだけ早く更新モジュールに更新することをお勧めします。
>
>影響を受けるモジュールの一覧については、[Adobe Photoshop APIの非推奨化に関する更新](#adobe-photoshop-api-deprecation-updates)を参照してください。
>
>APIの変更がWorkfront Fusionにどのような影響を与えるかについて詳しくは、[FusionでのAPIの概要](/help/workfront-fusion/get-started-with-fusion/understand-fusion/api-overview.md)を参照してください。

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
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
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

[!DNL Adobe Photoshop] コネクタを使用する前に、以下の前提条件が満たされていることを確認してください。

* アクティブな [!DNL Adobe Photoshop] アカウントが必要です。
* Firefly Services ライセンスが必要です。
* クライアント IDとクライアントシークレットが必要です。 Adobe Developer Consoleから入手できます。

## Adobe Photoshop APIの非推奨化の更新

Adobe Photoshopでは、FusionがPhotoshopでアクションを実行するために使用するAPIの一部の要素が廃止されました。

**したがって、既存のPhotoshop モジュールの一部は、2026年7月30日を過ぎると機能しません。**

この表では、どのモジュールがこの非推奨（廃止予定）の影響を受けたか、どのモジュールに更新する必要があるかを示しています。

| 非推奨のレガシーモジュール | 新しいモジュールへの更新 |
|---|---|
| PSDの編集を適用 | コンポジットの作成または編集 |
| 画像形式を変換 | コンポジットの作成または編集 |
| コンポジットの作成 | コンポジットの作成または編集 |
| 新しいPSDの作成 | コンポジットの作成または編集 |
| レンディションの作成 | コンポジットの作成または編集 |
| テキストレイヤーを編集 | Photoshopのアクション、スクリプト、変換を実行 |
| テキストレイヤーを編集2 | Photoshopのアクション、スクリプト、変換を実行 |
| アクション JSONの実行 | Photoshopのアクション、スクリプト、変換を実行 |
| 深度ブラーを実行 | (利用不可) |
| Photoshop アクションの実行 | Photoshopのアクション、スクリプト、変換を実行 |
| 商品切り抜きを実行 | Photoshopのアクション、スクリプト、変換を実行 |
| レイヤー情報を取得 | マニフェストを生成 |
| 画像のサイズ変更 | コンポジットの作成または編集 |
| スマートオブジェクトの置き換え | コンポジットの作成または編集 |
| スマートオブジェクト 2の置き換え | コンポジットの作成または編集 |
| 画像の回転 | Photoshopのアクション、スクリプト、変換を実行 |
| 画像に透かし | コンポジットの作成または編集 |

## Adobe Photoshop APIについて

Adobe Photoshop コネクタでは、次の機能が使用されます。

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

1. 任意のモジュールで、接続ボックスの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。

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
          <p>JWT接続またはサーバー間接続のどちらを使用するかを選択します。</p>
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
        <td>[!UICONTROL Adobe] [!UICONTROL Client ID]を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>[!DNL Adobe] [!UICONTROL Client Secret] を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>JWT接続を使用している場合は、[!DNL Adobe] [!UICONTROL Technical account ID]を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>JWT接続を使用している場合は、[!DNL Adobe] [!UICONTROL 組織ID]を入力します。 これは、の[!UICONTROL Credentials]の詳細セクションにあります。 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>JWT接続を使用している場合は、資格情報が[!DNL Adobe Developer Console]で作成されたときに生成された秘密キーを入力します。 </p>
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
              <p>「<b>保存</b>」をクリックしてファイルを抽出し、接続設定に戻ります。</p>
            </li>
          </ol>
        </td>
        </tr>
      </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Adobe Photoshop] モジュールとそのフィールド

[!DNL Adobe Photoshop] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。 これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Adobe Photoshop]」フィールドが表示される場合があります。 モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### アクション

* [16進数をRGBに変換](#convert-hex-to-rgb)
* [アートボードの作成](#create-an-artboard)
* [コンポジットの作成または編集](#create-or-edit-a-composite)
* [様々な調整を行った画像の編集](#edit-an-image-with-various-adjustments)
* [Photoshopのアクション、スクリプト、変換を実行](#execute-photoshop-actions-scripts-and-transformations)
* [マニフェストを生成](#generate-a-manifest)
* [背景を削除](#remove-background)

#### 16進数をRGBに変換

このモジュールは、16進数カラーコードをRGB カラーに変換します。



このモジュールは、Lightroom形式の補正を画像に適用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL HEX]</td>
      <td>RGBに変換する16進数コードを入力またはマッピングします。</td>
    </tr>
    </tbody>
</table>

#### アートボードの作成

このモジュールは、Photoshopで新しいアートボードを作成します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Images]</td>
      <td>
        <p>このアートボードに追加する画像ごとに、<b>項目を追加</b>をクリックし、画像のソースタイプと場所を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL アートボードの間隔]</p>
      </td>
   <td>各アートボード間の間隔をピクセル単位で入力またはマッピングします。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する変換された各ファイルについて、「項目を追加」をクリックし、リストに表示されているストレージ、場所、その他のオプションを入力します。</p>
      </td>
    </tr>
    </tbody>
</table>

#### コンポジットの作成または編集

このモジュールは、Photoshopでコンポジットを作成または編集します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Images]</td>
      <td>
        <p>このアートボードに追加する画像ごとに、<b>項目を追加</b>をクリックし、画像のソースタイプと場所を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td>画像を作成する場合は、画像の幅をピクセル単位で入力します。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Height]</td>
      <td>
        <p>画像を作成する場合は、画像の高さをピクセル単位で入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Mode]</td>
      <td>
        <p>この画像のカラーモードを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fill]</td>
      <td>
        <p>背景レイヤーの塗りのタイプを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>
        <p>新しい画像の名前を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Pixel scale factor]</td>
      <td>
        <p>ピクセル尺度係数を入力またはマッピングします。 0.1から1までの数字を指定してください。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 解像度]</td>
      <td>
        <p><b>値</b> フィールドに、解像度の値を密度単位（インチあたりのピクセル数）で入力します。 デフォルト値は72です。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL プロファイル タイプ &#x200B;]</td>
      <td>
        <p>デフォルトのカラープロファイルを上書きする場合は、プロファイルタイプを選択し、表示されているように詳細を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 切り抜き/上/左/下/右]</td>
      <td>
        <p>画像を切り抜く範囲を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Hide]</td>
      <td>
        <p>「はい」を選択して、切り抜き境界の外側のピクセルを非表示にします。 falseに設定すると、切り抜き境界の外側のピクセルが削除されます。 デフォルトはfalseです。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Resize &gt; Width]</td>
      <td>
        <p>幅に使用する単位を選択し、目的の幅を表す値を選択します。 </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL サイズ変更&gt;高さ]</td>
      <td>
        <p>高さに使用する単位を選択し、目的の高さを表す値を選択します。 </p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL 解像度]</td>
      <td>
        <p>解像度に使用する単位を選択し、目的の解像度を表す値を選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Resample]</td>
      <td>
        <p>リサイズ時に使用するリサンプリング方法を選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL 縦横比を固定]</td>
      <td>
        <p>「はい」を選択して、幅と高さの縦横比を維持します。 幅と高さを個別に調整するには、「いいえ」を選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Rasterize]</td>
      <td>
        <p>画像をラスタライズするかどうかを選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL スケール スタイル &#x200B;]</td>
      <td>
        <p>画像のサイズを変更するときにスタイルに拡大縮小を適用するかどうかを選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL トリミング時]</td>
      <td>
        <p>透明なピクセルをトリミングするかどうかを選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL レイヤー]</td>
      <td>
        <p>後で追加する各項目について、<b>項目を追加</b>をクリックし、レイヤーの詳細を入力します。 </p><p>詳しくは、Adobe ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop-v2/#operation/createComposite"> コンポジットの作成または編集</a>を参照してください。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Default font PostScript name]</td>
      <td>
        <p>使用するデフォルトフォントのPostScript名を入力するか、マッピングします。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL にフォント戦略がありません]</td>
      <td>
        <p>作成または編集を失敗させるか、フォントが使用できない場合にデフォルトのフォントを使用するかを選択します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL 追加フォント &#x200B;]</td>
      <td>
        <p>追加する各フォントについて、<b>項目を追加</b>をクリックし、フォントのソース URLを入力します。 </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する編集ファイルごとに、「項目を追加」をクリックし、出力の詳細を入力します。 </p><p>詳しくは、Adobe ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop-v2/#operation/createComposite"> コンポジットの作成または編集</a>を参照してください。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Maximum number of results]</td>
      <td>
        <p>1回の実行サイクル中にモジュールが処理する結果の最大数を入力またはマッピングします。</p>
      </td>
      </tr>
      </tbody>
</table>

#### 様々な調整を行った画像の編集

このモジュールは、Lightroom形式の補正を画像に適用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Images]</td>
      <td>
        <p>画像のソースタイプと場所を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Other fields]</p>
      </td>
   <td><p>詳しくは、Adobe ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/photoshop-v2/#operation/edit">様々な調整を含む画像の編集</a>を参照してください。</p></td> 
    </tr>
    </tbody>
</table>

#### Photoshopのアクション、スクリプト、変換を実行

このモジュールは、Firefly Photoshop APIで使用できるアクション、スクリプト、変換を実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Images]</td>
      <td>
        <p>画像のソースタイプと場所を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL アクション &#x200B;]</p>
      </td>
   <td><p>追加する各アクションについて、<b>項目を追加</b>をクリックし、アクションのソース、URL、名前を入力します。</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL UXP ソース &#x200B;]</p>
      </td>
   <td><p>UXP スクリプトを使用している場合は、URLまたはインラインコンテンツを提供するかどうかを選択し、URLまたはコンテンツを入力またはマッピングします。</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Additional contents]</p>
      </td>
   <td><p>アクションまたはUXPから参照される最大25個のファイルを追加します。</p></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する編集ファイルごとに、「項目を追加」をクリックし、形式、出力先、出力パターンを入力します。</p>
      </td>
    </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Maximum number of results]</td>
      <td>
        <p>1回の実行サイクル中にモジュールが処理する結果の最大数を入力またはマッピングします。</p>
      </td>
      </tr>
    </tbody>
</table>

#### マニフェストを生成

このモジュールは、指定された入力画像に対してPSD マニフェストを生成します。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Source]</td>
      <td>
        <p>画像のソースタイプと場所を入力またはマッピングします。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する編集ファイルごとに、「項目を追加」をクリックし、宛先の詳細を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL レイヤーのサムネールを含める]</p>
      </td>
   <td><p>マニフェストの各レイヤーのサムネールレンディションを生成するモジュールを作成する場合は、「はい」を選択します。</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL サムネールの最大深度]</p>
      </td>
   <td><p>サムネールレンディションの最大深度を入力またはマッピングします。 深度が最大でない場合は、<code>0</code>と入力します。</p></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layer thumbnail format]</p>
      </td>
   <td><p>サムネールをJPEG形式とPNG形式のどちらに設定するかを選択します。</p></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Extract Smart Object data]</td>
      <td>
        <p>埋め込みスマートオブジェクトを抽出し、マニフェストに事前署名済みURLを含めるかどうかを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 透明部分にトリミング &#x200B;]</td>
      <td>
        <p>各レイヤーサムネールをトリミングして、透明なピクセルを削除するかどうかを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximum number of results]</td>
      <td>
        <p>1回の実行サイクル中にモジュールが処理する結果の最大数を入力またはマッピングします。</p>
      </td>
      </tr>
    </tbody>
</table>

#### 背景を削除

このアクションモジュールは、画像の主な被写体を識別し、背景を削除します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>背景を削除するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> 背景を削除するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL カラースペース &#x200B;]</p>
      </td>
   <td>出力画像でRGBとRGBA カラーのどちらを使用するかを選択します。 </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL マスク形式]</p>
      </td>
   <td>画像のエッジをソフト（ぼかし）にするか、バイナリにするかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>速度を最適化するには「パフォーマンス」を選択し、待ち時間を許可するには「バッチ」を選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post プロセス &#x200B;]</p>
      </td>
   <td>後処理を有効にするかどうかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>デフォルトは4.0です</td> 
    </tr> 
    </tbody>
</table>


### レガシー

* [PSD編集の適用（レガシー）](#apply-psd-edits-legacy)
* [画像の自動カラー補正（レガシー）](#auto-color-correct-an-image-legacy)
* [画像形式の変換（レガシー）](#convert-image-format-legacy)
* [マスクの作成（レガシー）](#create-a-mask-legacy)
* [新しいPSD（レガシー）の作成](#create-a-new-psd-legacy)
* [レンディションの作成（レガシー）](#create-renditions-legacy)
* [テキストレイヤーの編集（レガシー）](#edit-text-layers-legacy)
* [テキストレイヤー2 （レガシー）の編集](#edit-text-layers-2-legacy)
* [アクション JSONの実行（レガシー）](#execute-an-action-json-legacy)
* [深度ぼかし（レガシー）を実行](#execute-depth-blur-legacy)
* [Photoshop アクションの実行（レガシー）](#execute-photoshop-actions-legacy)
* [製品切り抜きの実行（レガシー）](#execute-product-crop-legacy)
* [レイヤー情報の取得（レガシー）](#get-layer-info-legacy)
* [カスタム API呼び出しを行う（レガシー）](#make-a-custom-api-call-legacy)
* [背景を削除（レガシー） &#x200B;](#remove-background-legacy)
* [スマートオブジェクトの置換（レガシー）](#replace-a-smart-object-legacy)
* [スマートオブジェクト 2 （レガシー）の置き換え](#replace-a-smart-object-2-legacy)
* [画像のサイズ変更（レガシー）](#resize-an-image-legacy)
* [画像の透かし（レガシー）](#watermark-an-image-legacy)

#### PSD編集の適用（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

このアクションモジュールは、ドキュメントおよびレイヤーレベルのさまざまな編集を適用します。

このモジュールは大きなファイルをサポートします。 大きなファイルについて詳しくは、[大きなファイルの操作](/help/workfront-fusion/references/scenarios/fusion-large-files.md)を参照してください。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）の高さ]</p>
      </td>
      <td> 画像の高さをピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）幅]</p>
      </td>
      <td> 画像の幅をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options &gt; Document &gt; Canvas size） Top]</p>
      </td>
   <td> ドキュメントの左上隅のY座標をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options &gt; Document &gt; Canvas size） Bottom]</p>
      </td>
   <td> ドキュメントの右下隅のY座標をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/カンバスサイズ）左]</p>
      </td>
   <td> ドキュメントの左上隅のx座標をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options &gt; Document &gt; Canvas size） Right]</p>
      </td>
   <td> ドキュメントの右下隅のx座標をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント） トリミング &#x200B;]</p>
      </td>
   <td> 「透明なピクセル」を選択して、画像内の透明なピクセルに基づいてトリムを作成します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options） Default font]</p>
      </td>
   <td> ドキュメントのグローバルデフォルトとして使用するフォントの完全なPostscript名を入力します。 このフォントは、見つからないフォントを持ち、そのレイヤーに他のフォントが特別に提供されていないテキストレイヤーに使用されます。 このフォントが見つからない場合は、「見つからないフォントを管理」で指定したオプションが有効になります。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options） Fonts]</p>
      </td>
   <td> ドキュメントに必要な各フォントについて、「項目を追加」をクリックし、フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）環境にないフォントの管理]</p>
      </td>
   <td> ドキュメント内に1つ以上の環境にないフォントがある場合に実行するアクションを選択します。 <ul><li><code>fail</code>：ジョブは成功せず、ステータスは失敗に設定され、エラーの詳細はステータスの「詳細」セクションに記載されます。</li><li><code>useDefault</code>：ジョブは成功し、欠落しているすべてのフォントはArialMTに置き換えられます。</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） レイヤー]</p>
      </td>
   <td> 追加する各レイヤーについて、「項目を追加」をクリックし、レイヤーの詳細を入力します。 <p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの「<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/modifyDocumentAsync">PSDの編集を適用</a>」を参照してください。  </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する編集済みファイルごとに、「項目を追加」をクリックし、リストに表示されているストレージ、場所、タイプを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。 これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td>ファイルを変換するファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Trim to Canvas]</p>
      </td>
   <td>レンディションをカンバスサイズにする必要があるかどうかを選択します。 Trueを指定するとレンディションがカンバスサイズにトリミングされ、Falseを指定するとレンディションのレイヤーサイズが設定されます</td> 
    </tr>
    </tbody>
</table>

#### 画像の自動カラー補正（レガシー）

このアクションモジュールは、指定した画像を自動カラー補正します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>カラー補正するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> カラー補正するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。 これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td>ファイルを変換するファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    </tbody>
</table>

#### 画像形式の変換（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

このアクションモジュールは、ファイルをJPEG、PNG、PSDまたはTIFFに変換します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>背景を削除するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> 背景を削除するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する変換された各ファイルについて、「項目を追加」をクリックし、リストに表示されているようにストレージ、場所、およびタイプを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。 これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td>ファイルを変換するファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    </tbody>
</table>

#### マスクの作成（レガシー）

このアクションモジュールは、被写体の周囲にマスクが適用されたPNG ファイルを返します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>マスクを作成するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> マスクを作成するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>マスクファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> マスクファイルの保存先のURLまたはパスを入力またはマッピングします。 これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL カラースペース &#x200B;]</p>
      </td>
   <td>出力画像でRGBとRGBA カラーのどちらを使用するかを選択します。 </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL マスク形式]</p>
      </td>
   <td>マスクをソフト（ぼかし）にするか、バイナリにするかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>速度を最適化するには「パフォーマンス」を選択し、待ち時間を許可するには「バッチ」を選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post プロセス &#x200B;]</p>
      </td>
   <td>後処理を有効にするかどうかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>デフォルトは4.0です</td> 
    </tr> 
    </tbody>
</table>

#### 新しいPSD（レガシー）の作成

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

このアクションモジュールは、オプションのレイヤーを含む新しいPSDを作成し、レンディションまたはPSDとして保存します。

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
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）の高さ]</p>
      </td>
      <td> 画像の高さをピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント/画像サイズ）幅]</p>
      </td>
      <td> 画像の幅をピクセル単位で入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント）解像度]</p>
      </td>
   <td> 画像の解像度をインチあたりのピクセル単位で入力またはマッピングします。 これは72から300の間である必要があります。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション &gt; ドキュメント） モード &#x200B;]</p>
      </td>
   <td> 画像のモードを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント）入力]</p>
      </td>
   <td> 背景レイヤーの塗りつぶしを透明、白、または画像の背景色にするかどうかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション/ドキュメント）の深さ]</p>
      </td>
   <td> 画像のビット深度を選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション） レイヤー]</p>
      </td>
   <td> 追加する各レイヤーについて、「項目を追加」をクリックし、レイヤーの詳細を入力します。 <p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの「<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">PSDを作成</a>」を参照してください。  </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options） Global font]</p>
      </td>
   <td> ドキュメントのグローバルデフォルトとして使用するフォントの完全なPostscript名を入力します。 このフォントは、見つからないフォントを持ち、そのレイヤーに他のフォントが特別に提供されていないテキストレイヤーに使用されます。 このフォントが見つからない場合は、「見つからないフォントを管理」で指定したオプションが有効になります。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options） Fonts]</p>
      </td>
   <td> ドキュメントに必要な各フォントについて、「項目を追加」をクリックし、フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （オプション）環境にないフォントの管理]</p>
      </td>
   <td> ドキュメント内に1つ以上の環境にないフォントがある場合に実行するアクションを選択します。 <ul><li><code>fail</code>：ジョブは成功せず、ステータスは失敗に設定され、エラーの詳細はステータスの「詳細」セクションに記載されます。</li><li><code>useDefault</code>：ジョブは成功し、欠落しているすべてのフォントはArialMTに置き換えられます。</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する各ファイルについて、「項目を追加」をクリックし、リストに表示されているようにストレージ、場所、およびタイプを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。 これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td>ファイルを変換するファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Other fields]</td>
      <td>
        <p><p>出力オプションについて詳しくは、Adobe Photoshop ドキュメントの「<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">PSDを作成</a>」を参照してください。  </p>
      </td>
    </tr>
    </tbody>
</table>

#### レンディションの作成（レガシー）

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する各ファイルについて、「項目を追加」をクリックし、リストに表示されているストレージ、場所、タイプ、および上書きオプションを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイルの場所]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ &#x200B;]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
      </tbody>
</table>

#### テキストレイヤーの編集（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[Photoshopのアクション、スクリプト、変換の実行](#execute-photoshop-actions-scripts-and-transformations) モジュールに更新します。

このアクションモジュールは、Photoshop ファイルのテキストレイヤーを編集します。 同じファイル内の複数のレイヤーに対して、個別の編集の詳細を入力できます。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>ドキュメント内に1つ以上の環境にないフォントがある場合に実行するアクションを選択します。 フォントが指定されていない場合、モジュールはデフォルトのフォントを使用します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>ドキュメントのグローバルデフォルトとして使用するフォントの完全なPostscript名を入力します。 このフォントは、見つからないフォントを持ち、そのレイヤーに他のフォントが特別に提供されていないテキストレイヤーに使用されます。 このフォントが見つからない場合は、「見つからないフォントを管理」で指定したオプションが有効になります。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options） Fonts]</p>
      </td>
   <td> フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL レイヤー]</td>
   <td> <p>編集する各テキストレイヤーについて、<b>項目を追加</b>をクリックし、レイヤーオプションを入力します。<p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync"> テキストを編集</a>を参照してください。</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>

#### テキストレイヤー2 （レガシー）の編集

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[Photoshopのアクション、スクリプト、変換の実行](#execute-photoshop-actions-scripts-and-transformations) モジュールに更新します。

このアクションモジュールは、Photoshop ファイルのテキストレイヤーを編集します。

複数のレイヤーを編集するには、[&#x200B; テキストレイヤーを編集](#edit-text-layers) モジュールを使用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>ドキュメント内に1つ以上の環境にないフォントがある場合に実行するアクションを選択します。 フォントが指定されていない場合、モジュールはデフォルトのフォントを使用します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>ドキュメントのグローバルデフォルトとして使用するフォントの完全なPostscript名を入力します。 このフォントは、見つからないフォントを持ち、そのレイヤーに他のフォントが特別に提供されていないテキストレイヤーに使用されます。 このフォントが見つからない場合は、「見つからないフォントを管理」で指定したオプションが有効になります。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Options） Fonts]</p>
      </td>
   <td> フォントの保存場所とファイルの場所を入力します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL レイヤー]</td>
   <td> <p>レイヤーオプションについて詳しくは、Adobe Photoshop ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync"> テキストレイヤーの編集</a>を参照してください。</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 出力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
  </tbody>
</table>


#### アクション JSONの実行（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[Photoshopのアクション、スクリプト、変換の実行](#execute-photoshop-actions-scripts-and-transformations) モジュールに更新します。

このアクションモジュールは、JSON コマンドを使用してPhotoshop アクションを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action JSON]</td>
      <td>
        <p>実行するアクションのJSON コマンドを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL フォント / パターン / ブラシ / 追加画像]</td>
      <td>
        <p>このアクションで使用する各フォント、パターン、ブラシ、または追加の画像について、「項目を追加」をクリックし、項目の保存場所とファイルの場所を入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL フォント / パターン / ブラシファイル URL]</p>
      </td>
   <td> 使用するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する各ファイルについて、「項目を追加」をクリックし、リストに表示されているストレージ、場所、タイプ、および上書きオプションを入力します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイル URL]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ &#x200B;]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
      </tbody>
</table>

#### 深度ぼかし（レガシー）を実行

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。

このアクションモジュールは、選択したファイルに対して深度ぼかしを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイル URL]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ &#x200B;]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>その他の深度ぼかしオプションについて詳しくは、Adobe Photoshop API ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">深度ぼかしの実行</a>を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

#### Photoshop アクションの実行（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[Photoshopのアクション、スクリプト、変換の実行](#execute-photoshop-actions-scripts-and-transformations) モジュールに更新します。

このアクションモジュールは、選択した画像に対してPhotoshop アクションを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>編集するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 編集するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Actions ファイル ストレージ &#x200B;]</td>
      <td>
        <p>アクションファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Actions ファイル URL]</p>
      </td>
   <td> アクションファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL アクション名]</p>
      </td>
   <td> 特定のアクションのみを実行する場合は、ActionSetから再生するアクションを指定できます。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL フォント / パターン / ブラシ保存]</td>
      <td>
        <p>使用するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL フォント / パターン / ブラシファイル URL]</p>
      </td>
   <td> 使用するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイル URL]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ &#x200B;]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>その他の深度ぼかしオプションについて詳しくは、Adobe Photoshop API ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">深度ぼかしの実行</a>を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 製品切り抜きの実行（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[Photoshopのアクション、スクリプト、変換の実行](#execute-photoshop-actions-scripts-and-transformations) モジュールに更新します。

このアクションモジュールは、選択した画像に対して商品切り抜きを実行します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>切り抜くファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> 切り抜くファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Unit]</p>
      </td>
   <td> 高さと幅の調整をピクセル単位で表すか、パーセント単位で表すかを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> 追加する幅パディングの量を入力またはマップします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Height]</p>
      </td>
   <td> 追加する高さパディングの量を入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力） ストレージ &#x200B;]</td>
      <td>
        <p>編集したファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） ファイル URL]</p>
      </td>
   <td> 編集したファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ &#x200B;]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （出力）上書き]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>その他の深度ぼかしオプションについて詳しくは、Adobe Photoshop API ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">深度ぼかしの実行</a>を参照してください。</p>
      </td>
    </tr>
  </tbody>
</table>

#### レイヤー情報の取得（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[&#x200B; マニフェストを生成](#generate-a-manifest) モジュールに更新します。

このアクションモジュールは、指定したPSD ファイルからレイヤー情報を取得します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 入力ファイル ストレージ &#x200B;]</td>
      <td>
        <p>レイヤー情報を取得するファイルが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 入力ファイル URL]</p>
      </td>
   <td> レイヤー情報を取得するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL サムネール &#x200B;]</p>
      </td>
   <td> サムネールを作成するファイルのタイプを選択します。 サムネールは、レンダリング可能なレイヤーの小さなプレビューです。</td> 
    </tr>
  </tbody>
</table>

#### カスタム API 呼び出しの実行

このアクションモジュールは、Photoshop APIをカスタム呼び出します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p><code>https://image.adobe.io/pie/psdService</code> からの相対パスを入力します。 例： <code>/photoshopActions</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>API 呼び出しの設定に必要な HTTP リクエストメソッドを選択します。 詳しくは、<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP リクエスト方法</a>を参照してください。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>リクエストのヘッダーを標準 JSON オブジェクトの形式で追加します。</p>
        <p>例： <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion は認証ヘッダーを自動的に追加します。</p>
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

#### スマートオブジェクトの置換（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

このアクションモジュールは、PSD レイヤー内のスマートオブジェクトを置き換え、新しいレンディションを生成します。

このモジュールでは、スマートオブジェクト API バージョン 2を使用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>スマートオブジェクトが保存されるファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> スマートオブジェクトのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL レイヤー]</p>
      </td>
   <td>スマートオブジェクトに追加する各レイヤーについて、「項目を追加」をクリックし、オブジェクトの名前またはID、スマートオブジェクトが保存されているファイルサービス、レイヤーのURLまたはパスを入力します。<p>この領域の詳細設定について詳しくは、Photoshop API ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync"> スマートオブジェクトの置き換え</a>を参照してください </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Resize image during place]</p>
      </td>
   <td> 画像のサイズを変更するかどうかを選択します。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>モジュールで作成する新しいレンディションごとに、「項目を追加」をクリックし、次のフィールドに入力します。 最大25個の出力ファイルを持つことができます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力） タイプ &#x200B;]</p>
      </td>
   <td> 編集したファイルのファイルタイプを選択します。 </td> 
    </tr>
     </tbody>
</table>

#### スマートオブジェクト 2 （レガシー）の置き換え

このアクションモジュールは、PSD レイヤー内のスマートオブジェクトを置き換え、新しいレンディションを生成します。

このモジュールでは、従来のバージョンのスマートオブジェクトを使用します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Input） ストレージ &#x200B;]</td>
      <td>
        <p>スマートオブジェクトが保存されるファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Input） ファイルの場所]</p>
      </td>
   <td> スマートオブジェクトのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL レイヤー]</p>
      </td>
   <td>スマートオブジェクトに追加する各レイヤーについて、「項目を追加」をクリックし、オブジェクトの名前またはID、スマートオブジェクトが保存されているファイルサービス、レイヤーのURLまたはパスを入力します。<p>この領域の詳細設定について詳しくは、Photoshop API ドキュメントの<a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync"> スマートオブジェクトの置き換え</a>を参照してください </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>モジュールで作成する新しいレンディションごとに、「項目を追加」をクリックし、次のフィールドに入力します。 最大25個の出力ファイルを持つことができます。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力）幅]</p>
      </td>
   <td> 出力ファイルの幅（ピクセル単位）。 モジュールは元の縦横比を保持します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tbody>
</table>

#### 画像のサイズ変更（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

このアクションは、同じ縦横比を使用して画像のサイズを変更します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL ストレージ &#x200B;]</td>
      <td>
        <p>サイズ変更するファイルが格納されているファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ファイルの場所]</p>
      </td>
   <td> サイズ変更するファイルのURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>作成する変換された各ファイルについて、「項目を追加」をクリックし、リストに表示されているストレージ、場所、その他のオプションを入力します。</p>
      </td>
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL ストレージ &#x200B;]</td>
      <td>
        <p>新しいファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL ファイルの場所]</p>
      </td>
   <td> 新しいファイルの保存先のURLまたはパスを入力またはマッピングします。  これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> 出力ファイルの幅（ピクセル単位）。 モジュールは元の縦横比を保持します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Max width]</p>
      </td>
   <td>widthが0の場合、を指定してサイズを取得できます。 最大の幅は、ドキュメントの幅よりも小さい値が優先されます。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL カンバスにトリミング &#x200B;]</p>
      </td>
   <td>レンディションをカンバスサイズにトリミングするには「はい」を選択し、レンディションをレイヤーサイズにするには「いいえ」を選択します。</td> 
    </tr>
    </tbody>
</table>

#### 画像の透かし（レガシー）

>[!NOTE]
>
>このモジュールは非推奨（廃止予定）となり、2026年7月30日を過ぎると機能しなくなります。
>このモジュールを[複合](#create-or-edit-a-composite) モジュールの作成または編集に更新します。

このアクションモジュールは、選択した画像に透かしを追加します。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>[!DNL Adobe Photoshop] への接続を作成する手順については、この記事の<a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >[!DNL Adobe Photoshop]</a> への接続の作成を参照してください。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Base &gt; Input） ストレージ &#x200B;]</td>
      <td>
        <p>透かしを追加するファイルが保存されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Base &gt; Input） ファイルの場所]</p>
      </td>
   <td> 透かしを追加するファイルのURLまたはパスを入力またはマッピングします。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （透かし/入力） ストレージ &#x200B;]</td>
      <td>
        <p>追加する透かしが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （透かし/入力） ストレージ &#x200B;]</td>
      <td>
        <p>追加する透かしが格納されているファイルサービスを選択します。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし/境界）の高さ]</p>
      </td>
   <td>透かしの高さをピクセル単位で入力またはマッピングします。</td> 
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし/境界）の幅]</p>
      </td>
   <td> 透かしの望ましい幅をピクセル単位で入力またはマッピングします。 </td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし/境界）左]</p>
      </td>
   <td> 透かしを配置する画像の左側からの距離をピクセル単位で入力またはマッピングします。</td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （透かし/境界）上]</p>
      </td>
   <td> 透かしを配置する画像の上部からの距離をピクセル単位で入力またはマッピングします。</td> 
    </tr>  
    <tr>
      <td role="rowheader">[!UICONTROL （Output） ストレージ &#x200B;]</td>
      <td>
        <p>透かし入りファイルを保存するファイルサービスを選択します。</p><p>Fusionの内部ストレージを選択すると、ファイルは後のモジュールで使用できますが、シナリオ外では使用できません。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） ファイルの場所]</p>
      </td>
   <td> 透かし入りファイルの保存先のURLまたはパスを入力またはマッピングします。 これは、出力ストレージにFusion内部ストレージを選択していない場合にのみ必要です。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （Output） Type]</p>
      </td>
   <td>ファイルを変換するファイルタイプを選択します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL （出力）幅]</p>
      </td>
   <td> 出力ファイルの幅（ピクセル単位）。 モジュールは元の縦横比を保持します。 </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL （Output） Overwrite]</td>
      <td>
        <p>新しく編集したファイルが、既に存在する出力ファイルを上書きするかどうかを選択します。 これは、Adobe ストレージ内のファイルにのみ適用されます。</p>
      </td>
    </tbody>
</table>
