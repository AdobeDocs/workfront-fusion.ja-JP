---
title: SOAP モジュール
description: SOAP モジュールを使用して、Adobe Workfront Fusion で SOAP API に接続できます。
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: 3a27a51e10438e6cf8862bf28b1d58273bbaff36
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 37%

---

# [!UICONTROL SOAP] モジュール

[!UICONTROL SOAP] モジュールを使用して、[!UICONTROL Adobe Workfront Fusion] の [!UICONTROL SOAP] API に接続できます。

## SOAP モジュールとそのフィールド

SOAP コネクタには、「SOAPを実行」アクションという 1 つのモジュールのみが含まれます

### SOAP アクションの実行

このアクションモジュールは、指定されたSOAP アクションを実行します。



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
   <td> <p>新規：標準</p><p>または</p><p>現在：仕事以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>従来のバージョン：作業の自動化と統合のためのWorkfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront パッケージを選択する：Adobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront パッケージ：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

[!DNL Adobe Workfront Fusion] ライセンスについて詳しくは、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## SOAP モジュールとそのフィールド

SOAP モジュールを設定すると、以下に示 [!DNL Workfront Fusion] フィールドが表示されます。  モジュール内の太字のタイトルは、必須フィールドを示します。

フィールドまたは関数の上にマップボタンが表示されている場合は、このボタンを使用すると、そのフィールドの変数や関数を設定できます。詳しくは、[ モジュール間で情報をマッピングする ](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md) を参照してください。

![ マップ切り替え ](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### SOAP アクションの実行

このアクションモジュールは、指定した WSDL に基づいてSOAPのアクションを実行します。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL WSDL]</td> 
   <td> モジュールで使用する WSDL を選択します。 WSDL を作成するには、フィールドの横にある <b> 追加 </b> をクリックし、フィールドに入力します。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL HTTP headers]</td> 
   <td> 追加する HTTP ヘッダーごとに「<b> 項目を追加 </b>」をクリックし、ヘッダーの名前と値を入力します。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL SOAP headers]</td> 
   <td> 追加するSOAP ヘッダーごとに「<b> 項目を追加 </b>」をクリックし、ヘッダーの名前、値、名前空間および XMLNS を入力します。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Force SOAP headers]</td> 
   <td> SOAP 1.2 のヘッダーを設定する場合は、このオプションを有効にします。 </td> 
  </tr> 
  </tbody> 
</table>

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
* SOAPのエンコーディングスキーマと要素を利用して定義されたカスタム XML スキーマ要素。

>[!BEGINSHADEBOX]

**例：**

次の項目は [!UICONTROL Workfront Fusion] で正しく認識されません：

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

この例には、[!UICONTROL Workfront Fusion] でまだサポートされていない `soapenc:Array`、`soapenc:arrayType` および `wsdl:arrayType` 参照が含まれています。

>[!ENDSHADEBOX]

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

   <!--![Workaround](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. 新しい Web ブラウザーウィンドウまたはタブを開きます。
1. WSDL URL を Web ブラウザーのアドレスバーに貼り付け、XML ファイルを取得します。

   通常、WSDL URL の末尾は `?wsdl` になりますが、そうでない場合もあります。例：`http://voip.ms/api/v1/server.wsdl`

1. WSDL ファイルが Web ブラウザーに直接表示されない場合は、ダウンロードしたファイルをテキストエディターで開きます。
1. 次の `<service>` または `<wsdl:service>` タグを探します。

   <!--![Service](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. 見つかったら、`location` 属性から URL をコピーします。
1. [!DNL Workfront Fusion] で、URL を HTTP モジュールの「URL」フィールドに貼り付けます。
1. 新しい web ブラウザーのウィンドウまたはタブで [Online [!UICONTROL SOAP] Client](https://wsdlbrowser.com/) を開きます。
1. WSDL URL を「WSDL URL」フィールドに貼り付けます。
1. **[!UICONTROL Browse]** をクリックします。
1. 左側の機能のリストから選択します。例：`getLanguages`
1. [!UICONTROL Request XML] のテキスト領域のコンテンツをコピーします。
1. [!UICONTROL Workfront Fusion] で、コピーしたコンテンツをモジュールの URL フィールドに貼り付けます。
1. 疑問符を実際の値に置き換えることで、選択したパラメーターの値を指定します。

   <!--![Request](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. 「**[!UICONTROL OK]**」をクリックしてモジュールの設定を閉じます。
1. シナリオまたはモジュールを実行します。
