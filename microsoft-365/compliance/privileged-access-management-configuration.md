---
title: 特権アクセス管理の使用を開始する
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Office 365 での特権アクセス管理の有効化と構成の詳細については、この記事を使用してください。
ms.openlocfilehash: 4bae6d311b3447534165ee803d7094e5797a9b1c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936322"
---
# <a name="get-started-with-privileged-access-management"></a>特権アクセス管理の使用を開始する

このトピックでは、組織で特権アクセス管理を有効にして構成する手順を説明します。 Microsoft 365 管理センターまたは Exchange 管理 PowerShell のいずれかを使用して、特権アクセスを管理および使用することができます。

## <a name="before-you-begin"></a>はじめに

特権アクセス管理を使い始める前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)とアドオンを確認する必要があります。 特権アクセス管理にアクセスして使用するには、組織が次のいずれかのサブスクリプションまたはアドオンを所有している必要があります。

- Microsoft 365 E5 サブスクリプション (有料または試用版)
- Microsoft 365 E3 サブスクリプション (または Office 365 E3 サブスクリプション + Enterprise Mobility and Security E3 サブスクリプション) + Microsoft 365 E5 コンプライアンスアドオン
- Microsoft 365、Office 365、Exchange、SharePoint、または OneDrive for Business のサブスクリプション + Microsoft 365 E5 Insider リスク管理アドオン  
- Microsoft 365 A5 サブスクリプション (有料または試用版)
- Microsoft 365 A3 サブスクリプション (または Office 365 A3 サブスクリプション + Enterprise Mobility and Security A3 サブスクリプション) + Microsoft A5 コンプライアンスアドオン
- 任意の Microsoft 365、Office 365、Exchange、SharePoint、または OneDrive for エデュケーションサブスクリプション + Microsoft 365 A5 Insider リスク管理アドオン
- Office 365 Enterprise E5 サブスクリプション (有料または試用版)
- Office 365 Enterprise E3 サブスクリプション + Office 365 Advanced コンプライアンスアドオン (新しいサブスクリプションでは使用できなくなりました)。メモを参照してください。

特権アクセス管理要求を送信および応答するユーザーには、上記のいずれかのライセンスが割り当てられている必要があります。

>[!IMPORTANT]
>Office 365 Advanced コンプライアンスは、スタンドアロンサブスクリプションとして販売されなくなりました。 現在のサブスクリプションの有効期限が切れた場合、お客様は上記のサブスクリプションのいずれかに移行する必要があります。これには、同じまたは追加のコンプライアンス機能が含まれます。

既存の Office 365 Enterprise E5 プランを持っておらず、特権アクセス管理を実行する場合は、 [microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)を既存の office 365 サブスクリプションに追加するか、Microsoft 365 Enterprise E5 の[試用版にサインアップ](https://www.microsoft.com/microsoft-365/enterprise)することができます。

## <a name="enable-and-configure-privileged-access-management"></a>特権アクセス管理を有効にして構成する

次の手順に従って、組織内で特権アクセスを設定して使用します。

- [手順 1: 承認者のグループを作成する](privileged-access-management-configuration.md#step1)

    特権アクセスの使用を開始する前に、昇格されたタスクおよび権限のあるタスクへのアクセスを要求するための承認権限を必要とするユーザーを決定します。 承認者グループの一部であるユーザーは、アクセス要求を承認することができます。 このグループを有効にするには、Office 365 でメールが有効なセキュリティグループを作成します。

- [手順 2: 特権アクセスを有効にする](privileged-access-management-configuration.md#step2)

    特権アクセスは、既定の承認者グループを使用して Office 365 で明示的に有効にする必要があります。これには、特権アクセス管理アクセス制御から除外する一連のシステム アカウントが含まれます。

- [手順 3: アクセスポリシーを作成する](privileged-access-management-configuration.md#step3)

    承認ポリシーを作成すると、個々のタスクでスコープを設定する特定の承認要件を定義できます。 承認の種類のオプションは**自動**または**手動**です。

- [手順 4: 特権アクセス要求を送信/承認する](privileged-access-management-configuration.md#step4)

    有効にすると、特権アクセスは関連付けられた承認ポリシーが定義されているすべてのタスクにて承認が必要になります。 承認ポリシーに含まれるタスクの場合、タスクを実行するために必要なアクセス権限を持つには、ユーザーはアクセスを要求し、アクセスが許可されている必要があります。

承認が与えられると、アクセス要求したユーザーは目的のタスクを実行でき、特権アクセスはユーザーに代わってタスクを承認および実行します。 承認は、要求された期間 (既定の期間は 4 時間) にわたって有効で、その間依頼者は目的のタスクを複数回実行できます。 これらのすべての実行はログに記録され、セキュリティとコンプライアンスの監査で利用されます。 

>[!NOTE]
>Exchange 管理 PowerShell を使用して特権アクセスを有効にし、構成する場合は、「[複数要素認証を使用して Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)に接続する」の手順に従って、Office 365 資格情報を使用して Exchange online powershell に接続します。 Exchange Online PowerShell への接続中に特権アクセスを有効にする手順を使用して、組織で多要素認証を有効にする必要はありません。 多要素認証を使用して接続すると、要求に署名するために特権アクセスで使用される OAuth トークンが作成されます。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>手順 1: 承認者のグループを作成する

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、 **[グループ**  >  **の追加]** を選びます。

3. [**メールが有効なセキュリティグループ**] を選択し、新しいグループの**名前**、**グループ電子メールアドレス**、および**説明**フィールドを入力します。

4. グループを保存します。  グループが完全に構成され、Microsoft 365 管理センターに表示するには、数分かかることがあります。

5. 新しい承認者のグループを選択し、[**編集**] を選択してグループにユーザーを追加します。

6. グループを保存します。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>手順 2: 特権アクセスを有効にする

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**権限のあるタスクの承認を必須**にする] コントロールを有効にします。

4. 手順1で作成した承認者のグループを**既定の承認者グループ**として割り当てます。

5. **保存**して**閉じ**ます。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

特権アクセスを有効にし、承認者のグループを割り当てるには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

例:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>システムアカウント機能を使用して、組織内の特定のオートメーションが特権アクセスに依存せずに機能できるようにすることができます。ただし、そのような除外を定期的に行うことをお勧めします。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>手順 3: アクセスポリシーを作成する

組織に対して最大30の特権アクセスポリシーを作成し、構成することができます。

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**ポリシーの構成**] を選択し、[**ポリシーの追加**] を選択します。

5. ドロップダウンフィールドで、組織に適切な値を選択します。
    
    **ポリシーの種類**: タスク、役割、役割グループ

    **ポリシースコープ**: 交換

    **ポリシー名**: 利用可能なポリシーから選択します。

    **承認の種類**: 手動または自動

    **承認グループ**: 手順 1で作成した承認者グループを選択します。

6. [**作成**] を選択し、[**閉じる**] をクリックします。 ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

承認ポリシーを作成して定義するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

例:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>手順 4: 特権アクセス要求を送信/承認する

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>特権タスクを実行するための昇格認証の要求

特権アクセスの要求は、要求が送信されてから最大24時間有効です。 承認または拒否されない場合、要求は期限切れになり、アクセスは承認されません。

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**新しい要求**] を選択します。 ドロップダウンフィールドで、組織に適切な値を選択します。

    **要求の種類**: タスク、役割、役割グループ

    **要求スコープ**: 交換

    **要求名**: 利用可能なポリシーから選択します。

    **期間 (時間)**: アクセスを希望する時間数。 要求可能な時間数に制限はありません。

    **Comments**: アクセス要求に関連するコメントのテキストフィールド

5. [**保存**] を選択し、[**閉じる**] をクリックします。 要求は、電子メールを介して承認者のグループに送信されます。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

Exchange Online PowerShell で次のコマンドを実行して、承認要求を作成し、承認者のグループに送信します。

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

例:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>昇格要求の状態を表示する

承認要求が作成されると、昇格要求の状態は、管理センターまたは Exchange 管理 PowerShell で、関連付けられている要求 ID を使用して確認できます。

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**表示**] を選択して、送信された要求を**保留**、**承認**、**拒否**、または**顧客のロックボックス**の状態でフィルター処理します。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

Exchange Online PowerShell で次のコマンドを実行して、特定の要求 ID の承認要求の状態を表示します。

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

例:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>昇格認証要求を承認する

承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知を受信し、要求 ID に関連付けられている要求を承認できます。 アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. 詳細を表示し、要求に対してアクションを実行するには、リストされている要求を選択します。

5. [**承認**] を選択して要求を承認するか、[**拒否**] を選択して要求を拒否します。 以前に承認された要求では、 **Revoke**を選択することによってアクセスを取り消すことができます

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

昇格認証要求を承認するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

例:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

昇格認証要求を拒否するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

例:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Office 365 で特権アクセスポリシーを削除する

組織で不要になった場合は、特権アクセスポリシーを削除することができます。

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**構成ポリシー**] を選択します。

5. 削除するポリシーを選択し、[ポリシーの**削除**] を選択します。

6. **[閉じる]** を選択します。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

特権アクセスポリシーを削除するには、Exchange Online Powershell で次のコマンドを実行します。

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Office 365 で特権アクセスを無効にする

必要に応じて、組織の特権アクセス管理を無効にすることができます。 特権アクセスを無効にしても、関連付けられている承認ポリシーまたは承認グループは削除されません。

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. 管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [**特権アクセス制御の承認を必須**にする] を有効にします。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell

特権アクセスを無効にするには、Exchange Online Powershell で次のコマンドを実行します。

```PowerShell
Disable-ElevatedAccessControl
```
