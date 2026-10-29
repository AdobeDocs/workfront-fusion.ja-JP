---
title: シナリオへのモジュールの追加
description: この記事では、シナリオにモジュールを追加する基本的なプロセスについて説明します。
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
TQID: 'https://experienceleague.adobe.com/R2JCX7aaYzmYHgiLqj1WDlVFHI-s-qanltoOrycQ5JU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '1508'
ht-degree: 8%
---
# シナリオへのモジュールの追加

シナリオは、アプリ内でのデータの変換方法や、アプリと web サービスの間でのデータの転送方法を示す、一連のモジュールで構成されます。 モジュールを作成するには、モジュールを追加および設定します。

この記事では、シナリオにモジュールを追加する基本的なプロセスについて説明します。 シナリオの追加方法について詳しくは、[&#x200B; モジュールの追加：記事インデックス &#x200B;](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md)の他の記事を参照してください。

>[!NOTE]
>
>Workfront Fusionは、シナリオエディターを新しいエクスペリエンスに移行中です。 この移行中は、従来のエクスペリエンスと新しいエクスペリエンスの両方を利用でき、いつでも切り替えることができます。 新しいエクスペリエンスを使用することをお勧めします。 詳しくは、シナリオエディターの記事「[新しいエクスペリエンスと従来のエクスペリエンス &#x200B;](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)」を参照してください。

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

トリガーモジュールについて詳しくは、「モジュールの概要」の「[トリガーモジュール &#x200B;](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)」を参照してください。

* [新しいエクスペリエンスに最初のモジュールを追加する（推奨）](#add-the-first-module-in-the-new-experience-recommended)
* [クラシックエクスペリエンスに最初のモジュールを追加する](#add-the-first-module-in-the-classic-experience)

### 新しいエクスペリエンスに最初のモジュールを追加する（推奨）

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 画面の右上隅にある「**新しいシナリオを作成**」をクリックして、シナリオの作成を開始します。

   シナリオエディターが開き、プレースホルダーモジュールと使用可能なコネクタのリストが表示されます。

   ![&#x200B; プレースホルダーモジュール &#x200B;](/help/workfront-fusion/build-practice-scenarios/assets/new-placeholder-module.png)

   ![&#x200B; アプリとサービス ピッカー](/help/workfront-fusion/build-practice-scenarios/assets/new-connector-picker.png)

1. このシナリオを開始するコネクタまたはWebhookを選択します。

   * 左側のパネル（[!UICONTROL お気に入り]、[!UICONTROL すべてのアプリケーション &#x200B;]、[!UICONTROL Adobe Workfront]、[!UICONTROL Adobe Firefly Services]、[!UICONTROL Adobe Creativeとコンテンツ &#x200B;]、[!UICONTROL Adobe Cloud Services]、[!UICONTROL 生成AI]、または[!UICONTROL 組み込み]）を使用してカテゴリ別に参照するか、
   * 検索ボックスに語句を入力します。 入力すると結果が更新され、コネクタの一致はモジュール名と説明の一致の前に一覧表示されます。

1. シナリオに追加するモジュールをクリックします。

1. モジュールを設定します。

   モジュールの設定は、カンバスの右側にあるパネルで開きます。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>* コネクターのリストでは、バッジによってプライベートアプリ、プレミアムアプリ、ベータ版アプリが識別されます。
>* 大規模なアプリ用のモジュールは、グループ化されています。
>* エラーハンドラーを追加すると、最初にディレクティブがリストされます。
>* コネクタに複数のバージョンがある場合は、コネクタを選択した後にバージョンを選択できます。

>[!NOTE]
>
>シナリオから最初のモジュールを削除し、置き換える場合は、プレースホルダーモジュールをクリックしてコネクタのリストを開きます。

### クラシックエクスペリエンスに最初のモジュールを追加する

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. 画面の右上隅にある「**新しいシナリオを作成**」をクリックして、シナリオの作成を開始します。

   シナリオエディターが開き、プレースホルダー（疑問符）モジュールと使用可能なコネクタのリストが表示されます。

   ![&#x200B; プレースホルダーモジュール &#x200B;](assets/placeholder-module.png)

1. このシナリオを開始するコネクタまたはWebhookを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>シナリオから最初のモジュールを削除し、置き換える場合は、プレースホルダー（疑問符）モジュールをクリックしてコネクタのリストを開きます。

## シナリオへの別のモジュールの追加

* [新しいエクスペリエンスに別のモジュールを追加（推奨）](#add-another-module-in-the-new-experience-recommended)
* [クラシックエクスペリエンスに別のモジュールを追加する](#add-another-module-in-the-classic-experience)

### 新しいエクスペリエンスに別のモジュールを追加（推奨）

1. モジュールを追加するシナリオのシナリオエディターを使用していない場合は、左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. 別のモジュールの後にモジュールを追加するには、モジュールを追加するモジュールの右端にカーソルを合わせ、表示されたら「**別のモジュールを追加**」をクリックします。

   コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストで「**別のモジュールを追加**」をクリックし、コネクタを選択します。

   * 左側のパネル（[!UICONTROL お気に入り]、[!UICONTROL すべてのアプリケーション &#x200B;]、[!UICONTROL Adobe Workfront]、[!UICONTROL Adobe Firefly Services]、[!UICONTROL Adobe Creativeとコンテンツ &#x200B;]、[!UICONTROL Adobe Cloud Services]、[!UICONTROL 生成AI]、または[!UICONTROL 組み込み]）を使用してカテゴリ別に参照するか、
   * 検索ボックスに語句を入力します。 入力すると結果が更新され、コネクタの一致はモジュール名と説明の一致の前に一覧表示されます。

1. シナリオに追加するモジュールをクリックします。

1. モジュールを設定します。

   モジュールの設定は、カンバスの右側にあるパネルで開きます。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

### クラシックエクスペリエンスに別のモジュールを追加する

1. モジュールを追加するシナリオのシナリオエディターを使用していない場合は、左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. モジュールを別のモジュールに追加するには、モジュールを追加するモジュールの右側のハンドルにカーソルを合わせ、表示されたら「**別のモジュールを追加**」をクリックします。

   コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストで「**別のモジュールを追加**」をクリックし、コネクタを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

## シナリオ内の既存のモジュール間にモジュールを挿入する

* [新しいエクスペリエンスへのモジュールの挿入（推奨）](#insert-a-module-in-the-new-experience-recommended)
* [クラシックエクスペリエンスにモジュールを挿入する](#insert-a-module-in-the-classic-experience)

### 新しいエクスペリエンスへのモジュールの挿入（推奨）

1. モジュールを追加するシナリオのシナリオエディターを使用していない場合は、左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. モジュールを挿入するモジュール間のパスを右クリックし、**モジュールを追加**&#x200B;を選択します。

   ![既存のモジュール間にモジュールを追加](assets/add-a-module-between-modules.png)

   コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストで「**別のモジュールを追加**」をクリックし、コネクタを選択します。

   * 左側のパネル（[!UICONTROL お気に入り]、[!UICONTROL すべてのアプリケーション &#x200B;]、[!UICONTROL Adobe Workfront]、[!UICONTROL Adobe Firefly Services]、[!UICONTROL Adobe Creativeとコンテンツ &#x200B;]、[!UICONTROL Adobe Cloud Services]、[!UICONTROL 生成AI]、または[!UICONTROL 組み込み]）を使用してカテゴリ別に参照するか、
   * 検索ボックスに語句を入力します。 入力すると結果が更新され、コネクタの一致はモジュール名と説明の一致の前に一覧表示されます。

1. シナリオに追加するモジュールをクリックします。

1. モジュールを設定します。

   モジュールの設定は、カンバスの右側にあるパネルで開きます。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>特定のモジュールへのリンクを作成するには、次のページを表示するときにURLに`?moduleId=<module-id>`を追加します。
>
>* シナリオ編集ページ （URLの末尾は`/edit`）
>* 特定のシナリオ実行（URLの末尾は`/logs/<log-id>`）
>
>`<module-id>`は、シナリオを表示する際に、モジュールラベルの横にある番号を参照します。
>
>これは、シナリオのデバッグやモジュール設定のコピーに役立ちます。

### クラシックエクスペリエンスにモジュールを挿入する

1. モジュールを追加するシナリオのシナリオエディターを使用していない場合は、左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. モジュールを挿入するモジュール間の点線パスをクリックします。
1. 表示されるメニューで、**モジュールを追加**&#x200B;を選択します。

コネクタのリストが開き、シナリオで既に使用されているコネクタが表示されます。

1. （オプション）別のコネクタを選択するには、リストで「**別のモジュールを追加**」をクリックし、コネクタを選択します。 リストの検索バーにコネクタの名前を入力して、リストをフィルタリングできます。
1. モジュールを設定します。

   特定のモジュールの設定の手順については、[Fusion アプリケーションとそのモジュールのリファレンスに記載されている、選択したアプリケーションの記事を参照してください。記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

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
