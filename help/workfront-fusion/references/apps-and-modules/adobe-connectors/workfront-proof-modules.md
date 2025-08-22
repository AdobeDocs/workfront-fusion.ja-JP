---
title: Workfront Proof モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL Workfront Proof] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
feature: Workfront Fusion, Workfront Proof, Digital Content and Documents
exl-id: 9e556ae5-e672-4872-9c40-8c8e5f0305be
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '3131'
ht-degree: 80%

---

# [!DNL Workfront Proof] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL Workfront Proof] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

これは、Workfront内または [!DNL Workfront Proof] 内のプルーフで現在サポートされていないタスクを実行する必要がある場合に便利です。例えば、特定のイベントに基づいてプルーフを更新したり、プルーフの受信者を検索したりする場合です。

[!DNL Workfront Proof] コネクタは、組織で使用可能なアクティブなアプリの数に対してカウントされません。すべてのシナリオは、[!DNL Workfront Proof] アプリのみを使用する場合でも、組織の合計シナリオ数にカウントされます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Workfront Proof情報

Workfront Proof コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v21.3.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.8.92</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Workfront Proof] を Workfront Fusion に接続

Workfront Fusion モジュール内から [!DNL Workfront Proof] アカウントへの直接接続を作成できます。

1. 任意のWorkfront Fusion モジュールで、「[!UICONTROL **接続**] フィールドの横にある「[!UICONTROL  追加 ] をクリックします

2. 次のフィールドに入力します。

   <table style="table-layout:auto"> 
        <col/>
        <col/>
        <tbody>
            <tr>
                <td role="rowheader">
                    <p role="rowheader">[!UICONTROL Connection name]</p>
                </td>
                <td>接続に名前を入力します。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Environment]</td>
                <td>これが実稼動環境であるか、プレビューやサンドボックスなどの非実稼動環境であるかを選択します。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Type]</td>
                <td>これがサービスアカウントであるか、個人アカウントであるかを選択します。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Email / Username]</td>
                <td>[!DNL Workfront Proof] アカウントのユーザー名を入力します。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Password]</td>
                <td>[!DNL Workfront Proof] アカウントのパスワードを入力します。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL テナント ID]</td>
                <td><strong>メモ</strong>：BYOK を使用しないお客様は、このフィールドを空白のままにしておく必要があります。 <p>このアカウントのテナント ID を入力します。テナント ID の検索について不明な点がある場合は、Workfront カスタマーサポートにお問い合わせください。</p></td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Domain Extension]</td>
                <td>自分のアカウントへのアクセスに使用する URL の拡張子を入力します。 <p>例：<code>com</code> または <code>eu</code></p></td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Production, Preview, or Custom Environment]</td>
                <td>接続する実稼動、プレビューまたはカスタム環境。</td>
            </tr>
        </tbody>
    </table>


3. 「[!UICONTROL **続行**]」をクリックして接続を保存し、モジュールに戻ります。

## [!DNL Workfront Proof] モジュールとそのフィールド

[!DNL Workfront Proof] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL Workfront Proof]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)
* [検索](#searches)

### トリガー

* [PDF 概要の監視](#watch-for-pdf-summary)
* [[!UICONTROL プルーフアクティビティの監視]](#watch-proof-activity)
* [プルーフの監視](#watch-proofs)

#### [!UICONTROL PDF 概要の監視]

このインスタントトリガーモジュールは、誰かがプルーフの PDF 概要を作成する際にシナリオを実行します。

このモジュールには web フックが必要です。

このモジュールは、プルーフに関連付けられたすべての標準フィールドおよび接続がアクセスするカスタムフィールドおよび値を返します。また、PDF の概要に関する新しいイベント登録を作成し、ペイロードで送信される `pdf_url` 属性からコンテンツを出力します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Webhook name]</td> 
   <td>新しい Webhook の名前を入力またはマッピングします</td> 
  </tr> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プルーフアクティビティの監視]

このトリガーモジュールは、プルーフで指定されたアクティビティが発生した場合にシナリオを実行します。

このモジュールは、プルーフに関連付けられたすべての標準フィールドおよび接続がアクセスするカスタムフィールドおよび値を返します。また、PDF の概要に関する新しいイベント登録を作成し、ペイロードで送信される `pdf_url` 属性からコンテンツを出力します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Activity type]</td> 
   <td>新しい決定（プルーフステータスの変更を含む）を監視するか、全体的なプルーフステータスの変更のみを監視するかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL プルーフの監視]

このスケジュール済みトリガーモジュールは、誰かがプルーフを作成またはプルーフでの決定する際にシナリオを実行します。

このモジュールは、指定した期間に見つかったすべてのレコードのリストと、そのレコードのタイプを返します。また、指定したフィールドの値も返します。モジュールでプルーフに関する決定が見つかった場合は、以前の値と現在の値の両方が個別のフィールドに含まれます。この情報は、シナリオ内の後続のモジュールにマッピングできます。

この処理は、指定した間隔で定期的に実行されます。

この情報を取得するには、[!DNL Workfront Proof] でプルーフにアクセスまたはプルーフするのに十分な権限が必要です。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">レコードタイプ</td> 
   <td>新しいプルーフを監視するか、プルーフ全体の新しい決定を監視するかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">制限</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">1 ページあたりの項目数</td> 
   <td> <p>結果にページ番号を付けるには、結果の各ページに表示する結果の数を入力するかマップします。 この数は 100 以下にする必要があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL プルーフの作成]](#create-proof)
* [[!UICONTROL カスタム API 呼び出し]](#custom-api-call)
* [[!UICONTROL プルーフのダウンロード]](#download-proof)
* [[!UICONTROL レコードの読み取り]](#read-a-record)
* [[!UICONTROL PDF 概要のリクエスト]](#request-pdf-summary)
* [[!UICONTROL プルーフの更新]](#update-proof)
* [[!UICONTROL ファイルをアップロード]](#upload-file)

#### [!UICONTROL プルーフの作成]

<!--Cannot test Jan 2025-->

このアクションモジュールは、[!DNL Workfront Proof] で新規プルーフまたは新しいバージョンのプルーフを作成します。

新しいバージョンを作成する場合は、新しいプルーフのパラメーターと、ソースプルーフのパラメーターを指定します。

モジュールは、新しいプルーフまたはプルーフバージョンの ID を返します。 この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof Type]</td> 
   <td> <p>作成するプルーフに対して、基本ワークフローまたは [!UICONTROL Automated Workflow] のどちらを使用するかを指定します。</p> <p>次に、選択したプルーフタイプに対して表示するフィールドに入力します。例えば、[!UICONTROL Automated Workflow] を選択した場合、<strong>[!UICONTROL Workflow Stages]</strong> フィールドを使用してステージを設定します。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Allow original file to be downloaded]</td> 
   <td>プルーフの作成元となった元のファイルのダウンロードを許可するかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Classic Proof Viewer]</td> 
   <td>クラシックプルーフビューアーを使用するかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Combine all files into single proof]</td> 
   <td>すべてのファイルを 1 つの複数ページのプルーフに組み合わせるには、このオプションを有効にします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create a new proof version]</td> 
   <td>モジュールで既存のプルーフの新しいバージョンを作成する場合は、このオプションを選択します。次に、表示される <strong>[!UICONTROL Existing Proof ID]</strong> フィールドに、プルーフの一意の ID をマッピングまたは入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Custom Link Label]</td> 
   <td>カスタムプルーフリンクのラベルを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Custom Link URL]</td> 
   <td>カスタムリンクの URL を入力またはマッピングします。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Default email notifications for subscribers]</td> 
   <td>次のいずれかの数値を入力して、作成されるプルーフに使用する次のデフォルトのメール通知設定を指定します。
    <ul>
     <li><strong>1</strong> - すべての新しいコメントと返信</li>
     <li><strong>2</strong> - 自分のコメントへの返信</li>
     <li><strong>3</strong> - 毎日の概要</li>
     <li><strong>4</strong> - 毎時の概要</li>
     <li><strong>5</strong> - 決定のみ</li>
     <li><strong>9</strong> - 無効</li>
    </ul></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Disable Excel Summary]</td> 
   <td>プルーフのコメントを Excel ファイルにダウンロードする機能を無効にするかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Disable PDF Summary]</td> 
   <td>プルーフのコメントを PDF ファイルにダウンロードする機能を無効にするかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Disable Subscription Email]</td> 
   <td>このプルーフの登録メールを無効にするかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Enable Embed Player]</td> 
   <td>このプルーフに埋め込まれたプレーヤーを有効にするかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Enable Subscriptions]</td> 
   <td>参加者以外に対して、プルーフへの登録を許可するかどうかを選択します。<br>このオプションを選択すると、この表で説明するように、サブスクライバーのデフォルトの役割も選択できます。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Enable Subscriptions Validation]</td> 
   <td>登録メールの検証を有効にするかどうかを選択します。このオプションが有効な場合、サブスクライバーはプルーフにアクセスするために、メール内のリンクをクリックする必要があります。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Enable Team URL]</td> 
   <td>作成したプルーフでチーム URL を表示するか非表示にするかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL File Hash] <span style="font-weight: normal;">または</span> [!UICONTROL File Hashes]</td> 
   <td>プルーフまたは複数のプルーフの作成元となるファイルまたは複数のファイルの ID を追加します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL File Names]</td> 
   <td>作成されるプルーフのファイル名または名前を追加します。これは必須フィールドです。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Lock proof when all required decisions are made]</td> 
   <td>作成されるプルーフを必要なすべての決定が行われた後にロックするかどうかを指定します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Notify recipients about this proof]</td> 
   <td>プルーフの作成時に受信者に通知するかどうかを指定するオプションを選択します。&gt;</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof name]</td> 
   <td>作成されるプルーフの名前を入力します。これは必須フィールドです。複数のプルーフの名前を区切るには、パイプ記号（|）を使用します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof owner ID]</td> 
   <td>プルーフの所有者の ID を入力またはマッピングします。このフィールドを空白のままにすると、プルーフの所有者は現在のユーザーに設定されます。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Reference ID]</td> 
   <td>プルーフの参照 ID を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Require electronic signature]</td> 
   <td>電子サインの送信を、プルーフに関する決定を行ったユーザーに対して要求するかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Require login]</td> 
   <td> <p>作成されるプルーフにログインを必要とするかどうかを指定します。 </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Resolution ID]</td> 
   <td>プルーフに使用する解決策の ID を入力します。解決策の ID のリストについて詳しくは、[!DNL Workfront Proof] <a href="https://api.proofhq.com/home/objects/soapworkflowproofobject.html">API ドキュメント</a>を参照してください。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL SWF]</td> 
   <td>SWF プルーフのタイプを入力します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Show] [item]</td> 
   <td>各項目について、プルーフに表示するかどうかを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Workspace ID]</td> 
   <td>プルーフを作成するワークスペースの ID を入力します。 </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Recipients]</td> 
   <td>作成するプルーフに必要な受信者のメールアドレスを追加します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Deadline]</td> 
   <td> <p>プルーフを作成する期限を指定します。次の日付形式を使用します。</p> <p><code>YYYY-MM-DD hh:mm</code></p> </td> 
  </tr> 
 </tbody> 
</table>



#### [!UICONTROL カスタム API 呼び出し]

このアクションモジュールは、[!DNL Workfront Proof] API に対して認証済みのカスタム呼び出しを実行します。これにより、他の [!DNL Workfront Proof] モジュールでは達成できないデータフローの自動化を作成できます。

このモジュールは、ステータスコード、ヘッダーおよび本文を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Method]</td> 
   <td>API 呼び出しのアクションを設定します。使用可能なアクションについて詳しくは、<a href="https://api.proofhq.com/">プルーフ API ドキュメント</a>を参照してください。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Body (XML)]</td> 
   <td> <p>標準の JSON オブジェクトの形式で、API 呼び出しの本文の内容を追加します。</p> <p>メモ：  <p><code>if</code> などの条件ステートメントを JSON で使用する場合、条件ステートメントの外側に引用符を挿入します。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**例：**
>
>![Proof API モジュールの例 ](/help/workfront-fusion/references/apps-and-modules/assets/wfp-api-module-example-350x586.png)

#### [!UICONTROL プルーフのダウンロード]

このアクションモジュールは、ID を使用して識別する特定のプルーフのソースファイルをダウンロードします。

プルーフの ID を指定します。

このモジュールは、プルーフの作成に使用するソースファイルのコンテンツを返します。この情報は、シナリオの後続のモジュールでマッピングできます。

この情報を取得するには、[!DNL Workfront Proof] のレコードにアクセスするのに十分な権限が必要です。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof ID]</td> 
   <td> <p>[!UICONTROL プルーフの詳細 ] ページにあるプルーフの一意の ID を入力します。  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL レコードの読み込み]

このアクションモジュールは、[!DNL Workfront Proof] の単一のプルーフからデータを読み込みます。

プルーフの ID およびプルーフに必要な情報を指定します。

このモジュールは、プルーフ用に選択したフィールドの値およびそのタイプを返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

この情報を取得するには、[!DNL Workfront Proof] のレコードにアクセスするのに十分な権限が必要です。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td>プルーフ、プルーフのコメントまたはプルーフのレビュアーを読み込むかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ID]</td> 
   <td>モジュールで読み取るレコードの一意の [!DNL Workfront Proof] ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL PDF 概要をリクエスト]

このアクションモジュールは、[!DNL Workfront Proof] の特定のプルーフの PDF 概要をリクエストします。

プルーフの ID を指定します。

モジュールは、PDF 概要の情報を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

この情報を取得するには、[!DNL Workfront Proof] のレコードにアクセスするのに十分な権限が必要です。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof ID]</td> 
   <td> <p>PDF 概要をリクエストするプルーフの一意の [!DNL Workfront Proof] ID を入力します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Callback URL]</td> 
   <td>PDF 概要を送信する URL を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

##### 考えられるエラー

* **エラー**：「[!UICONTROL このリクエストを実行する権限がありません。ステージには少なくとも 1 人の受信者が含まれている必要があります]」
* **解決策**：ワークフローのステージに自分だけしか割り当てられていないことを確認します。ワークフローのステージに別のユーザーを割り当てる必要があります。

#### [!UICONTROL プルーフを更新]

このアクションモジュールは、[!DNL Workfront Proof] で既存のプルーフを更新します。

プルーフの ID とレコードタイプおよび出力に含めるフィールドを指定します。

このモジュールは、レコードに関連付けられた標準フィールドのほか、接続を介してアクセスされるカスタムフィールドおよび値を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

この情報を取得するには、[!DNL Workfront Proof] のレコードにアクセスするのに十分な権限が必要です。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof ID]</td> 
   <td> <p>[!UICONTROL プルーフの詳細 ] ページにあるプルーフの一意の ID を入力します。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Deadline]</td> 
   <td> <p>プルーフを作成する期限を指定します。日付形式 <code>YYYY-MM-DD hh:mm</code> を使用します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Default email notifications for subscribers]</td> 
   <td>作成されるプルーフで使用する、次のデフォルトのメール通知設定の中からいずれかを選択します。
    <ul>
     <li> [!UICONTROL All new comments and replies]</li>
     <li>[!UICONTROL Replies to my comments]</li>
     <li>[!UICONTROL Daily summary]</li>
     <li> [!UICONTROL Hourly summary]</li>
     <li> [!UICONTROL Decisions only]</li>
     <li> [!UICONTROL Disabled]</li>
    </ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Default Role]</td> 
   <td>プルーフのデフォルトの役割を選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Disable Subscription Email]</td> 
   <td>このプルーフの登録メールを無効にするかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Enable Subscriptions]</td> 
   <td>参加者以外に対して、プルーフへの登録を許可するかどうかを選択します。<br> このオプションを選択すると、[!UICONTROL のデフォルトの役割 ] フィールドでオプションを選択することもできます。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Enable Subscriptions Validation]</td> 
   <td>登録メールの検証を有効にするかどうかを選択します。このオプションが有効な場合、サブスクライバーはプルーフにアクセスするために、メール内のリンクをクリックする必要があります。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Enable Team URL]</td> 
   <td>作成したプルーフでチーム URL を表示するか非表示にするかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Lock proof when all required decisions are made]</td> 
   <td>作成されるプルーフを必要なすべての決定が行われた後にロックするかどうかを指定します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Message]</td> 
   <td>プルーフに伴うメッセージを入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof ID] </td> 
   <td>更新するプルーフの ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Proof Name]</td> 
   <td>更新するプルーフの名前を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Require login]</td> 
   <td> <p>作成されるプルーフにログインを必要とするかどうかを指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show Versions Like]</td> 
   <td>このプルーフの他のバージョンへのリンクを表示するかどうかを選択します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject]</td> 
   <td>プルーフの件名を入力またはマッピング</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをアップロード]

このアクションモジュールは [!DNL Workfront Proof] の[!UICONTROL プルーフを作成]モジュールで使用するファイルをアップロードします。

このモジュールは、アップロードされたファイルのハッシュ ID を返します。この情報は、シナリオ内の後続のモジュールにマッピングできます。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 検索

* [[!UICONTROL ワークフローテンプレートをリスト]](#list-workflow-templates)
* [[!UICONTROL 検索]](#search)

#### [!UICONTROL ワークフローテンプレートをリスト]

この検索モジュールは、使用可能なすべてのワークフローテンプレートを一覧表示します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントを Workfront Fusion に接続する手順について詳しくは、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion への接続の作成 - 基本手順</a>を参照してください</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>このモジュールの出力バンドルに含める情報を選択します。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すテンプレートの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 検索]

この検索モジュールは、指定された検索クエリに一致するレコードを [!DNL Workfront Proof] のオブジェクト内で検索します。

このモジュールは、プルーフを検索する場合に、プルーフの ID を返します。また、受信者を検索する場合は、受信者のユーザー ID、メール、名前、位置およびメールエイリアスを返します。この情報は、シナリオの後続のモジュールでマッピングできます。

この情報を取得するには、[!DNL Workfront Proof] のレコードにアクセスするのに十分な権限が必要です。

このモジュールを設定する際には、次のフィールドが表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!DNL Connection]</td> 
   <td> <p>[!DNL Workfront Proof] アカウントをAdobe Workfront Fusion に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Workfront Fusion への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 検索 ]</td> 
   <td> <p>モジュールで検索するレコードのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Proof]</strong> </p> <p>検索するプルーフのプルーフ名を入力します。</p> </li> 
     <li> <p><strong>[!UICONTROL Recipient]</strong> </p> <p>検索する受信者のメールアドレスを入力します。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Result Set]</td> 
   <td>モジュールが <strong>[!UICONTROL All Matching Records]</strong> を検索または <strong>[!UICONTROL First Matching Record]</strong> のみを検索するかどうかを示します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Sort By]</td> 
   <td>結果の並べ替えに使用するフィールドを選択します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Sorting Direction]</td> 
   <td> <p>結果を昇順または降順に並べ替えるかどうかを選択します。</p> </td> 
  </tr> 
 </tbody> 
</table>

