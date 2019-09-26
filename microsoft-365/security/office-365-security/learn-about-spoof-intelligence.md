---
title: スプーフィング インテリジェンスをもっとよく知る
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/22/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: '[スパム対策設定] ページ&amp;のセキュリティコンプライアンスセンターのスプーフィングインテリジェンスを使用して、組織の一部であるドメインを偽装している、または外部ドメインのスプーフィングを行っているすべての送信者を確認します。 スプーフィングインテリジェンスは、Office 365 Enterprise E5 の一部として、または Advanced Threat Protection と Exchange Online Protection の一部として別途利用できます。'
ms.openlocfilehash: 3e3e858c8ecd363d62adc33473af2eea239fbaef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085606"
---
# <a name="learn-more-about-spoof-intelligence"></a>スプーフィング インテリジェンスをもっとよく知る

[ &amp; **スパム対策設定] ページ**のセキュリティコンプライアンスセンターのスプーフィングインテリジェンスを使用して、組織の一部であるドメインを偽装している、または外部ドメインのスプーフィングを行っているすべての送信者を確認します。 スプーフィングインテリジェンスは、Office 365 Enterprise E5 の一部として、または Advanced Threat Protection (ATP) の一部として、または、2018の Exchange Online Protection (EOP) の一部として別途利用できます。 
  
## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a>どのような種類の電子メールスプーフィングをレビューできるのか、どのような種類のスプーフィングを使用して保護する必要があるか。

所有するドメインについては、ドメインを偽装している送信者を確認し、送信者が続行またはブロックする送信者を選択できるようにすることができます。 外部ドメインの場合は、送信元の電子メールアドレスではなく、送信側のドメインを送信側のインフラストラクチャと組み合わせて使用できます。
  
送信者が電子メールアドレスをスプーフすると、組織のドメイン内の1つまたは複数のユーザーアカウントに代わってメールを送信したり、外部ドメインから組織に送信したりしたように見えます。 意外にも、なりすましにはいくつかの正当なビジネス上の理由があります。 たとえば、このような場合は、送信者がドメインをスプーフィングすることを禁止することはありません。
  
- 自分のドメインを使用して、会社の投票のために自分の従業員に一括メールを送信するサードパーティの送信者がある。
    
- あなたは、お客様の代わりに、広告や製品の更新を生成して送信するために、外部企業に入社しました。
    
- 組織内の別のユーザーに電子メールを定期的に送信する必要があるアシスタント。
    
- 内部通知を電子メールで送信するために、自分の組織をスプーフィングするように構成されたアプリケーション。
    
外部ドメインは頻繁にスプーフィングされた電子メールを送信するため、これらの理由の多くは正当です。 たとえば、外部の送信者がスプーフィングされた電子メールを送信するという正当なケースを以下に示します。
  
- 送信者がディスカッションのメーリングリストにあり、メーリングリストが元の送信者からメーリングリストのすべての参加者に電子メールを中継しています。
    
- 外部企業は、別の会社 (たとえば、自動化されたレポートや、サービスとしてのソフトウェア会社) に代わって電子メールを送信しています。
    
正規のなりすまし者によって送信されるメールが、Office 365 または外部の電子メールシステムのスパムフィルターでキャッチされないようにする方法が必要です。 通常、Office 365 はこれらの電子メールメッセージをスパムとして扱います。 Office 365 管理者は、セキュリティ&amp; /コンプライアンスセンターでスプーフィングフィルターを設定することによって、これを防止することができます。 ドメインを所有している場合は、これらの送信者に対して許可するように SPF、DKIM、および DMARC を構成できます。
  
その一方で、悪意のあるなりすまし者は、ドメインをスプーフィングしている送信者、または外部ドメインにスパムまたはフィッシング電子メールを送信する送信者をブロックする必要があります。 スプーフィングは、phishers がユーザーの資格情報を取得するための一般的な方法でもあります。 Office 365 には、このような悪意のある電子メールの送信者に組織を保護するためのスプーフィング保護が組み込まれています。 組織のドメインのスプーフィング保護は、すべての Office 365 ユーザーに対して常にオンになっており、高度な脅威保護のお客様や 2018 EOP のお客様のために、外部ドメインのスプーフィング対策が既定でオンになっています。 この保護をさらに強化するには、どの送信者が組織のドメインを偽装し、自分の代わりに電子メールを送信することを許可されているかを指定します。また、すべての外部ドメインでスプーフィングを許可することもできます 承認しない送信者から送信された電子メールは、Office 365 によってスパムまたはスプーフィングとして扱われます。 ドメインをスプーフィングしている送信者を常に把握し、セキュリティ&amp; /コンプライアンスセンターを使用してスプーフィングインテリジェンスを向上させることができます。
  
## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターでのスプーフィングインテリジェンスの管理
<a name="Managespooflist"> </a>

設定したスプーフィングインテリジェンスポリシーは、常に Office 365 によって適用されます。 この機能を無効にすることはできませんが、どの程度アクティブに管理するかを選択できます。
  
ドメインまたは外部ドメインをスプーフィングしている送信者を確認し、セキュリティ&amp;コンプライアンスセンターを使用して各送信者に許可するかどうかを決定することができます。 送信者がドメインまたは外部ドメインからスプーフィングする各スプーフィングされたユーザーアカウントについて、次の表の情報を表示できます。
  
|**パラメーター**|**説明**|
|:-----|:-----|
|Sender  <br/> |実際の送信者とも呼ばれます。 これは通常、スプーフィングメールが発信されるドメインです。 Office 365 は、組織をスプーフィングしている送信元 IP アドレスのポインター (PTR) DNS レコードのドメインを決定します。 ドメインが見つからない場合は、代わりに送信者の IP アドレスがレポートに表示されます。  <br/> |
|偽装ユーザー  <br/> |送信者によってスプーフィングされているユーザーアカウント。  <br/> [**内部**] タブのみ このフィールドには1つの電子メールアドレスが含まれているか、または送信者が複数のユーザーアカウントを偽装している場合は、複数のユーザーアカウントが含まれて**います。**  <br/> **外部**タブのみ 外部ドメインには、送信ドメインのみが含まれ、完全な電子メールアドレスは含まれません。  <br/> **部!上級管理者向け。** スプーフィングされたユーザーは、メールクライアントによって From アドレスとして表示されるアドレスでもある、From (5322.from) アドレスです。 これは、ヘッダーアドレスと呼ばれることがあります。 このアドレスの有効性は、SPF によってチェックされません。           |
|メッセージ数  <br/> |過去30日間の特定のスプーフィングされた送信者または送信者に代わって組織に送信者が送信したメールメッセージの数。  <br/> |
|ユーザーの苦情の数  <br/> |過去30日間のユーザーによってこの送信者に対してユーザーが苦情を提出します。 通常、苦情は Microsoft への迷惑メール送信の形式です。  <br/> |
|認証の結果  <br/> |この値は、送信者が Exchange Online Protection (EOP) sender 認証チェック (SPF、DKIM など) を通過した場合、送信者が EOP sender 認証チェックの失敗時に**失敗**した場合、またはこれらのチェックの結果が**不明**な場合に**渡さ**れます。一般的.  <br/> |
|判断セットの条件  <br/> |Office 365 管理者またはスプーフィングインテリジェンスポリシーが、送信者がユーザーになりすますことが許可されているかどうかを判断したかどうかを示します。  <br/> |
|最終表示日時  <br/> |このスプーフィングされたユーザーに代わって、この送信者がメッセージを受信した最後の日付。  <br/> |
|スプーフィングが許可されますか?  <br/> | この送信者が、偽装されたユーザーの代わりに電子メールを送信することを許可されているかどうかを表示します。 次の値を指定できます。  <br/> **はい**このスプーフィング送信者からのすべてのスプーフィングされたアドレスは、組織になりすますことが許可されます。  <br/> **いいえ**このスプーフィング送信者からのスプーフィングされたアドレスは、組織になりすますことは許可されません。 代わりに、この送信者からのメッセージは、Office 365 によってスパムとしてマークされます。  <br/> **一部のユーザー**送信者が複数のユーザーをスプーフィングしている場合、この送信者からのスプーフィングされたアドレスの一部は、組織になりすますことが許可され、残りはスパムとしてマークされます。 特定のアドレスを表示するには、[**詳細**] タブを使用します。  <br/> |
|スプーフィングの種類  <br/> |この値は、ドメインが組織の準備済みドメインのいずれかである場合に**内部**になります。それ以外の場合、値は**External**です。  <br/> |
   
 **セキュリティ&amp; /コンプライアンスセンターを使用してドメインをスプーフィングしている送信者を管理するには**
  
1. [ &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)に移動します。
    
2. 職場または学校のアカウントを使用して、Office 365 にサインインします。 アカウントには、Office 365 組織の管理者の資格情報が必要です。
    
3. セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \>のスパム**対策**] を展開します。  
  
    ![スパム対策ページへのアクセスを示すスクリーンショット](../media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)
  
4. 右ウィンドウの [**スパム対策設定**] ページで、[**カスタム**] タブを選択し、下にスクロールして [**スプーフィングインテリジェンスポリシー**] を展開します。  
  
    ![スパム対策カスタム設定へのアクセスを示すスクリーンショット](../media/a5112100-0b37-460f-932d-5b2f98157871.jpg)
  
5. ドメインをスプーフィングしている送信者の一覧を表示するには、[**新しい送信者の確認**] を選択して、[**自分のドメイン**] タブを選択します。 
    
    既に送信者をレビューしていて、以前の選択の一部を変更する場合は、代わりに [**既にレビュー**した送信者を表示する] を選択します。 どちらの場合も、次のパネルが表示されます。  
  
    ![[スプーフィングされた送信者] タブへのアクセスを示すスクリーンショット](../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)
  
    各スプーフィングされたユーザーは個別の行に表示されるので、送信者が個々のユーザーを個別にスプーフィングすることを許可またはブロックするかどうかを選択できます。  
  
    ユーザーの許可リストに送信者を追加するには、[**スプーフィングを許可する**] 列から [**はい**] を選択します。 ユーザーの禁止一覧に送信者を追加するには、[**いいえ**] を選択します。
     
    所有していないドメインのポリシーを設定するには、[**外部ドメイン**] タブを選択します。 [**スプーフィングを許可**する] 列で送信者を**Yes**に変更して、その送信者が認証されていない電子メールを組織に送信できるようにします。 または、Office 365 で、送信者がスプーフィングされた電子メールを送信することを許可することに間違いがあると思われる場合は、[**スプーフィングを許可する**] 列を [**いいえ**] に変更します。  
  
    ![送信者にスプーフィングが許可されているかどうかを示すスクリーンショット](../media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)
  
6. [**保存**] を選択して変更を保存します。 

Office 365 Enterprise E5 サブスクリプションを使用している場合、または Advanced Threat Protection をアドオンとして別途購入している場合は、[スプーフィングインテリジェンスの洞察](https://docs.microsoft.com/en-us/office365/securitycompliance/walkthrough-spoof-intelligence-insight)を通じてドメインをスプーフィングしている送信者を管理することもできます。
    
## <a name="configuring-the-anti-spoofing-policy"></a>スプーフィング対策ポリシーの構成
<a name="Managespooflist"> </a>

特定の送信者が組織内のスプーフィングされた電子メールを送信することを許可またはブロックすることに加えて、フィルターの厳密さを設定したり、スプーフィングメッセージが見つかったときに実行するアクションを構成したりすることもできます。
  
Office 365 組織の外部にあるドメインからの送信者からの電子メールに、スプーフィング対策保護が適用されます。 ポリシーは、メールボックスが Office 365 Enterprise E5 用にライセンスされている受信者に適用することができます。また、高度な脅威保護と 2018 EOP の顧客についても同様です。 他のフィッシング対策設定と共に、スプーフィング対策ポリシーを管理します。 フィッシング対策設定の詳細については、「 [Office 365 のフィッシング対策ポリシーをセットアップする](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions)」を参照してください。
  
Office 365 には、常に実行している既定のスプーフィング防止保護が含まれています。 この既定の保護は、セキュリティ&amp;コンプライアンスセンターでは表示されません。また、Windows PowerShell コマンドレットから取得することもできません。 既定のスプーフィング防止保護を変更することはできません。 その代わりに、Office 365 で、作成した各フィッシング対策ポリシーのスプーフィング対策保護を強制的に適用する方法を構成できます。 
  
セキュリティ&amp; /コンプライアンスセンターのフィッシング対策ポリシーの下には、スプーフィング対策ポリシーが表示されていても、スパム対策構成の下にある既存のフィッシング設定から既定の動作を継承しません。 スプーフィング対策のためにレプリケートする**スパム** \>対策**フィッシング**の下に設定がある場合は、フィッシング対策ポリシーを作成してから、スプーフィングの設定を反映するようにフィッシング対策ポリシーのスプーフィング部分を編集する必要があります。次のセクションでは、バックグラウンドで実行される既定の設定を受け入れずに説明します。 
  
 **セキュリティ&amp; /コンプライアンスセンターを使用してフィッシング対策ポリシー内のスプーフィング対策保護を構成するには**
  
1. [ &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)に移動します。
    
2. 職場または学校のアカウントを使用して、Office 365 にサインインします。 アカウントには、Office 365 組織の管理者の資格情報が必要です。
    
3. セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \>の**フィッシング対策**] を展開します。 
    
4. 右ウィンドウの [**フィッシング対策**] ページで、構成するフィッシング対策ポリシーを選択します。 
    
5. 表示されるページの [**スプーフィング**] 行で、[**編集**] を選択します。 
    
6. 次に、クロスドメインのスプーフィングとしてメッセージが検出されたときに実行するアクションを構成します。 既定の動作では、メッセージを受信者の迷惑メールフォルダーに移動します。 もう1つの方法は、メッセージを検疫に送信することです。 検疫に送信されたメッセージの管理の詳細については、「 [Office 365 で電子メールメッセージを検疫](quarantine-email-messages.md)する」を参照してください。  
  
    ![スプーフィング対策ポリシーの編集オプションを示すスクリーンショット](../media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)
  
7. 選択を行い、[**保存**] を選択します。 
    
## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a>Office 365 を使用してスプーフィングとフィッシングを管理するその他の方法
<a name="Managespooflist"> </a>

スプーフィングとフィッシングの保護については、入念に行ってください。 ここでは、ドメインをスプーフィングしている送信者をチェックして、組織の損害を防ぐ方法について説明します。
  
- 「Exchange Online Protection のスプーフィング」メールレポートをルーチンの一部として確認します。 このレポートは多くの場合、スプーフィングされた送信者を表示して管理するために使用できます。 詳細については **、「** [Use mail Protection reports in Office 365」を参照して、マルウェア、スパム、ルールの検出に関するデータを表示](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx)します。
    
より高度な Office 365 管理者の場合は、次のチェックを実行することもできます。
    
    
- Sender Policy Framework (SPF) 構成を確認します。 SPF の概要と簡単な構成方法を確認するには、「[Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)」をご確認ください。
    
- DomainKeys が識別されたメール (DKIM) 構成を確認します。 ドメインから送信されたように見えるメッセージをなりすまし者が送信できないようにするためには、SPF と DMARC に加え、DKIM を使用する必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については、「 [DKIM を使用して、Office 365 のドメインから送信される送信電子メールを検証する](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)」を参照してください。
    
- ドメインベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については、「 [USE DMARC to validate email In Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)」を参照してください。
    
- [Get-phishfilterpolicy](https://technet.microsoft.com/en-us/library/mt735158%28v=exchg.160%29.aspx) Windows PowerShell コマンドレットを使用して、スプーフィングされた送信者の詳細データを収集し、許可リストとブロックリストを生成します。さらに、より包括的な SPF、dkim、および DMARC DNS レコードを作成する方法を決定するのに役立ちます。正当な電子メールは、外部スパムフィルターでキャッチされます。 詳細については、「 [Office 365 でのスプーフィング対策保護のしくみ](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/)」を参照してください。
    
