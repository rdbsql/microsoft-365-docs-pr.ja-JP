---
title: DKIM 署名付きメッセージの検証をサポートする
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online Protection と Exchange Online での DKIM 署名付きメッセージの検証について
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631207"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

Exchange Online Protection (EOP) および Exchange Online では、ドメインキー識別メール ([Dkim](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートしています。 DKIM は、メッセージがドメインから送信されたことを検証する方法です。これは、そのメッセージが送信者からのものであり、他のユーザーによってスプーフィングされていないことを示します。 これにより、電子メール メッセージがその送信を担当する組織に対応付けられます。 DKIM 検証は、IPv6 通信で送信されるすべてのメッセージに対して自動的に使用されます。 また、Microsoft 365 は、メールが IPv4 経由で送信されるときに、DKIM をサポートするようになりました。 (IPv6 のサポートの詳細については、「 [ipv6 経由の匿名受信電子メールメッセージのサポート](support-for-anonymous-inbound-email-messages-over-ipv6.md)」を参照してください)。

DKIM は、メッセージ ヘッダー内の DKIM 署名ヘッダーに表示されるデジタル署名付きメッセージを検証します。DKIM 署名検証の結果は RFC 7001 ([メッセージ認証状態を示すためのメッセージ ヘッダー フィールド](https://www.rfc-editor.org/rfc/rfc7001.txt)) に準拠した認証結果ヘッダー内でスタンプされます。メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

管理者は、DKIM 検証の結果に対して Exchange[メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)(トランスポートルールとも呼ばれます) を作成し、必要に応じてメッセージをフィルター処理またはルーティングすることができます。
