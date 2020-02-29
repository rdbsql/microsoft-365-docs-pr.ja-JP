---
title: Freenom で Office 365 用の DNS レコードを作成する
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: ドメインを確認し、電子メール、Skype for Business Online、および Office 365 用の Freenom の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: a1396964c7dc9c279589a6020e0c741fd0cb29d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248971"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a>Freenom で Office 365 用の DNS レコードを作成する

探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。 
  
> [!CAUTION]
> Freenom の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Office 365 プランでも、かなりのサービスの制限事項があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。 
  
サービスの制限があっても、Freenom で Office 365 の DNS レコードを管理する場合は、この記事に示す手順に従って、ドメインを確認し、メールや他のサービスの DNS レコードを設定してください。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。
  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認用に TXT レコードを追加する
<a name="bkmk_txt"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [**サービス**] を選択し、[**マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの**管理**] を選択します。
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom Manage Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。 
    
    ![Freenom Add Record type TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**名前**|**Type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |TXT  <br/> |3600 (秒)  <br/> |MS = msXXXXXXXX  <br/> **注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. [ **Save Changes**] を選びます。
    
    ![Freenom TXT record Save Changes](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。

    
2. [**ドメイン**] ページで、確認するドメインを選択します。 
    
    
  
3. [**セットアップ**] ページで、[**セットアップの開始**] を選択します。
    
    
  
4. [**ドメインの確認**] ページで、[**確認**] を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする
<a name="bkmk_mx"> </a>

1. まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [**サービス**] を選択し、[**マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの**管理**] を選択します。
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. ドメインの名前機能を既定の Freenom ネームサーバーに設定します。 [**管理ツール**] を選択し、[**ネーム**サーバー] を選択します。
    
    ![Freenom Nameservers setting](../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. [既定のネームサーバーを**使用する**] が選択されていることを確認し、[ネームサーバーの**変更**] を選択します
    
    ![Freenom Change Nameservers](../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom select Freenom DNS の管理](../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **MX** ] を選びます。 
    
    ![Freenom Add Record type MX](../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    |**名前**|**Type**|**TTL**|**Target**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |MX (Mail Exchanger)  <br/> |3600 (秒)  <br/> |\<ドメインキー\>. mail.protection.outlook.com  <br/> **注:** Office 365 アカウントから* \<ドメイン\>キー*を取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 優先度の詳細については、「[What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)」を参照してください。 <br/> |
   
   ![Freenom MX record](../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. [ **Save Changes**] を選びます。
    
    ![Freenom MX record Save Changes](../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. その他の MX レコードがある場合は、すべてを削除します。 レコードごとに [**削除**] を選択します。 メッセージを**本当に削除したい場合は**、[ **OK**] を選択します。
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な CNAME レコードを追加する
<a name="bkmk_cname"> </a>

1. まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [**サービス**] を選択し、[**マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの**管理**] を選択します。
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom select Freenom DNS の管理](../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **CNAME** ] を選びます。 
    
    ![Freenom Add Record type CNAME](../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 最初の CNAME レコードを作成します。新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    |**Name**|**Record type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (秒)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (秒)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (秒)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (秒)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (秒)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. [ **Save Changes**] を選びます。
    
    ![Freenom CNAME Save Changes](../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。 
    
    レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 

1. まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [**サービス**] を選択し、[**マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの**管理**] を選択します。
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom select Freenom DNS の管理](../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。 
    
    ![Freenom Add Record type TXT](../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. 新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。 
    
    |**Name**|**Record type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |TXT  <br/> |3600 (秒)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Freenom TXT values for SPF](../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. [ **Save Changes**] を選びます。
    
    ![Freenom TXT record for SPF Save Changes](../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  
