---
title: Microsoft 365 とのセキュリティで保護されたコラボレーションをセットアップする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 機密に基づいてデータを保護するために Teams をセットアップする方法について説明します。
ms.openlocfilehash: 77493398b11109a51c4e60599561fd8cd4f6c3ac
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002955"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="05962-103">Microsoft 365 とのセキュリティで保護されたコラボレーションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="05962-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="05962-104">情報を適切な人と簡単に共有できるようにする一方で、過剰な共有が組織の成功にとって重要であることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="05962-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="05962-105">これには、機密データをアクセスする必要があるユーザーに対してのみ安全に共有できることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="05962-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="05962-106">プロジェクトによっては、機密データを組織外のユーザーと共有する場合があります。</span><span class="sxs-lookup"><span data-stu-id="05962-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

<span data-ttu-id="05962-107">このソリューションガイダンスには、次のような2つのコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="05962-107">This solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="05962-108">各プロジェクトの適切なレベルの保護を使用して Microsoft Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="05962-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="05962-109">プロジェクトごとに適切なセキュリティ設定を使用して外部共有を構成する</span><span class="sxs-lookup"><span data-stu-id="05962-109">Configure external sharing with appropriate security settings for each project</span></span>

![適切な保護を使用して Teams を展開し、適切なセキュリティ設定を使用して外部共有を構成する](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="05962-111">多目的で使いやすいコラボレーションツールを使用できない場合、ユーザーはメールでドキュメントを送信することによって共同作業を行うことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="05962-111">If versatile and easy-to-use collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="05962-112">これは、単調でエラーが発生しやすいコラボレーションの方法であり、情報が不適切に共有されるリスクを高めることができます。</span><span class="sxs-lookup"><span data-stu-id="05962-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="05962-113">ユーザーが情報を共有することが困難すぎる場合は、その情報が管理されていないコンシューマー製品の使用に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="05962-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="05962-114">これにより、さらに大きなリスクが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05962-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="05962-115">Microsoft 365 では、次のようなさまざまな構成を使用して Teams を展開できます。</span><span class="sxs-lookup"><span data-stu-id="05962-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="05962-116">知的所有権を保護する</span><span class="sxs-lookup"><span data-stu-id="05962-116">Protect your intellectual property</span></span>
- <span data-ttu-id="05962-117">簡単にコラボレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="05962-117">Enable easy collaboration</span></span>
- <span data-ttu-id="05962-118">セキュリティと操作性のバランスを確立して、ユーザーの満足度を上げ、シャドウを考慮するリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="05962-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="05962-119">ほとんどの組織にはさまざまな情報があり、機密度が異なり、情報が適切に共有されていない場合にはさまざまなビジネスへの影響があります。</span><span class="sxs-lookup"><span data-stu-id="05962-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="05962-120">特定の情報の機密性に応じて、次のような共有を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="05962-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="05962-121">すべてのユーザー (認証されていない)</span><span class="sxs-lookup"><span data-stu-id="05962-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="05962-122">組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="05962-122">People inside the organization</span></span>
- <span data-ttu-id="05962-123">組織内の特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="05962-123">Specific people inside the organization</span></span>
- <span data-ttu-id="05962-124">組織の内部および外部の特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="05962-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="05962-125">マーケティングパンフレットなどの情報は、組織外での共有を目的としています。</span><span class="sxs-lookup"><span data-stu-id="05962-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="05962-126">カフェテリアのメニューなどの情報は、外部共有を目的としたものではありませんが、外部で共有されている場合はビジネスへの影響はありません。</span><span class="sxs-lookup"><span data-stu-id="05962-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="05962-127">これらの種類の情報は、ほとんどまたはまったく保護する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="05962-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="05962-128">開発中の同じマーケティングパンフレットは、組織内でのみ共有することができます。</span><span class="sxs-lookup"><span data-stu-id="05962-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="05962-129">この場合は、Teams の既定の共有設定で十分です。</span><span class="sxs-lookup"><span data-stu-id="05962-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="05962-130">開発中の新しい製品に関する情報は、組織内であっても機密であると見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="05962-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="05962-131">この場合は、より高いレベルの保護が適している場合があります。</span><span class="sxs-lookup"><span data-stu-id="05962-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="05962-132">たとえば、特定のチームのメンバーに対するこの情報へのアクセスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="05962-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="05962-133">プロジェクトによっては、ベンダーやパートナー組織などの組織外のユーザーと共同作業が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="05962-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="05962-134">組織の成功にとって重要な情報、またはセキュリティやコンプライアンスに関する厳しい要件がある場合は、より高いレベルの保護が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="05962-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![低 (リリースパンフレット) から高 (機密性の高いビジネスデータ) までのリスクスケール](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="05962-136">上記のすべてのシナリオでは、Microsoft Teams の teams を使用して、情報を格納、共有、および共同作業することができます。</span><span class="sxs-lookup"><span data-stu-id="05962-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

## <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="05962-137">すべての種類のデータに Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="05962-137">Using Teams for all kinds of data</span></span>

<span data-ttu-id="05962-138">さまざまな反応を持つ情報へのアクセスを管理するために、 [Teams に対して3つの異なる保護レベル](configure-teams-three-tiers-protection.md)を開発しました。</span><span class="sxs-lookup"><span data-stu-id="05962-138">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="05962-139">これらの層のいずれかをカスタマイズして、ニーズやビジネスに適したものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="05962-139">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams の論理的なアーキテクチャ ポスターのサムネイル](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="05962-141">次の表に示すよう*に、これら*の*階層によって、過度\*\*な共有*や情報漏洩を防止するための保護が徐々に増加します。</span><span class="sxs-lookup"><span data-stu-id="05962-141">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

||<span data-ttu-id="05962-142">**ベースライン層**</span><span class="sxs-lookup"><span data-stu-id="05962-142">**Baseline tier**</span></span>|<span data-ttu-id="05962-143">**機密層**</span><span class="sxs-lookup"><span data-stu-id="05962-143">**Sensitive tier**</span></span>|<span data-ttu-id="05962-144">**非常に機密性の高い層**</span><span class="sxs-lookup"><span data-stu-id="05962-144">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="05962-145">パブリックまたはプライベートチーム</span><span class="sxs-lookup"><span data-stu-id="05962-145">Public or private team</span></span>|<span data-ttu-id="05962-146">[Either/リンク/埋め込み]</span><span class="sxs-lookup"><span data-stu-id="05962-146">Either</span></span>|<span data-ttu-id="05962-147">プライベート</span><span class="sxs-lookup"><span data-stu-id="05962-147">Private</span></span>|<span data-ttu-id="05962-148">プライベート</span><span class="sxs-lookup"><span data-stu-id="05962-148">Private</span></span>|
|<span data-ttu-id="05962-149">認証されていない共有</span><span class="sxs-lookup"><span data-stu-id="05962-149">Unauthenticated sharing</span></span>|<span data-ttu-id="05962-150">Blocked</span><span class="sxs-lookup"><span data-stu-id="05962-150">Blocked</span></span>|<span data-ttu-id="05962-151">Blocked</span><span class="sxs-lookup"><span data-stu-id="05962-151">Blocked</span></span>|<span data-ttu-id="05962-152">Blocked</span><span class="sxs-lookup"><span data-stu-id="05962-152">Blocked</span></span>|
|<span data-ttu-id="05962-153">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="05962-153">File sharing</span></span>|<span data-ttu-id="05962-154">可</span><span class="sxs-lookup"><span data-stu-id="05962-154">Allowed</span></span>|<span data-ttu-id="05962-155">可</span><span class="sxs-lookup"><span data-stu-id="05962-155">Allowed</span></span>|<span data-ttu-id="05962-156">チーム所有者のみが共有できます。</span><span class="sxs-lookup"><span data-stu-id="05962-156">Only team owners can share.</span></span>|
|<span data-ttu-id="05962-157">チームメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="05962-157">Team membership</span></span>|<span data-ttu-id="05962-158">すべてのユーザーがパブリックチームに参加できます。</span><span class="sxs-lookup"><span data-stu-id="05962-158">Anyone can join public teams.</span></span><br><span data-ttu-id="05962-159">チーム所有者の承認は、プライベートチームに参加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="05962-159">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="05962-160">参加するには、チーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="05962-160">Team owner approval required to join.</span></span>|<span data-ttu-id="05962-161">参加するには、チーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="05962-161">Team owner approval required to join.</span></span>|
|<span data-ttu-id="05962-162">ドキュメントの暗号化</span><span class="sxs-lookup"><span data-stu-id="05962-162">Document encryption</span></span>|||<span data-ttu-id="05962-163">機密ラベルで使用可能</span><span class="sxs-lookup"><span data-stu-id="05962-163">Available with sensitivity label</span></span>|
|<span data-ttu-id="05962-164">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="05962-164">Guest sharing</span></span>|<span data-ttu-id="05962-165">可</span><span class="sxs-lookup"><span data-stu-id="05962-165">Allowed</span></span>|<span data-ttu-id="05962-166">許可またはブロックできる</span><span class="sxs-lookup"><span data-stu-id="05962-166">Can be allowed or blocked</span></span>|<span data-ttu-id="05962-167">許可またはブロックできる</span><span class="sxs-lookup"><span data-stu-id="05962-167">Can be allowed or blocked</span></span>|
|<span data-ttu-id="05962-168">非管理対象デバイス</span><span class="sxs-lookup"><span data-stu-id="05962-168">Unmanaged devices</span></span>|<span data-ttu-id="05962-169">制限なし</span><span class="sxs-lookup"><span data-stu-id="05962-169">No restriction</span></span>|<span data-ttu-id="05962-170">Web 専用アクセス</span><span class="sxs-lookup"><span data-stu-id="05962-170">Web-only access</span></span>|<span data-ttu-id="05962-171">Blocked</span><span class="sxs-lookup"><span data-stu-id="05962-171">Blocked</span></span>|

<span data-ttu-id="05962-172">これらの層の構成には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="05962-172">Configuring these tiers involves:</span></span>

- <span data-ttu-id="05962-173">Teams でゲストアクセスおよびプライベートチャネルの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="05962-173">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="05962-174">内部およびゲストの共有、アクセスの要求、および共有リンクについて、チームの関連付けられた SharePoint サイトの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="05962-174">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="05962-175">*機密性*の*高い機密*層に対して、チームを分類するための機密ラベルを構成し、管理されていないデバイスからゲストの共有とアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="05962-175">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="05962-176">非常に*機密性の高い*層の場合は、機密ラベルを構成して、適用されるドキュメントを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="05962-176">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="05962-177">ベースライン層から始め、必要に応じて*機密*および*機密性の高い*階層を使用する teams を追加して、組織内の情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="05962-177">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="05962-178">開始するには、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05962-178">See these resources to get started:</span></span>

- [<span data-ttu-id="05962-179">ベースライン保護を使用して teams を構成する</span><span class="sxs-lookup"><span data-stu-id="05962-179">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="05962-180">機密データの保護で teams を構成する</span><span class="sxs-lookup"><span data-stu-id="05962-180">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="05962-181">非常に機密性の高いデータの保護を使用して teams を構成する</span><span class="sxs-lookup"><span data-stu-id="05962-181">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="05962-182">組織内でも、共有に対する追加の保護を必要とする非常に機密性の高いプロジェクトがある場合は、チームのメンバーだけがファイルを読むことができるように、独自の機密ラベルを使用してファイルを暗号化するようにチームを構成できます。</span><span class="sxs-lookup"><span data-stu-id="05962-182">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="05962-183">詳細について[は、「セキュリティの分離を使用してチームを構成](secure-teams-security-isolation.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="05962-183">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

## <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="05962-184">組織外のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="05962-184">Sharing with people outside your organization</span></span>

<span data-ttu-id="05962-185">[組織外のユーザーとの秘密度の情報を共有](collaborate-with-people-outside-your-organization.md)する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="05962-185">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="05962-186">これは、単一のドキュメントを1人のユーザーと共有することから、世界中の大規模なパートナー組織またはフリーランサーを持つ主要なプロジェクトで共同作業を行うことまで多岐に沿っています。</span><span class="sxs-lookup"><span data-stu-id="05962-186">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="05962-187">Microsoft 365 では、機密情報を保護するための適切な保護対策を使用して、この範囲の外部共有を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="05962-187">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="05962-188">これらのリソースは、組織外のユーザーと共同作業するための環境のセットアップを開始するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05962-188">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="05962-189">フォルダーの個々のファイルを共有するために[ドキュメントで共同作業](collaborate-on-documents.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="05962-189">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="05962-190">SharePoint サイトのゲストと共同作業するために[サイトで共同作業](collaborate-in-site.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="05962-190">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="05962-191">チーム内のゲストと共同作業を行う[チームとして共同作業](collaborate-as-team.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="05962-191">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="05962-192">共有されている情報の機密性に応じて、保護を追加して、過度の共有を防止できます。</span><span class="sxs-lookup"><span data-stu-id="05962-192">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="05962-193">次のリソースは、組織に必要な保護を設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05962-193">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="05962-194">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="05962-194">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="05962-195">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="05962-195">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="05962-196">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="05962-196">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="05962-197">パートナー組織との主要なプロジェクトがある場合は、プロジェクトに対して設定したチームで、Azure の資格管理を使用してその組織からゲストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="05962-197">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="05962-198">詳細について[は、「管理されたゲストでの B2B エクストラネットの作成](b2b-extranet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05962-198">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="see-also"></a><span data-ttu-id="05962-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="05962-199">See also</span></span>

[<span data-ttu-id="05962-200">Microsoft 365 のセキュリティに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="05962-200">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="05962-201">Microsoft 365 コンプライアンスのドキュメント</span><span class="sxs-lookup"><span data-stu-id="05962-201">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="05962-202">Microsoft Teams にようこそ</span><span class="sxs-lookup"><span data-stu-id="05962-202">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)