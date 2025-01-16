---
title: SOAP モジュール
description: SOAP モジュールを使用して、Adobe Workfront Fusion で SOAP API に接続できます。
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: bf9af473f08463c00578a1a8b07c800239225f09
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 54%

---

# [!UICONTROL SOAP] モジュール

[!UICONTROL SOAP] モジュールを使用して、[!UICONTROL Adobe Workfront Fusion] の [!UICONTROL SOAP] API に接続できます。

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
   <p>レガシーライセンス要件：作業の自動化と統合の [!UICONTROL [!DNL Workfront Fusion]] </p>
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

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

## [!UICONTROL SOAP] モジュールの制限事項

>[!NOTE]
>
>WDSL 読み込み中は、リダイレクトは無効になります。 これはセキュリティ機能ですが、モジュールの実行時に未検証のリダイレクトがブロックされる可能性があります。

[!UICONTROL SOAP] モジュールは現在ベータ版で、次の機能をサポートしていません。

* 要素の再定義
* 小数部桁数の制限
* 合計桁数の制限
* 空白の制限
* マルチパートの入出力メッセージ。シングルパートメッセージのみがサポートされています。
* [[!UICONTROL SOAP] エンコーディング、スキーマおよび要素を使用して定義され ](https://schemas.xmlsoap.org) カスタム XML スキーマ要素。

>[!INFO]
>
>**例：**
>  
>次の項目は [!UICONTROL Workfront Fusion] で正しく認識されません：
>
>```
><complexType name="ArrayOfFloat">
>     <complexContent>
>           <restriction base="soapenc:Array">
>                 <attribute ref="soapenc:arrayType"
>                       wsdl:arrayType="xsd:integer[]"/>
>           </restriction>
>     </complexContent>
></complexType>
>```
>
>この例には、[!UICONTROL Workfront Fusion] でまだサポートされていない `soapenc:Array`、`soapenc:arrayType` および `wsdl:arrayType` 参照が含まれています。

## 回避策

[!UICONTROL SOAP] モジュールが WSDL ファイルの処理を拒否した場合や、モジュールの設定で様々なエラーがスローされた場合は、代わりに universal **[!UICONTROL HTTP]/[!UICONTROL Make a request]** モジュールを使用してみてください。

1. [!DNL Workfront Fusion] で新しいシナリオを作成します。
1. シナリオで **[!UICONTROL HTTP]/[!UICONTROL Make a request]** モジュールを挿入します。
1. モジュールの設定を開き、次のフィールドに入力します。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Method]</td> 
      <td> <p>[!UICONTROL POST]</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td role="rowheader">[!UICONTROL Body type]</td> 
      <td> <p>[!UICONTROL Raw]</p> </td>
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Content type]</td> 
      <td> <p>[!UICONTROL XML (application/xml)]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Parse response]</td> 
      <td>[!UICONTROL Enabled]</td> 
     </tr> 
    </tbody> 
   </table>

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. 新しい Web ブラウザーウィンドウまたはタブを開きます。
1. WSDL URL を Web ブラウザーのアドレスバーに貼り付け、XML ファイルを取得します。

   通常、WSDL URL の末尾は `?wsdl` になりますが、そうでない場合もあります。例：`http://voip.ms/api/v1/server.wsdl`

1. WSDL ファイルが Web ブラウザーに直接表示されない場合は、ダウンロードしたファイルをテキストエディターで開きます。
1. 次の `<service>` または `<wsdl:service>` タグを探します。

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. 見つかったら、`location` 属性から URL をコピーします。
1. [!DNL Workfront Fusion] で、URL を HTTP モジュールの「URL」フィールドに貼り付けます。
1. 新しい web ブラウザーのウィンドウまたはタブで [Online [!UICONTROL SOAP] Client](https://wsdlbrowser.com/) を開きます。
1. WSDL URL を「WSDL URL」フィールドに貼り付けます。
1. **[!UICONTROL Browse]** をクリックします。
1. 左側の機能のリストから選択します。例：`getLanguages`
1. [!UICONTROL Request XML] のテキスト領域のコンテンツをコピーします。
1. [!UICONTROL Workfront Fusion] で、コピーしたコンテンツをモジュールの URL フィールドに貼り付けます。
1. 疑問符を実際の値に置き換えることで、選択したパラメーターの値を指定します。

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. 「**[!UICONTROL OK]**」をクリックしてモジュールの設定を閉じます。
1. シナリオまたはモジュールを実行します。
