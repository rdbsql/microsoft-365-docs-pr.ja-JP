---
title: DNSMadeEasy で Office 365 用の DNS レコードを作成する
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: ドメインを確認し、電子メール、Skype for Business Online、および Dnsat for Office 365 の他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248826"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>DNSMadeEasy で Office 365 用の DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが DNSMadeEasy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。
  
これらのレコードを DNSMadeEasy で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
> [!IMPORTANT]
> Dnsが簡単なアカウントの場合、追加したドメインは別のドメインレジストラーから購入されました。 Dns は簡単にドメイン登録サービスを提供しません。 Dnsて簡単にログインし、DNS レコードを作成することで、所有権を十分に証明できます。 
  
1. まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。 
    
3. [管理された**DNS** ] ページの [ **TXT Records** ] 領域で**+**、() コントロール ([**新規追加**]) を選択します。
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**名前** <br/> |**Value** <br/> |**TTL** <br/> |
    |(このフィールドは空のままにします。)  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。 Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. **[送信]** を選択します。
    
6. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

    
2. [**ドメイン**] ページで、確認するドメインを選択します。 
    
3. [**セットアップ**] ページで、[**セットアップの開始**] を選択します。
    
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。 
    
    [**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。 
    
    ![Dnsの簡単な設定-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. [管理された**DNS** ] ページの [ **MX Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。
    
    (You may have to scroll down.)
    
    ![Dnsの簡単な設定-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. [ **Add MX Records**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    |**名前**|**サーバー**|**MX レベル**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **This value MUST end with a period (.)** <br/> **注:**\<Office 365 アカウントから*ドメインキー* \>を取得します。 [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> |1800  <br/> |
   
    ![Dnsの簡単な設定-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. **[送信]** を選択します。
    
    ![Dnsの簡単な設定-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. [ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、1 つずつ選択してそれらを全部削除します。 
    
    ![Dnsの簡単な設定-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. すべてのレコードが選択されたら、[**選択した**ものを削除] を選択します。
    
    ![Dnsの簡単な設定-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. [ **MX レコードの削除**] ダイアログボックスで、[**削除**] を選択して変更を確認します。 
    
    ![Dnsの簡単な設定-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な5つの CNAME レコードを追加します。
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。 
    
3. [管理された**DNS** ] ページの [ **CNAME Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。
    
    (下へスクロールしなければならないことがあります。)
    
    ![Dnsの簡単な設定-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. 5つの CNAME レコードの最初のレコードを追加します。
    
    [ **Add CNAME Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    |**Name**|**Alias to (エイリアス)**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
   
    ![Dnsの簡単な設定-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. **[送信]** を選択します。
    
    ![Dnsの簡単な設定-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. 他の4つの CNAME レコードをそれぞれ追加します。
    
    [ **CNAME Records** ] セクションで、 **(+)** コントロール ([**新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。 
    
    この手順を繰り返し、5つの CNAME レコードをすべて作成します。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 次に例を示します。 参考にしてください。 SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。 
  
1. まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。 
    
3. [管理された**DNS** ] ページの [ **TXT Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。
    
    (下へスクロールしなければならないことがあります。)
    
    ![Dnsの簡単な設定-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**名前**|**Value**|**TTL**|
    |:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |1800  <br/> |
   
    ![Dnsの簡単な設定-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. **[送信]** を選択します。
    
    ![Dnsの簡単な設定-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 個の SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。
    
2. [**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。 
    
3. [管理された**DNS** ] ページの [ **SRV Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。
    
    (下へスクロールしなければならないことがあります。)
    
    ![Dnsの簡単な設定-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. 2 つの SRV レコードの最初のレコードを追加します。
    
    [ **Add SRV Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    |**Name**|**Priority**|**Weight**|**Port**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
    |_sipfederationtls _tcp  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **この値は、末尾がピリオド (.) でなければなりません** <br/> |1800  <br/> |
   
    ![Dnsの簡単な設定-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. **[送信]** を選択します。
    
    ![Dnsの簡単な設定-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. 残りの SRV レコードを追加します。
    
    [ **SRV Records** ] セクションで、 **(+)** コントロール ([**新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。 
    
> [!NOTE]
> 通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
