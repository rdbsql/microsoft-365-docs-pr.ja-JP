---
title: 通信コンプライアンスを使用して開始する
description: コミュニケーションコンプライアンスポリシーを設定して、レビューのために従業員の通信を構成します。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 8ec31bb08933ba9c1f0cc264bafc8d39bf64a003
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936852"
---
# <a name="get-started-with-communication-compliance"></a>通信コンプライアンスを使用して開始する

コミュニケーションコンプライアンスポリシーを使用して、内部または外部のレビューアーによる調査のために従業員の通信をキャプチャします。 通信コンプライアンスポリシーが組織内の通信の監視にどのように役立つかについては、「 [Microsoft 365 の通信コンプライアンスポリシー](communication-compliance.md)」を参照してください。 Microsoft Teams、Exchange Online、Yammer の通信で不快な言葉を監視するために、Contoso 社がどのようにコミュニケーションコンプライアンスポリシーを構成したかを確認したい場合は、この[ケーススタディー](communication-compliance-case-study.md)をご覧ください。

## <a name="before-you-begin"></a>はじめに

コミュニケーションの法令遵守を開始する前に、 [Microsoft 365 のサブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)とアドオンを確認する必要があります。 通信コンプライアンスにアクセスして使用するには、組織が次のいずれかのサブスクリプションまたはアドオンを所有している必要があります。

- Microsoft 365 E5 サブスクリプション (有料または試用版)
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 コンプライアンスアドオン
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 Insider リスク管理アドオン
- Microsoft 365 A5 サブスクリプション (有料または試用版)
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 コンプライアンスアドオン
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 Insider リスク管理アドオン
- Microsoft 365 G5 サブスクリプション (有料または試用版)
- Microsoft 365 G5 サブスクリプション + Microsoft 365 G5 コンプライアンスアドオン
- Microsoft 365 G5 サブスクリプション + Microsoft 365 G5 Insider リスク管理アドオン
- Office 365 Enterprise E5 サブスクリプション (有料または試用版)
- Office 365 Enterprise E3 サブスクリプション + Office 365 Advanced コンプライアンスアドオン (新しいサブスクリプションでは使用できなくなりました)。メモを参照してください。

通信コンプライアンスポリシーに含まれるユーザーには、上記のいずれかのライセンスを割り当てる必要があります。

>[!IMPORTANT]
>Office 365 Advanced コンプライアンスは、スタンドアロンサブスクリプションとして販売されなくなりました。 現在のサブスクリプションの有効期限が切れた場合、お客様は上記のサブスクリプションのいずれかに移行する必要があります。これには、同じまたは追加のコンプライアンス機能が含まれます。

既存の Office 365 Enterprise E5 プランを所有しておらず、insider リスク管理を試みる場合は、既存のサブスクリプションに[Microsoft 365 を追加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)するか、Office 365 Enterprise e5 の[試用版にサインアップ](https://www.microsoft.com/microsoft-365/enterprise)することができます。

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>手順 1 (必須): 通信のコンプライアンスのためのアクセス許可を有効にする

>[!Important]
>既定では、全体管理者は通信コンプライアンス機能にアクセスできません。 この手順で割り当てられる役割は、通信コンプライアンス機能がアクセス可能になる前に必要です。

Microsoft 365 コンプライアンスセンターのメニューオプションとして**通信のコンプライアンス**を実現するには、**監督レビュー管理者**の役割が割り当てられている必要があります。 **監督レビュー管理者**、**ケース管理**、**コンプライアンス管理者**、および**レビュー**の役割を持つレビュー担当者用の新しい役割グループを作成して、ポリシーが一致するメッセージを調査および修復する必要があります。

### <a name="create-a-new-role-group"></a>新しい役割グループを作成する

1. [https://protection.office.com/permissions](https://protection.office.com/permissions)Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインします。

2. セキュリティ &amp; /コンプライアンスセンターで、[**アクセス許可**] に移動します。 Office 365 で役割を表示および管理するためのリンクを選択します。

3. **[作成]** を選択します。

4. [**名前**] フィールドに、新しい役割グループにフレンドリ名を付けます。 [**次へ**] を選択します。

5. [**役割の選択**] を選択し、[**追加**] を選択します。 **監督レビュー管理者**、**ケース管理**、**コンプライアンス管理者**、および**レビュー**のチェックボックスをオンにし、[**追加**] を選択して、[**完了**] を選択します。 [**次へ**] を選択します。

    ![通信コンプライアンスに必要な役割グループ](../media/communication-compliance-role-groups-1.png)

6. [**メンバーの選択**] を選択し、[**追加**] を選択します。 [ポリシーの作成] と [ポリシーの一致でメッセージを管理する] を使用するすべてのユーザーおよびグループのチェックボックスをオンにし、[**追加** **] を選択します。** [**次へ**] を選択します。

7. [**役割グループの作成**] を選択します。

役割グループとアクセス許可の詳細については、「[Permissions in the Compliance Center (コンプライアンス センターのアクセス許可)](../security/office-365-security/protect-against-threats.md)」を参照してください。 

## <a name="step-2-required-enable-the-audit-log"></a>手順 2 (必須): 監査ログを有効にする

通信コンプライアンスには、警告を表示し、レビュー担当者が行った修復処置を追跡するための監査ログが必要です。 監査ログは、定義済みの組織ポリシーに関連付けられているすべてのアクティビティ、または通信コンプライアンスポリシーが変更されるたびに、その概要を示します。

監査を有効にするための詳細な手順について[は、「監査ログの検索を有効または無効](turn-audit-log-search-on-or-off.md)にする」を参照してください。 監査を有効にすると、監査ログの準備中で、準備が完了してから数時間で検索を実行できるというメッセージが表示されます。 この操作は1回だけ実行する必要があります。 監査ログの使用の詳細については、「 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)」を参照してください。

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>手順 3 (省略可能): 通信コンプライアンス用にグループをセットアップする

 通信コンプライアンスポリシーを作成する場合は、通信をレビューしたユーザーとレビューを実行するユーザーを定義します。 ポリシーでは、メール アドレスを使って、個人または複数人のグループを指定します。 セットアップを簡単にするために、コミュニケーションをレビューしたユーザーのためのグループを作成できます。 グループを使用している場合は、複数必要になる場合があります。 たとえば、2つの異なるユーザーグループ間の通信を監視する場合、または、監視されないグループを指定する場合などです。

次の表を使用して、通信コンプライアンスポリシー用に組織内のグループを構成する方法について説明します。

| **ポリシー メンバー** | **サポートされているグループ** | **サポートされていないグループ** |
|:-----|:-----|:-----|
|監督対象ユーザー <br> 非監督対象ユーザー | 配布グループ <br> Microsoft 365 グループ | 動的配布グループ |
| レビュー担当者 | なし | 配布グループ <br> 動的配布グループ <br> メールが有効なセキュリティ グループ |
  
ポリシーで配布グループを割り当てると、ポリシーは配布グループ内の各ユーザーからのすべての電子メールを監視します。 ポリシーに Microsoft 365 グループを割り当てると、そのグループに送信されるすべてのメールが、各グループメンバーが受信する個々の電子メールではなく、このポリシーによって監視されます。

Exchange オンプレミス展開または外部電子メールプロバイダーを使用している組織で、ユーザーのチームのチャットを監視する場合は、オンプレミスまたは外部のメールボックスを監視するユーザー用に配布グループを作成する必要があります。 この手順の後半では、ポリシーウィザードで [**ユーザーとグループの監視**] を選択して、この配布グループを割り当てます。

>[!IMPORTANT]
>組織がセキュリティ & コンプライアンスセンターでグラフィカルユーザーインターフェイスを使用してオンプレミスユーザーの Teams チャットデータを検索できるようにするには、Microsoft サポートを使用して要求をファイルにする必要があります。 詳細については、「[オンプレミスユーザーのクラウドベースのメールボックスの検索](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。

グループの設定の詳細については、次の記事を参照してください。

- [配布グループを作成して管理する](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Microsoft 365 グループの概要](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>手順 4 (省略可能): Yammer テナントがネイティブモードになっていることを確認する

ネイティブモードでは、すべての Yammer ユーザーが Azure Active Directory (AAD)、すべてのグループが Office 365 グループ、すべてのファイルが SharePoint Online に保存されます。 Yammer テナントは、コミュニケーションコンプライアンスポリシーのネイティブモードになっている必要があります。これをスキャンして、Yammer のプライベートメッセージとコミュニティの会話で、危険な会話をスキャンして識別します。

ネイティブモードでの Yammer の構成の詳細については、以下を参照してください。

- [Microsoft 365 の Yammer ネイティブモードの概要](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [Microsoft 365 のネイティブ モードで Yammer ネットワークを構成する](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>手順 5 (必須): 通信コンプライアンスポリシーを作成する
  
>[!Important]
>PowerShell を使用して通信コンプライアンスポリシーを作成し、管理することはできません。 これらのポリシーを作成および管理するには、 [Microsoft 365 コミュニケーションコンプライアンスソリューション](https://compliance.microsoft.com/supervisoryreview)のポリシー管理コントロールを使用する必要があります。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインします。

2. Microsoft 365 コンプライアンスセンターで、[**通信コンプライアンス**] を選択します。
  
3. [**ポリシー** ] タブを選択します。

4. [**ポリシーの作成**] を選択して、テンプレートから新しいポリシーを作成して構成するか、カスタムポリシーを作成して構成します。

    ポリシーを作成するポリシーテンプレートを選択する場合は、次の操作を行います。

    - ポリシー名を確認または更新します。 ポリシー名は、ポリシーの作成後に変更することはできません。
    - 除外するユーザーやグループの選択などを含めて、監督するユーザーまたはグループを選択します。
    - ポリシーのレビュー担当者を選択します。 レビュー担当者は個々のユーザーで、すべての校閲者が Exchange Online でホストされたメールボックスを持っている必要があります。 ここに追加されたレビュー担当者は、アラートを調査および修復ワークフローでエスカレーションする際に選択できるレビュー担当者です。 レビュー担当者がポリシーに追加されると、ポリシーへの割り当てを通知する電子メールメッセージを自動的に受信し、レビュープロセスに関する情報へのリンクを提供します。
    - 制限された条件フィールド (通常は、ポリシーに適用する機密情報の種類またはキーワードディクショナリ) を選択します。

    ポリシーウィザードを使用してカスタムポリシーを作成する場合は、次の操作を行います。

    - ポリシーに名前と説明を付けます。 ポリシー名は、ポリシーの作成後に変更することはできません。
    - 組織内のすべてのユーザー、特定のユーザーとグループ、または除外する他のユーザーとグループを含む、監督するユーザーまたはグループを選択します。
    - ポリシーのレビュー担当者を選択します。 レビュー担当者は個々のユーザーで、すべての校閲者が Exchange Online でホストされたメールボックスを持っている必要があります。 ここに追加されたレビュー担当者は、アラートを調査および修復ワークフローでエスカレーションする際に選択できるレビュー担当者です。 レビュー担当者がポリシーに追加されると、ポリシーへの割り当てを通知する電子メールメッセージを自動的に受信し、レビュープロセスに関する情報へのリンクを提供します。
    - Exchange、Microsoft Teams、Yammer、または Skype for Business など、スキャンする通信チャネルを選択します。 また、Microsoft 365 でコネクタを構成した場合は、サードパーティのソースをスキャンすることもできます。
    - 受信、送信、内部通信など、監視する通信方向を選択します。
    - 通信コンプライアンスポリシーの[条件](communication-compliance-feature-reference.md#ConditionalSettings)を定義します。 [メッセージ アドレス]、[キーワード]、[ファイルの種類]、および [サイズの一致条件] の中から選ぶことができます。
    - 機密情報の種類を含めるかどうかを選択します。 この手順では、既定およびカスタムの機密情報の種類を選択できます。 コミュニケーションコンプライアンスポリシーウィザードで、既存のカスタムの機密情報の種類またはカスタムキーワードディクショナリから選択します。 これらの項目は、必要に応じてウィザードを実行する前に作成できます。 コミュニケーションコンプライアンスポリシーウィザードから、新しい機密情報の種類を作成することもできます。
    - 分類子を有効にする場合に選択します。 分類子は、電子メールメッセージやその他の種類のテキストで送受信された不適切な言語を検出できます。

    >[!CAUTION]
    >組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、[**脅威**]、[**冒涜的表現**]、および [**ハラスメント**] の組み込み分類子を使用することをお勧めします。

    - レビューする通信の割合を定義します。
    - 選択したポリシーを確認し、ポリシーを作成します。

5. テンプレートを使用する場合は [**ポリシーの作成**] を選択し、カスタムポリシーウィザードを使用する場合は [**送信**] を選択します。

6. [**ポリシーが作成**されました] ページが表示され、ポリシーがアクティブ化され、どの通信が取得されるかについてのガイドラインが表示されます。

## <a name="step-6-optional-create-employee-notice-templates"></a>手順 6 (オプション): 従業員の通知テンプレートを作成する

関連付けられた従業員にアラーム通知を送信してポリシーの警告に応答するオプションを使用する場合は、組織内に少なくとも1つの通知テンプレートを作成する必要があります。 通知テンプレートフィールドは、通知修復プロセスの一環として送信される前に編集でき、コミュニケーションコンプライアンスポリシーごとにカスタマイズされた通知テンプレートを作成することをお勧めします。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインします。

2. Microsoft 365 コンプライアンスセンターで、[通信の**コンプライアンス**] に移動します。

3. [**通知テンプレート**] タブを選択してから、[**通知テンプレートの作成**] を選択します。

4. [**通知テンプレートの変更**] ページで、以下のフィールドに入力します。

    - 通知テンプレート名 (必須)
    - 送信元 (必須)
    - Cc および Bcc (省略可能)
    - 件名 (必須)
    - メッセージ本文 (必須)

5. [**保存**] を選択して、通知テンプレートを作成して保存します。

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>手順 7 (オプション): 通信コンプライアンスポリシーをテストする

通信コンプライアンスポリシーを作成した後、それをテストして、定義した条件がポリシーによって適切に適用されていることを確認することをお勧めします。 また、通信コンプライアンスポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテスト](create-test-tune-dlp-policy.md)することもできます。 テストする通信が取得されるように、ポリシーの時間をアクティブにする必要があることを確認してください。

コミュニケーションコンプライアンスポリシーをテストするには、次の手順を実行します。

1. テストするポリシーで定義された、監視対象のユーザーとしてサインインしているときに、電子メールクライアント、Microsoft Teams、または Yammer を開きます。
2. 通信コンプライアンスポリシーで定義した条件を満たすメール、Microsoft Teams チャット、または Yammer のメッセージを送信します。 このテストには、キーワード、添付ファイルのサイズ、ドメインなどを指定できます。ポリシーに構成された条件設定が制限を超えているか、厳しすぎるかを確認してください。

    > [!NOTE]
    > すべてのソースチャネルでの通信は、ポリシー内で完全に処理されるまでに最大24時間かかる場合があります。

3. コミュニケーションコンプライアンスポリシーで指定されたレビュー担当者として Microsoft 365 にサインインします。 [**通信コンプライアンス**  >  **アラート**に移動して、ポリシーのアラートを表示します。

4. 修復コントロールを使用してアラートを修復し、アラートが適切に解決されることを確認します。
