---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: カスタム拡張機能のトラブルシューティング
description: カスタム拡張機能のトラブルシューティング
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
source-wordcount: 1136
ht-degree: 0%

---


# カスタム拡張機能のトラブルシューティング

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

この記事では、カスタム拡張機能を作成する際に発生する可能性が最も高い問題に対する解決策を、開発中に発生する順序で紹介します。

## クイックチェックリスト

何か機能しない場合は、まずこれらを確認してください。

* Node.jsはバージョン 18または20 （`node --version`）です。
* （`aio login`）で正しい組織/プロジェクト/ワークスペース （`aio console where`）にサインインしています。
* 拡張ポイント名は、バージョン `fusion/nav-organization/1`を含め、正確に一致します。
* `getWidget()`の`url`は、アプリのルートと一致します。
* 表示されているUIから`attach({ id })`が呼び出されます。
* Fusionで適切な拡張機能セットを確認します。
  * ステージのビルドを確認するには、ステージにデプロイし、Fusion プロファイルのステージ拡張機能スイッチをオンにします（製品設定/Fusion プロファイル/環境設定）。
  * 公開された拡張機能を確認するには、実稼動環境にデプロイして承認を得ます。

## エラー1060: 「拡張ポイントが存在しません」

**完全メッセージ：** `CoreConsoleAPISDK ... 1060: Extension point 'fusion/nav-organization/1' does not exist` （`aio app deploy`中）

**意味：** Fusion拡張ポイントは、お使いのAdobe組織に対してまだ有効になっていません（「オンボーディング」）。 Adobeは、デプロイ時に、拡張ポイントが組織のカタログに存在することを検証します。 これは、コードまたはYAMLに関する問題として&#x200B;**not**&#x200B;です。

**修正：** Fusion チームに、IMS組織の拡張ポイント （`fusion/nav-organization/1`または`fusion/nav-team/1`）のオンボーディングを依頼します。 オンボーディングをリクエストする際には、以下を含めます。

* **IMS組織id** （`XXXX@AdobeOrg`）、
* 必要な&#x200B;**拡張ポイント**,
* **Developer Console プロジェクトとワークスペース**&#x200B;の名前。

オンボーディングが確認されたら、`aio app deploy`を再実行します。


## &quot;Awaiting initial message from target iframe&quot; / パネルは永遠に回転します

**意味：** Fusionは表示されたUIを開きましたが、ハンドシェイクを完了しなかったため、Fusionがタイムアウトしました。

**一般的な原因：**

* `attach`は登録コンポーネント内にのみ存在し、表示ウィジェット内には存在しません。
* `getWidget()`の`url`は、ウィジェットの代わりに&#x200B;**登録** コンポーネント（または空白ページ）をレンダリングするルートを指しています。
* `attach`に渡された`id`は、`register`で使用されている`id`とは異なります。 これらは同じである必要があるので、両方を`Constants.js`に保持します。

**修正：** **visible** コンポーネントが`attach({ id })`を呼び出していることを確認します。

```jsx
useEffect(() => {
  attach({ id: extensionId }).catch(console.error);
}, []);
```

詳しくは、[&#x200B; カスタム拡張機能UIの作成](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)を参照してください。



## Fusionにナビゲーションボタンが表示されない

カスタム拡張機能のナビゲーションボタンがFusionに表示されない場合は、次の項目を順番に確認します。

1. **適切な拡張機能セットをお探しですか？** デフォルトでは、公開された拡張機能のみが表示され、実稼動環境にデプロイされ、承認されています。 ステージのビルドをテストする場合は、Fusion プロファイル（製品設定/Fusion プロファイル/環境設定）のステージ拡張機能スイッチをオンにしてリロードします。 ステージ項目には&#x200B;**（ステージ）**&#x200B;というラベルが付いています。
詳しくは、[&#x200B; カスタム拡張機能を公開](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)を参照してください。
1. **取り消されたか、取り消されたか？** 失効または取り消された拡張機能が、エラーなしでFusionに表示されなくなります。 以前に動作していたボタンが消えた場合は、コードの問題を探す前に、Adobe Exchangeで引き続きアクティブであることを確認します。
1. **正しいワークスペースにデプロイされていますか？** ステージテスト スイッチを使用しているときに、実際に読み込んでいるワークスペースであるステージワークスペースにデプロイします。
1. **正しい組織にデプロイされていますか？** デプロイ先の&#x200B;**same** IMS組織のアカウントでFusionにログインします。
1. **正しいセクションですか？** `fusion/nav-organization/1`は&#x200B;**組織**&#x200B;の下に表示され、`fusion/nav-team/1`は&#x200B;**チーム**&#x200B;の下に表示されます（最初にチームを選択する必要があります）。
1. **拡張機能ポイント名のタイプミスはありますか？** `app.config.yaml`とフォルダーの`ext.config.yaml`のインクルードパスの両方で正確に`fusion/nav-organization/1`を読み取る必要があります。


## ボタンが表示されますが、パネルは空白です

ボタンが表示されていてパネルが空白の場合は、次の点を確認します。

* **ルートの不一致：**、`getWidget()`の`url`、`/index.html#/my-widget`など）は`App.js`の`<Route>`と一致する必要があります。 不一致は、コンポーネントのないページを読み込みます。
* **JavaScript エラー：** ブラウザーの開発者向けツール （F12） > **コンソール** タブを開き、iframeからエラーが発生していないか探します。 報告されたエラーを修正し、再デプロイします。
* `getWidget()`の&#x200B;**ヘッダーが見つからないか、重複しています：** `hideWidgetHeader`が、FusionでUIの上にタイトルを表示するかどうかを制御します。 独自のヘッダーをレンダリングする場合は、`true`に設定します。

## iframeがブロックされています（コンテンツセキュリティポリシー/「フレーム拒否」）

Fusionでは、Adobeでホストされている拡張機能のみが許可されます。これは、`aio app deploy`がデフォルトでファイルを保存するApp Builder CDN （`*.adobeio-static.net`）です。 カスタムドメインなど、別の場所でUIをホストする場合、Fusionは読み込みを拒否します。 ドキュメントに従ってApp Builderを通じてデプロイするか、Fusion チームにドメインを許可リストに加えるできるかどうかを尋ねます。

## コンテキストが空または古い

* **読み込み直後に空です：** コンテキストを読み取る&#x200B;**後** `attach`解決します。前ではありません。 それまでは、「接続…」状態を表示します。
* **ユーザーが組織またはチームを切り替える際に更新されない：** `contextchange` イベントを購読し、ハンドラー内のキーを再読します。 詳しくは、「カスタム拡張機能UIの構築」の記事の[Fusionのコンテキスト共有](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md#read-the-context-fusion-shares)を参照してください。
* **日付が間違っています：**&#x200B;日付フィールドは、`Date`個のオブジェクトではなく、ISO **文字列**&#x200B;として届きます。 `new Date(...)`でそれらをラップします。 Fusionのコンテキストリファレンスの記事の[日付](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md#dates)を参照してください。

## APIの呼び出しがCORS エラーで失敗する

**現象：** UIがWorkfront/Fusion APIを直接呼び出すと、ブラウザーコンソールに&#x200B;*「Access-Control-Allow-Origin」ヘッダーが表示されない（またはリクエストがブロックされる）*。

**修正：** ブラウザーからこれらのAPIを呼び出さないでください。 独自のApp Builder **ランタイムアクション** （サーバーサイド、CORSなし）を通じて呼び出しをルーティングし、ゲストが相対する同一オリジン URLを使用してアクションを呼び出すようにします。 詳しくは、[WorkfrontとFusion APIの呼び出し](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)を参照してください。


## 有効なトークンがある場合でも、プロキシアクションは401を返します

**意味：** `require-adobe-auth: true`では、Adobeのゲートウェイは、アクションが実行される前に呼び出しを検証し、それを拒否したり、アップストリームに必要なカスタムヘッダーをドロップしたりして、`401`として表示することができます。

**修正：** アクション **および**&#x200B;で`require-adobe-auth: false`を設定し、自分で認証を強制します。 `Authorization`人のベアラーを要求し、それを上流に転送し、厳格な目標許可リストに加えるを維持します。 [require-adobe-auth: true vs. false](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md#require-adobe-auth-true-vs-false)を参照してください。

## Fusion `GET /api/v3/hooks`は400を返します

**意味：** フック エンドポイントは&#x200B;**チーム スコープ**&#x200B;であるため、`teamId`は必須のクエリ パラメーターです。

**修正：** `/api/v3/hooks?teamId=<team.id>`への電話。 フックは、アクティブなチームでのみ返されます。 組織をカバーするには、チームをループ化して結合します。 シナリオは、対照的に、`organizationId`を受け入れます。 [Fusion v3 APIの詳細](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md#fusion-v3-api-specifics)を参照してください。


## `aio` のエラー

* **`aio: command not found`:** CLIがPATHにインストールされていないか、インストールされていません。 `npm install -g @adobe/aio-cli`を再実行してから、新しいターミナルを開きます。
* **まったく新しいノードバージョン**&#x200B;でビルド/デプロイに失敗しました。ノード **18または20 LTS**&#x200B;を使用してください。 非常に新しい非LTS リリースでは、ツールチェーンが壊れることがあります。
* **「You are not a developer」 / 組織を表示できません：** Adobeの組織管理者は、**Developer** ロールとApp Builder アクセスを許可する必要があります。 詳しくは、[UI拡張機能ツールとアカウントの設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)を参照してください。
* **401 / デプロイまたは発見中に無効なトークン：** セッションが期限切れになっているか、環境を混在しています。 `aio logout`を実行してから`aio login`を実行し、`aio console where`を確認して、読み込むワークスペースにデプロイします。

## サポート情報の収集

診断をより迅速にするために、次の情報を収集します。

* 実行した正確なコマンドと&#x200B;**full** エラー出力。
* お客様の&#x200B;**IMS組織ID**、**プロジェクト**、および&#x200B;**ワークスペース**。
* ターゲットにしている&#x200B;**拡張ポイント**。
* `aio app deploy`が成功したかどうか、および拡張機能が&#x200B;**公開**&#x200B;かどうか（またはステージテストの場合は、ステージング拡張機能スイッチがオンになっているかどうか）。
* Fusionでパネルを開くときに、ブラウザー&#x200B;**コンソール** （F12）でエラーが発生しました。
