---
title: 削除したグループを復元する
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 削除された Microsoft 365 グループを復元する方法について説明します。
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818509"
---
# <a name="restore-a-deleted-group"></a>削除されたグループを復元する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

グループを削除した場合、既定では30日間保持されます。 この30日の期間は、引き続きグループを復元できるため、"ソフト削除" と見なされます。 30日後、グループとそれに関連するコンテンツは完全に削除され、復元することはできません。

グループを復元すると、次のコンテンツが復元されます。
  
- Azure Active Directory (AD) Microsoft 365 グループオブジェクト、プロパティ、およびメンバー。
    
- グループの電子メールアドレス。
    
- Exchange Online の共有の受信トレイと予定表。
    
- SharePoint Online チームサイトとファイル。
    
- OneNote ノートブック
    
- Planner
    
- Teams

- Yammer グループとグループのコンテンツ (Yammer から Microsoft 365 グループが作成されている場合)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>Outlook on the web を使用して自分が所有するグループを復元する

Microsoft 365 グループの所有者である場合は、次の手順に従って、そのグループを web 上の Outlook で自分で復元することができます。

1. [[削除さ](https://outlook.office.com/people/group/deleted)れたグループ] ページで、[**グループ**] ノードの下の [**グループの管理**] オプションを選択し、[**削除済み**] を選択します。

2. 復元するグループの横にある [**復元**] タブをクリックします。

削除されたグループがここに表示されない場合は、管理者に問い合わせてください。

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでグループを復元する

グローバル管理者またはグループ管理者の場合は、次のように、削除されたグループを Microsoft 365 管理センターで復元できます。

1. [管理センター](https://admin.microsoft.com)に移動します。
2. [**グループ**] を展開し、[**削除済みグループ**] をクリックします。
3. 復元するグループを選択し、[**グループの復元**] をクリックします。

> [!NOTE]
> 場合によっては、グループとそのすべてのデータが復元されるまでに24時間かかることがあります。 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Microsoft 365 グループを完全に削除する

場合によっては、30日間のソフト削除期間が経過するのを待たずに、グループを完全に削除する必要があります。 それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。
  
```
Get-AzureADMSDeletedGroup
```

完全に削除するグループまたはグループのオブジェクト ID を書き留めておきます。
  
> [!CAUTION]
> グループを削除すると、グループとそのデータが永久に削除されます。 
  
グループを削除するには、PowerShell で次のコマンドを実行します。
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Microsoft 365 グループに関する質問

Microsoft[技術コミュニティ](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)にアクセスして、microsoft 365 グループに関する質問を投稿し、会話に参加してください。 
  
## <a name="related-articles"></a>関連記事

[PowerShell を使用して Microsoft 365 グループを管理する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Remove-UnifiedGroup コマンドレットを使用してグループを削除する](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[グループに接続されたチーム サイトの設定を管理する](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Outlook でグループを削除する](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
