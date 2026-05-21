---
title: シナリオへのモジュールの追加
description: この記事では、シナリオにモジュールを追加する基本的なプロセスについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
TQID: https://experienceleague.adobe.com/R2JCX7aaYzmYHgiLqj1WDlVFHI-s-qanltoOrycQ5JU
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 684
ht-degree: 18%

---

# シナリオへのモジュールの追加

シナリオは、アプリ内でのデータの変換方法や、アプリと web サービスの間でのデータの転送方法を示す、一連のモジュールで構成されます。 モジュールを作成するには、モジュールを追加および設定します。

この記事では、シナリオにモジュールを追加する基本的なプロセスについて説明します。 シナリオの追加方法について詳しくは、[ モジュールの追加：記事インデックス ](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md)の他の記事を参照してください。

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

## シナリオへの最初のモジュールの追加

シナリオの最初のモジュールは、通常、トリガーモジュールです。

トリガーモジュールについて詳しくは、「モジュールの概要」の「[トリガーモジュール ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)」を参照してください。

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 画面の右上隅にある「**新しいシナリオを作成**」をクリックして、シナリオの作成を開始します。

   シナリオエディターが開き、プレースホルダー（疑問符）モジュールと使用可能なコネクタのリストが表示されます。

   ![ プレースホルダーモジュール ](assets/placeholder-module.png)

1. このシナリオを開始するコネクタまたはWebhookを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>シナリオから最初のモジュールを削除し、置き換える場合は、プレースホルダー（疑問符）モジュールをクリックしてコネクタのリストを開きます。

## シナリオへの別のモジュールの追加

1. モジュールを追加するシナリオのシナリオエディターを使用していない場合は、左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. モジュールを別のモジュールに追加するには、モジュールを追加するモジュールの右側のハンドルにカーソルを合わせ、表示されたら「**別のモジュールを追加**」をクリックします。

   コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストで「**別のモジュールを追加**」をクリックし、コネクタを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

## シナリオ内の既存のモジュール間にモジュールを挿入する

1. モジュールを追加するシナリオのシナリオエディターを使用していない場合は、左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. モジュールを挿入するモジュール間の点線パスをクリックします。
1. 表示されるメニューで、**モジュールを追加**&#x200B;を選択します。

コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストで「**別のモジュールを追加**」をクリックし、コネクタを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>特定のモジュールへのリンクを作成するには、次のページを表示するときにURLに`?moduleId=<module-id>`を追加します。
>
>* シナリオ編集ページ （URLの末尾は`/edit`）
>* 特定のシナリオの実行（URLの末尾は`/logs/<log-id>`）
>
>`<module-id>`は、シナリオを表示する際に、モジュールラベルの横にある番号を参照します。
>
>これは、シナリオのデバッグやモジュール設定のコピーに役立ちます。
