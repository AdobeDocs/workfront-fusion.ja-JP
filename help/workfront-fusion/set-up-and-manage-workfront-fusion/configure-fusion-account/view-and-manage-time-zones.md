---
title: タイムゾーンの表示と管理
description: Adobe Workfront Fusionでタイムゾーン設定を表示および管理する方法について説明します。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9910d9b4-5a7a-4f4a-9e66-8600d3b6c785
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 39c34b17e766678e187837e07c90b67f365a4f1d
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 17%
---
# タイムゾーンの表示と管理

Adobe Workfront Fusionには、組織およびユーザーレベルでのタイムゾーンの制御が含まれています。

* 組織タイムゾーン：シナリオでは、組織タイムゾーンを使用して、スケジュールされたイベントがいつ発生するかを判断します。

* ユーザータイムゾーン：ユーザータイムゾーンは、ユーザーに表示される時間を決定します。

>[!BEGINSHADEBOX]

例：

組織はニューヨーク市を拠点とし、組織時間はUTC-5 （アメリカ/ニューヨーク）に設定されます。 シナリオ Aは、この組織が所有しており、毎日午前9時に実行するようにスケジュールされています。 シナリオは、ニューヨークのタイムゾーンで午前9時に実行されます。

この組織のユーザーはロサンゼルス在住で、ユーザーのタイムゾーンがUTC-8 （アメリカ/ロサンゼルス）に設定されています。 このユーザーがシナリオ Aのシナリオ実行履歴を表示すると、シナリオが午前6時に実行されていることがわかります。 シナリオはニューヨークの時間に従って実行されましたが、ユーザーは時間を自分のタイムゾーンに変換しました。

>[!ENDSHADEBOX]



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
  <tr> 
   <td role="rowheader">アクセスレベル</td> 
   <td> 組織のタイムゾーンを編集するには、その組織の所有者または管理者である必要があります。 </td>
   </tr>
 </tbody> 
</table>

この表の情報について詳しくは、[ドキュメントのアクセス要件](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)を参照してください。

+++

## ユーザータイムゾーンの表示と管理

1. Fusionで、画面の右上にあるAdobe プロファイルアイコンをクリックします。
1. 開いたメニューで、**Fusion プロファイル**&#x200B;を選択します。
1. 「**タイムゾーンオプション**」タブを選択します。 タブはユーザー名の直下にあります。
タイムゾーンオプション リストが開きます。
1. タイムゾーンオプションリストの「Web」エリアで、自分の名前を見つけます。

   現在のユーザーのタイムゾーン設定は、名前の右側に表示されます。
1. タイムゾーンを編集するには、タイムゾーンの横にある「![&#x200B; タイムゾーンを編集](assets/edit-timezone-icon.png)」をクリックします。
1. 「詳細を変更」ウィンドウの「**タイムゾーン**」フィールドで、自分に設定するタイムゾーンを選択します。
1. 「**保存**」をクリックします。


## 組織のタイムゾーンの表示と管理

>[!NOTE]
>
>組織のタイムゾーンを編集するには、その組織の所有者または管理者である必要があります。

1. Fusionで、画面の右上にあるAdobe プロファイルアイコンをクリックします。
1. 開いたメニューで、**Fusion プロファイル**&#x200B;を選択します。
1. 「**タイムゾーンオプション**」タブを選択します。 タブはユーザー名の直下にあります。
タイムゾーンオプション リストが開きます。
1. タイムゾーンオプションリストの「シナリオ」エリアで、タイムゾーンを表示または管理する組織を見つけます。

   組織の現在のタイムゾーン設定は、組織名の右側に表示されます。
1. タイムゾーンを編集するには、タイムゾーンの横にある「![&#x200B; タイムゾーンを編集](assets/edit-timezone-icon.png)」をクリックします。
1. 「詳細を変更」ウィンドウの「**タイムゾーン**」フィールドで、組織に設定するタイムゾーンを選択します。
1. 「**保存**」をクリックします。


