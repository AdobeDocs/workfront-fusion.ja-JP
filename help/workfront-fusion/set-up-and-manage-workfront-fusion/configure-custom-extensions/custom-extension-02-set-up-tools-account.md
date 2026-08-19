---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: UI拡張機能ツールとアカウントの設定
description: UI拡張機能ツールとアカウントの設定
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
source-wordcount: 500
ht-degree: 0%

---


# UI拡張機能ツールとアカウントの設定

Workfront FusionのUI拡張機能を作成する前に、ツールとアカウントを設定する必要があります。 これは一度おこなう必要があります。

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

<!--Access requirements-->

## 前提条件

UI拡張機能ツールとアカウントを設定するには、次の手順を実行する必要があります。

* **Adobe組織へのアクセス権を持つAdobe ID**。 これは、Fusionへのログインに使用するアカウントです。
* **App Builderへの開発者アクセス：** 組織管理者は、**Developer** ロールを付与し、App Builderを含む&#x200B;**Product Profile**&#x200B;に追加する必要がある場合があります。 後でコマンドが「開発者以外のユーザー」で失敗する場合、または組織が表示されない場合は、Adobeの組織管理者に連絡して追加を依頼してください。
* 最後のリリースステップの&#x200B;**システム管理者** <!--Adobe? Fusion?--> （チームの他のユーザーの可能性があります）です。 作成とデプロイには開発者の役割のみが必要ですが、**承認/公開用に拡張機能を送信するには、システム管理者の役割**&#x200B;が必要です。

  Adobeのアクセスレベルについて詳しくは、を参照してください
  Adobe ドキュメントの[&#x200B; アクセスを取得する方法](https://developer.adobe.com/uix/docs/guides/get-access/)。

* **ソフトウェアをインストールし、ターミナル コマンド （macOS、Windows、またはLinux）を実行できるコンピューター**。

## Node.jsのインストール

Adobe ツールは&#x200B;**Node.js**&#x200B;で実行されます。 **LTS** バージョン （18または20）をインストールする必要があります。

1. <https://nodejs.org>に移動し、**LTS** インストーラーをダウンロードします。
1. インストーラーを実行し、デフォルトを受け入れます。
1. ターミナルを開いて実行して、動作することを確認します。

   ```sh
   node --version
   npm --version
   ```

   バージョン番号（`v20.17.0`や`10.x`など）が表示されます。

1. （条件付き） `node`が見つからない場合は、ターミナルを閉じて再度開くか、コンピューターを再起動してください。

1. 引き続き[Adobe I/O CLI （`aio`） &#x200B;](#install-the-adobe-io-cli-aio)をインストールします。

>[!TIP]
>
>* 複数のNode バージョンを使用する場合は、`nvm`などのバージョン マネージャーが便利ですが、オプションです。
>* Adobe CLIにはNode 18以降が必要です。 非常に新しい、非LTS バージョンは、時折問題を引き起こす可能性があるので、LTSを使用することをお勧めします。

## Adobe I/O CLIをインストールします（`aio`）

拡張機能の作成、ビルド、公開に使用するコマンドライン ツールは`aio`と呼ばれます。

グローバルにインストールするには：

1. コマンドラインで次の`npm` コマンドを使用します。

   ```sh
   npm install -g @adobe/aio-cli
   ```

1. 次のコマンドを使用して、インストールされていることを確認します。

   ```sh
   aio --version
   ```

   `@adobe/aio-cli/11.x.x`のような表示になります。

1. 引き続き[Adobeにログイン &#x200B;](#sign-in-to-adobe)します。

>[!NOTE]
>
> MacOS/Linuxで権限エラーが発生した場合は、**not**&#x200B;で`sudo`を使用してください。 代わりに、npmのグローバルフォルダー権限を修正するか、ホームディレクトリにインストールするNode バージョンマネージャーを使用します。

## Adobeにログイン

1. 次のコマンドを使用して、CLIをAdobe アカウントに接続します。

   ```sh
   aio login
   ```

1. 開いたブラウザーウィンドウで、Adobe IDでログインしてアクセスを承認します。

1. ログインが成功したら、ブラウザーのタブを閉じてターミナルに戻ります。

1. （オプション）後でログアウトするには（アカウントの切り替えなど）、次のコマンドを使用します：`aio logout`。
1. 引き続き[&#x200B; アクティブな組織を確認](#confirm-your-active-organization)してください。

## アクティブな組織を確認

CLIがどの組織を指しているかを確認します。

```sh
aio console org list      # see organizations you can use
aio console where         # see your currently selected org/project/workspace
```

複数の組織に属している場合は、正しい組織を選択します。

```sh
aio console org select
```

これで、プロジェクトを作成する準備が整いました。
