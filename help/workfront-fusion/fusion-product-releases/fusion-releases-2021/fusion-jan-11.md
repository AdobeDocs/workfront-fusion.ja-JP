---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion リリースアクティビティ：2021年1月11日（PT）の週
description: このページでは、2021年1月11日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: d5732b6c-b039-4bf7-a7e6-e59b6e8f1a63
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 100%

---

# Workfront Fusion リリースアクティビティ：2021年1月11日（PT）の週

このページでは、2021年1月11日（PT）の週に Adobe Workfront Fusion で行われたすべての機能強化について説明します。

最近のすべての変更内容のリストについては、[Adobe Workfront Fusion リリースアクティビティ](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)を参照してください。

Workfront Fusion での最近のバグ修正のリストについては、[Workfront メンテナンスアップデート](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=ja)ページで、Workfront Fusion メンテナンスアップデートというラベルが付いたアップデートがあるか確認してください。

## Widen コネクタとモジュールが利用可能になります

Workfront Fusion を使用して、お使いの Widen アカウントに接続できるようになりました。Widen モジュールを使用すると、次のことが可能になります。

* コレクションに対してアセットを追加または削除
* ファイルのダウンロードやアップロード
* アセットのメタデータの読み取りや更新
* 指定した条件に基づいてアセットを検索
* コレクション内のアセットのリストの取得
* カスタム API 呼び出しを実行します。

## DataDog コネクタとモジュールが利用可能になります

Workfront Fusion を使用して、お使いの Datadog アカウントに接続できるようになりました。

DataDog モジュールを使用すると、次のことが可能になります。

* 時系列ポイントの投稿
* カスタム API 呼び出しの実行

## Cvent コネクタとモジュールが利用可能になります

Workfront Fusion 2.0 を使用して、お使いの Cvent アカウントに接続できるようになりました。

Cvent モジュールを使用すると、次のことが可能になります。

* 会議出席リクエストの作成
* 連絡先、イベントまたは招待者などのレコードの読み取り
* 指定した条件に基づくレコードの一覧表示
* 特定のイベントへの招待者の登録または追加
* 連絡先の更新または削除
* カスタム API 呼び出しを実行


## Microsoft Dynamics 365 コネクタとモジュールが利用可能になります

Workfront Fusion 2.0 を使用して、お使いの Microsoft Dynamics 365 アカウントに接続できるようになりました。Microsoft Dynamics 365 モジュールを使用すると、次のことが可能になります。

* Microsoft Dynamics 365 でレコードが追加または更新された場合のシナリオのトリガー
* Microsoft Dynamics 365 レコードの作成、読み取り、更新、削除
* カスタム API 呼び出しの実行

## DocuSign コネクタとモジュールが利用可能になります

Workfront Fusion 2.0 を使用して、お使いの Docusign アカウントに接続できるようになりました。Docusign モジュールを使用すると、次のことが可能になります。

* エンベロープがステータスを変更した際にシナリオをトリガーする
* エンベロープを作成する
* 既存のエンベロープに受信者を読み取り、送信、または追加する
* ドキュメント内のカスタムフィールドを追加または変更する
* ドキュメントをファイルとしてダウンロードする
* エンベロープにファイルをアップロードする
* カスタム API 呼び出しの実行

## シナリオ実行履歴の検索

以前のシナリオ実行の特定の情報が見つけやすくなりました。Fusion の新しい全文検索では、バンドルに含まれている任意のデータの実行履歴を検索できます。例えば、特定のタスクを作成した実行を識別するには、全文検索を使用してそのタスクの ID を検索することができます。

これまでは、特定の実行情報を見つけるには、それぞれの実行を個別に表示する必要がありました。

## Fusion 2.0 データストアの更新

データストアをカスタマイズしやすくなるように、新しい機能が追加されました。データストアの表示中に、次の操作を行えるようになりました。

* ドラッグ＆ドロップして列を並べ替え
* 1 つのセルを編集
* 複数行を追加


## HTTP コネクタを使用した API キー認証リクエストの実行

より柔軟に API にアクセスできるように、HTTP コネクタに新しいモジュールが追加されました。これで、アクセスする web サービスで API キーを使用する必要がある場合に、HTTP コネクタを使用してリクエストを実行できるようになりました。

## マッピングパネルで使用できる新しい関数

モジュール内の数式をカスタマイズしたり簡素化したりできるように、新しい関数がいくつか追加されました。

* この

  ```
  omit
  ```

  関数は、オブジェクトの指定のキーを省略し、残りのキーを返す一般関数です。
* この

  ```
  pick
  ```

  関数は、オブジェクトから指定のキーのみを選択する一般関数です。
* この

  ```
  escapeMarkdown
  ```

  関数は、テキスト内のすべての Markdown タグをエスケープする文字列関数です。
