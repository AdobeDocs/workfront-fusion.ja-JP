---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: カスタム拡張機能のデモチュートリアル
description: カスタム拡張機能のデモチュートリアル
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 964
ht-degree: 0%

---


# Fusionでカスタム拡張機能を作成するデモチュートリアル

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

このデモでは、カスタム拡張機能の作成、デプロイ、Fusionでの実行について説明します。

次のものがあります。

* 汎用Experience Cloud Shell テンプレートからApp Builder アプリをスキャフォールドします。
* アプリをFusion拡張機能ポイントにリターゲティングします。
* アプリをステージワークスペースにデプロイします。
* Fusionでステージテストをオンにして、アプリの実行中を表示します。

空の`--standalone-app`ではなくテンプレートから開始すると、SPA ブートストラップが生成されます（ルーティングと`ErrorBoundary`を含む`index.js`、`exc-runtime.js`、`App.js`、およびサンプル `ExtensionRegistration`）。 デモのライブ手順では、設定を再ターゲティングし、2つのファイルを編集します。これは、実際の`fusion-uix-guest`がどのように構築されたかです。

>[!NOTE]
>
> **時間：** ライブデモは、ツールを設定してから約10分かかります。 1回限りの設定（ノード 18/20、`aio` CLI、`aio login`）を行う必要があります。デモの&#x200B;**前**。 手順については、[UI拡張機能ツールとアカウントの設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)を参照してください。


## 事前準備

これは一度だけ行う必要があり、デモの前にカメラ外で行うことができます。

```sh
node --version          # must be 18 or 20
aio --version           # @adobe/aio-cli installed
aio login               # signs you into your Adobe org
aio console org select  # pick the org you'll demo in (same org as Fusion)
```

デモ組織では、次の2つのことが当てはまる必要があります。

* 組織の`fusion/nav-organization/1`拡張ポイントがオンボーディングされました。 オンボーディングされていない場合、デプロイはエラー1060で失敗します。 詳しくは、[ カスタム拡張機能のトラブルシューティング ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)を参照してください。
* カスタム拡張機能は、Fusion ホストで有効になります。 （この機能はデフォルトでオンになっています）。 公開されたビルドではなくステージのビルドをデモするため、Fusion プロファイルで&#x200B;**ステージ拡張機能** スイッチも有効になります。 （このスイッチは、手順7で示します）。 公開された拡張機能のみが表示されます。

## 手順1：汎用テンプレートからアプリを生成する

```sh
aio app init my-fusion-extension --template @adobe/generator-app-excshell
cd my-fusion-extension
```

* プロンプトが表示されたら「**新しいプロジェクトを作成**」を選択し、提案された名前を承認します。
* `@adobe/generator-app-excshell`は汎用の&#x200B;**Experience Cloud Shell** UI拡張テンプレートであり、製品固有ではありません。 `src/dx-excshell-1/`の下に完全な作業中のSPAを基礎に設定します。

>[!NOTE]
>
>メニューを希望する場合は、`aio app init my-fusion-extension`を実行し、**拡張機能またはスタンドアロンアプリを追加** > **テンプレート**&#x200B;を選択し、**「Experience Cloud Shell用App Builder UIX拡張機能」**&#x200B;を選択します。

次のような一連のファイルが表示されます。

```
my-fusion-extension/
|-- app.config.yaml
|-- src/dx-excshell-1/
    |-- ext.config.yaml
    |-- web-src/src/
        |-- index.js          // SPA bootstrap (exc-app Runtime + React render)
        |-- exc-runtime.js    // Experience Cloud Shell runtime glue
        |-- components/
            |-- App.js                    // Router + ErrorBoundary (generated)
            |-- ExtensionRegistration.js  // sample registration (generated)
```

## 手順2:Fusion ゲストライブラリの追加

テンプレートには、React、React Spectrum、exc-appが既に含まれています。 Fusion ホストに接続するライブラリを1つ追加します。

```sh
npm install @adobe/uix-guest
```

## 手順3：設定をFusionにリターゲティングする

**`app.config.yaml`**&#x200B;を開き、**Experience Cloud Shell ポイントから**&#x200B;の拡張ポイントキーのみをFusion 1に変更します（`$include` パスをそのまま残します）。

```yaml
extensions:
  fusion/nav-organization/1:                 # was: dx/excshell/1
    $include: src/dx-excshell-1/ext.config.yaml
```

設定の他の項目を変更する必要はありません。 フォルダー名`dx-excshell-1`は内部であり、Fusionには影響しないため、そのままにしておくことができます。 名前を変更すると、アクションパスも更新されます。 デモではこれをスキップしてください。

>[!NOTE]
>
>**チーム** セクションをターゲットにしている場合は、代わりに`fusion/nav-team/1`を使用してください。 **組織とチームの両方を実稼動環境で出荷するには、** 2つの個別のプロジェクト **を使用します。**&#x200B;レジストリ名ごとに1つの拡張機能ポイントバンドルを使用すると、共有アプリの競合を回避できます。

## 手順4：登録ファイルとウィジェットファイルの編集

すべてのパスは`src/dx-excshell-1/web-src/src/components/`未満です。

### **`ExtensionRegistration.js`**

生成されたファイルは、Experience Cloud Shell サンプルを登録します。 その`methods`をFusion **`dashboard.getWidget`**&#x200B;契約に置き換えて、FusionがタイトルとUIの位置を把握できるようにします。

```js
import { Text } from "@adobe/react-spectrum";
import { register } from "@adobe/uix-guest";
import metadata from "../../../../app-metadata.json";
import { extensionId } from "./Constants";

function ExtensionRegistration() {
  const init = async () => {
    await register({
      id: extensionId,
      metadata,
      methods: {
        dashboard: {
          getWidget() {
            return {
              id: extensionId,
              title: "My Fusion tool",          // label on the Fusion nav button
              description: "Hello from App Builder",
              url: "/index.html#/widget",       // route to the visible UI (4b)
              widgetSize: { defaultWidth: 6, defaultHeight: 6 },
              hideWidgetHeader: false,
            };
          },
        },
      },
    });
  };
  init().catch(console.error);

  return <Text>Registering with Fusion...</Text>;
}

export default ExtensionRegistration;
```

`Constants.js`が横に存在しない場合は、作成します。

```js
module.exports = { extensionId: "my-fusion-extension" };
```

### `DashboardWidget.js`

このファイルを作成します。 これにより、ハンドシェイクが完了し、ライブ Fusion コンテキストが表示されます。

```js
import { useEffect, useState } from "react";
import { Flex, Heading, Text, View } from "@adobe/react-spectrum";
import { attach } from "@adobe/uix-guest";
import { extensionId } from "./Constants";

const KEYS = ["imsOrgId", "imsUserId", "organization", "team", "user"];

export default function DashboardWidget() {
  const [ctx, setCtx] = useState(null);

  useEffect(() => {
    attach({ id: extensionId })
      .then((guest) => {
        const read = () =>
          KEYS.reduce((acc, k) => ({ ...acc, [k]: guest.sharedContext.get(k) }), {});
        setCtx(read());
        guest.addEventListener("contextchange", () => setCtx(read()));
      })
      .catch((e) => console.error("attach failed", e));
  }, []);

  return (
    <View padding="size-300">
      <Heading level={2}>Hello from App Builder</Heading>
      {!ctx ? (
        <Text>Connecting to Fusion...</Text>
      ) : (
        <Flex direction="column" gap="size-100" marginTop="size-200">
          <Text>User: {ctx.user?.name ?? ctx.imsUserId}</Text>
          <Text>Organization: {ctx.organization?.name} (id {ctx.organization?.id})</Text>
          <Text>Team: {ctx.team?.name ?? "-"}</Text>
        </Flex>
      )}
    </View>
  );
}
```

### `App.js`

生成されたルーターは既に`index` / `index.html`を`ExtensionRegistration`に送信しています。 ウィジェットのルートを追加して読み込みます。

```js
import DashboardWidget from "./DashboardWidget";
// ...inside <Routes>, alongside the existing ExtensionRegistration routes:
<Route exact path="widget" element={<DashboardWidget />} />
```

> ルート パス （`widget`）は、`getWidget().url` （`/index.html#/widget`）のハッシュと一致する必要があります。 生成された`index.js` / `exc-runtime.js`と残りの`App.js`は、テンプレートで提供するブートストラップであるため、厳密に足場に合わせて保持します。

## ステップ 5：構築

```sh
aio app build
```

これにより、フロントエンドがコンパイルされ、`app-metadata.json`を生成するメタデータフックが実行されます。 続行する前にエラーを修正してください。

## 手順6：ステージへのデプロイ

```sh
aio console workspace select     # choose Stage
aio app deploy
```

`deploy`はAdobeのCDNでUIをホストし、拡張機能エンドポイントをステージワークスペースに登録します。これは、Fusionが検出するものです。 CLIは、`https://<project>-stage.adobeio-static.net`などのエンドポイント URLを出力します。

## ステップ 7: ステージテストをオンにして、Fusionで拡張機能を表示する

1. Adobe Experience CloudでFusionを開き、デプロイ先と同じ組織にログインします。
1. ユーザーアバターメニューを開き、**製品設定** > **Fusion プロファイル** > **環境設定**&#x200B;に移動します。
1. **ステージング拡張機能** スイッチをオンにして、リロードを確認します。

   Fusionがステージワークスペースから拡張機能を読み込み、それらを&#x200B;**（ステージ）**&#x200B;とマークするようになりました。
1. 左側のナビゲーションの&#x200B;**組織**&#x200B;領域に移動します。

   **「My Fusion tool （Stage）」** ボタンが表示されます。
1. 「**」 My Fusion ツール （ステージ）「**」ボタンをクリックします。
UIがメインパネルに読み込まれ、ライブユーザー、組織、チームが表示されます。
1. **Fusionでアクティブな組織またはチーム**&#x200B;を切り替えます。

   パネルが更新され、ライブコンテキスト （`contextchange`）が示されます。

>[!TIP]
>
>ボタンが表示されない場合は、検出はセッションごとにキャッシュされるので、1回リロードします。 次に、[ カスタム拡張機能のトラブルシューティング ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)を参照してください。


## デモ中の反復

変更を加え、再構築して再デプロイします。  次回ユーザーが拡張機能を開いたときに、更新された拡張機能が表示されます。

```sh
aio app build && aio app deploy
```

## デモの後、本番環境に移行する

デモするにはステージで十分です。 組織全体でリリースするには、実稼動ワークスペースに切り替えて、デプロイし、承認リクエストを送信します。 リクエストは、システム管理者の役割を使用して送信する必要があります。 完全なプロセスについては、[実稼動環境でのリリース ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md#release-on-production)を参照してください。

## デモトークトラック（オプション）

ライブデモでは、次の点を考慮する必要があります。

* **「汎用Experience Cloud Shell テンプレートから開始しました。」** SPA シェル全体をスキャフォールドするので、拡張ポイントをリターゲティングして2つのファイルを編集しただけです。
* **&quot;Fusionはホストです。アプリはゲストです。&quot;** これらは別々のフレームで実行され、カスタムネットワークを使用せずに、AdobeのUI拡張性SDKについて説明します。
* **「登録とビューの比較」** 非表示フレーム *は私が提供するものを*&#x200B;登録し（`dashboard.getWidget`）、表示フレーム *は*&#x200B;を添付し、コンテキストを読み取ります。
* **&quot;ステージテストはユーザーごとのスイッチです。&quot;** Fusionには、デフォルトで公開された拡張機能のみが表示されます。 私はFusion プロファイルのステージ拡張機能を反転して、実稼動リリースなしでステージのビルドを読み込みました。
* **「ライブ コンテキスト」** 組織またはチームを切り替えるとコンテキストが再送信され、ゲストは再レンダリングされます。
