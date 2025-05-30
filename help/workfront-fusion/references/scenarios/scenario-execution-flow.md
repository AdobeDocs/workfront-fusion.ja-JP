---
content-type: overview
title: シナリオ実行フロー
description: この記事では、シナリオの実行方法とシナリオ内のデータのフローを説明します。また、処理されたデータとその読み取り方法に関する情報の所在についても説明します。
author: Becky
feature: Workfront Fusion
exl-id: bd4f05e2-df3c-4848-9a70-3df18ca4461b
source-git-commit: 0ef6dde9566ca3b97c1c52d6055f0ce44f575cee
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# シナリオ実行フロー

この記事では、シナリオの実行方法、シナリオ内でのデータのフロー、各モジュールで処理されるデータの表示方法について説明します。

アクティブなシナリオでのデータのフローを表示するには、[ 実行中のシナリオでのデータフローの表示 ](/help/workfront-fusion/manage-scenarios/view-scenario-data-flow.md) を参照してください。

## シナリオ実行フロー

シナリオは、正しく設定されてアクティブ化されると、定義されたスケジュールに従って実行されます。

シナリオが開始すると、最初のモジュールが、監視対象として設定されたイベントに応答します。データを返す際、そのデータはバンドルにパッケージ化されます。 このシナリオでは、各イベントに対して 1 つのバンドルが返されます。 例えば、問題を監視するようにモジュールが設定されている場合、検出された各問題に関するデータのバンドルが返されます。

トリガーモジュールがデータのバンドルを返した場合、それらのバンドルは次のモジュールに渡され、シナリオは続行されて、後続の各モジュールで 1 つずつバンドルが渡されます。

バンドルがすべてのモジュールを通じて正しく処理した場合、シナリオの詳細ページでシナリオは成功とマークされます。

### 例：[!UICONTROL [!DNL Workfront Fusion] for Work Automation]

>[!BEGINSHADEBOX]

**例：** このシナリオでは、[!DNL Workfront] で受信リクエストを監視し、それらを [!DNL Workfront] プロジェクトに変換すると、データは次のように流れます。

最初のモジュールで実行される、シナリオの最初のステップは、リクエストを監視することです。見つかった各リクエストは 1 つのバンドルと見なされます。 モジュールが実行されてもバンドルが見つからない場合、シナリオは最初のモジュールの後で終了します。

最初のモジュールがバンドルを返した場合、そのバンドルは残りのシナリオに渡されていきます。この例では、バンドルは 2 番目のモジュールに移動し、リクエストをプロジェクトに変換します。

![Workfront シナリオの実行フロー ](assets/example-execution-flow-wf-only.png)

>[!ENDSHADEBOX]

### 例：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration]

>[!BEGINSHADEBOX]

**例：**&#x200B;[!DNL Adobe Workfront] からドキュメントをダウンロードして [!DNL Dropbox] のフォルダーに送信するシナリオでは、データは次のように流れます。

シナリオの最初の手順は、最初のモジュールが実行し、Workfrontでドキュメントを監視することです。 見つかった各ドキュメントは 1 つのバンドルと見なされます。 モジュールが実行されてもバンドルが見つからない場合、シナリオは最初のモジュールの後で終了します。

バンドルが返されると、そのバンドルは残りのシナリオに渡されていきます。この例では、残りのシナリオは、[!DNL Dropbox] フォルダーにバンドルをアップロードする secondmodule で構成されています。

![ 統合シナリオの実行フロー ](assets/example-execution-flow-wf-dropbox.png)

最初のモジュールが複数のバンドルを返した場合、最初のバンドルが [!DNL Dropbox] にアップロードされてから、2 番目のバンドルがアップロードされます。次に、2 番目のバンドルがアップロードされたあと、3 番目のバンドルがアップロードされ、以下同様の処理が繰り返されます。

>[!ENDSHADEBOX]

## 処理されたバンドルに関する情報

各モジュールについて、バンドルは次のモジュールに進む前または最終的な宛先に達する前に、4 つの手順のプロセスを経ます。

* 初期化
* 操作
* コミット/ロールバック
* 最終化

>[!NOTE]
>
>より大きなシナリオでも、このプロセスを実行します。 シナリオレベルでのこのプロセスについて詳しくは、[ シナリオの実行、サイクル、フェーズ ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md) を参照してください。

シナリオの実行が完了すると、各モジュールに、実行された操作の数を示すアイコンが表示されます。 このアイコンをクリックすると、プロセス内の各ステップの処理済みバンドルに関する詳細情報が表示されます。 使用されたモジュール設定と、各モジュールによって返されたバンドルを確認できます。

![ 処理済みのバンドル ](assets/Info-processed-bundles.png)

この例では、モジュールは次のような入力情報を受け取りました。

* 検出された問題の ID
* イシューの変換先のオブジェクト （Project）
* プロジェクトの作成に使用されるテンプレートの ID
* 検出されたオブジェクトのレコードタイプ（OPTASK、問題）

処理の後、モジュールは次の出力情報を返しました。

* 新しく作成されたプロジェクトの ID。

モジュールで複数の問題が見つかった場合、情報は各バンドルに対して個別にキャプチャされます。 2 番目のバンドルを記述する入力セクションと出力セクションを含む操作 2 領域があります。以下に例を示します。

## シナリオ実行中のエラー

シナリオの実行中にエラーが発生する場合があります。例えば、モジュールが新しいプロジェクトの作成に使用するテンプレートを削除した場合、シナリオはエラーメッセージで終了します。 エラーの処理方法について詳しくは、[ エラータイプ ](/help/workfront-fusion/references/errors/error-processing.md) を参照してください。

## リソース

* シナリオの設定について詳しくは、[ シナリオエディター ](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md) を参照してください。
* シナリオの詳細ページについて詳しくは、[ シナリオの詳細 ](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-details.md) を参照してください。
* シナリオのアクティブ化について詳しくは、[ シナリオのアクティブ化または非アクティブ化 ](/help/workfront-fusion/manage-scenarios/activate-deactivate-scenarios.md) を参照してください。
* シナリオのスケジュール設定の詳細については、[ シナリオのスケジュール設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。
* モジュールについて詳しくは、「[ モジュールの概要 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md)」を参照してください。
