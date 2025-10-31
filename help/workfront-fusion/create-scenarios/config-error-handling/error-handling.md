---
title: エラー処理の追加
description: シナリオの実行中にエラーが発生する場合、通常、その原因は、サービスが障害により利用できないか、サービスが予期しないデータで応答するか、入力データの検証が失敗するすることなどです。
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 26%

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

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意のAdobe Workfront ワークフローパッケージと任意のAdobe Workfront Automation and Integration パッケージ</p><p>WorkfrontUltimate</p><p>Workfront Fusion を追加購入したWorkfront Primeおよび Select パッケージ。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront ライセンス</td> 
   <td> <p>標準</p><p>ワークまたはそれ以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>組織がWorkfront Automation and Integration を含まない Select またはPrime Workfront パッケージを持っている場合は、Adobe Workfront Fusion を購入する必要があります。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

+++

## エラーハンドラーの追加

モジュールにエラーハンドラーを追加するには：

1. 左側のパネルで「**[!UICONTROL シナリオ]**」タブをクリックします。
1. エラー処理ルートを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに移動します。
1. エラーハンドラールートを追加するモジュールを右クリックし、「**[!UICONTROL エラーハンドラーを追加]**」を選択します。

   ![ エラーハンドラールート ](assets/error-handler-route.png)

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

* **[!UICONTROL 再開]**：エラーを含むモジュールの代替出力を指定できます。シナリオの実行ステータスは成功とマークされます。
* **[!UICONTROL 無視]**：エラーを無視します。シナリオの実行ステータスは成功とマークされます。
* **[!UICONTROL 一時停止]**：入力を不完全な実行のキューに保存します。シナリオの実行ステータスは、警告とマークされます。

  詳しくは、[ 不完全な実行の表示と解決 ](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md) を参照してください。

エラーが発生したときにシナリオの実行が停止する場合は、次のいずれかのディレクティブを使用します。

* **[!UICONTROL ロールバック]**：シナリオの実行を直ちに停止し、ステータスをエラーとしてマークします。
* **[!UICONTROL コミット]**：シナリオの実行を直ちに停止し、ステータスを成功としてマークします。

## リソース

エラー処理について詳しくは、以下を参照してください。

* [Adobe Workfront Fusion でのエラー処理のディレクティブ](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [エラー処理ルートへのフィルタリングとネストの追加](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
