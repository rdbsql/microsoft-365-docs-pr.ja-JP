---
title: 概要-高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7bda309dbb1b601c77b6fb34ff9b8be14d5638d
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138280"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。 ネットワーク内のイベントを事前に検査して、興味深いインジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対して、無制限な捜索が容易になります。

同じ脅威を探しているクエリを使用して、カスタムの検出ルールを構築できます。 これらのルールは自動的に実行され、さまざまなイベントやシステムの状態を確認して応答します。これには、違反の疑いがあるアクティビティや不適切なコンピューターが含まれます。

Microsoft 365 セキュリティセンターでは、高度な検索はさまざまなワークスペースからのデータになるクエリをサポートしています。これには、Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からのデバイス、メール、アプリ、id に関するデータが含まれます。 高度な捜索を使用するには、[Microsoft Threat Protection を有効](mtp-enable.md)にします。

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。

| 学習目標 | 説明 | リソース |
|--|--|--|
| **言語に慣れる** | 高度な検索は、 [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいており、同じ構文および演算子をサポートしています。 最初のクエリを実行して、クエリ言語を学習します。 | [クエリ言語の概要](advanced-hunting-query-language.md) |
| **クエリ結果の使用方法について説明します。** | グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。 クエリをすばやく微調整して、より豊富な情報を取得する方法について説明します。 | [クエリ結果を操作する](advanced-hunting-query-results.md) |
| **スキーマを理解する** | スキーマとその列のテーブルについて、高レベルで十分に理解してください。 これにより、データを検索する場所およびクエリの作成方法を決定できます。 | [スキーマ リファレンス](advanced-hunting-schema-tables.md) |
| **定義済みのクエリを活用する** | さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。 | - [共有クエリを使用する](advanced-hunting-shared-queries.md)<br>- [ハントに移動](advanced-hunting-go-hunt.md) |
| **クエリを最適化する** | 効率的なクエリおよびメールとデバイスからのデータを結合するクエリを作成する方法を理解します。 | - [クエリのベストプラクティス](advanced-hunting-shared-queries.md) <br>- [複数のデバイスとメールを探します。](advanced-hunting-best-practices.md) |
| **カスタム検出ルールを作成する** | 高度な検索クエリを使用して、通知をトリガーし、応答アクションを自動的に適用する方法について説明します。 | - [ユーザー設定の検出の概要](custom-detections-overview.md)<br>- [カスタム検出ルール](custom-detection-rules.md) |

## <a name="get-access"></a>アクセス権を取得する
高度な検索やその他の[Microsoft の脅威保護](microsoft-threat-protection.md)機能を使用するには、Azure AD で適切なロールが割り当てられている必要があります。 エンドポイントデータへのアクセスは、Microsoft Defender ATP のロールベースのアクセス制御の設定の影響を受けます。 [Microsoft の脅威保護へのアクセスの管理について確認する](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度
高度な検索データは、それぞれ異なる方法で2つの異なる種類に分類できます。

- **イベントまたはアクティビティのデータ**—アラート、セキュリティイベント、システムイベント、および定期的な評価に関する表について説明します。 高度な検索では、このデータを収集するセンサーが、対応するクラウドサービスに正常に送信された直後に受信します。 たとえば、Microsoft Defender ATP および Azure ATP で利用可能になった直後に、ワークステーションまたはドメインコントローラーの正常なセンサーからのイベントデータのクエリを開始することができます。
- **エンティティデータ**—ユーザーとデバイスに関する統合情報を表に示します。 このデータは、Active Directory エントリなどの比較的静的なデータソースおよびイベントログなどの動的ソースから取得されます。 最新のデータを提供するために、新しい情報で15分ごとにテーブルが更新され、完全には設定されていない行が追加されます。 24時間ごとにデータが統合され、各エンティティについての最新の最も包括的なデータセットを含むレコードが挿入されます。

## <a name="related-topics"></a>関連項目
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)
