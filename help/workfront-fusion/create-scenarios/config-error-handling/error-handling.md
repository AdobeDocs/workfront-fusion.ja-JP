---
title: エラー処理の追加
description: シナリオの実行中にエラーが発生する場合、通常、その原因は、サービスが障害により利用できないか、サービスが予期しないデータで応答するか、入力データの検証が失敗するすることなどです。
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: 0668441df8405610488e3e33658635e4cc7db270
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 25%

---

# エラー処理の追加

シナリオの実行中にエラーが発生する場合があります。

例えば、次の理由でエラーが発生する可能性があります。

* エラーのためサービスを利用できません
* サービスが予期しないデータで応答する
* 入力データの検証に失敗しました
* その他の理由

シナリオの実行中にモジュールがエラーに遭遇し、モジュールにエラー処理ルートが添付されていない場合、デフォルトのエラー処理ロジックが実行されます。

エラーハンドラールートをモジュールに追加することで、デフォルトのエラー処理ロジックを独自のエラー処理ロジックに置き換えることができます。Adobe Workfront Fusion には、エラーハンドラールートの末尾に挿入できる 5 つの異なるディレクティブが用意されています。

デフォルトのエラー処理について詳しくは、「[ エラータイプ ](/help/workfront-fusion/references/errors/error-processing.md)」を参照してください。

エラー処理ディレクティブについて詳しくは、「[ エラー処理用のディレクティブ ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)」を参照してください。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：ワーク以上</p> </td> 
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
   <p>新規：</p> <ul><li>Prime Workfront プランを選択する：組織がAdobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## エラーハンドラーの追加

モジュールにエラーハンドラーを追加するには：

1. 左側のパネルで「**[!UICONTROL Scenarios]**」タブをクリックします。
1. エラー処理ルートを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. エラーハンドラールートを追加するモジュールを右クリックし、**[!UICONTROL Add error handler]** のモジュールを選択します。

   ![](assets/error-handler-route.png)

   エラーハンドラールートがモジュールに追加されます。 モジュールがルート内の最後のモジュールの場合、エラーハンドラーディレクトリはモジュールに従います。 モジュールの後にさらにモジュールがある場合は、別のエラーハンドラールートが追加されます。

   エラー処理モジュールは、ディレクティブのリストと、シナリオで使用されているアプリを表示します。

   ![ エラールート ](assets/error-route.png)

1. いずれかのディレクティブを選択します。

   または

   1 つ以上のモジュールをエラーハンドラールートに追加します。

   ルートにさらにモジュールを追加する場合、デフォルトで無視ディレクティブが適用されます。 エラーが発生した場合、そのルート上の後続のモジュールが処理されます。

   ディレクティブについて詳しくは、この記事の [ エラー処理ディレクティブ ](#error-handling-directives) を参照してください。

1. （任意）エラー処理ルートにフィルターを追加します。 手順については、[ エラー処理ルートへのフィルタリングとネストの追加 ](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md) を参照してください。

>[!NOTE]
>
>エラーハンドラルートは透明な円で示され、通常のルートは不透明の円で示されます。

## エラー処理ディレクティブ

ディレクティブについて、以下で簡単に説明します。詳しくは、「エラー処理のディレクティブ [ を参照してください ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)。

5 つのディレクティブがあり、エラーの後にシナリオの実行が継続するかどうかに基づいて、次のカテゴリにグループ化できます。

次のディレクティブを使用して、シナリオの実行が継続されるようにします。

* **[!UICONTROL Resume]**: エラーが発生したモジュールの代替出力を指定できます。 シナリオの実行ステータスは成功とマークされます。
* **[!UICONTROL Ignore]**: エラーを無視します。 シナリオの実行ステータスは成功とマークされます。
* **[!UICONTROL Break]**：不完全な実行のキューへの入力を格納します。 シナリオの実行ステータスは、警告とマークされます。

  詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

エラーが発生したときにシナリオの実行が停止する場合は、次のいずれかのディレクティブを使用します。

* **[!UICONTROL Rollback]**: シナリオの実行を直ちに停止し、ステータスをエラーとしてマークします。
* **[!UICONTROL Commit]**: シナリオの実行を直ちに停止し、成功としてステータスをマークします。

## リソース

エラー処理について詳しくは、以下を参照してください。

* [Adobe Workfront Fusion でのエラー処理のディレクティブ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [エラー処理ルートへのフィルタリングとネストの追加](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
