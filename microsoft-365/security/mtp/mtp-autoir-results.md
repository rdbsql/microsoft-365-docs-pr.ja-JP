---
title: 自動調査の詳細と結果を表示する
description: 自動調査の結果と主な検出事項は、調査の実行中および実行後に表示できます。
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 7d3923a3032653f9bfc4a59dc98fe06953975bac
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967920"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="1f1d8-104">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="1f1d8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1f1d8-105">**Applies to:**</span></span>
- <span data-ttu-id="1f1d8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1f1d8-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="1f1d8-107">自動調査が Microsoft Threat Protection で実行された際は、自動調査プロセスの実行中および実行後に調査の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="1f1d8-108">[必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="1f1d8-109">調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![調査の詳細](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="1f1d8-111">調査の詳細ビューを開く</span><span class="sxs-lookup"><span data-stu-id="1f1d8-111">Open the investigation details view</span></span>

<span data-ttu-id="1f1d8-112">調査の詳細ビューを開くには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-112">You can identify the subscription by using one of the following methods:</span></span>
- [<span data-ttu-id="1f1d8-113">アクション センターでアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="1f1d8-114">インシデントの詳細ページから調査を選択する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="1f1d8-115">アクション センターでアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-115">Select an item in the list.</span></span>

<span data-ttu-id="1f1d8-116">アクション センターを使用して、承認が保留中のアクション ([**保留中**] タブで) または既に承認されているアクション ([**履歴**] タブで) を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="1f1d8-117">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-117">Go to https://security.microsoft.com and sign in.</span></span> 

2. <span data-ttu-id="1f1d8-118">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="1f1d8-119">[**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="1f1d8-120">[必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、保留中のアクションを承認 (または拒否) できます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="1f1d8-121">インシデントの詳細ページから調査を開く</span><span class="sxs-lookup"><span data-stu-id="1f1d8-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="1f1d8-122">インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="1f1d8-123">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-123">Go to https://security.microsoft.com and sign in.</span></span> 

2. <span data-ttu-id="1f1d8-124">ナビゲーション ウィンドウで、[**インシデント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-124">In the navigation pane, choose **Custom report**.</span></span> 

3. <span data-ttu-id="1f1d8-125">リスト内のアイテムを選択してインシデントの詳細ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-125">Select an item in the list to open the incident details view.</span></span><br/>![インシデントの詳細](../images/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="1f1d8-127">[**調査**] タブで、一覧から調査を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="1f1d8-128">調査の詳細</span><span class="sxs-lookup"><span data-stu-id="1f1d8-128">Investigation details</span></span>

<span data-ttu-id="1f1d8-129">調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="1f1d8-130">調査の詳細ビューの画像は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-130">The investigation details view resembles the following image:</span></span>

![調査の詳細](../images/mtp-air-investdetails.png)

<span data-ttu-id="1f1d8-132">調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="1f1d8-133">タブ</span><span class="sxs-lookup"><span data-stu-id="1f1d8-133">Tab</span></span>    |<span data-ttu-id="1f1d8-134">説明</span><span class="sxs-lookup"><span data-stu-id="1f1d8-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="1f1d8-135">Investigation graph (調査グラフ)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-135">Investigation graph</span></span>    |<span data-ttu-id="1f1d8-136">調査を視覚的に表します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="1f1d8-137">エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="1f1d8-138">グラフ上のアイテムをクリックすると、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="1f1d8-139">たとえば、[**Threats found (見つかった脅威)**] アイコンをクリックすると、[**Key findings (主な検出事項)**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="1f1d8-140">Alerts (警告)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-140">Alerts</span></span> |<span data-ttu-id="1f1d8-141">調査に関連する警告を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="1f1d8-142">警告は、ユーザーのコンピューター上または Office アプリ内の脅威対策機能、Cloud App Security、その他の Microsoft 365 Threat Protection 機能により出されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="1f1d8-143">Devices (デバイス)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-143">Devices</span></span>|<span data-ttu-id="1f1d8-144">調査に含まれるコンピューターと修復レベルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="1f1d8-145">Key findings (主な検出事項)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-145">Key findings</span></span>   |<span data-ttu-id="1f1d8-146">調査の結果と共に、状態と実行または保留されているアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="1f1d8-147">このタブでは、デバイスおよび ID に対する保留中のアクションを承認できます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="1f1d8-148">Entities (エンティティ)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-148">Entities</span></span>   |<span data-ttu-id="1f1d8-149">調査に関連付けられているユーザー アクティビティ、ファイル、プロセス、サービス、ドライバー、IP アドレス、および永続化の方法と共に、状態と実行されたアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="1f1d8-150">Log (ログ)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-150">Log</span></span>    |<span data-ttu-id="1f1d8-151">調査中に実行されたすべてのステップの詳細および状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="1f1d8-152">Pending actions (保留中のアクション)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-152">Pending actions</span></span>    |<span data-ttu-id="1f1d8-153">続けるには承認を必要とするアイテムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="1f1d8-154">自動調査後の修復アクション</span><span class="sxs-lookup"><span data-stu-id="1f1d8-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="1f1d8-155">自動調査が完了すると、関係するすべての証拠について判定が行われ、修復アクションが特定されます。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="1f1d8-156">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="1f1d8-157">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1f1d8-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="1f1d8-158">判定</span><span class="sxs-lookup"><span data-stu-id="1f1d8-158">Verdict</span></span>    |<span data-ttu-id="1f1d8-159">分野</span><span class="sxs-lookup"><span data-stu-id="1f1d8-159">Area</span></span>   |<span data-ttu-id="1f1d8-160">結果</span><span class="sxs-lookup"><span data-stu-id="1f1d8-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="1f1d8-161">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-161">Malicious</span></span>  |<span data-ttu-id="1f1d8-162">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-162">Devices (endpoints)</span></span>    |<span data-ttu-id="1f1d8-163">修復アクションが自動的に実行されます</span><span class="sxs-lookup"><span data-stu-id="1f1d8-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="1f1d8-164">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-164">Malicious</span></span>  |<span data-ttu-id="1f1d8-165">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="1f1d8-166">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="1f1d8-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="1f1d8-167">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-167">Suspicious</span></span> |<span data-ttu-id="1f1d8-168">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="1f1d8-168">Devices or email content</span></span> |<span data-ttu-id="1f1d8-169">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="1f1d8-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="1f1d8-170">Clean (クリーン)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-170">Clean</span></span>  |<span data-ttu-id="1f1d8-171">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="1f1d8-171">Devices or email content</span></span>   |<span data-ttu-id="1f1d8-172">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="1f1d8-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="1f1d8-173">保留中のアクションをアクション センターで確認する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

## <a name="next-steps"></a><span data-ttu-id="1f1d8-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1f1d8-174">Next steps</span></span>

- [<span data-ttu-id="1f1d8-175">アクション センターのアクセス許可の概要を確認する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-175">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [<span data-ttu-id="1f1d8-176">自動調査と応答に関連するアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="1f1d8-176">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
