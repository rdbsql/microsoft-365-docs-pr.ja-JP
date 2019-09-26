---
title: Office 365 で差出人セーフリストを作成する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 特定の送信者からのメールを確実に受信できるようにする場合は、Exchange 管理センターでスパムフィルターポリシーの許可リストを調整できます。このようなメッセージを受信します。
ms.openlocfilehash: b01abc327dd19a2d3098d3c49deed1edb1c07b68
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086742"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Office 365 で差出人セーフリストを作成する

ユーザーが特定の送信者または送信者からの電子メールを確実に受信できるようにする場合は、複数の方法から選択できます。 これらのオプションには、Exchange トランスポートルール (Etr)、Outlook の信頼できる差出人、IP 許可一覧、スパム対策送信者/ドメイン許可リストなどがあります。

> [!IMPORTANT]
> 組織の許可リストは、誤検知を解決するために使用できますが、これは一時的なソリューションとして考慮され、可能な場合は回避されます。 許可リストを使用して誤検知を管理することは推奨されません。これは、誤ってスプーフィング、偽装、その他の攻撃を受けて組織を開く可能性があるためです。 この目的のために許可リストを使用する場合は、準備が整っている必要があります。また、[スパム、非スパム、フィッシングメールを分析のために Microsoft に送信](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)するための記事を準備しておく必要があります。

安全な送信者リストを構成するために推奨される方法は、Exchange トランスポートルール (Etr) を使用することです。これは、適切なメッセージのみが許可されることを確実にするために、最大限の柔軟性を提供することです。 ドメインは簡単にスプーフィングできるため、*スパム対策ポリシーの電子メールアドレス*と*ドメインベースの許可リスト*は、 *IP アドレスベースのリスト*ほど安全ではありません。 ただし、スパム対策ポリシー IP ベースの許可リストは、その IP を経由して送信されるすべてのドメインがスパムフィルタリングをバイパスすることを許可するので、リスクを提示します。 慎重に、発生し*た例外を*監視してください。

> [!IMPORTANT]
> **受信拒否リスト**を作成する方法については、[こちら](create-block-sender-lists-in-office-365.md)を参照してください。

## <a name="options-from-most-to-least-recommended"></a>推奨されるオプションのうち、最も少ないもの

許可リストは、多くのセキュリティ対策をバイパスするため、常に制限する必要があります。 すべての許可リストは、標準のメンテナンスの一部として再チェックする必要があります。これにより、だれがバイパスを許可されているかを認識できるようになります。 可能な限り、制限の厳しい Etr を使用することをお勧めします。

- Exchange トランスポートルール (Etr はメールフロールールとも呼ばれる)
- Outlook の差出人セーフリスト
- スパム対策ポリシー: IP 許可一覧
- スパム対策ポリシー: 送信者/ドメイン許可リスト

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>Exchange トランスポートルール (Etr) を使用して特定の送信者を許可する (推奨)

正当なメッセージだけが組織に許可されるようにするには、条件を次のいずれかにする必要があります。

- 送信側ドメインの送信者の認証状態を使用します。 これは、"dmarc = pass" または "dmarc = bestguesspass" が含まれていることを確認するために、認証結果ヘッダーをチェックすることによって行われます。 これにより、送信側ドメインが認証され、スプーフィングされていないことが確認されます。 [SPF](https://docs.microsoft.com/en-us/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [dkim](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、および[DMARC](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dmarc-to-validate-email)電子メール認証の詳細については、をクリックしてください。

- または、送信側ドメインが認証されていない場合は、送信側ドメインと送信元 IP (または IP 範囲 *) を使用*します。 *可能な限り、これ*を可能な限り安全なものにすることを目標にしてください。 /24 より大きい IP 範囲は推奨され*ていません*。 コンシューマーサービスまたは共有インフラストラクチャに属する IP アドレス範囲を追加しないようにします。

> [!IMPORTANT]
> NATted の IP アドレスを許可する場合は、許可の範囲を知るために、その NAT プールに関係するコンピューターを認識しておく必要があります。 IP アドレスが変更される可能性があり、NAT 参加者も変わる可能性があることに注意してください。 IP を含むすべての許可リストは、標準メンテナンスの一部として再チェックする必要があります。

- *必要に応じ*て、メッセージが組織の外部から発信される条件を追加します (これは暗黙的ですが、正しく構成されていないオンプレミスのサーバーのための条件として追加するのが適切です)。

- *必要に応じ*て、電子メールの件名または本文に一意のキーワードまたは語句を指定する場合は、この情報を追加の条件として使用して、メールフロールールによって許可される電子メールメッセージをさらに制限することができます。

ルールのアクションは、次のパターンに従う必要があります。

1. スパム信頼レベル (SCL) を-1 (スパムフィルタリングをバイパスする) に設定します。

2. ルールの動作を言うために、X ヘッダーを追加します。 次の例では、簡単なヘッダー「X-ETR: 認証された送信者`contoso.com`のスパムフィルタリングをバイパスする」を追加できます。 このルールに複数のドメインがある場合は、ヘッダーテキストを必要に応じて変更できます。**メッセージが ETR によりフィルタリングをスキップすると、スパム対策ヘッダーの [fv: SKN] がスタンプされます。**(**IP 許可一覧にある場合は、IPV: CAL もスタンプ**します)。 これはトラブルシューティングに役立ちます。

![スパムフィルターをバイパスするための GUI。](../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> スパムフィルターをスキップする条件として *、送信者ドメイン*のみのメールフロールールを構成しないでください。 この方法によって、スパム送信者は、送信ドメインのスプーフィング (または完全な電子メールアドレスの偽装) がすべてのスパムフィルタリングをスキップし、送信者の認証チェックが行われ、メッセージがユーザーの受信トレイに届くようになります。

![SCL をマイナス-1 に設定する方法について説明します。](../media/2-AllowList-SetsSCLMinus1.png)

自分が所有しているドメイン、またはよく使用さ`microsoft.com`れるドメイン (例:) を条件としてメールフロールールに追加しないでください。 これは、誤った俳優がフィルター処理されないようなメールを送信するための機会を生み出すため、リスクが高いと考えられます。

[ETR を作成する手順をクリックしてください (メールフロールールとも呼ば](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)れます)。

## <a name="use-outlook-safe-senders-end-user-managed"></a>Outlook の差出人セーフリストを使用する (エンドユーザーによる管理)

エンドユーザーは、アドレス、ドメイン、または IP アドレスをグローバルに承認する代わりに、Outlook の差出人セーフリストを使用してアドレスを送信することもできます。 この設定を行うための手順は、 [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)と[outlook クライアント](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)で異なります。 **差出人セーフリストが原因でメッセージが正常に承認された場合は、** スパム/スプーフィング/フィッシングフィルターがバイパスされることを示す [スパム対策: sfv: sfv] が表示されます。

## <a name="use-anti-spam-policy-ip-allow-lists"></a>スパム対策ポリシーの IP 許可一覧の使用

Etr を使用して、送信者の認証を検証する際に特定の送信者をグローバルに許可したり、ドメインと IP を一緒に結び付けることができない場合は、次に、その送信者を*スパム対策ポリシーの IP 許可一覧*に追加することをお勧めします。 [詳細な手順については、「Configure the connection filter policy document」を参照して](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)ください。 許可された IP アドレスの一覧を最低限に保持し、IP アドレス範囲を使用しないようにすることが重要です。 コンシューマーサービスまたは共有インフラストラクチャに属する IP アドレスの範囲を追加しないでください。また、許可された IP アドレスの一覧を定期的に確認して、不要になった IP アドレスを削除するようにして*ください*。

> [!CAUTION]
> 送信者の IP アドレスのみに基づいて許可するスパム対策ポリシーを構成すると、その IP アドレスからのすべてのメッセージに対するスパムフィルター処理が許可ルールによってスキップされます。 これにより、他の方法ではフィルターを使用していないメールを送信する、不正な俳優の危険性が生じます。このメソッドは、すべてのスパムフィルター、送信者の認証チェック、およびメッセージがユーザーの受信トレイに表示されることをスキップして、リスクを高めます。

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>スパム対策ポリシーの送信者/ドメイン許可リストを使用する

少なくとも、送信者/ドメインによる承認の方が望ましいオプションです。 このオプションは、スパム/スプーフィング/フィッシング保護を完全にバイパスし、送信者の認証を評価しない*場合に限り*、避ける必要があります。 この方法を使用すると、不適切な俳優からのメールを受信するリスクが高まり、テストの際にのみ、一時的に推奨されるものになります。 詳細な手順については、「[スパムフィルターポリシーの構成](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)」のドキュメントを参照してください。

これらのリストの最大数は、約1000エントリです。

> [!CAUTION]
> スパム対策ポリシーを構成して、[*送信者/許可] ドメインを許可*すると、許可リスト内の送信者からの、または b) 許可されたドメインの送信者からのメッセージがスパムフィルター処理によってスキップされます。 この方法では、スパム送信者が送信ドメインをスプーフィングする (または完全な電子メールアドレスを偽装する) スパムフィルター処理を省略し、送信者の受信トレイにメッセージを直接送信するリスクを大幅に向上させることができます。
> 
> 自分のドメインやよく使用するドメイン (例: `microsoft.com`) を条件としてメールフロールールに追加しないでください。 この方法は、悪意のある俳優がメールを送信する機会を作成し、それ以外の場合はフィルター処理されないようにすることになるため、リスクが高くなると考えられます。

> [!IMPORTANT]
> **受信拒否リスト**を作成する方法については、[こちら](create-block-sender-lists-in-office-365.md)を参照してください。