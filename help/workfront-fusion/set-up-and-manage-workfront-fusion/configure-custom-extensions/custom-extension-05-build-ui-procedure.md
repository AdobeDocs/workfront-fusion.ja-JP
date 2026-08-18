---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: カスタム拡張機能UIの構築
description: カスタム拡張機能UIの構築
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 440
ht-degree: 0%

---


# カスタム拡張機能UIの構築

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

この手順では、ユーザーが実際に表示する画面を構築し、Fusionで&#x200B;**接続（「ハンドシェイク」）**&#x200B;を完了する方法について説明します。

このプロセスでは、拡張機能が、非表示の&#x200B;**登録** フレームと表示される&#x200B;**UI** フレームの2つのフレームで実行されていることを確認することが重要です。

カスタム拡張機能に関連するフレームについて詳しくは、[UI拡張機能に含まれるフレーム ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md#frames-included-in-a-ui-extension)を参照してください。

登録フレームの作成手順については、[UI拡張機能のプロジェクトの作成](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)を参照してください。

## 2つのフレーム間のルート

両方のフレームで同じ`index.html`が読み込まれます。小さなフロントエンドルーターが、URLに基づいて表示するコンポーネントを決定します。

1. `web-src/src/components/App.js`でルートを設定します。 重要な要素は次のとおりです。

   ```jsx
   import { HashRouter as Router, Routes, Route } from "react-router-dom";
   import ExtensionRegistration from "./ExtensionRegistration";
   import DashboardWidget from "./DashboardWidget";
   
   export default function App() {
     return (
       <Router>
         <Routes>
           {/* Background frame: registers the extension with Fusion */}
           <Route index element={<ExtensionRegistration />} />
           <Route path="index.html" element={<ExtensionRegistration />} />
   
           {/* Visible frame: the URL you returned from getWidget() */}
           <Route path="my-widget" element={<DashboardWidget />} />
         </Routes>
       </Router>
     );
   }
   ```

   これらのルートは、次のように以前の設定にマッピングされます。

   * 既定のルート （`index`）は、`register(...)`を呼び出す非表示フレーム **`ExtensionRegistration`**&#x200B;をレンダリングします。
   * `my-widget` ルートは、表示されるUIである&#x200B;**`DashboardWidget`**&#x200B;をレンダリングします。 これは、[前のページ ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)の`getWidget()`から返された`url: "/index.html#/my-widget"`と一致します。

   >[!NOTE]
   >
   > **ルートと`getWidget` URLは同意する必要があります。** ルート名を変更する場合は、`url`も変更するか、Fusionで空白ページが読み込まれます。

1. [引き続き`attach`](#complete-the-handshake-with-attach)でハンドシェイクを完了します。

## `attach`とのハンドシェイクを完了

これは、目に見えるUIで最も重要な行です。 FusionがUI フレームを開くと、そのフレームが「チェックイン」されるのを待ちます。 コードは`attach({ id })`を呼び出してチェックインします。

**これを省略すると、Fusionは**&#x200B;をタイムアウトし、「ターゲット iframeからの最初のメッセージを待っています」などのエラーが表示されます。**

1. 以下を`web-src/src/components/DashboardWidget.js`に追加します。

   ```jsx
   import { useEffect, useState } from "react";
   import { attach } from "@adobe/uix-guest";
   import { extensionId } from "./Constants";
   
   export default function DashboardWidget() {
     const [connection, setConnection] = useState(null);
   
     useEffect(() => {
       // Tell Fusion this UI frame is ready. Required.
       attach({ id: extensionId })
         .then(setConnection)
         .catch((e) => console.error("attach failed", e));
     }, []);
   
     if (!connection) {
       return <p>Connecting to Fusion...</p>;
     }
   
     return <h2>Hello from my Fusion extension!</h2>;
   }
   ```

   このコードでは、次の操作を行います。

   * `attach({ id })`は、Fusionが応答すると&#x200B;**接続オブジェクト**&#x200B;を返します。 これは、次の手順でFusionが送信するコンテキストを読み取るために使用するため、保存することをお勧めします。
   * 接続が解決するまで、短い「Connecting...」 メッセージが表示されます。
   * `Constants.js`で設定した&#x200B;**同じ`extensionId`**&#x200B;を使用します。

   この時点で、動作する拡張機能があります。これは、メッセージを登録、添付、表示します。 この後はすべて、Fusionが提供するデータの使用に関するものです。

1. 引き続き[Fusionのコンテキスト共有](#read-the-context-fusion-shares)を読みます。

## コンテクストを読むFusionの共有

接続を添付すると、現在のユーザー、組織、チームに関する情報を含む&#x200B;**共有コンテキスト**&#x200B;が接続に表示されます。 `connection.sharedContext.get("<key>")`を持つ個々の値を読み取ることができます：

```jsx
const orgId = connection.sharedContext.get("imsOrgId");
const organization = connection.sharedContext.get("organization"); // full Fusion org
const user = connection.sharedContext.get("user");                 // full Fusion user
```

次の例は、ユーザーが組織またはチームを切り替えた際にも更新される完全な事後対応の例を示しています。

```jsx
import { useEffect, useState } from "react";
import { attach } from "@adobe/uix-guest";
import { extensionId } from "./Constants";

const KEYS = ["imsOrgId", "imsUserId", "organization", "team", "user"];

function readContext(source) {
  // sharedContext behaves like a Map (.get); the change event gives a plain object.
  const get =
    typeof source.get === "function" ? (k) => source.get(k) : (k) => source[k];
  return Object.fromEntries(KEYS.map((k) => [k, get(k)]));
}

export default function DashboardWidget() {
  const [context, setContext] = useState(null);

  useEffect(() => {
    let cleanup = () => {};
    attach({ id: extensionId })
      .then((connection) => {
        // 1) initial values
        setContext(readContext(connection.sharedContext));

        // 2) react to org/team/user changes pushed by Fusion
        const onChange = (event) =>
          setContext(readContext(event?.detail?.context ?? connection.sharedContext));
        connection.addEventListener("contextchange", onChange);
        cleanup = () => connection.removeEventListener?.("contextchange", onChange);
      })
      .catch((e) => console.error("attach failed", e));
    return () => cleanup();
  }, []);

  if (!context) return <p>Connecting to Fusion...</p>;

  return (
    <div>
      <h2>{context.organization?.name ?? "No organization"}</h2>
      <p>Signed in as {context.user?.name} ({context.user?.email})</p>
      <p>IMS org: {context.imsOrgId}</p>
    </div>
  );
}
```

次の点に留意してください。

* **`attach`の直後に`connection.sharedContext.get(key)`から初期値**&#x200B;を読み取ります。
* **同期を維持するために`contextchange`**&#x200B;を購読します。 Fusionは、アクティブな組織、チーム、またはユーザーが変更されるたびに、このイベントを起動します。 新しい値は`event.detail.context`に到達します。

キーの完全なリストと各キーに含まれるものは、[Fusion コンテキスト リファレンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)に含まれています。

カスタム拡張機能の設定プロセスを続行するには、[Fusionのコンテキストリファレンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)に移動します。
