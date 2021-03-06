---
title: Microsoft Threat Protection の高度な捜索スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、データ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0cb275584acfc2ea0d2a2969694ee189f48a875d
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046049"
---
# <a name="understand-the-advanced-hunting-schema"></a>高度な捜索スキーマの概要

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な](advanced-hunting-overview.md)検索スキーマは、デバイス、アラート、id、およびその他のエンティティの種類に関するイベント情報または情報を提供する複数のテーブルで構成されています。 複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。

## <a name="get-schema-information-in-the-security-center"></a>セキュリティセンターでスキーマ情報を取得する
クエリを作成する際には、組み込みスキーマ参照を使用して、スキーマ内の各テーブルに関する以下の情報をすばやく取得します。

- [**テーブルの説明**]: テーブルに格納されているデータの種類と、そのデータのソース。
- **列**-表のすべての列。
- **アクションの種類**-列で、 `ActionType` テーブルでサポートされているイベントの種類を表す値を指定できます。 これは、イベント情報を含むテーブルに対してのみ提供されます。
- **サンプルクエリ**-テーブルを使用する方法を示すクエリの例です。

### <a name="access-the-schema-reference"></a>スキーマリファレンスにアクセスする
スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある [**参照の表示**] アクションを選択します。 [**スキーマ参照**] を選択して、テーブルを検索することもできます。   

![ポータル内スキーマリファレンスへのアクセス方法を示す画像 ](../../media/mtp-ah/ah-reference.png) 

## <a name="schema-tables"></a>スキーマ テーブル
次の参照は、スキーマ内のすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。 テーブル名と列名は、高度な捜索画面のスキーマ表現の一部として、セキュリティ センターにも一覧表示されます。

| テーブル名 | 説明 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | アラートに関連付けられているファイル、IP アドレス、Url、ユーザー、またはデバイス |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 重要な情報や脅威の分類など、Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からの通知  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | クラウドアプリとサービスのファイル関連アクティビティ |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント  |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | エンドポイントの証明書検証イベントから取得された署名済みファイルの証明書情報 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | ファイルの作成、変更、およびその他のファイル システム イベント |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL の読み込みイベント |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | OS 情報を含むマシン情報 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | デバイス上のサインインとその他の認証イベント |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | ネットワーク接続と関連イベント |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | アダプタ、IP アドレス、MAC アドレス、および接続されたネットワークとドメインを含むマシンのネットワーク プロパティ |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | プロセスの作成と関連イベント |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | レジストリ エントリの作成と変更 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | デバイス上のソフトウェアのインベントリ、およびこれらのソフトウェア製品の既知の脆弱性 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 電子メールに添付されたファイルに関する情報 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 の電子メールイベント (電子メール配信およびブロックイベントを含む) |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 がメールを受信者のメールボックスに配信した後の、配信後に発生するセキュリティイベント |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | メールの Url に関する情報 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory を含む、さまざまなソースからのアカウント情報 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory と Microsoft online services の認証イベント |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Active Directory オブジェクト (ユーザー、グループ、デバイス、ドメインなど) に対して実行されるクエリアクティビティ |

## <a name="related-topics"></a>関連トピック
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
