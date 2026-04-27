---
title: 更新されたセキュリティ対策を使用して Google Services に Adobe Workfront Fusion を接続
description: Googleでは、ユーザーがAPIを使用する方法に制限が導入されています。 この記事では、これらの更新プログラムのセキュリティ対策を考慮して、Adobe Workfront FusionをGoogleに接続する方法について説明します。
author: Becky
feature: Workfront Fusion
exl-id: eac7ba26-664e-464c-b05c-8c2ebf407fb3
source-git-commit: bbd1ec27e52127c8814188612a1e8d5cfab0cd25
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 27%

---

# 更新されたセキュリティ対策を使用して Google Services に Adobe Workfront Fusion を接続

Googleでは、ユーザーがAPIを使用する方法に制限が導入されています。 この記事では、これらの更新プログラムのセキュリティ対策を考慮して、Adobe Workfront FusionをGoogleに接続する方法について説明します。

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

## Google サービスの制限

Googleでは、2020年6月1日（PT）時点でユーザーがAPIを使用する方法に関する制限が導入されました。 これらのセキュリティ対策により、Googleをご利用のお客様は、Google上の個人情報の漏洩や悪用を防ぐことができます。

これらの制限は、GmailおよびGoogle Drive アプリに関連しています。

これらの制限について詳しくは、[Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes)の「Additional Requirements for Specific API Scopes」を参照してください

制限付き範囲にアクセスするには、接続されたサービス（Adobe Workfront FusionまたはAPIを介してユーザーのデータにアクセスするその他のサービス）を検証し、そのサービスがデータの使用方法について安全で透明性があることを証明するLetter of Assessmentを取得する必要があります。 Workfront Fusionは、制限付きスコープへのアクセスに関するGoogleのすべての要件に準拠しています。 しかし、Workfront Fusionのサードパーティのコネクテッドサービスの多くは、Letter of Assessmentを持っていないため、Googleの条件に準拠していません。 そのため、Workfront Fusionでは、これらのサービスにデータを送信することはできません。

## Google サービスの制限事項の例外

評価証明書を持たない未承認のサードパーティサービスが新しい制限に違反することなくデータを送信できるようにする例外措置がいくつかあります。 Google WorkspaceとWorkfront Fusion OAuth クライアント、Google Workspaceと別のOAuth クライアント、または@gmail.comと@googlemail.comによって異なります。

* [Google WorkspaceとWorkfront Fusion OAuth クライアント](#google-workspace-with-workfront-fusion-oauth-client)
* [Google Workspaceと別のOAuth クライアント](#google-workspace-with-another-oauth-client)
* [@gmail.comおよび@googlemail.com](#gmailcom-and-googlemailcom)

### Google WorkspaceとWorkfront Fusion OAuth クライアント

Workfront Fusionでは、ドメイン全体のインストール例外が使用されます。 Domain-wide Installationは、Google Workspace ユーザーに適しており、未承認のサービスを制限なく統合できます。 Google Workspaceを利用している場合、追加の手順を実行する必要はなく、未承認のサービスに直接接続できます。

### Google Workspaceと別のOAuth クライアント

Google Fusion OAuth クライアントを使用する代わりに独自のOAuth クライアントを使用するWorkfront Workspace ユーザーは、内部使用アプローチを使用してGoogle サービスに接続できます。 このオプションは、上級ユーザー向けです。 手順については、[ カスタム OAuth クライアントを使用してAdobe Workfront FusionをGoogle サービスに接続する](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)を参照してください。

### @gmail.comおよび@googlemail.com {#gmailcom-and-googlemailcom}

@gmail.comまたは@googlemail.comを介してGoogle サービスにアクセスするユーザーは、個人使用アプローチを使用してGoogle サービスに接続できます。 このオプションは、上級ユーザー向けです。 手順については、[ カスタム OAuth クライアントを使用してAdobe Workfront FusionをGoogle サービスに接続する](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)を参照してください。

## よくある質問

* [Adobe Workfront Fusionのどのアプリが影響を受けますか？](#what-apps-in-adobe-workfront-fusion-are-affected)
* [Google Workspaceのアカウントを所有していますか？](#do-i-have-a-g-suite-account)
* [@gmail.comまたは@googlemail.com ユーザーの場合はどうすればよいですか？](#what-should-i-do-if-im-gmailcom-or-googlemailcom-user)
* [Google Workspace ユーザーの場合はどうすればよいですか？](#what-should-i-do-if-im-a-g-suite-user)

### Adobe Workfront Fusionのどのアプリが影響を受けますか？ {#what-apps-in-adobe-workfront-fusion-are-affected}

Google Drive、Gmail、およびメール（Gmail アカウントに接続）。

### Google Workspaceのアカウントを所有していますか？ {#do-i-have-a-g-suite-account}

メールアドレスが@gmail.comまたは@googlemail.comで終わる場合、アカウントはGoogle Workspace アカウントではありません。 Google アカウントが@my-company.comなどのカスタムドメインで終わる場合は、Google Workspace アカウントです。

### @gmail.comまたは@googlemail.com ユーザーの場合はどうすればよいですか？ {#what-should-i-do-if-im-gmailcom-or-googlemailcom-user}

これらの新しい制限は、Google DriveまたはGmailを統合している場合にのみ適用されます。 Google DriveまたはGmailに接続する場合は、次の操作を実行できます

* Google Workspaceに切り替えます。

  または

* カスタム OAuth クライアントを作成。 このオプションは、上級ユーザー向けです。

  手順については、[ カスタム OAuth クライアントを使用してAdobe Workfront FusionをGoogle サービスに接続する](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)を参照してください。

Google DriveまたはGmail以外のサービスを統合する場合は、これらの制限は適用されません。

### Google Workspace ユーザーの場合はどうすればよいですか？ {#what-should-i-do-if-im-a-g-suite-user}

必要なアクションはありません。
