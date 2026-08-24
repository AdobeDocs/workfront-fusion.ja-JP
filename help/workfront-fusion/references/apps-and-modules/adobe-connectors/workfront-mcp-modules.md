---
title: Adobe Workfront MCP モジュール
description: Adobe Workfront MCP モジュールを使用すると、Adobe WorkfrontのMCP サーバーに平易な英語のプロンプトを送信し、AI モデルにリクエストを実行させることができます。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 88515edc81bafe2d1a81df627fd51dd4ed674c02
workflow-type: tm+mt
source-wordcount: 884
ht-degree: 16%

---

# Adobe Workfront MCP モジュール

Adobe Workfront MCP コネクタは、Adobe Workfront独自のModel Context Protocol （MCP）サーバ用の専用のFusion統合です。 各モジュールが1つの固定アクションを実行する一般的なコネクタとは異なり、このコネクタには、オープンエンドの平易な英語の命令を受け入れ、AI モデルがそれを実行するために必要なWorkfrontの操作を決定できる1つのモジュールがあります。

例えば、「スケジュールに遅れているアクティブなプロジェクトをすべて検索して、ステータスを要約する」というプロンプトを入力すると、モジュールは合成された回答を返します。複数のGet モジュールとFilter モジュールを連結する必要はありません。

AIが実行できるWorkfrontのアクションを制限できるため、無人シナリオでも予期しない破壊的なアクションが実行されないようにすることができます。

デフォルトでは、このモジュールは`claude-sonnet-5` モデルを使用するAdobe Managed AIを使用します。 キーやその他の資格情報を使用して、別のLLMを使用するようにモジュールを設定できます。

>[!NOTE]
>
>Adobe Managed AIの使用は、1組織あたり月額25 ドルに制限されています。

Fusion シナリオのMCPについて詳しくは、[AI プロンプトをシナリオに追加する](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md)を参照してください。

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
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## Adobe Workfront MCPとWorkfront Fusionの連携

Adobe Workfront MCP コネクタは、OAuth 2.0を使用してWorkfrontに接続します。 他のWorkfront コネクタとは異なり、入力するホスト、クライアント ID、クライアントシークレットなどの手動の接続フィールドはありません。

接続を作成するには：

1. Adobe Workfront MCP モジュールで、Connection フィールドの横にある&#x200B;**[!UICONTROL Add]**&#x200B;をクリックします。
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
          <p>この接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
      </tr>
    </tbody>
    </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を保存し、モジュールに戻ります。

   Workfront にログインしていない場合は、ログイン画面が表示されます。 ログインしてアクセスを承認します。

Workfront Fusionにリダイレクトされ、新しいコネクションがモジュールで使用できるようになります。

>[!NOTE]
>
>最初に使用すると、コネクションは自動的にWorkfrontのMCP サーバーに登録され、その後に作成するコネクションごとに再使用されます。

## Adobe Workfront MCP モジュールとそのフィールド

### ユーザープロンプトの処理

このアクションモジュールは、指定した言語モデルを使用して、WorkfrontのMCP サーバーに対して平易な英語プロンプトを処理し、AIの回答を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody>

<tr> 
   <td>LLM キー<i> （オプション、詳細） </i></td> 
   <td> <p>デフォルトでは、このモジュールはAdobe Managed AIを使用してプロンプトを処理するため、キーを選択する必要はありません。</p> <p>代わりに独自のAI プロバイダーを使用するには、既存のLLM キーを選択するか、<b>追加</b>をクリックして次の情報を入力して新しいLLM キーを作成します。</p>
     <ul>
       <li><b> キー名</b>：新しいキーの名前を入力します。</li>
       <li><b>LLM</b>：このキーが関連付けられている大規模言語モデルを選択します。 サポートされているプロバイダーは、OpenAI、Anthropic、Amazon Bedrockです。</li>
       <li><b> キー</b>：選択したプロバイダーのAPI キーを入力するか、マッピングします。</li>
       <li><b> モデル </b>: キーで使用するLLM モデルを選択します。</li>
       <li><b>その他のフィールド </b>: LLMに必要なその他のフィールドの値を入力します。</li>
      </ul>
    </td> 
  </tr>   <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Workfront アプリをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-adobe-workfront-mcp-to-workfront-fusion" class="MCXref xref">Adobe Workfront MCPをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>読み取り専用ツール <i> （オプション） </i></td> 
   <td> <p>AIが呼び出すことができる読み取り専用のWorkfront アクションを制限します。 ツールが選択されていない場合は、すべての読み取り専用ツールが許可されます。</p> </td> 
  </tr> 
  <tr> 
   <td>ツールの書き込み/削除<i> （オプション） </i></td> 
   <td> <p>AIが呼び出しを許可するWorkfrontの書き込みまたは削除アクションを入力します。 これを空のままにすると、すべての書き込みツールと削除ツールが許可されます。</p> <p>無人シナリオで破壊的なアクションが発生しないようにするには、このフィールドを制限なしのままにするのではなく、意図的に空の選択に設定しておくことをお勧めします。</p> </td> 
  </tr> 
  <tr> 
   <td>プロンプトを入力すると</td> 
   <td> <p>AIに実行させたい命令を分かりやすい英語で入力するか、マッピングします。</p> <p>例：<i>自分に割り当てられている、スケジュールより遅れているプロジェクトをすべて検索します。</i></p> </td> 
  </tr>  </tbody> 
</table>

読み取り専用ツールと書き込み/削除ツール フィールドに選択できるツールの一覧については、Workfront ドキュメントの[Adobe Workfront MCP server tools](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-tools)を参照してください。

モジュールは次の情報を返します。この情報は、シナリオの後続のモジュールにマッピングできます。

* **応答**: AIの最終的な回答をテキストとして返します。
* **監査証跡**: AIが実行した各ツール呼び出しの元のプロンプト、開始時間と終了時間、詳細（ツール名、引数、成功したかどうか、期間、出力など）を含む、セッションの記録。
* **概要**: ツール呼び出しの試行回数、成功または失敗した回数、合計処理時間、全体的なステータスなど、セッションの合計。
