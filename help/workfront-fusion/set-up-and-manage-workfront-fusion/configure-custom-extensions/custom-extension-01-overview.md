---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: UI拡張機能の概要
description: Workfront Fusionのカスタム拡張機能
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
source-wordcount: 835
ht-degree: 0%

---

# UI拡張機能の概要

UI拡張性を使用すると、カスタムロジックとUI （ユーザーインターフェイス）をAdobe Workfront Fusionに取り込むことができます。 Adobe App Builderを利用すれば、組織のWorkfront Fusion エクスペリエンスを変更して、組織のニーズにより的確に対応しながら、Fusionのコア機能にも依存させることができます。

この記事では、UI拡張機能の概要と、カスタム拡張機能とWorkfront Fusionとのコミュニケーション方法について説明します。

## 拡張機能の構造

* [ホストとゲスト](#hosts-and-guests)
* [基盤となるテクノロジー](#the-technology-underneath)

### ホストとゲスト

Fusionでは、Workfront Fusion チームが作成しなかったUIを表示できます。 これらのUIの変更がFusionのコア機能に影響を与えないようにするために、UIはFusionのコードとは完全に別の独立したブラウザーフレーム（`<iframe>`）で実行されます。

* **ホスト**: *に拡張機能が*&#x200B;含まれているアプリケーション。 これは&#x200B;**Fusion**&#x200B;です。 ホストは、拡張機能を表示できる場所と、拡張機能と共有するデータを決定します。
* **ゲスト**: *あなたの*&#x200B;拡張機能。 ホストがiframeに読み込む小さなweb アプリケーションです。

UI拡張機能を作成する場合、Fusionは変更されません。 ゲストを作成して公開し、ゲストが公開された後にFusionで使用できます。

### 基盤となるテクノロジー

お客様のゲストは、次の2つのAdobe テクノロジで構築されています。

* **Adobe App Builder**：小さなweb アプリとサーバーレスアクション用の無料のホスティングおよびツール プラットフォームです。 あなたの拡張機能はApp Builderアプリです。 App Builderでは、（Adobeの`*.adobeio-static.net` コンテンツ配信ネットワーク上で） UIをホストする場所と、`aio`というコマンドラインツールを使用して、作成、構築、公開できます。
* **Adobe UI Extensibility SDK （UIX）**: ホストとゲストが話し合うライブラリ。 1つのパッケージ `@adobe/uix-guest`を使用します。 Fusionは、一致する`@adobe/uix-host` パッケージをサイドで使用します。

<!--

```
   ┌────────── Browser ─────────────────────────────┐
   │                                                                   │
   │   Fusion (Host)                      Your extension (Guest)       │
   │   ────────────                       ─────────────────────        │
   │   @adobe/uix-host   ◀── messages ──▶  @adobe/uix-guest            │
   │        │                                    │                     │
   │   renders an iframe ───────────────▶  your React/HTML UI          │
   │                                                                   │
   └───────────────────────────────────────────────────────────────────┘

   Your UI files are hosted by Adobe App Builder at
   https://<your-app>.adobeio-static.net
```

-->

## 拡張ポイント

拡張ポイントは、ゲストを表示できるホスト内の「スロット」という名前です。 Fusionがそのスロットを定義し、ゲストがどのスロットを使用するかを選択します。

拡張ポイント名には3つの部分があります：`service/name/version`。

Fusionには、次の拡張ポイントがあります。

| 拡張ポイント | UIがFusionに表示される場所 | 利用するタイミング |
| --- | --- | ---- |
| `fusion/nav-organization/1` | 左側のナビゲーションの&#x200B;**組織** セクションの下にあります。 | ツールは組織全体を把握するためのものです。 |
| `fusion/nav-team/1` | 左側のナビゲーションの「**チーム**」セクション（チームが選択されている場合に表示）の下。 | 特定のチームを対象としたツールです。 |

* `fusion`は&#x200B;**サービス** （製品、Fusion）です。
* `nav-organization` / `nav-team`は&#x200B;**name** （特定のスロット）です。
* `1`は&#x200B;**バージョン**&#x200B;です。

1つの拡張機能は、1つまたは両方の拡張機能ポイントを実装できます。 ほとんどの拡張機能は1 ポイントを使用しています。

選択した拡張機能ポイントに基づいて、Fusionは対応するナビゲーションセクションに拡張機能のタイトルを含むボタンを追加します。 クリックすると、Fusionのメインコンテンツ領域に専用ページが開き、そこにUIが読み込まれます。

## UI拡張機能に含まれるフレーム

>[!IMPORTANT]
>
>この節では、混乱を引き起こす可能性のあるUI拡張機能の側面について説明します。 注意深く読むことをお勧めします。

Fusionがゲストを読み込むと、拡張機能が&#x200B;**2** フレームで実行されます。

1. **登録枠（非表示）。** 最初に、バックグラウンドで実行します。 登録フレームは、拡張機能が提供するものをFusionに伝えます。 例えば、ダッシュボードウィジェットがあることを示し、ウィジェットのタイトルとUIのURLを送信します。 登録フレームは、`register(...)`を呼び出すことによってこれを行います。 表示されるUIはレンダリングされません。
1. **UI フレーム （表示）。** これは、Adobe Workfront Fusionでユーザーに表示されるページです。 `attach(...)`を呼び出して、ホストに通知する必要があります。 `attach`が呼び出されない場合、Fusionは待機し、最終的にエラーでタイムアウトします。

>[!BEGINSHADEBOX]

この例では、ユーザーが拡張機能ボタンをクリックした場合のフローを示します。

1. ボタンがクリックされます。
1. Fusionが登録フレーム（非表示）を読み込みます。

   ```
   register({ methods: { dashboard: { getWidget() {...} } } })
   ```

   `getWidget()`は、表示されたUIのURLを返します
1. Fusionは、そのURLにUI フレーム（表示）を読み込みます。

   ```
   attach({ id }) 
   ```

   これが必要です。または、Fusionがタイムアウトします
1. Fusionがコンテキストを送信し、UIがレンダリングされます。

>[!ENDSHADEBOX]

UIの構築時には、両方のフレームが書き込まれます。 重要なことは、表示されるページ **は**&#x200B;が`attach`を呼び出さなければならないことを覚えておくことです。

UIの構築について詳しくは、[&#x200B; カスタム拡張機能UIの構築](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)を参照してください。

## Fusionからのコンテキスト

拡張機能を添付した後、Fusionはゲストと`context` オブジェクトを共有します。 次が含まれます。

* **User**：サインインしているユーザーのFusion プロファイルとAdobe IMSユーザーID。
* **組織**: アクティブな組織の完全なFusion組織レコードとAdobe IMS組織ID。
* **チーム**：アクティブなチーム（該当する場合）。
* **Adobe IMSアクセストークン**：これにより、必要に応じて、ユーザーに代わってAdobeまたはFusion APIが呼び出されます。

Adobe Workfront Fusionはアップデートもプッシュします。 たとえば、UIを開いているときにユーザーが組織やチームを切り替えた場合、UIが即座に反応できるように、Fusionは新しいコンテキストを送信します。

コンテキストフィールドの完全なリストについては、[Fusion コンテキストリファレンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)を参照してください。

## UI拡張機能の作成

UI拡張機能を作成するには、次の手順に従います。

1. [&#x200B; ツールをインストールして、Adobe プロジェクトを作成](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)。
1. [空のApp Builder プロジェクトを生成し、Fusion拡張機能ポイントに指定して、ウィジェットを登録します](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)。
1. [UIを作成し、Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)に接続します。
1. [Fusionが送信するコンテキストを使用](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)。
1. [Fusionが見つけられるように公開](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)。
1. （オプション） [CORS](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)を使用せずに、Workfront/Fusion APIを呼び出して実際のデータを取得します。

プロセスを開始するには、[&#x200B; ツールとAdobe アカウントの設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)に移動します。


