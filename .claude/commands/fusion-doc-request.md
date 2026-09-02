---
name: fusion-doc-request
description: null
source-git-commit: e354c51f13bd4f15172de068cac9720bd097eb8d
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 0%

---


# Fusion Documentation リクエスト

`#fusion-documentation` Slack チャネルに投稿された定期的な「新しい{person} ドキュメント リクエスト」パターンを処理します。リクエストを読み、ドキュメントを更新し、この種類のすべての以前のリクエストに使用するのと同じWorkfront カスタムフォームでトラッキングタスクを作成します。

これは、`fusion-release-notes` スキルとは異なるワークフローです。 このスキルは、参照記事を更新し、Workfront タスクを作成します。リクエストに「お知らせが必要：はい」と記載されている場合でも、このリポジトリで週次Fusion リリースノートのページを作成または更新しません。 ユーザーが毎週のリリースノートを個別に求める場合にのみ`fusion-release-notes`を使用してください。

## 手順1：リクエストの詳細を取得する

Slack リンクが指定されている場合は、URLから`channel_id`と`message_ts`を解析し、接続されているSlack MCP ツールに応じてスレッド（`slack_get_thread_replies`または`slack_read_thread`）を取得します。どちらか一方が失敗した場合は、両方を試してください）。 スレッドのパーマリンク/URLを維持する – ステップ 3で必要です。

この環境のSlack接続は不安定です（期限切れのトークン、セッションの途中で切断）。 フェッチが失敗した場合：
- 1回再試行してください。
- それでも失敗する場合は、フェッチが失敗したことをユーザーに明確に伝え、リクエストコンテンツを直接貼り付けるように依頼します。 内容を推測しないでください、そして言わずに黙ってあきらめないでください。

リクエストテンプレートには、次のフィールドがあります。各フィールドを抽出します。

* **機能タイトル**
* **説明**
* **ドキュメントに追加するポイント** *（特定のセクションや詳細が必要な場合があります。これらは必須として扱い、任意ではない場合は任意として扱います）*
* **リリース予定日**
* **お知らせが必要です** *（はい/いいえ – 情報提供のみ。上記のメモを参照してください。 このフィールドではアクションを実行しないでください。）*

リクエストが完全な仕様を持つConfluence Wiki ページにリンクしている場合は、ドキュメントを書く前にリクエストを取得します（`get_wiki_content`）。 技術的な詳細（正確なフィールド名、手順、UI ラベル）については、Slackの概要だけを参照しないでください。リンクされている場合は、Wiki仕様から取得します。

## 手順2：ドキュメントの更新

このリポジトリ内の関連する既存の記事を検索します（関連するモジュール名、UI ラベル、または設定名のgrep - ファイルを推測しないでください）。 記事の既存の構造、見出しレベル、および家のスタイルに従って、変更を反映するように更新します。

* Slack リクエストまたはリンクされたWiki仕様にない技術的な詳細（正確なフィールド名、権限範囲、設定ステップ）を作成しないでください。 何かが未確認の場合は、インラインでHTML コメント （例：`<!-- BECKY CHECK ME: confirm the exact permission scope before publishing -->`）としてフラグを付けます。推測ではなく、見えるコールアウトとしてフラグを立てることはありません。 公開されたページでレンダリングしてはなりません。
* これが真新しい記事ファイル（既存の記事ファイルへの編集だけでなく）を必要とする場合は、このリポジトリの常識に従ってください。frontmatterで`exl-id`/`TQID`を作成せず、新しいページを関連する目次に接続し、作成後にファイルをCRLF/no-BOMに変換します（`Write` ツールのデフォルトはLF）。

## 手順3:Workfront タスクの作成

プロジェクト：**製品ドキュメント タスク – メッセージを必要とする開発問題**&#x200B;について。 変更される場合に備えて、ハードコーディングではなく`insights_find_id_by_name` （エンティティ `project`）でIDを解決します。最後に解決されたIDについては、以下の「既知の値」を参照してください。

タスクフィールド：

| フィールド | 値 |
|---|---|
| `name` | `Becky - {Feature Title}` |
| `projectID` | 上のプロジェクトルックアップから |
| `assignedToID` | `insights_get_current_user`からの現在のユーザー |
| `categoryID` | 製品ドキュメントのカスタムフォーム ID – 以下の「既知の値」を参照してください。 不明な点がある場合は、このプロジェクトの最近の兄弟タスクに対して`task.task_categoryID`をクエリして確認します。 |
| `description` | **complete Slack message text** （リクエストテンプレートのすべてのフィールド、言い換えではありません）の後に、Slackの会話へのリンクが続きます |
| `DE:Release notes` | 書式設定されたリリースノート。以下の形式を参照してください。 |
| `DE:Preview Date Known` | `Yes` （デフォルト） |
| `DE:Preview Date` | リクエストの&#x200B;**リリース予定日** （デフォルト） |
| 製品/地域 | `Fusion`を選択します（製品ドキュメント フォームの列挙フィールド。不明な場合は`insights_search_fields`で正確なフィールド名を確認してください） |

プレビューの日付フィールドをこの同じ作成呼び出しの一部として設定します。後で表示したり、質問を待ったりしないでください。 ユーザーが後で別の日付を指定したり、日付がまだ知られていないと言った場合は、それに応じて更新しますが、毎回デフォルトで入力します。

`DE:Release notes` フィールドのリリースノート形式。 常に独自の行で`***FUSION***`から始まり、空白行、タイトルを入力します。これにより、メモが一目でFusionに属していることが示されます（core Workfrontとは異なります）。

```markdown
***FUSION***

## {Feature Title}

{Description of what changed and why it matters, in second person. A sentence or two is enough for a simple change - use multiple paragraphs and/or a bulleted list for anything with several parts or steps, the same way a full weekly release note would.}

For more information, see [{Article title}](/help/workfront-fusion/{path-to-article}.md).
```

作成呼び出しの前に、`read_workflow_docs`を`workfront://tools/create-any-object`で呼び出します。この呼び出しは、カスタムフィールドと列挙値（`DE:Preview Date Known`）を設定します。この値は、MCP サーバーのルールに従って必要です。

## 手順4：ユーザーに確認する

わかりやすい報告：

* 変更したドキュメントファイルと追加したドキュメント。
* タスク名とURL。
* プレビュー日フィールドを含め、設定した正確なフィールド値。
* 完全に自信を持っていなかったこと – 例えば、Slackが届かず、ペーストされたテキストのみから作業していたこと、ターゲットのドキュメント記事があいまいだったこと、または技術的な詳細がソース資料になかったため、推測ではなくフラグが立てられたこと。

## 既知の値（以前の実行から）

これらは永続的であると仮定するのではなく、依然として解決することを確認します。

* プロジェクト「製品ドキュメント タスク – メッセージを必要とする開発問題」はID `5e69583f00236b9f767c3e3944100ee4`にマッピングされます
* 製品ドキュメント カスタムフォーム （`categoryID`）は`5d7275b9000514604bd969d418725843`です
* 使用されるカスタムフィールド：`DE:Release notes`、`DE:Preview Date Known`、`DE:Preview Date`
