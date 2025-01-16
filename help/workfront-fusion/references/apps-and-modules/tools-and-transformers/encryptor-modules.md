---
title: 暗号化
description: Adobe Workfront Fusion 暗号化モジュールを使用すると、任意のテキストデータを暗号化できます。現在、AES256 と PGP（OpenPGP）を介したメッセージの暗号化をサポートしています。
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 73%

---

# 暗号化

[!DNL Adobe Workfront Fusion] [!UICONTROL Encryptor] モジュールを使用すると、任意のテキストデータを暗号化できます。 現在は、AES256 および PGP を使用したメッセージ暗号化をサポートしています（[!UICONTROL OpenPGP]）。

## アクセス要件

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] プラン*</td>
  <td> <p>[!UICONTROL Pro] またはそれ以降</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] ライセンス*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] ライセンス**</td> 
   <td>
   <p>現在のライセンス要件：[!DNL Workfront Fusion] ライセンス要件なし。</p>
   <p>または</p>
   <p>レガシーライセンス要件：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration], [!UICONTROL [!DNL Workfront Fusion] for Work Automation]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>現在の製品要件：[!UICONTROL Select] または [!UICONTROL Prime] [!DNL Adobe Workfront] プランがある場合、組織は [!DNL Adobe Workfront Fusion] を購入するだけでなく、この記事で説明されている機能を使用する [!DNL Adobe Workfront] 要があります。 [!DNL Workfront Fusion] は [!UICONTROL Ultimate] [!DNL Workfront] プランに含まれています。</p>
   <p>または</p>
   <p>従来の製品要件：この記事で説明している機能を使用するには、[!DNL Adobe Workfront Fusion] と [!DNL Adobe Workfront]を組織で購入する必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

ご利用のプラン、ライセンスタイプまたはアクセス権を確認するには、[!DNL Workfront] 管理者にお問い合わせください。

[!DNL Adobe Workfront Fusion] ライセンスについては、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## PGP を使用したメッセージの暗号化と復号

PGP で暗号化および復号する場合、キーチェーンを使用し、秘密鍵または公開鍵（またはその両方）を作成する必要があります。

公開鍵と秘密鍵について詳しくは、[Adobe Workfront Fusion 用語集 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md) を参照してください。<!--For more information on keychains, see [Keys in [!DNL Adobe Workfront Fusion]]().-->

## [!UICONTROL Encryptor] モジュールとそのフィールド

[!UICONTROL Encryptor] モジュールを設定すると、次のフィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

### PGP メッセージを暗号化

このモジュールで、公開鍵と秘密鍵を使用してメッセージを暗号化できます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>送信者の秘密鍵を入力します。これにより、送信者の ID を認証できます。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>受信者の公開鍵を入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>暗号化するメッセージを入力します。</td>
    </tr>

### PGP メッセージを復号化

このモジュールでは、公開鍵と秘密鍵を使用してメッセージを復号できます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>受信者の秘密鍵を入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>受信者の公開鍵を入力します。これにより、送信者の ID を認証できます。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>復号するメッセージをマッピングします。</td>
    </tr>
</table>
