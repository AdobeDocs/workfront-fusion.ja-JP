---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 拡張機能からのWorkfrontおよびFusion APIの呼び出し
description: 拡張機能からのWorkfrontおよびFusion APIの呼び出し
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
source-wordcount: 1083
ht-degree: 0%

---


# 拡張機能からのWorkfrontおよびFusion APIの呼び出し

>[!NOTE]
>
>この記事は、ソフトウェア開発ツールに精通していることを前提としています。

FusionのコンテキストリファレンスはサインインユーザーのIMS トークンを提供するので、次の自然なステップはWorkfrontまたはFusion APIを呼び出して実際のデータを表示することです。 これはCORSが原因で不可能です。 この記事では、App Builder ランタイムアクションをサーバーサイドプロキシとして使用して、その制限を回避する方法を説明します。また、例（イベントサブスクリプションダッシュボード）を含みます。

## ダイレクトブラウザーコール（CORS）が失敗する理由

表示されるUIは、AdobeのCDN （`https://<your-app>.adobeio-static.net`）から提供される`<iframe>`で実行されます。 そのページが&#x200B;**different** オリジン上のWorkfrontまたはFusion APIに`fetch(...)`を実行すると、ブラウザーはクロスオリジン リソース共有（CORS）を適用します。 APIがCDN オリジンに対して`Access-Control-Allow-Origin`を明示的に返さない限り、ブラウザーは応答をブロックします。 これらのAPIは任意の拡張機能のオリジンを許可リストに加えるしないので、ゲストからのダイレクトコールは失敗します。

CORSについて詳しくは、[CORS](https://developer.mozilla.org/docs/Web/HTTP/CORS)を参照してください。

## CORSなしで独自のランタイムアクションを呼び出す

この場合の修正は、CORSを使用せずに独自のランタイムアクションを呼び出すことです。

App Builder アプリケーションには、Adobe I/O Runtimeでサーバーサイドで実行される小さなサーバーレス関数であるランタイムアクションが含まれます。 サーバー間の呼び出しは、ブラウザーのCORSの対象ではありません。 また、アクションはアプリの一部であるため、ゲストは相対URLで呼び出すことができますが、これは同一生成元であり、ブロックされません。

```
  Guest UI (browser, adobeio-static.net)
     │  fetch('/api/v1/web/<app>/wf-proxy?...')   ← relative = same-origin, no CORS
     ▼
  Your runtime action  (Adobe I/O Runtime, server-side)
     │  fetch('https://fusion.adobe.com/api/v3/...')  ← server-to-server, no CORS
     ▼
  Workfront / Fusion API
```

アクションは、ユーザーのIMS トークンをゲストから受け取り、アップストリームに転送するため、ユーザーの代わりに呼び出しが許可を得て実行されます。

## 手順1：アクションの宣言

ランタイムアクションは、拡張機能の`runtimeManifest`の下の`app.config.yaml`で宣言されます。 拡張機能の横に`wf-proxy` アクションを追加します。

```yaml
extensions:
  fusion/nav-organization/1:
    $include: src/fusion-nav-organization-1/ext.config.yaml
    runtimeManifest:
      packages:
        fusion-uix-guest:                # ← your package name; part of the action URL
          license: Apache-2.0
          actions:
            wf-proxy:
              function: src/fusion-nav-organization-1/actions/wf-proxy/index.js
              web: 'yes'                  # exposes it at /api/v1/web/<package>/wf-proxy
              runtime: nodejs:22
              inputs:
                LOG_LEVEL: debug
              annotations:
                require-adobe-auth: false # see note below
                final: true
```

アクションは、次の場所で到達できるようになります。

```
/api/v1/web/<package>/<action>     e.g.  /api/v1/web/fusion-uix-guest/wf-proxy
```

### `require-adobe-auth`: true対false

この注釈は、アクションの実行前にAdobe ゲートウェイがIMS トークンを検証するかどうかを制御します。

* **`true`:**&#x200B;安全なデフォルトです。  ゲートウェイは、未認証の呼び出しを拒否します。 ただし、バリデーターは想定するヘッダーに厳格であり、リクエストを拒否したり、アップストリーム呼び出しに必要なカスタムヘッダーをドロップしたりできます。 その場合、トークンは有効ですが、`401`として表示されます。
* **`false`:** ゲートウェイ チェックをスキップします。 その後、あなたのアクションは公に呼び出すことができるため、**自分で認証を強制する必要があります**。 アクションに`Authorization`人のベアラーを必要とし、欠けている場合は却下してから、WorkfrontとFusionが検証するアップストリームに転送します。 手順2で説明した厳格なターゲット許可リストと組み合わせると、カスタムヘッダーを渡す必要があるプロキシの信頼性の高いパスになります。

>[!TIP]
>
> 最初に`true`をお試しください。 トークンが有効で、他の場所で機能するので説明できない`401`が表示された場合は、`false` **および**&#x200B;に切り替えて、ベアラーのチェックと移動を許可リストに加えるし、セキュリティが上流で適用されるようにします。

## 手順2:許可リストに加えるしたプロキシのアクションの記述

`src/fusion-nav-organization-1/actions/wf-proxy/index.js`を作成します。 2つのルールにより、アクションをオープンリレーとして使用できないようにアップストリームターゲットを許可リストに加えるし、アップストリームに転送される必要なベアラートークンを設定します。

```js
const fetch = require('node-fetch')
const { Core } = require('@adobe/aio-sdk')
const { errorResponse, getBearerToken, checkMissingRequestInputs } = require('../utils')

// Page-through query params (see "Paginate list results" below).
const pageQuery = (p) => {
  const q = new URLSearchParams()
  if (p.start != null) q.set('start', p.start)
  if (p.limit != null) q.set('limit', p.limit)
  return q
}

// Only these upstreams may be reached. Never build the URL from arbitrary input.
const TARGETS = {
  subscriptions: {
    method: 'GET',
    url: () => 'https://<your-wf-host>/attask/eventsubscription/api/v1/subscriptions',
  },
  hooks: {
    method: 'GET',
    // Fusion hooks are team-scoped: teamId is a REQUIRED query param (see below).
    url: (p) => {
      const q = pageQuery(p)
      if (p.teamId) q.set('teamId', p.teamId)
      return `https://fusion.adobe.com/api/v3/hooks?${q.toString()}`
    },
  },
  scenarios: {
    method: 'GET',
    url: (p) => {
      const q = pageQuery(p)
      if (p.fusionOrgId) q.set('organizationId', p.fusionOrgId)
      return `https://fusion.adobe.com/api/v3/scenarios?${q.toString()}`
    },
  },
}

async function main (params) {
  const logger = Core.Logger('main', { level: params.LOG_LEVEL || 'info' })
  try {
    const missing = checkMissingRequestInputs(params, ['target'], ['Authorization'])
    if (missing) return errorResponse(400, missing, logger)

    const target = TARGETS[params.target]
    if (!target) return errorResponse(400, `unknown target '${params.target}'`, logger)

    const token = getBearerToken(params)              // reads params.__ow_headers.authorization
    const headers = { authorization: `Bearer ${token}`, 'content-type': 'application/json' }
    if (params.orgId) headers['x-gw-ims-org-id'] = params.orgId        // Adobe IMS org id
    if (params.fusionOrgId) headers['x-organization-id'] = params.fusionOrgId  // Fusion tenant id
    if (params.teamId) headers['x-team-id'] = params.teamId            // Fusion team id

    const res = await fetch(target.url(params), { method: target.method, headers })
    const text = await res.text()
    let body
    try { body = JSON.parse(text) } catch (e) { body = text }

    if (!res.ok) {
      return { statusCode: res.status, body: { error: `upstream ${res.status}`, target: params.target, details: body } }
    }
    return { statusCode: 200, body }
  } catch (error) {
    logger.error(error)
    return errorResponse(500, 'server error: ' + error.message, logger)
  }
}

exports.main = main
```

`getBearerToken`、`errorResponse`および`checkMissingRequestInputs`は、生成された`actions/utils.js`から取得され、テンプレートによって基礎モードが設定されます。 `getBearerToken`は`params.__ow_headers.authorization`を読み取ります。これは、ゲートウェイが受信`Authorization` ヘッダーを入力する場所です。

## ステップ 3：ゲストからアクションを呼び出す

UIから、相対（同一生成元） URLを持つアクションを`fetch`し、IMS トークンをベアラーとして送信します。 アップストリームが必要とする組織とチーム IDをクエリパラメーターとして渡します。

```js
const PROXY_URL = "/api/v1/web/fusion-uix-guest/wf-proxy";

async function callProxy(target, token, { imsOrgId, fusionOrgId, teamId, start, limit } = {}) {
  const params = new URLSearchParams({ target });
  if (imsOrgId) params.set("orgId", imsOrgId);          // → x-gw-ims-org-id
  if (fusionOrgId) params.set("fusionOrgId", fusionOrgId); // → x-organization-id
  if (teamId) params.set("teamId", teamId);             // → x-team-id
  if (start != null) params.set("start", start);        // pagination offset
  if (limit != null) params.set("limit", limit);        // pagination page size
  const res = await fetch(`${PROXY_URL}?${params.toString()}`, {
    headers: { authorization: `Bearer ${token}` },
  });
  if (!res.ok) throw new Error(`${target} request failed: ${res.status}`);
  return res.json();
}
```

コンテキストから`token`、`imsOrgId`、`fusionOrgId`および`teamId`を取得します。

```js
const token       = connection.sharedContext.get("imsToken");
const imsOrgId    = connection.sharedContext.get("imsOrgId");
const fusionOrgId = connection.sharedContext.get("organization")?.id; // Fusion tenant id
const teamId      = connection.sharedContext.get("team")?.id;
```

コンテキストについて詳しくは、[Fusionのコンテキストリファレンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)を参照してください。

## Fusion v3 APIの詳細

`https://fusion.adobe.com/api/v3`に対するダッシュボードの機能：

| ヘッダー/パラメーター | 値 | メモ |
| ---------------- | ------- | ------- |
| `Authorization` | `Bearer <imsToken>` | コンテキストからのユーザーのIMS トークン。 |
| `x-organization-id` | `organization.id` | IMS組織IDではなく、Fusion独自のテナント IDを使用します。 Fusionはこれによりテナントを識別します。 |
| `x-team-id` | `team.id` | 通話がチームスコープの場合に送信します。 |
| `x-gw-ims-org-id` | `imsOrgId` | ゲートウェイのAdobe IMS組織ID。 |

次の注意事項に注意してください。

* **`GET /api/v3/hooks`はチーム スコープです：** `teamId`は&#x200B;**必須のクエリ パラメーター** （`/api/v3/hooks?teamId=...`）です。 これがないと、`400`が表示されます。 つまり、*アクティブなチームのみ*&#x200B;のフックが返され、組織をカバーし、チームをループして結合します。
* **`GET /api/v3/scenarios`**&#x200B;は`organizationId` （`/api/v3/scenarios?organizationId=...`）で動作します。

>[!NOTE]
>
> 正式なリファレンスは、Adobeの[Workfront Fusion API](https://developer.adobe.com/workfront-fusion-apis/)です。 ヘッダー/認証要件はゲートウェイによって異なります。 この表は、デモで実際に必要な情報を示しています。 呼び出しが`401`/`400`を返した場合は、まずこれらのヘッダーを再確認してください。

## リストの結果をページネーション

Fusion v3 リストエンドポイント（フック、シナリオ）は、セット全体ではなく、一度に1つの&#x200B;**ページ**&#x200B;を返します。 応答は次のようになります。

```json
{
  "items": [ /* ...this page of records... */ ],
  "_page": { "start": 0, "limit": 100, "total": 342 }
}
```

レコードは&#x200B;**`items`**&#x200B;未満で、ページネーション メタデータは&#x200B;**`_page`**&#x200B;未満です。 **`start`** （オフセット）および&#x200B;**`limit`** （ページサイズ）クエリパラメーターを使用してページを作成します。 上記のプロキシは両方を通過するので、すべてを収集するまでループしてゲストのページを作成します。

```js
const PAGE_LIMIT = 100;

async function fetchAllPages(target, token, opts = {}) {
  const all = [];
  let start = 0;
  // Stop when a page returns fewer than PAGE_LIMIT items, or when _page.total is reached.
  for (;;) {
    const res = await callProxy(target, token, { ...opts, start, limit: PAGE_LIMIT });
    const items = res.items ?? [];
    all.push(...items);

    const total = res._page?.total;
    const done = items.length < PAGE_LIMIT || (total != null && all.length >= total);
    if (done) break;
    start += PAGE_LIMIT;
  }
  return all;
}
```

ブラウザーからページングを維持する場合は、ランタイムアクション内で同じループを実行し、1つの応答で結合された`items`配列を返します。 いずれにしても、最初のページが結果セット全体であると仮定しないでください。 複数のページのフックを持つチームは、そうでない場合、シナリオが欠落しているように見えます。

## セキュリティチェックリスト

* **上流を許可リストに加えるします。** 生のクライアント入力からターゲット URLを作成しないでください。 手順2に従って、短い`target` キーを固定URLにマッピングします。 これにより、あなたの行動がオープンなリレーになるのを防ぎます。
* **アクションでベアラートークン**&#x200B;を要求し、アップストリームに転送します。 WorkfrontとFusionがユーザーの権限を適用します。
* **トークンを記録しません。** `imsToken`は資格情報です。 `LOG_LEVEL`さんが`stringParameters`さんの印刷物に注意してください。
* **信頼できるAdobeおよびWorkfront ホストに転送できるのは、HTTPS**&#x200B;経由のみです。

## 動作した例：イベント購読ダッシュボード

デモダッシュボードは、3つのソースを結合して、一致するFusion シナリオが正常かどうかをWorkfront イベントサブスクリプションごとに示します。

1. `fetchSubscriptions()` → Workfront イベント サブスクリプション （受信/渡されたカウンターあり）。
1. アクティブなチームの`fetchHooks(teamId)` → Fusion フック（`fetchAllPages`でページ化）。
1. `fetchScenarios(fusionOrgId)`→組織のFusion シナリオ （`fetchAllPages`でページ化）。

**join**&#x200B;は、それらを連鎖していますが、注意する価値のあるキャッチがあります。Workfront サブスクリプションとFusion フックは、**の異なるホスト**&#x200B;でライブを指しているので、URL フィールドがバイト単位で等しくありません。 安定しているのは、Webhook URL **（最後のパスセグメント）の最後にある** トークンです。 完全なURLではなく、末尾のトークンで一致させます。 フックの`scenarioId`は、シナリオの`id`と一致します。

```
subscription.targetUrl  ──(trailing token)──▶  hook.url
                                                hook.scenarioId  ──▶  scenario.id
```

```js
// Reduce a webhook URL to its trailing token so hosts/bases can differ.
function hookKey(url) {
  if (!url) return "";
  const path = String(url).trim().toLowerCase().split(/[?#]/)[0].replace(/\/+$/, "");
  const i = path.lastIndexOf("/");
  return i >= 0 ? path.slice(i + 1) : path;
}

// Index hooks by token, then look each subscription up by the same token.
const hooksByToken = new Map(hooks.map((h) => [hookKey(pick(h, ["url", "address", "targetUrl"], "")), h]));
const hook = hooksByToken.get(hookKey(pick(sub, ["url", "endpointUrl", "targetUrl", "target.url", "callbackUrl"], "")));
```

ステータスは、結合から派生します。

* **破損**：一致するフックがないか、フックが`gone`です。
* **フィルタリング**：一致していますが、`passed < received` （イベントは到着しますが、シナリオが実行される前にフィルタリングされます）。
* **正常**：一致して渡しています。

実際のペイロードのシェイプは異なるため、クライアントはフィールドを防御的にマッピングし、フィールドごとに複数の候補キーを試すため、わずかなAPIの違いによってテーブルが壊れることはありません。

```js
function pick(obj, keys, fallback) {
  for (const key of keys) {
    const value = key.split(".").reduce((acc, part) => (acc == null ? acc : acc[part]), obj);
    if (value != null) return value;
  }
  return fallback;
}
```

例をいくつか紹介します。 同じプロキシパターンが、必要なWorkfrontまたはFusion APIでも機能します。
