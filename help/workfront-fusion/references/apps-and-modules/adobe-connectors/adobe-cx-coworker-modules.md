---
title: Adobe CX Enterprise Coworkerモジュール
description: Adobe Workfront FusionのAdobe CX Enterprise Coworker コネクタを使用して、自然言語のプロンプトをCoworkerに送信し、その応答をシナリオで使用します。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 6efe84af0487893a3c33ba2bf6e3db5200f25446
workflow-type: tm+mt
source-wordcount: '1974'
ht-degree: 7%
---
# Adobe CX Enterprise Coworkerモジュール

Adobe Workfront FusionのAdobe CX Enterprise Coworker コネクタを使用して、自然言語のプロンプトをCoworkerに送信し、その応答をシナリオで使用します。 チームメンバーは、リクエストを解釈し、アカウントのツールを使用して作業を遂行します。

コネクタには、次の2つのモジュールがあります。

* **[!UICONTROL プロンプトを実行]**&#x200B;すると、新しいリクエストが開始され、デフォルトでは結果が待たれます。
* **[!UICONTROL 実行ステータスを取得]**&#x200B;は、以前に開始したリクエストを確認します。

## アクセス要件

<!-- BECKY CHECK ME: This table is copied from other Fusion connector articles. The source material does not list access requirements, but says you need an Adobe account that has access to Coworker. Confirm the requirements and whether Coworker needs its own license or entitlement. -->

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意の Adobe Workfront Workflow パッケージと任意の Adobe Workfront Automation および Integration パッケージ</p><p>Workfront Ultimate</p><p>Workfront Fusion を追加購入した Workfront Prime および Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>Work またはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## 前提条件

ADOBE CX ENTERPRISE COWORKERへのアクセス権を持つAdobe アカウントが必要です。

## Adobe CX Enterprise CoworkerとWorkfront Fusionの連携

Coworkerおよびリクエストに必要なサービスにアクセスできるAdobe アカウントでログインします。

接続を作成するには：

1. Adobe Fusion MCP モジュールで、**接続** フィールドの横にある&#x200B;**[!UICONTROL 追加]**&#x200B;をクリックします。
1. 次のフィールドに入力します。

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">接続名</td>
        <td>
          <p>この接続の名前を入力します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">環境</td>
        <td>
          <p>実稼動環境と非実稼動環境のどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">タイプ</td>
        <td>
          <p>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">クライアント ID</td>
        <td>
          <p>この接続のオプションの上書きを入力またはマッピングします。 それ以外の場合は、このアカウントタイプのplatform-managed clientIdを使用します。 専用Coworker アカウントの表示されたFusion コールバック URLを登録します。</p>
        </td>
      <tr>
        <td role="rowheader">クライアント秘密鍵</td>
        <td>
          <p>この接続のオプションの上書きを入力またはマッピングします。 それ以外の場合は、このアカウントタイプのプラットフォームで管理されるclientSecretを使用します。 設定されたIMS環境に対して発行された資格情報を使用します。</p>
        </td>
    </tbody>
   </table>

1. 「**[!UICONTROL 続行]**」をクリックします。

ログインできない場合や、必要なサービスを使用できない場合は、管理者にお問い合わせください。

## Adobe CX Enterprise Coworker モジュールとそのフィールド

>[!WARNING]
>
>プロンプトにパスワードやその他の資格情報を絶対に含めないでください。

### 実行ステータスを取得

このアクションモジュールは、**[!UICONTROL プロンプトの実行]**&#x200B;によって開始されたタスクの現在の状態を確認します。

このモジュールは、タスクを1回チェックします。 新しいタスクを開始したり、タスクが完了するまでチェックを続けたりすることはありません。 結果がまだ保留中の場合は、後でもう一度確認してください。

>[!NOTE]
>
>タスク IDを数値に変換したり、丸めたり、再フォーマットしたりしないでください。 同僚がタスク IDなしで即座に元のプロンプトに回答した場合、ステータスを確認する必要はありません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Include raw result] <i> （Optional, advanced） </i></td> 
   <td> <p>このオプションはデフォルトでオフになっています。 出力に完全なCoworker応答を含めます。 応答には機密情報が含まれている可能性があります。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>元の<b>[!UICONTROL プロンプトを実行]</b>実行で使用したのと同じ接続を選択します。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Task ID]</td> 
   <td> <p><b>[!UICONTROLが返したタスク IDをマッピングします。プロンプトを実行します]</b>。 返されたテキストとまったく同じようにしてください。</p> </td> 
  </tr> 
 </tbody> 
</table>

### プロンプトの実行

このアクションモジュールは、アカウントで利用可能なツールを使用してテキストの要約や情報の収集などの指示を共同作業者に送信します。

実行ごとにプロンプトを1回送信し、新しい会話を開始します。 AI モデルを選択したり、別のAI プロバイダーのキーを指定したりする必要はありません。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Coworker接続を選択します。 手順については、この記事の「<a href="#connect-adobe-cx-coworker-to-workfront-fusion" class="MCXref xref">Adobe CX Enterprise CoworkerをWorkfront Fusionに接続する</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ユーザープロンプト ]</td> 
   <td> <p>命令を入力してください。 複数の行を使用して、以前のモジュールの情報をマッピングできます。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Wait for completion] <i> （Optional, advanced） </i></td> 
   <td> <p>このオプションはデフォルトでオンになっています。 モジュールでタスクが完了するのを待つ場合や、注意が必要な場合は、このオプションを有効にします。 最初の結果をすぐに返すには、オフにします。</p><p>詳しくは、この記事の「<a href="#wait-for-completion">完了を待つ</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Include raw result] <i> （Optional, advanced） </i></td> 
   <td> <p>このオプションはデフォルトでオフになっています。 このオプションを有効にすると、モジュールがCoworkerの全応答を出力に含めることができます。 応答には機密情報が含まれている可能性があります。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
> 特定の目的のために完全な応答が必要な場合を除き、**[!UICONTROL 生の結果を含める]**&#x200B;をオフにすることをお勧めします。 生の結果には機密情報が含まれている可能性があり、すべてのアクションの完全な記録が保証されるわけではありません。 生の結果を保存、共有、または別のサービスに渡す前に、その結果に含まれるものを確認します。

#### 完了を待機

**[!UICONTROL 完了を待つ]**&#x200B;がオンになっている場合、モジュールは5秒間待ってからタスクを確認します。 タスクがまだ保留中の場合、モジュールは再度チェックするまでさらに5秒待ちます。 各チェックは、応答を受け取るのにも時間がかかります。 ステータスを確認しても、プロンプトは再度送信されません。

待ち時間は、タスクが完了、失敗、キャンセルまたは却下された場合、または入力または承認が必要な場合に停止します。 Coworkerが即座に回答を提供した場合、モジュールはそれ以上のチェックなしで返します。

**[!UICONTROL 完了を待つ]**&#x200B;がオフの場合、モジュールはタスクが完了するのを待たずに最初の結果を返します。 **[!UICONTROL 状態]**、**[!UICONTROL 完了済み]**、**[!UICONTROL を調査するには、次に何をすべきかを決定するために注意]**&#x200B;が必要です。 最初の結果が届いたときにすでにタスクを完了できます。

待機中はFusionのモジュールタイムアウトの対象となります。 モジュールがタイムアウトまたは停止した場合、共同作業者は引き続き作業を行います。 その場合、出力やタスク IDを受け取らない可能性があります。

長い作業の場合は、待ち時間をオフにして最初の&#x200B;**[!UICONTROL タスク ID]**&#x200B;を保存し、後でタスクを確認できるようにします。 タイムアウト後にプロンプトを再度自動的に実行しないでください。 最初のリクエストは既に進行中の場合があり、それを繰り返すと変更が重複する可能性があります。


## モジュール出力

どちらのモジュールも、エラーなしで終了すると、次の情報を返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p>タスクを識別します。 同僚がタスクを作成せずに即座に回答を提供する場合、これは空です。 この値を<b>[!UICONTROL Get Execution Status]</b>で使用します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL コンテキスト ID]</td> 
   <td> <p>会話を識別します。 会話を続けるためのインプットではありません。</p><p>詳しくは、この記事の「<a href="#use-previous-answers">以前の回答を使用</a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td> <p>現在のタスクの状態。 この記事の<a href="#task-states" class="MCXref xref"> タスクの状態</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Completed]</td> 
   <td> <p>Trueを指定すると、タスクが完了するか、共同作業者がすぐに回答します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROLは注意が必要です]</td> 
   <td> <p>同僚が入力または承認を必要とする場合はTrueです。</p><p>詳しくは、この記事の「<a href="#requests-that-need-attention">注意が必要なリクエスト </a>」を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Final assistant text]</td> 
   <td> <p>タスクが完了した時点での最終回答。 タスクが保留中または注意が必要な場合は、このフィールドは空です。 回答が完成した場合は、回答テキストがない場合もあります。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL テキスト アーティファクト （中間テキストを含める場合があります） ]</td> 
   <td> <p>作業中にテキストが返されます。 各アイテムには、アーティファクト ID、名前、テキストを含めることができます。 これらの項目は必ずしも最終的な答えではない。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Raw結果（オプトイン） ]</td> 
   <td> <p>完全な回答です。 これは、<b>[!UICONTROL Include raw result]</b>がオンの場合にのみ含まれます。</p> </td> 
  </tr> 
 </tbody> 
</table>

すべてのテキストアーティファクトを組み合わせるのではなく、回答に&#x200B;**[!UICONTROL 最終アシスタントテキスト]**&#x200B;を使用します。 成果物には、進捗状況の説明やその他の中間テキストを含めることができます。

### 注意が必要なリクエスト

作業を続けるには、より多くの情報や承認が必要になる場合があります。 この場合、**[!UICONTROL 要注意]**&#x200B;はtrueで、**[!UICONTROL 完了]**&#x200B;はfalseです。 完了済みの作業として処理するのではなく、結果を個人にルーティングします。

これらのモジュールは、フォローアップの質問に答えたり、ユーザーに代わってアクションを承認したりすることはできません。 **[!UICONTROL 実行ステータスを取得]**&#x200B;は、タスクの状態が変更されたかどうかを確認できますが、入力または承認の要求は解決されません。

### 以前の回答を使用

**[!UICONTROL プロンプトを実行]**&#x200B;するたびに、新しい会話が開始されます。 以前の回答を参照するには、新しいプロンプトに関連する質問と回答をテキストとして含めます。 これにより、同僚のコンテキストが得られますが、以前の会話は再開されません。

**[!UICONTROL コンテキスト ID]**&#x200B;は、結果に関連付けられている会話を識別します。 会話を続けるために、これらのモジュールにデータを供給することはできません。

>[!IMPORTANT]
>
>**[!UICONTROL Completed]**&#x200B;は、要求されたビジネス アクションが成功したことを保証するものではありません。 たとえば、同僚が、必要なツールが利用できないことを説明して終了する場合があります。 回答を確認し、必要な結果を確認してから次の操作を行います。

### タスクの状態

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"><code>submitted</code>, <code>working</code></td> 
   <td> <p>タスクは保留されています。 <b>[!UICONTROL Completed]</b>はfalseです。 <b>[!UICONTROL プロンプトの実行]</b>は、待機中の待機中も待機中です。 それ以外の場合は、タスク IDを保存して後で確認してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>completed</code></td> 
   <td> <p><b>[!UICONTROL Completed]</b>はtrueです。 <b>[!UICONTROL Final assistant text]</b>を確認し、期待される結果を確認してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>input-required</code>, <code>auth-required</code></td> 
   <td> <p>タスクには注意が必要です。 <b>[!UICONTROL Completed]</b>はfalseで、<b>[!UICONTROL Requires attention]</b>はtrueです。 キャンセル待ち。 人間によるレビューの結果のルーティング：</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>failed</code>, <code>canceled</code>, <code>rejected</code></td> 
   <td> <p>モジュールは、通常の結果ではなくエラーを報告します。</p> </td> 
  </tr> 
 </tbody> 
</table>

保留中の結果、つまり注意が必要な結果は、モジュールがエラーなしで返されても、正常に完了しません。

## 例

### 更新の要約

1. **[!UICONTROL プロンプトを実行]**&#x200B;を追加し、接続を選択します。
1. 「**[!UICONTROL ユーザープロンプト]**」フィールドに次の項目を入力します。

   ```text
   Summarize the following project update in three bullet points.
   Use only the supplied text; do not call tools or change any records.
   
   The planning workshop is complete. Two dependencies need confirmation.
   The team will review the delivery estimate on Friday.
   ```

1. **[!UICONTROL 完了待ち]**&#x200B;を残し、**[!UICONTROL 生の結果を含める]**&#x200B;をオフにします。
1. **[!UICONTROL 要注意]**&#x200B;がtrueの場合は、人間によるレビューのために結果をルーティングします。 **[!UICONTROL Completed]**&#x200B;がtrueの場合、**[!UICONTROL 最終アシスタントのテキスト]**&#x200B;を次のステップにマッピングします。

AIで生成された文言はさまざまです。 正確性が重要な場合は結果の確認：

### 後で長いタスクを確認する

1. **[!UICONTROL プロンプトを実行]**&#x200B;し、接続を選択し、指示を入力します。
1. **[!UICONTROL 完了を待つ]**&#x200B;をオフにします。
1. 最初の結果を確認します。

   * タスクが完了したら、結果を処理します。
   * タスクに注意が必要な場合は、結果をレビュー用にルーティングします。
   * タスクが保留中の場合は、**[!UICONTROL タスク ID]**&#x200B;をテキストとして保存し、使用した接続をメモします。

1. 後で、その接続とタスク IDで&#x200B;**[!UICONTROL 実行ステータスを取得]**&#x200B;を使用します。
1. タスクがまだ保留中の場合は、シナリオの制限内で別のチェックを手配します。 完了時に結果を1回処理し、注意やエラーを個別に処理します。

進行状況を確認するためだけに、元のプロンプトを再度実行しないでください。

## 使用上の考慮事項

* チームメンバーは、ツールを使用して、レコードの変更など、アカウントで許可されたアクションを実行できます。 信頼できるプロンプトと、適切なアクセス権を持つアカウントを使用する。
* これらのモジュールは、個々のツールを制限する方法を提供しません。 「何も変更しない」などの指示は、意図を表しますが、強制された読み取り専用モードではありません。
* 利用できるツールとスキルはアカウントによって異なります。 コネクターは、スキルセレクターを提供しないか、ジャーニーの作成やプロジェクトの更新など、特定のアクションを保証しません。 承認が必要なリクエストが無人で完了すると仮定しないでください。
* コネクターは同僚のリクエストを開始してチェックします。 プロジェクトの変更を監視したり、別のアプリケーションへの回答を自動的に保存したりすることはありません。 必要に応じて、適切なトリガー、ストレージ、フォローオンモジュールをシナリオに追加します。
* AIが生成した回答は不完全または不正確な場合があります。 重要な結果を事前に検証し、変更や意思決定に役立てることができます。
* コネクタは、失敗したリクエストを自動的に再試行しません。 シナリオのエラー処理で、結果が不確実なプロンプトが繰り返されないようにします。

## トラブルシューティング

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">必須フィールドがありません</td> 
   <td> <p>接続を選択し、必要なプロンプトまたはタスク IDを入力します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ログインに失敗するか、アクセスが拒否されました</td> 
   <td> <p>もう一度ログインし、Adobe アカウントがCoworkerと必要なサービスにアクセスできることを確認します。 必要に応じて、管理者に連絡してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">タスクが見つかりません</td> 
   <td> <p>タスク IDが変更されていないこと、および元の接続を使用していることを確認してください。 新しいタスクはすぐに表示されない場合があります。 もう一度プロンプトを送信する代わりに、後でステータスを確認します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ステータスチェックが失敗する</td> 
   <td> <p>エラーに使用可能なタスク IDが含まれている場合は、<b>[!UICONTROL Get Execution Status]</b>を使用して、そのタスクを調査します。 プロンプトを自動的に再起動しないでください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">プロンプトを実行すると、応答がタイムアウトまたは失われる</td> 
   <td> <p>IDを受け取っていない場合でも、タスクが開始されている可能性があります。 重複する作業を避けるために、リクエストを繰り返す前に調査します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">待機中にFusionがタイムアウトする</td> 
   <td> <p>同僚はまだ働いているかもしれません。 IDがある場合は、タスクを確認します。 今後の長いタスクの場合は、待ち時間をオフにして、最初に最初のIDを保存します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">同僚または必要なサービスが利用できません</td> 
   <td> <p>表示されたエラーを、資格情報や機密性の高い結果コンテンツを使用せずに、管理者と共有します。</p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- BECKY CHECK ME: Confirm the exact module and field labels in the UI (Run a Prompt, Get Execution Status, User prompt, Wait for completion, Include raw result, Task ID, and the output item names). Also confirm that the module is listed under "Adobe CX Enterprise Coworker" in the app picker. -->
