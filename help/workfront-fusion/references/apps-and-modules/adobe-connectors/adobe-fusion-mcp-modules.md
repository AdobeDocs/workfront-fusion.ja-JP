---
title: Adobe Fusion MCP モジュール
description: Adobe Fusion MCP モジュールを使用すると、Adobe FusionのMCP サーバーに平易な英語のプロンプトを送信し、AI モデルにリクエストを実行させることができます。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 06ba1c54288fff09f866bffa5c3fce7381c71ad2
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 14%
---
# Adobe Fusion MCP モジュール

Adobe Fusion MCP コネクタは、英語のプレーンプロンプトを1つAdobe Fusion Model Context Protocol （MCP）サーバーに送信します。 AI モデルがリクエストを解釈し、それを完了するために必要なFusion ツールを呼び出します。

コネクタは、ホストされているAdobe Fusion MCP サーバーでのみ機能します。 別のMCP サーバーを指定することはできません。

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## Adobe Fusion MCPとWorkfront Fusionの連携

Adobe Fusion MCP モジュール内から直接接続を作成できます。

1. Adobe Fusion MCP モジュールで、**接続** フィールドの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">接続名</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">環境</td>
        <td>
          <p>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">タイプ</td>
        <td>
          <p>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</p>
        </td>
      </tr>
    </tbody>
   </table>

1. 「**[!UICONTROL 続行]**」をクリックします。

Adobeのログインページにリダイレクトされます。 Adobe アカウントでログインし、アクセスを承認します。 Workfront Fusionにリダイレクトされ、新しいコネクションがモジュールで使用できるようになります。

## Adobe Fusion MCP モジュールとそのフィールド

### ユーザープロンプトの処理

このアクションモジュールは、Adobe Fusion MCP サーバーに平易な英語プロンプトを送信します。 AI モデルがプロンプトを解釈し、それを完了するために必要なFusion ツールを呼び出して、結果を返します。

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
  </tr> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Adobe Fusion MCPをWorkfront Fusionに接続する手順については、この記事の「<a href="#connect-adobe-fusion-mcp-to-workfront-fusion" class="MCXref xref">Adobe Fusion MCPをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>読み取り専用ツール <i> （オプション） </i></td> 
   <td> <p>特定の読み取り専用ツールを選択してAIを制限します。 何も選択しない場合は、このカテゴリのすべての読み取り専用ツールが許可されます。</p> </td> 
  </tr> 
  <tr> 
   <td>ツールの書き込み/削除<i> （オプション） </i></td> 
   <td> <p>特定の書き込みツールまたは削除ツールを選択して、AIを制限します。 何も選択しない場合は、このカテゴリのすべての書き込みツールと削除ツールが許可されます。</p> <p>無人シナリオで破壊的なアクションが発生しないようにするには、このフィールドを制限なしのままにするのではなく、意図的に空の選択に設定しておくことをお勧めします。</p> </td> 
  </tr> 
  <tr> 
   <td>プロンプトを入力すると</td> 
   <td> <p>AIに実行させたい命令を分かりやすい英語で入力するか、マッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### AIが呼び出せるツールを制限する

読み取り専用ツールと書き込み/削除ツール フィールドでツールを選択することで、AIが呼び出すことができるFusion ツールを制限できます。

* フィールドを空のままにすると、AIはそのカテゴリのすべてのツールを呼び出すことができます。
* 両方のフィールドを空のままにすると、AIはFusion MCP サーバー上のすべてのツールを呼び出すことができます。

無人シナリオで書き込みまたは削除アクションが実行されないようにするには、「読み取り専用ツール」フィールドで許可するツールのみを選択し、「書き込み/削除ツール」フィールドで、AIの呼び出しに適したツールを少なくとも1つ選択します。

リスト内のツール名は、Fusion MCP サーバーから取得されます。

#### モジュールがプロンプトを処理する方法

* モジュールにはフォローアップのターンがありません。 プロンプトが不明確な場合、AIは合理的な仮定をおこない、質問するのではなく回答として明記します。
* AIはツールを使用して変更できる情報を確認します。
* AIは、プロンプトが要求した以外の書き込みアクションや削除アクションを実行しません。
* モジュールには有効な接続が必要です。 無ければ走りません。

#### 出力

モジュールは次の情報を返します。この情報は、シナリオの後続のモジュールにマッピングできます。

* **応答**: AIの最終的な回答をテキストとして返します。
* **監査記録**：呼び出されたツール、引数と結果、およびタイミングを含む、セッションの記録。
* **概要**：成功したツール呼び出しの数と最終ステータスを含む、セッションの合計。
