---
title: MCP （Model Context Protocol）モジュール
description: Model Context Protocol （MCP）モジュールを使用すると、MCPを使用してユーザープロンプトを処理できます。
author: Becky
feature: Workfront Fusion
hide: true
exl-id: 748055ad-d305-4513-9a5c-9c970b74a96e
source-git-commit: 80f2d078cd624424f23bd007e852f49643fec7f3
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 18%

---

# MCP エージェントモジュール

<!--SET UP REDIRECTS-->

モデルコンテキストプロトコル（MCP）とは、AI言語モデルを他のアプリケーションと安全に接続する方法です。 AI モデルがアプリケーションにアクセスできるようにするMCP サーバーを設定します。 その後、AI モデルにプロンプトを送信し、アプリケーションから情報を返すことができます。

例えば、AI モデルをGmailに接続するようにMCP サーバーを設定できます。 「Gmailから最後の5通のメールを受け取ります」というプロンプトを送信すると、Gmailにアクセスしてメールを返すことができます。

Model Context Protocol （MCP）モジュールを使用すると、言語モデルとMCP サーバーを使用してユーザープロンプトを処理できます。

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

## 前提条件

* 接続するMCP サーバーを設定している必要があります。
* 選択したLLM （大規模言語モデル）へのLLM キーが必要です。

## モデルコンテキストプロトコルモジュールとそのフィールド

### プロセスユーザープロンプト

このアクションモジュールは、指定した言語モデルとMCP サーバーを使用してプロンプトを処理します。

>[!NOTE]
>
>このモジュールはオブジェクトを返す必要があります。 文字列や数値などの出力は返されません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>LLM キー</td> 
   <td> 既存のLLM キーを選択するか、<b>追加</b>をクリックして次の情報を入力して新しいLLM キーを作成します。 
     <ul>
       <li><b> キー名</b>：新しいキーの名前を入力します。</li>
       <li><b>LLM</b>：このキーが関連付けられている大規模言語モデルを選択します。</li>
       <li><b> キー</b>：選択したモデルのAPI キーを入力またはマッピングします。</li>
       <li><b> モデル </b>: キーで使用するLLM モデルを選択します。</li>
       <li><b>最大トークン </b>: LLMが応答で生成できるトークンの最大数を入力またはマッピングします。<p>1つのトークンは通常4文字、つまり英語では0.75単語に相当します。 「Hello world」は2つのトークンに相当し、「Authentication」は2つのトークンに1つに相当します。</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>MCP サーバー</td> 
   <td> <p>接続する各MCP サーバーについて、<b>Add</b>をクリックし、次の情報を入力します。 </p> 
     <ul>
       <li><b>接続</b>: FusionがMCP サーバーへの接続に使用する接続を選択します。</li>
       <li><b>MCP Server Host</b>: MCP サーバーのURLを入力します。</li>
       <li><b>MCP サーバー名</b>：このMCP サーバーの名前を入力するか、マッピングします。</li>
       <li><b> ヘッダー</b>：該当するヘッダーを追加します。</li>
       <li><b>MCP サーバーの種類</b>: サーバーの種類を選択します。</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>プロンプトを入力すると </td> 
   <td> <p>処理するプロンプトを入力するか、マッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>


