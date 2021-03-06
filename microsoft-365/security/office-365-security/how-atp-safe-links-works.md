---
title: ATP の安全なリンク機能のしくみ
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '[安全なリンク] 機能を使用すると、Office ドキュメントや電子メールメッセージ内のハイパーリンクの時間を確認できます。 ATP の安全なリンクのしくみについては、この記事をお読みください。'
ms.openlocfilehash: e79c44b91eb5de7564058b4dc50c94d2a4223f08
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046366"
---
# <a name="how-atp-safe-links-works"></a>ATP の安全なリンク機能のしくみ
> [!IMPORTANT] 
> Office 365 の ATP の安全なリンクが正しく動作するためには、すべてのサービスが同じバージョンになっている必要があります。
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>ATP の安全なリンクが電子メール内の Url と連携する方法

高レベルでは、(オンプレミスではなく Office 365 でホストされている) 電子メール内の Url に対して、 [ATP の安全なリンク](atp-safe-links.md)保護がどのように機能するかを説明します。
  
1. ユーザーが電子メールメッセージを受信します。その中には、Url が含まれています。
    
2. すべての電子メールは、インターネットプロトコル (IP) とエンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを適用する Exchange Online Protection によって処理されます。 
    
3. 電子メールは、ユーザーの受信トレイで到着します。
    
4. ユーザーが Office 365 にサインインし、電子メールの受信トレイに進みます。
    
5. ユーザーが電子メールメッセージを開き、電子メールメッセージ内の URL をクリックしたとき。
    
6. ATP の安全なリンク機能は、web サイトを開く前に、すぐに URL をチェックします。 URL は、ブロック、悪意、または安全として識別されます。
        
   - URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-atp.md)に含まれる web サイトに対するものである場合は、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。 
    
   - 悪意があると判断された web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が表示されます。 
    
   - URL がダウンロード可能なファイルに送られ、組織の[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)がそのようなコンテンツをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。 
    
   - URL が安全であると判断された場合は、web サイトが開きます。
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Office ドキュメントの Url で ATP の安全なリンクが機能するしくみ 

高レベルでは、エンタープライズまたはビジネスプレミアムアプリケーション用の Microsoft 365 アプリ (Windows、Mac、またはブラウザー、iOS または Android デバイス上の Office アプリ、ブラウザーでの OneNote) の Url に対して、 [ATP の安全なリンク](atp-safe-links.md)保護がどのように機能するかについて説明します。
  
1. ユーザーは、お客様のコンピューター、スマートフォン、またはタブレットに Microsoft 365 Apps for enterprise または Business Premium をインストールしています。 (または、ユーザーがブラウザーで Office を使用している場合)。
    
2. ユーザーが Word、Excel、PowerPoint、OneNote (ブラウザー)、または Visio (デスクトップ) を開き、職場または学校のアカウントを使用して Office 365 Enterprise にサインインします。 ドキュメントに Url が含まれている。
    
3. ユーザーがドキュメント内の URL をクリックすると、そのリンクは ATP の安全なリンクサービスによってチェックされます。
    
   - URL が組織のカスタムブロックされた[url リスト](set-up-a-custom-blocked-urls-list-atp.md)に含まれる web サイトに対するものである場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)に移動されます。
    
   - 悪意があると判断された web サイトに URL が設定されている場合、ユーザーは[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。
    
   - URL がダウンロード可能なファイルに送られ、そのようなダウンロードをスキャンするように[ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)が構成されている場合は、ダウンロード可能なファイルがチェックされます。 
    
   - URL が安全であると判断された場合は、ユーザーが web サイトに移動します。
      
   - URL チェックに失敗すると、安全なリンクの保護はトリガーされません。 デスクトップクライアントでは、ユーザーはサイトに進む前に警告が表示されます。
      
> [!NOTE]
> 各セッションの開始時に数秒間かかることがあり、ユーザーが Office 用の ATP の安全なリンクを有効にしていることを確認します。 
      
