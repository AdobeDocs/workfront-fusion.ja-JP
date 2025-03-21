---
title: GitLab モジュール
description: Adobe Workfront Fusion を使用するには、Adobe Workfront ライセンスに加えて、Adobe Workfront Fusion ライセンスが必要です。
author: Becky
feature: Workfront Fusion
exl-id: fabbadce-5669-4363-834e-6d7428520f62
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '3554'
ht-degree: 90%

---

# [!UICONTROL GitLab] モジュール

Adobe Workfront Fusion を使用するには、Adobe Workfront ライセンスに加えて、Adobe Workfront Fusion ライセンスが必要です。

[!DNL Adobe Workfront Fusion] のシナリオでは、[!UICONTROL GitLab] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。

>[!NOTE]
>
>この記事では、API ドキュメントや [!DNL GitLab] の機能全般についてある程度の知識があることを想定しています。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion]  ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## [!DNL GitLab] を [!DNL Workfront Fusion] に接続 {#connect-gitlab-to-workfront-fusion}

1. 任意の [!DNL Workfront Fusion] [!DNL Gitlab] モジュールで、接続フィールドの横にある「**[!UICONTROL Add]**」をクリックします。
1. 次のフィールドを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td> <p>接続に名前を入力します。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL [!DNL GitLab] URL]</td> 
      <td>[!DNL GitLab] インスタンスの URL を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Access Token]</td> 
      <td><p>[!UICONTROL Private Token] または [!UICONTROL Personal Access Token] を入力します。</p><p>[!DNL GitLab] での個人用アクセストークンの検索または作成について詳しくは、[!DNL GitLab] ドキュメントの<a href="https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html">個人用アクセストークン</a>にある「個人用アクセストークンの作成」を参照してください。</p></td> 
     </tr> 
    </tbody> 
   </table>


1. **[!UICONTROL Continue]** をクリックします。
1. 「**[!UICONTROL Authorize]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL GitLab] モジュールとそのフィールド

[!DNL GitLab] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL GitLab] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### トリガー

+++**[!UICONTROL Watch build status]**

このインスタントトリガーモジュールは、ビルドのステータスが変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでビルドステータスの変更を監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commit/MR/issue/snippet comments]**

このインスタントトリガーモジュールは、コミット、結合リクエスト、イシュー、またはコードスニペットに対してコメントが追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでコメントを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commits (pushes)]**

このインスタントトリガーモジュールは、コミットがリポジトリにプッシュされたときにシナリオを開始します。タグがプッシュされた場合は、このモジュールはシナリオを開始しません。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでコミットを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issue comment]**

このインスタントトリガーモジュールは、イシューに対してコメントが作成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでイシューコメントを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issues]**

この [!UICONTROL instant trigger] モジュールは、イシューが作成されたとき、または既存のイシューが更新、クローズ、再オープンされたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでイシューを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge requests]**

このインスタントトリガーモジュールは、次のいずれかが発生した場合にシナリオを開始します。

* 新しい結合リクエストが作成される
* 既存の結合リクエストが更新、結合、または閉じられる
* ソースブランチにコミットが追加される


<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックで結合リクエストを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge request comments]**

このインスタントトリガーモジュールは、結合リクエストに対してコメントが作成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックで結合リクエストのコメントを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch pipeline status]**

このインスタントトリガーモジュールは、パイプラインのステータスが変更されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでパイプラインステータスの変更を監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch projects]**

このスケジュール済みトリガーモジュールは、認証済みユーザーがメンバーとなっている新しいプロジェクトが追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL GitLab] アカウントを [!DNL Workfront] Fusion に接続する手順については、この記事の <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">[!DNL GitLab] を [!DNL Workfront] Fusion に接続</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">最大結果数</td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが監視するレコードの最大数を入力またはマッピングします。</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository branches]**

このスケジュール済みトリガーモジュールは、新しいブランチがリポジトリに追加されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL GitLab] アカウントを [!DNL Workfront] Fusion に接続する手順については、この記事の <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">[!DNL GitLab] を [!DNL Workfront] Fusion に接続</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">最大結果数</td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが監視するレコードの最大数を入力またはマッピングします。</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository tags]**

このインスタントトリガーモジュールは、リポジトリでタグが作成または削除されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでタグを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch snippet comments]**

このインスタントトリガーモジュールは、スニペットに対して新しいコメントが作成されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックでコメントを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch todos]**

このスケジュール済みスケジュールトリガーモジュールは、新しい TODO が追加されるとシナリオを開始します。フィルターが適用されない場合、トリガーは、新たな保留 TODO が追加されたときに実行されます。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントにある [DOS のリストを取得](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos)を参照してください。

+++

+++**[!UICONTROL Watch wiki page]**

このインスタントトリガーモジュールは、Wiki ページが作成または編集されたときにシナリオを開始します。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>このトリガーで使用する web フックを選択するか、新しい web フックを追加します。 </p><p>新しい web フックを追加するには、次の手順に従います。 <ol><li>[!UICONTROL webhook] フィールドの横にある「<b>[!UICONTROL Add]</b>」をクリックします。</li><li>以下の情報を入力します。 <ul><li>Web フックの名前</li><li>この web フックに使用する接続</li><li>Web フックで Wiki ページを監視するプロジェクト</li></ul></li><li>「<b>[!UICONTROL Save]</b>」をクリックして Webhook を保存し、モジュールに戻ります。 </td> 
   </tr> 
   </tbody> 
</table>

+++

### アクション

+++**[!UICONTROL Accept merge request]**

このアクションモジュールは、送信された変更を指定された結合リクエストと結合します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[結合リクエストの承認](https://docs.gitlab.com/ee/api/merge_requests.html#accept-mr)を参照してください。

+++

+++**[!UICONTROL Cancel a build]**

このアクションモジュールは、プロジェクトの単一のビルドをキャンセルします。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL GitLab] アカウントを [!DNL Workfront] Fusion に接続する手順については、この記事の <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">[!DNL GitLab] を [!DNL Workfront] Fusion に接続</a>を参照してください。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>キャンセルするビルドを含むプロジェクトを選択またはマッピングします。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td>キャンセルするビルドを選択またはマッピングします。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge commit message]</td> 
   <td> 結合のコミットメッセージを入力またはマッピングします。
    </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Should remove source branch]</td> 
   <td>結合が完了したときにソースブランチを削除するかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge when build succeeds]</td> 
   <td>ビルドが完了したら、すぐに結合リクエストを結合するかどうかを選択します。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL SHA]</td> 
   <td>SHA が存在する場合、この SHA はソースブランチの HEAD と一致する必要があります。一致しない場合、結合は失敗します。</td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Cancel a pipeline's builds]**

このアクションモジュールは、単一のパイプラインのビルドをキャンセルします。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[パイプラインのジョブのキャンセル](https://docs.gitlab.com/ee/api/pipelines.html#cancel-a-pipelines-jobs)を参照してください。

+++

+++**[!UICONTROL Cancel merge when pipeline succeeds]**

パイプラインの成功時に結合リクエストが結合に設定されている場合、このアクションモジュールはそのアクションをキャンセルします。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[パイプラインの成功時に結合をキャンセル](https://docs.gitlab.com/ee/api/merge_requests.html)を参照してください。

+++

+++**[!UICONTROL Cherry pick a commit]**

このチェリーアクションモジュールは、特定のブランチへのコミットを選択します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[チェリーがコミットを選択](https://docs.gitlab.com/ee/api/commits.html#cherry-pick-a-commit)を参照してください。

+++

+++**[!UICONTROL Create a new label]**

このアクションモジュールは、指定されたリポジトリのラベルを新規作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[ラベルの新規作成](https://docs.gitlab.com/ee/api/labels.html#create-a-new-label)を参照してください。

+++

+++**[!UICONTROL Create a new pipeline]**

このアクションモジュールは、指定されたプロジェクトにパイプラインを新規作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[パイプラインの新規作成](https://docs.gitlab.com/ee/api/pipelines.html#create-a-new-pipeline)を参照してください。

+++

+++**[!UICONTROL Create a new release]**

このアクションモジュールは、既存の Git タグにリリースノートを追加します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リリースを作成](https://docs.gitlab.com/ee/api/releases/#create-a-release)を参照してください。

+++

+++**[!UICONTROL Create a new tag]**

このアクションモジュールは、指定された参照を指すリポジトリに新しいタグを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[新しいタグを作成](https://docs.gitlab.com/ee/api/tags.html#create-a-new-tag)を参照してください。

+++

+++**[!UICONTROL Create a todo]**

このアクションモジュールは、選択したイシューで、現在のユーザーの TODO を作成します。現在のユーザーは、このモジュールで使用される接続の資格情報で識別されるユーザーです。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの [TODO を作成](https://docs.gitlab.com/ee/api/issues.html#create-a-todo)を参照してください。

+++

+++**[!UICONTROL Create a todo on a merge request]**

このアクションモジュールは、選択した結合リクエストで、現在のユーザーの TODO を作成します。現在のユーザーは、このモジュールで使用される接続の資格情報で識別されるユーザーです。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの [TODO を作成](https://docs.gitlab.com/ee/api/merge_requests.html#create-a-todo)を参照してください。

+++

+++**[!UICONTROL Create merge request]**

このアクションモジュールは、プロジェクトで新しい結合リクエストを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[結合リクエストを作成](https://docs.gitlab.com/ee/api/merge_requests.html#create-mr)を参照してください。

+++

+++**[!UICONTROL Create new file in repository]**

このアクションモジュールは、選択したリポジトリに新しいファイルを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリに新しいファイルを作成](https://docs.gitlab.com/ee/api/repository_files.html#create-new-file-in-repository)を参照してください。

+++

+++**[!UICONTROL Create new issue note]**

このアクションモジュールは、単一のプロジェクトイシューに関するイシューメモを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[新しいイシューメモを作成](https://docs.gitlab.com/ee/api/notes.html#create-new-issue-note)を参照してください。

+++

+++**[!UICONTROL Create new merge request note]**

このアクションモジュールは、単一の結合リクエストに関するメモを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[新しい結合リクエストメモを作成](https://docs.gitlab.com/ee/api/notes.html#create-new-merge-request-note)を参照してください。

+++

+++**[!UICONTROL Create a new milestone]**

このアクションモジュールは、プロジェクトの新しいマイルストーンを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[新しいマイルストーンを作成](https://docs.gitlab.com/ee/api/milestones.html#create-new-milestone)を参照してください。

+++

+++**[!UICONTROL Create new snippet note]**

このアクションモジュールは、単一のスニペットに関する新しいメモを作成します。スニペットメモとは、ユーザーがスニペットに対して投稿できるコメントのことです。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[新しいスニペットメモを作成](https://docs.gitlab.com/ee/api/notes.html#create-new-snippet-note)を参照してください。

+++

+++**[!UICONTROL Create repository branch]**

このアクションモジュールは、単一のリポジトリブランチを作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリブランチを作成](https://docs.gitlab.com/ee/api/branches.html#create-repository-branch)を参照してください。

+++

+++**[!UICONTROL Create build variable]**

このアクションモジュールは、新しいビルド変数を作成します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[変数を作成](https://docs.gitlab.com/ee/api/project_level_variables.html#create-variable)を参照してください。

+++

+++**[!UICONTROL Delete a merge request]**

このアクションモジュールは、管理者とプロジェクトの所有者専用です。該当する結合リクエストを削除します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[結合リクエストを削除](https://docs.gitlab.com/ee/api/merge_requests.html#delete-a-merge-request)を参照してください。

+++

+++**[!UICONTROL Delete existing file in repository]**

このアクションモジュールは、リポジトリから既存のファイルを削除します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリ内の既存のファイルを削除](https://docs.gitlab.com/ee/api/repository_files.html#delete-existing-file-in-repository)を参照してください。

+++

+++**[!UICONTROL Delete repository branch]**

このアクションモジュールは、リポジトリからブランチを削除します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリブランチを削除](https://docs.gitlab.com/ee/api/branches.html#delete-repository-branch)を参照してください。

+++

+++**[!UICONTROL Edit issue]**

このアクションモジュールは、既存のプロジェクトイシューを更新します。この呼び出しは、イシューをクローズ済みとマークするためにも使用されます。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[イシューを編集](https://docs.gitlab.com/ee/api/issues.html#edit-issue)を参照してください。

+++

+++**[!UICONTROL Edit Milestone]**
このアクションモジュールは、既存のプロジェクトマイルストーンを更新します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[マイルストーンを編集](https://docs.gitlab.com/ee/api/milestones.html#edit-milestone)を参照してください。

+++

+++**[!UICONTROL Erase a build]**

このアクションモジュールは、プロジェクトのビルドを消去します（ジョブのアーティファクトとジョブのログを削除します）。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[ジョブを消去](https://docs.gitlab.com/ee/api/jobs.html#erase-a-job)を参照してください。

+++

+++**[!UICONTROL Get a list of todos]**

この検索モジュールは、TODO 項目のリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの [TODO のリストを取得](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos)を参照してください。

+++

+++**[!UICONTROL Get a single build]**

このアクションモジュールは、プロジェクトの単一のジョブを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のジョブを取得](https://docs.gitlab.com/ee/api/jobs.html#get-a-single-job)を参照してください。

+++

+++**[!UICONTROL Get a single repository tag]**

このアクションモジュールは、名前によって決定された特定のリポジトリタグを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のリポジトリタグを取得](https://docs.gitlab.com/ee/api/tags.html#get-a-single-repository-tag)を参照してください。

+++

+++**[!UICONTROL Get a specific deployment]**

このアクションモジュールは、特定のデプロイメントを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[特定のデプロイメントを取得](https://docs.gitlab.com/ee/api/deployments.html#get-a-specific-deployment)を参照してください。

+++

+++**[!UICONTROL Get all issues assigned to a single milestone]**

この検索モジュールは、単一のプロジェクトマイルストーンに割り当てられたすべてのイシューを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のマイルストーンに割り当てられたすべてのイシューを取得](https://docs.gitlab.com/ee/api/milestones.html#get-all-issues-assigned-to-a-single-milestone)を参照してください。

+++

+++**[!UICONTROL Get file from repository]**

このアクションモジュールは、名前、サイズ、コンテンツなど、リポジトリ内のファイルに関する情報を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリからファイルを取得](https://docs.gitlab.com/ee/api/repository_files.html#get-file-from-repository)を参照してください。

+++

+++**[!UICONTROL Get project users]**

この検索モジュールは、プロジェクトのユーザーを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトユーザーを取得](https://docs.gitlab.com/ee/api/projects.html#get-project-users)を参照してください。

+++

+++**[!UICONTROL Get a single issue]**

このアクションモジュールは、イシューの詳細を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>新しい接続を作成する方法については、この記事の <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] to Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td> <p>詳細を取得するイシューを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID]</td> 
   <td> <p>詳細を取得するイシューの名前を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Get single issue note]**

このアクションモジュールは、特定のプロジェクトイシューに関する単一のメモを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のイシューのメモを取得](https://docs.gitlab.com/ee/api/notes.html#get-single-issue-note)を参照してください。

+++

+++**[!UICONTROL Get single merge request]**

このアクションモジュールは、単一の結合リクエストに関する情報を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一の結合リクエストを取得](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr)を参照してください。

+++

+++**[!UICONTROL Get single merge request changes]**

この検索モジュールは、ファイルや変更を含む、結合リクエストに関する情報を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一の結合リクエストの変更を取得](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-changes)を参照してください。

+++

+++**[!UICONTROL Get single merge request commits]**

このアクションモジュールは、結合リクエストのコミットのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一の結合リクエストのコミットを取得](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits)を参照してください。

+++

+++**[!UICONTROL Get single merge request note]**

このアクションモジュールは、指定した結合リクエストの単一のメモを返します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一の結合リクエストのメモを取得](https://docs.gitlab.com/ee/api/notes.html#get-single-merge-request-note)を参照してください。

+++

+++**[!UICONTROL Get a Milestone]**

このアクションモジュールは、マイルストーンの詳細を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のマイルストーンを取得](https://docs.gitlab.com/ee/api/milestones.html#get-single-milestone)を参照してください。

+++

+++**[!UICONTROL Get single project]**

このアクションモジュールは、プロジェクトの詳細を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のプロジェクトを取得](https://docs.gitlab.com/ee/api/projects.html#get-single-project)を参照してください。

+++

+++**[!UICONTROL Get single repository branch]**

このアクションモジュールは、リポジトリブランチの詳細を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のリポジトリブランチを取得](https://docs.gitlab.com/ee/api/branches.html#get-single-repository-branch)を参照してください。

+++

+++**[!UICONTROL Get snippet note]**

このモジュールは、指定したスニペットの単一のメモを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[単一のスニペットのメモを取得](https://docs.gitlab.com/ee/api/notes.html#get-single-snippet-note)を参照してください。

+++

+++**[!UICONTROL Get the comments of a commit]**

この検索モジュールは、プロジェクトのコミットのコメントを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[コミットのコメントを取得](https://docs.gitlab.com/ee/api/commits.html#get-the-comments-of-a-commit)を参照してください。

+++

+++**[!UICONTROL Get the diff of a commit]**

このアクションモジュールは、プロジェクトのコミットの差分を取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[コミットの差分を取得](https://docs.gitlab.com/ee/api/commits.html#get-the-diff-of-a-commit)を参照してください。

+++

+++**[!UICONTROL Keep artifacts]**

有効期限が設定されている場合にアーティファクトが削除されるのを防ぎます。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[アーティファクトを保持](https://docs.gitlab.com/ee/api/job_artifacts.html#keep-artifacts)を参照してください。

+++

+++**[!UICONTROL List all merge request notes]**

この検索モジュールは、単一の結合リクエストのすべてのメモのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[結合リクエストのすべてのメモを一覧表示](https://docs.gitlab.com/ee/api/notes.html#list-all-merge-request-notes)を参照してください。

+++

+++**[!UICONTROL List all snippet notes]**

このモジュールは、単一のスニペットのすべてのメモのリストを取得します。スニペットメモとは、ユーザーがスニペットに対して投稿できるコメントのことです。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[??](https://docs.gitlab.com/ee/api/notes.html#list-all-snippet-notes)を参照してください。

+++

+++**[!UICONTROL List commit builds]**

この検索モジュールは、プロジェクトの特定のコミットに対するビルドのリストを返します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>新しい接続を作成する方法については、この記事の <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] to Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>ビルドの一覧を表示するコミットを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> 検索対象を特定のステータスのビルドに制限するには、ステータスを選択します。このフィールドを空白のままにすると、コミットのすべてのビルドが返されます。  </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL List issues]**

この検索モジュールは、指定したフィルタリング設定に基づいてすべてのイシューを返します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[イシューを一覧表示](https://docs.gitlab.com/ee/api/issues.html#list-issues)を参照してください。

+++

+++**[!UICONTROL List Issues That Close on Merge]**

この検索モジュールは、指定した結合リクエストを結合することでクローズされるすべてのイシューを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[結合時にクローズするイシューを一覧表示](https://docs.gitlab.com/ee/api/merge_requests.html#list-issues-that-will-close-on-merge)を参照してください。

+++

+++**[!UICONTROL List Labels]**

この検索モジュールは、プロジェクトのすべてのラベルを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[ラベルを一覧表示](https://docs.gitlab.com/ee/api/labels.html#list-labels)を参照してください。

+++

+++**[!UICONTROL List merge requests]**

この検索モジュールは、フィルタリング設定に基づいてすべての結合リクエストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[結合リクエストを一覧表示](https://docs.gitlab.com/ee/api/merge_requests.html#list-merge-requests)を参照してください。

+++

+++**[!UICONTROL List Owned Projects]**

この検索モジュールは、認証済みユーザーが所有者として設定されているプロジェクトを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[ユーザーのプロジェクトを一覧表示](https://docs.gitlab.com/ee/api/projects.html#list-all-projects)を参照してください。

+++

+++**[!UICONTROL List project builds]**

この検索モジュールは、プロジェクト内のビルドのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのジョブを一覧表示](https://docs.gitlab.com/ee/api/jobs.html#list-project-jobs)を参照してください。

+++

+++**[!UICONTROL List project deployments]**

この検索モジュールは、プロジェクト内のデプロイメントのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのデプロイメントを一覧表示](https://docs.gitlab.com/ee/api/deployments.html#list-project-deployments)を参照してください。

+++

+++**[!UICONTROL List project issue notes]**

この検索モジュールは、単一のイシューに関するすべてのメモのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのイシューメモを一覧表示](https://docs.gitlab.com/ee/api/notes.html#list-project-issue-notes)を参照してください。

+++

+++**[!UICONTROL List project issues]**

この検索モジュールは、指定したプロジェクト内のすべてのイシューを返します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのイシューを一覧表示](https://docs.gitlab.com/ee/api/issues.html#list-project-issues)を参照してください。

+++

+++**[!UICONTROL List project milestones]**

この検索モジュールは、プロジェクト内のすべてのマイルストーンを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのマイルストーンを一覧表示](https://docs.gitlab.com/ee/api/milestones.html#list-project-milestones)を参照してください。

+++

+++**[!UICONTROL List project pipelines]**

この検索モジュールは、プロジェクトのすべてのパイプラインを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのパイプラインを一覧表示](https://docs.gitlab.com/ee/api/pipelines.html#list-project-pipelines)を参照してください。

+++

+++**[!UICONTROL List project repository tags]**

この検索モジュールは、プロジェクトからリポジトリタグのリストを取得し、名前で逆アルファベット順に並べ替えます。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトのリポジトリタグを一覧表示](https://docs.gitlab.com/ee/api/tags.html#list-project-repository-tags)を参照してください。

+++

+++**[!UICONTROL List project variables]**

この検索モジュールは、プロジェクトの変数のリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトの変数を一覧表示](https://docs.gitlab.com/ee/api/project_level_variables.html#list-project-variables)を参照してください。

+++

+++**[!UICONTROL List projects]**

この検索モジュールは、認証済みユーザーがメンバーであるすべてのプロジェクトを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[プロジェクトを一覧表示](https://docs.gitlab.com/ee/api/projects.html#list-all-projects)を参照してください。

+++

+++**[!UICONTROL List repository branches]**

このモジュールは、検索語でリポジトリブランチを検索します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリブランチを一覧表示](https://docs.gitlab.com/ee/api/branches.html#list-repository-branches)を参照してください。

+++

+++**[!UICONTROL List repository commits]**

この検索モジュールは、プロジェクト内のリポジトリのコミットのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリのコミットを一覧表示](https://docs.gitlab.com/ee/api/commits.html#list-repository-commits)を参照してください。

+++

+++**[!UICONTROL List repository contributors]**

この検索モジュールは、リポジトリのコントリビューターのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[コントリビューター](https://docs.gitlab.com/ee/api/repositories.html#contributors)を参照してください。

+++

+++**[!UICONTROL List repository tree]**

この検索モジュールは、プロジェクト内のリポジトリファイルとディレクトリのリストを取得します。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの[リポジトリツリーを一覧表示](https://docs.gitlab.com/ee/api/repositories.html#list-repository-tree)を参照してください。

+++

+++**[!UICONTROL Mark a todo as done]**

このアクションモジュールは、現在のユーザーの ID で指定された単一の保留中の TODO 項目を完了としてマークします。

フィールドについて詳しくは、[!DNL GitLab] ドキュメントの [TODO 項目を完了としてマーク](https://docs.gitlab.com/ee/api/todos.html#mark-a-todo-as-done)を参照してください。

+++

+++**[!UICONTROL Modify existing issue note]**

イシューの既存のメモを変更します。

フィールドについては、[!DNL GitLab] ドキュメントの[既存のイシューメモを変更](https://docs.gitlab.com/ee/api/notes.html#modify-existing-issue-note)を参照してください。

+++

+++**[!UICONTROL Modify existing merge request note]**

結合リクエストの既存のメモを変更します。

フィールドについては、[!DNL GitLab] ドキュメントの[既存の結合リクエストのメモを変更](https://docs.gitlab.com/ee/api/notes.html#modify-existing-merge-request-note)を参照してください。

+++

+++**[!UICONTROL Modify existing snippet note]**

このアクションモジュールは、スニペットの既存のメモを変更します。

フィールドについては、[!DNL GitLab] ドキュメントの[既存のスニペットメモを変更](https://docs.gitlab.com/ee/api/notes.html#modify-existing-snippet-note)を参照してください。

+++

+++**[!UICONTROL New issue]**

このアクションモジュールは、新しいプロジェクトイシューを作成します。

フィールドについては、[!DNL GitLab] ドキュメントの[新しいイシュー](https://www.integromat.com/en/help/app/gitlab)を参照してください。

+++

+++**[!UICONTROL Play a build]**

このアクションモジュールは、ジョブを開始する手動アクションをトリガーします。

フィールドについては、[!DNL GitLab] ドキュメントの[ジョブを再生](https://docs.gitlab.com/ee/api/jobs.html#play-a-job)を参照してください。

+++

+++**[!UICONTROL Post comment to commit]**

このアクションモジュールは、コミットにコメントを追加します。

フィールドについては、[!DNL GitLab] ドキュメントの[コミットにコメントを投稿](https://docs.gitlab.com/ee/api/commits.html#post-comment-to-commit)を参照してください。

+++

+++**[!UICONTROL Remove variable]**

このアクションモジュールは、プロジェクトの変数を削除します。

フィールドについては、[!DNL GitLab] ドキュメントの[変数を削除](https://docs.gitlab.com/ee/api/project_level_variables.html#remove-variable)を参照してください。

+++

+++**[!UICONTROL Retry a build]**

このアクションモジュールは、コミットで単一のビルドを再試行します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>新しい接続を作成する方法については、この記事の <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] to Workfront Fusion]</a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>再試行するビルドを含むプロジェクトを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td> 再試行するビルドを選択します。 </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Retry Failed Jobs in a Pipeline]**

このアクションモジュールは、パイプラインの失敗したビルドを再試行します。

フィールドについては、[!DNL GitLab] ドキュメントの[パイプラインのジョブを再試行](https://docs.gitlab.com/ee/api/pipelines.html#retry-jobs-in-a-pipeline)を参照してください。

+++

+++**[!UICONTROL Get a Variable]**

このモジュールは、プロジェクトの特定の変数の詳細を取得します。

フィールドについては、[!DNL GitLab] ドキュメントの[変数の詳細を表示](https://docs.gitlab.com/ee/api/project_level_variables.html#show-variable-details)を参照してください。

+++

+++**[!UICONTROL Update a release]**

このアクションモジュールは、リリースを更新します。

フィールドについては、[!DNL GitLab] ドキュメントの[リリースを更新](https://docs.gitlab.com/ee/api/releases/#update-a-release)を参照してください。

+++

+++**[!UICONTROL Update merge request]**

このアクションモジュールは、既存の結合リクエストを更新します。ターゲットのブランチやタイトルを変更したり、MR を閉じたりすることもできます。

フィールドについては、[!DNL GitLab] ドキュメントの[結合リクエストを更新](https://docs.gitlab.com/ee/api/merge_requests.html#update-mr)を参照してください。

+++

+++**[!UICONTROL Update a Variable]**

このアクションモジュールは、プロジェクトの変数を更新します。

フィールドについては、[!DNL GitLab] ドキュメントの[変数を更新](https://docs.gitlab.com/ee/api/project_level_variables.html#update-variable)を参照してください。

+++
