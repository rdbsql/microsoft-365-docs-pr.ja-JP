---
title: Office 365 での自動調査と応答によるカスタムレポートソリューションの使用
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 の自動調査と応答を、カスタムまたはサードパーティのレポートソリューションと統合する方法について説明します。
ms.openlocfilehash: 3df69c9118b3170924a99a1787761b1bb07aadfa
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175944"
---
# <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="b8604-104">カスタムまたはサードパーティのレポートソリューションに Office 365 Management Activity API を使用する</span><span class="sxs-lookup"><span data-stu-id="b8604-104">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="b8604-105">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)を使用すると、[自動調査に関する詳細情報](air-view-investigation-results.md)を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b8604-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="b8604-106">ただし、組織によっては、カスタムまたはサードパーティのレポートソリューションを使用する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b8604-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="b8604-107">このようなソリューションで自動調査に関する情報を統合する必要がある組織では、Office 365 Management Activity API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8604-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="b8604-108">これを設定するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8604-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="b8604-109">Resource</span><span class="sxs-lookup"><span data-stu-id="b8604-109">Resource</span></span>  |<span data-ttu-id="b8604-110">説明</span><span class="sxs-lookup"><span data-stu-id="b8604-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="b8604-111">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="b8604-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="b8604-112">Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b8604-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="b8604-113">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b8604-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="b8604-114">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Office 365 データにアクセスするための認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8604-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="b8604-115">これを設定するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b8604-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="b8604-116">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="b8604-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="b8604-117">Office 365 Management Activity API を使用して、Office 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="b8604-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="b8604-118">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8604-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="b8604-119">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b8604-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="b8604-120">Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="b8604-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="b8604-121">関連記事</span><span class="sxs-lookup"><span data-stu-id="b8604-121">Related articles</span></span>

- [<span data-ttu-id="b8604-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8604-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="b8604-123">Microsoft の脅威保護の自動化された調査と対応について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8604-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)