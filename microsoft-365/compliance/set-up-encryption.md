---
title: Office 365 Enterprise で暗号化を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Office 365 では、一部の暗号化機能が既定で有効になっています。その他の機能は、特定のコンプライアンスまたは法的な要件を満たすように構成できます。
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799992"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise で暗号化を設定する

暗号化によって、権限のないユーザーがコンテンツを読み取れないように保護することができます。 [Office 365 の暗号化](encryption.md)はさまざまなテクノロジと方法を使用して行うことができるため、暗号化をオンまたは設定する1つの場所がありません。 この記事では、情報保護戦略の一環として、暗号化をセットアップまたは構成するさまざまな方法について説明します。
  
> [!TIP]
> 暗号化に関する技術的な詳細情報については、「 [Office 365 の暗号化に関する技術リファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。
  
Office 365 では、いくつかの暗号化機能が既定で使用できます。 特定のコンプライアンスまたは法的な要件を満たすように、追加の暗号化機能を構成できます。 次の表では、さまざまなシナリオのいくつかの暗号化方法について説明します。
  
|**シナリオ**|**暗号化方法**|
|:-----|:-----|
|ファイルは Windows コンピューターに保存されます。  <br/> |コンピューターレベルでの暗号化は、Windows デバイス上で BitLocker を使用して行うことができます。 エンタープライズ管理者または IT プロフェッショナルは、Microsoft Deployment Toolkit (MDT) を使用してこれを設定できます。 「 [Set UP MDT For BitLocker」を](https://go.microsoft.com/fwlink/?linkid=849282)参照してください。  <br/> |
|ファイルはモバイルデバイスに保存されます。  <br/> |一部の種類のモバイルデバイスでは、既定でこれらのデバイスに保存されるファイルを暗号化します。 [Office 365 用の組み込みモバイルデバイス管理機能](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)を使用すると、モバイルデバイスから office 365 のデータへのアクセスを許可するかどうかを決定するポリシーを設定できます。 たとえば、コンテンツを暗号化するデバイスだけに Office 365 データへのアクセスを許可するポリシーを設定できます。 「[デバイスセキュリティポリシーの作成と展開」を](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)参照してください。  <br/> モバイルデバイスが Office 365 とどのように通信するかを制御するには、 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps)を追加することをお勧めします。  <br/> |
|Microsoft のデータセンターでデータを暗号化するために使用する暗号化キーを制御する必要がある  <br/> | Office 365 管理者は、組織の暗号化キーを制御し、Office 365 を構成して、Microsoft のデータセンターで保存されたデータを暗号化するために使用するように構成できます。  <br/> [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザーが電子メールで連絡している (Exchange Online)  <br/> | Exchange Online 管理者は、電子メールの暗号化を構成するためのいくつかのオプションがあります。 これには次のものが含まれます。  <br/>  Azure Rights Management (Azure RMS) で[Office 365 message encryption (OME)](set-up-new-message-encryption-capabilities.md)を使用して、ユーザーが組織の内部または外部に暗号化されたメッセージを送信できるようにする  <br/>  [メッセージの署名と暗号化に S/MIME](https://aka.ms/c6dozg)を使用して電子メールメッセージを暗号化し、デジタル署名する  <br/>  [他の組織とのセキュリティで保護されたメールフロー用のコネクタを設定](https://aka.ms/hs809p)するための TLS の使用 <br/>  「 [Office 365 の電子メールの暗号化」を](https://aka.ms/hic3f7)参照してください。  <br/> |
|ファイルは、チームサイトまたはドキュメントライブラリ (OneDrive for Business または SharePoint Online) からアクセスされます。  <br/> |ユーザーが OneDrive for business または SharePoint Online に保存されたファイルを使用している場合、TLS 接続が使用されます。 これは、Office 365 に自動的に組み込まれます。 「 [OneDrive For business および SharePoint Online のデータ暗号化](https://go.microsoft.com/fwlink/?linkid=526379)」を参照してください。  <br/> |
|オンライン会議および IM 会話でファイルが共有されている (Skype for Business Online)  <br/> |ユーザーが Skype for Business Online を使用してファイルを使用している場合、接続に TLS が使用されます。 これは、Office 365 に自動的に組み込まれます。 「 [Security And アーカイビング (Skype For Business Online)](https://aka.ms/nuq4ws)」を参照してください。  <br/> |
|オンライン会議および IM 会話でファイルが共有される (Microsoft Teams)  <br/> |ユーザーが Microsoft Teams を使用してファイルを扱う場合、TLS が接続に使用されます。 これは、Office 365 に自動的に組み込まれます。 現時点では、Microsoft Teams は暗号化された電子メールのインライン表示をサポートしていません。 Microsoft Teams での暗号化された電子メールを暗号化しないようにする方法については、「 [Message ENCRYPTION FAQ](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)」を参照してください。  <br/> 

## <a name="additional-information"></a>追加情報

暗号化オプションを含むファイル保護ソリューションの詳細については、「 [Office 365 のファイル保護ソリューション](https://www.microsoft.com/download/details.aspx?id=55523)」を参照してください。
 
