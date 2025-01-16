---
title: 接続の概要
description: ほとんどのアプリでは、接続を作成する必要があります。それによって、 [!DNL Adobe Workfront Fusion]  は特定のシナリオの設定に従って、特定のサードパーティサービスと通信できます。
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 15%

---

# 接続の概要

Workfront Fusion は、ほとんどの場合、接続が必要です。  この接続を使用して、指定のサードパーティサービスと通信します。

例えば、[!DNL Workfront] から情報を取得するシナリオを作成する場合、[!DNL Workfront Fusion] が [!DNL Workfront] アカウントにアクセスする権限を付与する必要があります。

接続は、Fusion がアプリケーションへのアクセスに使用する認証と権限を表します。 シナリオで使用する各アプリケーションに 1 つ以上の接続を作成し、複数のモジュールまたはシナリオで同じ接続を使用できます。

ほとんどの接続は、1 つのアプリケーションに対してのみ使用されます。 例えば、[!DNL Workfront] 接続は [!UICONTROL Salesforce] モジュールでは使用できません。 一部の [!DNL Adobe] アプリケーションは接続を共有できます。 詳細については、「[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)」にリストされている各アプリケーションの記事を参照してください。

接続はチームが所有します。 チームのすべてのメンバーはチームの接続にアクセスでき、チーム外のユーザーはチームの接続にアクセスできません。

## アクセス権

すべての接続に対して、[!DNL Workfront Fusion] では、特定のシナリオを正常に完了するために必要なアクセス権のみが必要です。例えば、[!DNL Workfront] からドキュメントをダウンロードするシナリオを作成し [!DNL Workfront Fusion] 場合、新しいプロジェクトを作成する権限は要求されません。 後でプロジェクトを作成する必要があることがわかった場合は、接続を更新するか、プロジェクトを作成できる新しい接続を作成します。

すべてのサービスで、特定のタスクへのアクセスを制限できるわけではありません。 このような場 [!DNL Workfront Fusion]、フルアクセス権が必要です。 [!DNL Workfront Fusion] これらのサービスに登録されたアカウントへのアクセスを制限する方法について詳しくは、[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス ](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md) に記載されているアプリケーション固有のドキュメントを参照してください。
