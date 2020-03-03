---
title: Register365 で Office 365 用の DNS レコードを作成する
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: ドメインを確認し、電子メール、Skype for Business Online、および Register365 for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362852"
---
# <a name="create-dns-records-at-register365-for-office-365"></a>Register365 で Office 365 用の DNS レコードを作成する

 **探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。 
  
使用している DNS ホスティング プロバイダーが Register365 の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。 
  
追加する主なレコードは次のとおりです。  
  
- [確認のための TXT レコードを追加する](#add-a-txt-record-for-verification)
    
- [MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Office 365 に必要な 6 つの CNAME レコードを追加する](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Office 365 に必要な 2 つの SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-office-365)
    
これらのレコードを Office 365 で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。
  
Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="BKMK_verify"> </a>

Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. [ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。 
    
    (You may have to scroll down.)
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。
    
    (You may have to scroll down.)
    
    |**ホスト名**|**種類**|**結果**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. [**保存**] を選択します。
    
    (You may have to scroll down.)
    
    ![[保存] を選択します。](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。
  
Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする
<a name="BKMK_add_MX"> </a>

1. まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. [ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。 
    
    (You may have to scroll down.)
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. [ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (You may have to scroll down.)
    
    |**ホスト名**|**Priority**|**結果**|
    |:-----|:-----|:-----|
    |(このフィールドは空のままにします。)  <br/> |1-d  <br/> 優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。 <br/> | *\<ドメインキー\>*  .mail.protection.outlook.com  <br/> **注:** Office 365 アカウントから* \<ドメイン\>キー*を取得します。  [確認する方法](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. [**保存**] を選択します。
    
    (You may have to scroll down.)
    
    ![[保存] を選択します。](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. 他の MX レコードがある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. [**保存**] を選択します。
    
    (You may have to scroll down.)
    
    ![[保存] を選択します。](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Office 365 に必要な 6 つの CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

1. まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. [ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。 
    
    (You may have to scroll down.)
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. [ **Add/Modify DNS Zone**] ページの [ **A, CNAME, AAAA, TXT and NS records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。
    
    (下へスクロールしなければならないことがあります。)
    
    |****Host name****|****Type****|****Result****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. [**保存**] を選択します。
    
    ![[保存] を選択します。](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 
  
1. まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. [ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。 
    
    (You may have to scroll down.)
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。
    
    (You may have to scroll down.)
    
    |**ホスト名**|**種類**|**結果**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. [**保存**] を選択します。
    
    (You may have to scroll down.)
    
    ![[保存] を選択します。](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Office 365 に必要な 2 つの SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

1. まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. [ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。 
    
    (You may have to scroll down.)
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. [ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    (下へスクロールしなければならないことがあります。)
    
    |**Name**|**Priority**|**Weight**|**Port**|**結果**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |100  <br/> |1-d  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |100  <br/> |1-d  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![[サービスレコード] セクションに値を入力する](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. [**保存**] を選択します。
    
    (You may have to scroll down.)
    
    ![[保存] を選択します。](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  