---
title: 管理されたゲストで B2B エクストラネットを作成する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: パートナー組織から管理されたゲストユーザーを使用して、B2B エクストラネットのサイトまたはチームを作成する方法について説明します。
ms.openlocfilehash: 24a2652d4d025f194d0754b90b6a21a054f4159a
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604772"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="69181-103">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="69181-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="69181-104">Azure active [Directory 受給管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)を使用して、Azure active directory を使用するパートナー組織と共同作業する B2B エクストラネットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="69181-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="69181-105">これにより、ユーザーは、エクストラネットサイトまたはチームで自分を登録し、承認ワークフローを使用してアクセスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="69181-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="69181-106">グループ作業のためにリソースを共有するためのこの方法を使用すると、パートナー組織は、エンドユーザーに対するゲストユーザーの管理と承認を支援し、IT 部門の負担を軽減して、ユーザーを管理するためのコラボレーション契約に精通しているユーザーを許可することができます。接続.</span><span class="sxs-lookup"><span data-stu-id="69181-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="69181-107">この記事では、セルフサービスアクセス登録モデルを使用してパートナー組織と共有できるリソース (この場合は、サイトまたはチーム) のパッケージを作成するための手順を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="69181-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="69181-108">開始する前に、パートナー組織と共有するサイトまたはチームを作成し、ゲスト共有に対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="69181-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="69181-109">詳細については[、「サイト内のゲストを使用した共同作業](collaborate-in-site.md)」または「[チーム内のゲストによる共同作業](collaborate-as-team.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69181-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="69181-110">また、ゲストを使用して共同作業を行う場合に、ガバナンスポリシーを維持するために使用できるセキュリティとコンプライアンスの機能については、「セキュリティ[保護されたゲスト共有環境を作成](create-secure-guest-sharing-environment.md)する」を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69181-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="connect-the-partner-organization"></a><span data-ttu-id="69181-111">パートナー組織を接続する</span><span class="sxs-lookup"><span data-stu-id="69181-111">Connect the partner organization</span></span>

<span data-ttu-id="69181-112">パートナー組織からゲストを招待するには、パートナーのドメインを、接続された組織として Azure Active Directory に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69181-112">In order to invite guests from a partner organization, you need to add the the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="69181-113">接続された組織を追加するには</span><span class="sxs-lookup"><span data-stu-id="69181-113">To add a connected organization</span></span>
1. <span data-ttu-id="69181-114">[Azure Active Directory](https://aad.portal.azure.com)で、[ **id ガバナンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-114">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="69181-115">[**接続組織**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-115">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="69181-116">[**接続組織の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-116">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="69181-117">組織の名前と説明を入力し、[**次へ: ディレクトリ + ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-117">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="69181-118">[**ディレクトリ + ドメインの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-118">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="69181-119">接続する組織のドメインを入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-119">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="69181-120">[**接続**] をクリックし、[**次へ: スポンサー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-120">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="69181-121">組織内のユーザー、またはゲストユーザーのアクセスを承認するユーザーを追加する組織からユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="69181-121">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="69181-122">[ **Next: Review + Create**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-122">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="69181-123">選択した設定を確認し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-123">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Azure Active Directory の [接続されている組織] ページのスクリーンショット](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="69181-125">共有するリソースを選択する</span><span class="sxs-lookup"><span data-stu-id="69181-125">Choose the resources to share</span></span>

<span data-ttu-id="69181-126">パートナー組織と共有するリソースを選択する最初の手順は、それらを含めるためのカタログを作成することです。</span><span class="sxs-lookup"><span data-stu-id="69181-126">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="69181-127">カタログを作成するには</span><span class="sxs-lookup"><span data-stu-id="69181-127">To create a catalog</span></span>
1. <span data-ttu-id="69181-128">[Azure Active Directory](https://aad.portal.azure.com)で、[ **id ガバナンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-128">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="69181-129">[**カタログ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-129">Click **Catalogs**.</span></span>
3. <span data-ttu-id="69181-130">[**新しいカタログ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-130">Click **New catalog**.</span></span>
4. <span data-ttu-id="69181-131">カタログの名前と説明を入力し、[**有効**] と [**外部ユーザーが有効**] と [有効] の両方が **[はい]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69181-131">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="69181-132">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-132">Click **Create**.</span></span>

   ![Azure Active Directory Id ガバナンスの [カタログ] ページのスクリーンショット](../media/identity-governance-catalogs.png)

<span data-ttu-id="69181-134">カタログを作成したら、パートナー組織と共有する SharePoint サイトまたはチームを追加します。</span><span class="sxs-lookup"><span data-stu-id="69181-134">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="69181-135">リソースをカタログに追加するには</span><span class="sxs-lookup"><span data-stu-id="69181-135">To add resources to a catalog</span></span>
1. <span data-ttu-id="69181-136">Azure AD Identity ガバナンスで、[**カタログ**] をクリックし、リソースを追加するカタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-136">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="69181-137">[**リソース**] をクリックし、[**リソースの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-137">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="69181-138">エクストラネットに含める teams または SharePoint サイトを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-138">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Azure Active Directory Id ガバナンスの [カタログリソース] ページのスクリーンショット](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="69181-140">共有するリソースを定義したら、次の手順として、アクセスパッケージを作成します。これにより、パートナーユーザーに付与されるアクセスの種類、およびアクセスを要求する新しいパートナーユーザーの承認プロセスが定義されます。</span><span class="sxs-lookup"><span data-stu-id="69181-140">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="69181-141">アクセスパッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="69181-141">To create an access package</span></span>
1. <span data-ttu-id="69181-142">Azure AD Identity ガバナンスで、[**カタログ**] をクリックし、アクセスパッケージを作成するカタログをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-142">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="69181-143">[ **Access パッケージ**] をクリックし、[**新しいアクセスパッケージ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-143">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="69181-144">アクセスパッケージの名前と説明を入力し、[**次へ: リソースロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-144">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="69181-145">エクストラネットに使用するリソースをカタログから選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-145">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="69181-146">各リソースの [**役割**] 列で、エクストラネットを使用するゲストユーザーに付与するユーザーロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-146">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="69181-147">[**次へ: 要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-147">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="69181-148">[**アクセスを要求できるユーザー**] で、**ディレクトリ以外のユーザーに対して**[] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-148">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="69181-149">[特定の**接続組織**] オプションが選択されていることを確認し、[**ディレクトリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-149">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="69181-150">以前に追加した接続済み組織を選択し、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-150">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="69181-151">[**承認**] で、[**承認を必須**にする] で [**はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-151">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="69181-152">[**最初の承認者**] で、前に追加したスポンサのいずれかを選択するか、特定のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-152">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="69181-153">[**フォールバックの追加**] をクリックし、フォールバック承認者を選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-153">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="69181-154">[**有効にする**] で、[**はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69181-154">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="69181-155">[**次へ: ライフサイクル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-155">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="69181-156">使用する有効期限とアクセスレビューの設定を選択し、[次へ] をクリックします。 [**確認 + 作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-156">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="69181-157">設定内容を確認し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-157">Review your settings, and then click **Create**.</span></span>

    ![Azure Active Directory Id ガバナンスの [access パッケージ] 画面のスクリーンショット](../media/identity-governance-access-packages.png)

<span data-ttu-id="69181-159">大規模な組織と提携している場合は、アクセスパッケージを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69181-159">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="69181-160">パッケージが非表示の場合、パートナー組織のユーザーには、*自分のアクセス*ポータルにパッケージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="69181-160">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="69181-161">代わりに、そのパッケージにサインアップするための直接リンクを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69181-161">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="69181-162">アクセスパッケージを非表示にすると、不適切なアクセス要求の数を減らすことができます。また、パートナー組織のポータルで利用できるアクセスパッケージを保持するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="69181-162">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="69181-163">アクセスパッケージを非表示に設定するには</span><span class="sxs-lookup"><span data-stu-id="69181-163">To set an access package to hidden</span></span>
1. <span data-ttu-id="69181-164">[Azure AD Identity ガバナンス] で、[**アクセスパッケージ**] をクリックし、アクセスパッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-164">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="69181-165">[**概要**] ページで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-165">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="69181-166">[**プロパティ**] で [**非表示**の場合は**はい]** を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-166">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![[Access パッケージの編集のプロパティ] 画面のスクリーンショット](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="69181-168">パートナーユーザーの招待</span><span class="sxs-lookup"><span data-stu-id="69181-168">Invite partner users</span></span>

<span data-ttu-id="69181-169">アクセスパッケージを非表示に設定した場合は、パートナー組織への直接リンクを送信して、サイトまたはチームへのアクセスを要求できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69181-169">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="69181-170">アクセスポータルのリンクを見つけるには</span><span class="sxs-lookup"><span data-stu-id="69181-170">To find the access portal link</span></span>
1. <span data-ttu-id="69181-171">[Azure AD Identity ガバナンス] で、[**アクセスパッケージ**] をクリックし、アクセスパッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-171">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="69181-172">[**概要**] ページで、[ **My Access ポータル] リンク**の [**クリップボードにコピー** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69181-172">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Access ポータルリンクを使用した access パッケージプロパティのスクリーンショット](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="69181-174">リンクをコピーしたら、パートナー組織の連絡先と共有することができます。また、そのリンクをコラボレーションチームのユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="69181-174">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="69181-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="69181-175">See Also</span></span>

[<span data-ttu-id="69181-176">セキュリティで保護されたゲスト共有の環境を作成する</span><span class="sxs-lookup"><span data-stu-id="69181-176">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
