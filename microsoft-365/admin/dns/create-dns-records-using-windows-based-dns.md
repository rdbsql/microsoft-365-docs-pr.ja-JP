---
title: Windows ベースの DNS を使用して Office 365 用の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Office 365 用の Windows ベースの DNS で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: ddea5cb95a7f2abef8b68b37de473f936ee08eb5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249314"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a><span data-ttu-id="33391-103">Windows ベースの DNS を使用して Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="33391-103">Create DNS records for Office 365 using Windows-based DNS</span></span>

 <span data-ttu-id="33391-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="33391-105">Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、電子メール、Skype for Business Online などのレコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="33391-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="33391-106">まず、 [dns レコードを Windows ベースの dns で検索して](#find-your-dns-records-in-windows-based-dns)更新できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33391-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="33391-107">また、オンプレミスの Active Directory を Office 365 と同期することを計画している場合は、オンプレミスの[Active directory で UPN として使用されるルーティング可能でない電子メールアドレス](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-107">Also, if you're planning to synchronize your on-premises Active Directory with Office 365, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="33391-108">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメイン名または dns レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="33391-109">Windows ベース DNS 内の DNS レコードを検索する</span><span class="sxs-lookup"><span data-stu-id="33391-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="33391-110"><a name="BKMK_find_your_dns_1"></a>ドメインの DNS レコードがあるページに移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="33391-111">Windows Server 2008 で作業している**場合は、** > [**実行**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="33391-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="33391-112">Windows Server 2012 で作業している場合は、Windows キーと**r**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="33391-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="33391-113">「 **Dnsmgmnt**」と入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="33391-114">Dns マネージャーで、[ \*\* \<dns サーバー名\> \>前方参照ゾーン  \*\*] を展開します。</span><span class="sxs-lookup"><span data-stu-id="33391-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="33391-115">ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-115">Select your domain.</span></span> <span data-ttu-id="33391-116">これで、DNS レコードを作成する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="33391-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="33391-117">MX レコードの追加</span><span class="sxs-lookup"><span data-stu-id="33391-117">Add MX record</span></span>
<span data-ttu-id="33391-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="33391-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="33391-119">MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにします。</span><span class="sxs-lookup"><span data-stu-id="33391-119">Add an MX record so email for your domain will come to Office 365.</span></span>
- <span data-ttu-id="33391-120">追加する MX レコードには、 **ポイント先のアドレス**を示す値が含まれており、\<MX token\>.mail.protection.outlook.com (\<MX token\> の値は MSxxxxxxx など) のような内容です。  </span><span class="sxs-lookup"><span data-stu-id="33391-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="33391-121">Office 365 の [DNS レコードの追加] ページの [Exchange Online] セクションの [MX] 行で、[point to アドレス] の下に表示されている値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="33391-121">From the MX row in the Exchange Online section of the Add DNS records page in Office 365, copy the value listed under Points to address.</span></span> <span data-ttu-id="33391-122">この値は、このタスクで作成しているレコードで使用します。</span><span class="sxs-lookup"><span data-stu-id="33391-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="33391-123">ドメインの [DNS マネージャー] ページで、[**アクション** > **メールエクスチェンジャー (MX)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="33391-124">ドメインのこのページを見つけるには、「 [Windows ベースの dns で dns レコードを検索](#find-your-dns-records-in-windows-based-dns)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="33391-125">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="33391-126">ホスト名:</span><span class="sxs-lookup"><span data-stu-id="33391-126">Host Name:</span></span> 
    - <span data-ttu-id="33391-127">@Address: Office 365 からコピーしたばかりのアドレス値をここに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="33391-127">@Address: Paste the Points to address  value that you just copied from Office 365 here.</span></span>  
    - <span data-ttu-id="33391-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="33391-128">Pref:</span></span> 
- <span data-ttu-id="33391-129">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="33391-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="33391-130">古い MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="33391-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="33391-131">他の場所に電子メールをルーティングする、このドメインの古い MX レコードがある場合は、古いレコードの横にあるチェックボックスをオンにして、[**削除** > **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="33391-132">CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="33391-132">Add CNAME records</span></span>
<span data-ttu-id="33391-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="33391-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="33391-134">Office 365 に必要な CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-134">Add the CNAME records that are required for Office 365.</span></span> <span data-ttu-id="33391-135">Office 365 にさらに CNAME レコードが一覧に含まれている場合は、これと同じ全般的な手順に従って追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-135">If additional CNAME records are listed in Office 365, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33391-136">Office 365 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33391-136">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="33391-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="33391-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="33391-138">(MDM を持っていない場合は、この手順を省略できます)。</span><span class="sxs-lookup"><span data-stu-id="33391-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="33391-139">ドメインの [DNS マネージャー] ページで、[ **Action** > **CNAME (cname)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="33391-140">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="33391-141">ホスト名: 自動検出</span><span class="sxs-lookup"><span data-stu-id="33391-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="33391-142">種類:</span><span class="sxs-lookup"><span data-stu-id="33391-142">Type:</span></span> 
    - <span data-ttu-id="33391-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="33391-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="33391-144">[ **O**K] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-144">Select **O**K.</span></span>

<span data-ttu-id="33391-145">SIP CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="33391-146">ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="33391-147">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="33391-148">ホスト名: sip</span><span class="sxs-lookup"><span data-stu-id="33391-148">Host Name: sip</span></span>
    - <span data-ttu-id="33391-149">型: CNAME</span><span class="sxs-lookup"><span data-stu-id="33391-149">Type: CNAME</span></span>
    - <span data-ttu-id="33391-150">アドレス: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33391-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="33391-151">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-151">Select **OK**.</span></span>

<span data-ttu-id="33391-152">Skype for Business Online の自動検出の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="33391-153">ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="33391-154">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="33391-155">ホスト名: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="33391-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="33391-156">型: CNAME</span><span class="sxs-lookup"><span data-stu-id="33391-156">Type: CNAME</span></span>
    - <span data-ttu-id="33391-157">アドレス: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33391-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="33391-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="33391-159">Office 365 のモバイル デバイス管理 (MDM) 用として 2 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="33391-159">Add two CNAME records for Mobile Device Management (MDM) for Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33391-160">Office 365 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33391-160">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="33391-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="33391-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="33391-162">> (MDM を使用していない場合は、この手順を省略できます)。</span><span class="sxs-lookup"><span data-stu-id="33391-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="33391-163">MDM Enterpriseregistration CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="33391-164">ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="33391-165">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="33391-166">ホスト名: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="33391-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="33391-167">型: CNAME</span><span class="sxs-lookup"><span data-stu-id="33391-167">Type: CNAME</span></span>
- <span data-ttu-id="33391-168">アドレス: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="33391-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="33391-169">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-169">Select **OK**.</span></span> 

<span data-ttu-id="33391-170">MDM Enterpriseenrollment CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="33391-171">ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="33391-172">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="33391-173">ホスト名: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="33391-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="33391-174">型: CNAME</span><span class="sxs-lookup"><span data-stu-id="33391-174">Type: CNAME</span></span>
    - <span data-ttu-id="33391-175">アドレス: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33391-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="33391-176">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="33391-177">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="33391-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="33391-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="33391-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="33391-179">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="33391-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="33391-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="33391-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="33391-181">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="33391-181">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="33391-182">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="33391-182">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="33391-183">自分のドメインの SPF TXT レコードを追加して、電子メールのスパム防止に役立てます。</span><span class="sxs-lookup"><span data-stu-id="33391-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="33391-184">このレコード (マーケティング電子メールの文字列など) の TXT 値には、既に他の文字列が含まれている場合がありますが、これは問題ありません。</span><span class="sxs-lookup"><span data-stu-id="33391-184">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine.</span></span> <span data-ttu-id="33391-185">これらの文字列をそのまま残して、この文字列を追加し、各文字列を二重引用符で区切って配置します。</span><span class="sxs-lookup"><span data-stu-id="33391-185">Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="33391-186">ドメインの [DNS マネージャー] ページで、[**アクション** \> **テキスト (TXT)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="33391-187">[**新しいリソースレコード**] ダイアログボックスで、フィールドが正確に次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="33391-188">Windows DNS マネージャーの一部のバージョンでは、ドメインがセットアップされていて、txt レコードの作成時にホーム名が既定で親ドメインになっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="33391-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="33391-189">このような場合、TXT レコードを追加するときに、@ またはドメイン名に設定するのではなく、ホスト名を空白 (値なし) に設定します。</span><span class="sxs-lookup"><span data-stu-id="33391-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="33391-190">ホストの種類:@</span><span class="sxs-lookup"><span data-stu-id="33391-190">Host type: @</span></span>
-  <span data-ttu-id="33391-191">レコードの種類: TXT</span><span class="sxs-lookup"><span data-stu-id="33391-191">Record Type: TXT</span></span>
-  <span data-ttu-id="33391-192">アドレス: v = spf1 には、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="33391-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="33391-193">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="33391-194">SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="33391-194">Add SRV records</span></span>
<span data-ttu-id="33391-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="33391-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="33391-196">Office 365 に必要な2つの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-196">Add the two SRV records that are required for Office 365.</span></span>

<span data-ttu-id="33391-197">Skype for Business Online web 会議の SIP SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="33391-198">ドメインの [DNS マネージャー] ページで、[**アクション** \> **その他の新しいレコード**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="33391-199">[**リソースレコードの種類**] ウィンドウで、[**サービスロケーション (SRV)**] を選択し、[**レコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="33391-200">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="33391-201">サービス: _sip</span><span class="sxs-lookup"><span data-stu-id="33391-201">Service: _sip</span></span>
    -  <span data-ttu-id="33391-202">プロトコル: _tls</span><span class="sxs-lookup"><span data-stu-id="33391-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="33391-203">優先度: 100</span><span class="sxs-lookup"><span data-stu-id="33391-203">Priority: 100</span></span>
    -  <span data-ttu-id="33391-204">重み: 1</span><span class="sxs-lookup"><span data-stu-id="33391-204">Weight: 1</span></span>
    -  <span data-ttu-id="33391-205">ポート: 443</span><span class="sxs-lookup"><span data-stu-id="33391-205">Port: 443</span></span>
    -  <span data-ttu-id="33391-206">ターゲット (ホスト名): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33391-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="33391-207">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-207">Select **OK**.</span></span> 


<span data-ttu-id="33391-208">Skype for Business Online フェデレーションの SIP SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="33391-209">ドメインの [DNS マネージャー] ページで、[**アクション** \> **その他の新しいレコード**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="33391-210">[**リソースレコードの種類**] ウィンドウで、[**サービスロケーション (SRV)**] を選択し、[**レコードの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="33391-211">[**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="33391-212">サービス: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="33391-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="33391-213">プロトコル: _tcp</span><span class="sxs-lookup"><span data-stu-id="33391-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="33391-214">優先度: 100</span><span class="sxs-lookup"><span data-stu-id="33391-214">Priority: 100</span></span>
    -  <span data-ttu-id="33391-215">重み: 1</span><span class="sxs-lookup"><span data-stu-id="33391-215">Weight: 1</span></span>
    -  <span data-ttu-id="33391-216">ポート: 5061</span><span class="sxs-lookup"><span data-stu-id="33391-216">Port: 5061</span></span>
    -  <span data-ttu-id="33391-217">ターゲット (ホスト名): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="33391-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="33391-218">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33391-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="33391-219">ドメインを所有していることを確認するためにレコードを追加します (まだ登録していない場合)。</span><span class="sxs-lookup"><span data-stu-id="33391-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="33391-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="33391-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="33391-221">Office 365 サービスをセットアップするために DNS レコードを追加する前に、Office 365 は、追加しているドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33391-221">Before you add the DNS records to set up your Office 365 services, Office 365 has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="33391-222">これを行うには、以下の手順に従ってレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33391-223">このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。</span><span class="sxs-lookup"><span data-stu-id="33391-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="33391-224">Office 365 から情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="33391-224">Gather information from Office 365.</span></span>  <br/> 
2. <span data-ttu-id="33391-225">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="33391-226">[**ドメイン**] ページで、確認するドメインの [**操作**] 列で、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="33391-227">[ **Office へのドメインの追加 365** ] ページで、[**ステップ1を開始**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-227">On the **Add a domain to Office 365** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="33391-228">[**自分のドメインを所有**していることを確認します] ページで、[**この手順を実行するための**手順を参照してください] ドロップダウンリストで、[**一般的な手順**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="33391-229">テーブルから、移動先またはポイントを [Address value] にコピーします。</span><span class="sxs-lookup"><span data-stu-id="33391-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="33391-230">次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="33391-230">You'll need it for the next step.</span></span> <span data-ttu-id="33391-231">この値をコピーして貼り付けることをお勧めします。これにより、すべてのスペースが正しく保たれるようになります。</span><span class="sxs-lookup"><span data-stu-id="33391-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="33391-232">TXT レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="33391-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="33391-233">ドメインの [DNS マネージャー] ページで、[**アクション** \> **テキスト (TXT)**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="33391-234">[**新しいリソースレコード**] ダイアログボックスで、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="33391-235">[**新しいリソースレコード**] ダイアログボックスの [**ユーザー設定のホスト名**] 領域で、フィールドが正確に次の値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="33391-236">Windows DNS マネージャーの一部のバージョンでは、ドメインがセットアップされていて、txt レコードの作成時にホーム名が既定で親ドメインになっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="33391-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="33391-237">このような場合、TXT レコードを追加するときに、@ またはドメイン名に設定するのではなく、ホスト名を空白 (値なし) に設定します。</span><span class="sxs-lookup"><span data-stu-id="33391-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="33391-238">ホスト名:@</span><span class="sxs-lookup"><span data-stu-id="33391-238">Host Name: @</span></span>
- <span data-ttu-id="33391-239">型: TXT</span><span class="sxs-lookup"><span data-stu-id="33391-239">Type: TXT</span></span>
- <span data-ttu-id="33391-240">住所: Office 365 からコピーしたばかりのアドレス値をコピー先またはポイントに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="33391-240">Address: Paste the Destination or Points to Address value that you just copied from Office 365 here.</span></span>  
- <span data-ttu-id="33391-241">[ **OK** > **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="33391-242">Office 365 でドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="33391-242">Verify your domain in Office 365.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="33391-243">この操作を行う前に15分ほど待ってから、作成したレコードがインターネットを介して更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="33391-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="33391-244">Office 365 に戻り、次の手順に従って確認を要求します。</span><span class="sxs-lookup"><span data-stu-id="33391-244">Go back to Office 365 and follow the steps below to request a verification check.</span></span> <span data-ttu-id="33391-245">このチェックボックスでは、前の手順で追加した TXT レコードを探します。</span><span class="sxs-lookup"><span data-stu-id="33391-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="33391-246">正しい TXT レコードが見つかった場合、ドメインは確認されます。</span><span class="sxs-lookup"><span data-stu-id="33391-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="33391-247">管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="33391-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="33391-248">[**ドメイン**] ページで、確認するドメインの [**処理**] 列で、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="33391-249">[**自分のドメインを所有**していることを確認してください] ページで、[**完了]、[今すぐ確認**] の順に選択し、確認のダイアログボックスで [**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33391-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="33391-p117">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="33391-253">オンプレミスの Active Directory で UPN として使用される、ルーティング不可能な電子メールアドレス</span><span class="sxs-lookup"><span data-stu-id="33391-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="33391-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="33391-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="33391-255">オンプレミスの Active Directory を Office 365 と同期することを計画している場合は、Active Directory ユーザープリンシパル名 (UPN) サフィックスが有効なドメインサフィックスであることを確認し、@contoso など、サポートされていないドメインサフィックスではないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33391-255">If you're planning to synchronize your on-premises Active Directory with Office 365, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="33391-256">UPN サフィックスを変更する必要がある場合は、「[ディレクトリ同期のためにルーティング不能なドメインを準備する方法](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="33391-p119">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33391-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  