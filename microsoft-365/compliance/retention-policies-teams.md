---
title: Teams のアイテム保持ポリシーの詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft Teams に適用されるアイテム保持ポリシーについて説明します。
ms.openlocfilehash: 709d4414ebb01081172aff932899146c06d05a19
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268280"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a><span data-ttu-id="b2943-103">Microsoft Teams のアイテム保持ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="b2943-103">Learn about retention policies for Microsoft Teams</span></span>

><span data-ttu-id="b2943-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="b2943-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b2943-105">この記事の情報は、Microsoft Teams に固有の情報が含まれているため、「[アイテム保持ポリシーの詳細](retention-policies.md)」を補足するものです。</span><span class="sxs-lookup"><span data-stu-id="b2943-105">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Microsoft Teams.</span></span>

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a><span data-ttu-id="b2943-106">アイテム保持ポリシーは Microsoft Teams に対してどのように作用するか</span><span class="sxs-lookup"><span data-stu-id="b2943-106">How a retention policy works with Microsoft Teams</span></span>

<span data-ttu-id="b2943-107">アイテム保持ポリシーを使用して、Teams 内のチャットとチャネル メッセージを保持できます。</span><span class="sxs-lookup"><span data-stu-id="b2943-107">You can use a retention policy to retain chats and channel messages in Teams.</span></span> <span data-ttu-id="b2943-108">Teams のチャットは、チャットに含まれる各ユーザーのメールボックス内の隠しフォルダーに保存されます。また、Teams のチャネル メッセージは、チーム用のグループ メールボックス内の同様の隠しフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-108">Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> 

<span data-ttu-id="b2943-109">Azure を利用したチャット サービスでもこのデータが保存されますが、Teams でもこのサービスを使用していることを理解することが重要です。既定では、このサービスはデータを無期限に保存します。</span><span class="sxs-lookup"><span data-stu-id="b2943-109">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="b2943-110">このため、Teams のデータの保持および削除を行うには、Teams の場所を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2943-110">For this reason, we strongly recommend that you use the Teams locations to retain and delete Teams data.</span></span> <span data-ttu-id="b2943-111">Teams の場所を使用すると、Exchange メールボックスおよび基になる Azure を利用したチャット サービスの両方から完全にデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-111">Using the Teams locations will permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="b2943-112">詳細については、「[Microsoft Teams のセキュリティとコンプライアンス](https://go.microsoft.com/fwlink/?linkid=871258)」、特に「[情報保護アーキテクチャ](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2943-112">For more information, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="b2943-113">Teams のチャットとチャネル メッセージは、ユーザーまたはグループのメールボックスに対して構成されているアイテム保持ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b2943-113">Teams chats and channel messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="b2943-114">Teams のチャットとチャネル メッセージは Exchange に保存されますが、この Teams のデータは、**Teams のチャネル メッセージ**と **Teams のチャット**の場所に対して構成されているアイテム保持ポリシーによってのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2943-114">Even though Teams chats and channel messages are stored in Exchange, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="b2943-115">ユーザーが Teams データを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Teams のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-115">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="b2943-116">ユーザーのこの Teams のデータを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。</span><span class="sxs-lookup"><span data-stu-id="b2943-116">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="b2943-117">アイテム保持ポリシーがチャット メッセージとチャネル メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーが保持および削除、保持のみ、あるいは削除のみのどれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b2943-117">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="b2943-118">アイテム保持ポリシーが保持および削除の場合</span><span class="sxs-lookup"><span data-stu-id="b2943-118">When the retention policy is to retain and delete:</span></span>

![Teams チャットとチャネル メッセージの保持フローの図](../media/TeamsRetentionLifecycle.png)

1. <span data-ttu-id="b2943-120">保存期間中に**ユーザーがチャットまたはチャネル メッセージを変更または削除した場合**、メッセージは SubstrateHolds フォルダー (すべてのユーザーまたはグループ メールボックスの非表示フォルダー) に移動 (または編集の場合はコピー) され、 保持期間が終了するまで、このフォルダに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-120">**If a chat or channel message is modified or deleted** by the user during the retention period, the message is moved (or copied, in the case of edit) to the SubstrateHolds folder (which is a hidden folder in every user or group mailbox) and is stored in this folder until the retention period expires.</span></span> <span data-ttu-id="b2943-121">メッセージは保持期間が終了する日に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-121">Messages are permanently deleted on the day the retention period expires.</span></span>

2. <span data-ttu-id="b2943-122">保持期間中に**チャットまたはチャネル メッセージが削除されない場合**、メッセージは保持期間が切れた後 1 日以内に SubstrateHolds フォルダーに移動されます (0 から 24 時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="b2943-122">**If a chat or channel message isn't deleted** during the retention period, the message is moved to the SubstrateHolds folder within one day after the retention period expires (it takes from 0 to 24 hours).</span></span> <span data-ttu-id="b2943-123">メッセージは SubstrateHolds フォルダーに移動した 1 日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-123">The message is permanently deleted one day after it is moved to the SubstrateHolds folder.</span></span> 

> [!NOTE]
> <span data-ttu-id="b2943-124">SubstrateHolds フォルダー内のメッセージは、電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="b2943-124">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="b2943-125">メッセージが完全に削除された後は、電子情報開示検索で返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b2943-125">After a message is permanently deleted, it won't be returned in an eDiscovery search.</span></span>

<span data-ttu-id="b2943-126">アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。</span><span class="sxs-lookup"><span data-stu-id="b2943-126">When the retention policy is retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="b2943-127">アイテム保持ポリシーが保持のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="b2943-127">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="b2943-128">保持期間中に、**チャット メッセージまたはチャネル メッセージが変更または削除された場合**、元のメッセージのコピーが SubstrateHolds フォルダーに作成され、保持期間の終了まで保持されます。保持期間が終了すると、SubstrateHolds フォルダー内のコピーは、アイテムの有効期限が切れてから 1 日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-128">**If a chat or channel message is modified or deleted** during the retention period: A copy of the original message is created in the SubstrateHolds folder and retained until the end of the retention period, when the copy in the SubstrateHolds folder is permanently deleted one day after the item expires.</span></span> 

2. <span data-ttu-id="b2943-129">保持期間中に**アイテムが変更または削除されてない場合**、保持期間の前後には何も起こりません。メッセージは、元の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="b2943-129">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

#### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="b2943-130">アイテム保持ポリシーが削除のみのコンテンツ パス</span><span class="sxs-lookup"><span data-stu-id="b2943-130">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="b2943-131">保持期間中に**メッセージが削除されない場合**、保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-131">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> 

2. <span data-ttu-id="b2943-132">期間中にユーザーがアイテムを**削除した場合**、アイテムはすぐに SubstrateHolds フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-132">**If the item is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="b2943-133">ユーザーが SubstrateHolds フォルダーからメッセージを削除するかフォルダーを空にすると、そのアイテムは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-133">If a user deletes the message from there or empties the SubstrateHolds folder, the item is permanently deleted.</span></span> <span data-ttu-id="b2943-134">それ以外の場合、メッセージは SubstrateHolds フォルダーに移動した 1 日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-134">Otherwise, the message is permanently deleted one day after being in the SubstrateHolds folder.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="b2943-135">Skype for Business および Teams の相互運用チャット</span><span class="sxs-lookup"><span data-stu-id="b2943-135">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="b2943-136">Skype for Business と Teams の相互運用チャットでも、処理のフローは同じです。</span><span class="sxs-lookup"><span data-stu-id="b2943-136">The same flow works for Skype for Business and Teams interop chats.</span></span> <span data-ttu-id="b2943-137">Skype for Business のチャットが Teams に届くと、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="b2943-137">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="b2943-138">Teams のアイテム保持ポリシーは、これらのメッセージを Teams のスレッドから削除します。</span><span class="sxs-lookup"><span data-stu-id="b2943-138">Teams retention policies will delete these messages from the Teams thread.</span></span> 

<span data-ttu-id="b2943-139">ただし、Skype for Business に対して会話履歴がオンになっていて、Skype for Business のクライアント側からその履歴がメールボックスに保存されている場合、このチャット データは Teams のアイテム保持ポリシーでは処理されません。</span><span class="sxs-lookup"><span data-stu-id="b2943-139">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

## <a name="files-in-teams"></a><span data-ttu-id="b2943-140">Teams のファイル</span><span class="sxs-lookup"><span data-stu-id="b2943-140">Files in Teams</span></span>

<span data-ttu-id="b2943-141">Teams では、チャット内で共有されるファイルは、ファイルを共有したユーザーの OneDrive アカウントに保存されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-141">In Teams, files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> <span data-ttu-id="b2943-142">チャネルにアップロードされたファイルは、チームの SharePoint 内に保存されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-142">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span> <span data-ttu-id="b2943-143">つまり、Teams でファイルを保持または削除するには、Teams 用に構成したアイテム保持ポリシーに加えて、**OneDrive アカウント**と **SharePoint サイト**に適用される 1 つ以上のアイテム保持ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-143">This means that to retain or delete files in Teams, you must configure one or more retention policies that apply to **OneDrive accounts** and **SharePoint sites** in addition to any retention policies you configure for Teams.</span></span> <span data-ttu-id="b2943-144">これらの場所でのアイテム保持ポリシーの機能の詳細については、「[SharePoint と OneDrive のアイテム保持ポリシーの詳細](retention-policies-sharepoint.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2943-144">For more information about how retention policies work for these locations, see [Learn about retention policies for SharePoint and OneDrive](retention-policies-sharepoint.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b2943-145">Teams のチャネル メッセージまたは Teams のチャットを含むアイテム保持ポリシーには、Teams の場所のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b2943-145">A retention policy that includes Teams channel messages or Teams chats can only include Teams locations.</span></span> <span data-ttu-id="b2943-146">したがって、Teams でこれらのファイルを保持または削除するには、個別のアイテム保持ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-146">So to retain or delete these files in Teams, you must create a separate retention policy.</span></span>
> 
> <span data-ttu-id="b2943-147">特定のチームのみのファイルにアイテム保持ポリシーを適用する場合は、チーム用の SharePoint サイトおよびチーム内のユーザーの OneDrive アカウントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2943-147">If you want to apply a retention policy to the files of just a specific team, you can choose the SharePoint site for the Team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="b2943-148">SharePoint や OneDrive に適用されているアイテム保持ポリシーにより、Teams のチャットやチャネル メッセージで参照されているファイルが、それらのメッセージが削除されるよりも先に削除される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-148">It's possible that a retention policy that's applied to SharePoint or OneDrive could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="b2943-149">このような場合、そのファイルは Teams のメッセージに依然として表示されてはいますが、ユーザーがファイルをクリックすると、"ファイルが見つかりません" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-149">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="b2943-150">この動作はアイテム保持ポリシーに固有のものではなく、ユーザーが SharePoint または OneDrive から手動でファイルを削除した場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-150">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="b2943-151">会議と外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="b2943-151">Meetings and external users</span></span>

<span data-ttu-id="b2943-152">チャネル会議メッセージはチャネル メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャネル メッセージ**の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2943-152">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="b2943-153">一時的な会議メッセージはグループ チャット メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャット**の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2943-153">Impromptu meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="b2943-154">組織が主催する会議に外部ユーザーが含まれる場合:</span><span class="sxs-lookup"><span data-stu-id="b2943-154">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="b2943-155">外部ユーザーがテナントのゲスト アカウントを使用して参加する場合、このユーザーには、組織の Teams のアイテム保持ポリシーの対象となるシャドウ メールボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="b2943-155">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="b2943-156">会議からのメッセージはすべて、ユーザーのメールボックスとシャドウ メールボックスの両方に保存されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-156">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="b2943-157">外部ユーザーが別の Microsoft 365 組織のアカウントを使用して参加した場合、そのユーザーのメッセージは別のテナントのメールボックスに保存されるため、削除できません。</span><span class="sxs-lookup"><span data-stu-id="b2943-157">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="b2943-158">ただし、同じ会議の場合、アイテム保持ポリシーによりユーザーのメッセージが削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-158">For the same meeting however, your retention policies can delete messages for your users.</span></span>


## <a name="limitations"></a><span data-ttu-id="b2943-159">制限事項</span><span class="sxs-lookup"><span data-stu-id="b2943-159">Limitations</span></span>

<span data-ttu-id="b2943-160">Teams の保持機能の最適化に継続的に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="b2943-160">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="b2943-161">それまでの間、注意すべき制限事項がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b2943-161">In the meantime, here are a few limitations to be aware of:</span></span>
  
- <span data-ttu-id="b2943-162">**Teams には、個別のアイテム保持ポリシーが必要です**。</span><span class="sxs-lookup"><span data-stu-id="b2943-162">**Teams requires a separate retention policy**.</span></span> <span data-ttu-id="b2943-163">アイテム保持ポリシーを作成して、Teams の場所をオンに切り替えると、その他のすべての場所がオフに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="b2943-163">When you create a retention policy and toggle on the Teams locations, all other locations toggle off.</span></span> <span data-ttu-id="b2943-164">Teams を含むアイテム保持ポリシーには、Teams のみを含めることが可能で、他の場所は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b2943-164">A retention policy that includes Teams can include only Teams and no other locations.</span></span> 
    
- <span data-ttu-id="b2943-165">**Teams は組織全体のポリシーに含まれていません**。</span><span class="sxs-lookup"><span data-stu-id="b2943-165">**Teams isn't included in an org-wide policy**.</span></span> <span data-ttu-id="b2943-166">組織全体のポリシーを作成する場合、Teams は別のアイテム保持ポリシーを必要とするため、含まれません。</span><span class="sxs-lookup"><span data-stu-id="b2943-166">If you create an org-wide policy, Teams isn't included because it requires a separate retention policy.</span></span> 
    
- <span data-ttu-id="b2943-167">**Teams は高度なアイテム保持をサポートしていません**。</span><span class="sxs-lookup"><span data-stu-id="b2943-167">**Teams doesn't support advanced retention**.</span></span> <span data-ttu-id="b2943-168">アイテム保持ポリシーを作成するときに、[[特定の条件を満たすコンテンツを特定するための高度な設定](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)] を選択した場合、Teams の場所は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b2943-168">When you create a retention policy, if you choose the [Advanced settings to identify content that meets specific conditions](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), the Teams locations are not available.</span></span> <span data-ttu-id="b2943-169">現在、Teams の保持は、それらの場所を選択すると、すべてのチャットおよびチャネル メッセージ コンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-169">Currently, retention in Teams applies to all the chat and channel message content when you select those locations.</span></span> 

- <span data-ttu-id="b2943-170">**Teams のチャネル メッセージのアイテム保持ポリシーを構成する場合、プライベート チャネルの Teams メッセージは含まれません**。</span><span class="sxs-lookup"><span data-stu-id="b2943-170">**Teams messages in private channels aren't included when you configure a retention policy for Teams channel messages**.</span></span> <span data-ttu-id="b2943-171">代わりに、プライベート チャネルからのメッセージは、**Teams チャット** オプションを使用したグループ チャットとしてユーザーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2943-171">Instead, messages from private channels are included for the users as group chats with the **Teams chats** option.</span></span> 
    
- <span data-ttu-id="b2943-172">**Teams は、期限切れのメッセージをクリーンアップするために最大 3 日を要する場合があります**。</span><span class="sxs-lookup"><span data-stu-id="b2943-172">**Teams may take up to three days to clean up expired messages**.</span></span> <span data-ttu-id="b2943-173">Teams に適用されるアイテム保持ポリシーは、保持期間が終了するとチャットとチャネル メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="b2943-173">A retention policy applied to Teams will delete chat and channel messages when the retention period expires.</span></span> <span data-ttu-id="b2943-174">ただし、これらのメッセージをクリーンアップして完全に削除するには、最大 3 日を要する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-174">However, it may take up to three days to clean up these messages and permanently delete them.</span></span> <span data-ttu-id="b2943-175">またチャットおよびチャネル メッセージは、保持期間が終了しメッセージが完全に削除されたときに電子情報開示ツールで検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b2943-175">Also, chat and channel messages will be searchable with eDiscovery tools during the time after the retention period expires and when messages are permanently deleted.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="b2943-176">以前は、アイテム保持ポリシーでは作成から 30 日未満の Teams コンテンツを削除できませんでしたが、この制限は削除されました。</span><span class="sxs-lookup"><span data-stu-id="b2943-176">It used to be true that a retention policy couldn't delete Teams content that's less than 30 days old, but we've removed this limitation.</span></span> <span data-ttu-id="b2943-177">Teams コンテンツの保持期間は、選択した任意の日数で、最短 1 日から設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b2943-177">Now the retention period for Teams content can be any number of days you choose and as short as one day.</span></span> <span data-ttu-id="b2943-178">保持期間が 1 日の場合、保持期間が終了してからメッセージが完全に削除されるまでに最大 3 日を要します。</span><span class="sxs-lookup"><span data-stu-id="b2943-178">If you do have a retention period of one day, it will take up to three days after the retention period expires before messages are permanently deleted.</span></span>

- <span data-ttu-id="b2943-179">**Outlook での誤った表示の問題**。</span><span class="sxs-lookup"><span data-stu-id="b2943-179">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="b2943-180">Skype または Teams の場所用にアイテム保持ポリシーを作成する場合、ユーザーが Outlook デスクトップ クライアントでメールボックス フォルダーのプロパティを表示すると、これらのポリシーの 1 つが既定のフォルダーポリシーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2943-180">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="b2943-181">これは、Outlook の誤表示の問題であり、[既知の問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)です。</span><span class="sxs-lookup"><span data-stu-id="b2943-181">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="b2943-182">既定のフォルダー ポリシーとして表示されるのは、フォルダーに適用されるメールボックス保持ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b2943-182">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="b2943-183">Skype または Teams の保持ポリシーは、ユーザーのメールボックスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b2943-183">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="b2943-184">**構成の問題**:</span><span class="sxs-lookup"><span data-stu-id="b2943-184">**Configuration issues**:</span></span> 
    - <span data-ttu-id="b2943-185">**[Teams のチャネル メッセージ]** の場所にある **[チームの選択]** を選択した場合、チームではない Office 365 グループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-185">When you select **Choose teams** for the **Teams channel messages** location, you might see Office 365 groups that aren't also teams.</span></span> <span data-ttu-id="b2943-186">これらのグループは選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b2943-186">Don't select these groups.</span></span>
    
    - <span data-ttu-id="b2943-187">**[Teams のチャット]** の場所にある **[ユーザーの選択]** を選択した場合、ゲストや、メールボックスのユーザーではないユーザーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2943-187">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="b2943-188">アイテム保持ポリシーはこれらのユーザー向けに設計されていないため、選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b2943-188">Retention policies aren't designed for these users, so don't select them.</span></span>


## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a><span data-ttu-id="b2943-189">Microsoft Teams のアイテム保持ポリシーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b2943-189">How to configure a retention policy for Microsoft Teams</span></span>

<span data-ttu-id="b2943-190">「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2943-190">See [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="b2943-191">ウィザードの [**場所の選択**] ページで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2943-191">For the **Choose locations** page of the wizard, select the following options:</span></span>

- <span data-ttu-id="b2943-192">[**特定の場所を選択**] > [**Teams のチャネル メッセージ**] と [**Teams のチャット**]</span><span class="sxs-lookup"><span data-stu-id="b2943-192">**Let me choose specific locations** > **Teams channel messages** and **Teams chats**</span></span>

<span data-ttu-id="b2943-193">Teams に適用されるアイテム保持ポリシーでは、規制上の理由で必要になる可能性がある [[保持ロック](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2943-193">A retention policy that applies to Teams can use [Preservation Lock](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements), which might be required for regulatory reasons.</span></span>

## <a name="related-information"></a><span data-ttu-id="b2943-194">関連情報</span><span class="sxs-lookup"><span data-stu-id="b2943-194">Related information</span></span>

[<span data-ttu-id="b2943-195">Microsoft Teams の保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="b2943-195">Retention policies in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/retention-policies)