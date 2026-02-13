---
title: 大きいファイルの操作
description: 現在、Workfrontおよび HTTP コネクタでは大きなファイルがサポートされています。
author: Becky
feature: Workfront Fusion
exl-id: 6df81943-e70c-42b3-aa44-d82343598a51
source-git-commit: 2493ce7ccca599e30b44b62558573ce2a55b03e0
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 8%

---

# 大きいファイルの操作

>[!IMPORTANT]
>
>大容量ファイルを使用できるのは、Workfront Ultimate パッケージに含まれている組織のみです。

Workfront Fusion で強化されたデータ転送機能が使用できるようになり、シナリオで大幅に大きなファイルを処理できるようになりました。

大きなファイルを処理するには、シナリオを更新する必要があります。

## 大きなファイルをサポートするコネクタ

現在、次のコネクタは、大きなファイルをサポートしています。

>[!NOTE]
>
>* 大きなファイルをサポートするモジュールを使用してファイルをダウンロードし、大きなファイルをサポートしないモジュールに渡した場合、そのモジュールはファイルを正常に処理できません。大きなファイルは、ワークフロー全体でサポートされているモジュールでのみ処理する必要があります。
>* 大きなファイルをサポートしないモジュールは、最大 200 MB のサイズのファイルを処理できます。

* Workfront
   * ドキュメントのアップロード
   * ドキュメントのダウンロード
* Adobe Experience Manager Assets
   * ドキュメントをアップロード
* Workfront Proof
   * ファイルをアップロード
   * プルーフをダウンロード
* Adobe Authenticator
   * カスタム API 呼び出しの実行
* Adobe Photoshop
   * PSDの編集の適用
* SharePoint
   * ファイルを作成
   * ファイルの作成（レガシー）
   * ファイルの取得
* Salesforce
   * ファイルをアップロード
* AWS S3
   * ファイルをアップロード
   * ファイルを入手
* HTTP

その他のコネクタは、今後のリリースでサポートされる予定です。

## 大きなファイルを処理するためのシナリオの更新

Workfront/ドキュメントをアップロード モジュールが変更され、大きなファイルを処理できるようになりました。 このモジュールの以前のバージョンでは、モジュール名に `(Legacy)` が追加されて表示されるようになりました。 ほとんどの場合、レガシーモジュールは引き続き機能します。

大きなファイルを扱う予定がある場合は、従来のモジュールを新しいドキュメントをアップロード モジュールに置き換えることをお勧めします。 新しいドキュメントをアップロードモジュールは、タイムアウトやその他のエラーを防ぎます。

![ドキュメントをアップロード](assets/new-upload-document.png)

## よくある質問

### 新しいファイルサイズ制限は何ですか。

ユーザーは、以前の 1 GB の制限を超えるファイルを処理できるようになり、効率と生産性が向上します。  Workfront Fusion プラットフォームにはファイルサイズの上限が定義されていませんが、大きなファイルの使用に影響を与える可能性がある要因は他にもあります。

* **Fusion が接続するサービスのファイルサイズの制限**：サービスがファイルサイズを制限している場合、Workfront Fusion はその制限を克服しません。 ファイルサイズの制限は、最終的には Fusion が接続する web サービスによって異なります。

* **シナリオ実行時間**:Fusion は、40 分の実行制限に達するまで、任意のサイズのファイルを処理します。 大きなファイルの場合、Fusion シナリオでアップロード、ダウンロードまたは処理に時間がかかる場合があります。 サイズの大きいファイルが原因で、実行に 40 分以上かかる場合は、シナリオが失敗します。 シナリオの実行時間は、シナリオのサイズ、モジュールの複雑さ、ネットワーク速度の影響も受ける場合があります。 したがって、大きなファイルを使用する場合は、シナリオのこれらの側面を考慮することをお勧めします。

>[!NOTE]
>
>ベストプラクティスとして、ファイルサイズを 15 GB に制限することをお勧めします。

### Fusion の新しいファイル転送はどのように機能しますか？

Fusion がファイルを処理すると、大きなファイルが永続ストレージ（S3 バケットまたはAzure Blob ストレージ）に追加されます。 Fusion モジュールがアップロードやダウンロードなどのファイルアクションを実行すると、Fusion はアクティブメモリではなく、永続ストレージのファイルをソースとして使用します。

### 不完全な実行を使用してより大きなファイルを操作できますか？

はい。Fusion では、大きなファイルを含んだ不完全な実行をサポートしています。 不完全な実行は 1 つの組織でのサイズが制限されるので、積極的に管理する必要があります。

### 大きなファイルをコネクタで使用できますか？

大きなファイルをサポートするには、各 Fusion コネクタを更新する必要があります。 サポートされているコネクタには、Workfront、HTTP およびAEM Assetsがあります。 Fusion コネクタは、web サービスでサポートされているファイルサイズによって、引き続き制限されます。 ファイルサイズの制限は、通常、ファイルをダウンロードおよびアップロードする web サービスエンドポイントに関する API ドキュメントに含まれています。

### これは業務に影響を与えますか？

いいえ。モジュールが実行する操作の数は同じです。

### Fusion の UI がファイル転送データを表示するように更新されるのはいつですか？

この機能は既に完了しており、実稼動環境にデプロイされています。

### シナリオの設計に役立つ新しいファイル処理制限について考える方法を教えてください。

実行の上限である 40 分以内に動作するようにシナリオを設計するのは複雑に思えるかもしれません。 シナリオを設計する際は、次の点に留意することをお勧めします。

* **実行時間のビジネス要件を理解する**:Fusion の実行時間のプラットフォーム制限は 40 分ですが、ほとんどのビジネスプロセスの自動化は、はるかに高速に実行されると予想されています。 例えば、ユーザーが開始し、結果に応じて継続する自動化は、40 分の制限内で十分に完了すると予想されます。
* **設計時の実行時間を考慮**：シナリオを設計する際は、アップロードやダウンロードなど、個々のファイルアクションのモジュール実行時間を理解することが重要です。 この知識は、複数のファイルアクションを含むシナリオを計画するのに役立ちます。  設計の正確性を確保するために、モジュールの実行時間をバッファを含むように切り上げることをお勧めします。
例えば、Fusion が 144 秒（2.4 分）でドキュメントをダウンロードする場合、1 回の実行で同様のアクションを複数回実行できると予測できます。 この例では、モジュールの実行には 144 秒かかるので、ダウンロードには 3 分間の実行時間を計画する必要があります。 要件にアップロードとダウンロードの両方が含まれる場合、予想実行時間は約 6 分です。 Fusion の実行時間は 40 分に制限されています。

* **ファイルアクションの統合**:Fusion シナリオにおけるファイルアクションの最も一般的な例は、ダウンロードとアップロードの 1 つです。 これら 2 つのアクションのみのシナリオのほとんどは、数分で実行されます。 可能であれば、Fusion デザイナーはシナリオを 1 回のダウンロードと 1 回のアップロードに制限する必要があります。

* **マッピングパネルを使用したサイズの計算**:Workfrontやその他の web サービスでは、ダウンロードモジュールの出力にファイルのファイルサイズが含まれます。 このデータを使用して、モジュールのアップロードには大きすぎるファイルや、シナリオの実行時間には大きすぎるファイルを除外できます。

* **複数のファイルを操作する際に、ファイル操作を独自のシナリオで分離する**:Fusion デザイナーは、ファイル操作を個別のシナリオに分離することを検討する必要があります。 例えば、複数のファイルが添付された新しいWorkfront リクエストでトリガーされた Fusion シナリオでは、最大 30 個のファイルを格納する必要がある場合があります。 各ファイルのアップロードとダウンロードに最大 3 分かかる場合があるので、1 回の実行ですべてのファイルを処理すると、Fusion の 40 分の実行制限を超えます。 解決策は、個々のファイルのアップロードおよびダウンロードを処理する専用のファイルアクションシナリオを作成することです。 リクエストトリガーのシナリオは、添付ファイルを繰り返し処理し、HTTP モジュールを使用して各ファイルのファイルアクションシナリオを呼び出します。 このアプローチにより、各ファイルが実行時間制限内で確実に処理されます。

<!--
## Connectors that do not support large files

Some Fusion connectors do not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.

The following connectors do **not** support large files. 

* Archive
* Box
* Convert
* CSV
* Datastores
* Flow control
* FTP
* JSON
* JWT
* Markdown
* Math
* Microsoft Word templates
* MIME
* Microsoft SQL
* SFTP
* Adobe Acrobat Sign
* SOAP
* Tools
* XML

If a connector is not on this list, it does not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.-->






<!--## Connectors that support large files

The following connectors support large files.

Workfront
HTTP
Webhooks
Salesforce
Microsoft Email
Workfront Proof
AEM Assets
Email
Slack
Jira
Microsoft Excel
SharePoint
Frame.io
Adobe PDF Services
Marketo
Azure Devops 
Google Email
Jira Server
Google Sheets
Microsoft OneDrive
ServiceNow 
AWS S3
Bynder
OneDrive Business
Adobe Authenticator
Google Drive
Microsoft Dynamics
Google Docs
NetSuite
Airtable
Azure AD
QuickBase 
Adobe Target
Adobe Campaign Classic
Microsoft Calendar
Workfront Planning
HubSpot CRM  
DropBox
Cloud Convert
Egnyte
Adobe Firefly
OpenAI / Chat GPT
Allocadia
Cvent
GitLab 
Google Team Drive
Google Calendar
Workfront SDL Managed Translation
Widen
Workfront Boards
Google Slides
Qualtrics
Microsoft Power BI
Adobe Photoshop
Anaplan
DocuSign 
MariaDB
Adobe Creative Cloud Libraries
Figma
AEM Forms
Datadog
GitHub 
Google Forms
Adobe I/O Events
Trello
Workday
Adobe Journey Optimizer
Adobe Lightroom


If a file is not on this list, it does not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.

-->
