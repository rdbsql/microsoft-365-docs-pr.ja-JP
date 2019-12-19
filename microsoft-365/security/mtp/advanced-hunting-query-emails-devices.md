---
title: 高度な捜索を使用してデバイスとメール全体で脅威を見つける
description: デバイスとメールを対象とした一般的な捜索シナリオとサンプル クエリを説明します。
keywords: 高度な捜索、Office365 データ、Windows デバイス、Office 365 メールの正規化、メール、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b374aac84b309d18a88ee7248021b50a893e120c
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911313"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="68289-104">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="68289-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="68289-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="68289-105">**Applies to:**</span></span>
- <span data-ttu-id="68289-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="68289-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="68289-107">[Microsoft Threat Protection](advanced-hunting-overview.md) の高度な捜索を使用すると、Windows デバイスおよび Office 365 メール全体で積極的に脅威を捜索できます。</span><span class="sxs-lookup"><span data-stu-id="68289-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="68289-108">デバイスとメールの両方を対象としたクエリの作成方法を検討する上で役立つ捜索シナリオとサンプル クエリをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="68289-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="68289-109">メール アドレスからユーザー アカウントを取得する</span><span class="sxs-lookup"><span data-stu-id="68289-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="68289-110">[デバイスとメールを対象とする複数のテーブル](advanced-hunting-schema-tables.md)全体に対してクエリを作成する場合、送信者または受信者のメール アドレスからユーザー アカウント名を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68289-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="68289-111">これを行うには、メール アドレスからの *local-host* を使用します。</span><span class="sxs-lookup"><span data-stu-id="68289-111">To do this use the *local-host* from the email address:</span></span>

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="68289-112">この正規化の手法は、以下のシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="68289-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="68289-113">捜索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="68289-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="68289-114">既知の悪意のある送信者からのファイルがデバイスに存在するかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="68289-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="68289-115">悪意のあるファイルを送信するメール アドレスが判明している場合、このクエリを実行すると、その送信者からのファイルがデバイスに存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="68289-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="68289-116">このクエリは、マルウェア配布キャンペーンの影響を受けたデバイスの数を特定する目的などに使用できます。</span><span class="sxs-lookup"><span data-stu-id="68289-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
FileCreationEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="68289-117">悪意のあるメール受信後のログオン試行を確認する</span><span class="sxs-lookup"><span data-stu-id="68289-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="68289-118">このクエリは、既知の悪意のあるメールの受信後 30 分以内に受信者が実行したログオン試行のうち、最新のもの 10 件を見つけます。</span><span class="sxs-lookup"><span data-stu-id="68289-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="68289-119">このクエリを使用することで、メールの受信者のアカウントが侵害されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="68289-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
LogonEvents
| project LogonTime = EventTime, AccountName, ComputerName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="68289-120">既知の悪意のある送信者からのメール受信後の PowerShell アクティビティを確認する</span><span class="sxs-lookup"><span data-stu-id="68289-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="68289-121">悪意のあるメールには多くの場合、PowerShell コマンドを実行して追加のペイロードを配信するドキュメントや特別に細工した添付ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="68289-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="68289-122">既知の悪意のあるユーザーから送信されたメールに気付いた場合、このクエリを使用することで、その送信者からのメールの受信後 30 分以内に発生した PowerShell アクティビティを表示および確認できます。</span><span class="sxs-lookup"><span data-stu-id="68289-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
ProcessCreationEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = EventTime, AccountName, ComputerName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="68289-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="68289-123">Related topics</span></span>
- [<span data-ttu-id="68289-124">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="68289-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="68289-125">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="68289-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="68289-126">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="68289-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="68289-127">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="68289-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="68289-128">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="68289-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)