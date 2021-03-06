---
title: メール メッセージの安全性に関するヒント
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: EOP と Office 365 が、電子メールの上部に安全なヒントを追加することによって、スパム、フィッシング、およびマルウェアの防止をどのように保護するかについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6fb461619aaacafad86bb3c53731526fd00047a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209153"
---
# <a name="safety-tips-in-email-messages"></a>メール メッセージの安全性に関するヒント

Exchange Online Protection (EOP) と Microsoft 365 は、スパム、フィッシング、マルウェアの防止を強化します。 今日では、これらの攻撃の一部は正当なものであることがよく細工されています。 [迷惑メール] フォルダーにメッセージを送信するだけでは不十分なわけではありません。 これで、Outlook または web 上の Outlook または電子メールクライアントで電子メールを確認すると、EOP によって送信者が自動的に確認され、安全なヒントが電子メールの上部に追加されます。

Outlook の安全のヒントは、安全のヒントが開かれ、メッセージ本文に直接挿入されるため、使用している Outlook のバージョンには依存しません。 これは、使用しているすべての電子メールクライアントに安全なヒントが表示されることを意味します。 これは電子メールフィルターレベルで行われ、メールクライアントレベルでは表示されないので、どのバージョンの Outlook でも表示されるだけでなく、どのような電子メールクライアントにも表示されます。

安全性に関するヒント (色分けされたメッセージ) は、潜在的に有害なメッセージに関する警告を表示します。 受信トレイ内のほとんどのメッセージには安全なヒントがありません。 スパム、フィッシング、およびマルウェア攻撃を防止するために必要な情報が EOP と Microsoft 365 にある場合にのみ表示されます。 受信トレイに安全のヒントが表示される場合は、次の例を使用して、安全に関するヒントの種類について詳しく調べることができます。

- 疑わしいメール (赤安全ヒント)。

    ![赤の安全ヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    電子メールの赤の安全ヒントは、受信したメッセージに疑わしいものが含まれていることを意味します (フィッシング詐欺など)。 この種類の電子メールメッセージは、受信トレイからは開かずに削除することをお勧めします。

- スパム (黄色の安全性ヒント)。

    ![黄色の安全性ヒントを示すスクリーンショット。](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    電子メールの黄色の安全ヒントは、メッセージがスパムとしてマークされていることを意味します。 メッセージの送信者を認識して信頼していない場合は、添付ファイルや画像をダウンロードしないで、メッセージ内のリンクをクリックしないでください。 Outlook on the web では、迷惑メールアイテムの黄色のバーにある [**スパムではない**] をクリックして、メッセージを受信トレイに移動できます。 受信トレイに配信されたメッセージに黄色の安全ヒントが表示される場合は、迷惑メールフォルダーへのスパムの移動を無効にしている可能性があります。

- 安全なメール (緑色の安全ヒント)。

    ![緑の安全ヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについても、緑色の安全ヒントを示しています。 電子メールのグリーンセーフヒントは、メッセージの送信者を確認し、安全であることを確認したことを意味します。 Microsoft では、多くの場合、頻繁にスプーフィングまたは偽装される金融機関やその他の信頼できる差出人のリストを保持しています。

- フィルター処理なしのメール (灰色の安全ヒント)。

    ![灰色の安全なヒントを示すスクリーンショット。](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    また、差出人セーフリストにある送信者からのメールの確認や、フィルターをバイパスするメールフロールールがある場合にも、メールのチェックをスキップしたことについてもお知らせします。

    また、外部画像がブロックされている場合、つまりメッセージが受信トレイにあり、スパムではないが、ダウンロードしていない外部画像が含まれている場合にも、灰色の安全なヒントが表示されます。
    

## <a name="working-with-safety-tips"></a>安全に関するヒントの使用

セキュリティヒントは、すべてのメッセージが受信するわけではありませんが、Outlook on the web では常に有効になります。 管理者は、Outlook などの他の電子メールクライアントに対して安全のヒントを無効にすることができます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

EOP がメッセージを分類した方法 (つまり、メッセージがスパムではないか、またはスパムとしてマークされている必要がある) に同意しない場合は、Microsoft にメッセージを送信して、快適な操作を行うことができます。 手順については、「 [Microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。 また、安全性ヒントの [フィードバック] リンクをクリックして、ご意見を Microsoft に直接送信し、改善を支援することもできます。
