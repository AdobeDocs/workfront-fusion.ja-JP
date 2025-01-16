---
title: SDL Managed Translation モジュール
description: ' [!DNL Adobe Workfront Fusion]  のシナリオでは、SDL Managed Translation アカウントをサードパーティの複数のアプリケーションとサービスに接続できます。'
author: Becky
feature: Workfront Fusion
exl-id: 41953b04-9011-4ddb-9f53-cdf11e807e04
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 89%

---

# [!DNL SDL Managed Translation] モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL SDL Managed Translation] アカウントを複数のサードパーティのアプリケーションとサービスに接続できます。

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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

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

#### [!UICONTROL Download Translated File]

このモジュールは、指定されたプロジェクトに含まれる、1 つの翻訳済みファイルの内容を取得します。要求されたファイルがダウンロードのステータスになっていない場合、ファイルの内容がまだ完全に翻訳されていない可能性があります。ファイルがダウンロードのステータスであり、そのファイルを正常に取得した場合は、必ず `Cancel or Complete File` メソッドを使用してファイルを完了としてマークしてください。

#### [!UICONTROL Upload a File]

このモジュールでは、翻訳用のファイル、または翻訳プロジェクトに含めるファイルを参照資料としてアップロードできます。アップロードは multipart/form-data を使用して送信する必要があり、ファイルを複数含めることができます。アップロードされたファイルの評価に使用する `ProjectOptionId` を指定します。これにより、アップロードする各ファイルが翻訳の候補として考えられるか、参照資料として処理する必要があるかが決まります。アーカイブ（`zip `、`rar`、`7z`、`tar` ファイル）の場合、アプリはアーカイブの内容を調べ、アーカイブ全体を翻訳できるかどうか、または翻訳可能なファイルと翻訳不可のファイルが混在しているかどうかを示します。

>[!NOTE]
>
>一度に複数のファイルをアップロードすることは、エラーの影響を大きくする可能性があるので、お勧めしません。

#### [!UICONTROL Add a Reference File]

このモジュールは、参照ファイルを追加します。

### プロジェクト

#### [!UICONTROL Create a project]

このモジュールは、指定されたプロジェクトを作成します。

#### プロジェクトをキャンセルまたは完了

このモジュールは、指定されたプロジェクトをキャンセルまたは完了します。プロジェクトがダウンロード待ちの場合、プロジェクトはワークフローの最終ステップを経て遷移し、最終的に完了に移ります。プロジェクトが承認待ちの場合、またはベンダーの選択がキャンセルされた場合。プロジェクトがその他のステータスの場合、リクエストは失敗します。

#### [!UICONTROL Download Project Zip]

このモジュールは、指定されたプロジェクトの翻訳済みファイルの `zip` ファイルを取得します。

#### [!UICONTROL Read a Project]

このモジュールは、指定されたプロジェクトを取得します。

#### [!UICONTROL Get Projects at Status]

このモジュールは、指定されたステータスにあるすべての使用可能なプロジェクトを取得します。このメソッドでは、`$top`、`$skip` および `$orderby` のクエリパラメーターを指定することで、結果をページ分割することができます。

#### [!UICONTROL Get Projects List]

すべてのプロジェクトの単純なリストを取得し、各プロジェクトに関する一般情報を提供します。このメソッドでは、`$top`、`$skip` および `$orderby` のクエリパラメーターを指定することで、結果をページ分割することができます。

#### [!UICONTROL Search Project Creation Options]

このモジュールは、プロジェクト作成オプションを取得します。

### その他

#### [!UICONTROL Make an API Call]

このモジュールは、許可された任意の API 呼び出しを実行します。
