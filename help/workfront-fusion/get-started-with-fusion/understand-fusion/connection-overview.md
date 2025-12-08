---
title: 接続の概要
description: ほとんどのアプリでは、接続を作成する必要があります。それによって、Adobe Workfront Fusion は特定のシナリオの設定に従って、特定のサードパーティサービスと通信できます。
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: ht
source-wordcount: '315'
ht-degree: 100%

---

# 接続の概要

Workfront Fusion は、ほとんどのアプリケーションで接続が必要です。この接続を使用して、特定のサードパーティサービスと通信します。

例えば、Workfront からの情報を取得するシナリオを作成する場合は、Workfront アカウントにアクセスするのに Workfront Fusion に対するアクセス権を付与する必要があります。

接続は、Fusion がアプリケーションへのアクセスに使用する認証と権限を表します。シナリオで使用する各アプリケーションに 1 つ以上の接続を作成し、複数のモジュールまたはシナリオで同じ接続を使用できます。

ほとんどの接続は、1 つのアプリケーションに対してのみ使用されます。例えば、Workfront 接続は [!UICONTROL Salesforce] モジュールでは使用できません。一部の [!DNL Adobe] アプリケーションは接続を共有できます。詳しくは、[Fusion アプリケーションとそのモジュールの参照：記事インデックス](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)にリストされているそれらのアプリケーションの記事を参照してください。

接続はチームが所有します。チームのすべてのメンバーはチームの接続にアクセスでき、チーム外のユーザーはチームの接続にアクセスできません。

## アクセス権

すべての接続に対して、Workfront Fusion では、特定のシナリオを正常に完了するのに必要なアクセス権のみが必要です。例えば、Workfront からドキュメントをダウンロードするシナリオを作成する場合は、Workfront Fusion は新しいプロジェクトを作成する権限を求めません。後でプロジェクトを作成する必要があることがわかった場合は、接続を更新するか、プロジェクトを作成できる新しい接続を作成できます。

一部のサービスでは特定のタスクへのアクセスを制限できません。このような場合、Workfront Fusion にはフルアクセス権が必要です。Workfront Fusion へのアクセスを、これらのサービスに登録されているアカウントに制限する方法について詳しくは、[Fusion アプリケーションとそのモジュールの参照：記事インデックス](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)にリストされているアプリケーション固有のドキュメントを参照してください。
