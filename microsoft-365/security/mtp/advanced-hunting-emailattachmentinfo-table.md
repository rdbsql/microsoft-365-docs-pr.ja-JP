---
title: 高度な捜索スキーマの EmailAttachmentInfo テーブル
description: 高度な捜索スキーマの EmailAttachmentInfo テーブルでのメール添付ファイルの情報について学習する
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、EmailAttachmentInfo、network message id、sender、recipient、attachment id、attachment name、マルウェア verdict
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
ms.openlocfilehash: c396689942a72a03120f0acd41d0d76abb720702
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899401"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**適用対象:**
- Microsoft Threat Protection



[高度な捜索](advanced-hunting-overview.md)スキーマの `EmailAttachmentInfo` テーブルには、Office 365 ATP によって処理されるメールの添付ファイルに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AttachmentId` | 文字列型 | 一意のメール添付ファイルの識別子 |
| `NetworkMessageId` | 文字列型 | Microsoft 365 によって生成される電子メールの一意識別子。 |
| `SenderFromAddress` | 文字列型 | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `RecipientEmailAddress` | 文字列型 | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `FileName` | 文字列型 | 記録されたアクションが適用されたファイルの名前 |
| `FileType` | 文字列型 | ファイル拡張子の種類 |
| `SHA256` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MalwareFilterVerdict` | 文字列型 | メールにマルウェアが含まれているかどうかに関する、メールのフィルター処理スタックの判定 (マルウェア、マルウェア以外) |
| `MalwareDetectionMethod` | 文字列型 | メールでマルウェアを検出するために使用される方法 (マルウェア対策エンジン、ファイル評価、ATP の安全な添付ファイル) |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
