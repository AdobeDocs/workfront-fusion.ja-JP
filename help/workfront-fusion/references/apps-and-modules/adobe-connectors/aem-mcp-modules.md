---
title: Adobe Experience Manager MCP モジュール
description: Adobe Experience Manager MCP モジュールを使用すると、Adobe Experience ManagerのMCP サーバーに平易な英語のプロンプトを送信し、AI モデルにリクエストを実行させることができます。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 4c23409465b4be9fd10ff6938a750bc662ba2fe4
workflow-type: tm+mt
source-wordcount: 1020
ht-degree: 11%

---

# Adobe Experience Manager MCP モジュール

Adobe Experience Manager MCP コネクタは、Adobe Experience Manager独自のModel Context Protocol （MCP）サーバ用の専用のFusion統合です。 各モジュールが1つの固定アクションを実行する一般的なコネクタとは異なり、このコネクタには、オープンエンドの平易な英語の指示を受け入れ、AI モデルが、サイト、デジタルアセット、コンテンツフラグメント、フォルダー、コンテンツリポジトリー、コンテンツ AIなどの領域をまたいで、それを実行するために必要なAdobe Experience Managerの操作を決定できる1つのモジュールがあります。

このコネクタは、Adobe Experience Manager独自のMCP サーバー専用です。 他の無関係なMCP サーバーはサポートしていません。 コネクタの場合は、代わりに任意のMCP サーバーを指定できます。MCP エージェントコネクタを使用します。

MCP エージェントコネクタについて詳しくは、[MCP エージェントモジュール ](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/model-context-protocol-mcp-connector.md)を参照してください。

>[!NOTE]
>
>このモジュールからの回答はAIが生成したもので、利用可能なあらゆるセーフガードが導入されていても、時折不完全なものになる可能性があります。 このモジュールは、人間がすべての実行をリアルタイムで確認しないが、従来のAdobe Experience Manager モジュールから得られる決定論的な動作を保証するものではありません。

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

* このモジュールを使用するには、Adobe Experience Manager アカウントが必要です。

## Adobe Experience Manager MCPとWorkfront Fusionの連携 {#connect-adobe-experience-manager-mcp-to-workfront-fusion}

Adobe Experience Manager MCP コネクタは、OAuthを使用してAdobe Experience Managerに接続します。 ユーザー名、パスワード、API キーなど、手動で入力する接続フィールドはありません。

接続を作成するには：

1. Adobe Experience Manager MCP モジュールで、Connection フィールドの横にある&#x200B;**[!UICONTROL Add]**&#x200B;をクリックします。
1. 実稼動環境と非実稼動環境のどちらに接続するかを選択します。
1. サービスアカウントと個人アカウントのどちらに接続しているかを選択します
1. 「**続行**」をクリックします。

   Adobeのログインページにリダイレクトされます。
1. Adobe ログインページで、ログインしてアクセスを承認します。

Workfront Fusionにリダイレクトされ、新しいコネクションがモジュールで使用できるようになります。

## Adobe Experience Manager MCP モジュールとそのフィールド

現在、Adobe Experience Manager MCP コネクタには1つのモジュールしかありません。

### ユーザープロンプトの処理

このアクションモジュールは、Adobe Experience ManagerのMCP サーバーに平易な英語の命令を送信し、AIの回答を返します。

このモジュールの各実行は、ライブの会話ではなくメールを送信するのと同様に、単一の自己完結型の実行です。 AIはフォローアップの質問をして返信を待つことはできません。 その代わりに、最善の判断を下し、完全な答えを返します。 プロンプトが曖昧な場合、AIは回答の一部として行った仮定を述べており、説明を求めるために停止することはありません。

>[!IMPORTANT]
>
>このモジュールは、プロンプトが実際に要求した場合にのみ、書き込みまたは削除アクションを実行します。 要求しなかった追加のアクションは、要求した他の何かを実行している同じ実行でも実行されません。

それぞれの実行は独立しているため、モジュールには以前の実行のメモリがありません。 複数のランをまたいで、複数のターンによる会話体験を構築するには、前の質問と回答を保存します。 データストアを使用し、その履歴を次のプロンプトの先頭にテキストとして含め、その後に新しい質問を入力することができます。

データストアについて詳しくは、[ データストア ](/help/workfront-fusion/create-scenarios/data-stores/data-store-overview.md)を参照してください。

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
   <td><p>Adobe Experience Manager アカウントをWorkfront Fusionに接続する方法については、この記事の「<a href="#connect-adobe-experience-manager-mcp-to-workfront-fusion" class="MCXref xref">Adobe Experience Manager MCPをWorkfront Fusionに接続する</a>」を参照してください。</p></td>
  </tr>
  <tr>
   <td role="rowheader">ユーザープロンプト</td>
   <td><p>AIに実行させたい命令を分かりやすい英語で入力するか、マッピングします。</p><p>例：<i>90日以内に更新されていないマーケティングフォルダー内のすべてのアセットを検索します。</i></p></td>
  </tr>
  <tr>
   <td role="rowheader">読み取り専用ツール <i> （オプション） </i></td>
   <td><p>AIが呼び出すことができる読み取り専用のAdobe Experience Managerアクション（アセットの検索やページのコンテンツの読み取りなど、特定の要素のみを参照し、何も変更しないアクション）を制限します。</p><p>このフィールドを空のままにすると、すべての読み取り専用アクションが許可されます。</p></td>
  </tr>
  <tr>
   <td role="rowheader">ツールの書き込み/削除<i> （オプション） </i></td>
   <td><p>AIが呼び出すことができるAdobe Experience Managerアクション（ページの更新、コンテンツの公開、アセットの削除など、何かを変更するアクション）を制限または削除します。</p><p>このフィールドを空のままにすると、すべての書き込みアクションと削除アクションが許可されます。 無人シナリオで破壊的なアクションが発生しないようにするには、このフィールドを制限なしのままにするのではなく、意図的に空の選択に設定しておくことをお勧めします。</p></td>
  </tr>
 </tbody>
</table>

このモジュールは、AIの最終的な回答をテキストとして返し、その回答を生成する際に何が起こったのか、どのツールが呼び出されたか、各呼び出しが成功したか、処理にどのくらいの時間がかかったかなどの記録を返します。
