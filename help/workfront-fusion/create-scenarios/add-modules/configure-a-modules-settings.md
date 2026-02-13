---
title: モジュールの設定
description: 作成するモジュールごとに設定を指定する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: ae82d1fe-31e1-424a-9c1a-42dc1a20b749
source-git-commit: a871a130a1ac023dcb4ce8da7241918da2431d3a
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 60%

---

# モジュールの設定

作成するモジュールごとに設定を指定する必要があります。

例えば、Workfront/ドキュメントをアップロード モジュールでは、ドキュメントをアップロードするレコードを指定する必要があります。

>[!NOTE]
>
>モジュール設定の他に、シナリオの設定を調整することもできます。シナリオの名前を変更したり、スケジュールを変更したり、他のアクションの中で追加の設定を指定したりできます。

## アクセス要件

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
   <p>組織が Workfront Automation および Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## モジュール設定を指定

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. フィルターを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. シナリオに新しいモジュールを追加。

   または

   設定するモジュールをクリックします。

1. モジュールで必要な場合は、**[!UICONTROL 接続の概要]** に記載されているように、指定したサービスに登録済みのユーザーアカウントに [&#x200B; 接続 &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md) を作成します。
1. 各フィールドに、適切なテキストを入力します。

   または

   前のモジュールからの出力をフィールドにマッピングします。

   マッピングについて詳しくは、[&#x200B; マッピングの概要 &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md) を参照してください。

   Workfront Fusion で認識できる様々な項目データタイプ（日付、数値、テキストなど）について詳しくは、[&#x200B; 項目データタイプ &#x200B;](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md) を参照してください。

   >[!NOTE]
   >
   >太字のパラメーターは必須です。

1. （条件付き）モジュールに、表示および使用する詳細オプションがある場合、「**[!UICONTROL 詳細設定を表示]**」を選択します。
