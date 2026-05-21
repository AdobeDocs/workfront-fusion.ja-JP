---
title: SOAP モジュール
description: SOAP モジュールを使用して、Adobe Workfront Fusion で SOAP API に接続できます。
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
TQID: https://experienceleague.adobe.com/MIMXln44-LWfrQf0w-lZXfZJ3020Flty2CgwSC3JI9c
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 647
ht-degree: 60%

---

# [!UICONTROL SOAP] モジュール

[!UICONTROL SOAP]モジュールを使用して、[!UICONTROL Adobe Workfront Fusion]で[!UICONTROL SOAP]API に接続できます。

## SOAP モジュールとそのフィールド

SOAP コネクタに含まれるモジュールは1つだけです。SOAPの実行アクション

### SOAP アクションの実行

このアクションモジュールは、指定したSOAP アクションを実行します。



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
   <td role="rowheader">Adobe Workfront Fusion ライセンス</td> 
   <td>
   <p>オペレーションベース：Workfront Fusion ライセンス要件なし</p>
   <p>コネクターベース（レガシー）：Workfront Fusion for Work Automation および Integration </p>
   </td> 
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

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## SOAP モジュールとそのフィールド

SOAP モジュールを設定すると、Workfront Fusionに以下のフィールドが表示されます。  モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。 詳しくは、[モジュール間での情報のマッピング](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)を参照してください。

![マップ切り替え](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### SOAP アクションの実行

このアクションモジュールは、指定したWSDLに基づいてSOAP アクションを実行します。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL WSDL]</td> 
   <td> モジュールで使用するWSDLを選択します。 WSDLを作成するには、フィールドの横にある<b>追加</b>をクリックし、フィールドに入力します。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL HTTP ヘッダー]</td> 
   <td> 追加するHTTP ヘッダーごとに、<b>項目を追加</b>をクリックし、ヘッダーの名前と値を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL SOAP headers]</td> 
   <td> 追加する各SOAP ヘッダーについて、<b>Add item</b>をクリックし、ヘッダーの名前、値、名前空間およびXMLNSを入力します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Force SOAP headers]</td> 
   <td> SOAP 1.2のヘッダーを設定するには、このオプションを有効にします。 </td> 
  </tr> 
  </tbody> 
</table>

## [!UICONTROL SOAP] モジュールの制限事項

>[!NOTE]
>
>WDSLの読み込み中にリダイレクトは無効になります。 これはセキュリティ機能ですが、モジュールの実行時に未検証のリダイレクトがブロックされる場合があります。

[!UICONTROL SOAP] モジュールは現在ベータ版であり、次の機能をサポートしていません。

* 要素の再定義
* 小数部桁数の制限
* 合計桁数の制限
* 空白の制限
* マルチパートの入出力メッセージ。 シングルパートメッセージのみがサポートされています。
* SOAP エンコーディングスキーマとエレメントの助けを借りて定義されたカスタム XML スキーマ要素。

>[!BEGINSHADEBOX]

**例：**

以下は、[!UICONTROL Workfront Fusion] では正しく認識されません。

```
<complexType name="ArrayOfFloat">
   <complexContent>
      <restriction base="soapenc:Array">
         <attribute ref="soapenc:arrayType"
            wsdl:arrayType="xsd:integer[]"/>
      </restriction>
   </complexContent>
</complexType>
```

この例には、`soapenc:Array`、`soapenc:arrayType`および`wsdl:arrayType`の参照が含まれます。これらの参照は、[!UICONTROL Workfront Fusion]ではまだサポートされていません。

>[!ENDSHADEBOX]

## 回避策

[!UICONTROL SOAP] モジュールが WSDL ファイルの処理を拒否するか、モジュールの設定で様々なエラーが発生する場合は、代わりに、汎用の **[!UICONTROL HTTP]／[!UICONTROL リクエストの実行]**&#x200B;モジュールを使用してみてください。

1. Workfront Fusionで、新しいシナリオを作成します。
1. シナリオに **[!UICONTROL HTTP]／[!UICONTROL リクエストの実行]**&#x200B;モジュールを挿入します。
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

   <!--![Workaround](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. 新しい Web ブラウザーウィンドウまたはタブを開きます。
1. WSDL URL を Web ブラウザーのアドレスバーに貼り付け、XML ファイルを取得します。

   通常、WSDL URL の末尾は `?wsdl` になりますが、そうでない場合もあります。例：`http://voip.ms/api/v1/server.wsdl`

1. WSDL ファイルが Web ブラウザーに直接表示されない場合は、ダウンロードしたファイルをテキストエディターで開きます。
1. 次の `<service>` または `<wsdl:service>` タグを探します。

   <!--![Service](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. 見つかったら、`location` 属性から URL をコピーします。
1. Workfront Fusionで、URLをHTTP モジュールの&#x200B;**コンテンツをリクエスト** フィールドに貼り付けます。
1. 疑問符を実際の値に置き換えて、選択したパラメーターの値を指定します。

   >[!NOTE]
   >
   > WSDL ファイルから特定の値を取得するには、オンライン WSDL ビューアを使用します。

   <!--![Request](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. 「**[!UICONTROL OK]**」をクリックしてモジュールの設定を閉じます。
1. シナリオまたはモジュールを実行します。
