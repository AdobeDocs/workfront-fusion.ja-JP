---
title: AI を使用したシナリオセグメントの生成
description: AI を使用すると、シナリオのセグメントで行う必要のある作業を説明するテキストプロンプトを入力できます。 次に、Fusion は、シナリオで使用できるこれらのアクションを実行する 1 つ以上のモジュールを生成します。
author: Becky
feature: Workfront Fusion
exl-id: d231e33a-6033-4e3c-b1d4-7034797c45a5
source-git-commit: 2bec2607d55e4ba2ffd6ddcae6daa51071b204c4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 19%

---

# AI を使用したシナリオセグメントの生成

<!--DO NOT DELETE - linked through CSH-->

<!--Check if this is in GA before repo goes live. If not, hide this article.-->

<!--Check if they need to have signed the rider and stuff-->

AI を使用すると、シナリオのセグメントで行う必要のある作業を説明するテキストプロンプトを入力できます。 次に、Fusion は、シナリオで使用できるこれらのアクションを実行する 1 つ以上のモジュールを生成します。

生成されるシナリオセグメントには、単一のコネクタ用のモジュールが含まれます。 別のコネクタ用のモジュールを生成するには、別のプロンプトを作成し、シナリオのシナリオセグメントを結合します。

AI から生成されるものと同様に、生成されたモジュールを再確認およびテストして、意図したとおりに実行されていることを確認することをお勧めします。

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

## 前提条件

この機能を使用するには、組織が次の前提条件を満たしている必要があります。

* 組織がWorkfront AI アシスタント Beta プログラムに参加している。
* Adobeには、署名済みのAdobe生成 AI 契約が必要です。

  契約への署名の詳細については、ワークフロント ドキュメントの記事「AI アシスタントの概要」の [Adobe Systems Gen AI 契約に署名する](https://experienceleague.adobe.com/ja/docs/workfront/using/basics/ai-assistant/ai-assistant-overview#sign-the-adobe-gen-ai-agreement) を参照してください。

## 現在サポートされている AI モジュールアプリケーション

Fusion AI は、現在、次のアプリケーションに接続するモジュールを生成できます。

* Adobe Firefly
* Azure OpenAI
* Microsoft グラフ
* Adobe Workfront Planning
* Adobe Analytics
* Adobe PDF サービス
* Adobe Marketo
* Adobe Systems Frame.io
* Dropbox
* NetSuite
* Google カレンダー
* Atlassian Jira
* GitLab
* Spotify
* ビットバケット
* OpenAI
* Slack

## モジュールの生成

1. 左側のパネルで **[!UICONTROL シナリオ]** タブをクリックします。
1. モジュールを追加するシナリオを選択します。
1. シナリオの任意の場所をクリックして、シナリオ 編集者に入ります。
1. 画面の右上隅付近にある **AI アシスタント** アイコン ![AI アシスタント アイコン &#x200B;](assets/ai-assistant-icon.png) をクリックします。
1. AIアシスタントパネルにテキストプロンプトを入力します。

   プロンプトのヒントについては、この記事の [シナリオ セグメントのプロンプトを作成するためのヒント](#tips-for-creating-prompts-for-scenario-segments) を参照してください。

   AI アシスタントは、モジュールまたはモジュールのセットを生成します。
1. (オプション)必要に応じて、アプリケーションの API トークンをモジュールに追加します。
1. モジュールをチェックして、適切なアプリケーションとアクション用に構成されていることを確認します。
1. (オプション)生成されたシナリオセクションがシナリオに添付されていない場合は、所定の位置にドラッグします。

モジュールをテストして、意図したとおりに動作していることを確認することをお勧めします。

## シナリオセグメントのプロンプトを作成するためのヒント

テキストプロンプトには、少なくとも次の情報を含める必要があります。

* 接続先のアプリケーション
* 実行する 1 つ以上のアクション

>[!IMPORTANT]
>
>一度に複数のモジュールを生成できますが、一度に生成できるモジュールは 1 つのアプリケーションのみです。

>[!BEGINSHADEBOX]

**例**:

* `Delete the records 'xyz-123', 'xyz-456', 'xyz-789' from Adobe Workfront Planning`
これには、アプリケーション `Workfront Planning` とアクション `delete records` が含まれます。 このプロンプトは、削除されるレコードごとに 1 つずつ、3 つのモジュールを作成します。
* `Change campaign summary of the record 'xyz-123' from Adobe Workfront Planning`これには、アプリケーション `Workfront Planning` とアクション `change campaign summary`が含まれます。
* `Get all field details in the record type with ID 'test-record' from Adobe Workfront Planning`
これには、アプリケーション `Workfront Planning` とアクション `get field details` が含まれます。

次の例は正しくありません。

* `Generate an image in Adobe Firefly and upload it to Dropbox`

  この例には複数のアプリケーションが含まれているので、正しくありません

>[!ENDSHADEBOX]

テキストプロンプトを作成する場合は、次の点に注意してください。

* 直接的でシンプルな言語を使用します。
* シナリオセグメントを確認およびテストします。 期待どおりに動作しない場合は、プロンプトを調整して再試行してください。
