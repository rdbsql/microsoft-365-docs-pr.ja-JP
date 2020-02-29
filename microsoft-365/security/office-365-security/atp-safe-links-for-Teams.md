---
title: Office 365 では、Teams、safelinks、安全なリンク、悪意のあるリンク、office 365 ATP、Teams の安全なリンク、ユーザーが無効なリンクをクリックするのを停止する悪意のあるリンク
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: クリックしたときに Teams が安全なリンクにアクセスできるようになります。 1対1のチャット、グループ間、またはチャネル内のチャットを使用しているかどうか、および Office 365 ATP へのサブスクリプションがある場合は、このセーフティ機能を有効にして使用することができます。
ms.openlocfilehash: ba7ef2ae63b788ec94fbbb15c3c00312177a59d5
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341610"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>Teams での Office 365 の安全なリンク

> [!IMPORTANT]
> この機能は、2020年2月28日の Microsoft Teams テクノロジ導入プログラム (タップ) にあるお客様向けの**パブリックプレビュー**です。 このメモは、Teams の安全なリンクがより幅広く利用できる場合に記事から削除されます。

作業を管理するための Office 365 クラウドベースのアプリケーションである Microsoft Teams は、既に安全な添付ファイル (Office 365) を使用していますが、これでクリック時に安全なリンクにアクセスできるようになります。 1対1のチャット、グループ間、またはチャネル内のチャットを使用しているかどうか、および Office 365 ATP へのサブスクリプションがある場合は、この安全策を有効にして使用することができます。

そのしくみは次のとおりです。 

1. Teams アプリケーションを起動すると、Office 365 は、ユーザーが Office 365 ATP を使用している組織に所属しており、ユーザーが Microsoft Teams の保護が有効になっているアクティブな安全リンクポリシーの一部であることを確認します。

2. 上記の条件に該当する場合、Url は、チャット、グループチャット、チャネル、およびそのユーザーのタブでクリックしたときに検証されます。
 
## <a name="what-will-users-experience"></a>ユーザーにはどのような状況がありますか? 

保護されたすべてのユーザーには、次のような危険な Url があります。 

- リンクが Teams 会話、グループチャット、またはチャネルからクリックされた場合は、既定のブラウザーでページが表示されます。 固定されたタブからリンクがクリックされた場合は、そのページがそのタブ内の Teams GUI に表示され、セキュリティ上の理由から、ブラウザーで開くオプションは無効になります。

- このユーザーは、URL のサイトへの進行をブロックされます。

リンクを送信したユーザーが Office 365 ATP によって保護されていない場合は、自分のコンピューターで URL をクリックして、問題のサイトを解決することができます。 これにより、Office 365 管理者は、保護されたユーザーがどのようなものであるかを認識できるようになります。

![Teams ページの安全なリンクは、悪意のあるリンクを報告し、ページへの送信をブロックします。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Teams で、このページの [*戻る*] ボタンをクリックすると、そのページが閉じます (または、ユーザーが空白のページが閉じられる可能性があります)。 ただし、リンクをもう一度クリックすると、このページが表示されるように、サイトの評価が reassessment されます。

> [!NOTE]
>一部の Office 365 管理者は、[ブロック] ページで**続行**するかどうかのメッセージを有効にします。 ただし、安全なリンクによってサイトの評価が測定され、不足している場合は、これ以上のクリックスルーを行う必要はありません。 ユーザーが安全対策を省略することはお勧めしません。 続行する前に、この点を考慮に入れてください。 
