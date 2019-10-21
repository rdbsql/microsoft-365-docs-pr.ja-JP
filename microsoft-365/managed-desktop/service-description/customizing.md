---
title: サービスをカスタマイズする
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b2b74194c9b73e538fc1be937456b76deef75feb
ms.sourcegitcommit: eed48c21790d31a85292f7e39bf1e30c42f10d36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37523672"
---
# <a name="customize-the-service"></a><span data-ttu-id="47a95-103">サービスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="47a95-103">Customize the service</span></span>

<span data-ttu-id="47a95-104">Microsoft マネージドデスクトップは、合わせデバイスリスト、[標準デバイス設定](device-policies.md)、アプリケーション要件、および特定の[構成可能な設定](../working-with-managed-desktop/config-setting-overview.md)を提供します。これらの設定は、エンドユーザーにとって安全で生産的で快適な操作性を提供するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="47a95-104">Microsoft Managed Desktop provides a curated device list, [standard device settings](device-policies.md), applications requirements, and certain [configurable settings](../working-with-managed-desktop/config-setting-overview.md), all designed to provide a secure, productive, and pleasant experience for end users.</span></span> <span data-ttu-id="47a95-105">提供されたとおりにサービスを常に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47a95-105">It’s best to always stay with the service as provided.</span></span> <span data-ttu-id="47a95-106">ただし、一部のサービスの詳細が組織のニーズに完全に適合しない場合があることを認識しています。</span><span class="sxs-lookup"><span data-stu-id="47a95-106">However, we recognize that some details of the service might not fit exactly with your organization’s needs.</span></span> <span data-ttu-id="47a95-107">何らかの方法でサービスを変更する必要があると思われる場合は、次のプロセスに従って変更を依頼することが重要です。</span><span class="sxs-lookup"><span data-stu-id="47a95-107">If you feel you need to alter the service in some way, it’s important that you follow the following processes to request those changes.</span></span>

 
## <a name="types-of-customizations"></a><span data-ttu-id="47a95-108">カスタマイズの種類</span><span class="sxs-lookup"><span data-stu-id="47a95-108">Types of customizations</span></span>
<span data-ttu-id="47a95-109">カスタマイズは、Microsoft マネージドデスクトップ基本構成に追加または変更することができます。例としては、USB ポート構成から新しいセキュリティエージェントを展開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-109">A customization is any addition or change to the Microsoft Managed Desktop base configuration; examples range from USB ports configuration to deploying a new security agent.</span></span> <span data-ttu-id="47a95-110">さまざまなカスタマイズを次のようにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="47a95-110">We group various customizations as follows:</span></span>


|<span data-ttu-id="47a95-111">型</span><span class="sxs-lookup"><span data-stu-id="47a95-111">Type</span></span>  |<span data-ttu-id="47a95-112">説明</span><span class="sxs-lookup"><span data-stu-id="47a95-112">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="47a95-113">生産性向上ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="47a95-113">Productivity software</span></span>     |  <span data-ttu-id="47a95-114">エンドユーザーが必要とするフォアグラウンドソフトウェア、[アプリケーション要件](mmd-app-requirements.md)による制限</span><span class="sxs-lookup"><span data-stu-id="47a95-114">Foreground software needed by end users, restricted by the [application requirements](mmd-app-requirements.md)</span></span>       |
|<span data-ttu-id="47a95-115">Vpn & のセキュリティエージェント</span><span class="sxs-lookup"><span data-stu-id="47a95-115">Security agents & VPNs</span></span>     |  <span data-ttu-id="47a95-116">デバイスまたはネットワークの動作をセキュリティで保護、監視、または変更するために使用されるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="47a95-116">Software used to secure, monitor, or change the behavior of the device or network</span></span>       |
|<span data-ttu-id="47a95-117">デジタル環境の監視</span><span class="sxs-lookup"><span data-stu-id="47a95-117">Digital experience monitoring</span></span>     |  <span data-ttu-id="47a95-118">ユーザーのデバイス上のデータを追跡してレポートを作成するために使用されるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="47a95-118">Software used to track data on a user’s device to report to IT</span></span>       |
|<span data-ttu-id="47a95-119">ハードウェアまたはソフトウェアのドライバー</span><span class="sxs-lookup"><span data-stu-id="47a95-119">Hardware or software drivers</span></span>     |   <span data-ttu-id="47a95-120">デバイスドライバー。[アプリケーション要件](mmd-app-requirements.md)による制限</span><span class="sxs-lookup"><span data-stu-id="47a95-120">Device drivers, restricted by the [application requirements](mmd-app-requirements.md)</span></span>      |
|<span data-ttu-id="47a95-121">ポリシー</span><span class="sxs-lookup"><span data-stu-id="47a95-121">Policies</span></span>     | <span data-ttu-id="47a95-122">管理対象デバイスでの Windows 10 または Office 365 ProPlus の設定</span><span class="sxs-lookup"><span data-stu-id="47a95-122">Windows 10 or Office 365 ProPlus settings on a managed device</span></span>        |
|<span data-ttu-id="47a95-123">デバイス</span><span class="sxs-lookup"><span data-stu-id="47a95-123">Devices</span></span>     | <span data-ttu-id="47a95-124">Microsoft マネージドデスクトップ[デバイスリスト](device-list.md)にないデバイス</span><span class="sxs-lookup"><span data-stu-id="47a95-124">Devices which are not on the Microsoft Managed Desktop [device list](device-list.md)</span></span>        |
|<span data-ttu-id="47a95-125">Other</span><span class="sxs-lookup"><span data-stu-id="47a95-125">Other</span></span>     |  <span data-ttu-id="47a95-126">他の領域でカバーされていないもの</span><span class="sxs-lookup"><span data-stu-id="47a95-126">Anything not covered by the other areas</span></span>       |



 
## <a name="request-a-customization"></a><span data-ttu-id="47a95-127">カスタマイズを要求する</span><span class="sxs-lookup"><span data-stu-id="47a95-127">Request a customization</span></span>

<span data-ttu-id="47a95-128">変更要求を作成して、Microsoft 管理対象デスクトップ管理ポータル経由で要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="47a95-128">Submit requests through the Microsoft Managed Desktop Admin portal by creating a change request.</span></span> <span data-ttu-id="47a95-129">次の詳細を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="47a95-129">Be sure to include these details:</span></span>
-   <span data-ttu-id="47a95-130">カスタマイズの種類: カスタマイズのカテゴリはどれですか。</span><span class="sxs-lookup"><span data-stu-id="47a95-130">Customization type: Which category of customization is it?</span></span> <span data-ttu-id="47a95-131">(前の表を参照)</span><span class="sxs-lookup"><span data-stu-id="47a95-131">(see the previous table)</span></span>
-   <span data-ttu-id="47a95-132">要件: カスタマイズの特定のビジネス要件は何ですか。</span><span class="sxs-lookup"><span data-stu-id="47a95-132">Requirement: What is the specific business requirement for the customization?</span></span>
-   <span data-ttu-id="47a95-133">提案: ビジネスが要求しているのはどのソリューションですか?</span><span class="sxs-lookup"><span data-stu-id="47a95-133">Proposal: Which solution is your business requesting?</span></span>
-   <span data-ttu-id="47a95-134">タイムライン: どのくらいの期間、このカスタマイズを最後にしますか?</span><span class="sxs-lookup"><span data-stu-id="47a95-134">Timeline: How long do you want this customization to last?</span></span> 


## <a name="how-we-assess-a-customization-request"></a><span data-ttu-id="47a95-135">カスタマイズ要求を評価する方法</span><span class="sxs-lookup"><span data-stu-id="47a95-135">How we assess a customization request</span></span>

<span data-ttu-id="47a95-136">カスタマイズ要求を確認するときは、次の順序でこれらの要素を評価します。</span><span class="sxs-lookup"><span data-stu-id="47a95-136">When we review customization requests, we assess these factors in this order:</span></span>
 
1.  <span data-ttu-id="47a95-137">Microsoft Managed Desktop がすべてのデバイスに展開されているアプリケーションとポリシーによってはネゴシエートできない場合があるため、要求がそれらに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="47a95-137">Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable, so your request must not affect those.</span></span> <span data-ttu-id="47a95-138">詳細については、「[デバイスの構成](device-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a95-138">See [Device configuration](device-policies.md) for more information.</span></span>
2.  <span data-ttu-id="47a95-139">エンドユーザーがジョブを実行するために必要な制限のある生産性ソフトウェアは、承認される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="47a95-139">Restricted productivity software required by an end user to do their job will likely be approved.</span></span> 
3.  <span data-ttu-id="47a95-140">Microsoft テクノロジを使用して要件を満たすことができる場合は、3 ~ 12 か月の移行期間の要求を承認する可能性があります (プロジェクトのスコープによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="47a95-140">If we can meet your requirement by using Microsoft technology, we’ll likely approve your request for a  migration period of three to twelve months (depending on the scope of the project).</span></span>
4.  <span data-ttu-id="47a95-141">Microsoft テクノロジを使用して要件を満たすことができない場合は、以下の条件のいずれかに違反しない限り、要求を承認する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="47a95-141">If we can’t meet your requirement by using Microsoft technology, we’ll likely approve your request unless it violates one of the conditions below.</span></span>  

<span data-ttu-id="47a95-142">これらの原則により、Microsoft マネージドデスクトップは、標準テンプレートからの逸脱を追跡しながら、常にニーズを満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="47a95-142">These principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.</span></span> 

## <a name="key-conditions"></a><span data-ttu-id="47a95-143">重要な条件</span><span class="sxs-lookup"><span data-stu-id="47a95-143">Key conditions</span></span>

<span data-ttu-id="47a95-144">カスタマイズを確認して、次の条件に違反していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="47a95-144">We review customizations to ensure they don't violate any of these conditions:</span></span>

-   <span data-ttu-id="47a95-145">カスタマイズがシステムセキュリティに悪影響を及ぼすことはありません。</span><span class="sxs-lookup"><span data-stu-id="47a95-145">A customization must not adversely impact system security.</span></span> 
-   <span data-ttu-id="47a95-146">カスタマイズを維持するには、Microsoft の管理されたデスクトップの操作またはサポートのコストが大きくならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-146">Maintaining the customization must not incur a significant cost for either Microsoft Managed Desktop operations or support.</span></span>
-   <span data-ttu-id="47a95-147">カスタマイズは、カーネルモードのクラッシュやハングなどによって、システムの安定性に影響しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-147">A customization must not affect system stability, for example, by causing kernel mode crashes or hangs.</span></span>
-   <span data-ttu-id="47a95-148">この変更によって、サービスの運用または Microsoft マネージドデスクトップのコアテクノロジとの競合が制限されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-148">The change must not restrict us from operating the service or conflict with core Microsoft Managed Desktop technology.</span></span>

<span data-ttu-id="47a95-149">これらの条件は将来変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-149">These conditions could change in the future.</span></span> <span data-ttu-id="47a95-150">このような変更を行う場合は、これらの条件が有効になる前に、30日の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="47a95-150">If we do make such changes, we’ll provide 30 days notice prior to those conditions coming into effect.</span></span>

## <a name="revoking-approval-for-a-customization"></a><span data-ttu-id="47a95-151">カスタマイズの承認を取り消す</span><span class="sxs-lookup"><span data-stu-id="47a95-151">Revoking approval for a customization</span></span>

<span data-ttu-id="47a95-152">要求されたカスタマイズが承認および展開された後、最初の場所で変更を承認したときに明らかになっていない重要な条件に違反する問題を発見する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-152">After a requested customization is approved and deployed, it’s possible that we might discover problems that violate the key conditions that weren’t evident when we approved the change in the first place.</span></span> <span data-ttu-id="47a95-153">このような状況では、カスタマイズの承認を取り消す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-153">In this situation, we might have to revoke approval for the customization.</span></span>
 
<span data-ttu-id="47a95-154">このような状況が発生した場合は、Microsoft Managed Desktop 管理ポータルを使用して通知します。</span><span class="sxs-lookup"><span data-stu-id="47a95-154">If this happens, we’ll notify you by using the Microsoft Managed Desktop admin portal.</span></span> <span data-ttu-id="47a95-155">初めて通知を受けたときに、カスタマイズを含むデバイスが Microsoft 管理対象デスクトップサービスレベル契約によってバインドされなくなる前に、90日でカスタマイズを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="47a95-155">From the first time we notify you, you have 90 days to remove the customization before the devices with the customization are no longer bound by Microsoft Managed Desktop service level agreements.</span></span> <span data-ttu-id="47a95-156">厳密なタイムラインに従っていくつかの通知を送信します。ただし、重大なインシデントや脅威では、タイムラインを変更したり、カスタマイズに関する決定を行ったりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47a95-156">We'll send you several notifications according to a strict timeline--however, a severe incident or threat might require us to change the timeline or our decisions about a customization.</span></span> <span data-ttu-id="47a95-157">同意せずにカスタマイズを*削除*することはありませんが、失効したカスタマイズが含まれるデバイスはサービスレベル契約によってバインドされなくなります。</span><span class="sxs-lookup"><span data-stu-id="47a95-157">We won't *remove* a customization without your consent, but any device with a revoked customization will no longer be bound by our service level agreement.</span></span> <span data-ttu-id="47a95-158">送信する通知のタイムラインは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="47a95-158">Here is the timeline of notifications we will send you:</span></span>

- <span data-ttu-id="47a95-159">**最初の通知:** 承認の取り消しについての最初の注意事項として、失効する理由、必要な処置、これらのアクションの期限、および決定を強化するための手順についての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47a95-159">**First notice:** We provide the first notice of our decision to revoke approval, including information about why we’re revoking it, the actions we advise you to take, the deadline for those actions, and steps to follow if you want to appeal the decision.</span></span> <span data-ttu-id="47a95-160">これは、カスタマイズがすべてのデバイスから削除される前に、90日前になります。</span><span class="sxs-lookup"><span data-stu-id="47a95-160">This is 90 days in advance before the customization needs to be removed from all devices.</span></span> 
- <span data-ttu-id="47a95-161">**2 番目の通知 (30 日後):** 最初の通知で提供されるものと同じ情報を含む2番目の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="47a95-161">**Second notice (30 days later):** We provide a second notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="47a95-162">**3 番目の通知 (最初の通知の60日以降):** 最初の通知で提供されるものと同じ情報を含む、3つ目の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="47a95-162">**Third notice (60 days after the first notice):** We provide a third notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="47a95-163">**最終通知 (90 日の期限の1週間前):** 最初の通知で提供されるものと同じ情報を含む4番目の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="47a95-163">**Final notice (1 week before the 90-day deadline):** We provide a fourth notice, including the same information provided in the first notice.</span></span>
- <span data-ttu-id="47a95-164">**最初の通知から90日後:** Microsoft マネージドデスクトップサービスレベルアグリーメントは、無効にされたカスタマイズを持つデバイスに適用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="47a95-164">**90 days after first notice:** Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked customization.</span></span> <span data-ttu-id="47a95-165">いつでも、意思決定をチャレンジして、アップグレード、構成の変更、ソフトウェアの変更など、考慮すべき追加情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="47a95-165">At any time, you can challenge the decision and provide additional information for consideration, including upgrade, configuration changes, or change of software.</span></span> 
