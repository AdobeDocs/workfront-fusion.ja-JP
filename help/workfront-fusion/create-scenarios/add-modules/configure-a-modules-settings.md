---
title: モジュールの設定
description: 作成するモジュールごとに設定を指定する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: ae82d1fe-31e1-424a-9c1a-42dc1a20b749
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 36%

---

# モジュールの設定

作成するモジュールごとに設定を指定する必要があります。

例えば、Workfront/ドキュメントをアップロード モジュールでは、ドキュメントをアップロードするレコードを指定する必要があります。

>[!NOTE]
>
>モジュール設定の他に、シナリオの設定を調整することもできます。シナリオの名前を変更したり、スケジュールを変更したり、他のアクションの中で追加の設定を指定したりできます。

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
   <td> <p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## モジュール設定を指定

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. シナリオに新しいモジュールを追加。

   または

   設定するモジュールをクリックします。

1. モジュールで必要な場合は、**[!UICONTROL 接続の概要]** に記載されているように、指定したサービスに登録済みのユーザーアカウントに [ 接続 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md) を作成します。
1. 各フィールドに、適切なテキストを入力します。

   または

   前のモジュールからの出力をフィールドにマッピングします。

   マッピングについて詳しくは、[ マッピングの概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md) を参照してください。

   Workfront Fusion で認識できる様々な項目データタイプ（日付、数値、テキストなど）について詳しくは、[ 項目データタイプ ](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md) を参照してください。

   >[!NOTE]
   >
   >太字のパラメーターは必須です。

1. （条件付き）モジュールに、表示および使用する詳細オプションがある場合、「**[!UICONTROL 詳細設定を表示]**」を選択します。
