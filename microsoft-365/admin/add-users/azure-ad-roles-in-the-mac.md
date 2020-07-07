---
title: Microsoft 365管理センター のAzure Active Directory の役割について
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
description: Microsoft 365 管理センターで Azure 管理者の役割を管理する。
ms.openlocfilehash: d35daab57446fd2a6a052f7e0fca29af7910c5f9
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432486"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a><span data-ttu-id="fcdfb-103">Microsoft 365管理センター のAzure Active Directory の役割について</span><span class="sxs-lookup"><span data-stu-id="fcdfb-103">Azure Active Directory roles in the Microsoft 365 admin center</span></span>

<span data-ttu-id="fcdfb-104">Microsoft 365 管理センターでは、30 を超える Azure AD の役割を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-104">The Microsoft 365 admin center lets you manage over 30 Azure AD roles.</span></span> <span data-ttu-id="fcdfb-105">ただし、これらの役割は、Azure ポータルで使用可能な役割のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-105">However, these roles are a subset of the roles available in the Azure portal.</span></span> <span data-ttu-id="fcdfb-106">大企業の場合、Azure ポータルに組織のニーズを満たす役割があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-106">If you have a large business, there might be roles in the Azure portal that meet your organizational needs.</span></span> <span data-ttu-id="fcdfb-107">Azure AD の役割の詳細な説明をお探しですか ?</span><span class="sxs-lookup"><span data-stu-id="fcdfb-107">Looking for the detailed role descriptions for Azure AD?</span></span> <span data-ttu-id="fcdfb-108">「[Azure Active Directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-108">Check out [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span></span>

<span data-ttu-id="fcdfb-109">Microsoft 365 管理センターまたは Azure ポータルで役割を割り当てても、Windows PowerShell の Azure AD モジュールを使用してロールを割り当てても関係なく、管理者ロールを割り当てられたユーザーが、組織が登録されているクラウド サービスへの同じアクセス レベルを所有します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-109">A user who is assigned an admin role will have the same level of access to cloud services that your organization has subscribed to, regardless of whether you assign the role in the Microsoft 365 admin center or the Azure portal, or by using the Azure AD module for Windows PowerShell.</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="fcdfb-110">Microsoft 365 管理センターで、[**役割**] に移動し、任意の役割を選択して詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-110">In the Microsoft 365 admin center, you can go to **Roles**, and then select any role to open its detail pane.</span></span> <span data-ttu-id="fcdfb-111">[**アクセス許可**] タブを選択して、実行する許可を持った役割を割り当てられた管理者についての詳細な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-111">Select the **Permissions** tab to view the detailed list of what admins assigned that role have permissions to do.</span></span> <span data-ttu-id="fcdfb-112">役割にユーザーを追加するには、**[割り当てられた]** または **[割り当てられた管理者]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-112">Select the **Assigned** or **Assigned admins** tab to add users to roles.</span></span> <span data-ttu-id="fcdfb-113">Microsoft 365 管理センターでの役割を割り当てる方法の詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-113">For more information on assigning roles in the Microsoft 365 admin center, see [Assign admin roles](assign-admin-roles.md).</span></span>

::: moniker-end

## <a name="all-azure-ad-roles"></a><span data-ttu-id="fcdfb-114">すべての Azure AD の役割</span><span class="sxs-lookup"><span data-stu-id="fcdfb-114">All Azure AD roles</span></span>

<span data-ttu-id="fcdfb-115">以下は、Microsoft 365 管理センターで利用可能なすべての管理者ロールの一覧です。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-115">Here's a list of all the admin roles available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fcdfb-116">Microsoft 365 の管理者役割について詳しい説明をお探しですか ?</span><span class="sxs-lookup"><span data-stu-id="fcdfb-116">Looking for the detailed role descriptions of the Microsoft 365 admin roles?</span></span> <span data-ttu-id="fcdfb-117">[管理者ロールの詳細](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)をチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-117">Check out [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

|<span data-ttu-id="fcdfb-118">管理者ロール</span><span class="sxs-lookup"><span data-stu-id="fcdfb-118">Admin role</span></span>     |<span data-ttu-id="fcdfb-119">説明</span><span class="sxs-lookup"><span data-stu-id="fcdfb-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fcdfb-120">アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-120">Application admin</span></span>     |    <span data-ttu-id="fcdfb-121">エンタープライズ アプリケーション、アプリケーションの登録、およびアプリケーション プロキシ設定へのフル アクセス。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-121">Full access to enterprise applications, application registrations, and application proxy settings.</span></span>     |
|<span data-ttu-id="fcdfb-122">アプリケーション開発者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-122">Application developer</span></span>     |    <span data-ttu-id="fcdfb-123">アプリケーションの登録を作成し、自分の代わりにアプリへのアクセスに同意します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-123">Create application registrations and consent to app access on their own behalf.</span></span>     |
|<span data-ttu-id="fcdfb-124">認証管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-124">Authentication admin</span></span>     |    <span data-ttu-id="fcdfb-125">ユーザーに対し、MFA などの非パスワード資格情報の認証の再登録を要求できます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-125">Can require users to re-register authentication for non-password credentials, like MFA.</span></span>     |
|<span data-ttu-id="fcdfb-126">Azure Information Protection 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-126">Azure Information Protection admin</span></span>     |   <span data-ttu-id="fcdfb-127">Azure Information Protection ポリシーのラベルを管理し、保護テンプレートを管理し、保護をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-127">Manages labels for the Azure Information Protection policy, manages protection templates, and activates protection.</span></span>       |
|<span data-ttu-id="fcdfb-128">請求管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-128">Billing admin</span></span>     |    <span data-ttu-id="fcdfb-129">購入、サブスクリプション管理、サービス リクエスト管理、サービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-129">Makes purchases, manages subscriptions, manages service requests, and monitors service health.</span></span>     |
|<span data-ttu-id="fcdfb-130">クラウド アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-130">Cloud application admin</span></span>     | <span data-ttu-id="fcdfb-131">エンタープライズ アプリケーション、アプリケーションの登録へのフル アクセス。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-131">Full access to enterprise applications and application registrations.</span></span> <span data-ttu-id="fcdfb-132">アプリケーションプロキシは対象外です。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-132">No application proxy.</span></span>     |
|<span data-ttu-id="fcdfb-133">クラウド デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-133">Cloud device admin</span></span>     |    <span data-ttu-id="fcdfb-134">デバイスの有効化、無効化、および削除をし、Windows 10 BitLocker キーを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-134">Enables, disables, and deletes devices and can read Windows 10 BitLocker keys.</span></span>     |
|<span data-ttu-id="fcdfb-135">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-135">Compliance admin</span></span>     |    <span data-ttu-id="fcdfb-136">規制要件および eDiscovery ケースを管理し、場所、ID、アプリのデータ ガバナンスを維持します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-136">Manages regulatory requirements and eDiscovery cases, maintains data governance for locations, identities, and apps.</span></span>     |
|<span data-ttu-id="fcdfb-137">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-137">Compliance data admin</span></span>     |    <span data-ttu-id="fcdfb-138">データを追跡し、データが保護されていることを確認し、問題に対する分析情報を取得し、リスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-138">Keeps track of data, makes sure it's protected, gets insights into issues, and helps mitigate risk.</span></span>     |
|<span data-ttu-id="fcdfb-139">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-139">Conditional Access admin</span></span>     |   <span data-ttu-id="fcdfb-140">Azure Active Directory の条件付きアクセス設定を管理しますが、Exchange ActiveSync の条件付きアクセス ポリシーは管理しません。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-140">Manages Azure Active Directory conditional access settings, but not Exchange ActiveSync conditional access policy.</span></span>      |
|<span data-ttu-id="fcdfb-141">カスタマー ロックボックス アクセス承認者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-141">Customer Lockbox access approver</span></span>     |      <span data-ttu-id="fcdfb-142">カスタマーロックボックス要求を管理します。カスタマーロックボックスのオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-142">Manages Customer Lockbox requests, can turn Customer Lockbox on or off.</span></span>   |
|<span data-ttu-id="fcdfb-143">Desktop Analytics 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-143">Desktop Analytics admin</span></span>     |   <span data-ttu-id="fcdfb-144">デスクトップ管理ツールおよびサービスにアクセスし、管理できます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-144">Can access and manage Desktop management tools and services.</span></span>      |
|<span data-ttu-id="fcdfb-145">Dynamics 365 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-145">Dynamics 365 admin</span></span>     |  <span data-ttu-id="fcdfb-146">Microsoft Dynamics 365 Online へのフル アクセス。サービス リクエストの管理、サービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-146">Full access to Microsoft Dynamics 365 Online, manages service requests, monitors service health.</span></span>       |
|<span data-ttu-id="fcdfb-147">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-147">Exchange admin</span></span>     |  <span data-ttu-id="fcdfb-148">Exchange Online へのフル アクセス。グループの作成および管理、サービス リクエストの管理、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-148">Full access to Exchange Online, creates and manages groups, manages service requests, and monitors service health.</span></span>    |
|<span data-ttu-id="fcdfb-149">外部 ID プロバイダー管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-149">External identity provider admin</span></span>    |     <span data-ttu-id="fcdfb-150">直接フェデレーションで使用する ID プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-150">Configure identity providers for use in direct federation.</span></span>    |
|<span data-ttu-id="fcdfb-151">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-151">Global admin</span></span>     |    <span data-ttu-id="fcdfb-152">すべての管理センターのすべての管理機能およびほとんどのデータに無制限にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-152">Has unlimited access to all management features and most data in all admin centers.</span></span>     |
|<span data-ttu-id="fcdfb-153">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-153">Global reader</span></span>     |    <span data-ttu-id="fcdfb-154">すべての管理センターのすべての管理機能およびほとんどのデータへの読み取り専用アクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-154">Has read-only access to all management features and most data in admin centers.</span></span> <span data-ttu-id="fcdfb-155">この役割のアクセス権および制限の詳細については、「[Azure Active Directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-155">For a detailed description of access rights and limitations of this role, please see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>    |
|<span data-ttu-id="fcdfb-156">グループ管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-156">Groups admin</span></span>   |<span data-ttu-id="fcdfb-157">グループを作成し、管理センター全体のすべてのグループ設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-157">Creates groups and manages all groups settings across admin centers.</span></span>|
|<span data-ttu-id="fcdfb-158">ゲスト招待者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-158">Guest inviter</span></span>     |    <span data-ttu-id="fcdfb-159">Azure Active Directory B2B ゲスト ユーザーの招待を管理します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-159">Manages Azure Active Directory B2B guest user invitations.</span></span>     |
|<span data-ttu-id="fcdfb-160">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-160">Helpdesk admin</span></span>     | <span data-ttu-id="fcdfb-161">すべての非管理者および一部の管理者ロールのパスワードをリセットして再認証し、サービス リクエストを管理し、サービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-161">Resets passwords and re-authenticates for all non-admins and some admin roles, manages service requests, and monitors service health.</span></span>      |
|<span data-ttu-id="fcdfb-162">Intune 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-162">Intune admin</span></span>     | <span data-ttu-id="fcdfb-163">Intune へのフル アクセス。ユーザーとデバイスの管理によるポリシーの関連付け、グループの作成および管理を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-163">Full access to Intune, manages users and devices to associate policies, creates and manages groups.</span></span>      |
|<span data-ttu-id="fcdfb-164">Kaizala 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-164">Kaizala admin</span></span>     |    <span data-ttu-id="fcdfb-165">すべての Kaizala 管理機能およびデータへのフル アクセス。サービス リクエストの管理を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-165">Full access to all Kaizala management features and data, manages service requests.</span></span>     |
|<span data-ttu-id="fcdfb-166">ライセンス管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-166">License admin</span></span>     |     <span data-ttu-id="fcdfb-167">ユーザーへのライセンスの割り当ておよび削除を行い、ユーザーの使用場所を編集します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-167">Assigns and removes licenses from users and edits their usage location.</span></span>    |
|<span data-ttu-id="fcdfb-168">メッセージ センターのプライバシー閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-168">Message center privacy reader</span></span>     |    <span data-ttu-id="fcdfb-169">メッセージ センターのデータ プライバシー メッセージへのアクセス。メール通知の取得を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-169">Access to data privacy messages in Message center, gets email notifications.</span></span>     |
|<span data-ttu-id="fcdfb-170">メッセージ センター閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-170">Message center reader</span></span>     | <span data-ttu-id="fcdfb-171">メッセージ センターで通常のメッセージの読み取りおよび共有を行い、毎週のメール ダイジェストを取得し、ユーザー、グループ、ドメイン、およびサブスクリプションへの読み取り専用アクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-171">Reads and shares regular messages in Message center, gets weekly email digests, has read-only access to users, groups, domains, and subscriptions.</span></span>     |
|<span data-ttu-id="fcdfb-172">Office アプリ管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-172">Office Apps admin</span></span>    |   <span data-ttu-id="fcdfb-173">Office のクラウドベース ポリシー、およびユーザーの Office アプリに表示される新しいコンテンツの管理を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-173">Manages cloud-based policies for Office and the What's New content that users see in their Office apps.</span></span>   |
|<span data-ttu-id="fcdfb-174">Power BI 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-174">Power BI admin</span></span>    |   <span data-ttu-id="fcdfb-175">Power Bl 管理タスクへのフル アクセス。サービス リクエストを管理し、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-175">Full access to Power Bl management tasks, manages service requests, and monitors service health.</span></span>   |
|<span data-ttu-id="fcdfb-176">Power プラットフォーム管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-176">Power platform admin</span></span>     |    <span data-ttu-id="fcdfb-177">Microsoft Dynamics 365、PowerApps、データ損失防止ポリシー、および Microsoft Flow へのフル アクセス。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-177">Full access to Microsoft Dynamics 365, PowerApps, data loss prevention policies, and Microsoft Flow.</span></span>     |
|<span data-ttu-id="fcdfb-178">特権ロール管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-178">Privileged role admin</span></span>     |    <span data-ttu-id="fcdfb-179">役割の割り当て、および Privileged Identity Management のすべてのアクセス制御機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-179">Manages role assignments and all access control features of Privileged Identity Management.</span></span>     |
|<span data-ttu-id="fcdfb-180">特権認証管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-180">Privileged authentication admin</span></span>     |    <span data-ttu-id="fcdfb-181">パスワードのリセットや、パスワード以外の資格情報の更新、強制的サインアウト、サービスの正常性の監視、およびサービス要求の管理を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-181">Resets passwords, updates non-password credentials, forces uses to sign out and monitors service health and manages service requests.</span></span>     |
|<span data-ttu-id="fcdfb-182">レポート閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-182">Reports reader</span></span>     |   <span data-ttu-id="fcdfb-183">レポート ダッシュボード、PowerBI 導入コンテンツ パック、サインイン レポート、および Microsoft Graph による API のレポートから使用状況レポート データを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-183">Reads usage reporting data from the reports dashboard, PowerBI adoption content pack, sign-in reports, and Microsoft Graph reporting API.</span></span>      |
|<span data-ttu-id="fcdfb-184">検索管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-184">Search admin</span></span>     |    <span data-ttu-id="fcdfb-185">Microsoft Search へのフル アクセス。検索管理者および検索編集者ロールの割り当て、編集コンテンツの管理、サービス正常性の監視、およびサービス リクエストの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-185">Full access to Microsoft Search, assigns the Search admin and Search editor roles, manages editorial content, monitors service health, and creates service requests.</span></span>     |
|<span data-ttu-id="fcdfb-186">検索編集者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-186">Search editor</span></span>     |    <span data-ttu-id="fcdfb-187">ブックマーク、Q＆A、場所など、Microsoft Search のコンテンツの作成、編集、および削除のみができます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-187">Can only create, edit, and delete content for Microsoft Search, like bookmarks, Q&A, and locations.</span></span>     |
|<span data-ttu-id="fcdfb-188">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-188">Security admin</span></span>     |    <span data-ttu-id="fcdfb-189">組織のセキュリティの制御、セキュリティ ポリシーの管理、セキュリティ分析およびレポートの確認、脅威の状況の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-189">Controls organization's security, manages security policies, reviews security analytics and reports, monitors the threat landscape.</span></span>     |
|<span data-ttu-id="fcdfb-190">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="fcdfb-190">Security operator</span></span>     |    <span data-ttu-id="fcdfb-191">セキュリティの警告の調査および対応、Identity Protection センターの機能の管理、サービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-191">Investigates and responds to security alerts, manages features in Identity Protection center, monitors service health.</span></span>     |
|<span data-ttu-id="fcdfb-192">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-192">Security reader</span></span>     |    <span data-ttu-id="fcdfb-193">セキュリティ機能、サインイン レポート、監査ログへの読み取り専用アクセス。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-193">Read-only access to security features, sign-in reports, and audit logs.</span></span>     |
|<span data-ttu-id="fcdfb-194">サービス サポート管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-194">Service support admin</span></span>     |    <span data-ttu-id="fcdfb-195">Azure、Microsoft 365、および Office 365 サービスのサービス リクエストの作成、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-195">Creates service requests for Azure, Microsoft 365, and Office 365 services, and monitors service health.</span></span>     |
|<span data-ttu-id="fcdfb-196">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-196">SharePoint admin</span></span>     |    <span data-ttu-id="fcdfb-197">SharePoint Online へのフル アクセス。Microsoft 365 グループの管理、サービス リクエストの管理、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-197">Full access to SharePoint Online, manages Microsoft 365 groups, manages service requests, and monitors service health.</span></span>     |
|<span data-ttu-id="fcdfb-198">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-198">Skype for Business admin</span></span>     | <span data-ttu-id="fcdfb-199">すべての Teams および Skype 機能、Skype ユーザー属性へのフル アクセス。サービス リクエストの管理、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-199">Full access to all Teams and Skype features, Skype user attributes, manages service requests, and monitors service health.</span></span>      |
|<span data-ttu-id="fcdfb-200">Teams 管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-200">Teams admin</span></span>     |    <span data-ttu-id="fcdfb-201">Teams および Skype 管理センターへのフル アクセス。Microsoft 365 グループおよびサービス リクエストの管理、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-201">Full access to Teams & Skype admin center, manages Microsoft 365 groups and service requests, and monitors service health.</span></span>     |
|<span data-ttu-id="fcdfb-202">Teams 通信マネージャー</span><span class="sxs-lookup"><span data-stu-id="fcdfb-202">Teams communication manager</span></span>     |    <span data-ttu-id="fcdfb-203">電話番号の割り当て、音声および会議ポリシーの作成および管理、通話分析の読み取りを行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-203">Assigns telephone numbers, creates and manages voice and meeting policies, and reads call analytics.</span></span>     |
|<span data-ttu-id="fcdfb-204">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="fcdfb-204">Teams communication support engineer</span></span>     |    <span data-ttu-id="fcdfb-205">すべての通話参加者の通話レコードの詳細情報を読み取り、通信の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-205">Reads call record details for all call participants to troubleshoot communication issues.</span></span>     |
|<span data-ttu-id="fcdfb-206">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="fcdfb-206">Teams communication support specialist</span></span>     |    <span data-ttu-id="fcdfb-207">特定のユーザーのみのユーザーの通話詳細を読み取り、通信の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-207">Reads user call details only for a specific user to troubleshoot communication issues.</span></span>|
|<span data-ttu-id="fcdfb-208">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="fcdfb-208">User admin</span></span>     |   <span data-ttu-id="fcdfb-209">ユーザー パスワードのリセット、フィルターを含むユーザーとグループの作成と管理、サービス リクエストの管理、およびサービス正常性の監視を行います。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-209">Resets user passwords, creates and manages users and groups, including filters, manages service requests, and monitors service health.</span></span>|

## <a name="delegated-administration-for-microsoft-partners"></a><span data-ttu-id="fcdfb-210">Microsoft パートナーの代理管理</span><span class="sxs-lookup"><span data-stu-id="fcdfb-210">Delegated administration for Microsoft Partners</span></span>

<span data-ttu-id="fcdfb-211">Microsoft パートナーと連携している場合、パートナーに管理者ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-211">If you're working with a Microsoft partner, you can assign them admin roles.</span></span> <span data-ttu-id="fcdfb-212">次に、彼らはあなたの会社のユーザーまたはその会社の管理者ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-212">They, in turn, can assign users in your company - or their company - admin roles.</span></span> <span data-ttu-id="fcdfb-213">たとえば、彼らがあなたのためにオンライン組織をセットアップし管理している場合、彼らにして欲しいのはこれかもしれません。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-213">You might want them to do this, for example, if they are setting up and managing your online organization for you.</span></span>
  
<span data-ttu-id="fcdfb-214">パートナーは、次の役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-214">A partner can assign these roles:</span></span>

- <span data-ttu-id="fcdfb-215">パートナー センターを介した多要素認証の管理を除いた、グローバル管理者と同等の特権を持つ完全な管理。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-215">Full administration, which has privileges equivalent to a global admin, with the exception of managing multi-factor authentication through the Partner Center.</span></span>

- <span data-ttu-id="fcdfb-216">ヘルプデスク管理者と同等の特権を持つ制限付き管理。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-216">Limited administration, which has privileges equivalent to a helpdesk admin.</span></span>

<span data-ttu-id="fcdfb-217">パートナーがこれらの役割をユーザーに割り当てる前に、パートナーを代理管理者としてアカウントに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-217">Before the partner can assign these roles to users, you must add the partner as a delegated admin to your account.</span></span> <span data-ttu-id="fcdfb-218">このプロセスは認定パートナーによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-218">This process is initiated by an authorized partner.</span></span> <span data-ttu-id="fcdfb-219">パートナーは管理者に電子メールを送信し、代理管理者となる権限を割り当てるかどうか質問します。手順については、「[パートナー リレーションシップの承認または削除](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdfb-219">The partner sends you an email to ask you if you want to give them permission to act as a delegated admin. For instructions, see [Authorize or remove partner relationships](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="fcdfb-220">関連記事</span><span class="sxs-lookup"><span data-stu-id="fcdfb-220">Related articles</span></span>

[<span data-ttu-id="fcdfb-221">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="fcdfb-221">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

[<span data-ttu-id="fcdfb-222">管理者の役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fcdfb-222">Assign admin roles</span></span>](assign-admin-roles.md)
  
[<span data-ttu-id="fcdfb-223">Microsoft 365 管理センターのアクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="fcdfb-223">Activity reports in the Microsoft 365 admin center</span></span>](../activity-reports/activity-reports.md)