---
title: キー
description: Adobe Workfront Fusionのキーチェーンを使用すると、公開鍵と秘密鍵を管理できます。 キーは例えば、PGP メッセージの暗号化または復号化のために、Encryptor アプリによって使用されます。
author: Becky
feature: Workfront Fusion
exl-id: b92e54ed-fa03-4af7-be7b-436907b2bff9
TQID: https://experienceleague.adobe.com/EV5p7TwCCWVwujv8x2r5MxTc1sZMEhTJey8Xodp5HTA
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 53%

---

# キー

公開鍵と秘密鍵は、データの暗号化と復号化に使用されます。 公開鍵は配布でき、公開鍵を持つすべてのユーザーがデータを暗号化できますが、復号化できるのは秘密鍵のみです。 同様に、同様に、秘密鍵を持つユーザーは、公開鍵を持つ誰もが復号化できるデータを暗号化できます。 キー領域では、チームが所有するキーを表示および管理できます。

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

## キーを作成

接続と同様に、キーは個々のモジュールに追加され、他のモジュールで使用できるようになります。

1. キーが必要なモジュールでは、「キー」フィールドで、ドロップダウンメニューから既存のキーを選択します。

   または

   キーフィールドの横にある「**追加**」をクリックし、キーとキー自体の名前を入力してから、「**キーを作成**」をクリックします。

既存のキーを表示するには、左側のナビゲーションの&#x200B;**Keys**&#x200B;領域をクリックします。

## キーの更新

既存のキーを更新できます。 キーが更新されると、キーを使用するすべてのシナリオで、更新されたキーが使用されます。

1. Fusionで、左側のナビゲーションで「キー![ キー」アイコン ](assets/keys-icon.png)をクリックします。
1. 編集するキーを選択し、画面下部のバーにある「編集」をクリックします。
1. 必要に応じてキーを編集します。
