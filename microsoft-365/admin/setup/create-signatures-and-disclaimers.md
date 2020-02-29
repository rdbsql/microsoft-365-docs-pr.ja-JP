---
title: 組織全体の署名と免責事項を作成する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 組織に対して送受信されるすべての電子メールメッセージに電子メール署名、法的免責事項、または開示ステートメントを追加する方法について説明します。
ms.openlocfilehash: 3d95e92c4994a99ab3426133580d70453a2f83eb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257034"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>組織全体の署名と免責事項を作成する

 組織で送受信されるメール メッセージに、メールの署名、法的免責事項、開示説明書を追加することができます。以下に示すように、すべての送受信メッセージに適用されるように設定できます。または、特定の単語やテキスト パターンを含むメッセージなど、特定のメッセージに適用することができます。

 会社全体の電子メール署名の作成に関する短いビデオを見ることができます。 <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

## <a name="create-a-signature-that-applies-to-all-messages"></a>すべてのメッセージに適用される署名を作成する

> [!TIP]
> 組織全体の署名は、何が含まれているかにかかわらず、"免責" と呼ばれます。 たとえば、署名だけでなく、自分の住所、法的免責事項、または必要な情報を含めることもできます。
    
::: moniker range="o365-worldwide"

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-germany"

<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> から管理センターにアクセスします。

::: moniker-end

1. Office 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)でアプリ![起動ツールのアプリ起動ツールのアイコンを選択し、[**管理者**] を選択します。
   
    アプリが見つからない場合は、アプリ起動ツールから、[**すべてのアプリ**] を選択して、利用できる Office 365 アプリのアルファベット順の一覧を表示します。そこから、特定のアプリを検索できます。 
    
2. [**管理センター**] を選択し、[ **Exchange**] を選択します。
    
3. [メールフロー] で、[**ルール**] を選択します。
    
4. [ **+** (追加)] アイコンを選択し、[免責事項の**適用**] を選択します。
    
5. ルールに名前を付けます。
    
6. [**このルールを適用**] で、 **[すべてのメッセージに適用]** を選択します。
    
    > [!TIP]
    > [こちら](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)を参照してください。 (このスコープの記事は Exchange Server 用ですが、Office 365 にも適用されます)。 
  
7. [実行する処理] の [ **免責事項を追加する**] はオンのままにします。 
    
8.  [**テキストの入力**] を選択して、免責事項を入力します。 
    
    > [!TIP]
    > [免責事項の書式設定の詳細](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)をご確認ください。 (この書式設定記事は Exchange Server 用ですが、Office 365 にも適用されます)。 

9. [ **1 つを選択**] を選択し、フォールバックオプションとして [**折り返し**] を選択します。 [ **OK**] を選択します。 これは、暗号化や別のメール設定のために免責事項を追加できない場合に、メッセージ エンベロープで免責事項がラップされることを意味します。
    
10. [ **このルールを次の重大度レベルで監査する**] はオンのままにします。次に、メッセージ ログに使用する [ **低**]、[ **中**]、または [ **高**] を選択します。 
    
11. 先にテストしない場合は、[ **強制**] を選択して免責事項を即時に有効にします。 
    
12. 追加の条件や例外を含めるには、[ **その他のオプション**] を選択します。 
    
13. 完了したら、[ **保存**] を選択します。 
    
## <a name="limitations-of-office-365-organization-wide-signatures"></a>Office 365 組織全体の署名の制限事項

Office 365 署名では、次の操作を行うことはできません。
  
- 最新の電子メールの返信または転送に直接署名を挿入する
    
- ユーザーの送信済みアイテムフォルダーにサーバー側の電子メール署名を表示する
    
- 電子メール署名に画像を埋め込む
    
- 更新できなかった変数を含む行をスキップします (例: ユーザーに対して値が指定されていないため)。
    
これらの機能を取得するには、サードパーティ製のツールを使用します。 **電子メール署名ソフトウェア**のインターネット検索を実行してください。 これらのプロバイダーの多くは Microsoft ゴールドパートナーであり、ソフトウェアによってこれらの機能が提供されます。 
  
## <a name="more-resources"></a>その他のリソース

- PowerShell の使用方法については、「 [Office 365 の組織全体のメッセージの免責事項、署名、フッター、またはヘッダー](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) 」を参照してください。 
    
