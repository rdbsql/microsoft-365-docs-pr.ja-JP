---
title: 分析のためにメッセージを手動で Microsoft に送信する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理者とエンドユーザーは、分析用に Microsoft に電子メールメッセージ (不良または無効なメールが許可されたメール) を送信する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6973330c4504bd6478265205f60798b3b7c1875
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811040"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>分析のためにメッセージを手動で Microsoft に送信する

> [!NOTE]
> Exchange Online メールボックスを使用している組織内の管理者である場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。 詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。

組織内のユーザーが迷惑メール (スパム) またはフィッシングメッセージを受信トレイで受信する場合や、迷惑メールとしてマークされているために正当な電子メールメッセージを受信しない場合は、ストレスがかかることがあります。 より正確になるように、スパムフィルターを常に微調整しています。

この処理を支援するには、誤検知 (不良としてマークされた良好な電子メール)、誤検知 (無効なメールが許可されている)、および Microsoft に対するフィッシングメッセージを分析用に送信します。

> [!NOTE]
> 大量の送信が送信されるため、分析のすべての要求に応答できない場合があります。

## <a name="submit-false-negatives-to-microsoft"></a>誤検知を Microsoft に送信する

> [!TIP]
> 次の手順を使用して誤検知を報告する代わりに、Outlook および web 上の Outlook (旧称 Outlook Web App) のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。 このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。

スパムまたはフィッシングとして識別されたスパムフィルタリングを通過したメッセージを受信した場合は、そのメッセージを Microsoft スパム分析および Microsoft フィッシング分析チームに適宜送信することができます。 アナリストはメッセージを確認し、分類基準を満たす場合は、サービス全体のフィルターに追加します。

1. 次のいずれかの受信者を使用して、新しい空の電子メールメッセージを作成します。

   - **迷惑メール**:`junk@office365.microsoft.com`

   - **フィッシング**:`phish@office365.microsoft.com`

2. 迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグアンドドロップします。 これにより、迷惑メールまたはフィッシングメッセージは新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。

   > [!NOTE]
   > <ul><li>新しいメッセージに複数のメッセージを添付することができます。 すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</li><li>新しいメッセージの本文は空のままにします。</li><li>添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</li></ul>

3. 完了したら、[**送信**] をクリックします。

> [!TIP]
> 管理者は、スパムとして misidentified されている特定のメッセージをブロックするいくつかの方法を用意しています。 詳細については、「 [EOP でブロックされる送信者のリストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。

## <a name="submit-false-positives-to-microsoft"></a>誤検知を Microsoft に送信する

> [!TIP]
> 次の手順を使用して誤検知を報告するのではなく、Outlook および web 上の Outlook のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。 このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。

メッセージが誤ってスパムとして識別された場合は、メッセージを Microsoft スパム分析チームに送信できます。 アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整して、メッセージを通過できるようにすることができます。

1. 受信者としての新しい空の電子メールメッセージを作成し `not_junk@office365.microsoft.com` ます。

2. Misidentified メッセージを新しいメッセージにドラッグアンドドロップします。 これにより、misidentified メッセージは新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。

   > [!NOTE]
   > <ul><li>新しいメッセージに複数のメッセージを添付することができます。 すべてのメッセージの種類が同一であることを確認してください。フィッシングメッセージと迷惑メールメッセージのいずれかです。</li><li>新しいメッセージの本文は空のままにします。</li><li>添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</li></ul>

3. 完了したら、[**送信**] をクリックします。

> [!TIP]
> 管理者は、特定のメッセージがスパムフィルタリングをスキップできるようにするいくつかの方法があります。 詳細については、「 [EOP での安全な送信者リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft に報告されたメッセージのコピーを受信するためのメールフロールールを作成する

手順については、「[メールフロールールを使用して、ユーザーが Microsoft に報告する内容を確認する」を](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)参照してください。
