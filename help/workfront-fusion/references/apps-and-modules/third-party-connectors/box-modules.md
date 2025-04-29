---
title: Box モジュール
description: ' [!DNL Adobe Workfront Fusion]  シナリオでは、Box を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりすることができます。指定されたフォルダーを監視して、ファイルの変更を確認したり、既存のファイルを変更および削除したり、新しいファイルをフォルダーにアップロードしたりします。'
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: f02c4df01c7fad6bb9cdf4911512eef97e71c82b
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 69%

---

# Box モジュール

[!DNL Adobe Workfront Fusion] のシナリオでは、[!DNL Box] を使用するワークフローを自動化したり、複数のサードパーティアプリケーションやサービスに接続したりできます。指定されたフォルダーを監視して、ファイルの変更を確認したり、既存のファイルを変更および削除したり、新しいファイルをフォルダーにアップロードしたりします。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。 モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンス要件なし</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## 前提条件

[!DNL Box] モジュールを使用するには、[!DNL Box] アカウントが必要です。

## Box API 情報

ボックスコネクタでは、次の機能を使用します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">ベース URL</td> 
   <td> https://api.box.com/2.0
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API バージョン</td> 
   <td> v2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API タグ</td> 
   <td>v3.0.3</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Box] モジュールとそのフィールド

[!DNL Box] モジュールを設定する際、[!DNL Workfront Fusion] に以下のフィールドが表示されます。これらに加えて、アプリまたはサービスのアクセスレベルなどの要因に応じて、追加の [!DNL Box] フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [トリガー](#triggers)
* [アクション](#actions)

### トリガー

* [[!UICONTROL 新しいイベント]](#new-event)
* [[!UICONTROL ファイルを監視]](#watch-files)

#### [!UICONTROL 新しいイベント]

このインスタントトリガーモジュールは、ファイルが追加、移動、コピー、削除、ロックまたはロック解除されたときにシナリオを開始します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>送信メッセージの監視に使用する web フックを選択します。Web フックを追加するには、「<strong>[!UICONTROL Add]</strong>」をクリックして、web フックの名前と接続を入力します。</p> <p> [!UICONTROL Box] アカウントを [!UICONTROL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref"> サービスへの接続 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Maximum number of returned events]</p> </td> 
   <td> <p>各シナリオの実行サイクル中にモジュールが返すイベントの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを監視]

このトリガーモジュールは、新しいファイルが追加されたとき、または既存のファイルが監視対象のフォルダー内で更新されたときに、シナリオを開始します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">接続</td> 
   <td> <p>[!DNL Box] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">フォルダー</td> 
   <td> <p>監視するフォルダーを選択します。 シナリオでは、1 つのフォルダーを監視できます。</p> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">監視</td> 
   <td> <p>監視するファイルのタイプを選択します。</p> 
    <ul> 
     <li> <p><strong>新しいファイルのみ</strong> </p> <p>新しいファイルが追加されると、シナリオが開始します。</p> </li> 
     <li> <p><strong>新しいファイルとすべての変更</strong> </p> <p>このシナリオは、ファイルが追加されたとき、またはファイルの内容やファイル属性（名前など）が変更されたときに開始されます。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ダウンロードされたファイルの最大数</p> </td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すファイルの最大数を入力します。</p> </td> 
  </tr> 
 </tbody> 
</table>

### アクション

* [[!UICONTROL ファイルを削除]](#delete-a-file)
* [[!UICONTROL ファイルを取得]](#get-a-file)
* [[!UICONTROL ファイルを更新]](#update-a-file)
* [ファイルを[!UICONTROL アップロード]](#upload-a-file)

#### [!UICONTROL ファイルを削除]

ファイルを削除するアクションモジュールです。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>モジュールで削除するファイルの一意の ID を入力またはマップします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルの取得]

このアクションモジュールは、ファイルをダウンロードします。

ファイルの ID を指定します。

>[!NOTE]
>
>このモジュールは、後続のモジュールにファイルを提供するのに役立ちます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>モジュールで取得するファイルの一意の ID を入力またはマッピングします。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルを更新]

ファイルを更新するアクションモジュールです。

ファイルの ID を指定します。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>モジュールを更新するファイルの一意の ID を入力またはマッピングします。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL ファイルをアップロード]

ファイルをアップロードするアクションモジュールです。

ファイルを指定します。また、ファイルの新しいファイル名を指定することもできます。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>[!DNL Box] アカウントを [!DNL Workfront Fusion] に接続する手順については、<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">[!DNL Adobe Workfront Fusion] への接続の作成 – 基本手順 </a> を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>ファイルをアップロードするフォルダーを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>以前のモジュールで使用したソースファイルを選択するか、ソースファイルの名前とデータをマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>このモジュールが正常に動作しない場合は、次の点を考慮してください。
>
>* ファイルのサイズが [!DNL Box] プランでのファイルサイズの上限を超えているか、[!DNL Box] アカウントのストレージ割り当てをすべて使用している可能性があります。ストレージスペースを増やすには、[!DNL Box] から既存のファイルを削除するか、[!DNL Box] アカウントをアップグレードしてください。
>* [!DNL Box] では、同じ名前の複数のファイルは 1 つのフォルダーにアップロードされません。アップロード先のフォルダーにアップロードするファイルと同じ名前のファイルが含まれている場合、シナリオの実行はエラーで終了します。この問題を回避するには、ファイルの名前を変更します。ファイルを更新する場合は、**[!UICONTROL ファイルを更新]**&#x200B;モジュールを使用します。
