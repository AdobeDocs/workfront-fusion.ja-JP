---
title: SDL Managed Translation モジュール
description: Adobe Workfront Fusion のシナリオでは、SDL Managed Translation アカウントを複数のサードパーティ製アプリケーションおよびサービスに接続できます。
author: Becky
feature: Workfront Fusion
exl-id: 41953b04-9011-4ddb-9f53-cdf11e807e04
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 71%

---

# [!DNL SDL Managed Translation] モジュール

Adobe Workfront Fusion シナリオでは、[!DNL SDL Managed Translation] アカウントを複数のサードパーティのアプリケーションやサービスに接続できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクタベース（従来）：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[&#x200B; ドキュメントのアクセス要件 &#x200B;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス &#x200B;](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## SDL Managed Translation API の情報

SDL Managed Translation コネクタでは、以下を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td>https://languagecloud.sdl.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v1.4.26</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL SDL Managed Translation] モジュール

>[!NOTE]
>
>[!DNL SDL Managed Translation] の呼び出し操作のタイムアウトは **120 秒**&#x200B;です。

### ファイル

#### [!UICONTROL 翻訳済みファイルをダウンロード]

このモジュールは、指定されたプロジェクトに含まれる、1 つの翻訳済みファイルの内容を取得します。要求されたファイルがダウンロードのステータスになっていない場合、ファイルの内容がまだ完全に翻訳されていない可能性があります。ファイルがダウンロードのステータスであり、そのファイルを正常に取得した場合は、必ず `Cancel or Complete File` メソッドを使用してファイルを完了としてマークしてください。

#### [!UICONTROL ファイルをアップロード]

このモジュールでは、翻訳用のファイル、または翻訳プロジェクトに含めるファイルを参照資料としてアップロードできます。アップロードは multipart/form-data を使用して送信する必要があり、ファイルを複数含めることができます。アップロードされたファイルの評価に使用する `ProjectOptionId` を指定します。これにより、アップロードする各ファイルが翻訳の候補として考えられるか、参照資料として処理する必要があるかが決まります。アーカイブ（`zip `、`rar`、`7z`、`tar` ファイル）の場合、アプリはアーカイブの内容を調べ、アーカイブ全体を翻訳できるかどうか、または翻訳可能なファイルと翻訳不可のファイルが混在しているかどうかを示します。

>[!NOTE]
>
>一度に複数のファイルをアップロードすることは、エラーの影響を大きくする可能性があるので、お勧めしません。

#### [!UICONTROL 参照ファイルを追加]

このモジュールは、参照ファイルを追加します。

### プロジェクト

#### [!UICONTROL プロジェクトの作成]

このモジュールは、指定されたプロジェクトを作成します。

#### プロジェクトをキャンセルまたは完了

このモジュールは、指定されたプロジェクトをキャンセルまたは完了します。プロジェクトがダウンロード待ちの場合、プロジェクトはワークフローの最終ステップを経て遷移し、最終的に完了に移ります。プロジェクトが承認待ちの場合、またはベンダーの選択がキャンセルされた場合。プロジェクトがその他のステータスの場合、リクエストは失敗します。

#### [!UICONTROL プロジェクト Zip をダウンロード]

このモジュールは、指定されたプロジェクトの翻訳済みファイルの `zip` ファイルを取得します。

#### [!UICONTROL プロジェクトの読み取り]

このモジュールは、指定されたプロジェクトを取得します。

#### [!UICONTROL 特定ステータスのプロジェクトの取得]

このモジュールは、指定されたステータスにあるすべての使用可能なプロジェクトを取得します。このメソッドでは、`$top`、`$skip` および `$orderby` のクエリパラメーターを指定することで、結果をページ分割することができます。

#### [!UICONTROL プロジェクトリストの取得]

すべてのプロジェクトの単純なリストを取得し、各プロジェクトに関する一般情報を提供します。このメソッドでは、`$top`、`$skip` および `$orderby` のクエリパラメーターを指定することで、結果をページ分割することができます。

#### [!UICONTROL プロジェクト作成オプションの検索]

このモジュールは、プロジェクト作成オプションを取得します。

### その他

#### [!UICONTROL API 呼び出しの実行]

このモジュールは、許可された任意の API 呼び出しを実行します。
