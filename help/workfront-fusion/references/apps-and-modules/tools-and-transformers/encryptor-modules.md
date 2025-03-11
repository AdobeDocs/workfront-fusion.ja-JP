---
title: 暗号化
description: Adobe Workfront Fusion 暗号化モジュールを使用すると、任意のテキストデータを暗号化できます。現在、AES256 と PGP（OpenPGP）を介したメッセージの暗号化をサポートしています。
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: 0689cfee7cf546a6c1f5f72c79a1e7be9df85a8c
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 28%

---

# 暗号化

[!DNL Adobe Workfront Fusion] [!UICONTROL 暗号化]モジュールを使用すると、任意のテキストデータを暗号化できます。現在、AES256 と PGP（[!UICONTROL OpenPGP]）を介したメッセージの暗号化をサポートしています。

これらのモジュールでは、暗号化プロセスに関する知識がある程度必要です。

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
   <p>Workfront Fusion のライセンス要件はありません。</p>
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

[!DNL Adobe Workfront Fusion] ライセンスについては、[[!DNL Adobe Workfront Fusion] ライセンス](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)を参照してください。

+++

## PGP を使用したメッセージの暗号化と復号

PGP で暗号化および復号する場合、キーチェーンを使用し、秘密鍵または公開鍵（またはその両方）を作成する必要があります。

公開鍵と秘密鍵について詳しくは、[Adobe Workfront Fusion 用語集 ](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md) を参照してください。

キーの詳細については、[ キー ](/help/workfront-fusion/references/modules/keys.md) を参照してください。

## [!UICONTROL 暗号化]モジュールとそのフィールド

[!UICONTROL 暗号化]モジュールの設定時に、以下のフィールドが表示されます。モジュール内の太字のタイトルは、必須フィールドを示します。

### AES 復号化（詳細）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、「<b> 追加 </b>」をクリックして、キーの名前、キー、エンコーディングタイプを入力します。</td>
    </tr>
    <tr>
        <td>ビット</td>
        <td>モジュールで 128 ビットまたは 256 ビットの暗号化を使用するかどうかを選択します。</td>
    </tr>
    <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>復号化するデータを入力またはマッピングします。</td>
    </tr>
    <tr>
        <td>出力エンコーディング</td>
        <td>使用する出力エンコーディングのタイプを選択します。
        <ul>
        <li>ASCII</li>
        <li>バイナリ</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>暗号アルゴリズム</td>
        <td>使用する暗号アルゴリズムを選択してください：
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>初期化ベクトルエンコーディング</td>
        <td>使用する初期化ベクターエンコーディングを選択します。
        <ul>
        <li>UTF-8</li>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>認証タグエンコーディング</td>
        <td>使用する認証タグエンコーディングを選択します。
        <ul>
        <li>UTF-8</li>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
</table>

### AES 復号化（シンプル）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、「<b> 追加 </b>」をクリックして、キーの名前、キー、エンコーディングタイプを入力します。</td>
    </tr>
   <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>復号化するデータを入力またはマッピングします。</td>
    </tr>
    <tr>
        <td>出力エンコーディング</td>
        <td>使用する出力エンコーディングのタイプを選択します。
        <ul>
        <li>ASCII</li>
        <li>バイナリ</li>
        <li>UTF-8</li>
        </ul>
        </td>
     </tr>
    <tr>
        <td>秘密鍵</td>
        <td>使用する秘密鍵を入力またはマッピングします。</td>
    </tr>
</table>

### AES 暗号化（詳細）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、「<b> 追加 </b>」をクリックして、キーの名前、キー、エンコーディングタイプを入力します。</td>
    </tr>
    <tr>
        <td>ビット</td>
        <td>モジュールで 128 ビットまたは 256 ビットの暗号化を使用するかどうかを選択します。</td>
    </tr>
    <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>ASCII</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>暗号化するデータを入力またはマッピングします。</td>
    </tr>
    <tr>
        <td>出力エンコーディング</td>
        <td>使用する出力エンコーディングのタイプを選択します。
        <ul>
        <li>ASCII</li>
        <li>バイナリ</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>暗号アルゴリズム</td>
        <td>使用する暗号アルゴリズムを選択してください：
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>初期化ベクトルエンコーディング</td>
        <td>使用する認証タグエンコーディングを選択します。
        <ul>
        <li>UTF-8</li>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
</table>

### AES 暗号化（シンプル）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、「<b> 追加 </b>」をクリックして、キーの名前、キー、エンコーディングタイプを入力します。</td>
    </tr>
   <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>ASCII</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>暗号化するデータを入力またはマッピングします。</td>
    </tr>
    <tr>
        <td>出力エンコーディング</td>
        <td>使用する出力エンコーディングのタイプを選択します。
        <ul>
        <li>Base 64</li>
        <li>バイナリ</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>秘密鍵</td>
        <td>使用する秘密鍵を入力またはマッピングします。</td>
    </tr>
</table>


### デジタル署名の作成

このモジュールでは、公開鍵と秘密鍵を使用してメッセージを復号できます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>この署名に使用する秘密鍵を選択します。 秘密鍵を追加するには、「<b> 追加 </b> をクリックし、鍵の名前、鍵のテキスト、パスフレーズを入力します。</td>
    </tr>
    <tr>
        <td>アルゴリズム </td>
        <td>RSA-SHA1 と RSA-SHA256 のどちらを使用するかを選択します。 </td>
    </tr>
   <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>ASCII</li>
        <li>バイナリ</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>出力エンコーディング</td>
        <td>使用する出力エンコーディングのタイプを選択します。
        <ul>
        <li>Base 64</li>
        <li>16 進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>署名を作成するデータを入力またはマッピングします。</td>
    </tr>
</table>

### PGP メッセージを復号化

このモジュールでは、公開鍵と秘密鍵を使用してメッセージを復号できます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>このメッセージに使用する受信者の秘密鍵を選択します。 秘密鍵を追加するには、「<b> 追加 </b> をクリックし、鍵の名前、鍵のテキスト、パスフレーズを入力します。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>送信者の公開鍵を入力します。 これにより、送信者の ID を認証できます。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>復号するメッセージをマッピングします。</td>
    </tr>
</table>

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
    </table>
