---
title: 分離した SharePoint Online チーム サイトの設計
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: アクセス許可レベルの決定、アクセスグループを持つユーザーへのアクセス許可の割り当て、およびネストされた Azure AD グループを含む、分離した SharePoint Online チームサイトを設計します。
ms.openlocfilehash: 821e15a05bc80e3795f9e18d4457416baf7145b7
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209513"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>分離した SharePoint Online チーム サイトの設計

 **概要:** 分離した SharePoint Online チーム サイトの設計プロセスをステップごとに示します。
  
この記事では、分離した SharePoint Online チーム サイトを作成する前に行う必要がある設計上の主要な決定事項について説明します。
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>フェーズ 1:SharePoint グループおよびアクセス許可レベルを決定します。

既定では、すべての SharePoint Online チーム サイトは次の SharePoint グループを使用して作成されます。
  
- \<サイト名> メンバー
    
- \<サイト名> 閲覧者
    
- \<サイト名> の所有者
    
これらのグループは、Microsoft 365 および Azure Active Directory (AD) グループとは別のものであり、サイトのリソースに対するアクセス許可を割り当てるための基礎となります。
  
SharePoint グループのメンバーがサイトで実行できる内容を決定する特定のアクセス許可のセットが、アクセス許可レベルになります。SharePoint Online チーム サイトでは、既定では次の 3 つのアクセス許可レベルがあります。編集、読み取り、フル コントロールです。次の表は、SharePoint グループと割り当てられるアクセス許可レベルとの既定の相関関係を示しています。
  
|**SharePoint グループ**|**アクセス許可レベル**|
|:-----|:-----|
|\<サイト名> メンバー  <br/> |Edit  <br/> |
|\<サイト名> 閲覧者  <br/> |Read  <br/> |
|\<サイト名> の所有者  <br/> |フル コントロール  <br/> |
   
 **ベスト プラクティス:** 追加の SharePoint グループおよびアクセス許可レベルを作成できます。ただし、分離した SharePoint Online サイトには、既定の SharePoint グループおよびアクセス許可レベルを使用することをお勧めします。
  
既定の SharePoint グループとアクセス許可レベルは次のとおりです。
  
![SharePoint Online サイトの既定の SharePoint グループとアクセス許可レベル。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>フェーズ 2:アクセス グループを使用してアクセス許可をユーザーに割り当てる

ユーザーにアクセス許可を割り当てるには、そのユーザーアカウント、またはユーザーアカウントがメンバーになっている Microsoft 365 または Azure AD グループを SharePoint グループに追加します。 追加されたユーザーアカウントには、Microsoft 365 または Azure AD グループのメンバーシップ経由で直接的または間接的に、SharePoint グループに関連付けられているアクセス許可レベルが割り当てられます。
  
既定の SharePoint グループを使用した例:
  
- [ ** \< サイト名> メンバー** ] SharePoint グループのメンバーには、ユーザーアカウントとグループの両方を含めることができます。このグループには、**編集**アクセス許可レベルが割り当てられます。
    
- ユーザーアカウントとグループの両方を含むことができる** \< サイト名> 閲覧**者 SharePoint グループのメンバーには、**読み取り**アクセス許可レベルが割り当てられます。
    
- [ ** \< サイト名> 所有者**] SharePoint グループのメンバーには、ユーザーアカウントとグループの両方を含めることができます。これには、**フルコントロール**のアクセス許可レベルが割り当てられます。
    
 **ベスト プラクティス:** 個々のユーザー アカウントを使用してアクセス許可を管理することもできますが、代わりにアクセス グループと呼ばれる 1 つの Azure AD グループを使用することをお勧めします。この方法は、SharePoint グループごとにユーザー アカウントのリストを管理するのではなく、アクセス グループのメンバーシップでアクセス許可の管理を簡略化するものです。
  
Microsoft 365 の Azure AD グループは、で Microsoft 365 のグループとは異なります。 Azure AD グループは、その**種類**が [**セキュリティ**] に設定され、電子メールアドレスを持たない Microsoft 365 管理センターに表示されます。 以下で Azure AD グループを管理できます。
  
- Active Directory ドメイン サービス (AD DS)
    
    これらは、オンプレミスの AD DS インフラストラクチャで作成され、Microsoft 365 サブスクリプションに同期されているグループです。 Microsoft 365 管理センターでは、これらのグループの**状態**は**Active directory と同期**しています。
    
- Office 365
    
    これらは、Microsoft 365 管理センター、Azure ポータル、または Microsoft PowerShell のいずれかを使用して作成されたグループです。 Microsoft 365 管理センターでは、これらのグループには**クラウド**の**状態**があります。
    
 **ベストプラクティス:** オンプレミスの AD DS を使用していて、Microsoft 365 サブスクリプションと同期している場合は、AD DS でユーザーとグループの管理を実行します。
  
分離した SharePoint Online チーム サイトの場合、推奨されるグループ構造は次のようになります。
  
|**SharePoint グループ**|**Azure AD ベースのアクセス グループ**|**アクセス許可レベル**|
|:-----|:-----|:-----|
|\<サイト名> メンバー  <br/> |\<サイト名> メンバー  <br/> |Edit  <br/> |
|\<サイト名> 閲覧者  <br/> |\<サイト名> 閲覧者  <br/> |Read  <br/> |
|\<サイト名> の所有者  <br/> |\<サイト名> 管理者  <br/> |フル コントロール  <br/> |
   
 **ベストプラクティス:** Microsoft 365 または Azure AD グループは SharePoint グループのメンバーとして使用できますが、Azure AD グループを使用することをお勧めします。 AD DS または Microsoft 365 によって管理される Azure AD グループでは、ネストされたグループを使用してアクセス許可を割り当てる方が柔軟性があります。
  
Azure AD ベースのアクセスグループを使用するように構成された既定の SharePoint グループを次に示します。
  
![Access グループを既定の SharePoint Online サイトグループのメンバーとして使用します。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
3 つのアクセス グループを設計するときは、以下の点にご注意ください。
  
- ** \< サイト名> Admins**アクセスグループには、チームサイトを管理している少数の SharePoint Online 管理者に対応する少数のメンバーのみが含まれている必要があります。
    
- サイトメンバーのほとんどは、[ ** \< サイト名> メンバー**または** \< サイト名> 閲覧**者アクセスグループに所属しています。 サイト** \< 名> members**アクセスグループのサイトメンバーは、サイト内のリソースを削除または変更できるため、そのメンバーシップを慎重に検討してください。 インダウトの場合は、サイト** \< 名> 閲覧**者アクセスグループにサイトメンバーを追加します。
    
ここでは、ProjectX という名前の分離されたサイトの SharePoint グループとアクセスグループの例を示します。
  
![ProjectX という名前の SharePoint Online サイトのアクセスグループを使用する例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>フェーズ 3: ネストされた Azure AD グループを使用する

少数のユーザーに限定されるプロジェクトの場合、ほとんどのシナリオはサイトの SharePoint グループに追加される単一レベルの Azure AD ベースのアクセス グループに収まります。ただし、多数のユーザーがおり、それらのユーザーが既に確立された Azure AD グループのメンバーである場合、ネストされたグループ、つまり他のグループがメンバーとして含まれるグループを使用することで簡単に SharePoint アクセス許可を割り当てることができます。
  
たとえば、営業部門、マーケティング部門、エンジニアリング部門、法律部門の役員間でコラボレーションするための分離した SharePoint Online チーム サイトを作成したいと考えており、それらの部門には既に役員のユーザー アカウントのメンバーシップを持つ独自のグループが存在するとします。この場合、新しいサイト メンバー用に新しいグループを作成して、それぞれの役員ユーザー アカウントをすべてそこに含めるのではなく、各部門の既存の役員グループを新しいグループに入れます。
  
 複数の組織間で Microsoft 365 サブスクリプションを共有している場合は、ユーザーアカウント数が非常に多くなるため、1つの組織の分離されたサイトに対して1つのレベルのグループメンバーシップを管理するのが困難になる可能性があります。 この場合、組織内のグループが含まれるネストされた Azure AD グループを組織ごとに使用して、アクセス許可を管理することができます。
  
ネストされた Azure AD グループを使用するには、以下を実行します。
  
1. ユーザー アカウントを含める Azure AD グループを特定するか作成し、適切なユーザー アカウントをメンバーとして追加します。
    
2. 他の Azure AD グループを含めるコンテナーとなる Azure AD ベースのアクセス グループを作成し、それらのグループをメンバーとして追加します。
    
3.   コンテナー アクセス グループの適切なアクセス レベルについては、SharePoint グループと、対応するアクセス許可レベルを識別します。
    
> [!NOTE]
> ネストされた Microsoft 365 グループは使用できません。 
  
ここでは、ProjectX メンバーアクセスグループのための、ネストされた Azure AD グループの例を示します。
  
![ProjectX サイトのメンバーアクセスグループにネストされたアクセスグループを使用する例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
リサーチ、エンジニアリング、プロジェクトリードの各チームのすべてのユーザーアカウントはサイトメンバーになることを目的としているため、Azure AD グループを ProjectX Members アクセスグループに追加するのが簡単です。
  
## <a name="next-step"></a>次の手順

分離したサイトを運用環境で作成および構成する準備ができたら、「[Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[分離した SharePoint Online チーム サイト](isolated-sharepoint-online-team-sites.md)
  
[分離した SharePoint Online チーム サイトの管理](manage-an-isolated-sharepoint-online-team-site.md)

[分離した SharePoint Online チーム サイトの展開](deploy-an-isolated-sharepoint-online-team-site.md)



