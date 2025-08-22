---
title: MariaDB モジュール
description: Adobe Workfront Fusion のシナリオでは、 [!DNL MariaDB] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりすることができます。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 41179cfe-c0f9-4d18-ab7e-374670ac688b
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 71%

---

# [!DNL MariaDB] モジュール

Adobe Workfront Fusion のシナリオでは、[!DNL MariaDB] を使用するワークフローを自動化したり、複数のサードパーティのアプリケーションやサービスに接続したりできます。

シナリオの作成方法については、[ シナリオの作成：記事のインデックス ](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md) の記事を参照してください。

モジュールについて詳しくは、「[ モジュール：記事インデックス ](/help/workfront-fusion/references/modules/modules-toc.md)」の記事を参照してください。

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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## 前提条件

[!DNL MariaDB] モジュールを使用するには、[!DNL MariaDB] アカウントが必要です。

## [!DNL MariaDB] を Workfront Fusion に接続

[!DNL MariaDB] アカウントへの接続を、[!DNL MariaDB] モジュール内から直接作成できます。

1. 任意の [!DNL MariaDB] モジュールで、「[!UICONTROL 接続]」フィールドの横にある「**[!UICONTROL 追加]**」をクリックします。
1. 次のフィールドを設定します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>新しい接続の名前を入力します。</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>この接続を実稼動環境と非実稼動環境のどちらで使用するかを選択します。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>サービスアカウントと個人アカウントのどちらに接続するかを選択します。</td>
        </tr>
     <tr> 
      <td role="rowheader">[!UICONTROL Host]</td> 
      <td> <p>データベースインスタンスの IP アドレスまたはホスト名を入力します。このホストは、ネットワークの外部からアクセスできる必要があります。</p> <p>例： <code>[!DNL mariadb.hwoh2j5h.us-east-1.rds.amazon.com]</code></p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Port]</td> 
      <td>デフォルトのポートは 3306 です。非標準のポートを使用している場合は、この番号をポートに設定します。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL データベース ]</td> 
      <td>操作するデータベースの名前を入力します。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL User]</td> 
      <td>ユーザー名を入力してください.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Password]</td> 
      <td>パスワードを入力します。</td> 
     </tr> 
    </tbody> 
   </table>

1. 「**[!UICONTROL 続行]**」をクリックして接続を作成し、モジュールに戻ります。

## [!DNL MariaDB] モジュールとそのフィールド

[!DNL MariaDB] モジュールを設定すると、Workfront Fusion には以下のフィールドが表示されます。これらとともに、アプリやサービスのアクセスレベルなどの要因に応じて、追加の「[!DNL MariaDB]」フィールドが表示される場合があります。モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### クエリの実行（上級）

このアクションモジュールは、指定したクエリに基づいて、データベースから情報を取得します。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL MariaDB] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL MariaDB] の接続 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>モジュールがデータの取得に使用する SQL クエリを入力します。</p> <p>重要：クエリで使用される変数は不要部分が削除されていません。SQL 挿入を防ぐために、変数の不要部分を適切に削除してください。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL テーブルから行を選択（上級）]

このモジュールは、データベースからレコードを読み取ります。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>[!DNL MariaDB] アカウントをWorkfront Fusion に接続する手順については、この記事の <a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">Workfront Fusion への [!DNL MariaDB] の接続 </a> を参照してください。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table]</td> 
   <td> <p>読み取るレコードがあるテーブルを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>行の選択に使用するフィルターを設定します。</p> 
    <ul> 
     <li> <p>検索の基準となるフィールドを選択</p> </li> 
     <li> <p>検索に使用する演算子を選択</p> </li> 
     <li> <p>検索する値を入力またはマッピング</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort] </td> 
   <td> <p>結果を並べ替える各レベルで「<strong>[!UICONTROL Add item]</strong>」をクリックし、次に、結果の並べ替えの基準となるフィールドを選択し、昇順または降順のどちらで並べ替えるかを選択します。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>各シナリオの実行サイクル中に、モジュールが返すレコードの最大数を入力またはマッピングします。</p> </td> 
  </tr> 
 </tbody> 
</table>
