---
title: ATP の安全なリンクを使用して、リライトしないカスタムの Url リストを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 の ATP の安全なリンクポリシーでユーザーのブロックされたユーザーの Url を設定する方法と、ユーザーのグループの Url のリストを書き換えない方法について説明します。
ms.openlocfilehash: 183291ef5b43248c5ff3d4e63b03a170416119bf
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702538"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>ATP の安全なリンクを使用して、リライトしないカスタムの Url リストを設定する

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織に[カスタムのブロック](set-up-a-custom-blocked-urls-list-atp.md)された url を設定できます。これにより、ユーザーが電子メールメッセージや特定の Office ドキュメント内の web アドレス (url) をクリックしたときに、それらの url にアクセスできなくなります。 組織では、組織内の特定のグループに対してカスタムの "書き換え不可" リストを作成することもできます。 [書き換えない] リストを使用すると、一部のユーザーは、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)によってブロックされている url にアクセスすることができます。

この記事では、ATP の安全なリンクスキャンから除外する Url の一覧を指定する方法と、注意すべき重要な点について説明します。

## <a name="set-up-a-do-not-rewrite-list"></a>「書き換えない」リストを設定する

ATP の安全なリンク保護では、組織のブロックされた Url のリストや例外の「書き換えない」リストを含むいくつかのリストを使用します。 必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストを設定できます。 この操作は、組織内の特定の受信者に適用する安全なリンクポリシーを追加または編集するときに行います。

ATP ポリシーを編集 (または定義) するには、適切な役割が割り当てられている必要があります。 次の表は、いくつかの例を示しています。 詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

|役割  |参照先/割り当て方法  |
|---------|---------|
|グローバル管理者 |Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。 (詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)てを参照してください)。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください) |

> [!TIP]
> 役割とアクセス許可の詳細については、「[セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>ユーザー設定の「リライトしない」 Url リストを表示または編集するには

1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。

2. 左側のナビゲーションで、[**脅威管理** \> **ポリシー** \> **セーフリンク**] の下にあります。

3. [**特定の受信者に適用するポリシー** ] セクションで、[**新規**作成] (新しいボタンはプラス記号 () に似ています) を選択して、 **+** 新しいポリシーを作成します。 (または、既存のポリシーを編集することもできます)。<br/>![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. ポリシーの名前と説明を指定します。

5. [**次の url を書き換えない**] セクションで、[**有効な url を入力**してください] ボックスを選択し、url を入力して、プラス記号 (+) を選択します。

6. [**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。 [**追加**] を選択し、[ **OK]** を選択します。

7. 画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。

> [!NOTE]
> 組織の禁止された Url のカスタムリストを必ず確認してください。 「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-atp.md)」を参照してください。

## <a name="important-points-to-keep-in-mind"></a>留意すべき重要な点

- [書き換えない] ボックスの一覧で指定したすべての Url は、指定した受信者の ATP の安全なリンクスキャンから除外されます。

- ユーザーの操作を改善するために、よく使用される内部 Url を "リライトしない" リストに追加することを検討してください。 たとえば、Skype for Business や Sharepoint などのオンプレミスのサービスがある場合は、それらの Url をリストに追加してスキャンから除外することができます。

- 「書き換えない」リスト内に既に Url のリストがある場合は、そのリストを確認し、必要に応じてワイルドカードを追加してください。 たとえば、既存のリストにそのようなエントリがあり、 `https://contoso.com/a` ポリシーにそのようなサブパスを含める場合は、 `https://contoso.com/a/b` エントリにワイルドカードを追加して、次のように `https://contoso.com/a/*` します。

- ATP の安全なリンクポリシーの "書き込み不可" リストを指定する場合は、最大3つのワイルドカード () を含めることができ \* ます。 ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。 たとえば、エントリ `contoso.com` はと同じではありません `*.contoso.com/*` 。これに `*.contoso.com/*` より、ユーザーは指定したドメインのサブドメインとパスにアクセスできるようになります。

次の表に、入力できる内容と、それらのエントリの影響についての例を示します。

|エントリの例|機能|
|:-----|:-----|
|`contoso.com`|受信者がサブドメインやパスではなく、サイトにアクセスできるように `https://contoso.com` します。|
|`*.contoso.com/*`|受信者が、、、またはなどのドメイン、サブドメイン、およびパスにアクセスできるようにし `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` ます。 <br/><br/> このエントリには、次のように、 `*contoso.com*` 偽装している可能性のあるサイトが含まれていないため、 `https://www.falsecontoso.com` またはのようになります。`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|特定の受信者が、次のようなサブパスではなく、サイトにアクセスできるようにし `https://contoso.com/a` ます。`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|特定の受信者が、次のようなサブパスでサイトにアクセスできるようにします。 `https://contoso.com/a``https://contoso.com/a/b`|
