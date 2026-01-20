---
title: キー
description: Adobe Workfront Fusion のキーチェーンは、公開鍵と秘密鍵の管理に役立ちます。 キーは例えば、PGP メッセージの暗号化または復号化のために、Encryptor アプリによって使用されます。
author: Becky
feature: Workfront Fusion
exl-id: b92e54ed-fa03-4af7-be7b-436907b2bff9
source-git-commit: 3ae274720ea2d7e4ee823a8467b750ad6f4d0c52
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 53%

---

# キー

公開鍵と秘密鍵は、データの暗号化と復号化に使用されます。公開鍵は配布でき、公開鍵を持つすべてのユーザーがデータを暗号化できますが、復号化できるのは秘密鍵のみです。同様に、同様に、秘密鍵を持つユーザーは、公開鍵を持つ誰もが復号化できるデータを暗号化できます。キー領域では、チームが所有するキーを表示および管理できます。

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

## キーの作成

接続と同様に、キーは個々のモジュールに追加され、他のモジュールで使用できます。

1. キーを必要とするモジュールの場合、「キー」フィールドで、ドロップダウンメニューから既存のキーを選択します。

   または

   キーフィールドの横にある「**追加**」をクリックし、キーの名前とキー自体を入力して、「**キーを作成**」をクリックします。

既存のキーを表示するには、左側のナビゲーションの **キー** 領域をクリックします。

## キーを更新

既存のキーを更新できます。 キーが更新されると、キーを使用するすべてのシナリオで、更新されたキーが使用されます。

1. Fusion で、左側のナビゲーションのキー ![&#x200B; キーアイコン &#x200B;](assets/keys-icon.png) をクリックします。
1. 編集するキーを選択し、画面の下部にあるバーの「編集」をクリックします。
1. 必要に応じてキーを編集します。
