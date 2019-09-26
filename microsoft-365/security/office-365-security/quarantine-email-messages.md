---
title: Office 365 でメール メッセージを検疫する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Office 365 で受信メールメッセージの検疫を設定することができます。これは、スパム、バルク、フィッシングメール、マルウェアとしてフィルター処理された受信メールメッセージを後で確認するために保持することができます。
ms.openlocfilehash: 5590c9de9ff596c359910b5b1793004ae1913365
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086800"
---
# <a name="quarantine-email-messages-in-office-365"></a>Office 365 でメール メッセージを検疫する

Office 365 で受信メールメッセージの検疫をセットアップすることができます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含むメール、および指定されたメールフロールールと一致したメールを、後で確認するために保持することができます。
  
既定では、フィルター処理されたメッセージは受信者の迷惑メールフォルダーに送信されます。ただし、既定で検疫に送信されるマルウェアを含むメールは除きます。 管理者として、コンテンツフィルターポリシーを設定して、フィルター処理されたすべてのメッセージを検疫に送信することができます。 コンテンツフィルター処理されたメッセージに対して実行できるさまざまな操作は、「[スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」によって異なります。
  
ユーザーと管理者の両方が、検疫済みメッセージを操作できます。 ユーザーは、隔離された独自のフィルター処理されたメッセージのみを操作できます。 管理者は、すべてのユーザーの検疫済みメッセージを検索し、管理することができます。

> [!NOTE]
> フィッシングメールフロールール (トランスポートルールとも呼ばれる) によって検疫されたメッセージおよびメッセージは、管理者検疫でのみ使用できます。
  
検疫済みメッセージの使用の詳細については、次を参照してください。
  
- [管理者として検疫済みメッセージを管理する](manage-quarantined-messages-and-files.md)

- [ユーザーが検閲済みメッセージを検出して解放する](find-and-release-quarantined-messages-as-a-user.md)

- [ユーザースパム通知を使用してスパム検疫済みメッセージを解放して報告する](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [検疫に関する FAQ](quarantine-faq.md)