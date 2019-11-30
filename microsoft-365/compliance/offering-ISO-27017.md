---
title: ISO/IEC 27017:2015 情報セキュリティ コントロールの実施基準
description: Microsoft クラウド サービスでは、情報セキュリティ コントロールに関するこの実施基準が採用されています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 6002637496cfa01bc7b14ad29069493e45142c33
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "39625319"
---
# <a name="compliance-offering-isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="aeea1-104">コンプライアンス サービス: ISO/IEC 27017:2015 情報セキュリティ コントロールの実施基準</span><span class="sxs-lookup"><span data-stu-id="aeea1-104">Compliance offering: ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="aeea1-105">ISO-IEC 27017 の概要</span><span class="sxs-lookup"><span data-stu-id="aeea1-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="aeea1-106">ISO/IEC 27017:2015 実施基準は、組織が ISO/IEC 27002:2013 に基づいてクラウド コンピューティング情報セキュリティ管理システムを実装するときにクラウド サービス情報セキュリティ コントロールを選択するためのリファレンスとして使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="aeea1-107">また、クラウド サービス プロバイダーが、一般に受け入れられている保護コントロールを実装するためのガイダンス資料としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="aeea1-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="aeea1-108">この国際的な基準は、ISO/IEC 27002 に基づくクラウド特有の実装ガイダンスも提供されています。さらに、ISO/IEC 27002: 2013 の 5 項から 18 項で示されるコントロール、実装ガイダンスおよび各種情報に対するクラウド特有の情報セキュリティの脅威とリスクに対応するための追加コントロールも示されています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="aeea1-109">具体的にはこの基準では ISO/IEC 27002 の 37 のコントロールに関するガイダンスを提供すると同時に、ISO/IEC 27002 では取り上げられていない 7 つの新しいコントロールにも言及しています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="aeea1-110">これらの新しいコントロールは、次の重要な分野に対応しています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="aeea1-111">クラウド コンピューティング環境で共有される役割と責任</span><span class="sxs-lookup"><span data-stu-id="aeea1-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="aeea1-112">契約終了時におけるクラウド サービスのお客様の資産の削除と返却</span><span class="sxs-lookup"><span data-stu-id="aeea1-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="aeea1-113">お客様の仮想環境を他お客様の仮想環境から保護および分離すること</span><span class="sxs-lookup"><span data-stu-id="aeea1-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="aeea1-114">ビジネス ニーズに応じた仮想マシンの要塞化要件</span><span class="sxs-lookup"><span data-stu-id="aeea1-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="aeea1-115">クラウド コンピューティング環境の管理運用の手順</span><span class="sxs-lookup"><span data-stu-id="aeea1-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="aeea1-116">クラウド コンピューティング環境内の関連アクティビティに対する監視手段の提供</span><span class="sxs-lookup"><span data-stu-id="aeea1-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="aeea1-117">仮想ネットワークと物理ネットワークのセキュリティ管理の連携</span><span class="sxs-lookup"><span data-stu-id="aeea1-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="aeea1-118">Microsoft と ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="aeea1-118">Microsoft and ISO/IEC 27001</span></span>

<span data-ttu-id="aeea1-119">ISO/IEC 27017 は、クラウド サービス プロバイダーとクラウド サービスお客様の両方にガイダンスを提供している点で独特です。</span><span class="sxs-lookup"><span data-stu-id="aeea1-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="aeea1-120">また、クラウド サービスお客様がクラウド サービス プロバイダーに期待できることに関する実際的な情報も示しています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="aeea1-121">お客様が ISO/IEC 27017 から直接得られるメリットとして、クラウドにおける共同責任を理解できます。</span><span class="sxs-lookup"><span data-stu-id="aeea1-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="aeea1-122">Microsoft クラウドでの ISO/IEC 27017 の利点について確認してください: [ISO/IEC 27017: 情報セキュリティ管理の実務基準をダウンロードしてください](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="aeea1-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="aeea1-123">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="aeea1-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="aeea1-124">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="aeea1-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="aeea1-125">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="aeea1-125">Cloud App Security</span></span>
- [<span data-ttu-id="aeea1-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="aeea1-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="aeea1-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="aeea1-127">Genomics</span></span>
- <span data-ttu-id="aeea1-128">Graph</span><span class="sxs-lookup"><span data-stu-id="aeea1-128">Graph</span></span>
- <span data-ttu-id="aeea1-129">Intune</span><span class="sxs-lookup"><span data-stu-id="aeea1-129">Intune</span></span>
- <span data-ttu-id="aeea1-130">Microsoft Flow クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="aeea1-130">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="aeea1-131">Office 365、Office 365 米国政府、Office 365 米国防総省、Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="aeea1-131">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="aeea1-132">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="aeea1-132">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="aeea1-133">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="aeea1-133">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="aeea1-134">Office 365 の対象サービスの[詳細なリスト](https://go.microsoft.com/fwlink/p/?linkid=2077751)をご覧ください</span><span class="sxs-lookup"><span data-stu-id="aeea1-134">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="aeea1-135">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="aeea1-135">Audits, reports, and certificates</span></span>

<span data-ttu-id="aeea1-136">Microsoft クラウド サービスは、年 1 回、ISO/IEC 27001:2013 の認定プロセスの一環として、ISO/IEC 27017:2015 実施基準に関する監査を受けています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-136">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

- [<span data-ttu-id="aeea1-137">Azure ISO 27017 証明書</span><span class="sxs-lookup"><span data-stu-id="aeea1-137">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="aeea1-138">Azure ISO 27017 評価レポート</span><span class="sxs-lookup"><span data-stu-id="aeea1-138">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="aeea1-139">Azure ISO 27017 適用宣言書</span><span class="sxs-lookup"><span data-stu-id="aeea1-139">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/azureiso27017StatementofApplicability)
- [<span data-ttu-id="aeea1-140">Office 365 ISO 27001、27018、27017 監査評価レポート</span><span class="sxs-lookup"><span data-stu-id="aeea1-140">Office 365 — ISO 27001, ISO 27018, and ISO 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="aeea1-141">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="aeea1-141">Frequently asked questions</span></span>

<span data-ttu-id="aeea1-142">この標準はだれに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="aeea1-142">To whom does the standard apply?</span></span>

<span data-ttu-id="aeea1-143">この実施基準では、クラウド サービス プロバイダーとクラウド サービスお客様の両方にコントロールと実装のガイダンスが提供されています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-143">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="aeea1-144">ISO/IEC 27002:2013 と似た構成になっています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-144">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="aeea1-145">**Microsoft ISO/IEC 27017:2015 コンプライアンス情報はどこで確認できますか?**</span><span class="sxs-lookup"><span data-stu-id="aeea1-145">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

<span data-ttu-id="aeea1-146">Azure、Intune、Power BI の [ISO/IEC 27017:2015 認定証](https://aka.ms/azureiso27017)をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="aeea1-146">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="aeea1-147">**Microsoft サービスの ISO/IEC 27017 コンプライアンスを私の組織の認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="aeea1-147">**Can I use the ISO/IEC 27001 compliance of Microsoft services in my organization’s certification?**</span></span>

<span data-ttu-id="aeea1-148">はい。</span><span class="sxs-lookup"><span data-stu-id="aeea1-148">Yes.</span></span> <span data-ttu-id="aeea1-149">ビジネスで求められているのが、Microsoft の適用エンタープライズ クラウド サービスのいずれかにデプロイされている実装の認定である場合は、Microsoft の関連認定をコンプライアンス評価で利用できます。</span><span class="sxs-lookup"><span data-stu-id="aeea1-149">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="aeea1-150">ただし、コンプライアンスや、組織内の統制およびプロセスに関して、実装を評価する査定人の手配の責任は、審査を受ける組織が負うものとします。</span><span class="sxs-lookup"><span data-stu-id="aeea1-150">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="aeea1-151">**該当する監査レポートのコピーはどのようにして入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="aeea1-151">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="aeea1-152">[Service Trust Portal](https://aka.ms/stphelp) では、独立している第三者監査レポートと他の関連資料が提供されています。</span><span class="sxs-lookup"><span data-stu-id="aeea1-152">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="aeea1-153">このポータルを利用して、お客様の規制要件に役立つ資料をダウンロードおよび確認できます。</span><span class="sxs-lookup"><span data-stu-id="aeea1-153">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="aeea1-154">リソース</span><span class="sxs-lookup"><span data-stu-id="aeea1-154">Resources</span></span>

- [<span data-ttu-id="aeea1-155">ISO/IEC 27017:2015 実施基準</span><span class="sxs-lookup"><span data-stu-id="aeea1-155">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="aeea1-156">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="aeea1-156">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="aeea1-157">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="aeea1-157">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="aeea1-158">サービスの背景資料をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="aeea1-158">Download the offering backgrounder</span></span>

<span data-ttu-id="aeea1-159">このサービスに関する背景資料が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="aeea1-159">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="aeea1-160">[PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aeea1-160">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>