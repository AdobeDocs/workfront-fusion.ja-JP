---
title: シナリオへのモジュールの追加
description: この記事では、シナリオにモジュールを追加する基本的なプロセスについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
source-git-commit: 860209fdcf2e7707663cc2d454c0499972b1261e
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 5%

---

# シナリオへのモジュールの追加

シナリオは、アプリ内でデータを変換する方法や、アプリと web サービスの間でデータを転送する方法を示す一連のモジュールで構成されます。 モジュールを作成するには、モジュールを追加および設定します。

この記事では、シナリオにモジュールを追加する基本的なプロセスについて説明します。 シナリオの追加方法について詳しくは、[ モジュールの追加：記事インデックス ](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md) の他の記事を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス</td> 
   <td> <p>新規：[!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在：[!DNL Workfront Fusion] ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：[!DNL Adobe Workfront Fusion] を購入してください。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## シナリオへの最初のモジュールの追加

シナリオの最初のモジュールは、通常、トリガーモジュールです。

トリガーモジュールについて詳しくは、「モジュールの概要」の [トリガーモジュール ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) を参照してください。

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 画面の右上隅にある「**新しいシナリオを作成**」をクリックして、シナリオの作成を開始します。

   シナリオエディターが開き、プレースホルダー（疑問符）モジュールと使用可能なコネクタのリストが表示されます。

   ![ プレースホルダーモジュール ](assets/placeholder-module.png)

1. このシナリオを開始するコネクタまたは Webhook を選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定手順については、「[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)」にリストされている選択したアプリケーションの記事を参照してください。

>[!NOTE]
>
>シナリオから最初のモジュールを削除し、それを置き換える場合は、プレースホルダー（疑問符）モジュールをクリックして、コネクタのリストを開きます。

## シナリオに別のモジュールを追加

1. モジュールを追加するシナリオのシナリオエディターを開いていない場合は、左パネルの **[!UICONTROL シナリオ]** タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. 別のモジュールにモジュールを追加するには、モジュールの右側のハンドルをポイントして、そのハンドルの後にモジュールを追加します。次に、表示されたら **別のモジュールを追加** をクリックします。

   コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストの **別のモジュールを追加** をクリックしてから、コネクタを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定手順については、「[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)」にリストされている選択したアプリケーションの記事を参照してください。

## シナリオ内の既存のモジュール間にモジュールを挿入します

1. モジュールを追加するシナリオのシナリオエディターを開いていない場合は、左パネルの **[!UICONTROL シナリオ]** タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. モジュールを挿入するモジュール間の点線パスをクリックします。
1. 表示されるメニューで、「**モジュールを追加**」を選択します。

コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストの **別のモジュールを追加** をクリックしてから、コネクタを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定手順については、「[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)」にリストされている選択したアプリケーションの記事を参照してください。
