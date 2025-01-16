---
title: Web フック
description: Web フックは、イベントによってトリガーされる HTTP 呼び出しです。Web フックを使用して、インスタントトリガーモジュールをアクティベートできます。インターネットに接続しており、HTTP リクエストを許可するアプリケーションは、Adobe Workfront Fusion に web フックを送信できます。
author: Becky
feature: Workfront Fusion
exl-id: 8e415378-e9c1-4b49-874b-6d38aba0c303
source-git-commit: d5ab7dc135206a7269ad4fa0b5c02bf77b97d873
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 67%

---

# Web フック



<!--This information moved to the webhooks article in the create scenarios folders in the new repo-->

Web フックは、イベントによってトリガーされる HTTP 呼び出しです。Web フックを使用して、インスタントトリガーモジュールをアクティベートできます。インターネットに接続しており、HTTP リクエストを許可するアプリケーションは、Adobe Workfront Fusion に web フックを送信できます。

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

## [!DNL Workfront Fusion] で web フックを使用

>[!NOTE]
>
>サードパーティの web フック（送信 web フック）を呼び出すには、いずれかの HTTP モジュールを使用します。詳しくは、[HTTP モジュール](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)を参照してください。

Web フックを使用してアプリを [!DNL Workfront Fusion] に接続するには、次の手順に従います。

1. **[!UICONTROL Webhooks]**/**[!UICONTROL Custom Webhook]** インスタントトリガーモジュールをシナリオに追加します。

1. Webhook フィールドの横にある「**[!UICONTROL Add]**」をクリックし、新しい Webhook の名前を入力します。
1. （任意）「**[!UICONTROL Advanced Settings]**」をクリックします。
1. 「**[!UICONTROL IP restrictions]**」フィールドに、モジュールがデータを受け入れ可能な IP アドレスのコンマ区切りリストを入力します。
1. **[!UICONTROL Save]** をクリック

Web フックを作成すると、一意の URL が表示されます。これは、web フックがデータを送信するアドレスです。Workfront Fusion は、このアドレスに送信されたデータを検証し、そのデータをシナリオでの処理に渡します。

>[!NOTE]
>
>Web フックを作成したら、一度に複数のシナリオで使用できます。

### Web フックのデータ構造を設定 {#configure-the-webhook-s-data-structure}

受信ペイロードのデータ構造を認識するために、[!DNL Workfront Fusion] は、表示されたアドレスに送信したサンプルデータを解析します。 サンプルデータを指定するには、そのサービスまたはアプリを変更して、サービスまたはアプリが web フックを呼び出すようにします。例えば、ファイルを削除できます。

または、[!UICONTROL HTTP]/[!UICONTROL Make a request] モジュールを介してサンプルデータを送信できます。

1. **[!UICONTROL HTTP]**/**[!UICONTROL Make a request]** モジュールを使用して新しいシナリオを作成します

1. 次の値を使用してモジュールを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"><p>[!UICONTROL URL] </p></td> 
      <td>Web フックの URL を入力します。この URL は、Webhook の設定に使用した [!UICONTROL Webhooks] モジュールにあります。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Method] </td> 
      <td><p>[!UICONTROL POST]</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Body type]</td> 
      <td><p> [!UICONTROL Raw]</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Content type]</td> 
      <td><p> JSON（application/json）</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Request content]</td> 
      <td><p>Web フックには生の JSON が必要です。</p></td> 
     </tr> 
    </tbody> 
   </table>

   ![](/help/workfront-fusion/references/apps-and-modules/assets/new-scenario-set-up-like-this-350x446.png)

1. 別のブラウザータブまたはウィンドウで、[!UICONTROL Webhooks] モジュールを使用してシナリオを開きます。
1. Webhook モジュールで、「**[!UICONTROL Redetermine data structure]**」をクリックします。

   Webhooks モジュールから他のモジュールのリンクを解除する必要はありません。

1. [!UICONTROL HTTP] モジュールでシナリオに切り替えて実行します。
1. Webhooks モジュールを使用してシナリオに戻ります。

   「[!UICONTROL Successfully determined]」メッセージは、モジュールがデータ構造を正常に決定したことを意味します。

   ![](/help/workfront-fusion/references/apps-and-modules/assets/successfully-determined-350x175.png)

1. 「**[!UICONTROL OK]**」をクリックして、データ構造を保存します。

   これで、web フックの項目がマッピングパネルに表示され、シナリオの後続モジュールで使用できるようになりました。

## Webhook キュー

Web フックがデータを受け取り、そのデータを期待するアクティブなシナリオがない場合、データはキューに格納されます。シナリオをアクティベートすると、キューで待機しているすべてのバンドルが順番に処理されます。

>[!IMPORTANT]
>
>Web フックのキューは、同じ web フックを使用するシナリオ間で共有されます。いずれかのシナリオが無効な場合、すべての受信データはキューに保持されます。

## サポートされる受信データ形式

[!DNL Workfront Fusion] は、[!UICONTROL Query String]、[!UICONTROL Form Data]、[!UICONTROL JSON] の 3 種類の受信データ形式をサポートしています。

[!DNL Workfront Fusion] は、選択したデータ構造に対するすべての受信データを検証します。次に、シナリオの設定に応じて、データは処理用のキューに格納されるか、すぐに処理されます。

データのいずれかの部分が検証に合格しない場合、[!DNL Workfront Fusion] は 400 HTTP ステータスコードを返し、HTTP 応答の本文で、受信データが検証チェックに失敗した理由を指定します。受信データの検証が成功した場合、Workfront Fusion は「[!UICONTROL 200 Accepted]」ステータスを返します。

* [[!UICONTROL Query String]](#query-string)
* [[!UICONTROL Form Data]](#form-data)
* [[!UICONTROL JSON]](#json)

### [!UICONTROL Query String]

```
GET https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>?name=<yourname>&job=automate
```

### [!UICONTROL Form Data]

```
POST https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>

Content-Type: application/x-www-form-urlencoded

name=<yourname>&job=automate
```

#### マルチパートフォームデータ

```
POST https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>


Content-Type: multipart/form-data; boundary=---generatedboundary

---generatedboundary

Content-Disposition: form-data; name="file"; filename="file.txt"


Content-Type: text/plain


Content of file.txt


---generatedboundary

Content-Disposition: form-data; name="name"

Workfront Fusion

---generatedboundary
```

`multipart/form-data` でエンコードされたファイルを受信するには、ネストされたフィールド `name`、`mime`、`data` を含む `collection` タイプのフィールドを使用してデータ構造を設定する必要があります。フィールド `name` は `text` タイプで、アップロードされたファイルの名前が含まれます。`mime` は `text` タイプで、MIME 形式のファイルが含まれます。フィールド `data` は `buffer` タイプで、転送中のファイルのバイナリデータが含まれます。

MIME 形式について詳しくは、[MIME モジュール](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/mime.md)を参照してください。

### [!UICONTROL JSON]

```
POST https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>

Content-Type: application/json

{"name": "Workfront Fusion", "job": "automate"}
```

>[!TIP]
>
>元の JSON にアクセスする場合は、web フックの設定時に JSON パススルーを有効にします。
>
>1. 「**[!UICONTROL Add]**」をクリックして、新しい Webhook を追加します。
>1. **[!UICONTROL Show advanced settings]** をクリックします。
>1. **[!UICONTROL JSON pass-through]** をクリックします。
>

## Web フックヘッダー

Web フックのヘッダーにアクセスするには、web フックの設定時に GET リクエストヘッダーを有効にします。

1. 「**[!UICONTROL Add]**」をクリックして、新しい Webhook を追加します。
1. **[!UICONTROL Show advanced settings]** をクリックします。
1. **[!UICONTROL Get request headers]** をクリックします。

`map()` 関数と `get()` 関数を組み合わせて、特定のヘッダー値を抽出することができます。

>[!INFO]
>
>**例：**
>
>以下の例は、`Headers[]` 配列から `authorization` ヘッダーの値を抽出する式を示しています。この式は、抽出された値と指定されたテキストを比較し、一致する場合に web フックのみを渡すフィルターで使用されます。
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/set-up-a-filter-350x169.png)
>
>指定されたキーを使用して配列の要素を取得する方法については、「配列をマッピングする」の [ 指定されたキーを使用して配列の要素をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md#map-an-arrays-element-with-a-given-key) を参照してください。

## Web フックへの応答

Web フック呼び出しに対するデフォルトの応答は、「受理」というテキストです。応答は、カスタム web フックモジュールの実行中に web フックを呼び出したアプリに返されます。

* [Web フックへの応答のテスト](#test-the-response-to-a-webhook)
* [HTML 応答の例](#html-response-example)
* [リダイレクトの例](#redirect-example)

### Web フックへの応答をテスト

1. シナリオに **[!UICONTROL Custom Webhook]** モジュールを含めます。
1. モジュールに新しい web フックを追加します。
1. Web フックの URL をクリップボードにコピーします。
1. シナリオを実行します。

   [!UICONTROL Custom Webhook] モジュールの稲妻アイコンが点を回転するように変わります。 これは、モジュールが web フック呼び出しを待機していることを示しています。

1. 新しいブラウザーウィンドウを開き、コピーした URL をアドレスバーに貼り付け、**[!UICONTROL Enter]** キーを押します。

   [!UICONTROL Custom Webhook] モジュールがトリガーされ、ブラウザーに新しいページが表示されます。

Web フックの応答をカスタマイズする場合は、web フックの応答モジュールを使用します。

モジュールの設定には、[!UICONTROL Status] と [!UICONTROL Body] の 2 つのフィールドが含まれています。

* [!UICONTROL Status] フィールドには、成功の場合は 2xx （例：OK の場合は `200`）、リダイレクトの場合は 3xx （例：一時的なリダイレクトの場合は `307`）、クライアントエラーの場合は 4xx （例：無効なリクエストの場合は `400`）などの HTTP 応答ステータスコードが含まれています。

* [!UICONTROL Body] フィールドには、Webhook の呼び出しで受け入れられるすべての項目が含まれます。 シンプルなテキスト、HTML、XML、JSON などが含まれます。

  >[!TIP]
  >
  >`Content-Type` ヘッダーを対応する MIME タイプに設定することをお勧めします。プレーンテキストの場合は `text/plain`、HTMLの場合は `text/html`、JSON の場合は `application/json`、XML の場合は `application/xml` などです。MIME タイプについて詳しくは、[MIME モジュール](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/mime.md)を参照してください。

応答の送信のタイムアウトは 40 秒です。その期間内に応答が利用できない場合、Workfront Fusion は「200 受理」ステータスを返します。

### HTML 応答の例

>[!INFO]
>
>**例：**
>
>[!UICONTROL Webhook Response] モジュールを次のように設定します。
>
><table style="table-layout:auto"> 
&gt; <col> 
&gt; <col> 
&gt; <tbody> 
&gt;  <tr> 
&gt;   <td role="rowheader">[!UICONTROL Status] </td> 
&gt;   <td> <p>2xx 成功 HTTP ステータスコード（例：200）</p> </td> 
&gt;  </tr> 
&gt;  <tr> 
&gt;   <td role="rowheader">[!UICONTROL Body] </td> 
&gt;   <td> <p>HTML コード</p> </td> 
&gt;  </tr> 
&gt;  <tr> 
&gt;   <td role="rowheader"> <p>[!UICONTROL Custom headers]</p> </td> 
&gt;   <td> 
&gt;    <ul> 
&gt;     <li><strong>キー</strong>：Content-type</li> 
&gt;     <li><strong>値</strong>：text/html</li> 
&gt;    </ul> </td> 
&gt;  </tr> 
&gt; </tbody> 
&gt;</table>
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/custom-headers-350x235.png)
>
>これにより、web ブラウザーに表示される HTML 応答が生成されます。
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/html-response-350x70.png)

### リダイレクトの例

>[!INFO]
>
>**例：**[!UICONTROL Webhook Response] モジュールを次のように設定します。
>
><table style="table-layout:auto"> 
&gt; <col> 
&gt; <col> 
&gt; <tbody> 
&gt;  <tr> 
&gt;   <td role="rowheader">[!UICONTROL Status] </td> 
&gt;   <td> <p>3xx リダイレクト HTTP ステータスコード（例：303）</p> </td> 
&gt;  </tr> 
&gt;  <tr> 
&gt;   <td role="rowheader"> <p>[!UICONTROL Custom headers]</p> </td> 
&gt;   <td> 
&gt;    <ul> 
&gt;     <li><strong>[!UICONTROL Key]</strong>：場所</li> 
&gt;     <li><strong>[!UICONTROL Value]</strong>：リダイレクト先の URL。</li> 
&gt;    </ul> </td> 
&gt;  </tr> 
&gt; </tbody> 
&gt;</table>
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/webhook-response-350x279.png)

## Webhook の無効化

次のいずれかに該当する場合、Web フックは自動的に非アクティブ化されます。

* Web フックが 6 日以上どのシナリオにも接続されていない
* Web フックが、非アクティブなシナリオ（非アクティブになってから 30 日を超えたシナリオ）でのみ使用される。

非アクティブ化された web フックは、いかなるシナリオにも接続されておらず、非アクティブ状態となって 30 日が経過した場合、自動的に削除され、登録解除されます。


## トラブルシューティング

### マッピングパネルに項目がありません

[!UICONTROL Webhooks]/[!UICONTROL Custom Webhook] モジュールに続くモジュールの設定のマッピングパネルに一部の項目がない場合は、**[!UICONTROL Webhooks]/[!UICONTROL Custom Webhook]** モジュールをクリックして設定を開き、「**[!UICONTROL Re-determine data structure]**」をクリックします。

![](/help/workfront-fusion/references/apps-and-modules/assets/redetermine-data-structure-btn-350x195.png)

次に、この記事の [web フックのデータ構造の設定](#configure-the-webhook-s-data-structure)の節で説明されている手順に従います。
