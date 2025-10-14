---
title: 接続の概要
description: ほとんどのアプリでは、特定のシナリオの設定に従って、Adobe Workfront Fusion が特定のサードパーティサービスと通信するための接続を作成する必要があります。
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# 接続の概要

Workfront Fusion は、ほとんどの場合、接続が必要です。  この接続を使用して、指定のサードパーティサービスと通信します。

例えば、Workfrontから情報を取得するシナリオを作成する場合は、Workfront アカウントにアクセスする権限をWorkfront Fusion に付与する必要があります。

接続は、Fusion がアプリケーションへのアクセスに使用する認証と権限を表します。 シナリオで使用する各アプリケーションに 1 つ以上の接続を作成し、複数のモジュールまたはシナリオで同じ接続を使用できます。

ほとんどの接続は、1 つのアプリケーションに対してのみ使用されます。 例えば、Workfront接続は [!UICONTROL Salesforce] モジュールでは使用できません。 一部の [!DNL Adobe] アプリケーションは接続を共有できます。 詳細については、「[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)」にリストされている各アプリケーションの記事を参照してください。

接続はチームが所有します。 チームのすべてのメンバーはチームの接続にアクセスでき、チーム外のユーザーはチームの接続にアクセスできません。

## アクセス権

Workfront Fusion では、すべての接続について、特定のシナリオを正常に実行するために必要なアクセス権のみを必要とします。 例えば、Workfrontからドキュメントをダウンロードするシナリオを作成した場合、Workfront Fusion は新しいプロジェクトを作成する権限を求めません。 後でプロジェクトを作成する必要があることがわかった場合は、接続を更新するか、プロジェクトを作成できる新しい接続を作成します。

すべてのサービスで、特定のタスクへのアクセスを制限できるわけではありません。 このような場合、Workfront Fusion にはフルアクセス権が必要です。 Workfront Fusion へのアクセスを、これらのサービスに登録されているアカウントに制限する方法について詳しくは、「[Fusion アプリケーションとそのモジュールのリファレンス：記事インデックス &#x200B;](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)」にリストされているアプリケーション固有のドキュメントを参照してください。
