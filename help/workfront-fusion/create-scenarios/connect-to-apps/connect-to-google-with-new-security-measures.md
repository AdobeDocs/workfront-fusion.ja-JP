---
title: 更新されたセキュリティ対策を使用して Google Services に Adobe Workfront Fusion を接続
description: Googleでは、ユーザーが API を使用する方法に制限が導入されています。 ここでは、これらの更新プログラムのセキュリティ対策を考慮して、Adobe Workfront Fusion をGoogleに接続する方法について説明します。
author: Becky
feature: Workfront Fusion
exl-id: eac7ba26-664e-464c-b05c-8c2ebf407fb3
source-git-commit: 362952ec85b0df2306ba117ba530e95201330cca
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 15%

---

# 更新されたセキュリティ対策を使用して Google Services に Adobe Workfront Fusion を接続

Googleでは、ユーザーが API を使用する方法に制限が導入されています。 ここでは、これらの更新プログラムのセキュリティ対策を考慮して、Adobe Workfront Fusion をGoogleに接続する方法について説明します。

## アクセス要件

+++ 展開すると、この記事の機能のアクセス要件が表示されます。

この記事で説明している機能を使用するには、次のアクセス権が必要です。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront パッケージ 
   <td> <p>任意</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront プラン</td> 
   <td> <p>新規：標準</p><p>または</p><p>現在：ワーク以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion ライセンス**</td> 
   <td>
   <p>現在：Workfront Fusion ライセンスは必要ありません。</p>
   <p>または</p>
   <p>レガシー：任意 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">製品</td> 
   <td>
   <p>新規：</p> <ul><li>Prime Workfront プランを選択する：組織がAdobe Workfront Fusion を購入する必要があります。</li><li>Ultimate Workfront プラン：Workfront Fusion が含まれています。</li></ul>
   <p>または</p>
   <p>現在：Adobe Workfront Fusion を購入する必要があります。</p>
   </td> 
  </tr>
 </tbody> 
</table>

このテーブルの情報について詳しくは、[ ドキュメントのアクセス要件 ](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md) を参照してください。

Adobe Workfront Fusion ライセンスについて詳しくは、[Adobe Workfront Fusion ライセンス ](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md) を参照してください。

+++

## Google サービスの制限事項

Googleでは、2020 年 6 月 1 日（PT）以降、ユーザーによる API の使用方法に関する制限を導入しました。 これらのセキュリティ対策により、Google ユーザーは、Google上で自身の個人データが漏洩したり、誤って使用されたりするのを防ぐことができます。

これらの制限は、Gmail およびGoogle Drive アプリに関連しています。

これらの制限について詳しくは、[Google API サービスユーザーデータポリシーの「特定の API 範囲に関するその他の要件」を参照してください ](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes)

制限付き範囲にアクセスするには、接続されたサービス（Adobe Workfront Fusion または API を介してユーザーのデータにアクセスするその他のサービス）を検証し、サービスがデータの使用方法について安全で透明性を持っていることを証明する評価書を用意する必要があります。 Workfront Fusion は、制限付きスコープへのアクセスに関するGoogleのすべての要件に準拠しています。 ただし、Workfront Fusion のサードパーティ製の接続サービスのほとんどは、評価書を持っていないので、Googleの条件に準拠していません。 そのため、Workfront Fusion はこれらのサービスにデータを送信できません。

## Google サービスの制限事項の例外

評価証明書を持たない未承認のサードパーティサービスが新しい制限に違反することなくデータを送信できるようにする例外措置がいくつかあります。これらは、Workfront Fusion OAuth クライアントを使用するGoogle Workspace、別の OAuth クライアントを使用するGoogle Workspace、または@gmail.comと@googlemail.comによって異なります。

* [Workfront Fusion OAuth クライアントを使用したGoogle Workspace](#google-workspace-with-workfront-fusion-oauth-client)
* [Google Workspaceと別の OAuth クライアント](#google-workspace-with-another-oauth-client)
* [@gmail.comおよび@googlemail.com](#gmailcom-and-googlemailcom)

### Workfront Fusion OAuth クライアントを使用したGoogle Workspace

Workfront Fusion では、ドメイン全体のインストールの例外を使用します。 ドメイン全体のインストールは、Google Workspaceのユーザーに適しており、ユーザーは制限なしに未承認のサービスを統合できます。 Google Workspaceのユーザーは、追加の手順を実行する必要がなく、未承認のサービスに直接接続できます。

### Google Workspaceと別の OAuth クライアント

Workfront Fusion OAuth クライアントを使用する代わりに独自の OAuth クライアントを使用する場合は、Google Workspaceのユーザーは、内部使用アプローチを通じてGoogle サービスに接続できます。 このオプションは、上級ユーザー向けです。手順については、[ カスタム OAuth クライアントを使用したAdobe Workfront Fusion のGoogle サービスへの接続 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md) を参照してください。

### @gmail.comおよび@googlemail.com {#gmailcom-and-googlemailcom}

@gmail.comまたは@googlemail.comを通じてGoogle サービスにアクセスするユーザーは、個人使用アプローチを通じてGoogle サービスに接続できます。 このオプションは、上級ユーザー向けです。手順については、[ カスタム OAuth クライアントを使用したAdobe Workfront Fusion のGoogle サービスへの接続 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md) を参照してください。

## よくある質問

* [Adobe Workfront Fusion で影響を受けるアプリは何ですか？](#what-apps-in-adobe-workfront-fusion-are-affected)
* [Google Workspace アカウントを持っていますか。](#do-i-have-a-g-suite-account)
* [@gmail.comまたは@googlemail.comのユーザーの場合はどうすればよいですか？](#what-should-i-do-if-im-gmailcom-or-googlemailcom-user)
* [Google Workspaceを使用している場合はどうすればよいですか？](#what-should-i-do-if-im-a-g-suite-user)

### Adobe Workfront Fusion で影響を受けるアプリは何ですか？ {#what-apps-in-adobe-workfront-fusion-are-affected}

（Gmail アカウントに接続されている）Google ドライブ、Gmail およびメール。

### Google Workspace アカウントを持っていますか。 {#do-i-have-a-g-suite-account}

メールアドレスが@gmail.comまたは@googlemail.comで終わる場合、お使いのアカウントはGoogle Workspace アカウントではありません。 Google アカウントが@my-company.comのようなカスタムドメインで終わる場合、そのアカウントはGoogle Workspace アカウントです。

### @gmail.comまたは@googlemail.com ユーザーの場合はどうすればよいですか？ {#what-should-i-do-if-im-gmailcom-or-googlemailcom-user}

これらの新しい制限事項は、Google Drive または Gmail を統合している場合にのみ適用されます。 Google Drive または Gmail に接続する場合は、次の操作を行います

* Google Workspaceに切り替える

  または

* カスタム OAuth クライアントを作成。 このオプションは、上級ユーザー向けです。

  手順については、[ カスタム OAuth クライアントを使用したAdobe Workfront Fusion のGoogle サービスへの接続 ](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md) を参照してください。

Google Drive または Gmail 以外のサービスを統合する場合、これらの制限事項は適用されません。

### Google Workspaceを使用している場合はどうすればよいですか？ {#what-should-i-do-if-im-a-g-suite-user}

必要なアクションはありません。
