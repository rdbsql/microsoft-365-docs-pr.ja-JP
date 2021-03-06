---
title: 推奨される Teams ポリシー-Microsoft 365 Enterprise |Microsoft Docs
description: Teams の通信とファイルアクセスをセキュリティで保護する方法に関する Microsoft の推奨事項のポリシーを説明します。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: f1a4a4ea69efc3c68bdc8ed66aa18833a28feb94
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636725"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Teams のチャット、グループ、およびファイルを保護するためのポリシーの推奨事項

この記事では、推奨される id とデバイスアクセスポリシーを実装して、Teams のチャット、グループ、およびファイルや予定表などのコンテンツを保護する方法について説明します。 このガイダンスでは、[共通の id およびデバイスアクセスポリシー](identity-access-policies.md)と、Teams 固有の追加情報を作成します。 Teams は他の製品と統合されているため、 [SharePoint サイトとファイルをセキュリティで保護するためのポリシー推奨事項](sharepoint-file-access-policies.md)と、[電子メールをセキュリティ保護するためのポリシー推奨](secure-email-recommended-policies.md)事項も参照してください。

これらの推奨事項は、ニーズの粒度 (基準、機密、高規制) に基づいて適用できる、3つの異なるレベルのセキュリティと、Teams の保護に基づいています。 これらのセキュリティ層および推奨されるポリシーの詳細については、「 [id とデバイスのアクセス構成](microsoft-365-policies-configurations.md)」を参照してください。

この記事には、Teams の展開に関するその他の推奨事項が含まれており、組織外のユーザーを含む特定の認証状況について説明しています。 セキュリティを完全に向上させるには、このガイダンスに従う必要があります。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>他の依存サービスの前に Teams を使い始める

Microsoft Teams の使用を開始するために、依存サービスを有効にする必要はありません。 これらはすべて "機能します" ということになります。 ただし、次のものを管理するための準備が必要です。

- Microsoft 365 グループ
- SharePoint チーム サイト
- OneDrive for Business
- メールボックス
- ストリーミングビデオおよび Planner プラン (これらのサービスが有効になっている場合)

## <a name="updating-common-policies-to-include-teams"></a>共通ポリシーを更新して Teams を含める

次の図は、Teams のチャット、グループ、コンテンツを保護するために推奨されるポリシーのセットを示しています。 鉛筆アイコンは、クラウドアプリの割り当てに Teams および依存サービスが含まれることを確認するために再検討する必要があるポリシーを示しています。

![さまざまなデバイスで Microsoft Teams を使用する方法を示す図。](../media/identity-access-ruleset-teams.png)

Teams のクラウドアプリの割り当てに含める依存サービスは次のとおりです。

- Microsoft Teams
- Sharepoint Online と OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会議のレコーディング)
- Microsoft Planner (Planner タスクおよびプランデータ)

この表には、すべての Office アプリケーションに対して広範にルールが設定されている[共通の id およびデバイスアクセスポリシー](identity-access-policies.md)における再検討が必要なポリシーと、各ポリシーへのリンクが記載されています。

|保護レベル|ポリシー|Teams の実装に関するその他の情報|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|アプリの一覧に Teams および依存サービスが含まれていることを確認してください。 Teams にはゲストアクセスと外部アクセスのルールが含まれています。これについては、この記事の後半で説明します。|
|        |[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウドアプリの割り当てに Teams および依存するサービスを含めます。|
|        |[リスクの高いユーザーがパスワードを変更する必要がある](identity-access-policies.md#high-risk-users-must-change-password)|リスクの高いアクティビティがアカウントに対して検出された場合に、サインイン時に Teams ユーザーがパスワードを変更することを強制します。 アプリの一覧に Teams および依存サービスが含まれていることを確認してください。|
|        |[アプリデータ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|アプリの一覧に Teams および依存サービスが含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新します。|
|        |[承認済みアプリとアプリ保護を必要とする](identity-access-policies.md#require-approved-apps-and-app-protection)|このポリシーに Teams および依存するサービスを含めます。|
|        |[デバイスコンプライアンスポリシーの定義](identity-access-policies.md#define-device-compliance-policies)|このポリシーに Teams および依存するサービスを含めます。|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|このポリシーに Teams および依存するサービスを含めます。|
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams にはゲストアクセスと外部アクセスのルールが含まれています。これについては、この記事の後半で説明します。 このポリシーに Teams および依存するサービスを含めます。|
|         |[準拠*して*いる pc とモバイルデバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|このポリシーに Teams および依存するサービスを含めます。|
|**高度な規制**|[*常に*MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ユーザー id に関係なく、MFA は組織によって使用されます。 このポリシーに Teams および依存するサービスを含めます。
| | |

## <a name="teams-dependent-services-architecture"></a>Teams 依存サービスのアーキテクチャ

参考として、次の図は、サービスチームが依存していることを示しています。 詳細とその他の図については、「microsoft [Teams and related プロダクティビティ service In microsoft 365 IN IT アーキテクト](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects)」を参照してください。

![SharePoint Online、OneDrive for Business、および Exchange への Teams の依存関係を示す図。](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Teams でゲストおよび外部アクセスを有効にする

Azure AD では、ゲストユーザーと外部ユーザーは同じです。 これらの両方のユーザーの種類は Guest です。 ゲストユーザーは B2B ユーザーです。 Microsoft Teams は、アプリ内のゲストユーザーと外部ユーザーを区別します。 これらの各操作が Teams でどのように扱われるかを理解することは重要ですが、どちらの種類のユーザーも Azure AD の B2B ユーザーであり、B2B ユーザーの推奨ポリシーは両方に適用されます。 ゲストアクセスを許可するために推奨されるポリシーについては、「[ゲストおよび外部の B2B アクセスを許可するためのポリシー](identity-access-policies-guest-access.md)」を参照してください。

### <a name="guest-access-in-teams"></a>Teams でのゲストアクセス

企業または組織の内部にあるユーザーのポリシーに加えて、管理者はゲストアクセスを有効にして、ユーザーごとに、組織外のユーザーが Teams のリソースにアクセスしたり、グループの会話、チャット、会議などの内部ユーザーと対話したりすることができます。 ゲストアクセスの詳細については、次のリンクを参照してください。 [Teams ゲストアクセス](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Teams での外部アクセス

外部アクセスは、ゲストアクセスと混同されることがあるため、これらの2つの非内部アクセスメカニズムが実際に大きく異なることを明確にすることが重要です。 ゲストアクセスはユーザー単位で行われますが (一度に1人のユーザーを追加する)、管理者が外部アクセスを有効にすると、外部ドメインのすべてのユーザーを Teams に同時に追加することができます。 ただし、これらの外部ユーザーは、ゲストアクセスで追加された個人よりもアクセスと機能が少なくなります。 外部アクセスユーザーは、Teams を使用して内部ユーザーとチャットすることができます。

外部アクセスの詳細と、必要に応じてそれを実装する方法については、「 [Microsoft Teams で外部アクセスを管理](https://docs.microsoft.com/microsoftteams/manage-external-access)する」を参照してください。

## <a name="teams-policies"></a>Teams ポリシー

上記の一般的なポリシーの範囲外では、さまざまなチームの機能を管理するために構成できる Teams 固有のポリシーがあります。

### <a name="teams-and-channels-policies"></a>Teams およびチャネルのポリシー

Teams とチャネルは、Microsoft Teams でよく使用される2つの要素であり、teams やチャネルを使用する際にユーザーが実行できることとできないことを制御するために配置できるポリシーがあります。 グローバルチームを作成することはできますが、組織のユーザーが5000人以下の場合は、組織のニーズに合わせて、特定の目的のためにチームとチャネルを小さくした方が便利な場合があります。

既定のポリシーを変更するか、カスタムポリシーを作成することをお勧めします。このリンクでは、「 [Microsoft teams で teams ポリシーを管理する」に記載](https://docs.microsoft.com/microsoftteams/teams-policies)されているポリシーの管理について説明します。

### <a name="messaging-policies"></a>メッセージングポリシー

メッセージングやチャットは、既定のグローバルポリシーまたはカスタムポリシーを使用して管理することもできます。これにより、ユーザーは自分の組織に適した方法で相互に通信することができます。 この情報は、「 [Teams でのメッセージングポリシーの管理」](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)で確認できます。

### <a name="meeting-policies"></a>会議ポリシー

Teams の会議に関するポリシーを計画して実装しなくても、チームの討議は完了しません。 会議は、Teams の重要なコンポーネントであり、会議に関連するコンテンツの共有だけでなく、複数のユーザーに対して、ユーザーが正式に会うことができるようにしたり、一度に表示したりすることができます。 組織に適したポリシーを会議に沿って設定することが重要です。

詳細については、「 [Teams での会議ポリシーの管理」](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)を参照してください。

### <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

Teams では、チャネルや個人のチャットなど、さまざまな場所でアプリを使用することもできます。 セキュリティで保護されたコンテンツリッチな環境を維持するには、追加および使用できるアプリケーションに関するポリシーが必要です。

アプリのアクセス許可ポリシーの詳細については、「 [Microsoft Teams でアプリのアクセス許可ポリシーを管理](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)する」を参照してください。

## <a name="next-steps"></a>次の手順

[Exchange Online の条件付きアクセスを有効にする方法について説明します。](secure-email-recommended-policies.md)


