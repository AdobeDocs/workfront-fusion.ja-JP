---
content-type: reference
title: 組織とチームの設定と管理：記事索引
description: この節では、Adobe Workfront Fusion での組織とチームの設定および管理に関する記事を紹介します。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: aa570f28-7387-47c5-9968-e3554921b0f5
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 50%

---

# [!DNL Adobe Admin Console] を使用したユーザーの削除

ユーザーをAdobe Workfront Fusion からのみ削除して、その他の [!DNL Adobe] 製品プロファイルへのアクセス権を残すか、ユーザーを [!DNL Adobe Admin Console] から完全に削除できます。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ</td> 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：[!UICONTROL Work] 以上</p> </td> 
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
   <p>新規：</p> <ul><li>[!UICONTROL Select] または [!UICONTROL Prime] Workfront プラン：組織はAdobe Workfront Fusion を購入する必要があります。</li><li>[!UICONTROL Ultimate] Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">アクセスレベル設定*</td> 
   <td> 
     <p>組織の [!DNL Adobe Admin Console] 管理者である必要があります。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Adobe Workfront Fusion からのみユーザーを削除

他のAdobe製品の権限はそのままにして、Workfront Fusion からユーザーを削除できます。

手順については、「Admin Consoleでの製品の管理 [ の「製品からユーザーおよびユーザーグループを削除する」を参照してくだ ](https://helpx.adobe.com/jp/enterprise/using/manage-products.html) い。

## [!DNL Adobe Admin Console] ージ内のすべての製品のユーザーをディアクティベート

ユーザーを削除するには、[!DNL Adobe Admin Console] を通じてユーザーをディアクティベートする必要があります。

次のいずれかに該当する場合、ユーザーは [!DNL Adobe Admin Console] から非アクティブ化されます。

* ユーザーは製品または製品プロファイルから移動され、他の製品または製品プロファイルに割り当てられません。
* ユーザーは製品プロファイルにリンクされているグループから削除され、製品プロファイルにリンクされている他のグループには含まれません。
* ユーザーは製品プロファイルから削除され、別の製品プロファイルに割り当てられません。
* Workfront Fusion を含む組織でユーザーが削除または非アクティブ化されます。

  手順について詳しくは、[ユーザーの個別管理](https://helpx.adobe.com/jp/enterprise/using/manage-users-individually.html)の「ユーザーの削除」の節を参照してください。

Workfront Fusion では、アクティベートを解除すると、次のいずれかの影響が出ます。

* ユーザーが 1 つの組織にのみ存在する場合、そのユーザーは非アクティブ化されます。
* ユーザーが複数の組織に属している場合、[!DNL Adobe Admin Console] でユーザーが変更された組織から削除されます。
* ユーザーを削除する際は、次の点を考慮してください。

### Workfront Fusion でユーザーを削除する際の考慮事項

ユーザーを削除する際は、次の点を考慮してください。

* ユーザーを削除すると、そのユーザーの接続、キー、Webhook は削除されます。
* ユーザーに属するシナリオは、組織の所有者に転送されます。ユーザーに属する接続が有効ではなくなったので、これらのシナリオの接続を更新する必要があります。
* 削除されたユーザーがアプリケーションや公開テンプレートを所有している場合、そのアプリケーションまたは公開テンプレートは組織の所有者に転送されます。組織の所有者がいない場合、そのアプリケーションや公開テンプレートは別のユーザーに転送されます。
