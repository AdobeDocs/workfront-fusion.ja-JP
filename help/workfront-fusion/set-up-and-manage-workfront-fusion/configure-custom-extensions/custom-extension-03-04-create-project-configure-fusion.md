---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: UI拡張性用のプロジェクトの作成
description: UI拡張性用のプロジェクトの作成
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 1360
ht-degree: 0%

---

# UI拡張性用のプロジェクトの作成

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

カスタム UI拡張機能を作成するには、それに対応するApp Builder プロジェクトを作成する必要があります。

ここでは、`aio` コマンドラインを使用して汎用App Builder プロジェクトを生成する方法について説明します。 「汎用」とは、プロジェクトが製品固有のテンプレートから&#x200B;**not**&#x200B;開始することを意味します。 汎用アプリから始めることで、プロジェクトはシンプルになり、Workfront Fusionと接続できます。

Adobe Fusion AI拡張機能で使用するプロジェクトの作成に関する次の概念と用語を理解しておくと便利です。

* **Adobe Developer Console** （<https://developer.adobe.com/console>）は、プロジェクトが存在するWeb ダッシュボードです。

* **用語**:

  | 用語 | 意味 |
  | ------ | --------------- |
  | **組織** | 自社のAdobe組織。 Fusionで使用する組織と同じです。 |
  | **プロジェクト** | 1つのアプリ/拡張機能のコンテナ。 拡張機能に1つのプロジェクトを作成します。 |
  | **ワークスペース** | 作業段階におけるプロジェクト設定のコピー。 各プロジェクトには&#x200B;**実稼動** ワークスペースがあり、通常は&#x200B;**ステージ** ワークスペースを使用してテストを行います。 「環境」のようなワークスペースを考えてみましょう。 |
  | **資格情報/ サービス** | アプリで使用できる権限。 作成されたデフォルトは、開始するのに十分です。 |

* プロジェクトを作成するには、次の2つの方法があります。

  * **自動（推奨）:** コマンド `aio app init`は、コードの生成中にプロジェクトとワークスペースを作成します。 この記事では、このプロセスについて説明します。
  * **手動：**&#x200B;最初にDeveloper Consoleで自分でプロジェクトを作成し、次に`aio`を指定します。 これは、組織でプロジェクトを一元的に作成する必要がある場合にのみ行うことをお勧めします。

* 使用するワークスペースを決定する際は、まず&#x200B;**ステージ**&#x200B;に開発してデプロイします。 Fusionは、ユーザーがFusion プロファイル（ユーザーアバターメニュー/製品設定/Fusion プロファイル/環境設定/ステージ拡張機能）でステージテストをオンにした場合にのみステージビルドを読み込みます。そうでない場合、公開された実稼動拡張機能のみが表示されます。 `aio app run`でローカルにプレビューしてから、後で&#x200B;**実稼動**&#x200B;に昇格することもできます。

  本番環境へのプロモーションについて詳しくは、[拡張機能の公開](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)を参照してください。


## `aio app init`を実行

1. ターミナルを開きます。
1. ターミナルで、プロジェクトを保存するフォルダーに移動します。
1. 実行：

   ```sh
   aio app init my-fusion-extension --standalone-app
   ```

   * `my-fusion-extension`はフォルダー/アプリ名です。 この名前は選択できますが、小文字、ハイフン、スペースは使用できません。
   * `--standalone-app`は、製品テンプレートを選択するように求める代わりに、**プレーンアプリケーションスケルトン**&#x200B;を作成するようにCLIに指示します。 これは、AEM（またはその他の）テンプレートを回避するための鍵です。

1. プロンプトが表示されたら、**組織を選択します** （複数に属している場合）。
1. プロンプトが表示されたら、「**新しいプロジェクトを作成**」を選択し、提案された名前を受け入れるか、既存の空のプロジェクトを選択します。

   このコマンドは、**ステージ**&#x200B;および&#x200B;**実稼動** ワークスペースを自動的に設定します。

   このコマンドは、ファイルを`my-fusion-extension` フォルダーに生成し、`npm install`を実行します。

1. [ プロジェクト作成の確認](#confirm-project-creation)に進みます。

>[!NOTE]
>
> **インタラクティブ メニューを希望する場合：**&#x200B;実行`aio app init my-fusion-extension` > （`--standalone-app`なし）。 **「どのテンプレートを検索しますか？」という質問が表示された場合** AEMのような商品テンプレートを選択しないでください。 **スタンドアロンアプリケーション** / **を作成するオプションを選択します「すべての拡張ポイント→なし」**。

## プロジェクト作成の確認

1. ターミナルで、作成したフォルダーに移動します。

   ```sh
   cd my-fusion-extension
   ```

   次のような構造が表示されます（一部のファイルは省略されています）。

   ```
   my-fusion-extension/
   |--- app.config.yaml   // main configuration (you will edit this)
   |---  package.json   //dependencies and scripts
   |---  src/    // your source code
   |---  web-src/  or  src/.../web-src/  // front-end files (HTML/JS)
   ```

   最も関心のある2つのファイルは次のとおりです。

   * **`app.config.yaml`**：中央設定。 このプロセスの後半で、アプリをFusion拡張機能ポイントに接続する`extensions:` セクションをここに追加します。
   * **`package.json`**: アプリで使用するライブラリを一覧表示します。 Adobe UI拡張性ゲストライブラリは、ここに追加します。

1. 続行して[必要なライブラリを追加](#add-required-libraries)します。

>[!TIP]
>
> 生成されたレイアウトがCLI バージョン間で少し異なる場合でも心配しないでください。 この手順では、作成するファイルとその中に入れるファイルを正確に指定するため、開始点に関係なく、想定される構造を一致させることができます。

## 必要なライブラリを追加

この拡張機能には2つのライブラリが必要です。

* **`@adobe/uix-guest`**: アプリをFusion （ホスト）と通信できます。
* **`@adobe/react-spectrum`**: AdobeのReact UI コンポーネントで、画面がAdobeのルックアンドフィールと一致します。 （オプションですが、推奨。代わりにプレーンHTMLを使用できます）。

これらのライブラリをインストールするには：

1. ターミナルで、以下を実行します。

   ```sh
   npm install @adobe/uix-guest @adobe/react-spectrum
   ```

1. （条件付き）生成されたプロジェクトにReactが含まれていない場合は、次もインストールします。

   ```sh
   npm install react react-dom react-router-dom
   ```

1. 続行[ プロジェクトのビルドを確認](#confirm-the-project-builds)します。

## プロジェクトの構築を確認する

何かを変更する前に、空のプロジェクトのビルドを確認してください

1. ターミナルで、以下を実行します。

   ```sh
   aio app build
   ```

   エラーなしで完了すると、ツールとプロジェクトは正しく設定されます。 プロジェクトをFusionに接続する準備が整いました。

   >[!TIP]
   >
   > **ビルドが失敗した場合、**&#x200B;最も一般的な原因は、サポートされていないNode.js バージョンです。 `node --version`を実行し、18または20であることを確認します。
   >
   >* Node.jsのインストールについて詳しくは、[ ツールの設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)を参照してください。
   >* その他の考えられるエラーについては、[ トラブルシューティング ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)を参照してください。

1. 引き続き[Fusion](#configure-the-project-for-fusion)用にプロジェクトを設定します。

## Fusion用にプロジェクトを設定する

カスタム拡張機能を設定する次のステップは、汎用プロジェクトをWorkfront Fusionに接続することです。

次のことをおこないます。

1. [拡張機能のフォルダーを作成する](#create-a-folder-for-your-extension)
1. App BuilderにFusion **拡張ポイント** （`app.config.yaml`内）について伝えます。
1. 拡張機能の部分を記述してください（`ext.config.yaml`）。
1. **ウィジェットを登録**&#x200B;し、FusionがタイトルとUIの位置を把握できるようにします。

私たちは全体を通して`fusion/nav-organization/1`を使用しています。 代わりに、「チーム」セクションをターゲットにするには、どこでも`fusion/nav-team/1`を入れ替えます。 両方をサポートするには、それぞれのパターンを繰り返します。

## 拡張機能のフォルダーを作成する

1. プロジェクトが次のように見えるように、ファイルを作成します。

   ```
   my-fusion-extension/
   |-- app.config.yaml
   |-- src/
          |-- fusion-nav-organization-1/          // one folder per extension point
             |-- ext.config.yaml
             |-- web-src/
                |-- src/
                   |-- components/
                      |-- App.js
                      |-- ExtensionRegistration.js
                      |-- DashboardWidget.js
                      |-- Constants.js
   ```

   拡張ポイント （`fusion-nav-organization-1`）の後にフォルダーの名前を付けることをお勧めします。 正確な名前は自分で決めますが、`app.config.yaml`で参照する名前と一致する必要があります。

1. [引き続き`app.config.yaml`](#declare-the-extension-point-in-appconfigyaml)で拡張ポイントを宣言します。

## `app.config.yaml`で拡張ポイントを宣言します

1. `app.config.yaml`を開き、その内容を次のように更新します。

   ```yaml
   extensions:
     fusion/nav-organization/1:
       $include: src/fusion-nav-organization-1/ext.config.yaml
   ```

   次の内容について説明します。

   * `extensions:`：このアプリは1つ以上の拡張ポイントを実装しています。
   * `fusion/nav-organization/1`：接続中のFusion スロット。 **名前は、バージョン `1`を含め、正確に**&#x200B;と一致する必要があります。
   * `$include:`：この拡張機能の内容を説明する2番目の構成ファイル （次の手順で作成）を指します。 別のファイルに保存すると、`app.config.yaml`がクリーンになり、後で拡張ポイントを追加できます。

   >[!NOTE]
   >
   >両方の拡張機能をターゲットにしている場合は、両方をリスト化し、それぞれに独自のフォルダーを持たせます。
   >
   > ```yaml
   > extensions:
   >     fusion/nav-organization/1:
   >         $include: src/fusion-nav-organization-1/ext.config.yaml
   >     fusion/nav-team/1:
   >         $include: src/fusion-nav-team-1/ext.config.yaml
   > ```

   1. [に進み、`ext.config.yaml`](#describe-the-extension-in-extconfigyaml)で拡張機能を説明してください

## `ext.config.yaml`の拡張機能を説明してください

1. `src/fusion-nav-organization-1/ext.config.yaml`の作成条件：

   ```yaml
   operations:
      view:
       - type: web
         impl: index.html
   web: web-src
   hooks:
     pre-app-build: node node_modules/@adobe/uix-guest/scripts/generate-metadata.js
      pre-app-run: node node_modules/@adobe/uix-guest/scripts/generate-metadata.js
   ```

   次の内容について説明します。

   * **`operations.view`**：拡張機能が`index.html`から提供される&#x200B;**ビュー** （表示されるUI）を提供することを宣言します。 これは、拡張機能がバックグラウンドでのみ実行するのではなく、画面を表示するようなものです。
   * **`web: web-src`**: フロントエンドファイルを保持するフォルダー。 App Builderでは、これらのコンポーネントをすべてAdobe Content Delivery Network （CDN）上に構築し、ホストしています。
   * **`hooks`**: ビルド/実行時に自動的に実行される小さなコマンド。 `generate-metadata.js` スクリプトは`@adobe/uix-guest`に付属しており、登録コードが必要とする`app-metadata.json` ファイルを生成します（手順4を参照）。 このスクリプトを書くのではなく、単に参照するだけです。

   >[!NOTE]
   >
   > サーバーサイド ロジックも必要な場合は、サーバーレス `actions` （小さなバックエンド関数）を追加することもできます。 アクションはオプションであり、UIのレンダリングには必要ないので、このガイドをフォーカスしておくためにアクションは省略します。 後で追加する場合は、ここで`actions:` フォルダーを宣言し、`app.config.yaml`に`runtimeManifest:`を宣言します。 これを追加する最も一般的な理由は、ブラウザーのCORSを押さずにWorkfront/Fusion APIを呼び出すことです。
   > APIの呼び出しについて詳しくは、[WorkfrontおよびFusion APIの呼び出し](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)を参照してください。
1. [安定した拡張機能IDの設定](#set-a-stable-extension-id)に進みます。

## 安定した拡張機能IDの設定

拡張機能には、両方のフレームが共有する一意のIDが必要です。

カスタム拡張機能に関連するフレームについて詳しくは、[UI拡張機能に含まれるフレーム ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md#frames-included-in-a-ui-extension)を参照してください。

1. `src/fusion-nav-organization-1/web-src/src/components/Constants.js`を作成：

   ```js
   module.exports = {
     extensionId: 'my-fusion-extension'
   };
   ```

   コードが拡張機能IDを参照するあらゆる場所で同じ値を使用します。
1. [ ウィジェットの登録](#register-your-widget)に進みます。


## ウィジェットを登録

「登録」は、非表示の背景フレームがFusionに対して拡張機能が提供するものを伝える方法です。 ウィジェットのタイトルと表示されるUIのURLを返す`dashboard.getWidget()` メソッドを宣言します。

1. `src/fusion-nav-organization-1/web-src/src/components/ExtensionRegistration.js`を作成します。
重要な部分は`register(...)`呼び出しです。

   ```js
   import { register } from "@adobe/uix-guest";
   import metadata from "../../../../app-metadata.json";
   import { extensionId } from "./Constants";
   
   async function init() {
     await register({
       id: extensionId,
       metadata,
       methods: {
         dashboard: {
           getWidget() {
             return {
               id: extensionId,
               title: "My Fusion tool",        // shown on the Fusion nav button
               description: "What this tool does",
               url: "/index.html#/my-widget",  // route to your visible UI
               hideWidgetHeader: false          // false = Fusion shows the title
             };
           }
         }
       }
      });
   }
   
   init().catch(console.error);
   ```

   重要なポイント：

   * **`title`**&#x200B;は、Fusionがナビゲーションボタンに付けるラベルです。 `hideWidgetHeader`が`false`の場合、タイトルはUIの上のヘッダーとしても表示されます。
   * **`url`**&#x200B;は、同じアプリ内の&#x200B;*visible* UIへのルートです。 これは、フロントエンドルーターが処理するハッシュルート（`#/my-widget`）です（次のページで設定します）。 画面をレンダリングするコンポーネントに解決する必要があります。
   * **`metadata`**&#x200B;は`app-metadata.json`から取得され、`generate-metadata` フックがビルド時に作成します。 図のように読み込みます。
   * `dashboard.getWidget` メソッド名は、ウィジェットを検出するためにFusionが呼び出す契約に同意した名前です。 `dashboard`の名前空間と`getWidget`の名前を保持します。

拡張機能のバックエンドが完了しました。 次のステップは、拡張機能のUIを構築することです。

UIの構築手順については、[ カスタム拡張機能UIの構築](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)を参照してください。
