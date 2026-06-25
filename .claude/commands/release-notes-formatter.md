---
name: release-notes-formatter
description: Workfront リリースノートの書式と検証を行って、一貫性、正しい構造、適切なリンクを確認します。 製品リリースディレクトリ内のリリースノートファイル、またはユーザーがリリースノート、製品リリース、または四半期リリースについて言及した場合にのみ使用します。 ハウツー記事や一般的なドキュメントには適用されません。
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 2%

---


# リリースノート形式

`help/quicksilver/product-announcements/product-releases/` ディレクトリのAdobe Workfront リリースノートをフォーマットして検証します。

## ページタイプ

ファイルパスとコンテンツからページタイプを特定します。

| ページ タイプ | ファイルパターン | テンプレート |
|-----------|-------------|----------|
| **概要** | `{YY}-q{N}-release-overview.md` | .claude/commands/_release-notes-formatter-reference.mdを参照してください#overview-page-template |
| **製品エリア** | `{YY}-q{N}-{area}.md` | .claude/commands/_release-notes-formatter-reference.mdを参照してください#product-area-page-template |
| **計画中** | `planning-release-activity-{YY}-q{N}.md` | 商品エリアと同様 |
| **ルックアンドフィール** | `look-and-feel-updates-{YY}-q{N}.md` | .claude/commands/_release-notes-formatter-reference.mdを参照してください#look-and-feel-page-template |

## 書式設定ワークフロー

### 手順1:Frontmatterの検証

すべてのリリースノートページの必須フィールド：

```yaml
---
title: <descriptive title>
description: <matches or summarizes the title>
author: <author name>
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: <existing UUID — never generate or change>
---
```

ルール：
- `feature`は正確に`Product Announcements`でなければなりません
- `recommendations`は正確に`noDisplay, noCatalog`でなければなりません
- `exl-id`を発明しない – 既に存在する場合にのみ含める
- 実際のページに`draft: Probably`を追加しない（テンプレートのみ）

### 手順2：ページタイプ別の構造の検証

#### 製品エリアページ

1. **H1**: `{Written Quarter} {Area} enhancements`
   - 例：`# Second Quarter 2026 Administrator enhancements`
   - 四半期には、「第1四半期」、「第2四半期」、「第3四半期」、「第4四半期」と記載する必要があります

2. **イントロパラグラフ**：概要のエリアとリンクを説明します
   - **四半期の**&#x200B;概要ファイルにリンクする必要があります
   - 一般的なバグ：前の四半期へのリンク（例：`26-q2`ではなく`26-q1`）

3. 機能ごとの&#x200B;**H2**：見出しとしての機能タイトル
   - **最新の機能が最初に** – 最新のリリースノートは、イントロパラグラフの後の最初のH2として表示される必要があります
   - 古い機能は時系列が逆になります

4. **各H2の後の日付コールアウトブロック**:

```markdown
>[!NOTE]
>
>Preview: {Month Day, Year}
>Production fast release: {Month Day, Year}
>Production for everyone: {Month Day, Year}
```

5. **Body**：機能の説明、ヘルプドキュメントへのリンク

#### 概要ページ

1. **H1**: `{Written Quarter} release overview`

2. 予定公開月を含む&#x200B;**イントロパラグラフ**

3. リリーススケジュール表を含む&#x200B;**`>[!IMPORTANT]`ブロック**

4. アンカーリンクの箇条書きリストを含む&#x200B;**H2`Adobe Workfront enhancements`**:

```markdown
* [Administrator enhancements](#administrator-enhancements)
* [Document enhancements](#document-enhancements)
```

5. HTML機能テーブルを含む製品領域&#x200B;**ごとの** H3 （。claude/commands/_release-notes-formatter-reference.md#overview-feature-tableを参照）
   - 各テーブル内では、**最新の機能が最初に** – 最新の行がテーブルの上部（ヘッダー行の後）に表示されます

6. **後続セクション** （H2）：その他の領域のリリースノート、デスクトップ校正ビューアの更新、お知らせ、API バージョン、メンテナンスの更新、トレーニングの更新

### 手順3：リンクの検証

- **製品領域ページの概要リンク**：同じ四半期を指す必要があります
   - 正解：`26-q2-release-activity/26-q2-release-overview.md`
   - 間違っています：`26-q1-release-activity/26-q1-release-overview.md`
- **概要**&#x200B;のアンカーリンク：H3 ID （小文字、ハイフン）と一致する必要があります
- **概要テーブルの機能リンク**: `class="MCXref xref" xrefformat="{para}"`を使用する必要があります
- **ヘルプドキュメントのリンク**: `/help/quicksilver/`で始める必要があります

### 手順4：日付の検証

- 形式：`{Month} {Day}, {Year}` （例：「2026年3月12日」）
- 不明な日付に`TBD`を使用
- 製品領域ページ `>[!NOTE]` ブロックの日付は、対応する概要テーブル行と一致する必要があります
- プレビュー日は生産日より前にする必要があります

### 手順5：一般的な修正

書式設定時に次の修正を適用します。

| イシュー | 修正 |
|-------|-----|
| 不適切な概要リンク四半期 | ファイルの独自の四半期に一致するように更新 |
| `>[!NOTE]`日付ブロックがありません | H2機能見出しの後にブロックを追加 |
| 日付形式に一貫性がない | `Month Day, Year`に標準化 |
| `>[!NOTE]`の前に空白行がありません | 空白行を追加 |
| 吹き出し線内の余分なスペース | 末尾の空白をトリミング |
| HTMLの商品エリアページ | マークダウンとして保持（HTMLは概要テーブル専用） |
| `exl-id`がありません | そのままにしておきます。生成しないでください |

### 手順6：目次の更新

**new** リリースノート ページ （概要または製品領域）を作成するたびに、同じ変更で`help/quicksilver/TOC.md`に追加します。 目次にないページは、概要テーブル内のリンクがそのページを指している場合でも、公開されたナビゲーションには表示されません。

追加先：

- 目次には、四半期ごとに`* 2026 Q3 Release {#release-26-q3}`のような見出しの下にセクションがあります。 四半期の見出しがまだ存在しない場合（新しい四半期の最初のページ）、前の四半期の上に追加して、新しい四半期が上に表示されるようにします。
- その四半期の見出しの下に、次の順序でページをリストします。
   1. **概要**&#x200B;最初（`Third Quarter 2026 release overview`）。
   2. **製品領域ページ**&#x200B;のアルファベット順の地域名（管理者、文書、エンタープライズ操作、プロジェクト、レポート、リクエスト）。
   3. **その他の機能強化**&#x200B;は最後に（常にアルファベット順の製品領域の後に）。

各目次エントリは、ページタイトルと絶対リポジトパスを使用したマークダウンリンクです。

```markdown
      * [Third Quarter 2026 Documents enhancements](/help/quicksilver/product-announcements/product-releases/26-q3-release-activity/26-q3-documents.md)
```

周囲のエントリにインデント（6つのスペース）を一致させます。 ページ H1のverbatimをリンクテキストとして使用します（例：`Documents enhancements`、`Requesting enhancements` （`Requests`ではなく））。したがって、目次ラベルは前四半期と一致します。

回避すべき主な間違い：

- 目次に追加せずに製品領域ページを作成します。
- 新しい製品領域ページから別の四半期の概要にリンクする（手順3）。
- 前四半期の見出しに新しい四半期のページを挿入します。

## ファイル命名規則

| タイプ | パターン | 例 |
|------|---------|---------|
| 概要 | `{YY}-q{N}-release-overview.md` | `26-q2-release-overview.md` |
| 製品エリア | `{YY}-q{N}-{area-slug}.md` | `26-q2-admin-and-setup.md` |
| ディレクトリ | `{YY}-q{N}-release-activity/` | `26-q2-release-activity/` |

標準領域スラグ：`admin-and-setup`、`documents`、`projects`、`reports`、`requests`、`other`

## 四半期マッピング

| 四半期 | 手書きフォーム | 月 |
|---------|-------------|--------|
| Q1 | 第1四半期 | ヤン=マール |
| Q2 | 第2四半期 | 4月 |
| Q3 | 第3四半期 | 7月 |
| Q4 | 第4四半期 | Oct-Dec |

四半期ごとの生産リリースは、通常、四半期の最後の月の第2週の木曜日にリリースされます。

## 検証チェックリスト

リリースノートファイルを確認する際は、次の点を確認します。

- [ ] Frontmatterには、すべての必須フィールドが正しい値で含まれています
- [ ] H1がページタイプ形式と一致しています
- [ ]概要リンクが正しい四半期を指しています
- [ ]各機能には`>[!NOTE]`個の日付ブロック （製品領域ページ）があります
- [ ]日付形式が一貫しています（`Month Day, Year`）
- [ 概要内の]機能テーブル行が製品領域ページのコンテンツに一致
- [ ]壊れた内部リンクはありません
- [ 概要の]個のアンカーリンクがH3 セクション IDと一致
- [ ]機能は、最新の順に並べられます（製品エリアページと概要テーブルの両方）
- [ ]新しいリリースノートのページが`help/quicksilver/TOC.md`に正しい四半期の下に一覧表示され、概要が最初に、製品領域がアルファベット順に表示されます（その他の最後）

## その他のリソース

- HTMLのテンプレートと例については、.claude/commands/_release-notes-formatter-reference.mdを参照してください。
