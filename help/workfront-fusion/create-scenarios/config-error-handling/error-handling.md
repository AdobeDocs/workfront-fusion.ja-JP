---
title: エラー処理の追加
description: シナリオの実行中にエラーが発生する場合、通常、その原因は、サービスが障害により利用できないか、サービスが予期しないデータで応答するか、入力データの検証が失敗するすることなどです。
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
TQID: https://experienceleague.adobe.com/3Ro1DMD2tIXSZuXo77JEw2EtlVpoS-D6CNGyR9QcFXg
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1156
ht-degree: 22%

---

# エラー処理の追加

シナリオの実行中にエラーが発生する可能性があります。

例えば、次の理由でエラーが発生する可能性があります。

* エラーが発生したため、サービスを利用できません
* サービスが予期しないデータで応答する
* 入力データの検証が失敗する
* その他の理由

シナリオの実行中にモジュールでエラーが発生し、モジュールまたはそのルートにエラー処理ルートが添付されていない場合、デフォルトのエラー処理ロジックが実行されます。

エラーハンドラーをモジュールまたはルートに追加することで、デフォルトのエラー処理ロジックを独自のロジックに置き換えることができます。 Adobe Workfront Fusionには、エラーハンドラールートの最後に挿入できる5つの異なるディレクティブが用意されています。

デフォルトのエラー処理について詳しくは、[&#x200B; エラータイプ &#x200B;](/help/workfront-fusion/references/errors/error-processing.md)を参照してください。

エラー処理ディレクティブについて詳しくは、[&#x200B; エラー処理のディレクティブ &#x200B;](/help/workfront-fusion/references/errors/directives-for-error-handling.md)を参照してください。

>[!NOTE]
>
>Workfront Fusionは、ルートレベルのエラー処理をサポートしており、個々のモジュールにエラーハンドラーを添付するのではなく、ルートごとに1回エラー処理ロジックを定義できます。
>ルートレベルのエラー処理は、特に高度なマルチブランチ自動処理では、よりスケーラブルで一貫性のある、アーキテクチャ的にクリーンな方法でエラーを管理できるので、ルートレベルのエラー処理をベストプラクティスとして使用することをお勧めします。

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

## エラーハンドラーの場所と階層

個々のモジュールまたはルーターにエラーハンドラーを追加できます。

モジュールに添付されたエラーハンドラーは、そのモジュールの処理中に発生したエラーに対してのみトリガーします。

ルータのルート上の任意のモジュールで発生したエラーに対して、ルータのトリガーに接続されたエラーハンドラ。 これには、自分のルータにエラーハンドラを持たない子ルートで発生したエラーが含まれます。

エラーは、次の階層で処理されます。

1. モジュール
2. ルーター
3. 親ルータ
4. デフォルトのエラー処理

>[!BEGINSHADEBOX]

### 例

次のシナリオ例を考えてみましょう。

![&#x200B; ルートとエラーハンドラーを示すシナリオの例](assets/error-handling-route-example-with-numbers.png)

1. このモジュールにはエラーハンドラーがあります。 このモジュールのエラーは、Commit ディレクティブによって処理されます。
1. このモジュールにはエラーハンドラーがありません。 このモジュールでエラーが発生した場合、そのエラーはモジュールのルートを作成したルータ上のハンドラによって処理されます。 このモジュール上のエラーは、Rollback ディレクティブによって処理されます。
1. このモジュールにはエラーハンドラも、モジュールのルートを作成したルータもありませんが、次のルータにエラーハンドラがあります。 このモジュール上のエラーは、Break ディレクティブによって処理されます。

>[!NOTE]
>
>* モジュールにエラーハンドラー、そのルーター、または親ルーターがない場合、そのモジュールのエラーはデフォルトのエラー処理で処理されます。
>* グローバルエラーハンドラーを作成するには、シナリオの開始部付近にルーターを作成し、そのルーターにエラー処理を添付します。


>[!ENDSHADEBOX]

## エラーハンドラーの追加

エラーハンドラーは、モジュールまたはルーターに追加できます。

* [モジュールへのエラーハンドラーの追加](#add-an-error-handler-to-a-module)
* [ルーターへのエラーハンドラーの追加](#add-an-error-handler-to-a-router)

### モジュールへのエラーハンドラーの追加

モジュールにエラーハンドラーを追加するには：

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. エラー処理ルートを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. エラーハンドラーのルートを追加するモジュールを右クリックし、**[!UICONTROL エラーハンドラーを追加]**&#x200B;を選択します。

   ![&#x200B; エラーハンドラーのルート &#x200B;](assets/error-handler-route.png)

   エラーハンドラーのルートがモジュールに追加されます。 モジュールがルートの最後のモジュールである場合、エラーハンドラーはモジュールに直接従います。 モジュールの後にモジュールが多い場合は、別のエラーハンドラールートが追加されます。

   エラー処理モジュールには、ディレクティブのリストと、シナリオで使用されているアプリが表示されます。

   ![&#x200B; エラーのルート &#x200B;](assets/error-route.png)

1. いずれかのディレクティブを選択します。

   または

   1 つ以上のモジュールをエラーハンドラールートに追加します。

   ルートにさらにモジュールを追加する場合は、デフォルトでIgnore ディレクティブが適用されます。 エラーが発生した場合は、そのルートの後続のモジュールが処理されます。

   ディレクティブについて詳しくは、この記事の「[&#x200B; ディレクティブの処理エラー](#error-handling-directives)」を参照してください。

1. （オプション）エラー処理ルートにフィルターを追加します。 手順については、「[&#x200B; フィルターとネストをエラー処理ルートに追加](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)」を参照してください。

>[!NOTE]
>
>エラーハンドラルートは透明な円で示され、通常のルートは不透明の円で示されます。

### ルーターへのエラーハンドラーの追加

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. エラー処理ルートを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. エラーハンドラーのルートを追加するルーターを右クリックし、**[!UICONTROL エラーハンドラーを追加]**&#x200B;を選択します。

   ![&#x200B; エラーハンドラーのルート &#x200B;](assets/error-handler-on-router.png)

   エラーハンドラーのルートがルーターに追加されます。

   エラー処理モジュールには、ディレクティブのリストと、シナリオで使用されているアプリが表示されます。

   ![&#x200B; エラーのルート &#x200B;](assets/error-handler-route-from-router.png)

1. いずれかのディレクティブを選択します。

   または

   1 つ以上のモジュールをエラーハンドラールートに追加します。

   ルートにさらにモジュールを追加する場合は、デフォルトでIgnore ディレクティブが適用されます。 エラーが発生した場合は、そのルートの後続のモジュールが処理されます。

   ディレクティブについて詳しくは、この記事の「[&#x200B; ディレクティブの処理エラー](#error-handling-directives)」を参照してください。

1. （オプション）エラー処理ルートにフィルターを追加します。 手順については、「[&#x200B; フィルターとネストをエラー処理ルートに追加](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)」を参照してください。

## エラー処理ディレクティブ

ディレクティブについて、以下で簡単に説明します。 詳しくは、[&#x200B; エラー処理のディレクティブ &#x200B;](/help/workfront-fusion/references/errors/directives-for-error-handling.md)を参照してください。

5つのディレクティブがあり、エラー後にシナリオ実行が続行されるかどうかに基づいて、次のカテゴリに分類できます。

次のディレクティブを使用して、シナリオの実行が継続されるようにします。

* **[!UICONTROL 再開]**：エラーを含むモジュールの代替出力を指定できます。 シナリオの実行ステータスは成功とマークされます。
* **[!UICONTROL 無視]**：エラーを無視します。 シナリオの実行ステータスは成功とマークされます。
* **[!UICONTROL 一時停止]**：入力を不完全な実行のキューに保存します。 シナリオの実行ステータスは警告としてマークされます。

  詳細については、[不完全な実行を表示して解決する](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)を参照してください。

エラーが発生したときにシナリオの実行が停止する場合は、次のいずれかのディレクティブを使用します。

* **[!UICONTROL ロールバック]**: シナリオの実行を即座に停止し、そのステータスをエラーとしてマークします。
* **[!UICONTROL コミット]**: シナリオの実行を即座に停止し、そのステータスを成功としてマークします。

## リソース

エラー処理について詳しくは、以下を参照してください。

* [Adobe Workfront Fusion でのエラー処理のディレクティブ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [エラー処理ルートへのフィルタリングとネストの追加](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
