---
source-git-commit: 4d32e8aab5b3b8a12dbc23e61f517fc4fd6dc9e5
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---
# リリースノートのリファレンステンプレート

各リリースノートのページタイプの詳細テンプレート。 テンプレートにもとづいています
`help/quicksilver/product-announcements/product-releases/release-note-templates/`および
直近の四半期リリースで使用された実際の書式設定。

---

## 製品領域ページテンプレート

```markdown
---
title: {Written Quarter} {Year} {Area} enhancements
description: {Written Quarter} {Year} {Area} enhancements
author: {Author}
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: {existing UUID}
---
# {Written Quarter} {Year} {Area} enhancements

This page describes {Area} enhancements made with the {Written Quarter} {Year} release to the Preview environment. These enhancements will be made available in the Production environment as noted.

For a list of all changes available at this point in the {Written Quarter} {Year} release cycle, see [{Written Quarter} {Year} release overview](/help/quicksilver/product-announcements/product-releases/{YY}-q{N}-release-activity/{YY}-q{N}-release-overview.md).

## Feature Title Here

>[!NOTE]
>
>Preview: {Month Day, Year}
>Production fast release: {Month Day, Year}
>Production for everyone: {Month Day, Year}

Feature description paragraph.

For more information, see [Help article title](/help/quicksilver/path/to/article.md).
```

### 商品エリアページのルール

- 本文コンテンツにマークダウン（HTMLではなく）を使用する
- 各機能にはH2見出しが付きます
- `>[!NOTE]`の吹き出しの前に空白行が必要です
- `>[!NOTE]`形式は正確に次のとおりです。

  ```
  >[!NOTE]
  >
  >Preview: {date}
  >Production fast release: {date}
  >Production for everyone: {date}
  ```
- 機能が一時的に削除された場合は、日付の後に行を追加します。

  ```
  >
  >This feature has been temporarily removed from the Production environment on {date}.
  ```
- ヘルプリンクは、`/help/quicksilver/`で始まる絶対パスを使用します

---

## 概要ページテンプレート

```markdown
---
title: {Written Quarter} {Year} release overview
description: This page provides information about functionality that is included in the {Written Quarter} {Year} release. These enhancements are planned to become available in the Production environment throughout the quarter.
author: {Author}
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: {existing UUID}
---
# {Written Quarter} {Year} release overview

This page provides information about functionality that is included in the {Written Quarter} {Year} release scheduled for {Release Month} {Year}.

The enhancements on this page are available in the Preview environment. This page will be updated with additional enhancements as the {Written Quarter} {Year} release nears its planned Production release.

>[!IMPORTANT]
>
>
>Monthly and quarterly releases are planned to be available on the Thursday of the second full week of the month, unless otherwise specified.
>
>|Monthly release|Quarterly release|
>|----|----|
>|<ul><li>{VV}.{M} ({Month Day, Year})</li><li>{VV}.{M} ({Month Day, Year})</li><li>{VV}.{M} ({Month Day, Year})</li></ul>|<ul><li>{VV}.{M} ({Month Day, Year})</li></ul>|
>
>Note that for the final release of each quarter ({VV}.{M} this quarter), users on the fast release schedule will receive the release one day early ({Month Day, Year}).
>
>For more information on the fast release process, see [Enable or disable the fast release process](/help/quicksilver/administration-and-setup/set-up-workfront/configure-system-defaults/enable-fast-release-process.md).

## Adobe Workfront enhancements

* [Administrator enhancements](#administrator-enhancements)
* [Document enhancements](#document-enhancements)
* [Project enhancements](#project-enhancements)
* [Reporting enhancements](#reporting-enhancements)
* [Requesting enhancements](#requesting-enhancements)
* [Other enhancements](#other-enhancements)
```

### 概要機能テーブル

各H3製品領域セクションには、HTML テーブルが含まれています。 次の構造を使用します。

```html
### {Area} enhancements

<table>
            <col style="width: 50%;" />
            <col style="width: 25%;" />
            <tbody>
              <tr>
        <td><strong>Feature</strong>
        </td>
        <td><strong>Preview</strong></td>
        <td><strong>Fast release</strong></td>
        <td><strong>Quarterly</strong></td>
        </tr>
    <tr>
        <td>
            <a href="/help/quicksilver/product-announcements/product-releases/{YY}-q{N}-release-activity/{YY}-q{N}-{area}.md" class="MCXref xref" xrefformat="{para}">Feature Title</a><p>Short description of the feature.</p>
        </td>
        <td><p>{Month Day, Year}</p></td>
        <td><p>{Month Day, Year}</p></td>
        <td><p>{Month Day, Year}</p></td>
    </tr>
            </tbody>
        </table>
```

#### テーブルルール

- 機能セル：`<a>` タグに`class="MCXref xref" xrefformat="{para}"`が付けられ、その後`<p>`の説明が続きます
- `href`は製品領域ページにリンクします（特定のアンカーではありません）
- 日付セル：`<p>` タグで折り返されています
- スケジュール外の項目の場合は、リンクの後に`<p>[!BADGE Off schedule]{type=Neutral}</p>`を追加します
- バッジが不要な場合、リンクが許可された後に`<p></p>`が空になります
- HTMLのインデントを既存のファイルと一致させる

### 概要の末尾のセクション

すべての製品領域テーブルの後：

```markdown
## Release notes for other areas

### Workfront Fusion enhancements

New features in Workfront Fusion are available in Production at a cadence outside of the standard release schedule. For more information about the latest features, see [Adobe Workfront Fusion release activity](https://experienceleague.adobe.com/en/docs/workfront-fusion/using/fusion-release-activity/fusion-release-activity).

### Workfront Planning enhancements

New features in Workfront Planning are available in Production. For more information about the latest features, see [{Written Quarter} {Year} release activity for Adobe Workfront Planning](/help/quicksilver/product-announcements/product-releases/planning-release-activity/planning-release-activity-{YY}-q{N}.md).

There are no updates for the following at this point in the release:

* Scenario Planner
* Proof
* Goals

## Desktop proofing viewer updates

{Version info if available, otherwise omit section}

## Announcements

{Announcement content}

### API version {NN}

{API version info}

### Workfront Maintenance Updates

For information about the maintenance updates made during the {Written Quarter} {Year} release, see [Workfront Maintenance Updates](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html).

### Training updates

Explore the latest updates made to learning programs, learning paths, videos, and guides for each Adobe Workfront product release. For more information, see the "What's New" section of the [Workfront Tutorials page](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/home.html).
```

---

## ルックアンドフィールのページテンプレート

```markdown
---
title: Look-and-feel updates during the {Written Quarter} {Year} release time frame
description: Look-and-feel updates during the {Written Quarter} {Year} release time frame
author: {Author}
feature: Product Announcements
recommendations: noDisplay, noCatalog
exl-id: {existing UUID}
---

# Look-and-feel updates during the {Written Quarter} {Year} release time frame

This page describes minor updates to the look and feel of various areas of the Adobe Workfront application that were made within the {Written Quarter} {Year} release timeframe. These enhancements will be made available in the Production environment a minimum of 2 weeks after releasing to Preview.

For a list of all changes available with the {Written Quarter} {Year} release, see [{Written Quarter} {Year} Release overview](/help/quicksilver/product-announcements/product-releases/{YY}-q{N}-release-activity/{YY}-q{N}-release-overview.md).

## Feature Title

>[!NOTE]
>
>Preview release: {Month Day, Year}; Planned Production release: {Month Day, Year}

Description of the look-and-feel change.
```

---

## 日付コールアウト形式

### 商品エリアページ（複数行）

```markdown
>[!NOTE]
>
>Preview: March 5, 2026
>Production fast release: April 15, 2026
>Production for everyone: April 16, 2026
```

### ルックアンドフィールページ（単一行）

```markdown
>[!NOTE]
>
>Preview release: March 5, 2026; Planned Production release: March 19, 2026
```

### 週別ページ （単一行）

```markdown
>[!NOTE]
>
>Preview release: February 9, 2023; Planned Production release: February 23, 2023
```

---

## 監視すべき既知の不整合

1. **不適切な概要リンク四半期** – 製品領域のページが前四半期の概要にリンクされることがあります（`26-q2`ではなく`26-q1`など）
2. **間違った年を表示する日付のプレビュー** – 概要テーブルで、プレビュー列に前年が表示されることがある（「2026」ではなく「2025」など）
3. **閉じる`</tr>` タグが見つかりません** – 一部のHTML テーブル行に適切な閉じるタグがありません
4. **`content-type: release-notes`** – 古いファイルに存在し、新しい26 ～ q2の製品領域ページでは省略されます。 現在の四半期のパターンに従います。
5. **テンプレートのタイプミス** — ルックアンドフィール テンプレートには`release`ではなく`relesae`が含まれています。常に正しいスペルを使用してください
6. **機能リンク**&#x200B;の後に`<p></p>`がありません。一部の概要テーブル行では、`<a>` タグの後の空の`<p>` タグが省略されています
