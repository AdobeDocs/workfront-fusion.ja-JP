---
title: ストレージの概要
description: Storageとは、Workfront Fusionのページで、Adobe Enterprise Storage Management （ESM）リポジトリに直接アクセスでき、フォルダーの閲覧、ファイルのアップロードとダウンロード、バージョン履歴の表示、自動化シナリオの作成が可能です。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: d5568479d43bd5518adae5b66b132b4075e7f356
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 2%

---

# ストレージの概要

<!--Add to navigation articles once this goes to production-->

Workfront Fusionのストレージ領域では、Adobe Enterprise Storage Management （ESM）リポジトリに直接アクセスできます。 ユーザーは、Fusionから直接、フォルダーの参照、ファイルのアップロードとダウンロード、バージョン履歴の表示、自動化シナリオの作成をおこなうことができます。

ストレージはチームが所有しており、Adobe ストレージにアクセスするには、Adobe Identity Management System （IMS）にオンボーディングする必要があります。

Fusion ストレージ内のファイルはAdobe ファイル（adobe.com/files）にミラーリングされるので、Adobe ファイルでアクセスできるファイルはすべてFusion ストレージでアクセスできます。

ストレージの使用方法については、次を参照してください。

* [ストレージの初期化](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/initialize-storage.md)
* [Workfront Fusionでのストレージの表示と管理](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/view-and-manage-storage-in-workfront-fusion.md)
* [ストレージへのファイルのアップロード](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/upload-files-to-storage.md)
* [ストレージからファイルをダウンロード](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/download-files-from-storage.md)
* [ストレージからファイルを削除](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/delete-files-from-storage.md)
* [ストレージでのファイルのバージョン履歴の表示](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/view-storage-file-version-history.md)
* [ストレージからのシナリオの作成](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/create-scenarios-from-storage.md)

## ストレージの前提条件

Workfront Fusion ストレージ領域を使用するには、次の条件を満たす必要があります。

* **Adobe Identity Management System （IMS）**&#x200B;にオンボーディングされました
* 組織では&#x200B;**Adobe ストレージ**&#x200B;を利用できます
* ユーザーは&#x200B;**正しいAdobe IMS組織**&#x200B;にサインインしています（選択したFusion組織に一致する組織）
* ユーザーのアカウントには、**Adobe ストレージへのアクセス**&#x200B;があります

## 用語集

使用時

| 用語 | 定義 |
| ------ | ----------- |
| **リポジトリ** | Adobe ESMの最上位のストレージコンテナ。通常、プロジェクトまたはワークスペースにマッピングされる |
| **接続** | FusionとAdobe Storageの間の安全なリンクが、初期化中に自動的に作成されます。 トークンの自動更新によるAdobe IMS認証を使用する |
| **ESM** | Enterprise Storage Management、Adobeクラウドファイルストレージサービス |
| **IMS** | Adobe Identity Management System、Adobeの認証およびID プラットフォーム |

<!--

## UI Reference — Key Screens

### 1. Initialization Screen

* Cloud icon with **"Adobe Storage"** heading
* Description text explaining the feature
* **"Initialize Storage"** button (primary action)
* Error variants for access restriction, org mismatch, access denied, no storage found

### 2. Repository List

* Table with **Name** and **Region** columns
* **"Open"** action button per row

### 3. File Browser

* Breadcrumb navigation bar
* **"Upload File"** dropdown button (with "Upload File" and "Upload File in Scenario" options)
* File/folder table with **Name**, **Type**, **Size**, **Created** columns
* Floating action bar on file selection with: **Download**, **Download in Scenario**, **Versions**, **Delete**
* Upload/download progress banners (top-right corner)

### 4. Version History Panel

* Right-side slide-out panel
* Version list with date, version badge, and download button per entry
* **"current"** label on the latest version

-->
