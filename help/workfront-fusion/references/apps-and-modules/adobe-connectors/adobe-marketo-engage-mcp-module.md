---
title: Adobe Marketo Engage MCP モジュール
description: Adobe Marketo Engage MCP モジュールを使用すると、Adobe Marketo EngageのMCP （Model Context Protocol）サーバーに自然言語プロンプトを送信できます。
author: Becky
feature: Workfront Fusion
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
    internal-label: APIs
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
  - id: e14a7f57-c82c-4874-a495-5d036cbbdc3d
    internal-label: Resource management
subfeature_v2:
  - id: b70a979b-965d-47a9-a360-e7ec2a19b8c1
    internal-label: Digital content and documents
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 9e08c421a53c7ca499715fa8e32be6c10fbde1d9
workflow-type: tm+mt
source-wordcount: '1579'
ht-degree: 10%
---
# Adobe Marketo Engage MCP モジュール

Adobe Marketo Engage MCP モジュールを使用すると、AI モデルを使用してAdobe Marketo EngageのMCP （Model Context Protocol）サーバーに自然言語プロンプトを送信し、リクエストを解釈してMarketo独自のツールを呼び出して処理できます。 各モジュールが「リードを作成」などの1つの固定アクションを行う従来のMarketo コネクタとは異なり、このコネクタには、オープンエンドの命令を平易な英語で受け付け、AIがそれを満たすために必要なMarketoの操作を決定できる1つのモジュールがあります。

このコネクタは、Marketo Engage独自のMCP サーバー専用です

他のアプリケーションのMCPに接続するには、[AI プロンプトをシナリオに追加する](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md)を参照してください。

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
   <p>オペレーションベース：オペレーションベースのライセンスを持つ組織で使用できます</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

* Adobe Marketo Engage アカウントと有効なMarketo インスタンスが必要です。

## Adobe Marketo Engage MCPとWorkfront Fusionの連携 {#connect-adobe-marketo-engage-mcp-to-workfront-fusion}

Adobe Marketo Engage MCP モジュール内から直接Marketo インスタンスへの接続を作成できます。

1. Adobe Marketo Engage MCP モジュールで、**Connection** フィールドの横にある&#x200B;**Add**&#x200B;をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>新しい接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>
          <p>Marketo LaunchPointで作成したMarketo REST API サービスのクライアント IDを入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>
          <p>Marketo LaunchPointで作成したMarketo REST API サービスのクライアントシークレットを入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Munchkin ID]</td>
        <td>
          <p>Marketo インスタンスのMunchkin ID （「123-ABC-456」など）を入力します。 Munchkin IDは、<b>管理者→Munchkin</b>の下のMarketoに表示されます。</p>
        </td>
      </tr>
    </tbody>
   </table>

1. 「**続行**」をクリックして接続を作成し、モジュールに戻ります。

>[!IMPORTANT]
>
> * 管理者アカウントを再利用するのではなく、シナリオに必要な最小限の役割と権限を持つ専用のAPI専用のMarketo ユーザーを使用します。
> * 接続を作成しても、資格情報が検証されません。 Fusionはテスト呼び出しなしで保存するため、値が間違っていたり、誤って入力されたりしても、接続が正常に作成されたように見えます。 資格情報が正しくない場合は、通常、モジュールが最初にMarketoに到達しようとしたときや、ツールリストの読み込みが失敗したときに、後でエラーが表示されます。

## モジュール：「ユーザープロンプトの処理」

これは、コネクタが提供する唯一のモジュールです。 シナリオでは、次の項目を指定して使用します。

1. **Connection** – 上記で作成されたMarketo接続。
2. **プロンプト**&#x200B;を入力します。この指示は、わかりやすい英語で入力します（例：「先週のSpring Webinar リストに追加されたすべてのリードを検索し、会社名が設定されていないリードを教えてください」）。
3. **ツール** （オプション） – 以下で説明します。 これらのフィールドは、接続が選択された場合にのみ表示されます。
4. **LLM キー** （オプション、詳細） – 以下で説明します。

AIの最終的な回答をテキストとして返し、その回答を生成している間に何が起こったのかを詳細に把握できます。

## Adobe Marketo Engage MCP モジュールとそのフィールド

### ユーザープロンプトの処理

このアクションモジュールは、Adobe Marketo EngageのMCP サーバーに平易な英語の命令を送信し、AIの応答を返します。

<table style="table-layout:auto"> 
 <col/>
 <col/>
 <tbody>
  <tr>
   <td role="rowheader">LLM キー<i> （オプション、詳細） </i></td>
   <td><p>デフォルトでは、このモジュールはAdobe独自のAI サービスを使用してプロンプトを処理します。キーを選択する必要はありません。</p><p>代わりに独自のAI プロバイダーを使用するには、既存のLLM キーを選択するか、<b>追加</b>をクリックして次の情報を入力して新しいLLM キーを作成します。</p>
    <ul>
     <li><b> キー名</b>：新しいキーの名前を入力します。</li>
     <li><b>LLM</b>：このキーが関連付けられている大規模言語モデルを選択します。 サポートされているプロバイダーは、OpenAI、Anthropic Claude、Amazon Bedrockです。</li>
     <li><b> キー</b>：選択したプロバイダーのAPI キーを入力するか、マッピングします。</li>
     <li><b> モデル </b>: キーで使用するLLM モデルを選択します。</li>
     <li><b>その他のフィールド </b>: LLMに必要なその他のフィールドの値を入力します。</li>
    </ul>
   </td>
  </tr>
  <tr>
   <td role="rowheader">接続</td>
   <td><p>Marketo アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-adobe-marketo-engage-mcp-to-workfront-fusion" class="MCXref xref">Adobe Marketo Engage MCPをWorkfront Fusionに接続する</a>」を参照してください。</p></td>
  </tr>
  <tr>
   <td role="rowheader">ユーザープロンプト</td>
   <td><p>AIに実行させたい命令を分かりやすい英語で入力するか、マッピングします。</p><p>例：<i>過去7日間にSpring Webinar リストに追加されたすべてのリードを検索し、最も一般的な業界を要約します。</i></p></td>
  </tr>
 </tbody>
</table>

### モジュール出力

出力は、次の内容を含む単一のバンドルです。

* 回答：AIの最終的な答えをテキストとして返します。 このデータを後続のモジュールにマッピングできます。
* 監査証跡：セッション ID、元のプロンプト、開始時間と終了時間、合計時間、全体的なステータス、最終応答、ツール呼び出しリストなど、実行の詳細レコード。 各ツール呼び出しエントリは、実行したMarketo ツール、その引数、出力、開始時間と終了時間、期間、成功したかどうか、シーケンス内の順序を記録します。
* 概要：同じ実行がカウントに凝縮されています：合計ツール呼び出し、成功した呼び出し、失敗した呼び出し、処理時間、およびステータス。

### AI モデル

デフォルトでは、モジュールはキーや資格情報を入力することなく、Adobe独自のマネージド AI サービスを自動的に使用します。

代わりに、OpenAI、Anthropic Claude、またはAmazon Bedrockのいずれかを使用する特定のLLM キーを選択できます（組織がアカウントを持っている場合）。

### AIが実行できるMarketoのアクションを選ぶ

接続を選択すると、モジュールはMarketo MCP サーバーに対して、提供するツールを尋ね、複数選択リストとして表示します。各リストには、次のツールが含まれています。

* 読み取り専用ツール：リードの検索、キャンペーンメンバーのリストアップ、プログラムの詳細の読み取りなど、何も変更せず、特定の項目のみを参照するアクション。
* ツールの書き込み/削除：リードの作成や更新、リストへの追加、キャンペーンのアクティブ化、メールの承認や送信など、何かを変更するアクション。
* その他のツール：Marketo サーバーが読み取り専用としてラベル付けされていないツールを提供する場合にのみ表示される3番目のリスト。 これらは、安全または安全でないと見なされるのではなく、個別に表示されます。 サーバーがすべてをラベル付けすると、このリストは表示されません。

ツールが選択されていない場合、AIはそれらすべてを使用できます。 リストは、特定のアクションに制限できます。 例えば、「読み取り専用」のままにして2つの特定の「書き込み」アクションのみを選択すると、AIは必要な内容を自由に検索できますが、その2つの特定の種類の変更のみを行うことができます。 リストを空のままにすると、そのカテゴリ内のすべてのアクションが許可されます。 AIを制限するには、そのカテゴリーで許可する特定のアクションを積極的に選択する必要があります。 これにより、AIが自由に情報を収集しながら、ライブマーケティングデータに対して予期せぬ破壊的なアクションを起こさないようにすることができます。

リストはMarketo サーバーからライブで読み取られるため、Adobeがそのサーバーを更新すると、表示されるツールが正確に変化する可能性があります。

### 永続的な会話履歴はありません

このモジュールの各実行は、1つの自己完結実行です。 AIはフォローアップの質問をして返信を待つことはできません。 その代わりに、最善の判断を下し、1回のパスで完全で最終的な答えを生成する必要があります。 リクエストが曖昧な場合、AIは合理的な仮定を行い、その仮定を回答の一部として述べ、続行します。 1回の実行で返信を受け取る方法がないので、ユーザーに確認を求めたりしません。

また、以前の実行時からMarketoのデータが変更された可能性があるため、AIはメモリに依存するのではなくツールコールでファクトを検証するように指示されます。

AIは、プロンプトが実際に要求した場合にのみ、書き込み、更新、削除アクションを実行します。 キャンペーンのアクティベートや非アクティベート、リードとリストの作成と削除、メールの承認や送信など、要求されなかったアクションを、ユーザーが要求した他の作業を実行している場合でも実行しません。

それぞれの実行は独立しているため、AIには以前の実行のメモリがありません。 マルチターンでチャットのようなエクスペリエンスを望むシナリオでは、Fusionのデータストアに以前の質問と回答を保存したり、モジュール間で渡したり、新しいプロンプトの最初にテキストとして含めたり、新しい質問を続けたりするなど、新しいプロンプトの一部として、その履歴を明示的に提供する必要があります。 以前の実行を自動的に記憶するセッション IDや会話IDはありません。

## サンプルプロンプト

次のようなプロンプトを使用できます。

* *過去7日間に「第3四半期製品発売」プログラムに参加したリードをリストアップし、そのリードが属する業界を要約します。*
* *「ウェルカムシリーズ」スマートキャンペーンが現在有効かどうかを確認し、そのキャンペーンに何人のユーザーがいるか教えてください。*
* *価格ページで使用されているフォームを検索し、必須とマークされているフィールドを教えてください。*
* *電子メール `jane@example.com`のリードを「VIPのお客様」の静的リストに追加します。*
* *春のニュースレターのプログラムで、すべての電子メールのパフォーマンスを要約します。*

<!--

## What a content writer should NOT claim

* Connection form: Do not describe the connection as an OAuth or "sign in with Adobe" flow. It is not one. It is three credential fields that the user copies out of Marketo's LaunchPoint and Munchkin admin pages. Screenshots or steps borrowed from the AEM MCP connector docs would be wrong here.
* Credential validation: Do not imply that the connection form validates the credentials. It saves them without testing them.
* Module scope: This is not a substitute for individual Marketo action modules. It is a single, flexible AI-driven module, not a set of deterministic single-purpose modules.
* Reliability: Results are AI-generated and can occasionally be imperfect, even with every safeguard above in place. This is appropriate for automation where a human is not reviewing every single run in real time, but it is not a guarantee of 100% deterministic behavior the way a traditional Marketo module is. This deserves extra emphasis for Marketo specifically, because a write action here can email real customers or alter real lead records.
* Tool restrictions: The read/write tool split limits what categories of Marketo actions the AI can take. It is not a way to sandbox or limit what the AI is capable of reasoning about or discussing in its answer text.
* Tool naming: Do not name specific Marketo MCP tools or actions unless they are verified against the live tool list. This document intentionally describes capability areas, such as leads, lists, campaigns, programs, emails, forms, snippets, and bulk operations, rather than exact tool names, since the server's exact tool set may evolve.
* API limits: Do not state Marketo API rate limits, quotas, or daily call caps as if this connector defines them. Any such limit comes from the user's own Marketo subscription and REST API allowance; verify with the Marketo team before publishing numbers.

## Reference links used while compiling this

* Adobe Marketo Engage MCP server (developer documentation):
  https://experienceleague.adobe.com/ja/docs/marketo-developer/marketo/mcp-server

  -->
