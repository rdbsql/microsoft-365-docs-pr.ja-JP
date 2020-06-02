---
title: 保持ラベルを作成、発行、および自動適用する
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
description: 必要なものを保持し、不要なものを削除し、Office 365 環境でアイテムをレコードとして宣言するための、保持ラベルの作成、発行、および自動適用の手順。
ms.openlocfilehash: 65319baa0fd238ebdc403307fb8bb91a59d87cd6
ms.sourcegitcommit: 3cd487476efe4138d1b42499fbffbbe4bacfe5b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "44408469"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="c6d5c-103">保持ラベルを作成、発行、および自動適用する</span><span class="sxs-lookup"><span data-stu-id="c6d5c-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="c6d5c-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="c6d5c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c6d5c-105">次の情報を使用して、[保持ラベル](labels.md)を作成し、ドキュメントやメールに自動的に適用するか、ユーザーが手動で適用できるように公開します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="c6d5c-106">保持ラベルは、必要なものを保持し、不要なものを削除するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="c6d5c-107">また、Microsoft 365 データの[レコード管理](records-management.md)ソリューションの一部として、アイテムをレコードとして宣言するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="c6d5c-108">保持ラベルを作成して構成する場所は、レコード管理を使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="c6d5c-109">手順は両方のシナリオに提供されます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c6d5c-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="c6d5c-110">Before you begin</span></span>

<span data-ttu-id="c6d5c-111">保持ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ &amp; コンプライアンス センターにアクセスする許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c6d5c-112">テナント管理者は、規定でこの場所にアクセスできるため、法令遵守責任者や他のユーザーにセキュリティ &amp; コンプライアンス センターへのアクセス権を付与できます。テナント管理者が持つすべてのアクセス許可を付与する必要はありません。これを行うには、セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページに移動して、[**コンプライアンス管理者**] 役割グループを編集し、その役割グループにメンバーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="c6d5c-113">詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="c6d5c-p104">これらのアクセス許可は、保持ラベルとラベル ポリシーを作成して適用するときにのみ必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="c6d5c-116">保持ラベルを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="c6d5c-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="c6d5c-117">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c6d5c-118">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-118">If you are using records management:</span></span>
        - <span data-ttu-id="c6d5c-119">[**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]</span><span class="sxs-lookup"><span data-stu-id="c6d5c-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="c6d5c-120">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-120">If you are not using records management:</span></span>
       - <span data-ttu-id="c6d5c-121">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]</span><span class="sxs-lookup"><span data-stu-id="c6d5c-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="c6d5c-122">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="c6d5c-122">Don't immediately see your option?</span></span> <span data-ttu-id="c6d5c-123">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="c6d5c-124">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="c6d5c-125">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="c6d5c-126">ファイル計画記述子については、「[ファイル計画マネージャーの概要](file-plan-manager.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="c6d5c-127">保持ラベルを使用してコンテンツをレコードとして宣言するには、[**このラベルを使用して、コンテンツを「レコード」に分類する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="c6d5c-128">さらにラベルを作成するには、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="c6d5c-129">既存のラベルを編集するには、目的のラベルを選択し、[**ラベルの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="c6d5c-130">これにより同じウィザードが起動し、手順 2 でラベルの説明と設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="c6d5c-131">保持ラベル ポリシーを作成して保持ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="c6d5c-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="c6d5c-132">保持ラベルを発行して、ユーザーが手動で適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="c6d5c-133">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c6d5c-134">レコード管理を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-134">If you are using records management:</span></span>
        - <span data-ttu-id="c6d5c-135">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**ラベルの発行**]</span><span class="sxs-lookup"><span data-stu-id="c6d5c-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="c6d5c-136">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-136">If you are not using records management:</span></span>
        - <span data-ttu-id="c6d5c-137">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**ラベルの発行**]</span><span class="sxs-lookup"><span data-stu-id="c6d5c-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="c6d5c-138">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="c6d5c-138">Don't immediately see your option?</span></span> <span data-ttu-id="c6d5c-139">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="c6d5c-140">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="c6d5c-141">保持ラベルでサポートされている場所については、「[保持ラベルと場所](labels.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="c6d5c-142">自動適用の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="c6d5c-142">Auto-apply a retention label</span></span>

<span data-ttu-id="c6d5c-143">指定した条件に基づいて、保持ラベルを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="c6d5c-144">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c6d5c-145">レコード管理を使用している場合: **情報ガバナンス**:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="c6d5c-146">[**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="c6d5c-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="c6d5c-147">レコード管理を使用していない場合:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-147">If you are not using records management:</span></span>
        - <span data-ttu-id="c6d5c-148">[**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]</span><span class="sxs-lookup"><span data-stu-id="c6d5c-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="c6d5c-149">すぐにオプションが表示されませんか?</span><span class="sxs-lookup"><span data-stu-id="c6d5c-149">Don't immediately see your option?</span></span> <span data-ttu-id="c6d5c-150">最初に [**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="c6d5c-151">ウィザードでプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="c6d5c-152">保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="c6d5c-153">保持ラベルでサポートされている場所については、「[保持ラベルと場所](labels.md#retention-label-policies-and-locations)」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-153">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="c6d5c-154">自動適用の保持ラベルの条件の構成</span><span class="sxs-lookup"><span data-stu-id="c6d5c-154">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="c6d5c-155">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-155">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="c6d5c-156">特定の種類の機密情報</span><span class="sxs-lookup"><span data-stu-id="c6d5c-156">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="c6d5c-157">作成したクエリに一致する特定のキーワード</span><span class="sxs-lookup"><span data-stu-id="c6d5c-157">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="c6d5c-158">トレーニング可能な分類子の一致</span><span class="sxs-lookup"><span data-stu-id="c6d5c-158">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動適用ラベルの [条件選択] ページ](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="c6d5c-160">構成した条件に一致するすべてのコンテンツに保持ラベルを自動的に適用するには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-160">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="c6d5c-161">特定の種類の機密情報によるコンテンツへのラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="c6d5c-161">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="c6d5c-162">機密情報用に自動適用の保持ラベルを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-162">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="c6d5c-163">各ポリシー テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-163">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="c6d5c-164">たとえば、次に示すテンプレートは、米国の ITIN、SSN、パスポート番号を探します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-164">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="c6d5c-165">DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-165">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="c6d5c-p111">ポリシー テンプレートを選択すると、すべての種類の機密情報を追加または削除したり、インスタンス数と一致精度を変更したりできます。ここに示す例では、保持ラベルは次の場合にのみ自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p111">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="c6d5c-p112">コンテンツに、次の 3 種類の機密情報のいずれかに 1 から 9 個のインスタンスが含まれる場合。**最大** 値を削除して、**任意** の値に変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p112">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="c6d5c-p113">検出された機密情報の種類は、一致精度 (または信頼レベル) が少なくとも 75 に設定されています。多くの機密情報の種類は複数のパターンで定義されています。一致精度の高いパターンでは、より多くの証拠 (キーワード、日付、アドレスなど) が検索される必要がありますが、一致精度の低いパターンでは必要な証拠は少なくなります。簡単に言えば、一致精度の **最小** 値が低いほど、コンテンツは条件に一致しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p113">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="c6d5c-174">これらのオプションの詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-174">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="c6d5c-176">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="c6d5c-176">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="c6d5c-p114">特定の条件を満たすコンテンツにラベルを自動的に適用できます。現在利用可能な条件では、特定の単語、フレーズ、または検索可能なプロパティの値を含むコンテンツへのラベルの適用がサポートされています。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p114">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="c6d5c-180">クエリ構文の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-180">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="c6d5c-181">キーワード クエリ言語 (KQL) 構文のリファレンス</span><span class="sxs-lookup"><span data-stu-id="c6d5c-181">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="c6d5c-p115">クエリ ベースのラベルは検索インデックスを使用してコンテンツを特定します。有効な検索可能なプロパティの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p115">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="c6d5c-184">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="c6d5c-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="c6d5c-185">クロールされたプロパティと管理プロパティの概要 (SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="c6d5c-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="c6d5c-186">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-186">Examples queries:</span></span>

- <span data-ttu-id="c6d5c-187">Exchange</span><span class="sxs-lookup"><span data-stu-id="c6d5c-187">Exchange</span></span>
    - <span data-ttu-id="c6d5c-188">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="c6d5c-188">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="c6d5c-189">受信者: garthf</span><span class="sxs-lookup"><span data-stu-id="c6d5c-189">recipients:garthf</span></span><!--nolink--><span data-ttu-id="c6d5c-190">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6d5c-190">@contoso.com</span></span>
- <span data-ttu-id="c6d5c-191">SharePoint および OneDrive</span><span class="sxs-lookup"><span data-stu-id="c6d5c-191">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="c6d5c-192">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="c6d5c-192">contenttype:contract</span></span>
    - <span data-ttu-id="c6d5c-193">site:https</span><span class="sxs-lookup"><span data-stu-id="c6d5c-193">site:https</span></span><!--nolink--><span data-ttu-id="c6d5c-194">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="c6d5c-194">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![クエリ エディター](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="c6d5c-196">トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="c6d5c-196">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="c6d5c-197">トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-197">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="c6d5c-198">組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および**脅威**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-198">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

<span data-ttu-id="c6d5c-200">このオプションを使用してラベルを自動的に適用するには、SharePoint Online サイトとメールボックスには少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-200">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="c6d5c-201">トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-201">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="c6d5c-202">構成の例については、「[組み込みの分類子を準備して使用する方法](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-202">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="c6d5c-203">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="c6d5c-203">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="c6d5c-204">保持ラベルを発行または自動適用しても、すぐには有効になりません。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-204">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="c6d5c-205">まず、ラベル ポリシーを管理センターからポリシー内の場所に同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-205">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="c6d5c-206">また、発行された保持ラベルをエンド ユーザーが利用したり、ラベルをコンテンツに自動適用したりできるようになるまでには、場所で時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-206">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="c6d5c-207">これにかかる時間は、場所と保持ラベルの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-207">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="c6d5c-208">発行された保持ラベル</span><span class="sxs-lookup"><span data-stu-id="c6d5c-208">Published retention labels</span></span>

<span data-ttu-id="c6d5c-p118">SharePoint または OneDrive に保持ラベルを発行する場合、保持ラベルがエンド ユーザーに表示されるまでに 1 日かかる場合があります。また、Exchange に保持ラベルを発行する場合は、保持ラベルがエンド ユーザーに表示するまでに 7 日間かかる場合があり、さらにメールボックスには少なくとも 10 MB のデータが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-p118">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![手動ラベルが有効になるタイミングの図](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="c6d5c-212">自動適用の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="c6d5c-212">Auto-apply retention labels</span></span>

<span data-ttu-id="c6d5c-213">特定の条件に一致するコンテンツに保持ラベルを自動適用する場合、条件に一致するすべての既存コンテンツに保持ラベルが適用されるまでに 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-213">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="c6d5c-215">Exchange に発行された保持ラベルの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c6d5c-215">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="c6d5c-216">Exchange Online では、7 日ごとにプロセスが実行され、保持ラベルがエンド ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-216">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="c6d5c-217">PowerShell を使用することで、このプロセスが最後に実行された日時を確認できるため、いつ実行されるかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-217">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="c6d5c-218">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-218">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="c6d5c-219">これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-219">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="c6d5c-220">結果の中で、`ELCLastSuccessTimeStamp` (UTC) プロパティは、システムがメールボックスを最後に処理した日時を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-220">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="c6d5c-221">ポリシーの作成後に処理がまだ行われていない場合は、ラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-221">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="c6d5c-222">処理を強制的に行うには、`Start-ManagedFolderAssistant -Identity <user>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-222">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="c6d5c-223">Outlook on the web にラベルが表示されると思われるにもかかわらず、ラベルが表示されない場合は、ブラウザーのキャッシュを必ず消去してください (CTRL + F5)。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-223">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="c6d5c-224">保持ラベルとそのポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="c6d5c-224">Updating retention labels and their policies</span></span>

<span data-ttu-id="c6d5c-225">保持ラベル、保持ラベル ポリシー、または自動適用ポリシーを編集し、保持ラベルが既にコンテンツに適用されている場合、更新された設定は、新しくラベル付けされたコンテンツに加えて、このコンテンツに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c6d5c-225">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="c6d5c-226">保持ラベルの PowerShell コマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="c6d5c-226">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="c6d5c-227">保持ラベルのコマンドレットを使用するには:</span><span class="sxs-lookup"><span data-stu-id="c6d5c-227">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="c6d5c-228">Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="c6d5c-228">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="c6d5c-229">以下の Office 365 セキュリティ センターとコンプライアンス センターのコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="c6d5c-229">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="c6d5c-230">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="c6d5c-230">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="c6d5c-231">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="c6d5c-231">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="c6d5c-232">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="c6d5c-232">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="c6d5c-233">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="c6d5c-233">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="c6d5c-234">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="c6d5c-234">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="c6d5c-235">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="c6d5c-235">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="c6d5c-236">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c6d5c-236">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c6d5c-237">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c6d5c-237">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c6d5c-238">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c6d5c-238">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c6d5c-239">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c6d5c-239">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c6d5c-240">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c6d5c-240">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="c6d5c-241">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c6d5c-241">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="c6d5c-242">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c6d5c-242">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="c6d5c-243">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c6d5c-243">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)