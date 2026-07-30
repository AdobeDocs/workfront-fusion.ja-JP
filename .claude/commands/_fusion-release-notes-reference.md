---
source-git-commit: 67301a4e3c16eaed28f92a1be7556c5574308429
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---
# Fusion リリースノートのリファレンス例

実際の最近のページに基づく、`fusion-release-notes` スキルの作業済み例
`help/workfront-fusion/fusion-product-releases/fusion-releases-2026/`.

&#x200B;---

## 例1：単純なマルチフィーチャー週

`fusion-2026-6-22.md`に基づきます。

```markdown
---
title: Workfront Fusion release activity Week of June 22, 2026
description: Workfront Fusion release activity Week of June 22, 2026
author: Becky
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
# Workfront Fusion release activity: Week of June 22, 2026

This page describes all enhancements made in Adobe Workfront Fusion the week of June 22, 2026.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## Create custom JavaScript packages to use in scenarios

To provide better flexibility and control of your scenarios, we've added the ability to create a custom JavaScript packages that you can then use in scenarios. You can create custom packages in the Packages area of Fusion. You then add functions or variables from these packages to your scenarios in the form of an Adobe App Builder module.

Packages include functions, along with any variables or dependencies the functions rely on. You can also test functions in your package before using them in your scenarios

Because custom packages work through Adobe App Builder, your organization must have an Adobe App Builder license to use them.

For more information on using custom functions in Fusion, see [Use custom function packages](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md).

## View changes between scenario versions

To make it easier to understand changes between scenario versions, we've added the ability to view and compare those changes. Now you can bring up a window that displays specific changes between two selected versions of the same scenario.

For more information, see [View and manage scenario versions](/help/workfront-fusion/manage-scenarios/restore-a-scenario-version.md).
```

&#x200B;---

## 例2：アクションが必要/非推奨のコールアウトを含む週

`fusion-2026-3-9.md`に基づきます。

```markdown
---
title: Workfront Fusion release activity Week of March 9, 2026
description: Workfront Fusion release activity Week of March 9, 2026
author: Becky
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
# Workfront Fusion release activity: Week of March 9, 2026

This page describes all enhancements made in Adobe Workfront Fusion the week of March 9, 2026.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## Log in to Fusion through Adobe IMS

>[!IMPORTANT]
>
>**Action Required: Migrate to IMS Login for Adobe Workfront Fusion by April 15.**
>
>To ensure that you will be able to log in after April 15, your Fusion administrator must migrate you to Adobe IMS. Please contact your Fusion administrator to be migrated.

As part of our ongoing security enhancements, Adobe is deprecating the legacy username and password login method for Adobe Workfront Fusion. Effective **April 15**, the legacy login flow **will no longer be supported**.

Going forward, access to Adobe Workfront Fusion will require authentication through the Adobe Identity Management System (IMS) login flow.

For instructions on provisioning access through the Adobe Admin Console, see [Add users to Adobe Workfront Fusion through the Adobe Admin Console](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-fusion-users-admin-console.md).

If you have questions or need assistance with the migration process, please contact your Adobe representative.

## New route labels

To make it easier to identify routes, we've added labels. Now, routes are labeled in the order they execute. Fallback and error handling routes are also labeled. Route labels also display any filters used for that route.

For more information on routes, see [Add a Router module and configure routes](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).
```

&#x200B;---

## 例3：新しいコネクタの起動

`fusion-2026-7-27.md`に基づきます。

```markdown
## Adobe Content Tagger connector and modules now available

You can now use Workfront Fusion to tag content in Adobe documents.

With the Adobe Content Tagger modules, you can:

* Tag colors in an image, returning the percentage covered by different pixel colors
* Tag keywords or key phrases that best describe the subject of a document
* Tag text in an image, indicating whether text is present and returning it if so

For more information, see [Adobe Content Tagger modules](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/content-tagging-modules.md).
```

このようなコネクター起動の場合は、ユーザーがリダイレクトの設定を必要とするかどうかを（スキルの手順1に従って）常に尋ねます。

&#x200B;---

## 概要ページ （`fusion-release-activity.md`）の更新パターン

2026年7月20日の週を、既存の2026年7月の月セクションに追加します。

```markdown
## Fusion releases in 2026

### July 2026

* [Workfront Fusion release activity: Week of July 20, 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-20.md)
* [Workfront Fusion release activity: Week of July 13 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-13.md)
```

真新しい年を開始する（例えば、{YYYY+1}の最初のリリースが公開されたときにのみ行う）:

```markdown
## Fusion releases in 2027

### January 2027

* [Workfront Fusion release activity: Week of January 4, 2027](/help/workfront-fusion/fusion-product-releases/fusion-releases-2027/fusion-2027-1-4.md)

## Fusion releases in 2026

+++ **Click to open**

### December 2026
...
+++
```

&#x200B;---

## TOC.md更新パターン

2026年7月20日の週を新しいエントリとして追加します。

```markdown
* Fusion release activity {#fusion-release-activity}
    * [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)
    * Fusion releases - 2026 {#fusion-releases-2026}
        * [Workfront Fusion release activity: Week of July 20, 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-20.md)
        * [Workfront Fusion release activity: Week of July 13 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-13.md)
        ...
```

&#x200B;---

## リポジトリ参照をリダイレクトします（手順7の場合）。

兄弟`redirects` リポジトリ （`Adobe-Enterprise-Docs/redirects`）は、`redirects/`の下のCSV ファイルに1:1のリダイレクトを保持しており、環境ごとに1つ保持しています：`redirects-dev.csv`、`redirects-stage.csv`、`redirects-prod.csv`。

行ルール（そのリポジトリのREADMEから）:

- `source`は`/en`で始まる必要があり（言語のバリエーションが自動作成されます）、スペースが含まれていません。
- `destination`は、`/en`で始まる相対パス、または`https`で始まる完全なURLであり、スペースを含めることはできません。
- 重複する`source`はなく、`source`/`destination` ペアも重複しません。
- リダイレクトはリダイレクトループを引き起こしてはなりません。

行を追加した後も、PRを`redirects` リポジトリで引き上げ、ライブになる前にマージする必要があります（1:1 リダイレクトのマージ後は約5分）。 このスキルは、ユーザーが確認した後にのみ行を追加します。つまり、PRは上げません。

&#x200B;---

## 既存ページの既知の不整合（参照用のみ。新しいページにコピーしないでください）

1. **TOC.md**&#x200B;で年の見出しが間違っています – 2026年1月から2月のエントリは、現在`Fusion releases - 2026`ではなく`Fusion releases - 2025`の見出しの下にあります。 これは既存のバグであり、意図された構造ではありません。
2. **年より前にコンマがありません** — `fusion-2026-7-13.md`などのページでは、タイトル/説明/H1に「2026年7月13日」ではなく「2026年7月13日」を使用します。 常に新しいページにコンマを含めます。
3. **`hidefromtoc`対`exl-id`/`TQID`** — `fusion-2026-4-27.md`までのページには`exl-id` （場合によっては`TQID`）が含まれます。代わりに`fusion-2026-5-4.md`以降のページでは`hidefromtoc: true`が使用されます。 新しいページは、後で公開パイプラインによって識別子が割り当てられるため、新しいパターン（`hidefromtoc: true`、なし`exl-id`/`TQID`）に従う必要があります。
4. TOC.md **の**`{hide-from-toc}`&#x200B;接頭辞 – レンダリングされたナビゲーション内の古いエントリが最近使用したビューから古くなると、そのエントリを非強調表示するために使用されます。 新しいエントリに追加しないでください。
