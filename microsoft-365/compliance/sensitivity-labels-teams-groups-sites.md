---
title: Microsoft Teams、Office 365 グループ、および SharePoint サイトで機密ラベルを使用する (パブリックプレビュー)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: ラベルは、Microsoft Teams、Office 365 グループ、および SharePoint サイトに適用できます。
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686850"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="5351d-103">Microsoft Teams、Office 365 グループ、および SharePoint サイトで機密ラベルを使用する (パブリックプレビュー)</span><span class="sxs-lookup"><span data-stu-id="5351d-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="5351d-104">[Microsoft 365 コンプライアンスセンター](https://protection.office.com/)で機密ラベルを作成すると、それらを microsoft Teams、Office 365 グループ、および SharePoint サイトに適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5351d-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="5351d-105">ポリシーをラベルに関連付けて、次の操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="5351d-106">パブリック/プライベート設定</span><span class="sxs-lookup"><span data-stu-id="5351d-106">Public/private settings</span></span>
- <span data-ttu-id="5351d-107">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="5351d-107">Guest access</span></span>
- <span data-ttu-id="5351d-108">非管理対象デバイスからのアクセス</span><span class="sxs-lookup"><span data-stu-id="5351d-108">Access from unmanaged devices</span></span>

<span data-ttu-id="5351d-109">チームまたはグループにラベルを適用すると、ラベルは接続された SharePoint チームサイトに自動的に適用され、その他の方法も使用されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="5351d-110">これで、SharePoint および OneDrive で Office ファイルの機密ラベルを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5351d-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="5351d-111">[詳細については、こちらを参照してください](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="5351d-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="5351d-112">Microsoft Teams、Office 365 グループ、および SharePoint サイトのパブリックプレビューについて</span><span class="sxs-lookup"><span data-stu-id="5351d-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="5351d-113">Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルは、テナントに段階的にロールアウトされるため、最終リリースまでに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5351d-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

## <a name="overview"></a><span data-ttu-id="5351d-114">概要</span><span class="sxs-lookup"><span data-stu-id="5351d-114">Overview</span></span>

<span data-ttu-id="5351d-115">機密ラベルを発行すると、Office 365 のユーザーは、同じラベルリストにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5351d-115">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="5351d-116">次の画像が表示:</span><span class="sxs-lookup"><span data-stu-id="5351d-116">These images show:</span></span>

- <span data-ttu-id="5351d-117">SharePoint から新しいチームサイトを作成するときのリストの表示方法</span><span class="sxs-lookup"><span data-stu-id="5351d-117">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="5351d-118">Word でリストを表示する場合</span><span class="sxs-lookup"><span data-stu-id="5351d-118">When you view the list in Word</span></span>

![SharePoint からチームサイトを作成するときの機密ラベル](media/sensitivity-label-new-team-site.png)

![Word デスクトップアプリに表示される機密ラベル](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="5351d-121">Azure PowerShell を使用してこのプレビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="5351d-121">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="5351d-122">Azure PowerShell を使用して、グローバル管理者として Azure にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5351d-122">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="5351d-123">手順については、「 [Azure PowerShell を使用](/powershell/azure/authenticate-azureps)してサインインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-123">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="5351d-124">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5351d-124">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="5351d-125">このプレビューを有効にした場合、Office 365 は新しいグループおよび SharePoint サイトに古い分類を使用しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5351d-125">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="5351d-126">[AZURE AD サイトの分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification)($setting ["ClassificationList"]) を使用した場合は、既存のグループとサイトでも古い分類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-126">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="5351d-127">新しい分類を表示するには、変換します。</span><span class="sxs-lookup"><span data-stu-id="5351d-127">To display the new classifications, convert them.</span></span> <span data-ttu-id="5351d-128">変換方法の詳細については、「[従来の AZURE AD サイトの分類を使用したかどうか](#if-you-used-classic-azure-ad-site-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-128">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span>

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a><span data-ttu-id="5351d-129">機密ラベルを作成するときにサイトとグループの設定を設定する</span><span class="sxs-lookup"><span data-stu-id="5351d-129">Set site and group settings when you create sensitivity labels</span></span>

<span data-ttu-id="5351d-130">プレビューを有効にした後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5351d-130">After you enable the preview, follow these steps:</span></span>

1. <span data-ttu-id="5351d-131">Microsoft 365 コンプライアンスセンターで、[**分類** > **機密ラベル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5351d-131">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="5351d-132">[**ラベルの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5351d-132">Select **Create a label**.</span></span>

3. <span data-ttu-id="5351d-133">必要なオプションを選択し、[**サイトとグループの設定**] タブで以下を選択します。</span><span class="sxs-lookup"><span data-stu-id="5351d-133">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="5351d-134">Privacy (パブリック/プライベート): Private は、組織内の承認されたメンバーのみがグループ内の内容を表示できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5351d-134">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="5351d-135">組織内の他のすべてのユーザーはグループの内容を表示できません。</span><span class="sxs-lookup"><span data-stu-id="5351d-135">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="5351d-136">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5351d-136">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="5351d-137">ゲストアクセス: グループにゲストを追加できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-137">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="5351d-138">Office 365 グループでのゲストアクセスの管理について</span><span class="sxs-lookup"><span data-stu-id="5351d-138">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="5351d-139">[管理されていないデバイス]: この設定を使用すると、ハイブリッド AD に参加していない、または Intune で準拠していないデバイスから SharePoint コンテンツへのアクセスをブロックまたは制限できます</span><span class="sxs-lookup"><span data-stu-id="5351d-139">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="5351d-140">管理されていないデバイスを選択する場合は、ポリシーの設定を完了するために Azure AD に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5351d-140">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="5351d-141">詳細については、「[非管理対象デバイスからのアクセスの制御](/sharepoint/control-access-from-unmanaged-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-141">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![[サイトとグループの設定] タブ](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="5351d-143">チーム、グループ、またはサイトにラベルを適用すると、サイトおよびグループの設定のみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="5351d-143">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="5351d-144">暗号化やコンテンツマーキングなどのその他の設定は、チーム、グループ、またはサイト内のすべてのコンテンツに適用されません。</span><span class="sxs-lookup"><span data-stu-id="5351d-144">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="5351d-145">同様に、ラベルを作成してサイトとグループの設定を有効にしない場合でも、ユーザーがチーム、グループ、およびサイトを作成するときに、ラベルは使用できますが、ユーザーがそれを適用しても何も実行しません。</span><span class="sxs-lookup"><span data-stu-id="5351d-145">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="5351d-146">機密ラベルを発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5351d-146">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="5351d-147">新しいチームに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="5351d-147">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="5351d-148">ユーザーは、Microsoft Teams で新しいチームを作成するときに機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-148">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="5351d-149">機密レベルを選択すると、必要に応じてプライバシー設定が変更されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-149">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="5351d-150">ラベルに対して選択したゲストアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-150">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![新しいチームを作成するときのプライバシー設定](media/privacy-setting-new-team.png)

<span data-ttu-id="5351d-152">チームを作成すると、すべてのチャネルの右上隅に [機密] ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-152">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![機密ラベルがチームに表示されます。](media/privacy-setting-teams.png)

<span data-ttu-id="5351d-154">サービスは、Office 365 グループと接続された SharePoint チームサイトに同じ機密ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="5351d-154">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="5351d-155">新しいグループに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="5351d-155">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="5351d-156">Web 上の Outlook の場合、[新しい**秘密度**] ボックスには、発行済みのラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-156">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="5351d-157">ユーザーが詳細情報を必要とする場合は、ヘルプアイコンをクリックすると、使用可能なラベルと関連付けられているポリシーの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-157">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![グループを作成し、[感度] の下でオプションを選択する](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="5351d-159">新しいサイトに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="5351d-159">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="5351d-160">管理者とエンドユーザーは、モダンチームサイトとコミュニケーションサイトを作成するときに機密ラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-160">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="5351d-161">新しい SharePoint 管理センターでサイトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5351d-161">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="5351d-162">ユーザーがモダンチームおよびコミュニケーションサイトを作成する場合、既定では、既に機密ラベルが選択されています。</span><span class="sxs-lookup"><span data-stu-id="5351d-162">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="5351d-163">ユーザーは、[ヘルプ] アイコンを選択して、ラベルの詳細を参照できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-163">Users can select the help icon to learn more about the labels.</span></span>

![サイトを作成し、[秘密度] の下でオプションを選択する](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="5351d-165">ユーザーがサイトを参照すると、ラベルの名前と適用されたポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-165">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![機密ラベルが適用されたサイト](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="5351d-167">SharePoint 管理センターで機密ラベルを管理する</span><span class="sxs-lookup"><span data-stu-id="5351d-167">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="5351d-168">ラベルを表示および編集するには、新しい SharePoint 管理センターの [アクティブなサイト] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="5351d-168">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![[アクティブなサイト] ページの [秘密度] 列](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="5351d-170">[新しい SharePoint 管理センターでのサイト管理の詳細については、「」を参照して](/sharepoint/manage-sites-in-new-admin-center)ください。</span><span class="sxs-lookup"><span data-stu-id="5351d-170">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="5351d-171">ラベルのサイトとグループの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="5351d-171">Change site and group settings for a label</span></span>

<span data-ttu-id="5351d-172">ベストプラクティスとして、複数のチーム、グループ、またはサイトにラベルを適用した後に設定を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="5351d-172">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="5351d-173">変更を加える必要がある場合は、Azure AD PowerShell スクリプトを使用して更新プログラムを手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5351d-173">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="5351d-174">この方法により、既存のすべてのチーム、サイト、およびグループで新しい設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-174">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="5351d-175">新しい機密ラベルのサポート</span><span class="sxs-lookup"><span data-stu-id="5351d-175">Support for the new sensitivity labels</span></span>

<span data-ttu-id="5351d-176">このプレビューでは、次のアプリとサービスが機密ラベルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5351d-176">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="5351d-177">Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="5351d-177">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="5351d-178">SharePoint</span><span class="sxs-lookup"><span data-stu-id="5351d-178">SharePoint</span></span>
- <span data-ttu-id="5351d-179">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="5351d-179">Outlook on the web</span></span>
- <span data-ttu-id="5351d-180">Teams</span><span class="sxs-lookup"><span data-stu-id="5351d-180">Teams</span></span>
- <span data-ttu-id="5351d-181">SharePoint 管理センター</span><span class="sxs-lookup"><span data-stu-id="5351d-181">SharePoint admin center</span></span>
- <span data-ttu-id="5351d-182">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="5351d-182">Azure AD admin center</span></span>

<span data-ttu-id="5351d-183">次のアプリとサービスを使用して、新しい機密ラベルを使用して Office 365 グループを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="5351d-183">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="5351d-184">Mac 用の Outlook</span><span class="sxs-lookup"><span data-stu-id="5351d-184">Outlook for the Mac</span></span>
- <span data-ttu-id="5351d-185">Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="5351d-185">Outlook mobile</span></span>  
- <span data-ttu-id="5351d-186">Windows 用 Outlook デスクトップ</span><span class="sxs-lookup"><span data-stu-id="5351d-186">Outlook desktop for Windows</span></span>
- <span data-ttu-id="5351d-187">フォーム</span><span class="sxs-lookup"><span data-stu-id="5351d-187">Forms</span></span>  
- <span data-ttu-id="5351d-188">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5351d-188">Dynamics 365</span></span>  
- <span data-ttu-id="5351d-189">Yammer</span><span class="sxs-lookup"><span data-stu-id="5351d-189">Yammer</span></span>  
- <span data-ttu-id="5351d-190">Stream</span><span class="sxs-lookup"><span data-stu-id="5351d-190">Stream</span></span>  
- <span data-ttu-id="5351d-191">Planner</span><span class="sxs-lookup"><span data-stu-id="5351d-191">Planner</span></span>  
- <span data-ttu-id="5351d-192">Project</span><span class="sxs-lookup"><span data-stu-id="5351d-192">Project</span></span>  
- <span data-ttu-id="5351d-193">PowerBI</span><span class="sxs-lookup"><span data-stu-id="5351d-193">PowerBI</span></span>  
- <span data-ttu-id="5351d-194">Teams 管理センター</span><span class="sxs-lookup"><span data-stu-id="5351d-194">Teams admin center</span></span>  
- <span data-ttu-id="5351d-195">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="5351d-195">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="5351d-196">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="5351d-196">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="5351d-197">従来の Azure AD サイトの分類を使用している場合</span><span class="sxs-lookup"><span data-stu-id="5351d-197">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="5351d-198">このプレビューを有効にした場合、Office 365 は新しいグループと SharePoint サイトの古い分類をサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5351d-198">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="5351d-199">ただし、既存のグループやサイトでは、変換しない限り古い分類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-199">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="5351d-200">古い分類には、設定に対し`ClassificationList`て定義された "モダン" サイト分類があります。これには、Azure AD PowerShell または PnP コアライブラリを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="5351d-200">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="5351d-201">たとえば、PowerShell で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5351d-201">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="5351d-202">古い分類法の詳細については、「 [SharePoint "モダン" サイトの分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-202">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="5351d-203">現在の展開に基づいて、古い分類を新しい分類に変換するための2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5351d-203">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="5351d-204">ファイルと電子メールの機密ラベル (統合 Microsoft Information Protection ラベル) を使用していない場合</span><span class="sxs-lookup"><span data-stu-id="5351d-204">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="5351d-205">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5351d-205">We recommend that you:</span></span>

1. <span data-ttu-id="5351d-206">Microsoft 365 コンプライアンスセンターで、既存の分類と同じ名前を持つ新しい機密ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5351d-206">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="5351d-207">PowerShell を使用して、名前のマッピングを使用して、既存の Office 365 グループおよび SharePoint サイトに新しいラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="5351d-207">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="5351d-208">古い分類を削除します。</span><span class="sxs-lookup"><span data-stu-id="5351d-208">Delete the old classifications.</span></span>

<span data-ttu-id="5351d-209">新しい機密ラベルをサポートするアプリとサービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-209">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="5351d-210">新しいチーム、グループ、およびサイトを新しいラベルで作成します。</span><span class="sxs-lookup"><span data-stu-id="5351d-210">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="5351d-211">ユーザーは、新しいラベルをサポートしていないアプリやサービスからグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5351d-211">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="5351d-212">ただし、ユーザーはこれらのグループにラベルを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5351d-212">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="5351d-213">PowerShell を使用して、これらのグループに新しい機密ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="5351d-213">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="5351d-214">古い分類を維持することができます。ただし、これらのグループに新しい機密ラベルを適用するには、PowerShell を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5351d-214">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="5351d-215">新しい機密ラベルをサポートするアプリとサービスは、新しいラベルを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="5351d-215">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="5351d-216">ユーザーが新しいラベルをサポートしていないアプリやサービスからグループを作成する場合は、分類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5351d-216">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="5351d-217">ファイルと電子メールに機密ラベル (統合 Microsoft Information Protection ラベル) を使用する場合</span><span class="sxs-lookup"><span data-stu-id="5351d-217">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="5351d-218">このプレビューを有効にしたら、Microsoft 365 コンプライアンスセンターの各ラベルに移動し、サイトとグループに必要なポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="5351d-218">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="5351d-219">ユーザーは、サイトおよびグループで使用可能な既存のラベルを表示し始めます。</span><span class="sxs-lookup"><span data-stu-id="5351d-219">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="5351d-220">Office 365 グループのラベルを書き換える前に SharePoint Online 管理シェルを準備する</span><span class="sxs-lookup"><span data-stu-id="5351d-220">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="5351d-221">新しいラベルを適用する前に、最新の SharePoint Online 管理シェルを実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-221">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="5351d-222">すでに最新バージョンをお持ちの場合は、[新しい機密ラベルを使用して Office 365 グループの](#relabel-office-365-groups-with-new-sensitivity-labels)ラベルを書き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="5351d-222">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="5351d-223">プレビュー用の SharePoint Online 管理シェルを準備するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5351d-223">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="5351d-224">以前のバージョンの SharePoint Online Management Shell をインストールした場合は、[**プログラムの追加と削除**] に移動し、"SharePoint Online Management shell" をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="5351d-224">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="5351d-225">Web ブラウザーで、ダウンロードセンターページに移動して、[最新の SharePoint Online 管理シェルをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=255251)します。</span><span class="sxs-lookup"><span data-stu-id="5351d-225">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="5351d-226">言語を選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5351d-226">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="5351d-227">X64 ファイルと x86 .msi ファイルのどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5351d-227">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="5351d-228">64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="5351d-228">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="5351d-229">不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5351d-229">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="5351d-230">ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5351d-230">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="5351d-231">新しい機密ラベルを使用して Office 365 グループのラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="5351d-231">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="5351d-232">SharePoint Online 管理シェルの最新バージョンを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5351d-232">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5351d-233">手順については、「 [Office 365 グループのラベルを書き換える前に SharePoint Online 管理シェルを準備](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-233">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="5351d-234">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint Online 管理シェルに接続します。</span><span class="sxs-lookup"><span data-stu-id="5351d-234">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="5351d-235">方法の詳細については、「[SharePoint のオンライン管理シェルを使うにあたって](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5351d-235">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="5351d-236">次のコマンドを実行して、機密ラベルとその Guid の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="5351d-236">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="5351d-237">上書きするラベルの GUID をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="5351d-237">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="5351d-238">たとえば、"General" というラベルがあります。</span><span class="sxs-lookup"><span data-stu-id="5351d-238">For example, the "General" label.</span></span>

5. <span data-ttu-id="5351d-239">"General" 分類を持つグループの一覧を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5351d-239">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="5351d-240">このコマンドを実行すると、Exchange Online PowerShell に接続し、Set-unifiedgroup コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5351d-240">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="5351d-241">各グループに対して、新しい機密ラベル GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="5351d-241">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```