---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: カスタム拡張機能の公開
description: カスタム拡張機能の公開
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 1236
ht-degree: 1%

---

# カスタム拡張機能の公開

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

拡張機能がFusionで実行されるのは、お客様の組織に&#x200B;**ビルド**、**デプロイ**、**承認済み**&#x200B;の後だけです。 このページの手順では、拡張機能を公開する方法と結果を検証する方法について説明します。

この情報は、Adobeの公式ドキュメントに適合しており、Workfront Fusionに特に適用されます。 Adobeの一般的な情報については、Adobe ドキュメントの[UI拡張機能の開発フロー](https://developer.adobe.com/uix/docs/guides/development-flow/)および[UI拡張機能の管理](https://developer.adobe.com/uix/docs/guides/publication/)を参照してください。

## ワークスペース

すべてのApp Builder プロジェクトには、**ステージ**&#x200B;と&#x200B;**実稼動** ワークスペースがあります。 それらを環境と考えてください。

* **ステージ**&#x200B;は開発とテスト用です。 イテレーション中にここにデプロイします。 承認は必要なく、結果は以下に説明するステージテストスイッチ（またはローカルプレビュー）を通じてのみ表示されます。
* **本番**&#x200B;は、全員にリリースするためのものです。 実稼動環境にデプロイした後、**承認リクエスト**&#x200B;を送信し、承認されると、拡張機能はAdobe App Registryに登録され、組織全体に表示されます。

>[!NOTE]
>
> **役割：**&#x200B;を作成およびデプロイするには&#x200B;**開発者**&#x200B;の役割が必要です。パブリッシュに承認要求を送信するには、**システム管理者**&#x200B;の役割が必要です。
>詳しくは、以下を参照してください。
>
> * [UI拡張機能ツールとアカウントを設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)
> * Adobe ドキュメントの[&#x200B; アクセスを取得する方法](https://developer.adobe.com/uix/docs/guides/get-access/)。

デフォルトでは、Fusionには&#x200B;**公開済み**&#x200B;の拡張機能のみが表示されます。 これらは、**実稼動** ワークスペースにデプロイしてから、**承認**&#x200B;用に送信した拡張機能です。 これは安全なデフォルトであるため、作業中のデプロイが組織全体に誤って表示されることはありません。

**ステージ** ワークスペースへのデプロイは公開されないので、Fusionに表示されません。 拡張機能を公開する前に、次の2つの方法で試すことができます。

* **ローカルで**&#x200B;を`aio app run`と共にプレビューします（[Adobe ドキュメントのUI拡張機能のローカルプレビュー](https://developer.adobe.com/uix/docs/guides/preview-extension-locally/)を参照）。 何も展開されず、見るだけです。
* **Fusion プロファイルでユーザーごとのテストスイッチをオンにして、Fusion**&#x200B;内のステージから読み込みます。 これは、この記事の[Fusionでのステージビルドのテスト &#x200B;](#test-a-stage-build-in-fusion)で説明します。

## Fusionでのステージビルドのテスト

このフローを使用して、公開する前にFusion内でステージのデプロイを確認します。

### 手順1：ステージワークスペースの選択

```sh
aio console where                  # shows current org / project / workspace
aio console workspace select       # choose Stage
```

### ステップ 2：構築

```sh
aio app build
```

これにより、フロントエンドがコンパイルされ、メタデータフックが実行されます（これにより`app-metadata.json`が生成されます）。 報告されたエラーを修正してから続行します。

### 手順3：デプロイ

```sh
aio app deploy
```

`deploy`は次の2つの操作を行います。

* **Adobeのコンテンツ配信ネットワーク上で`https://<project>-stage.adobeio-static.net`のようなURLでUI**&#x200B;をホストします。 この&#x200B;**拡張エンドポイント URL**&#x200B;は、完了時にCLIによって印刷されます。 これは、URL Fusionがiframeに読み込まれます。
* **拡張機能のエンドポイント**&#x200B;をステージワークスペースの拡張ポイント （`fusion/nav-organization/1`）に登録します。

>[!TIP]
>
> **展開が「拡張ポイント &#39;fusion/nav-organization/1&#39;が存在しません」で失敗した場合（エラー1060）:** Fusion拡張ポイントは、組織ではまだ有効になっていません。 これはオンボーディングステップであり、コードの間違いではありません。
>詳しくは、トラブルシューティング記事の「[拡張ポイントが存在しない](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md#error-1060-extension-point-does-not-exist)」を参照してください。

### 手順4:Fusion プロファイルでステージテストを有効にする

Fusionは、ユーザーごとにオプトインした場合にのみステージング拡張機能を読み込みます。

1. 展開した&#x200B;**同じ組織**&#x200B;のアカウントでFusionにログインします。
1. 上隅のユーザーアバターメニューを開き、**製品設定** > **Fusion プロファイル** > **環境設定**&#x200B;に移動します。
1. **ステージング拡張機能** スイッチをオンにします。

   Fusionでリロードを求めるプロンプトが表示されます。
1. リロードを確認します。

リロード後、Fusionは公開されたセットではなくステージワークスペースからエクステンションを読み込み、ナビゲーション内の各&#x200B;**（ステージ）**&#x200B;にラベルを付けて区別できるようにします。

このスイッチは、組織設定ではなく、ブラウザーに保存されている個人用テスト設定です。 公開した拡張機能に戻るには、これをオフにして再読み込みします。 ローカルに保存されているため、別のブラウザーやコンピューターには移動しません。

### 手順5:Fusionでの確認

1. 拡張機能ポイントに一致するセクションを開きます。
   * `fusion/nav-organization/1`→左ナビゲーションの&#x200B;**組織**&#x200B;領域に移動します。
   * `fusion/nav-team/1`→**チーム**&#x200B;領域に移動します（最初にチームを選択してください）。

   `getWidget()`で設定したタイトルのボタンが表示され、**（ステージ）**&#x200B;とマークされます。
1. 表示されたボタンをクリックします。

UIが読み込まれ、[Fusion コンテキスト &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)が受け取られます。

ボタンが表示されない場合、またはパネルにエラーが表示される場合は、[&#x200B; トラブルシューティング &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)を参照してください。

## 実稼動環境でのリリース

拡張機能がステージで動作し、すべてのユーザーの準備が整ったら：

### 手順1：実稼動ワークスペースへの切り替え

```sh
aio console workspace select       # choose Production
```

CLIで`.env` ファイルに関するプロンプトが表示されたら、**結合**&#x200B;を選択して、環境変数を保持します。

### 手順2：ビルドと実稼動環境へのデプロイ

```sh
aio app build
aio app deploy
```

### 手順3：承認リクエストの送信

公開は、実稼動ワークスペース **から送信された**&#x200B;承認要求です。

1. [Adobe Developer Console](https://developer.adobe.com/console)を開き、**組織**&#x200B;を選択し、**プロジェクト**&#x200B;を開き、**実稼動** ワークスペースに切り替えます。
1. アプリを&#x200B;**承認/公開**&#x200B;用に送信します（これには&#x200B;**システム管理者**&#x200B;の役割が必要です）。
1. 承認後、拡張機能が&#x200B;**Adobe App Registry**&#x200B;に追加され、Fusionを含む[Adobe Experience Cloud](https://experience.adobe.com)全体で使用できるようになります。

詳しい手順については、Adobe Developer ドキュメントの[UI Extensions Management](https://developer.adobe.com/uix/docs/guides/publication/)を参照してください。

## ステータスと更新

いくつかの行動は知る価値があるので、「何かが間違っている」とは別に「まだ取り組んでいる」と言うことができます。

* 実稼動環境にデプロイされた&#x200B;**は、表示可能な状態と同じではありません。** 実稼動用に`aio app deploy`がアプリをアップロードしますが、拡張機能が表示されません。 承認リクエストが送信され、承認された後にのみ表示されます。 実稼動環境にデプロイしてもFusionに表示されない場合、通常の理由は、まだ承認されていないことです。
* **コードのみの更新には、新しい承認は必要ありません。** 拡張機能が既に公開されていて、そのコード（UIまたはランタイムアクション）のみを変更する場合は、次のようにして同じURLに再デプロイします。

  ```sh
  aio app deploy --force-deploy
  ```

  次回に拡張機能を開いたときに、新しいバージョンが表示されます。 インストールするものはありません。 新しい拡張ポイントの追加や`getWidget()`広告の変更など、**登録**&#x200B;自体を変更する場合にのみ、新しい承認リクエストを送信する必要があります。
* **失効または取り消された拡張機能が表示されなくなります。** 拡張機能が失効または取り消された場合、エラーメッセージなしでFusionに表示されなくなります。 以前に動作していた拡張機能が全員に表示されない場合は、コードの問題を検索する前に、それが失効したかどうかを確認します。

## 拡張機能の削除（取り消し）

公開された拡張機能の削除は、Adobe Exchangeで&#x200B;**無効化**&#x200B;することによって実行されます。

1. **Adobe Exchange**&#x200B;にログインします。
1. **管理** > **App Builder アプリ**&#x200B;に移動します。
1. 削除する拡張機能の横にある「**失効**」を選択し、確認します。

取り消し後、拡張機能はExtension Managerに&#x200B;*失効* ステータスを表示し、Fusionには表示されなくなります。 完全に削除するには、Developer Consoleでプロジェクトを削除します。 プロジェクトは、拡張機能が失効するまで削除できません。

ステージングのみのテストデプロイメントの場合、デプロイメントを削除するには、次の手順を実行します。

```sh
aio app undeploy
```

## 追加のリソース

Adobeのドキュメントでは、次のリソースを使用できます。

* [UI拡張機能の開発フロー](https://developer.adobe.com/uix/docs/guides/development-flow/)
* [UI拡張機能の管理（公開/承認/取り消し）](https://developer.adobe.com/uix/docs/guides/publication/)
* [Developer Consoleでのプロジェクトの作成](https://developer.adobe.com/uix/docs/guides/creating-project-in-dev-console/)
* [アクセス方法（役割）](https://developer.adobe.com/uix/docs/guides/get-access/)
* [UI拡張機能のローカルプレビュー](https://developer.adobe.com/uix/docs/guides/preview-extension-locally/)
