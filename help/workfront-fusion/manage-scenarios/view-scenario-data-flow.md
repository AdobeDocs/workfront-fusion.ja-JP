---
title: シナリオでのデータフローの表示
description: 実行中のシナリオを見て、データがどのように流れるのかを確認できます。
author: Becky
feature: Workfront Fusion
exl-id: 24eeb1d3-b5a7-4486-8d0b-0a43eb154e8e
TQID: 'https://experienceleague.adobe.com/Ni0X8egfhVILudqNjtxx8iiMmlSrJa-0JPH-XGeqYeM'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 27%
---
# 実行中のシナリオでのデータフローの表示

実行中のシナリオを見て、データがどのように流れるのかを確認できます。

>[!NOTE]
>
>Workfront Fusionは、シナリオエディターを新しいエクスペリエンスに移行中です。 この移行中は、従来のエクスペリエンスと新しいエクスペリエンスの両方を利用でき、いつでも切り替えることができます。 新しいエクスペリエンスを使用することをお勧めします。 詳しくは、シナリオエディターの記事「[新しいエクスペリエンスと従来のエクスペリエンス &#x200B;](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)」を参照してください。

シナリオの実行中に、アクティブなモジュールは、新しいエクスペリエンスのモジュールのアイコンに回転するリング、またはクラシックエクスペリエンスのモジュールの周りに成長するリングでマークされます。 リングは、モジュールが実行中であることを示すだけで、進行状況は表示されません。 迅速に動作するモジュールは、リングの小さな部分しか表示されない場合があります。

新しいエクスペリエンス

![新しいエクスペリエンスのモジュールのアイコンにリングを回転](assets/new-spinning-icon.png)

従来のエクスペリエンス

![従来のエクスペリエンスでモジュールを呼び出す](assets/ring-around-module.png)

モジュールを実行すると、出力インジケーターが表示されます。

新しいエクスペリエンス

![新しいエクスペリエンスの出力インジケーター](assets/new-output-indicator.png)

従来のエクスペリエンス

![&#x200B; クラシックエクスペリエンスの出力インジケーター](assets/data-flow-output.png)

モジュールが複数のバンドルを処理する場合、処理された各バンドルにリングが表示され、出力インジケーターは出力する各バンドルに対してカウントされます。

シナリオデータフローについて詳しくは、[&#x200B; シナリオ実行フロー](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md)を参照してください。

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

## 実行中のシナリオでのデータフローの表示

1. 左側のパネルの「**[!UICONTROL シナリオ]**」タブをクリックします。
1. データフローを表示するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオエディターに入ります。
1. シナリオが実行されていない場合は、シナリオをアクティブにするか、**1回実行**&#x200B;をクリックしてシナリオの実行を開始します。
1. 実行履歴パネルの「現在実行中」セクションで、表示する実行を選択します。

![現在実行中](assets/currently-running.png)
