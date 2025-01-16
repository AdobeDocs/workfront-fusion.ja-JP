---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 基本的なシナリオの作成
description: Adobe Workfront Fusion を使用してシンプルな自動処理シナリオを作成する方法について説明します。 自動処理シナリオは、データの操作や変換を含む Workfront プロセスを自動化します。この例では、Workfront内のタスクを検索し、 [!DNL Workfront]  れをプロジェクトに変換するシナリオの作成手順を説明します。
author: Becky
feature: Workfront Fusion
exl-id: 5284dee1-e890-4357-a28d-29e09ac02822
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 25%

---

# 基本的なシナリオの作成

[!DNL Adobe Workfront Fusion] の役割は、同じタスクを何度も繰り返すのではなく、新しいタスクに集中できるようにプロセスを自動化することです。これは、アプリ内やサービス内、およびそれらの間でアクションをリンクし、データを自動的に転送および変換するシナリオを作成することで機能します。作成するシナリオは、アプリまたはサービス内のデータを監視し、そのデータを処理して必要な結果を提供します。

この例では、Workfrontでリクエストを検索し、によってリクエストがプロジェクトに変換されるシナリオの作成プロセスを説明します。

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
   <td> <p>新規： [!UICONTROL Standard]</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
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
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Workfront] プラン：組織は [!DNL Adobe Workfront Fusion] を購入する必要があります。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] プラン：[!DNL Workfront Fusion] が含まれています。</li></ul>
   <p>または</p>
   <p>現在：[!DNL Adobe Workfront Fusion] を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについては、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++



## 練習シナリオを作成

### シナリオの作成を開始

1. **シナリオ** エリアで、「**新しいシナリオを作成**」をクリックします。

   「シナリオ」領域を見つけるには、[Workfront Fusion に移動 ](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/navigate-workfront-fusion.md) を参照してください。

   シナリオエディターが表示され、中央に空のモジュールが含まれます。

1. 左上隅の **[!UICONTROL New scenario]** プレースホルダー名を選択し、名前を入力します。
1. [ 最初のモジュールを追加して設定 ](#add-and-configure-the-first-module) を続行します。

### 最初のモジュールを追加して設定

1. 空のモジュールをクリックして、モジュールを選択するアプリを選択します。

   アプリのリストがモジュールの右側に表示されます。

1. 「**[!DNL Adobe Workfront]**」を選択します。 表示されない場合は、リストの下部にある検索バーをクリックして「Workfront」と入力し、リストに表示されたら選択します。

   リストが変わり、使用可能なすべて [!DNL Workfront] モジュールが表示されます。

1. **[!UICONTROL Search]** モジュールをクリックします。

   モジュール設定ウィンドウが開きます。

1. [!UICONTROL Connection] ボックスで、Workfront接続を選択します。

   Workfrontに接続されていない場合は、[ 接続の作成 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) を参照してください
1. 「[!UICONTROL Record Type]」ボックスで「**[!UICONTROL Issue]**」を選択します。 これにより、モジュールはリクエストを含む問題のみを検索するように設定されます。

   「**[!UICONTROL Issue]**」という単語を入力し始めると、リストに [!UICONTROL Issue] が表示されます。

1. 「**[!UICONTROL Result Set]**」ボックスで「**[!UICONTROL First Matching Record]**」を選択します。

   これにより、条件を満たす最初のレコードのみを返すようにモジュールが設定されます。
1. **[!UICONTROL Search criteria]** 領域で、特定のタスクを返す条件を設定します。

   1. [!UICONTROL Search Criteria] の下にある最初のボックスで、検索に含めるフィールドを選択します。 この例では、「**[!UICONTROL Name]**」を選択します。

      「**[!UICONTROL Name]**」という単語を入力し始めると、リストに [!UICONTROL name] が表示されます。
   1. オペレーターの場合は、「存在する **の横にあるドロップダウン矢印をクリックし** 「含む [!UICONTROL **大文字と小文字を区別しない）**] に変更します。

      これにより、名前全体を入力しない場合または名前に大文字と小文字を区別せずに入力した場合でも、モジュールは名前に選択した単語を含むプロジェクトを検索できます（すべて大文字など）。
   1. [!UICONTROL Search Criteria] の下の最後のフィールドに、検索するタスクの名前に含まれていることがわかっている単語または語句を入力します。

1. **[!UICONTROL Outputs]** リストで、モジュールの出力に使用するフィールドを選択します。 この例では、「**[!UICONTROL ID]**」フィールドと「**[!UICONTROL Name]**」フィールドを選択します。

   >[!TIP]
   >
   >**Cmd+F**（[!DNL Mac] OS）または **Ctrl+F**（[!DNL Windows] OS）を使用して、すばやくフィールドを検索できます。

1. 「**[!UICONTROL OK]**」をクリックして、モジュール設定を保存します。

1. モジュールを右クリックして [**[!UICONTROL Rename]**] をクリックし、モジュールで実行する内容を説明する名前（「要求の検索」など）を入力して [**[!UICONTROL OK]**] をクリックします。

   名前はモジュールのすぐ下に表示されます。その下に [!DNL Workfront Fusion] には、モジュールで実行されるアクションのタイプに関する簡単な説明が含まれます。

   ![](assets/module-renamed-wf.png)

1. [2 つ目のモジュールを追加して設定](#add-and-configure-the-second-module)に進みます。

## 2 つ目のモジュールを追加して設定

1. モジュールの右側にある円の上にマウスポインターを置き、「**[!UICONTROL Add another module]**」をクリックします。
1. アプリケーションのリストから「[!DNL Adobe Workfront]」を選択し、モジュール **[!UICONTROL Convert object]** を選択します。
1. [!UICONTROL Connection] フィールドで、前のモジュールで使用したのと同じWorkfront接続を選択します。
1. モジュールはイシューを変換するので、「**[!UICONTROL Record type]**」フィールドで「**[!UICONTROL issue]**」を選択します。
1. 「**[!UICONTROL Convert to]**」フィールドで「**プロジェクト**」を選択します。
1. 「タスク ID」フィールドの横にある「マップ」切替スイッチをクリックして有効にします。

   切替スイッチが有効になると青に変わります。 これにより、前のモジュールからタスク ID をマッピングできます。

   ![ マップ切り替え ](assets/map-toggle.png)
1. **[!UICONTROL Task ID]** フィールドをクリックします。

   パネルが開き、プロジェクトに変換するタスクの ID として使用するものを選択できます。 マッピングを有効にしたため、パネルには以前のモジュールからの出力が含まれます。 以前のモジュールの出力として ID を選択したので、パネルで使用できるようになりました。

   このパネルは、マッピングパネルと呼ばれます。 マッピングパネルについて詳しくは、[ マッピングの概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md) を参照してください。
1. マッピングパネルで **ID** を選択します。

   「ID」フィールドに ID ブロックが表示されます。 マッピング元のモジュールの数と、マッピングされたフィールドが表示されます。

   ![ マップ ID](assets/map-id.png)

1. 「**テンプレート ID**」フィールドをクリックし、このプロジェクトに使用するWorkfront テンプレートの名前の入力を開始し、リストに表示されたら選択します。
1. 「**[!UICONTROL OK]**」をクリックして、モジュール設定を保存します。

1. モジュールを右クリックして [**[!UICONTROL Rename]**] をクリックし、モジュールで実行する内容を説明する名前（[ プロジェクトに変換 ] など）を入力して、[**[!UICONTROL OK]**] をクリックします。

1. [ シナリオのテスト ](#test-the-scenario) に進みます。

## シナリオのテスト

シナリオをアクティベートする前にテストすることが重要です。少なくとも 1 回実行して結果を確認します。これは、シナリオにおけるデータの流れを理解し、エラーを見つけるのに役立ちます。

このシナリオでは、テストが成功すると、リクエストが見つかり、プロジェクトに変換されます。

1. シナリオエディターの左下にある「**[!UICONTROL Run once]**」をクリックします。
1. シナリオの実行が完了したら、最初のモジュールの上にあるバブルをクリックして、モジュールが処理したデータのバンドルに関する情報（モジュールが返した要求から取り込まれたデータを含む）を表示できます。

1. 2 番目のモジュールの上にある実行インスペクターのバブルをクリックして、入力（要求）と出力（変換されたプロジェクト）を確認します。

   検査バブル内のデータの詳細については、以下を参照してください。

   * 一般情報については、[ シナリオ実行フロー ](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md) を参照してください。
   * 処理されたバンドルについて詳しくは、[ シナリオ実行、サイクル、フェーズ ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md) を参照してください。

1. [!DNL Workfront Fusion] では、左下隅付近の **[!UICONTROL Save]** をクリックして、シナリオの進捗を保存します。

   >[!IMPORTANT]
   >
   >シナリオを改良、テストするたびに保存するようにしてください。

>[!TIP]
>
>各モジュールに関するメモを追加する方法として、任意ではあるものの便利な方法をお勧めします。
>
>1. モジュールを右クリックし、「**[!UICONTROL Add a note]**」を選択します。
>1. 表示されるメモに、モジュールの概要を入力します。
>
>    1 つのモジュールに複数のノートを追加できます。
>
>1. **[!UICONTROL Notes]** 領域を閉じます。
>
>     シナリオにメモを追加すると、シナリオエディターの下部にある **[!UICONTROL Notes]** アイコンにオレンジ色の点が表示され ![](assets/notes-icon-w-dot.png) す。
>
>1. **[!UICONTROL Notes]** アイコン ![](assets/notes-icon-w-dot.png) をクリックして、メモを表示します。
>

## シナリオをアクティベート

シナリオを作成するための最後の手順は、シナリオをアクティブ化することです。

このシナリオでは特定の問題を検索するので、アクティブ化する必要はありません。 シナリオをアクティブ化すると、スケジュールに従って、またはアプリケーションで特定のアクションが発生したときにシナリオが実行されます。 シナリオをアクティベートすると、デフォルトでは 15 分ごとに実行されます。これは、実行するタイミングと頻度を定義することで変更できます。

シナリオのアクティブ化の詳細については、[ シナリオのアクティブ化または非アクティブ化 ](/help/workfront-fusion/manage-scenarios/activate-deactivate-scenarios.md) を参照してください。

スケジュールについては、[ シナリオのスケジュール ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。

## 次のステップ

* [トリガーモジュールを追加 ](/help/workfront-fusion/build-practice-scenarios/add-a-webhook-to-basic-scenario.md) して、シナリオが定期的に新しいリクエストを検索し、プロジェクトに変換できるようにします。
* [Webhook を追加 ](/help/workfront-fusion/build-practice-scenarios/add-a-webhook-to-basic-scenario.md) して、リクエストが入力されるたびにシナリオを実行できるようにします。
* [ フィルターを追加 ](/help/workfront-fusion/build-practice-scenarios/add-filter-basic-scenario.md) して、特定のリクエストのみがプロジェクトに変換されるようにします。
* 新しいプロジェクトの名前をカスタマイズする [ 関数を追加 ](/help/workfront-fusion/build-practice-scenarios/use-function-to-build-practice-scenario.md) します。
