---
title: モデル コンテキスト プロトコル （MCP） モジュール
description: Model Context Protocol （MCP）モジュールを使用すると、MCP を使用してユーザ プロンプトを処理できます。
author: Becky
feature: Workfront Fusion
source-git-commit: d8ae176db714d2b9f041b74a62e8276171745c4b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 11%

---

# モデル コンテキスト プロトコル （MCP） モジュール

Model Context Protocol （MCP）は、AI 言語モデルを他のアプリケーションと安全に接続する方法です。 MCP サーバーを設定すると、AI モデルがアプリケーションにアクセスできるようになります。 その後、AI モデルにプロンプトを送信し、アプリケーションから情報を返すことができます。

例えば、MCP サーバーを設定して、AI モデルを Gmail に接続できます。 「Gmail から最新の 5 通のメールを送ってください」というプロンプトを送信すると、Gmail にアクセスしてメールを返すことができます。

モデルコンテキストプロトコル（MCP）モジュールを使用すると、言語モデルと MCP サーバーを使用してユーザープロンプトを処理できます。

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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## モデルコンテキストプロトコルモジュールとそのフィールド

MCP モジュールを設定すると、以下に示 [!DNL Adobe Workfront Fusion] フィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

### ユーザープロンプトの処理

このアクション モジュールは、指定した言語モデルと MCP サーバーを使用して、プロンプトを処理します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大規模言語モデル （LLM） キー ]</td> 
   <td> <p>このプロンプトに使用する大規模言語モデルの API キーを入力またはマップします。 </p> <p>現在は、Anthropic API キーのみがサポートされています。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL MCP サーバー ]</td> 
   <td> <p>このプロンプトで使用可能にする各 MCP サーバに対して、<b> アイテムの追加 </b> をクリックし、サーバの名前とホストを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL プロンプトを入力 ]</td> 
   <td> <p>大言語モデルのプロンプトを入力またはマップします。 </p> </td> 
  </tr> 
 </tbody> 
</table>
