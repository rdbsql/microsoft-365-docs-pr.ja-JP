---
title: Microsoft 365 Endpoint データ損失防止 (プレビュー) を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Microsoft 365 エンドポイントのデータ損失防止を設定して、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに実装します。
ms.openlocfilehash: ee276c81a0ebfbf44dd77f6016172f9bf7ed3022
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200007"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="a5d6f-103">Endpoint Data Loss Prevention (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="a5d6f-104">Microsoft Endpoint Data Loss Prevention (Endpoint DLP) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="a5d6f-105">Microsoft のすべての DLP製品 の詳細については、 「[データ損失防止の概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="a5d6f-106">Endpoint DLP の詳細については、「[Endpoint のデータ損失防止について (プレビュー) ](endpoint-dlp-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="a5d6f-107">Microsoft Endpoint DLP は、Windows 10 デバイスを監視し、機密性の高いアイテムが使用および共有されていることを検出します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="a5d6f-108">これにより、適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a5d6f-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="a5d6f-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="a5d6f-110">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="a5d6f-111">Endpoint DLP を開始する前に、「[Microsoft 365サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="a5d6f-112">Endpoint DLP 機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="a5d6f-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a5d6f-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="a5d6f-114">Microsoft 365 A5 (EDU) </span><span class="sxs-lookup"><span data-stu-id="a5d6f-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="a5d6f-115">Microsoft 365 E5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="a5d6f-116">Microsoft 365 A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="a5d6f-117">Microsoft 365 E5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="a5d6f-118">Microsoft 365 A5 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="a5d6f-119">許可</span><span class="sxs-lookup"><span data-stu-id="a5d6f-119">Permissions</span></span>

<span data-ttu-id="a5d6f-120">デバイス管理を有効にするには、使用するアカウントが次のいずれかの役割のメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="a5d6f-121">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-121">Global admin</span></span>
- <span data-ttu-id="a5d6f-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-122">Security admin</span></span>
- <span data-ttu-id="a5d6f-123">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-123">Compliance admin</span></span>

<span data-ttu-id="a5d6f-124">カスタムアカウントを使用してデバイス管理設定を表示する場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="a5d6f-125">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-125">Global admin</span></span>
- <span data-ttu-id="a5d6f-126">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-126">Compliance admin</span></span>
- <span data-ttu-id="a5d6f-127">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-127">Compliance data admin</span></span>
- <span data-ttu-id="a5d6f-128">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="a5d6f-128">Global reader</span></span>

<span data-ttu-id="a5d6f-129">カスタムアカウントを使用してオンボーディング/オフボーディングページにアクセスする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="a5d6f-130">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-130">Global admin</span></span>
- <span data-ttu-id="a5d6f-131">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-131">Compliance admin</span></span>

<span data-ttu-id="a5d6f-132">カスタムアカウントを使用してデバイスの監視をオン/オフにする場合は、次のいずれかの役割でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="a5d6f-133">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-133">Global admin</span></span>
- <span data-ttu-id="a5d6f-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-134">Compliance admin</span></span>

<span data-ttu-id="a5d6f-135">Endpoint DLP からのデータは、[Activity エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="a5d6f-136">Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="a5d6f-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-137">Global admin</span></span>
- <span data-ttu-id="a5d6f-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-138">Compliance admin</span></span>
- <span data-ttu-id="a5d6f-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-139">Security admin</span></span>
- <span data-ttu-id="a5d6f-140">コンプライアンスデータ管理者</span><span class="sxs-lookup"><span data-stu-id="a5d6f-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="a5d6f-141">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-141">Prepare your endpoints</span></span>

<span data-ttu-id="a5d6f-142">これらの要件を満たすために、Endpoint DLP の導入を計画している Windows 10 デバイスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="a5d6f-143">Windows 10 ビルド1809 以降を実行していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-143">Must be running Windows 10 build 1809 or up.</span></span>
2. <span data-ttu-id="a5d6f-144">すべてのデバイスは[Azure Active Directory (AAD) に参加していなければなりません](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join).</span></span>
3. <span data-ttu-id="a5d6f-145">エンドポイントデバイスに Microsoft Chromium Edge ブラウザをインストールして、クラウドへのアップロードアクティビティのポリシーアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the the upload to cloud activity.</span></span> <span data-ttu-id="a5d6f-146">「[Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="a5d6f-147">デバイス管理へのデバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="a5d6f-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="a5d6f-148">デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="a5d6f-149">これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="a5d6f-150">まだオンボーディングされていないデバイスをオンボーディングする場合は、適切なスクリプトをダウンロードして、それらのデバイスに導入します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="a5d6f-151">[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="a5d6f-152">すでに[Microsoft Defender Advanced Threat Protection (MDATP) ](https://docs.microsoft.com/windows/security/threat-protection/) にオンボーディングされているデバイスがある場合、それらはすでに管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-152">If you already have devices onboarded into [Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="a5d6f-153">「[MDATPにオンボーディングされたデバイス」の手順](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp)に従います。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-153">Follow the [With devices onboarded into MDATP procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="a5d6f-154">オンボーディングデバイス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-154">Onboarding devices</span></span>

<span data-ttu-id="a5d6f-155">この導入シナリオでは、まだオンボーディングされていないデバイスをオンボードし、Windows 10 デバイスで意図しない共有から機密アイテムを監視および保護します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="a5d6f-156">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="a5d6f-157">コンプライアンスセンターの設定ページを開き、[**オンボードデバイス**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

> [!NOTE]
> <span data-ttu-id="a5d6f-159">通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="a5d6f-160">[**デバイス管理**]を選択して、[**デバイス**]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="a5d6f-161">デバイスをオンボードするまで、リストは空になります。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="a5d6f-162">オンボーディングプロセスを開始するには、[**オンボーディング**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="a5d6f-163">これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、**パッケージをダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

![導入方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)
1. <span data-ttu-id="a5d6f-165">「[Windows 10 マシンのオンボーディングツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="a5d6f-166">このリンクをクリックしますと、手順 5 で選択した導入パッケージと一致するMDATPプロシージャにアクセスするランディングページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-166">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="a5d6f-167">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="a5d6f-168">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="a5d6f-169">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="a5d6f-170">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="a5d6f-171">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="a5d6f-172">完了後、エンドポイントがオンボードされ、デバイスリストに表示され、監査アクティビティログのActivity エクスプローラーへの報告も開始されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="a5d6f-173">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-173">This experience is under license enforcement.</span></span> <span data-ttu-id="a5d6f-174">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-mdatp"></a><span data-ttu-id="a5d6f-175">MDATP にオンボーディングされたデバイス</span><span class="sxs-lookup"><span data-stu-id="a5d6f-175">With devices onboarded into MDATP</span></span>

<span data-ttu-id="a5d6f-176">このシナリオでは、MDATP はすでに導入されており、レポートするエンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-176">In this scenario, MDATP is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="a5d6f-177">これらすべてのエンドポイントが管理対象デバイスのリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="a5d6f-178">新しいデバイスを引き続き Endpoint DLP にオンボーディングして、[オンボーディングデバイスの手順](endpoint-dlp-getting-started.md#onboarding-devices)を使用してカバレッジを拡大します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="a5d6f-179">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="a5d6f-180">コンプライアンスセンターの設定ページを開き、[**デバイスの監視を有効にする**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="a5d6f-181">[**デバイス管理**]を選択して、[**デバイス**]リストを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="a5d6f-182">すでに MDATP にレポートしているデバイスのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-182">You should see the list of devices that are already reporting in to MDATP.</span></span> <span data-ttu-id="a5d6f-183">![デバイス管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="a5d6f-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="a5d6f-184">追加のデバイスをオンボードする必要がある場合は、[**オンボーディング**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="a5d6f-185">これらの追加デバイスに導入する方法を[**導入方法**]リストから選択し、[**パッケージをダウンロード**]します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="a5d6f-186">「[Windows 10 マシンのオンボーディングツールと方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)」の適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="a5d6f-187">このリンクをクリックしますと、手順 5 で選択した導入パッケージと一致するMDATPプロシージャにアクセスするランディングページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-187">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="a5d6f-188">グループポリシーを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="a5d6f-189">Microsoft Endpoint Configuration Manager を使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="a5d6f-190">モバイルデバイス管理ツールを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="a5d6f-191">ローカルスクリプトを使用した Windows 10 マシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="a5d6f-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="a5d6f-192">非永続的な仮想デスクトップインフラストラクチャ (VDI) マシンをオンボーディングします。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="a5d6f-193">完了後、エンドポイントがオンボードされ、[**デバイス**]テーブルの下に表示され、**Activity エクスプローラー**に監査ログのレポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="a5d6f-194">これは、ライセンス執行時でのエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-194">This experience is under license enforcement.</span></span> <span data-ttu-id="a5d6f-195">必要なライセンスがないと、データは表示されず、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="a5d6f-196">Activity エクスプローラーでのEndpoint DLPデータの表示</span><span class="sxs-lookup"><span data-stu-id="a5d6f-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="a5d6f-197">Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="a5d6f-198">エンドポイントデバイスのすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![エンドポイントデバイスの Activity エクスプローラーフィルター](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="a5d6f-200">次の手順</span><span class="sxs-lookup"><span data-stu-id="a5d6f-200">Next steps</span></span>
<span data-ttu-id="a5d6f-201">デバイスがオンボードされ、Activity Explorer でアクティビティデータを表示できるようになりました。次の手順に進み、機密アイテムを保護する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

1) [<span data-ttu-id="a5d6f-202">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="a5d6f-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="a5d6f-203">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="a5d6f-203">See also</span></span>

- [<span data-ttu-id="a5d6f-204">エンドポイントのデータ損失防止について学ぶ (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="a5d6f-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="a5d6f-205">エンドポイントのデータ損失防止の使用 (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="a5d6f-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="a5d6f-206">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="a5d6f-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="a5d6f-207">DLPポリシーを作成、テスト、調整する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a5d6f-208">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="a5d6f-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a5d6f-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) </span><span class="sxs-lookup"><span data-stu-id="a5d6f-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="a5d6f-210">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="a5d6f-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="a5d6f-211">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="a5d6f-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="a5d6f-212">Azure Active Directory (AAD) が参加しました</span><span class="sxs-lookup"><span data-stu-id="a5d6f-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="a5d6f-213">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="a5d6f-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)