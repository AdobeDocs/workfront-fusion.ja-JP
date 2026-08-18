---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Fusionのコンテキスト参照
description: Fusionのコンテキスト参照
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 757
ht-degree: 8%

---

# Fusionのコンテキスト参照

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

UIが`attach(...)`を呼び出すと、Fusionは現在のセッションを説明する&#x200B;**コンテキスト** オブジェクトを共有します。 このページでは、すべてのフィールド、その意味、およびFusionとAdobe IMSIDの関連付けを説明します。

## コンテキストの読み方

* **初期値：** `connection.sharedContext.get("<key>")`
* **更新：** `contextchange` イベントをリッスンします。 最新のオブジェクトは`event.detail.context`に届きます。

完全なコードパターンについては、[&#x200B; カスタム拡張機能UIの構築](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)を参照してください。

```js
const organization = connection.sharedContext.get("organization");
const fusionOrgId  = organization?.id;        // Fusion's organization id
const imsOrgId     = connection.sharedContext.get("imsOrgId"); // Adobe IMS org id
```

## トップレベルキー

| キー | タイプ | 説明 |
| ----- | ------ | ------------- |
| `imsToken` | 文字列 | サインイン ユーザーのAdobe **IMS アクセス トークン**。 これを`Bearer` トークンとして使用して、ユーザーの代わりにAdobeまたはFusion APIを呼び出します。 **機密性が高いため、ログを記録したり、表示したりしないでください。** |
| `imsOrgId` | 文字列 | フォーム `XXXXXXXXXXXX@AdobeOrg`のAdobe **IMS組織ID**。 |
| `imsUserId` | 文字列 | サインイン ユーザーのAdobe **IMS ユーザーID**。 |
| `organization` | オブジェクト | **完全にアクティブなFusion組織**。 詳しくは、この記事の[`organization` フィールド &#x200B;](#organization-fields)を参照してください。 |
| `team` | オブジェクト \|未定義 | アクティブな&#x200B;**フルアクティブなFusion チーム** （常に`fusion/nav-team/1`に関連）。 詳しくは、この記事の[`team` フィールド &#x200B;](#team-fields)を参照してください。 |
| `user` | オブジェクト | **フル サインイン Fusion ユーザー**&#x200B;です。 詳しくは、この記事の[`user` フィールド &#x200B;](#user-fields)を参照してください。 |

### Fusion IDとIMS ID

各エンティティには&#x200B;**Fusion ID**&#x200B;があり（Fusion独自のAPIで使用）、存在する場合は&#x200B;**Adobe IMSID** （Adobe Platform APIで使用）があります。

| エンティティ | Fusion id | Adobe IMS id |
| -------- | ----------- | -------------- |
| 組織 | `organization.id` | `imsOrgId` （`organization.externalOrgId`としても公開） |
| チーム | `team.id` | *（チームはFusion専用です。IMS IDはありません）* |
| ユーザー | `user.id` | `imsUserId` |

## `organization` フィールド

これらのフィールドは、アクティブな組織レコードにあります。 ほとんどの拡張機能は`id`、`name`、および識別子のみを必要とします。

| フィールド | タイプ | 説明 |
| ------- | ------ | ------------- |
| `id` | 文字列 | Fusion組織ID。 |
| `name` | 文字列 | 組織の表示名 |
| `externalOrgId` | 文字列 | Adobe IMS組織ID （`imsOrgId`と同じ値）。 |
| `externalId` | 文字列 | Fusion統合で使用される外部識別子 |
| `countryId` | 文字列 | 国設定ID。 |
| `timezoneId` | 文字列 | タイムゾーン設定ID |
| `serviceName` | 文字列 | サービス/プランの識別子 |
| `teamIds` | 文字列[] | この組織内のチームのID |
| `license` | オブジェクト | 運用、データ転送、ユーザーシート、機能フラグなど、プランの制限と使用権限 |
| `scenariosCount` | 数値 | 組織内のシナリオの合計 |
| `activeScenarios` | 数値 | 現在アクティブなシナリオ |
| `activeApps` | 数値 | アクティブなアプリまたは接続の数 |
| `operations`, `operationsExt` | 数値 | 操作の使用カウンター |
| `transfer`, `transferExt` | 数値 | データ転送使用カウンター |
| `isPaused` | ブール値 | 組織が一時停止されているかどうか |
| `isDeleted` | ブール値 | 組織が削除済みとマークされているかどうか |
| `imsEnabled` | ブール値 | Adobe IMSにリンクしている組織かどうか |
| `usersCount` | 数値 | 組織内のユーザー数 |
| `nextReset` | 文字列（日付） | 使用状況カウンターが次にリセットされたとき。 [日付](#dates)を参照 |

## `team` フィールド

これらのフィールドは、チームがアクティブな場合に表示されます。 チームが`undefined`の場合は、フォールバックを指定する必要があります（例えば、チームが選択されていない組織レベルの画面など）。

| フィールド | タイプ | 説明 |
| ------- | ------ | ------------- |
| `id` | 文字列 | Fusion チーム ID。 |
| `name` | 文字列 | チーム表示名。 |
| `organizationId` | 文字列 | このチームが属する組織のFusion ID。 |
| `country` | 文字列 | チームの国設定： |
| `timezone` | 文字列 | チームタイムゾーン： |
| `license` | オブジェクト | チームレベルの制限と使用権限： |
| `activeScenarios` | 数値 | チーム内のアクティブなシナリオ： |
| `activeApps` | 数値 | チーム内のアクティブなアプリまたは接続： |
| `scenarioDrafts` | ブール値 | シナリオドラフトが有効になっているかどうか。 |
| `isDeleted` | ブール値 | チームが削除済みとマークされているかどうか。 |
| `created` | 文字列（日付） | チームが作成されたとき。 [日付](#dates)を参照してください。 |

## `user` フィールド

これらのフィールドは、ログインしているFusion ユーザーに適用されます。

| フィールド | タイプ | 説明 |
| ------- | ------ | ------------- |
| `id` | 文字列 | Fusion ユーザーID。 |
| `name` | 文字列 | 氏名： |
| `email` | 文字列 | メールアドレス： |
| `avatar` | 文字列 | アバター画像のURL: |
| `locale` | 文字列 | `en`などのユーザーロケール。 |
| `language` | 文字列 | 設定した場合の優先言語。 |
| `timezone` | 文字列 | タイムゾーン名。 |
| `timezoneId` | 文字列 | タイムゾーン設定ID。 |
| `countryId` | 文字列 | 国設定ID。 |
| `localeId` | 文字列 | ロケール設定ID。 |
| `features` | オブジェクト | ユーザーごとの機能フラグ （例：`allow_apps`、`public_templates`） |
| `usersAdminsRoleId` | 文字列 | 該当する場合、ユーザーの管理者ロール ID。 |

>[!NOTE]
>
> `user` オブジェクトには、追加の内部フィールドが含まれる場合があります。 ここで説明したフィールドのみに依存してください。 その他のフィールドは予告なく変更される可能性があり、認証関連のフィールドの中にはログを記録したり表示したりしてはならないものもあります。

## 日付

コンテキストは拡張機能に到達する前にシリアル化されるので、**日付フィールドはJavaScript `Date` オブジェクトではなく文字列** （ISO 8601、`"2026-06-24T00:00:00.000Z"`など）として到達します。 必要に応じてこれらを変換できます。

```js
const resetDate = new Date(context.organization.nextReset);
```

## コンテキストの更新

次の場合、Fusionはコンテキスト全体（`contextchange`経由）を再送信します。

* ユーザー&#x200B;**は組織を切り替えます**,
* ユーザー&#x200B;**はチーム**&#x200B;を切り替えるか、または
* **サインイン ユーザーの**&#x200B;情報が変更されます。

1つの値のみを変更すると仮定するのではなく、`contextchange` ハンドラー内で使用するすべてのキーを常に再読み取りしてください。

## セキュリティのベストプラクティス

* **`imsToken`を記録、表示、または永続化しない。** パスワードとして扱ってください。
* 信頼できるAdobe/Fusion エンドポイントにのみ、HTTPS経由で`Bearer` トークンとしてトークンを送信します。
* 機能が必要とするものを超えたコンテキストから個人データを保存しないでください。

## トークンを使用したAPIの呼び出し

`imsToken` （プラス `organization.id` / `team.id`）を実際のWorkfrontに変換するには、または
CORSはブロックするため、Fusion データを使用すると、これらのAPIをブラウザーから直接呼び出すことはできません
it。 代わりに、小さなApp Builder ランタイムアクションを通じて呼び出しをルーティングします。 を参照
[WorkfrontおよびFusion APIの呼び出し](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)。


カスタム拡張機能の作成プロセスを続行するには、[拡張機能の公開](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)を参照してください。
