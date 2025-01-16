---
title: モジュールの概要
description: Adobe Workfront Fusion は、アクションモジュール、検索モジュール、トリガーモジュール、アグリゲータ、イテレータの 5 種類のモジュールを区別します。 アグリゲーターとイテレーターは、詳細なシナリオ用です。
author: Becky
feature: Workfront Fusion
exl-id: 4c8fe028-8425-426d-a006-f0c66871b3cd
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 22%

---

# モジュールの概要

Adobe Workfront Fusion は、次の 5 種類のモジュールを区別します。

* アクションモジュール
* モジュールの検索
* トリガーモジュール
* アグリゲーター
* イテレータ

アグリゲーターとイテレーターは、詳細なシナリオ用です。

## アクションモジュール

アクションモジュールは、最も一般的なタイプのモジュールです。一般的なアクションモジュールは、アクションを実行して 1 つのバンドルを返し、バンドルは処理のために次のモジュールに渡されます。

トリガー モジュールとは異なり、アクション モジュールはシナリオの最初、中間、または最後に配置できます。

シナリオに含まれるアクションモジュールの数は無制限ですが、多数のモジュール（150 以上）がパフォーマンスに影響を与える可能性があります。

>[!BEGINSHADEBOX]

**例：**

* **[!DNL Workfront]>[!UICONTROL Upload a file]** はファイルを [!DNL Workfront] に送信し、その識別子を返します。
* **[!UICONTROL Image]>[!UICONTROL Resize]** は画像を受け取り、指定された寸法にサイズ変更し、サイズ変更された画像を次のアクションに渡します。

>[!ENDSHADEBOX]

アクションタイプには、次の 4 つのサブタイプがあります。

* 作成
* Read
* アップデート
* 削除

「更新」サブタイプには、次の 3 つの操作が含まれます。

* **フィールドの内容を消去する**。この操作は、フィールドの内容が（`empty` と混同しないように） `erase` キーワードに評価されたときに発生します。

  ![Erase キーワード ](assets/erase-content-of-field.png)

* **フィールドの内容を変更しない**。この操作は、フィールドが空白のままになっているか、フィールドの内容が空白と評価される（JSON の null で表される）場合に実行されます。

  ![ 空のバンドル ](assets/leave-content-field-unchanged.png)

* **フィールドの内容を置き換える**。この操作は、上記の 2 つ以外のすべての場合に実行されます。

>[!NOTE]
>
>* `erase` キーワードがマッピングパネルに表示されない場合、モジュールが更新モジュールでないか、アプリの最新の仕様に更新されていません。
>* `Empty` はフィールドの内容を変更しません。 フィールドを消去する必要がある場合は、次の数式を使用できます。
>
>   ![ 空の場合 ](assets/formula-ifempty-name-erase.png)
>
>* コンテンツが空と評価された場合にフィールドを変更しないままにしておくことは、現在サポートされていません。

## モジュールの検索

検索モジュールは、0 個、1 個または複数のバンドルを返し、これらは処理のために次のモジュールに渡されます。

検索モジュールは、シナリオの先頭、中間、末尾に配置できます。

シナリオに含まれる検索モジュールの数は無制限ですが、モジュールの数が多い（150 以上）とパフォーマンスに影響が出る場合があります。

>[!BEGINSHADEBOX]

**例：**

**[!DNL Workfront]>[!UICONTROL Read Related Records]** は、特定の親オブジェクト内で、指定した検索クエリに一致するレコードを読み取ります。

>[!ENDSHADEBOX]

## トリガーモジュール

トリガーは、特定のサービスに変更があった場合（レコードの作成や更新など）にバンドルを生成します。

トリガーは、0 個、1 個または複数のバンドルを返し、それらを次のモジュールに渡して処理します。

トリガーはシナリオの実行を開始させる原因となるので、シナリオの先頭にのみ配置できます。

各シナリオにはトリガーを 1 つだけ含めることができます。

[!DNL Workfront Fusion] では、ポーリングトリガーとインスタントトリガーの 2 種類のトリガーを使用します。

### ポーリングトリガー

ポーリングトリガーは、前のシナリオの実行以降に変更がない場合でも、指定されたサービスを定期的にポーリングします。 ポーリングトリガーを含むシナリオを、一定の間隔で実行するようにスケジュールすることをお勧めします。トリガーの設定に一致する変更がある場合、トリガーは変更に関する情報を含むバンドルを返します。 設定に一致する変更がない場合、トリガーはバンドルを出力しません。

シナリオのスケジュールを設定する手順については、[ シナリオのスケジュール設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。

ポーリングトリガーを使用すると、トリガーを保存した後やトリガーを変更した後に自動的に表示されるパネルを介して出力される最初のバンドルを選択できます。 この選択は、モジュールの最初の実行にのみ影響します。 モジュールが 1 回実行された後の後続の実行では、最後の実行後に行われた変更のみが監視されます。

詳しくは、[トリガーモジュールの開始位置の選択 ](/help/workfront-fusion/create-scenarios/add-modules/choose-where-trigger-module-starts.md) を参照してください。

>[!BEGINSHADEBOX]

**例：**

* **[!DNL Workfront]>[!UICONTROL Watch records]** は、シナリオが前回実行された後に新しく追加されたレコードを返します。

* **[!DNL Google Sheets]>[!UICONTROL Watch Rows]** は、シナリオが前回実行された後に追加された新しい行を返します。

>[!ENDSHADEBOX]

### インスタントトリガー

インスタントトリガーを使用すると、サービスは変更が発生した直後に [!DNL Workfront Fusion] ーザーに通知を送信できます。 インスタントトリガーを含むシナリオをすぐに実行するようにスケジュールすることをお勧めします。

手順については、[ シナリオのスケジュール設定 ](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md) を参照してください。

受信データがインスタントトリガーでどのように処理されるかについて詳しくは、[ インスタントトリガー（Webhook） ](/help/workfront-fusion/references/modules/webhooks-reference.md) を参照してください。

>[!BEGINSHADEBOX]

**例：**

* **[!DNL Workfront]>[!UICONTROL Watch Events]** は、Workfrontで特定のタイプのイベント（タスクの作成など）が発生した場合に情報を返します。
* **[!DNL Google Sheets]>[!UICONTROL Watch Changes]** は、セルが更新されるたびに情報を返します。

>[!ENDSHADEBOX]

## アグリゲーター

集約モジュールは、複数のバンドルを 1 つのバンドルに蓄積する。

アグリゲータは 1 つのバンドルのみを返し、その後、さらに処理するために次のモジュールに渡されます。

アグリゲーターは、シナリオの途中にのみ配置できます。

シナリオに含まれるアグリゲータの数は無制限ですが、多数のモジュール（150 以上）がパフォーマンスに影響を与える可能性があります。

>[!BEGINSHADEBOX]

**例：**

* **[!UICONTROL Archive]>[!UICONTROL Create an archive]** は、複数のファイルを zip アーカイブに圧縮します。
* **[!UICONTROL CSV]>[!UICONTROL Aggregate to CSV]** は、CSV ファイルの複数の文字列を 1 行に結合します。
* **[!UICONTROL Tools]>[!UICONTROL Text aggregator]** は、複数の文字列を 1 つの文字列に結合します。

>[!ENDSHADEBOX]

詳しくは、[ アグリゲータモジュール ](/help/workfront-fusion/references/modules/aggregator-module.md) を参照してください。

## イテレータ

イテレータは、配列を個別のバンドルに分割するモジュールの一種です。

イテレータは 1 つ以上のバンドルを返し、それらを次のモジュールに渡して処理します。

イテレーターは、シナリオの途中にのみ配置できます。

シナリオには無制限の数のイテレータを含めることができますが、多数のモジュール（150 以上）がパフォーマンスに影響を与える可能性があります。

>[!BEGINSHADEBOX]

**例：**

**[!UICONTROL Email]>[!UICONTROL Retrieve attachments]** は、添付ファイルの配列を個別のバンドルに分割します。

>[!ENDSHADEBOX]

詳しくは、[Iterator モジュール ](/help/workfront-fusion/references/modules/iterator-module.md) および [ 配列のマッピング ](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md) を参照してください。
