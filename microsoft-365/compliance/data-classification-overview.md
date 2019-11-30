---
title: データ分類の使用を開始する (プレビュー)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: データ分類ダッシュボードを使用すると、組織内で検出、分類された機密データの量を確認できます。
ms.openlocfilehash: cb728c4e6a88fc7bb47716a40addd01f9828208f
ms.sourcegitcommit: 9206e7f2d61b5ba7f788fe5e7f75a2218c12c716
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "39622619"
---
# <a name="data-classification-overview-preview"></a><span data-ttu-id="995d5-103">データ分類の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="995d5-103">Data classification overview (preview)</span></span>

<span data-ttu-id="995d5-104">Microsoft 365 の管理者またはコンプライアンス管理者は、組織内のコンテンツを評価してタグ付けすることにより、コンテンツの保存場所を制御し、保存場所に関わらずコンテンツを保護でき、また、組織のニーズに合わせてコンテンツを保持および削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="995d5-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="995d5-105">これらは、[秘密ラベル](sensitivity-labels.md)、[保持ラベル](labels.md)、および機密情報の種類の分類を適用することにより行います。</span><span class="sxs-lookup"><span data-stu-id="995d5-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="995d5-106">検出、評価、タグ付けを行うにはさまざまな方法がありますが、最終的には、これらのラベルの一方または両方を使用してタグ付けおよび分類された大量のドキュメントとメールが生み出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="995d5-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large numbers of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="995d5-107">保持ラベルと機密ラベルを適用した後は、テナント全体でラベルがどのように使用されているか、これらのアイテムに対してどのような操作が行われているかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="995d5-107">After you apply  your retention labels and sensitivity labels, you’ll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="995d5-108">こうした内容は、データ分類のページで確認できます。具体的には次の内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="995d5-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="995d5-109">機密情報の種類として分類されたアイテムの数およびこれらの分類の種類</span><span class="sxs-lookup"><span data-stu-id="995d5-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="995d5-110">Microsoft 365 および Azure Information Protection の両方で最も多く適用されている機密ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="995d5-111">最も多く適用されている保持ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-111">the top applied retention labels</span></span>
- <span data-ttu-id="995d5-112">機密コンテンツに対してユーザーが行っているアクティビティの概要</span><span class="sxs-lookup"><span data-stu-id="995d5-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="995d5-113">機密データおよび保持されたデータの保存場所</span><span class="sxs-lookup"><span data-stu-id="995d5-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="995d5-114">データ分類は、**Microsoft 365 コンプライアンス センター**または **Microsoft 365 セキュリティ センター**  >  [**分類**]  >  [**データ分類**] で確認できます。</span><span class="sxs-lookup"><span data-stu-id="995d5-114">You can find label analytics in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Label analytics**.</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="995d5-115">コンテンツで最も多く使用されている機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="995d5-115">Sensitive information types used most in your content</span></span>

<span data-ttu-id="995d5-116">Microsoft 365 では、社会保障番号を含むアイテムやクレジットカード番号を含むアイテムなど、機密情報の種類の定義が多数提供されています。</span><span class="sxs-lookup"><span data-stu-id="995d5-116">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="995d5-117">機密情報の種類の詳細については、「[機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-117">For more information on sensitive information types, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="995d5-118">機密情報の種類カードには、組織全体で検出されたラベル付けされている機密情報の種類のうち上位のものが示されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-118">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![上位の機密情報の種類](media/data-classification-sens-info-types-card.png)

<span data-ttu-id="995d5-120">特定の分類カテゴリに含まれるアイテムの数を確認するには、そのカテゴリのバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="995d5-120">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![上位の機密情報の種類をポイントした際の詳細情報](media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="995d5-122">"No data found with sensitive information" (機密情報が含まれるデータが見つかりませんでした) というメッセージがカードに表示される場合、</span><span class="sxs-lookup"><span data-stu-id="995d5-122">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="995d5-123">機密情報の種類として分類されているアイテムが組織に存在しないか、クロールされたアイテムが存在しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="995d5-123">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="995d5-124">ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-124">To get started with TypeScript, see the following resources:</span></span>
>- [<span data-ttu-id="995d5-125">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-125">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="995d5-126">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-126">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="995d5-127">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="995d5-127">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="995d5-128">コンテンツに適用されている上位の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-128">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="995d5-129">Microsoft 365 または Azure Information Protection (AIP) のいずれかでアイテムに機密ラベルを適用すると、次の 2 つのことが起こります。</span><span class="sxs-lookup"><span data-stu-id="995d5-129">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="995d5-130">組織にとってのアイテムの価値を示すタグがドキュメントに埋め込まれ、そのタグはドキュメントとともにどこにでも移動します。</span><span class="sxs-lookup"><span data-stu-id="995d5-130">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="995d5-131">タグが含まれることで、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-131">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="995d5-132">エンド ポイントの保護を有効にすると、アイテムを組織の制御から離れさせないようにもできます。</span><span class="sxs-lookup"><span data-stu-id="995d5-132">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="995d5-133">機密ラベルの詳細については、「[機密ラベルの概要](sensitivity-labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-133">For more information, see [Overview of sensitivity labels](sensitivity-labels.md).</span></span>

<span data-ttu-id="995d5-134">機密ラベル カードには、機密レベルごとのアイテム (メールやドキュメント) の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-134">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![機密ラベルの分類別のコンテンツの内訳用プレースホルダーのスクリーンショット](media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="995d5-136">機密ラベルをまだ作成または発行していない場合、または、いずれのコンテンツにも機密ラベルが適用されていない場合、"No sensitivity labels detected" (機密ラベルが検出されませんでした) というメッセージがこのカードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-136">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="995d5-137">ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-137">To get started with TypeScript, see the following resources:</span></span>
>- <span data-ttu-id="995d5-138">「[機密ラベル](sensitivity-labels.md)」または、AIPについては「[Azure Information Protection ポリシーを構成する](https://docs.microsoft.com/azure/information-protection/configure-policy)」</span><span class="sxs-lookup"><span data-stu-id="995d5-138">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="995d5-139">コンテンツに適用されている上位の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-139">Top retention labels applied to content</span></span>

<span data-ttu-id="995d5-140">保持ラベルは、組織内のコンテンツの廃棄を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-140">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="995d5-141">適用された保持ラベルは、ドキュメントが削除されるまでの期間、削除前に確認を必要とするかどうか、保持期間の有効期限、または削除できないよう記録としてマークするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="995d5-141">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="995d5-142">詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-142">For more information about labels, see [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="995d5-143">最も多く適用されている保持ラベルのカードには、特定の保持ラベルが付けられているアイテムの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-143">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![最も多く適用されている保持ラベル用プレースホルダーのスクリーンショット](media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="995d5-145">"No retention labels detected" (保持ラベルが検出されませんでした) というメッセージがカードに表示される場合、保持ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="995d5-145">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="995d5-146">保持ラベルの使用を開始するには、</span><span class="sxs-lookup"><span data-stu-id="995d5-146">To get started with retention labels, see:</span></span>
>- <span data-ttu-id="995d5-147">「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-147">[Overview of retention labels](labels.md)</span></span>

## <a name="top-activities-detected"></a><span data-ttu-id="995d5-148">検出された上位アクティビティ</span><span class="sxs-lookup"><span data-stu-id="995d5-148">Top activities detected</span></span>

<span data-ttu-id="995d5-149">このカードでは、機密ラベルが付けられたアイテムに対してユーザーが行う最も一般的な操作の概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-149">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="995d5-150">[アクティビティ エクスプローラー](data-classification-activity-explorer.md)を使用すると、ラベル付きコンテンツおよび Windows 10 のエンドポイントにあるコンテンツでの、Microsoft 365 により追跡される 8 つの異なるアクティビティの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="995d5-150">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="995d5-151">"No activity detected" (アクティビティが検出されませんでした) というメッセージがこのカードに表示される場合、ファイルに対して行われたアクティビティがなかったか、ユーザーまたは管理者による監査が有効化されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="995d5-151">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="995d5-152">監査ログをオンにするには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-152">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="995d5-153">セキュリティ/コンプライアンス センターで監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="995d5-153">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="995d5-154">場所別の機密ラベルおよび保持ラベル付きデータ</span><span class="sxs-lookup"><span data-stu-id="995d5-154">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="995d5-155">データ分類の報告の目的は、どのラベルが付いているアイテムがどこにいくつあるかを確認できるようにすることにあります。</span><span class="sxs-lookup"><span data-stu-id="995d5-155">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="995d5-156">これらのカードでは、Exchange、SharePoint、OneDrive などにあるラベル付きのアイテムの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="995d5-156">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="995d5-157">"No locations detected" (場所が検出されませんでした) というメッセージがこのカードに表示される場合、機密ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="995d5-157">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="995d5-158">機密ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="995d5-158">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="995d5-159">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-159">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="995d5-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="995d5-160">See also</span></span>

- [<span data-ttu-id="995d5-161">ラベル アクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="995d5-161">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="995d5-162">ラベル付きコンテンツの表示 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="995d5-162">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="995d5-163">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-163">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="995d5-164">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="995d5-164">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="995d5-165">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="995d5-165">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="995d5-166">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="995d5-166">Overview of retention policies</span></span>](retention-policies.md)