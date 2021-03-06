---
title: 送信と受信のメール フロー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードの送信および受信メールフローウィジェットについて学習できます。
ms.openlocfilehash: a1070783f60edf2de62d78c3094e9c20e3dd26f3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635198"
---
# <a name="outbound-and-inbound-mail-flow"></a>送信と受信のメール フロー

**送信メールフロー**ウィジェットは、**コネクタレポート**と以前の**TLS 概要レポート**の情報を1つの場所で結合します。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの [送信および受信メールフロー] レポート](../../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

ウィジェットの情報は、Office 365 のコネクタと TLS メッセージ保護に関連しています。 詳細については、以下のトピックを参照してください。

- [Office 365 でコネクタを使用してメール フローを構成する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a>送信で保護されたメッセージ (TLS)

**送信および受信メールフロー**ウィジェットは、組織との間でメッセージが配信されるときに接続に使用される TLS 暗号化を表示します。 他の電子メールサービスで確立された接続は、両方の側で TLS が提供されるときに TLS によって暗号化されます。 このウィジェットは、メールフローの最終週のスナップショットを提供します。 [詳細の**表示**] をクリックすると、**送信中 (TLS) によって保護さ**れたメッセージには、組織に出入りするメッセージの TLS 保護が表示されます。

![セキュリティ & コンプライアンスセンターの送信中 (TLS) によって保護されたメッセージ](../../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

現時点では、TLS 1.2 は、Office 365 で提供される最も安全な TLS のバージョンです。 多くの場合、コンプライアンス監査に使用されている TLS 暗号化を知っておく必要があります。 ほとんどの場合、送信元および送信先の電子メールサーバー (それらを所有しておらず、Microsoft も対象としていません) との直接的な関係はありません。そのため、これらのサーバーで使用される TLS 暗号化を改善するためのオプションは多くありません。

ただし、[コネクタ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)を使用して、電子メールサーバーと Office 365 との間で送信されるメッセージに対して最適な TLS 保護を確保することができます。 Microsoft 365 と、パートナーに属する独自の電子メールサーバーまたはサーバー間のメールフローは、通常のメッセージよりも重要で重要なものなので、追加のセキュリティと警戒をこれらのメッセージに適用する必要があります。 独自の電子メールサーバーをアップグレードまたは修正して、使用されている TLS 暗号化を改善したり、パートナーに接続して同じ操作を実行したりすることができます。 **コネクタレポート**には、Microsoft 365 コネクタを使用するメッセージのメールフローボリュームと TLS 暗号化の両方が表示されます。

## <a name="connector-report"></a>コネクタレポート

[**送信中 (TLS)] ポップアップで保護**されたメッセージから、**コネクタレポート**のリンクをクリックすると、コネクタを使用して組織との間で送受信されたメッセージに関する情報がレポートに表示されます。 独自の電子メールサーバーと Microsoft 365 またはパートナーのサーバーと Office 365 間のコネクタを使用します。 各コネクタのメッセージボリュームと、接続の TLS 暗号化を使用できます。 また、コネクタを使用せずに Microsoft 365 で送受信されたメッセージのデータを表示することもできます。

**メールフロー**ビューには、過去1週間のコネクタを介してメッセージの量が表示されます。 日付範囲を変更するには、[**フィルター** ] を選択して、範囲を最大30日間まで拡大します。 [**すべてのメールフロー** ] ビューには、すべてのコネクタ経由で組織との間のすべてのメールフローが表示されます。 ドロップダウンメニューでは、名前によって特定のコネクタを選択できます。

ドロップダウンから [ **tls usage]** ビューを選択すると、そのコネクタ経由でメッセージに対する tls 保護の内訳を確認できます。 **Tls の概要レポート**レポートと同様に、このビューには、さまざまな tls バージョンの割合が表示されます。 TLS 1.0 接続の場合は、実際には、Office 365 で TLS 1.0 サポートが廃止された場合の問題を回避するために、電子メールサーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。 詳細については、「 [Office 365 の暗号化に関するテクニカルリファレンスの詳細](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)」を参照してください。

Insights コネクタの潜在的な TLS 暗号化の問題に注意を向けるために役立つコネクタを指します。 分析情報は次のとおりです。 **tls が25% を超え**ているか、 **tls 1.0 が50% を超え**ています。 このような洞察がある場合は、コネクタに関連付けられている電子メールサーバーを調査するか、パートナー組織に連絡する必要があります。

## <a name="see-also"></a>関連項目

メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
