---
title: モデル コンテキスト プロトコル （MCP） モジュール
description: Model Context Protocol （MCP）モジュールを使用すると、MCP を使用してユーザ プロンプトを処理できます。
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 748055ad-d305-4513-9a5c-9c970b74a96e
source-git-commit: 5dfca593b17a234c80c807470026a7b192cbf7fa
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 23%

---

# モデルコンテキストプロトコル（MCP）モジュール

<!--SET UP REDIRECTS-->

Model Context Protocol （MCP）は、AI 言語モデルを他のアプリケーションと安全に接続する方法です。 MCP サーバーを設定すると、AI モデルがアプリケーションにアクセスできるようになります。 その後、AI モデルにプロンプトを送信し、アプリケーションから情報を返すことができます。

例えば、MCP サーバーを設定して、AI モデルを Gmail に接続できます。 「Gmail から最新の 5 通のメールを送ってください」というプロンプトを送信すると、Gmail にアクセスしてメールを返すことができます。

モデルコンテキストプロトコル（MCP）モジュールを使用すると、言語モデルと MCP サーバーを使用してユーザープロンプトを処理できます。

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





## モデルコンテキストプロトコルモジュールとそのフィールド

MCP モジュールを設定する際に、Adobe Workfront Fusion は以下に示すフィールドを表示します。 モジュール内の太字のタイトルは、必須フィールドを示します。

### ユーザープロンプトの処理

このアクション モジュールは、指定した言語モデルと MCP サーバーを使用して、プロンプトを処理します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>LLM キー</td> 
   <td> 既存の LLM キーを選択するか、「<b> 追加 </b>」をクリックして新しいキーを作成し、次の情報を入力します。 
     <ul>
       <li><b> キー名 </b>：新しいキーの名前を入力します。</li>
       <li><b>LLM</b>：このキーが関連付けられている大規模言語モデルを選択します。</li>
       <li><b> キー </b>：選択したモデルの API キーを入力またはマッピングします。</li>
       <li><b> モデル </b>: キーで使用する LLM モデルを選択します。</li>
       <li><b> 最大トークン </b>:LLM が応答で生成できる最大トークン数を入力またはマッピングします。<p>1 つのトークンは通常、4 文字、つまり英語の単語の。75 と等しくなります。 「Hello world」は 2 つのトークンと等しく、「Authentication」は 1 つのトークンと 2 つのトークンと等しくなります。</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>MCP サーバー</td> 
   <td> <p>接続する各 MCP サーバに対して、<b> 追加 </b> をクリックし、次の情報を入力します。 </p> 
     <ul>
       <li><b> 接続 </b>:Fusion が MCP サーバーへの接続に使用する接続を選択します。</li>
       <li><b>MCP サーバーホスト </b>:MCP サーバーの URL を入力します。</li>
       <li><b>MCP サーバー名 </b>：この MCP サーバーの名前を入力またはマッピングします。</li>
       <li><b> ヘッダー </b>：適用可能なヘッダーを追加します。</li>
       <li><b>MCP サーバータイプ </b>: サーバータイプを選択します。</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>プロンプトを入力 </td> 
   <td> <p>処理するプロンプトを入力またはマップします…</p> </td> 
  </tr> 
 </tbody> 
</table>


