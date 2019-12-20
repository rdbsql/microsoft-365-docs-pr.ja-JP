---
title: 高度な検索スキーマの DeviceEvents テーブル
description: 高度な検索スキーマの [その他のデバイスイベント (DeviceEvents)] テーブルのウイルス対策、ファイアウォール、およびその他のイベントの種類について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の探し、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、security events、antivirus、firewall、exploit guard、DeviceEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aec5751cf400f94abaf259aaa5fe2238b4b91311
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809340"
---
# <a name="deviceevents"></a>DeviceEvents

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な](advanced-hunting-overview.md)検索スキーマの`DeviceEvents`その他のデバイスイベントまたはテーブルには、さまざまなイベントの種類に関する情報が含まれています。これには、Windows Defender ウイルス対策や exploit protection などのセキュリティコントロールによってトリガーされるイベントが含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。


| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類 |
| `FileName` | 文字列型 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列型 | 記録されたアクションが適用されたファイルを含むフォルダ |
| `SHA1` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-256 通常、このフィールドは入力されません。使用可能な場合は SHA1 列を使用します。 |
| `MD5` | 文字列型 | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `AccountDomain` | 文字列型 | アカウントのドメイン |
| `AccountName` | 文字列型 | アカウントのユーザー名 |
| `AccountSid` | 文字列型 | アカウントのセキュリティ識別子 (SID) |
| `RemoteUrl` | 文字列型 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `RemoteDeviceName` | 文字列 | 影響を受けるコンピューターでリモート操作を実行したコンピューターの名前。 報告されるイベントによっては、この名前は完全修飾ドメイン名 (FQDN)、NetBIOS 名、またはドメイン情報のないホスト名の場合があります。 |
| `ProcessId` | int | 新しく作成されたプロセスのプロセス ID (PID) |
| `ProcessCommandLine` | 文字列型 | 新しいプロセスを作成するために使用されるコマンドライン |
| `ProcessCreationTime` | 日付型 | プロセスが作成された日付と時刻 |
| `ProcessTokenElevation` | 文字列型 | 新たに作成されたプロセスに適用されたユーザーアクセス制御 (UAC) 権限昇格が存在するかどうかを示すトークンの種類 |
| `LogonId` | 文字列型 | ログオンセッションの識別子。 この識別子は、再起動の間にのみ同じコンピューター上で一意です。 |
| `RegistryKey` | 文字列型 | 記録済みのアクションが適用されたレジストリキー |
| `RegistryValueName` | 文字列型 | 記録されたアクションが適用されたレジストリ値の名前 |
| `RegistryValueData` | 文字列型 | 記録された操作が適用されたレジストリ値のデータ |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemotePort` | int | 接続先のリモートデバイスの TCP ポート |
| `LocalIP` | 文字列型 | 通信時に使用されるローカルコンピューターに割り当てられた IP アドレス |
| `LocalPort` | int | 通信時に使用されるローカルコンピューターの TCP ポート |
| `FileOriginUrl` | 文字列型 | ファイルのダウンロード元の URL |
| `FileOriginIP` | 文字列型 | ファイルのダウンロード元の IP アドレス |
| `AdditionalFields` | 文字列型 | JSON 配列形式でのイベントに関する追加情報 |
| `InitiatingProcessSHA1` | 文字列型 | イベントを開始したプロセス (画像ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | 文字列型 | イベントを開始したプロセス (イメージファイル) の256。 通常、このフィールドは入力されません。使用可能な場合は SHA1 列を使用します。 |
| `InitiatingProcessFileName` | 文字列型 | イベントを開始したプロセスの名前 |
| `InitiatingProcessFolderPath` | 文字列型 | イベントを開始したプロセス (画像ファイル) を含むフォルダー |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | 文字列型 | イベントを開始したプロセスを実行するために使用されるコマンドライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日付と時刻 |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | 文字列型 | イベントを処理するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `InitiatingProcessMD5` | 文字列型 | イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ |
| `InitiatingProcessAccountDomain` | 文字列型 | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | 文字列型 | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | 文字列型 | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessLogonId` | 文字列型 | イベントを開始したプロセスのログオンセッションの識別子。 この識別子は、再起動の間にのみ同じコンピューター上で一意です。 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | 文字列型 | Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子 |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)