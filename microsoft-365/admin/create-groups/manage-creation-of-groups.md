---
title: グループを作成できるユーザーを管理する
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 グループを作成できるユーザーを制御する方法について説明します。
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761676"
---
# <a name="manage-who-can-create-groups"></a>グループを作成できるユーザーを管理する

  
ユーザーは、Microsoft 365 グループを作成するのが簡単なので、他のユーザーに代わってそれらを作成するための要求は殺到しません。 ただし、業務によっては、グループを作成できるユーザーを制御したい場合があります。
  
この記事では、次のようなグループを使用するすべての Microsoft 365 サービスでグループを作成する機能を無効にする方法について説明します。
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream

- Planner
    
- PowerBI

- Web およびロードマップのプロジェクト
    
Microsoft 365 グループの作成を特定のセキュリティグループのメンバーに制限できます。 制限するには、Windows PowerShell を使用します。 この記事では、必要な手順について説明します。
  
この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。 グローバル管理者は、Microsoft 365 管理センター、Planner、Teams、Exchange、SharePoint Online などの任意の方法でグループを作成できます。 他の役割は、以下のような制限付きの方法でグループを作成できます。
        
  - Exchange 管理者: Exchange 管理センター、Azure AD
    
  - パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD
    
  - パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD
    
  - ディレクトリ製作者: Azure AD

  - SharePoint 管理者: SharePoint 管理センター、Azure AD
  
  - Teams サービス管理者: Teams 管理センター、Azure AD
  
  - ユーザー管理の管理者: Microsoft 365 管理センター、Yammer、Azure AD
     
これらの役割のいずれかのメンバーである場合は、制限されたユーザーに対して Microsoft 365 グループを作成し、そのユーザーをグループの所有者として割り当てることができます。 この役割を持つユーザーは、作成を妨げる可能性のある PowerShell 設定に関係なく、Yammer で接続済みグループを作成できます。

## <a name="licensing-requirements"></a>ライセンス要件

グループを作成するユーザーを管理するには、以下のユーザーが Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要があります。

- これらのグループ作成の設定を管理している管理者
- グループの作成が許可されているセキュリティグループのメンバー

> [!NOTE]
> Azure ライセンスの割り当て方法の詳細については[、「Azure Active Directory ポータルでライセンスを割り当てるまたは削除](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)する」を参照してください。

以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。

- Microsoft 365 グループのメンバーであり、他のグループを作成する機能を持たないユーザー。

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>手順 1: Microsoft 365 グループを作成する必要があるユーザーのセキュリティグループを作成する

グループを作成できるユーザーを制御するために使用できる組織内のセキュリティ グループは 1 つです。 ただし、このグループのメンバーとして、他のセキュリティ グループをネストすることができます。 たとえば、Allow Group Creation という名前のグループが指定されたセキュリティ グループで、Microsoft Planner Users and Exchange Online Users という名前のグループがそのグループのメンバーであるとします。

上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。

> [!IMPORTANT]
> グループを作成できるユーザーを制限するには、必ず **セキュリティー グループ** を使用してください。 Microsoft 365 グループを使用しようとしても、メンバーはセキュリティグループをチェックするため、SharePoint からグループを作成することはできません。 
    
1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。

2. [**グループの追加**] をクリックします。

3. グループの種類として [**セキュリティ**] を選択します。 グループの名前は覚えておいてください。 後で必要になります。
  
4. セキュリティグループの設定を終了し、組織内でグループを作成できるユーザーまたは他のセキュリティグループを追加します。
    
詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](../email/create-edit-or-delete-a-security-group.md)」を参照してください。
 
## <a name="step-2-run-powershell-commands"></a>手順 2: PowerShell コマンドを実行する

グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

- Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。

- プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。



下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。

を、 *\<SecurityGroupName\>* 作成したセキュリティグループの名前に置き換えます。 例:

`$GroupName = "Group Creators"`

GroupCreators.ps1 としてファイルを保存します。 

PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。

次のように入力してスクリプトを実行します。

`.\GroupCreators.ps1`

サインインを求められたら、[管理者アカウントでサインイン](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)します。

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

スクリプトの最後の行に、更新された設定が表示されます。

![完了すると、設定は次のように表示されます。](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

使用するセキュリティグループを変更する場合は、新しいセキュリティグループの名前でスクリプトを再実行します。

グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。
    
## <a name="step-3-verify-that-it-works"></a>手順 3: 動作することを確認する

変更が有効になるまでに30分以上かかる場合があります。 新しい設定を確認するには、次の手順を実行します。

1. グループを作成する権限を持たないユーザーのユーザーアカウントでサインインします。 作成したセキュリティ グループのメンバーまたは管理者ではないユーザーのアカウントを使用します。
    
2. [**Planner**] タイルを選択します。 
    
3. Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。 
  
4. プランとグループの作成が無効になっていることを示すメッセージが表示されます。

セキュリティグループのメンバーと同じ手順をもう一度試してください。

> [!NOTE]
> セキュリティグループのメンバーがグループを作成できない場合は、そのグループが [OWA メールボックス ポリシー](https://go.microsoft.com/fwlink/?linkid=852135) によってブロックされていないことを確認します。
    
## <a name="related-articles"></a>関連記事

[Office 365 PowerShell の概要](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[ExecutionPolicy の設定](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
