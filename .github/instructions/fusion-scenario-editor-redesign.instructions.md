---
applyTo: "help/workfront-fusion/**"
source-git-commit: e3e28f86494207dd5e674a2882887d00da6a0c61
workflow-type: tm+mt
source-wordcount: '2352'
ht-degree: 1%
---

# Fusion scenario-editor UI redesign — プロジェクトノート

> このファイルは、GitHub Copilotが同じコンテキストを持つように保持されるClaude Code メモリ ファイル （`fusion-scenario-editor-redesign.md`）の同期コピーです。 Claudeのコピーは信頼できる唯一の情報源です。更新されるたびに、このファイルは同じ編集/コミットで一致するように更新する必要があります。 両者が同意しない場合は、Claude メモリファイルを信頼し、これを再同期します。
>
> これは、スコープが指定されたCopilot命令ファイル （`.github/instructions/*.instructions.md`）であり、リポジトリ全体の`.github/copilot-instructions.md`ではないため、Copilotが`help/workfront-fusion/`の下のファイルで作業している場合にのみ適用されます。リポジトリ内のすべてのリクエストには適用されません。

Becky氏は、多くの記事でFusionのシナリオエディターUIの再設計（新しいエクスペリエンスと従来のエクスペリエンス）を文書化しています。 これは&#x200B;**生きている索引**&#x200B;です。新しいスクリーンショットが撮影されたり、新しいUIの詳細が確認されたりするたびに更新します（追加するだけではありません）。この作業を受け取る誰か（または任意のアシスタント）は、「Xのスクリーンショット/事実は既に用意されていますか？」と答えることができます。 戦略に組み込むことができます。

作業はブランチ `becky-updates-to-Fusion-scenario-editor`で行われます。 マスタートラッキング スプレッドシート：`C:\Users\rebeccas\Desktop\Fusion scenario editor UI redesign - affected articles.xlsx` （シート「影響を受ける記事」 = アーティクルごとのステータス/優先度；シート「機能比較」 = クラシックと新しい機能の差分）。

これらのドキュメント内の未確認のインラインにフラグを立てるための規則：`<!-- BECKY CHECK ME: ... -->`は、その場で、目に見えるコールアウトとして表示されません。

## スクリーンショットインベントリ（新しいエクスペリエンス）

ファイルを複製せずに、絶対パス （例：`/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/run-once-new.png`）を使用して記事をまたいで再利用できます。

**`help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/`** （`scenario-editor.md`の書き換えから – 共有UI クロム アイコン、どこでも再利用）:
`run-once-new.png` （1回実行、アイコンのみ）、`save-icon-new.png`、`notes-icon-new.png`、`scheduling-new.png` （下バーのスケジュール設定トグル +頻度ラベル、例：「データが届くとすぐに」）、`auto-align-icon-new.png`、`scenario-editor-new.png` （フルキャンバス）、`top-bar-new.png`、`controls-new.png`、`tools-new.png`、`favorites-new.png`、`ask-ai-new.png`、`canvas-navigation-new.png`、`search-modules-icon-new.png`、`find-and-replace-icon-new.png`、`snippets-icon-new.png`、`explain-flow-icon-new.png`、`export-blueprint-icon-new.png`、`export-as-headless-template-icon-new.png`、`import-blueprint-icon-new.png`、`previous-version-icon-new.png`、`devtool-icon-new.png` `scenario-settings-icon-new.png`、`additional-controls-new.png`。

**`help/workfront-fusion/build-practice-scenarios/assets/`** （基本シナリオのチュートリアルから）:
`new-placeholder-module.png` （空のカンバスプレースホルダーカード）、`new-connector-picker.png` （アプリ/サービス選択パネル – カテゴリーリスト左：お気に入り、All apps、Adobe Workfront、Adobe Firefly Services、Adobe Creative &amp; Content、Adobe Cloud Services、生成AI、組み込み検索権限）、`new-renamed-module.png`、`new-map-toggle.png`、`new-map-id.png`、`new-execution-bubble.png`、`clock-icon-on-watch-record.png` （モジュールレベルのスケジュール/クロックバッジをカードに配置）、`new-map-in-filter.png` （マッピングされたプロジェクト ID条件を持つフィルターウィンドウの設定）、`new-mapped-update-record.png` （マッピング パネルタブ）、{9）、`new-text-binary-function.png` （star mapping-panel タブ）、`new-mapped-name-block.png` （`upper(...)`内のマップされた名前ブロック）。`new-module-output-icon.png`

**`help/workfront-fusion/create-scenarios/add-modules/assets/`**:
`add-a-module-between-modules.png` （2つのモジュール間のパスを右クリック → メニュー：フィルターの設定/リンク解除/ ルーターの追加/ モジュールの追加/ メモの追加 – フィルター/ルーターを使用しないパスにキャプチャされたメモを追加）、`new-filter-setup-xml-example.png` （フィルターウィンドウの設定は、`add-a-filter-to-a-scenario.md`で使用したFile-Name-ends-with-xmlの例と一致しない場合があります）、`fallback-route-new.png` （フィルターウィンドウの設定、代替ルートチェックボックスのオンとハイライト表示、ルーターユーザーパスの設定）、`new-filter-specific-user.png` fallback チェックボックスがオフの場合、マッピングされたID条件、オレンジ色のハイライトボックス — router-module.mdの「新しいエクスペリエンスのルートにフィルターを追加する」ステップバイステップで使用）、`new-filter-specific-user-unmarked.png` （同じ「特定ユーザー」フィルター、ハイライトボックスは、router-module.mdのif/else例の`if`半分として使用）、`new-not-specific-user-unmarked.png` （「特定ユーザーではない」というラベルの付いたフィルターウィンドウを設定、no condition、no highlight box — router.mdの`else`半分でに使用）。

**まだ取得されていません**：現在router-module.mdに対して未解決の状態はありません。

**`help/workfront-fusion/create-scenarios/config-error-handling/assets/`**:
`new-add-error-handler-in-menu.png` （モジュールを右クリック→設定コンテキストメニュー：このモジュールのみを実行/ エラーハンドラーを追加/名前を変更/ モジュールをコピー/ メモを追加/ マッピング / モジュール名をコピー/ アプリのメタデータ / モジュールを削除 – 「エラーハンドラーを追加」を強調表示 – error-handling.mdで使用）、`new-error-handling-directives.png` （エラーハンドラーから開いたアプリ/サービスピッカーで、専用の「エラー処理」カテゴリが選択され、左側の通常アプリカテゴリと両方にerror-handling.mdを同時使用して、エラーを追加モジュールモジュールに追加しましたハンドラーフロー）、`new-error-handler-examples-with-numbers.png` （`scenario-editor.md`のcanvas-view トグルごとに&#x200B;**Compact view**&#x200B;でキャプチャされたerror-handler階層ウォークスルーの番号付きシナリオ。error-handling.mdで使用。画像を読みやすくするためにコンパクトビューとしてキャプション付けする）。

**`help/workfront-fusion/get-started-with-fusion/understand-fusion/assets/`**:
`new-scenario-example-unmarked.png` （ソースのスクリーンショット Becky provided, unmarked — 8-module Excel/Workfront user-sync scenario: Watch for added User → Router → Find User in Workfront → Router → 3 branches [Set existing User ID / Create new user in Workfront → Set new User ID / Get User ID Variable → Upload userID to spreadsheet] — Classicの`fusion-integration-example.png`および`fusion-glossary.md`の「Scenario」エントリ （`entire-scenario-blank.png`）と同じシナリオです。この例では、これ以降のマークアップのソースとして保持してください）、`new-entire-scenario-scenario.png`、`new-scenario-trigger.png`、`new-scenario-module.png`、`new-scenario-route.png`すべて派生取得から取得しました上：赤いハイライトボックスを介した場合（正確なボックス配置については、記事ごとのメモを参照）、`new-scenario-connectors.png` （Becky提供、新しいExperience Connector ピッカーのアプリリストの周りの赤いボックス）、`new-scenario-segment.png` （Becky提供、2 モジュールのWorkfront Watch Events → Convert object segment、boxed、unboxed Microsoft 365 メールモジュール）、`new-fusion-automation-example.png` （Becky提供、マークなし、4 モジュールのWorkfrontのみの例）、Watch Record → Get project info → → Get Get &quot;assigned to Create update — classicののをののの例をのをの例例111とと111111111111111111111331111311111111113333331133311 Workfront Fusion for Work Automation」セクション、`new-module.png` （`new-scenario-example-unmarked.png`の「Workfrontでユーザーを検索」モジュールのシングルカード切り抜き、PowerShell/System.Drawingを介して切り抜く）、`fusion-glossary.md`の「モジュール」エントリで一般的に使用されます。赤いボックスはありません）。`fusion-template-example.png``license-automation-vs-integration.md`

**`help/workfront-fusion/create-scenarios/config-scenarios-settings/assets/`**:
`new-scenario-settings-ex-1.png` （2 モジュールのシナリオの例 – 「着信要求を監視する…」というラベルの付いたレコードを監視します。 →その他のアクション 「リクエストをプロジェクトに変換」というラベル付き – configure-scenario-settings.mdのMax-number-of-cyclesの例で使用）、`new-max-number-cycles.png` （キャンバス上に開いたシナリオ設定パネル。コントロール領域の歯車アイコンで開いた、「Max number of cycles」フィールドが値`1`で強調表示され、configure-scenario-settings.mdで使用）。

## 確認された新しいエクスペリエンス UIの事実（これらの再利用にスクリーンショットは必要ありません）

- モジュールの右端→**別のモジュールを追加** ボタンが表示され→クリックすると、アプリ/サービスピッカー（最初のモジュールを追加→のと同じピッカー）が開きます。
- モジュール→設定コンテキストメニュー（順序）を右クリック：このモジュールのみを実行/**エラーハンドラー**&#x200B;を追加/名前を変更/複製/モジュールをコピー/メモを追加/マッピングをコピー/モジュール名をコピー/アプリメタデータをコピー/**モジュールを削除**。 両方ともクラシックから変わりません。
- 2つのモジュール間のパスを左クリック→、**フィルターを設定** ウィンドウが直接開きます。 同じパスを右クリックすると、代わりに別の（完全な）コンテキストメニューが開きます。オプションとして「フィルターを設定」を含むメニューは開きません。
- パス→右クリック **ルーターを追加**&#x200B;および&#x200B;**モジュールを追加**&#x200B;は両方のオプションです（`add-a-module-between-modules.png`を参照）。
- **フィルターをコピー** / **フィルターを貼り付ける** （既にフィルターがあるパスを右クリックします）は引き続き存在し、同じように機能します。新しいカードキャンバスに合わせて視覚的にスタイルを変更しますが、同じオプション/ラベルを使用します。
- ルーターモジュール自体をクリックしても（エッジをホバリングしない）、新しいルートが追加されます（変更されずに確認）。
- **ルートを注文** （ルーターモジュールを右クリックし→「ルートを注文」→ドラッグ&amp;ドロップします） – 有効であることが確認され、従来の状態から変更されません。
- **ルートを無効にする** （「ルートを無効にする」→ルートのパスを右クリック）と、無効なルートのビジュアル （ラベルのグレーのパス +無効なルートアイコン）は、クラシックから変更されずに確認されます。
- ルーターモジュール（「フロー制御」 > 「ルーター」）は、新しいピッカーの&#x200B;**ビルトイン** カテゴリの下にファイルされます（「すべてのアプリ」の下にも表示されますが、ビルトインは指示で引用するカテゴリです）。
- フォールバックルート：従来の（ルーターモジュール自体に明確な矢印を付けてマークする）とは異なり、新しいエクスペリエンスでは、ルートのラベルに緑色のテキストで&#x200B;**「フォールバック」**&#x200B;を表示することで、フォールバックルートをマークします。この事実に対して矢印マーカーのスクリーンショットは必要ありません。
- エラーハンドラーのルート：従来の（透明な円と実線の円）とは異なり、新しいエクスペリエンスでは、点線と赤い&#x200B;**「エラーハンドラー」** ラベルでエラーハンドラーのルートが示されます。この事実にスクリーンショットは必要ありません。
- モジュール名の修正（古いドラフトから運ばれたタイプミスではなく、実際のWorkfront名）: **「Watch Record」** （「Watch Records」ではなく単数）、**「Update a record」** （「Update Record」ではない）。
- まだ未確認で、`debug-a-scenario.md`をブロックしています。その他の記事：**DevTool**&#x200B;が新しいエクスペリエンスからまったく削除されているかどうか（噂として聞かれた、他の詳細はまだありません。機能比較表「DevTool」の行を参照してください）。

## この再設計のために定められた家屋規約（残りのすべての記事に適用されます）

- 完全並列複製：「。..新しいエクスペリエンスで（おすすめ）」用のH2/H3 ツリーと「。..クラシックなエクスペリエンスで」用の別のH2/H3 ツリーで、アンカーの衝突を避けるために必要な場所に`(Classic)`個のサフィックスが付いています。 2つ以上の子がある見出しの下にミニ目次を追加します。
- 「new vs. classic」の説明を、記事の紹介&#x200B;**の**&#x200B;末尾の単一の`>[!NOTE]`に折りたたみ（独自のH2ではなく）、この正確な文言を再利用し、「記事のシナリオエディターで」をリンクに追加します。
  > Workfront Fusionは、シナリオエディターを新しいエクスペリエンスに移行中です。 この移行中は、従来のエクスペリエンスと新しいエクスペリエンスの両方を利用でき、いつでも切り替えることができます。 新しいエクスペリエンスを使用することをお勧めします。 詳しくは、シナリオエディターの記事「[新しいエクスペリエンスと従来のエクスペリエンス ](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)」を参照してください。
- 新しいエクスペリエンスの見出しには`(Recommended)` （例：`## Add a filter in the new experience (Recommended)`）が含まれています。
- UIに依存しないコンテンツ（例：`add-a-module-basic.md`の`?moduleId=` URL パラメーターのメモ）は、重複する必要がありません。判断を使用しますが、わからないことがある場合は最初にBeckyに確認してください（確認せずにメモが移動される前に戻されます）。
- Becky氏が操作全体がエクスペリエンス間で同じであることを確認した場合（UIに依存しないメモだけでなく）、まったく新しい/従来のH2/H3に分割しないでください。新しいエクスペリエンスの文言を使用して単一の手順に折りたたみます（`view-scenario-data-flow.md`の「実行中のシナリオでデータフローを表示」など）。 デフォルトの仮定は、手順が異なり、分割が必要な場合です。明示的な確認が行われた後にのみ折りたたまれます。
- 新しいビジュアルと従来のビジュアルが真に異なる単一のイラストスクリーンショット（完全なステップバイステップの手順ではない）の場合は、1つ選択したり、フラグと待機したりしないでください。両方を表示する最初に、各画像の上にプレーンテキストのラベルライン（「新しいエクスペリエンス」/「従来のエクスペリエンス」）を表示します。最初に新しいエクスペリエンスを作成します。 新しいエクスペリエンスの動作については、画像ラベルだけでなく、周囲の文章でも最初に言及してください（例えば、「新しいエクスペリエンスでXでマークされる、またはクラシックエクスペリエンスでYでマークされる」）。 `view-scenario-data-flow.md`の実行/出力インジケーターを参照してください。
- 確認されていないインラインのメッセージには、その場で`<!-- BECKY CHECK ME: ... -->`というフラグを付けます。目立つコールアウトは表示されません。
- 記事のすべてのフラグが解決したら、トラッキングスプレッドシートの「影響を受ける記事」シート（列G）の行`Yes`にマークを付けます。 一部のフラグのみが解決された場合は、`In progress`を使用します。

## 記事ごとのステータス（2026-09-22現在）

完全に完了（0 フラグ、スプレッドシート列Gは`Yes`とマークされています）: `scenario-editor.md`、`create-basic-scenario.md`、`add-trigger-to-basic-scenario.md`、`add-filter-basic-scenario.md`、`add-a-webhook-to-basic-scenario.md`、`use-function-to-build-practice-scenario.md`、`add-a-module-basic.md`、`add-a-filter-to-a-scenario.md`、`router-module.md` （行10）、`error-handling.md` （行15、新しい/古典的なパラレル H3/H4 ツリーに再構築して、「エラーハンドラーをモジュールに追加」と「。..ルーターに」）、`configure-scenario-settings.md` （行20 — スプレッドシートに`Yes`、まだ更新していません）。 「シナリオ設定を開く」を新しい/クラシック H2/H3 スプリットに再構築しました。新しいエクスペリエンスでは、クラシックギアアイコンではなく、既存の`scenario-settings-icon-new.png` （コントロール領域、3 ドットアイコンの後ろにある可能性があります）を使用します。 「最大サイクル数」の例のシェードボックスで、新しいエクスペリエンスのスクリーンショット `new-scenario-settings-ex-1.png` （2つのモジュールの例シナリオ、Watch Record → Misc Action/Convert オブジェクト）と`new-max-number-cycles.png` （コントロールのギアアイコンを介して開いたシナリオ設定パネル、「最大サイクル数」フィールドが強調表示）が使用されるようになりました。 3つ目のスクリーンショット （`scenario-detail-350x207.png`）が完全にドロップされました。「シナリオの詳細ページの履歴領域で、既に実行されているサイクルを確認できます。」というテキストに置き換えられました。

`scenario-overview.md` （行34 — トラッキングスプレッドシートの`Yes`にマークを付け、まだ更新されていません）：完全に完了、0 フラグ。 純粋に概念的な記事（ステップバイステップの「クリック X」の指示はありません）なので、新しい/クラシックなH2/H3の分割は必要ありませんでした。標準のトランジションノートを追加しただけです。 解決済みの8つの元のフラグ：
- 4 （シナリオ全体、トリガー、モジュール、ルート）は、Beckyのマークされていないソース `new-scenario-example-unmarked.png`にPowerShell/System.Drawingで描かれた赤いハイライトボックスを介して表示されます（ピクセルスキャンではなく、ソースをトリミング+ズームすることで見つかった座標 – PowerShell 5.1のフラッドフィル/ピクセルループアプローチは、配列とスカラーのクエリで失敗し続け、とにかく遅すぎました）。`new-entire-scenario-scenario.png`、`new-scenario-trigger.png`、`new-scenario-module.png`、`new-scenario-route.png`。
- 2 （connector, scenario-segment） via screenshots Becky provided already marked up: `new-scenario-connectors.png`, `new-scenario-segment.png`.
- `fusion-integration-example.png` （クラシック）が`new-scenario-example-unmarked.png`とまったく同じシナリオであることを確認して解決した1 （統合例）は、直接再利用され、新しいマークアップは表示されません。
- 1 （テンプレートの例）は、Beckyのマークが付いていない`new-fusion-automation-example.png`、クラシックの`fusion-template-example.png`と一致して解決されました。Beckyが作業の自動処理を希望する場合は、`license-automation-vs-integration.md`の「Workfront Fusion for Work Automationの例」セクションでも再利用できます。

`view-scenario-data-flow.md` （行23 — トラッキングスプレッドシートの`Yes`にマークを付け、まだ更新されていません）：完全に完了、0 フラグ。 標準の遷移メモを追加しました。 「実行中のシナリオでデータフローを表示」は、両方のエクスペリエンスで同じであることが確認されます（他の多くの手順とは異なり、Beckyの呼び出しは、ここでは新しい/古典的な分割は必要ありません）。新しいエクスペリエンスの文言を使用して単一の手順に折りたたまれます（「シナリオの任意の場所をクリックしてシナリオエディターに入る」ステップ含含む）。実行履歴パネル変更が変更されないので、既存変更されていないため、既存の既存従来従来の従来スクリーンショット `assets/currently-running.png`のスクリーンショット変更変更変更を変更変更変更変更変更がされます。 2つのランニング/出力インジケーターは、エクスペリエンス間で視覚的に異なるため、通常の単一スクリーンショットとスワップパターンとは異なり、古いスクリーンショットと新しいスクリーンショットの両方が横に並べて表示され、それぞれにプレーンテキストラベルが表示されます（新しいエクスペリエンス / クラシック体験、新しい最初）。ランニングインジケーターは`assets/new-spinning-icon.png` （モジュールのアイコンのスピンリング）とを比較）。 `assets/ring-around-module.png``assets/new-output-indicator.png``assets/data-flow-output.png`この「show both, labeled, new first, label above image」パターンは、家の慣習です。上記を参照してください。 説明的な段落テキスト自体は、最初に新しいエクスペリエンスの動作を記述し、次にクラシックを記述します（例：「。..は、新しいエクスペリエンスのモジュールのアイコンに回転するリング、またはクラシックエクスペリエンスのモジュールの周りに成長するリングによってマークされます」）。  – 新しい最初の順序は、画像/ラベルの順序だけでなく、散文に適用されます。

`fusion-glossary.md` （行43 — トラッキングスプレッドシートの`Yes`にマークを付け、まだ更新されていません）：完全に完了、0 フラグ。 純粋な用語集テーブル、手順はありません。 表の前に標準の遷移メモを追加しました。 埋め込まれた両方の画像（生のHTML `<img>` タグ、マークダウンではない）は、ユーザーが提供した新しいスクリーンショットを必要とせずに解決されました。「シナリオ」エントリの`entire-scenario-blank.png`は`new-scenario-example-unmarked.png`とまったく同じシナリオであり（直接再利用）、「モジュール」エントリの`module.png`は、同じソースから作成されたシングルカード切り抜きの`new-module.png`に置き換えられました。

ブロックされました（`debug-a-scenario.md`と同じ処理 – フラグが付けられ、フラグを超えて編集されません。列Gは空白のままです）: `advanced-error-handling.md` （行16）。 標準のトランジションノートがイントロに追加されましたが、その2つの例（「例：フィルターによるエラー処理」と「ネストの例」）は、ステップバイステップの「X」コンテンツをクリックして新しい/クラシックに分割しない、単一の継続的なイラストDropboxシナリオです。スクリーンショットは、Beckyの指示に従ってクラシックとして意図的に残されました。 フラグ付きのインライン（例：「####」の直前、およびネストする`>[!BEGINSHADEBOX]`の直前）に、既存のシナリオのスクリーンショットを置き換えるだけでなく、新しいエクスペリエンス **に組み込まれた**&#x200B;まったく新しいサンプルシナリオ（Dropboxではなくベッキーが提案したWorkfront モジュール）が必要であることを示すエラーが発生しました。 スプレッドシートの列DとFが同じスコープノートで更新されました。列Gは空白のままです。

未着手：トラッキングスプレッドシート内の他のすべてのもの（`debug-a-scenario.md`は開発ツールの確認時にブロックされ、残りは未操作）。
