---
title: リモート ワーカーを支援する
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/27/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 従業員がいつでもどこからでもリモートで作業できるようにするインフラストラクチャとセキュリティを構成します。
ms.openlocfilehash: 2ff9923d0a301ba6ced720a9934ceb62bdff37c4
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306561"
---
# <a name="empower-remote-workers"></a><span data-ttu-id="c9f7b-103">リモート ワーカーを支援する</span><span class="sxs-lookup"><span data-stu-id="c9f7b-103">Empower remote workers</span></span>

<span data-ttu-id="c9f7b-104">*このシナリオは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*</span><span class="sxs-lookup"><span data-stu-id="c9f7b-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c9f7b-105">従業員がオフィスからシームレスかつ安全に離れて作業できるようにすることは、多くの組織にとって、オフィス スペースの節約、転勤を望まない従業員の採用および維持、通勤時間の短縮など、従業員の生産性の向上と仕事以外でストレスを軽減するために重要です。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-105">Allowing employees to work away from the office seamlessly and securely is important for many organizations to save on office space, hire and retain employees who are unwilling to relocate, and reduce employee commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="c9f7b-106">リモート作業 (テレワーキングとも呼ばれる) は、次のような範囲に及ぶことがあります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-106">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="c9f7b-107">会議やクライアント会議のために時々オフィスを離れる従業員。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-107">Employees that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="c9f7b-108">リモートでフルタイムで働く一部の従業員。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-108">Some employees that work remotely full-time.</span></span>
- <span data-ttu-id="c9f7b-109">オフィスがなく、すべての従業員が離れている完全なリモートの組織。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-109">A fully remote organization in which tHere's no office and all employees are remote.</span></span>

<span data-ttu-id="c9f7b-110">リモート ワーカーをサポートするために、Microsoft 365 Enterprise の機能を組み合わせることで、次のような高度な共同作業が可能になります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-110">To support remote workers, a combination of features in Microsoft 365 Enterprise enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="c9f7b-111">オンライン会議およびチャット セッション。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-111">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="c9f7b-112">グローバルなアクセシビリティとリアルタイムのコラボレーションを実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-112">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="c9f7b-113">作業を分割して完了するための共有タスクとワークフロー。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-113">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="c9f7b-114">セキュリティを強化するために、Microsoft 365 Enterprise には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-114">For strong security, Microsoft 365 Enterprise includes:</span></span>

- <span data-ttu-id="c9f7b-115">認証要件の適用、高リスクのサインインの検出と応答、選択したアプリと非準拠デバイスのブロック。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-115">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="c9f7b-116">クラウド内の暗号化された接続とデジタル資産。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-116">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="c9f7b-117">ファイルに対して誰が何を実行できるかを定義する権限。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-117">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="c9f7b-118">高度に規制されたデータの漏洩を防ぐデータ損失防止 (DLP)。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-118">Data loss prevention (DLP) to prevent leakage of highly regulated data.</span></span>

<span data-ttu-id="c9f7b-119">これらのリモート ワーカーの基準を満たすには、次の Microsoft 365 Enterprise 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-119">To meet these criteria for remote workers, use the following Microsoft 365 Enterprise features:</span></span>

- <span data-ttu-id="c9f7b-120">ユーザー ID とサインイン セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c9f7b-120">User identity and sign-in security</span></span>
  - <span data-ttu-id="c9f7b-121">多要素認証 (MFA) を使用する Azure Active Directory (Azure AD) ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="c9f7b-121">Azure Active Directory (Azure AD) user accounts with multi-factor authentication (MFA)</span></span>
  - <span data-ttu-id="c9f7b-122">危険なサインインに MFA を要求する条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="c9f7b-122">Conditional Access policies to require MFA for risky sign-ins</span></span>
- <span data-ttu-id="c9f7b-123">コラボレーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c9f7b-123">Collaboration platforms</span></span>
  - <span data-ttu-id="c9f7b-124">リモート ワーカーがオンライン ビデオベースの会議にスケジュールおよび参加し、同時に同じドキュメントで作業できるようにする Microsoft Teams、SharePoint、および OneDrive</span><span class="sxs-lookup"><span data-stu-id="c9f7b-124">Microsoft Teams, SharePoint, and OneDrive, with which remote workers can schedule and attend online video-based meetings and work on the same documents at the same time</span></span>
- <span data-ttu-id="c9f7b-125">リソースへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="c9f7b-125">Secure access to resources</span></span>
  - <span data-ttu-id="c9f7b-126">Teams、SharePoint サイト、および OneDrive のグループとアクセス許可により、認証および許可されたユーザーのみがアクセス可能</span><span class="sxs-lookup"><span data-stu-id="c9f7b-126">Groups and permissions for Teams, SharePoint sites, and OneDrive so that only authenticated and permitted users have access</span></span>
- <span data-ttu-id="c9f7b-127">漏洩ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="c9f7b-127">Protection for leaked files</span></span>
  - <span data-ttu-id="c9f7b-128">Office 365 DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="c9f7b-128">Step 2: Office 365 labels and DLP policies</span></span>
  - <span data-ttu-id="c9f7b-129">暗号化のための機密ラベルとファイルとともに移動するアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c9f7b-129">Sensitivity labels for encryption and permissions that travel with files</span></span>
- <span data-ttu-id="c9f7b-130">Microsoft Intune によるデバイス管理とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c9f7b-130">Device management with Microsoft Intune</span></span>
  - <span data-ttu-id="c9f7b-131">管理対象デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="c9f7b-131">Enrollment for managed devices</span></span>
  - <span data-ttu-id="c9f7b-132">個人用デバイスのアプリ設定</span><span class="sxs-lookup"><span data-stu-id="c9f7b-132">App settings for personal devices</span></span>
  - <span data-ttu-id="c9f7b-133">デバイスとアプリのポリシー</span><span class="sxs-lookup"><span data-stu-id="c9f7b-133">Device and app policies</span></span>
- <span data-ttu-id="c9f7b-134">デバイス用の生産性アプリ</span><span class="sxs-lookup"><span data-stu-id="c9f7b-134">Productivity apps for devices</span></span>
  - <span data-ttu-id="c9f7b-135">Teams、SharePoint、および OneDrive とのコラボレーション エクスペリエンスのための Office 365 ProPlus アプリ</span><span class="sxs-lookup"><span data-stu-id="c9f7b-135">Office 365 ProPlus apps for collaborative experiences with Teams, SharePoint, and OneDrive</span></span> 
- <span data-ttu-id="c9f7b-136">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9f7b-136">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="c9f7b-137">サイバー攻撃から保護し、データ漏洩を防止する包括的なセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="c9f7b-137">Comprehensive security features to protect against cyberattacks and prevent data leakage</span></span>
- <span data-ttu-id="c9f7b-138">オンプレミス アプリへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c9f7b-138">Access to on-premises apps</span></span>
  - <span data-ttu-id="c9f7b-139">ハイブリッド ID を持つ組織は、仮想プライベート ネットワーク (VPN) 接続の代わりに Azure AD アプリケーション プロキシを使用可能</span><span class="sxs-lookup"><span data-stu-id="c9f7b-139">Organizations that have hybrid identity can use Azure AD Application Proxy instead of virtual private network (VPN) connections</span></span>

<span data-ttu-id="c9f7b-140">次のフェーズでは、リモート アクセスを可能にする Microsoft 365 Enterprise の機能を展開し、リモート ワーカーの採用を推進する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-140">The following phases step you through deploying the feature of Microsoft 365 Enterprise for remote access and driving adoption for remote workers.</span></span> <span data-ttu-id="c9f7b-141">これらのフェーズの要素がすでに展開されている場合は、次の要素に進む前に、それらの要素が上記の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-141">If you have already deployed elements of these phases, ensure that they meet the stated requirements before moving on to the next element.</span></span>

## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a><span data-ttu-id="c9f7b-142">フェーズ 1: リモート ワーカーに Microsoft 365 の機能を展開する</span><span class="sxs-lookup"><span data-stu-id="c9f7b-142">Phase 1: Deploy Microsoft 365 features and capabilities for remote workers</span></span>

<span data-ttu-id="c9f7b-143">このシナリオに必要な機能の幅と数が多いため、「[Microsoft 365 Enterprise の展開ガイド](deploy-microsoft-365-enterprise.md)」の基盤インフラストラクチャとワークロード セクションの必須要素を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-143">Because of the breadth and number of features and capabilities required for this scenario, we’ll step you through the required elements of the foundation infrastructure and workloads sections of the [Microsoft 365 Enterprise Deployment Guide](deploy-microsoft-365-enterprise.md).</span></span>

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a><span data-ttu-id="c9f7b-144">手順 1: リモート ワーカーの基盤インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="c9f7b-144">Step 1: Foundation infrastructure requirements for remote workers</span></span>

<span data-ttu-id="c9f7b-145">この手順では、[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)のフェーズにアクセスし、リモート ワーカーを有効にするために必要な要素を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-145">In this step, we’ll visit the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) and list the required elements to enable remote workers.</span></span>

<span data-ttu-id="c9f7b-146">[フェーズ 2: ID](identity-infrastructure.md) の場合、ユーザー ID およびサインイン セキュリティ用に次を展開します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-146">For [Phase 2: Identity](identity-infrastructure.md), deploy the following for user identity and sign-in security:</span></span>

- <span data-ttu-id="c9f7b-147">ハイブリッド ID の場合、オンプレミスの Active Directory ドメイン サービス (AD DS) から同期されたユーザー アカウントとグループ。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-147">For hybrid identity, user accounts and groups synchronized from on-premises Active Directory Domain Services (AD DS).</span></span>
- <span data-ttu-id="c9f7b-148">権限を割り当てる場合、適切なメンバーと同期または Azure AD グループ。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-148">For assigning permissions, synchronized or Azure AD groups with the appropriate members.</span></span>
- <span data-ttu-id="c9f7b-149">MFA の要求などの認証設定。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-149">Authentication settings, such as requiring MFA.</span></span>
- <span data-ttu-id="c9f7b-150">危険なサインインに MFA を要求する条件付きアクセス ポリシーおよび先進認証をサポートしないクライアントのブロック。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-150">Conditional Access policies to require MFA for risky sign-ins and block clients that don’t support modern authentication.</span></span>

<span data-ttu-id="c9f7b-151">次に、ID 要素を強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-151">Here's the resulting configuration with the identity elements highlighted.</span></span>

![リモート ワーカーの ID 要素](./media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
<span data-ttu-id="c9f7b-153">[フェーズ 3: Windows 10 Enterprise](windows10-infrastructure.md) の場合、次を展開します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-153">[Phase 3: Windows 10 Enterprise](windows10-infrastructure.md)</span></span>

- <span data-ttu-id="c9f7b-154">Windows 10 Enterprise で新しいデバイスを展開し、Windows 7 または Windows 8.1 デバイスを Windows 10 Enterprise にアップグレードするためのインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="c9f7b-154">The infrastructure to deploy new devices with Windows 10 Enterprise and to upgrade of your Windows 7 or Windows 8.1 devices to Windows 10 Enterprise</span></span>
- <span data-ttu-id="c9f7b-155">ID、脅威、および情報保護のための包括的なセキュリティ機能の有効化</span><span class="sxs-lookup"><span data-stu-id="c9f7b-155">Enabling comprehensive security features for identity, threat, and information protection</span></span>

<span data-ttu-id="c9f7b-156">次に、Windows 10 Enterprise デバイスの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-156">Here's the resulting configuration with Windows 10 Enterprise devices.</span></span>

![リモート ワーカー向けの Windows 10 Enterprise の要素](./media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
<span data-ttu-id="c9f7b-158">[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md) の場合、インフラストラクチャを展開して Office 365 ProPlus をインストールするか、Office 2010 や Office 2013 などの現在インストールされている Office スイートを組織のデバイス上の Office 365 ProPlus にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-158">For [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md), deploy the infrastructure to install Office 365 ProPlus or upgrade your currently installed Office suite, such as Office 2010 or Office 2013, to Office 365 ProPlus on your organization devices.</span></span> <span data-ttu-id="c9f7b-159">これにより、ユーザーがセキュリティと共同作業エクスペリエンスを最大限活用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-159">This will give your users the best security and collaborative experiences.</span></span>

<span data-ttu-id="c9f7b-160">次に、Office 365 ProPlus がデバイスにインストールされた場合の構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-160">Here's the resulting configuration with Office 365 ProPlus installed on devices.</span></span>

![リモート ワーカー向けの Office 365 ProPlus 要素](./media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
<span data-ttu-id="c9f7b-162">[フェーズ 5: モバイル デバイス管理](mobility-infrastructure.md)の場合、次の目的で Intune デバイスとアプリの管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-162">For [Phase 5: Mobile device management](mobility-infrastructure.md), deploy Intune device and app management for:</span></span>

- <span data-ttu-id="c9f7b-163">組織が定義した機能とセキュリティ設定を受信するように、Windows 10 Enterprise、iOS、macOS、Android、および Android Enterprise デバイスを登録。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-163">Enrollment of your Windows 10 Enterprise, iOS, macOS, Android, and Android Enterprise devices so they receive features and security settings defined by your organization.</span></span>
- <span data-ttu-id="c9f7b-164">従業員が所有する個人用デバイスであっても、セキュリティを強化するため、アプリを許可またはブロックするアプリの設定。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-164">App settings for extra security and to allow or block apps, even on employee-owned personal devices.</span></span>
- <span data-ttu-id="c9f7b-165">非準拠デバイスの接続を防ぐための条件付きアクセスを備えたコンプライアンス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-165">Compliance policies with Conditional Access to prevent non-compliant devices from connecting.</span></span>

<span data-ttu-id="c9f7b-166">次に、Intune の登録済みデバイスとポリシーを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-166">Here's the resulting configuration with Intune enrolled devices and policies highlighted.</span></span>

![リモート ワーカー向けのモバイル デバイス管理の要素](./media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
<span data-ttu-id="c9f7b-168">[フェーズ 6: 情報保護](infoprotect-infrastructure.md)の場合、デジタル資産の保護を次の機能により設計および構成します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-168">For [Phase 6: Information protection](infoprotect-infrastructure.md), design and configure protection for your digital assets with:</span></span>

- <span data-ttu-id="c9f7b-169">Office 365 DLP ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-169">Step 2: Office 365 labels and DLP policies</span></span>
- <span data-ttu-id="c9f7b-170">ファイルと共に移動する暗号化およびアクセス許可のための Office 365 の機密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-170">Office 365 sensitivity labels for encryption and permissions that travel with files.</span></span>

<span data-ttu-id="c9f7b-171">次に、DLP ポリシーと機密度ラベルを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-171">Here's the resulting configuration with DLP policies and sensitivity labels highlighted.</span></span>

![リモート ワーカー向けの情報保護の要素](./media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
<span data-ttu-id="c9f7b-173">オンプレミス アプリにアクセスするには、ハイブリッド ID 環境を必要とする [Azure AD アプリケーション プロキシ](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-173">For access to on-premises apps, you can use [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), which requires a hybrid identity environment.</span></span>

<span data-ttu-id="c9f7b-174">次に、アプリケーション プロキシ コンポーネントを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-174">Here's the resulting configuration with the application proxy components highlighted.</span></span>

![リモート ワーカーのアプリケーション プロキシの要素](./media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a><span data-ttu-id="c9f7b-176">手順 2: リモート ワーカーのワークロード</span><span class="sxs-lookup"><span data-stu-id="c9f7b-176">Step 2: Workloads for remote workers</span></span>

<span data-ttu-id="c9f7b-177">[Exchange Online](exchangeonline-workload.md) の場合、Exchange Online メールボックスを各ユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-177">For [Exchange Online](exchangeonline-workload.md), deploy Exchange Online mailboxes to each of your users.</span></span>

<span data-ttu-id="c9f7b-178">[Teams](teams-workload.md) の場合、Teams をユーザーとグループに展開します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-178">For [Teams](teams-workload.md), deploy Teams to your users and groups.</span></span>

<span data-ttu-id="c9f7b-179">[SharePoint および OneDrive](sharepoint-online-onedrive-workload.md) の場合、SharePoint チームまたはコミュニケーション サイトと OneDrive フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-179">For [SharePoint and OneDrive](sharepoint-online-onedrive-workload.md), deploy SharePoint team or communication sites and OneDrive folders.</span></span>

<span data-ttu-id="c9f7b-180">次に、ワークロードを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-180">Here's the resulting configuration with the workloads highlighted.</span></span>

![リモート ワーカー向けの Microsoft 365 ワークロード](./media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a><span data-ttu-id="c9f7b-182">展開結果</span><span class="sxs-lookup"><span data-stu-id="c9f7b-182">Deployment results</span></span>

<span data-ttu-id="c9f7b-183">基盤インフラストラクチャとワークロードを展開し、Windows 10 Enterprise および Office 365 ProPlus を展開した後、リモート ワーカーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-183">After deploying the foundation infrastructure and workloads and rolling out Windows 10 Enterprise and Office 365 ProPlus, remote workers:</span></span>

- <span data-ttu-id="c9f7b-184">強力な認証および ID 保護の対象になります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-184">Are subject to strong authentication and identity protection.</span></span>
- <span data-ttu-id="c9f7b-185">Windows デバイスで最新かつ最も安全なバージョンの Windows を使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-185">Have the latest and most secure version of Windows on their Windows devices.</span></span>
- <span data-ttu-id="c9f7b-186">デバイスで最新かつ最も生産的なバージョンの Office スイートを使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-186">Have the latest and most productive version of the Office suite on their devices.</span></span>
- <span data-ttu-id="c9f7b-187">アプリ管理およびデバイス コンプライアンス ポリシーの対象になります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-187">Are subject to app management and device compliance policies.</span></span>
- <span data-ttu-id="c9f7b-188">DLP ポリシーおよび制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-188">Are subject to DLP policies and restrictions.</span></span>
- <span data-ttu-id="c9f7b-189">ファイルおよびメールとともに送信される暗号化およびアクセス許可に機密度ラベルを割り当てられるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-189">Can assign sensitivity labels for encryption and permissions that travel with files and email.</span></span>
- <span data-ttu-id="c9f7b-190">VPN 接続なしでオンプレミスのアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-190">Can access on-premises apps without a VPN connection.</span></span>
- <span data-ttu-id="c9f7b-191">Teams 内のチャット、会議、ファイル、SharePoint および OneDrive 内のファイルを使用して、自分の作業を実行し、同僚とのリアルタイム コラボレーションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-191">Can perform their own work and participate in real-time collaboration with co-workers with chats, meetings, and files in Teams and files in SharePoint and OneDrive.</span></span>

<span data-ttu-id="c9f7b-192">オフライン (インターネットに接続されていない) の場合、リモート ワーカーはファイルのローカル コピーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-192">When offline (not connected to the Internet), your remote workers can change local copies of files.</span></span> <span data-ttu-id="c9f7b-193">インターネットに再接続すると、OneDrive はローカル コピーを Microsoft 365 サブスクリプションに保存されているファイルと同期します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-193">When they reconnect to the Internet, OneDrive synchronizes local copies with the files stored in your Microsoft 365 subscription.</span></span> 

<span data-ttu-id="c9f7b-194">次に、ハイブリッド ID を使用する場合の、組織のリモート ワーカーの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-194">Here's the resulting configuration for remote workers of your organization if you use hybrid identity.</span></span>

![ハイブリッド ID を持つ組織の最終の構成](./media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
<span data-ttu-id="c9f7b-196">次に、クラウド専用 ID を使用する場合の、組織のリモート ワーカーの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-196">Here's the resulting configuration for remote workers your organization if you use cloud-only identity.</span></span>

![クラウド専用 ID を持つ組織の最終の構成](./media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a><span data-ttu-id="c9f7b-198">フェーズ 2: リモート ワーカーに導入を促す</span><span class="sxs-lookup"><span data-stu-id="c9f7b-198">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="c9f7b-199">基盤インフラストラクチャとワークロードが整ったので、これらの機能の継続的な使用をリモート ワーカーに促し、いつでもどこでも生産的になるようにします。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-199">Now that the foundation infrastructure and workloads are in place, it’s time to drive the ongoing usage of these capabilities to your remote workers so they can be productive anywhere and at any time.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="c9f7b-200">手順 1: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="c9f7b-200">Step 1: Train your users</span></span>

<span data-ttu-id="c9f7b-201">リモート ワーカーを以下の内容についてトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-201">Train your remote workers on:</span></span>

- <span data-ttu-id="c9f7b-202">MFA 登録を含む適切なサインインの手順、およびリスクが検出されたときにサインインにチャレンジする方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-202">Proper sign-in procedures, including MFA registration, and how sign ins can be challenged when risk is detected.</span></span>
- <span data-ttu-id="c9f7b-203">デバイスの使用と、ポリシーを使用して非準拠デバイスのアクセスをブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-203">The use of devices and how policies can be used to block access for non-compliant devices.</span></span>
- <span data-ttu-id="c9f7b-204">許可されたアプリの使用と、Intune アプリ ポリシーを使用してアプリをブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-204">The use of allowed apps and how Intune app polices can be used to block apps.</span></span>
- <span data-ttu-id="c9f7b-205">Windows 10 Enterprise のセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-205">Deploy Windows 10 Enterprise security features</span></span>
- <span data-ttu-id="c9f7b-206">電子メールと予定表に Outlook を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-206">How to use Outlook for email and calendaring.</span></span>
- <span data-ttu-id="c9f7b-207">[Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) を使用してチャット、ビデオベースの会議、ドキュメント共有、およびスレッド形式の会話を行う方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-207">How to use [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="c9f7b-208">SharePoint チームまたはコミュニケーション サイトと OneDrive フォルダーを使用して、ユーザーのライブラリおよびグループに属するファイルを閲覧する方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-208">How to use SharePoint team or communication sites and OneDrive folders to browse files in a user's library and those belonging to a group.</span></span>
- <span data-ttu-id="c9f7b-209">ファイルのローカル バージョンとオンライン バージョンの両方で、機密データまたは厳しく規制されたデータを含むファイルに機密度ラベルを使用および適用する方法。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-209">How to use and apply sensitivity labels for files containing sensitive or highly regulated data, for both local and online versions of files.</span></span>

<span data-ttu-id="c9f7b-210">このトレーニングには、生徒が上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-210">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a><span data-ttu-id="c9f7b-211">手順 2: 使用状況を定期的にレビューし、作業者のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="c9f7b-211">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="c9f7b-212">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-212">In the weeks after training:</span></span>

- <span data-ttu-id="c9f7b-213">リモート ワーカーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-213">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="c9f7b-214">チーム、SharePoint サイト、および OneDrive フォルダーの使用状況を分析し、予想される使用状況と比較します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-214">Analyze usage for teams, SharePoint sites, and OneDrive folders and compare it with usage expectations.</span></span>
- <span data-ttu-id="c9f7b-215">機密または厳しく規制されたファイルが適切な機密度ラベルで適切にラベル付けされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-215">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="c9f7b-216">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-216">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="c9f7b-217">ユーザーによる採用の結果</span><span class="sxs-lookup"><span data-stu-id="c9f7b-217">User adoption results</span></span>

<span data-ttu-id="c9f7b-218">リモート ワーカーは、Windows 10 Enterprise または他のデバイスと Office 365 ProPlus を使用して、安全な環境で共有 Microsoft 365 Enterprise クラウド サービスとリソースにアクセスして作業し、リアルタイムで会議、作成、コラボレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c9f7b-218">Your remote workers can use their Windows 10 Enterprise or other devices and Office 365 ProPlus to access and work on shared Microsoft 365 Enterprise cloud services and resources in a secure environment, and they’re meeting, creating, and collaborating in real time.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9f7b-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9f7b-219">See also</span></span>

[<span data-ttu-id="c9f7b-220">ワークロードとシナリオ</span><span class="sxs-lookup"><span data-stu-id="c9f7b-220">Workloads and scenarios</span></span>](deploy-workloads.md)

[<span data-ttu-id="c9f7b-221">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="c9f7b-221">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
