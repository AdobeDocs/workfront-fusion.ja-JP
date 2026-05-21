---
title: 暗号化
description: Adobe Workfront Fusion 暗号化モジュールを使用すると、任意のテキストデータを暗号化できます。 現在、AES256 と PGP（OpenPGP）を介したメッセージの暗号化をサポートしています。
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
TQID: https://experienceleague.adobe.com/C4okceW3ZngBJrcDS-qymjR16GwTb3pFfdZpG-CoSwc
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 863
ht-degree: 34%

---

# 暗号化

Adobe Workfront Fusion [!UICONTROL Encryptor] モジュールを使用すると、任意のテキストデータを暗号化できます。 現在、AES256 と PGP（[!UICONTROL OpenPGP]）を介したメッセージの暗号化をサポートしています。

これらのモジュールは、暗号化プロセスに関するある程度の知識を必要とします。

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



## PGP を使用したメッセージの暗号化と復号

PGP で暗号化および復号する場合、キーチェーンを使用し、秘密鍵または公開鍵（またはその両方）を作成する必要があります。

公開鍵と秘密鍵について詳しくは、[Adobe Workfront Fusion用語集](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md)を参照してください。

キーについて詳しくは、[ キー](/help/workfront-fusion/references/modules/keys.md)を参照してください。

## [!UICONTROL 暗号化]モジュールとそのフィールド

[!UICONTROL 暗号化]モジュールの設定時に、以下のフィールドが表示されます。 モジュール内の太字のタイトルは、必須フィールドを示します。

### AES復号（詳細）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、<b>Add</b>をクリックし、キーの名前、キー、およびエンコーディングタイプを入力します。</td>
    </tr>
    <tr>
        <td>Bits</td>
        <td>モジュールで128 ビットまたは256 ビットの暗号化を使用するかどうかを選択します。</td>
    </tr>
    <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>復号するデータを入力するか、マッピングします。</td>
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
        <td>使用する暗号アルゴリズムを選択します。
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>初期化ベクターエンコーディング</td>
        <td>使用する初期化ベクターエンコーディングを選択します。
        <ul>
        <li>UTF-8</li>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16進数</li>
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
        <li>16進数</li>
        </ul>
        </td>
    </tr>
</table>

### AES復号（シンプル）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、<b>Add</b>をクリックし、キーの名前、キー、およびエンコーディングタイプを入力します。</td>
    </tr>
   <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>復号するデータを入力するか、マッピングします。</td>
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
        <td>使用する秘密鍵を入力するか、マッピングします。</td>
    </tr>
</table>

### AES暗号化（高度）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、<b>Add</b>をクリックし、キーの名前、キー、およびエンコーディングタイプを入力します。</td>
    </tr>
    <tr>
        <td>Bits</td>
        <td>モジュールで128 ビットまたは256 ビットの暗号化を使用するかどうかを選択します。</td>
    </tr>
    <tr>
        <td>入力エンコーディング</td>
        <td>使用する入力エンコーディングのタイプを選択します。
        <ul>
        <li>バイナリ</li>
        <li>ASCII</li>
        <li>16進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>暗号化するデータを入力するか、マッピングします。</td>
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
        <td>使用する暗号アルゴリズムを選択します。
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>初期化ベクターエンコーディング</td>
        <td>使用する認証タグエンコーディングを選択します。
        <ul>
        <li>UTF-8</li>
        <li>バイナリ</li>
        <li>Base 64</li>
        <li>16進数</li>
        </ul>
        </td>
    </tr>
</table>

### AES暗号化（シンプル）

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>モジュールで使用するキーを選択します。 キーを作成するには、<b>Add</b>をクリックし、キーの名前、キー、およびエンコーディングタイプを入力します。</td>
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
        <td>暗号化するデータを入力するか、マッピングします。</td>
    </tr>
    <tr>
        <td>出力エンコーディング</td>
        <td>使用する出力エンコーディングのタイプを選択します。
        <ul>
        <li>Base 64</li>
        <li>バイナリ</li>
        <li>16進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>秘密鍵</td>
        <td>使用する秘密鍵を入力するか、マッピングします。</td>
    </tr>
</table>


### デジタル署名の作成

このモジュールでは、公開鍵と秘密鍵を使用してメッセージを復号できます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>この署名に使用する秘密鍵を選択します。 秘密鍵を追加するには、<b>Add</b>をクリックし、キーの名前、キーテキスト、およびパスフレーズを入力します。</td>
    </tr>
    <tr>
        <td>アルゴリズム </td>
        <td>RSA-SHA1とRSA-SHA256のどちらを使用するかを選択します。 </td>
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
        <li>16進数</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>データ</td>
        <td>署名を作成するデータを入力するか、マッピングします。</td>
    </tr>
</table>

### PGP メッセージを復号化

このモジュールでは、公開鍵と秘密鍵を使用してメッセージを復号できます。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>このメッセージに使用する受信者の秘密鍵を選択します。 秘密鍵を追加するには、<b>Add</b>をクリックし、キーの名前、キーテキスト、およびパスフレーズを入力します。</td>
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
        <td>送信者の秘密鍵を入力します。 これにより、送信者の ID を認証できます。</td>
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
