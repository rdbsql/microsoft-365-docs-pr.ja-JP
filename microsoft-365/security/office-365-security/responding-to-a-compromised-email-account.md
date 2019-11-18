---
title: 侵害された Office 365 電子メール アカウントへの対応
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 侵害された Office 365 電子メール アカウントを認識して対処する方法について説明します
ms.openlocfilehash: af57d1fb52718561b1d8e9feef90a46613d753ee
ms.sourcegitcommit: 8aa9f204b056f01bfb4c357347dc1592d0c9b688
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38669846"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="6e64a-103">侵害された Office 365 電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="6e64a-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="6e64a-104">**概要** 侵害された Office 365 電子メール アカウントを認識して対処する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="6e64a-105">侵害された Office 365 電子メール アカウントとは何か?</span><span class="sxs-lookup"><span data-stu-id="6e64a-105">What is a Compromised Email Account in Office 365?</span></span>

<span data-ttu-id="6e64a-p101">Office 365 のメールボックス、データ、およびその他のサービスへのアクセスは、ユーザー名とパスワードや暗証番号 (PIN) などの資格情報を使用して制御されます。意図したユーザー以外の何者かがこれらの資格情報を盗んだ場合、盗まれた資格情報は侵害されたと見なされます。攻撃者は盗んだ資格情報を使用して、正規のユーザーとしてサインインし、不正な操作を行うことができます。また、攻撃者は盗んだ資格情報を使用して、ユーザーの Office 365 メールボックス、SharePoint フォルダー、または OneDrive 内のファイルにアクセスできます。よく見られるのは、組織の内外の受信者に正規のユーザーとして電子メールを送り付ける攻撃者です。データが攻撃者によって外部の受信者に電子メールで送信される事象をデータ流出と言います。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p101">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="6e64a-112">侵害された Office 365 電子メール アカウントの兆候</span><span class="sxs-lookup"><span data-stu-id="6e64a-112">Symptoms of a Compromised Office 365 Email Account</span></span>

<span data-ttu-id="6e64a-p102">ユーザーが自分の Office 365 メールボックスでの異常な活動に気付いて報告してくる場合があります。よく見られる兆候を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p102">Users might notice and report unusual activity in their Office 365 mailboxes. Here are some common symptoms:</span></span>

- <span data-ttu-id="6e64a-115">電子メールの消失や削除などの不審な活動。</span><span class="sxs-lookup"><span data-stu-id="6e64a-115">Suspicious activity, such as missing or deleted emails.</span></span>
- <span data-ttu-id="6e64a-116">侵害されたアカウントから電子メールを受信したが、その送信者の**送信済みアイテム** フォルダーに対応する電子メールが存在しない。</span><span class="sxs-lookup"><span data-stu-id="6e64a-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>
- <span data-ttu-id="6e64a-p103">意図したユーザーまたは管理者が作成していない受信トレイ ルールの存在。このようなルールによって、自動的に不明なアドレスに電子メールが転送されたり、**メモ** フォルダー、**迷惑メール** フォルダー、または **RSS 購読**フォルダーに移動されたりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>
- <span data-ttu-id="6e64a-119">グローバル アドレス一覧内のユーザーの表示名が変更される。</span><span class="sxs-lookup"><span data-stu-id="6e64a-119">The user's display name might be changed in the Global Address List.</span></span>
- <span data-ttu-id="6e64a-120">ユーザーのメールボックスが電子メールの送信をブロックされる。</span><span class="sxs-lookup"><span data-stu-id="6e64a-120">The user's mailbox is blocked from sending email.</span></span>
- <span data-ttu-id="6e64a-121">Microsoft Outlook または Outlook on the web (旧名称は Outlook Web App) の送信済みアイテム フォルダーまたは削除済みアイテム フォルダーに "I'm stuck in London, send money" などのハッキングされたアカウント メッセージが格納される。</span><span class="sxs-lookup"><span data-stu-id="6e64a-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>
- <span data-ttu-id="6e64a-122">名前、電話番号、郵便番号などのめったに変更されないプロフィールが更新される。</span><span class="sxs-lookup"><span data-stu-id="6e64a-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>
- <span data-ttu-id="6e64a-123">複数のパスワードの変更など、異常な資格情報の変更が要求される。</span><span class="sxs-lookup"><span data-stu-id="6e64a-123">Unusual credential changes, such as multiple password changes are required.</span></span>
- <span data-ttu-id="6e64a-124">メールの転送が最近追加された。</span><span class="sxs-lookup"><span data-stu-id="6e64a-124">Mail forwarding was recently added.</span></span>
- <span data-ttu-id="6e64a-125">偽の銀行署名や処方薬署名など、通常とは異なる署名が最近追加された。</span><span class="sxs-lookup"><span data-stu-id="6e64a-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="6e64a-126">ユーザーが上記の兆候のいずれかを報告してきた場合は、詳しい調査を実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="6e64a-127">Microsoft 365 セキュリティ/コンプライアンス センターと Azure ポータルには、侵害が疑われるユーザー アカウントの活動を調査するためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6e64a-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="6e64a-p105">セキュリティ/コンプライアンス センターの Office 365 統合監査ログ - 不審な活動が発生する直前から現在の日付までの範囲で結果をフィルター処理すると、疑わしいアカウントのすべての活動を確認します。検索期間の活動はフィルター処理しないでください。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p105">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>
- <span data-ttu-id="6e64a-p106">Azure AD ポータルで利用可能な Azure AD サインイン ログとその他のリスク レポートを使用します。次の列の値を調査します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p106">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal. Examine the values in these columns:</span></span>
    - <span data-ttu-id="6e64a-132">IP アドレスの確認</span><span class="sxs-lookup"><span data-stu-id="6e64a-132">Review IP address</span></span>
    - <span data-ttu-id="6e64a-133">サインインの場所</span><span class="sxs-lookup"><span data-stu-id="6e64a-133">sign-in locations</span></span>
    - <span data-ttu-id="6e64a-134">サインインの時刻</span><span class="sxs-lookup"><span data-stu-id="6e64a-134">sign-in times</span></span>
    - <span data-ttu-id="6e64a-135">サインインの成功/失敗</span><span class="sxs-lookup"><span data-stu-id="6e64a-135">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="6e64a-136">電子メール機能をセキュリティで保護し、侵害が疑われる Office 365 アカウントとメールボックスを復元する方法</span><span class="sxs-lookup"><span data-stu-id="6e64a-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="6e64a-137">アカウントへのアクセスが回復されても、攻撃者がアカウントの制御を再開できるようなバック ドア エントリを追加している場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="6e64a-p107">次の手順を最後まで実行して、できるだけ早くアカウントへのアクセスを回復し、乗っ取り犯がアカウントの制御を再開できないことを確認する必要があります。次の手順は、乗っ取り犯がアカウントに追加したかもしれないバック ドア エントリを削除できるように支援します。この手順を完了したら、ウイルス スキャンを実行してコンピューターが侵害されていないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p107">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="6e64a-141">ステップ 1 ユーザーのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="6e64a-141">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="6e64a-142">この時点ではまだ攻撃者がメールボックスへのアクセス権を握っている可能性があるため、意図したユーザーに新しいパスワードを電子メールで送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="6e64a-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="6e64a-143">「[管理者: Office 365 Business のパスワードをリセットする](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)」の手順に従って、他のユーザーの Office 365 Business パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span></span>

<span data-ttu-id="6e64a-144">**メモ:**</span><span class="sxs-lookup"><span data-stu-id="6e64a-144">**Notes:**</span></span>
- <span data-ttu-id="6e64a-145">パスワードは、強力で、大文字と小文字、少なくとも 1 つの数字、および少なくとも 1 つの特殊文字が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e64a-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span> 
- <span data-ttu-id="6e64a-p108">直近の 5 つのパスワードのいずれかを再利用しないでください。パスワードの履歴要件によって最近のパスワードを再利用できる場合でも、攻撃者が推測できないパスワードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
- <span data-ttu-id="6e64a-148">オンプレミス ID が Office 365 とフェデレーションされている場合は、パスワードをオンプレミスで変更してから、侵害を管理者に報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="6e64a-p109">特に、管理者特権を持っているアカウントの侵害を避けるために、多要素認証 (MFA) を有効にすることを強くお勧めします。詳細については、[ここ](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p109">It is highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.  You can learn more [here](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="6e64a-151">ステップ 2 不審な電子メール転送アドレスを削除する</span><span class="sxs-lookup"><span data-stu-id="6e64a-151">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="6e64a-152">**[Microsoft 365 管理センター] > [アクティブなユーザー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-152">Open the **Microsoft 365 admin center > Active Users**.</span></span>
2. <span data-ttu-id="6e64a-153">対象のユーザー アカウントを探して、**[メール設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-153">Find the user account in question and expand **Mail Settings**.</span></span>
3. <span data-ttu-id="6e64a-154">**[メールの転送]** で、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-154">For **Email forwarding**, click **Edit**.</span></span>
4. <span data-ttu-id="6e64a-155">不審な転送アドレスを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-155">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="6e64a-156">ステップ 3 不審な受信トレイ ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="6e64a-156">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="6e64a-157">Outlook on the web を使用して、ユーザーのメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-157">Sign in to the user's mailbox using Outlook on the web.</span></span>
2. <span data-ttu-id="6e64a-158">歯車アイコンをクリックして、**[メール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-158">Click on the gear icon and click **Mail**.</span></span>
3. <span data-ttu-id="6e64a-159">**[受信トレイと一括処理ルール (Inbox and sweep rules)]** をクリックして、ルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-159">Click **Inbox and sweep rules** and review the rules.</span></span>
4. <span data-ttu-id="6e64a-160">不審なルールを無効にするか、削除します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-160">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="6e64a-161">ステップ 4 ユーザーのメールの送信をブロック解除する</span><span class="sxs-lookup"><span data-stu-id="6e64a-161">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="6e64a-162">侵害が疑われるメールボックスがスパム メールを送信するために不正に使用された場合は、メールボックスのメールの送信がブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-162">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>
1. <span data-ttu-id="6e64a-163">メールボックスのメールの送信をブロック解除するには、「[ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6e64a-163">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="6e64a-164">ステップ 5 オプション: ユーザー アカウントのサインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="6e64a-164">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e64a-165">アクセスを有効に戻しても安全なことが確認されるまでは、侵害が疑われるアカウントのサインインをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-165">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="6e64a-166">Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-166">Go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="6e64a-167">Microsoft 365 管理センターで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-167">In the Microsoft 365 admin center, select **Users**.</span></span>
3. <span data-ttu-id="6e64a-168">ブロックする従業員を選択してから、ユーザー ウィンドウの **[サインイン状態]** の横にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-168">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>
4. <span data-ttu-id="6e64a-169">**[サインイン状態]** ウィンドウで、**[サインインを許可されていない]** を選択してから、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-169">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span> 
5. <span data-ttu-id="6e64a-170">管理センターの左下のナビゲーション ウィンドウで、**[管理センター]** を展開し、**[Exchange]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-170">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>
6. <span data-ttu-id="6e64a-171">Exchange 管理センターで、**[受信者] > [メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-171">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>
7. <span data-ttu-id="6e64a-172">ユーザーを選択して、そのユーザーのプロパティ ページの **[モバイル デバイス]** で、**[Exchange ActivcSync を無効にする]** と \*\*[デバイス用の OWA を無効にする] \*\* をクリックし、両方に **[はい]** と答えます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-172">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>
8. <span data-ttu-id="6e64a-173">**[電子メールの接続性]** で、**[無効にする]** を選択し、**[はい]** と答えます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-173">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span> 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="6e64a-174">ステップ 6 オプション: すべての管理者役割グループから侵害が疑われるアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="6e64a-174">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="6e64a-175">管理者役割グループ メンバーシップは、アカウントをセキュリティで保護した後に復元できます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-175">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="6e64a-176">グローバル管理者アカウントで Microsoft 365 管理センターにサインインし、**[アクティブなユーザー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-176">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>
2. <span data-ttu-id="6e64a-177">侵害が疑われるアカウントを探して、そのアカウントに割り当てられた管理者役割が存在するかどうかを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-177">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>
3. <span data-ttu-id="6e64a-178">**[セキュリティとコンプライアンス センター]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-178">Open the **Security & Compliance Center**.</span></span>
4. <span data-ttu-id="6e64a-179">**[アクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-179">Click **Permissions**.</span></span>
5. <span data-ttu-id="6e64a-p110">侵害が疑われるアカウントが役割グループのメンバーかどうかを手動で確認します。そうだった場合: a. 役割グループをクリックして、**[役割グループの編集 (Edit Role Group)]** をクリックします。b. **[メンバーの選択 (Chose Members) ]** と **[編集]** をクリックして、役割グループからユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p110">Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:  a. Click the role group and click **Edit Role Group**.  b. Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>
6. <span data-ttu-id="6e64a-185">**[Exchange 管理センター]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-185">Open the **Exchange admin center**</span></span>
7. <span data-ttu-id="6e64a-186">**[アクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e64a-186">Click **Permissions**.</span></span>
8. <span data-ttu-id="6e64a-p111">侵害が疑われるアカウントが役割グループのメンバーかどうかを手動で確認します。そうだった場合: a. 役割グループをクリックして、**[編集]** をクリックします。b. **[メンバー]** セクションを使用して、役割グループからユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p111">Manually review the role groups to see if the suspected compromised account is a member of any of them. If it is:  a. Click the role group and click **Edit**.  b. Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="6e64a-192">ステップ 7 オプション: その他の予防手順</span><span class="sxs-lookup"><span data-stu-id="6e64a-192">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="6e64a-p112">送信済みアイテムを確認します。連絡先リストに掲載されている人にアカウントが侵害されたことを通知する必要があります。攻撃者は、彼らにお金を要求したり、あなたが外国で足留めされ、お金が必要だなどと偽ったり、彼らにウイルスを送り付けて彼らのコンピューターも乗っ取ろうとしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p112">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>
2. <span data-ttu-id="6e64a-p113">この Exchange アカウントを代替電子メール アカウントとして使用していた他のサービスが侵害されている場合があります。まず、Office 365 サブスクリプションに関する手順を実行してから、その他のアカウントに関する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p113">Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>
3. <span data-ttu-id="6e64a-198">電話番号や住所などの連絡先情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-198">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="6e64a-199">cybersecurity pro などの Office 365 の保護</span><span class="sxs-lookup"><span data-stu-id="6e64a-199">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="6e64a-p114">Office 365 サブスクリプションには、データとユーザーを保護するために使用可能な強力なセキュリティ機能のセットが付属しています。「[Office 365 のセキュリティ ロードマップ: 最初の 30 日間、90 日間、およびそれ以後の優先事項](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)」を使用して、Office 365 テナントをセキュリティで保護するためのマイクロソフト推奨ベスト プラクティスを実践します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p114">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="6e64a-p115">最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p115">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="6e64a-p116">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p116">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="6e64a-p117">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="6e64a-p117">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e64a-208">関連項目:</span><span class="sxs-lookup"><span data-stu-id="6e64a-208">See also:</span></span>

- [<span data-ttu-id="6e64a-209">Office 365 のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="6e64a-209">Security best practices for Office 365</span></span>](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [<span data-ttu-id="6e64a-210">Office 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="6e64a-210">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](/security/office-365-security/detect-and-remediate-outlook-rules-forms-attack.md)
- [<span data-ttu-id="6e64a-211">米国インターネット犯罪苦情センター</span><span class="sxs-lookup"><span data-stu-id="6e64a-211">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)
- [<span data-ttu-id="6e64a-212">米国証券取引委員会 - "フィッシング" 詐欺</span><span class="sxs-lookup"><span data-stu-id="6e64a-212">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)
- <span data-ttu-id="6e64a-213">迷惑メールを Microsoft および管理者に直接報告する場合に[迷惑メール報告アドインを使用する](https://support.office.com/ja-JP/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="6e64a-213">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/ja-JP/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>