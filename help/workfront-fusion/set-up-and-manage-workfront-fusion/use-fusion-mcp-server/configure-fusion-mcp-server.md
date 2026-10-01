---
title: Adobe Workfront Fusion MCP サーバーの設定
description: Adobe Workfront Fusionを、MCP対応のAI エージェンティックプラットフォームまたはCoworker （スタンドアロンまたはFusionの右側パネル）に接続します。
source-git-commit: 6d447c16d199c69ae670f59bb56cf79464cbe057
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%
---

# Adobe Workfront Fusion MCP サーバーの設定

Adobe Workfront Fusion MCP サーバーでは、サポート対象のAI エージェント基盤での自然言語の会話を通じて、Fusion組織のシナリオ、実行、接続、webhook、データストアなどと連携できます。

Adobe Workfront Fusion MCP サーバーで使用できるツールの一覧については、[Adobe Workfront Fusion MCP サーバーツール &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-fusion-mcp-server/fusion-mcp-server-tools.md)を参照してください。

## サポートされているAI エージェント型プラットフォーム

Fusion MCP サーバーは、モデルコンテキストプロトコル（MCP）とOAuthを備えたリモート（ストリーマブル HTTP） MCP サーバーをサポートするあらゆるAI エージェント型プラットフォームで動作します。

>[!NOTE]
>
> Adobeは現在、Cloud Connectors ディレクトリまたはChatGPT アプリ/プラグインディレクトリにWorkfront Fusion コネクタを公開していません。 FusionをClaude、ChatGPT、またはMicrosoft Copilotと共に使用するには、この記事に記載されているように、URLで&#x200B;**カスタム MCP サーバー**&#x200B;として追加します。

この記事では、次の接続手順について説明します。

* [Adobe Coworker](#use-fusion-with-coworker): Fusionの右側のパネルのスタンドアロンおよびCoworkerとしてのCoworker
* [Claude](#connect-fusion-to-claude): カスタムコネクタ
* [ChatGPT](#connect-fusion-to-chatgpt): カスタム MCP サーバー
* [カスタム MCP ソリューション](#connect-fusion-to-a-custom-mcp-solution)

>[!IMPORTANT]
>
>Gemini、Cursor、VS Codeなど、別のMCP互換プラットフォームを使用している場合は、そのプラットフォームのカスタム MCP サーバーの追加方法に関するドキュメントに従ってください。 MCP サーバーのURLの入力を求められたら、次のように入力します。
>
>```
>https://mcp.fusion.adobe.com/mcp
>```

## 前提条件

Adobe Workfront FusionをAI エージェント型プラットフォームに接続する前に、次のことをおこなう必要があります。

* アクティブなAdobe Workfront Fusion ライセンスを持ち、少なくとも1つのFusion組織にアクセスする。
* Fusion ユーザーの役割と、操作するデータへのアクセス権を付与するチームの役割があります。
* Adobe ID（Adobe Identity Management System、IMS）でログインします。
* MCP対応のAI エージェント型プラットフォームやCoworkerにアクセスする。

## Adobe Workfront Fusionと同僚の連携

CoworkerはAdobeのAI エージェントです。 FusionはCoworkerに組み込まれているため、MCP URLを入力したり、OAuth アプリを登録したりする必要はありません。 Coworker with Fusionは、次の2つの場所で使用できます。

* [同僚（スタンドアロン） &#x200B;](#use-fusion-in-coworker)：他のAdobe アプリケーションと一緒にFusionを使用します。
* [Fusionの右側パネルの同僚](#use-coworker-in-the-fusion-right-rail): Fusion UI内のパネルで同僚を開きます。

どちらも、同じFusion MCP ツール、Adobe ID、Fusion権限を使用します。 MCP ツールの読み取りまたは書き込み設定は、両方で適用されます。 削除、キューのクリア、上書きなどの破壊的なアクションは、常に確認を求めます。

### Adobe Workfront Fusionの共同作業の活用

1. 共同作業者を開きます。
2. **カスタマイズ** > **統合**&#x200B;を開く
3. **fusion-mcp**&#x200B;を見つけ、**テスト**&#x200B;をクリックします。
4. 複数のFusion組織にアクセスできる場合は、自動的に選択されます。 必要に応じて、後で組織を切り替えるように同僚に依頼できます。

### Fusionの右側のパネルで同僚を使用する

Fusionで、右側のパネルに同僚が開きます

1. Workfront Fusionにログインします。
2. 右側のパネルで「**同僚**」アイコンをクリックします。
3. パネルで質問します。

### サンプルプロンプト

* *過去24時間に実行できなかったシナリオをすべて表示します。*
* *今週作成または削除されたすべてのシナリオを、最新の順に並べ替えて一覧表示します。*
* *このシナリオは何を実行していますか？*
* *なぜこの実行が失敗しましたか？*

## FusionをClaudeに接続する

Fusionをカスタムコネクタとして追加します。

>[!NOTE]
>
> Claude Team/Enterpriseでは、カスタムコネクタを追加するには所有者である必要があります。 詳しくは、Claude ドキュメントの「[&#x200B; リモート MCP](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)を使用したカスタムコネクタの基本を学ぶ」を参照してください。

1. [Claude](https://claude.ai)にログインします。
2. 左側のメニューで、**カスタマイズ**&#x200B;を選択します。
3. **コネクタ**&#x200B;を選択します。
4. **+**&#x200B;を選択してから、**カスタムコネクタを追加**&#x200B;します。
5. 名前（「Workfront Fusion」など）とMCP サーバーのURLを入力します。

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

6. 「**接続**」をクリックします。
7. サインインする。 プロファイルとFusion組織を選択します。

Claude Codeの場合、コマンドラインからサーバーを追加できます。

```
claude mcp add --transport http fusion-mcp https://mcp.fusion.adobe.com/mcp
```

## FusionをChatGPTに接続

Fusionをカスタム MCP サーバーとして追加します。

### ChatGPT デスクトップまたはCodex

1. ChatGPTで、**設定**&#x200B;を開きます。
2. 「**プラグイン**」をクリックします。
3. 「**サーバーを追加**」をクリックします。
4. サーバーの名前を入力します。
5. タイプに「**ストリーマブル HTTP**」を選択します。
6. MCP サーバーのURLを入力します。

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

7. 「**保存**」をクリックします。
8. 新しいサーバーの&#x200B;**認証**&#x200B;をクリックしてログインします。
9. サーバーの横にあるトグルがオンになっていることを確認します。

### ChatGPT web版

1. [ChatGPT](https://chatgpt.com)にログインします。
2. [https://chatgpt.com/plugins](https://chatgpt.com/plugins)に移動します。 （開発者モードは&#x200B;**設定**&#x200B;で有効にする必要がある場合があります。Business/Enterprise プランでは、管理者がカスタムコネクタを許可する必要があります）。
3. **+**&#x200B;をクリックします。
4. 「**名前**」を入力します。
5. **接続**&#x200B;で、**サーバーURL**&#x200B;を選択し、MCP サーバーURLを入力します。
6. **認証**&#x200B;を&#x200B;**OAuth**&#x200B;に設定したままにします。
7. リスクメッセージを読み、チェックボックスを選択します。
8. 「**作成**」をクリックし、次に自分のアカウントでログインします。

## Fusionをカスタム MCP ソリューションに接続する

独自のアプリケーションやエージェントを構築する場合は、Fusion MCP サーバーに直接接続します。

## 別のFusion組織への切り替え

組織を変えるために断絶する必要はありません。 Fusion MCP サーバーは、セッション内でアクティブな組織を切り替えることができます。

* _どのFusion組織がありますか？_
* _1234組織に切り替えます。_

エージェントは`fusion_orgs_list`と`fusion_orgs_set`を使用しています。 切り替えは、現在の会話/セッションにのみ適用されます。 異なるデータセンターゾーン（米国やEUなど）にある組織はすべて、同じMCP URLを通じて利用できます。

## セットアップと認証のトラブルシューティング

| 問題 | 考えられる原因 | 修正 |
| --- | --- | --- |
| CloudまたはChatGPT ディレクトリにFusion コネクタが見つかりません。 | Adobeは、Fusion用のディレクトリコネクタを公開しません。 | この記事のURLを使用して、Fusionをカスタム MCP サーバーとして追加します。 |
| ClaudeまたはChatGPTにカスタムコネクタを追加することはできません。 | プランでは、カスタムコネクタを所有者または管理者に制限します。 | ClaudeまたはChatGPT管理者に、コネクタを追加するか、カスタム MCP サーバーを許可するように依頼します。 |
| データが接続されていないか、間違ったデータが表示されます。 | 間違ったFusion組織がアクティブです。 | 担当者に組織のリストを表示して、適切な組織に切り替えるように依頼します。 |
| 認証に失敗したか、接続が機能しなくなりました。 | セッションの有効期限が切れているか、接続エラーが発生しました。 | サーバーを切断して再接続します。 |
| MCP アクセスが無効になっていることを示すメッセージが表示されます。 | Fusion組織のMCP アクセスはオフになっています。 | Fusion管理者に有効にするように依頼します。 |
| エージェントはシナリオを読み取ることはできますが、シナリオを作成、実行、更新、または削除することはできません。 | MCPの書き込みツールが無効であるか、チームの役割で許可されていません。 | Fusion管理者に、書き込みツールを有効にするか、必要なチームの役割を付与するように依頼します。 |
| カスタムアプリ認証は拒否されました。 | コールバック URLが承認済みリストにありません。 | 正確なコールバック URLを追加するように管理者に依頼します。 |
| FusionがCoworkerにリストされていないか、CoworkerがFusionの右側のパネルにありません。 | お使いの組織では機能が有効になっていません。<!-- BECKY CHECK ME: confirm whether this is the correct admin guidance before publishing. --> | Fusion管理者にお問い合わせください。 |

## よくある質問

### ClaudeまたはChatGPT用の正式なFusion コネクタはありますか？

今は必要ない。 カスタム MCP サーバーのURLを使用します。 Workfront （スタンドアロンおよびFusionの右側のパネル）にはFusionが組み込まれています。

### 複数のFusion組織を使用できますか？

はい。 再接続せずに、会話中にアクティブな組織を切り替えることができます。

### 担当者は私の代わりに何ができますか？

エージェントは、Fusionの役割とチームの権限を使用して、ユーザーと同じように機能します。 Fusionでアクセスできないものにはアクセスできません。 破壊的な行動には明示的な確認が必要です。

### エージェントは私の接続シークレットを見ますか？

いいえ。 接続ツールとキーツールは、資格情報や秘密鍵の値ではなく、メタデータ（名前、タイプ、スコープ、有効期限）を返します。
