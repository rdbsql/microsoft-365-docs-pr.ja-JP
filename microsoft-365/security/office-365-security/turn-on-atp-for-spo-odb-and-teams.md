---
title: Office 365 の ATP-SharePoint、OneDrive、& Teams をオンにする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 検出されたファイルに対して通知を設定する方法など、SharePoint、OneDrive、Teams の ATP を有効にする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 976911abe047be350ae6c64409cd6607ea75de7a
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811076"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[Office 365 ATP For SharePoint、OneDrive、Microsoft Teams では](atp-for-spo-odb-and-teams.md)、組織が悪意のあるファイルを誤って共有することを防止します。 悪意のあるファイルが検出されると、そのファイルはブロックされるようになり、組織のセキュリティチームによって追加の操作が行われるまで、そのファイルを開いたり、コピー、移動、または共有することができなくなります。 この記事では、SharePoint、OneDrive、Teams の ATP を有効にし、検出されたファイルについて通知する通知を設定し、次の手順を実行します。

ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。 次の表では、いくつかの例について説明します。

|役割|参照先/割り当て方法|
|---------|---------|
|グローバル管理者|Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。 (詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)てを参照してください)。|
|セキュリティ管理者|Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理|Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください)|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする

**この手順を開始する前に、Microsoft 365 環境の監査ログが既に有効になっていることを確認して**ください。 これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。 詳細については、「[監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」をご覧ください。

1. に移動 [https://protection.office.com](https://protection.office.com) し、職場または学校のアカウントでサインインします。

2. [セキュリティ & コンプライアンスセンター] の左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー**の \> **安全な添付ファイル**] を選択します。

   ![[セキュリティ & コンプライアンスセンター] で、[脅威管理ポリシー] を選択します。 \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. **[SharePoint、OneDrive、および Microsoft Teams に対して ATP を有効にする]** をオンにします。

   ![SharePoint Online、OneDrive for Business、Microsoft Teams の Advanced Threat Protection を有効にします。](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. **[保存]** をクリックします。

5. 組織の[安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)と[安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認し、必要に応じて編集します。

6. 勧めグローバル管理者または SharePoint Online 管理者として、 _DisallowInfectedFileDownload_パラメーターを*true*に設定して**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します。

   - このパラメーターを*true*に設定すると、検出されたファイルのすべてのアクション (削除を除く) がブロックされます。 ユーザーは、検出されたファイルを開いたり、移動、コピー、または共有したりできません。

   - パラメーターを*false*に設定すると、削除とダウンロード以外のすべてのアクションがブロックされます。 ユーザーは、リスクを容認し、検出されたファイルをダウンロードすることを選択できます。

7. 変更がすべての Microsoft 365 データセンターに蔓延するまで最大30分かかります。

8. 勧め検出されたファイルの通知の設定に進みます。

Microsoft 365 での PowerShell の使用の詳細については、「 [Manage microsoft 365 With powershell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)」を参照してください。

ファイルが悪意のあるものとして検出された場合のユーザーの操作の詳細については、「 [SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合の対処](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)方法」を参照してください。

## <a name="set-up-alerts-for-detected-files"></a>検出されたファイルの通知を設定する

SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるものとして識別された場合に通知を受け取るには、警告を設定します。

1. [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、 **[通知の**管理] を選択し \> **Manage alerts**ます。

2. [**新しい通知ポリシー**] を選択します。

3. 通知の名前を指定します。 たとえば、ライブラリに悪意のあるファイルを入力することができます。

4. 通知の説明を入力します。 たとえば、SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出されたときに管理者に通知を入力できます。

5. [**この通知を送信するタイミング**] セクションで、次の操作を行います。

   a. [**アクティビティ**] リストで、[**検出されたマルウェア (ファイル内**)] を選択します。

   b. [**ユーザー** ] フィールドは空のままにします。

6. [**この通知を送信する**ユーザー...] セクションで、悪意のあるファイルが検出されたときに通知を受信する必要がある1つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者を選択します。

7. **[保存]** をクリックします。

通知の詳細については、「[セキュリティ & コンプライアンスセンターでアクティビティ警告を作成](../../compliance/create-activity-alerts.md)する」を参照してください。

## <a name="next-steps"></a>次の手順

1. [SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する](malicious-files-detected-in-spo-odb-or-teams.md)

2. [Microsoft 365 で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)
