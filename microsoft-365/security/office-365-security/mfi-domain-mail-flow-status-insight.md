---
title: トップ ドメインのメール フローの状態洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフローの状態に関する洞察を得ることができます。
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818593"
---
# <a name="top-domain-mail-flow-status-insight"></a>トップ ドメインのメール フローの状態洞察

**上位ドメインのメールフローの状態**に関する情報は、メールフローの観点から、組織のドメインの現在の状態を示します。 この洞察は、***メールフローに影響を与える***(たとえば、外部電子メールを受信できない) 問題が発生しているドメインを特定してトラブルシューティングするのに役立ちます。特に、ドメインの有効期限、または間違った MX レコードがあるドメイン。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインフローの状態の洞察](../../media/domain-mail-flow-status-selected.png)

[**詳細**] をクリックすると、各ドメインの状態の詳細が表示されるポップアップが表示されます。

ドメインに緑のチェックマークが表示されている場合は、現在の MX レコード (メールフローインサイトダッシュボードを参照した場合) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。

ドメインの赤色の x は、MX レコードが変更されており、過去6時間以内にドメインがメールを受信していないことを示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。

![トップドメインフローの状態に関する詳細ポップアップ](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a>関連項目

メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
