---
title: Web フック
description: Web フックは、イベントによってトリガーされる HTTP 呼び出しです。Web フックを使用して、インスタントトリガーモジュールをアクティベートできます。インターネットに接続しており、HTTP リクエストを許可するアプリケーションは、Adobe Workfront Fusion に web フックを送信できます。
author: Becky
feature: Workfront Fusion
exl-id: 8e415378-e9c1-4b49-874b-6d38aba0c303
source-git-commit: f4d3c64b1cf7f34ca71f8882a8f65c11afe674f5
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 77%

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

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Workfront Fusion での Webhook の使用

>[!NOTE]
>
>サードパーティの web フック（送信 web フック）を呼び出すには、いずれかの HTTP モジュールを使用します。詳しくは、[HTTP モジュール](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)を参照してください。

Webhook を使用してアプリをWorkfront Fusion に接続するには：

1. **[!UICONTROL Webhook]**/**[!UICONTROL Custom Webhook]** インスタントトリガーモジュールをシナリオに追加します。

1. Web フックフィールドの横にある「**[!UICONTROL 追加]**」をクリックして、新規 web フックの名前を入力します。
1. （オプション）「**[!UICONTROL 詳細設定]**」をクリックします。
1. **[!UICONTROL IP 制限]**&#x200B;フィールドに、モジュールがデータを受け入れることができる IP アドレスのカンマ区切りのリストを入力します。
1. 受信データを検証する場合は、「**データ構造**」フィールドで、使用するデータ構造を選択または追加します。

   データ構造について詳しくは、[&#x200B; データ構造 &#x200B;](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md) を参照してください。
1. 「**資格情報**」フィールドに、認証に使用する資格情報を入力できます。 資格情報を入力するには、「**追加**」をクリックして、資格情報を入力します。
1. 必要に応じて他の設定を有効にします。
1. 「**[!UICONTROL 保存]**」をクリックします。

Web フックを作成すると、一意の URL が表示されます。これは、web フックがデータを送信するアドレスです。Workfront Fusion は、このアドレスに送信されたデータを検証し、そのデータをシナリオでの処理に渡します。

>[!NOTE]
>
>Webhook を作成すると、一度に複数のシナリオで使用できます。

### Web フックのデータ構造を設定 {#configure-the-webhook-s-data-structure}

Workfront Fusion は、受信ペイロードのデータ構造を認識するために、表示されたアドレスに送信するサンプルデータを解析します。 サンプルデータを指定するには、そのサービスまたはアプリを変更して、サービスまたはアプリが web フックを呼び出すようにします。例えば、ファイルを削除できます。

または、[!UICONTROL HTTP]/[!UICONTROL &#x200B; リクエストを行う &#x200B;] モジュールを介してサンプルデータを送信できます。

1. **[!UICONTROL HTTP]**／**[!UICONTROL リクエストを実行]**&#x200B;モジュールを使用して、新しいシナリオを作成します。

1. 次の値を使用してモジュールを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"><p>[!UICONTROL URL] </p></td> 
      <td>Web フックの URL を入力します。この URL は、web フックの設定に使用した [!UICONTROL Webhooks] モジュールに含まれています。</td> 
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

   ![&#x200B; 新しいシナリオの設定 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/new-scenario-set-up-like-this-350x446.png)

1. 別のブラウザーのタブまたはウィンドウで、[!UICONTROL Webhooks] モジュールを使用してシナリオを開きます。
1. Webhooks モジュールで、「**[!UICONTROL データ構造を再決定]**」をクリックします。

   Webhooks モジュールから他のモジュールのリンクを解除する必要はありません。

1. [!UICONTROL HTTP] モジュールを使用してシナリオに切り替え、実行します。
1. Webhooks モジュールを使用してシナリオに戻ります。

   「[!UICONTROL 正常に決定されました]」というメッセージは、モジュールがデータ構造を正常に決定したことを意味します。

   ![&#x200B; 正常に決定されました &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/successfully-determined-350x175.png)

1. 「**[!UICONTROL OK]**」をクリックして、データ構造を保存します。

   これで、web フックの項目がマッピングパネルに表示され、シナリオの後続モジュールで使用できるようになりました。

## Webhook キュー

Web フックがデータを受け取り、そのデータを期待するアクティブなシナリオがない場合、データはキューに格納されます。シナリオをアクティベートすると、キューで待機しているすべてのバンドルが順番に処理されます。

>[!IMPORTANT]
>
>Web フックのキューは、同じ web フックを使用するシナリオ間で共有されます。いずれかのシナリオが無効な場合、すべての受信データはキューに保持されます。

## サポートされる受信データ形式

Workfront Fusion は、[!UICONTROL &#x200B; クエリ文字列 &#x200B;]、[!UICONTROL &#x200B; フォームデータ &#x200B;]、[!UICONTROL JSON] の 3 つの受信データ形式をサポートしています。

Workfront Fusion は、選択したデータ構造に対して、すべての受信データを検証します。 次に、シナリオの設定に応じて、データは処理用のキューに格納されるか、すぐに処理されます。

データの一部が検証に合格しない場合、Workfront Fusion は 400 HTTP ステータスコードを返し、受信データが検証チェックに失敗した理由を HTTP レスポンスの本文に指定します。 受信データの検証が成功した場合、Workfront Fusion は「[!UICONTROL 200 受理]」ステータスを返します。

* [[!UICONTROL クエリ文字列]](#query-string)
* [[!UICONTROL フォームデータ]](#form-data)
* [[!UICONTROL JSON]](#json)

### [!UICONTROL クエリ文字列]

```
GET https://app.workfrontfusion.com/wh/<yourunique32characterslongstring>?name=<yourname>&job=automate
```

### [!UICONTROL フォームデータ]

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
>1. 「**[!UICONTROL 追加]**」をクリックして、新しい web フックを追加します。
>1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
>1. 「**[!UICONTROL JSON パススルー]**」をクリックします。
>

## Web フックヘッダー

Web フックのヘッダーにアクセスするには、web フックの設定時に GET リクエストヘッダーを有効にします。

1. 「**[!UICONTROL 追加]**」をクリックして、新しい web フックを追加します。
1. 「**[!UICONTROL 詳細設定を表示]**」をクリックします。
1. 「**[!UICONTROL リクエストヘッダーを取得]**」をクリックします。

`map()` 関数と `get()` 関数を組み合わせて、特定のヘッダー値を抽出することができます。

>[!INFO]
>
>**例：**
>
>以下の例は、`Headers[]` 配列から `authorization` ヘッダーの値を抽出する式を示しています。この式は、抽出された値と指定されたテキストを比較し、一致する場合に web フックのみを渡すフィルターで使用されます。
>
>![&#x200B; フィルターの設定 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/set-up-a-filter-350x169.png)
>
>指定されたキーを使用して配列の要素を取得する方法については、「配列をマッピングする」の [&#x200B; 指定されたキーを使用して配列の要素をマッピングする &#x200B;](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md#map-an-arrays-element-with-a-given-key) を参照してください。

## Web フックへの応答

Web フック呼び出しに対するデフォルトの応答は、「受理」というテキストです。応答は、カスタム web フックモジュールの実行中に web フックを呼び出したアプリに返されます。

* [Web フックへの応答のテスト](#test-the-response-to-a-webhook)
* [HTML 応答の例](#html-response-example)
* [リダイレクトの例](#redirect-example)

### Web フックへの応答をテスト

1. **[!UICONTROL カスタム web フック]**&#x200B;モジュールを含めます。
1. モジュールに新しい web フックを追加します。
1. Web フックの URL をクリップボードにコピーします。
1. シナリオを実行します。

   [!UICONTROL カスタム web フック]モジュールの稲妻アイコンが回転する点に変わります。これは、モジュールが web フック呼び出しを待機していることを示しています。

1. 新しいブラウザーウィンドウを開き、コピーした URL をアドレスバーにペーストして、**[!UICONTROL Enter]** キーを押します。

   [!UICONTROL カスタム web フック]モジュールがトリガーされ、ブラウザーに新しいページが表示されます。

Web フックの応答をカスタマイズする場合は、web フックの応答モジュールを使用します。

モジュールの設定には、[!UICONTROL ステータス]および[!UICONTROL 本文]の 2 つのフィールドが含まれます。

* [!UICONTROL ステータス]フィールドには、成功の 2xx（OK の `200` など）、リダイレクトの 3xx（一時リダイレクトの `307` など）、4xx のクライアントエラー（例えば、無効なリクエストの `400`）などの HTTP 応答ステータスコードが含まれます。

* [!UICONTROL 本文]フィールドには、web フックの呼び出しで受け入れられるすべてが含まれます。シンプルなテキスト、HTML、XML、JSON などが含まれます。

  >[!TIP]
  >
  >`Content-Type` ヘッダーを対応する MIME タイプに設定することをお勧めします。プレーンテキストの場合は `text/plain`、HTMLの場合は `text/html`、JSON の場合は `application/json`、XML の場合は `application/xml` などです。MIME タイプについて詳しくは、[MIME モジュール](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/mime.md)を参照してください。

応答を送信するためのタイムアウトは 5 分です。 その期間内に応答が利用できない場合、Workfront Fusion は「200 受理」ステータスを返します。

### HTML 応答の例

>[!INFO]
>
>**例：**
>
>[!UICONTROL Web フック応答]モジュールを次のように設定します。
>
><table style="table-layout:auto"> 
>&gt; <col> 
>&gt; <col> 
>&gt; <tbody> 
>&gt;  <tr> 
>&gt;   <td role="rowheader">[!UICONTROL Status] </td> 
>&gt;   <td> <p>2xx 成功 HTTP ステータスコード（例：200）</p> </td> 
>&gt;  </tr> 
>&gt;  <tr> 
>&gt;   <td role="rowheader">[!UICONTROL Body] </td> 
>&gt;   <td> <p>HTML コード</p> </td> 
>&gt;  </tr> 
>&gt;  <tr> 
>&gt;   <td role="rowheader"> <p>[!UICONTROL Custom headers]</p> </td> 
>&gt;   <td> 
>&gt;    <ul> 
>&gt;     <li><strong>キー</strong>：Content-type</li> 
>&gt;     <li><strong>値</strong>：text/html</li> 
>&gt;    </ul> </td> 
>&gt;  </tr> 
>&gt; </tbody> 
>&gt;</table>
>
>![&#x200B; カスタムヘッダー &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/custom-headers-350x235.png)
>
>これにより、web ブラウザーに表示される HTML 応答が生成されます。
>
>![HEML 反応 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/html-response-350x70.png)

### リダイレクトの例

>[!INFO]
>
>**例：**&#x200B;[!UICONTROL web フック応答]モジュールを次のように設定します。
>
><table style="table-layout:auto"> 
>&gt; <col> 
>&gt; <col> 
>&gt; <tbody> 
>&gt;  <tr> 
>&gt;   <td role="rowheader">[!UICONTROL Status] </td> 
>&gt;   <td> <p>3xx リダイレクト HTTP ステータスコード（例：303）</p> </td> 
>&gt;  </tr> 
>&gt;  <tr> 
>&gt;   <td role="rowheader"> <p>[!UICONTROL Custom headers]</p> </td> 
>&gt;   <td> 
>&gt;    <ul> 
>&gt;     <li><strong>[!UICONTROL Key]</strong>：場所</li> 
>&gt;     <li><strong>[!UICONTROL Value]</strong>：リダイレクト先の URL。</li> 
>&gt;    </ul> </td> 
>&gt;  </tr> 
>&gt; </tbody> 
>&gt;</table>
>
>![Webhook 応答 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/webhook-response-350x279.png)

## Webhook の無効化

次のいずれかに該当する場合、Web フックは自動的に非アクティブ化されます。

* Web フックが 6 日以上どのシナリオにも接続されていない
* Web フックが、非アクティブなシナリオ（非アクティブになってから 30 日を超えたシナリオ）でのみ使用される。

非アクティブ化された web フックは、いかなるシナリオにも接続されておらず、非アクティブ状態となって 30 日が経過した場合、自動的に削除され、登録解除されます。


## トラブルシューティング

### マッピングパネルに項目がありません

[!UICONTROL Web フック]／[!UICONTROL カスタム web フック]モジュールに続くモジュールの設定でマッピングパネルに一部の項目が欠落している場合は、**[!UICONTROL Web フック]／[!UICONTROL カスタム web フック]**&#x200B;モジュールを選択して設定を開き、「**[!UICONTROL データ構造を再決定]**」をクリックします。

![&#x200B; データ構造の再定義 &#x200B;](/help/workfront-fusion/references/apps-and-modules/assets/redetermine-data-structure-btn-350x195.png)

次に、この記事の [web フックのデータ構造の設定](#configure-the-webhook-s-data-structure)の節で説明されている手順に従います。
