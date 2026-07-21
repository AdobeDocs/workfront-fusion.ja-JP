---
name: fusion-release-notes
description: 新しいWorkfront Fusion週次リリースノートを作成し、リリースアクティビティの概要ページと目次に接続します。 ユーザーが新しいFusion リリースノートまたは週次リリースページの作成、追加、ドラフトを作成する場合、またはリリースの新しいFusion機能のドキュメント作成を依頼する場合に使用します。 product-announcements/product-releasesのWorkfront（Quicksilver）リリースノートには使用しないでください。これにはrelease-notes-formatterを使用します。
source-git-commit: 59a8d8ee83906bc16fc627bd348accc4e588cf9b
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 1%

---


# Fusion リリースノート

`help/workfront-fusion/fusion-product-releases/`に新しい週次Adobe Workfront **Fusion** リリースノートを作成し、リリースアクティビティの概要ページと`help/workfront-fusion/TOC.md`の2つの場所からリンクします。

これは、`release-notes-formatter` スキルが処理するクイックシルバー（コア Workfront）のリリースノートとは異なるシステムです。

| | Fusion リリースノート（このスキル） | クイックシルバーのリリースノート （`release-notes-formatter`） |
|---|---|---|
| 頻度 | 毎週 | 四半期ごと |
| ディレクトリ | `help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/` | `help/quicksilver/product-announcements/product-releases/` |
| 機能ごとの日付コールアウト | いいえ、ページタイトルには週が含まれます | はい – 1つの機能につき`>[!NOTE]` ブロック |
| インデックスページ | `fusion-release-activity.md` （年/月別） | `{YY}-q{N}-release-overview.md` （四半期別） |

## ステップ 1：機能の収集

1週間のドキュメントの機能/変更点のリスト、および各機能のリストについて、ユーザー（まだ提供されていない場合）に尋ねます。

- 機能の短いタイトル
- 何が変更されたのか、なぜ重要なのかを明確に説明することで
- リンク先のヘルプ記事（パスが存在することを確認します。推測しないでください）
- ユーザー/管理者の操作が必要か、非推奨か（コールアウト `>[!IMPORTANT]`が必要）

## 手順2：ファイル名と日付を決定する

- 文書化されている週の月曜日（またはリリース日）を見つけ、曖昧な場合はユーザーに確認します。
- ファイルパス：`help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md`
  - `{M}`と`{D}`には&#x200B;**先頭のゼロがありません**: `fusion-2026-7-20.md`、`fusion-2026-07-20.md`。
  - 年フォルダーがまだ存在しない場合は、作成します。
- 新しいページを作成する前に、その週のページが既に存在するかどうかを確認します。

## ステップ 3：ページの作成

### Frontmatter

```yaml
---
title: Workfront Fusion release activity Week of {Month} {Day}, {Year}
description: Workfront Fusion release activity Week of {Month} {Day}, {Year}
author: {Author}
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
```

ルール：
- `title`と`description`は同一です。
- 古いページによっては省略されていても、日付（`July 20, 2026`）にコンマを必ず含めてください。その不整合をコピーしないでください。
- **新しいページごとに`hidefromtoc: true`を使用します。 `exl-id`または`TQID`.**&#x200B;を追加しないでください ページが公開されると、後で割り当てられます。ページを作成する方法が間違っています。 （2026年半ば以降のページはすべて、このパターンに従っています。例を確認する必要がある場合は、`_fusion-release-notes-reference.md`を参照してください）。

### 本文

```markdown
# Workfront Fusion release activity: Week of {Month} {Day}, {Year}

This page describes all enhancements made in Adobe Workfront Fusion the week of {Month} {Day}, {Year}.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## {Feature title}

Feature description paragraph(s) — what changed, why, and how it affects existing scenarios/configurations if relevant.

For more information, see [{Help article title}](/help/workfront-fusion/{path-to-article}.md).

## {Next feature title}

...
```

メモ：
- 機能ごとに1つのH2を、ユーザーが提供した順序で提供します（ページ内で強制的に最新の順に注文することはなく、1週間です）。
- 機能ごとに`>[!NOTE]`の日付コールアウトがありません。ページタイトルには既に日付が含まれています。
- 機能に対してアクションが必要な場合、または機能が破壊的な変更/非推奨化の場合は、説明の前にH2の直下に`>[!IMPORTANT]` コールアウトを追加します。

  ```markdown
  ## {Feature title}
  
  >[!IMPORTANT]
  >
  >**Action Required: {short summary of what the user must do and by when}**
  >
  >{Details of the requirement.}
  
  {Regular description paragraph(s).}
  ```

- すべての機能は、「詳細については、[...]」で終わる必要があります。 関連するヘルプ記事へのリンク。 リンクターゲットがリポジトリに存在することを確認します。

## 手順4：概要インデックスにページを追加する

`help/workfront-fusion/fusion-product-releases/fusion-release-activity.md`を編集：

- `## Fusion releases in {current year}` セクションを検索します（**not**&#x200B;は`+++`折りたたみ可能なブロックにラップされています。過去1年間のみ折りたたまれます）。
- リリースの月の`### {Month} {Year}`見出しを検索または作成します（年見出しの直下）。
  - 月の見出しがまだ存在しない場合は、前の月（新しい月が最初）の&#x200B;**上記**&#x200B;を追加します。
- 新しいページを、その月の見出しの下の&#x200B;**first**&#x200B;箇条書きとして追加します（新しい週が最初）。

  ```markdown
  * [Workfront Fusion release activity: Week of {Month} {Day}, {Year}](/help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md)
  ```

- これが新しい年の最初のリリースである場合は、前の年の見出しの上に新しい`## Fusion releases in {YYYY}`見出しを追加し、まだ展開されていない場合は&#x200B;*前*&#x200B;年のセクションを`+++ **Click to open**` / `+++`折りたたみ可能なブロックにラップします（現在の年のみが展開されます）。

## 手順5：目次にページを追加する

`help/workfront-fusion/TOC.md`を編集：

- `* Fusion release activity {#fusion-release-activity}`の下にネストされた現在の年の`* Fusion releases - {YYYY} {#fusion-releases-{YYYY}}`を検索します。
- 新しいページを、既存のインデント （8 スペース）と一致する、その見出しの下の&#x200B;**first** エントリとして追加します。

  ```markdown
        * [Workfront Fusion release activity: Week of {Month} {Day}, {Year}](/help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md)
  ```

- 現在の年の見出しがまだ存在しない場合は、前年の見出しの上に`* Fusion releases - {YYYY} {#fusion-releases-{YYYY}}`を追加します。
- **新しいエントリに`{hide-from-toc}` プレフィックスを追加しないでください。これは、古いエントリが表示されているナビゲーションから外れた場合にのみ使用されます（以下の「既知の不整合」を参照）。**

### 監視すべき既知の不整合（レプリケートしない）

- ページ自体が2026年リリースであるにもかかわらず、`Fusion releases - 2025`の見出しの下に2026年初頭の目次エントリがいくつかネストされています。 新しいエントリを追加する場合は、前のエントリが配置される場所ではなく、常に&#x200B;**自身の年**&#x200B;に一致する見出しの下に表示されることを再確認してください。
- 古いページタイトル/H1では、年（`July 13, 2026`ではなく`July 13 2026`）の前にコンマが省略されています。 新しいページでは常にコンマを使用する。

## ステップ 6：最終的なチェックリスト

- [ ] ファイルが正しいパスで作成され、日付に先頭ゼロが含まれていません
- [ ] Frontmatterは`hidefromtoc: true`を使用していますが、`exl-id`/`TQID`は発明されていません
- [ ] タイトル/説明の一致、日付にコンマが含まれる
- [ ]各機能には説明と「詳細情報」リンクが検証されています
- [ ] アクションが必要/非推奨化機能には`>[!IMPORTANT]`個のコールアウトがあります
- [ ]新しいページが`fusion-release-activity.md`の最新のエントリとして正しい年/月に追加されました
- [ ]新しいページが`TOC.md`の最新のエントリとして正しい年の見出しの下に追加されました
- [ ]必要に応じて新しい年/月の見出しを作成し、前年は`fusion-release-activity.md`で折りたたまれます

## 追加のリソース

完全に動作する例（簡単な複数機能の週、および`>[!IMPORTANT]`個のアクションが必要なコールアウトを含む週）については、`.claude/commands/_fusion-release-notes-reference.md`を参照してください。
