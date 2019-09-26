---
title: 機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。機密ラベルでは、コンテンツの保護のために暗号化を使用できます。
ms.openlocfilehash: ea7eda3558313389bfa2bc752a469e00cc7ae577
ms.sourcegitcommit: 328b31f69663669b3c656b2e4db529f70d1c753e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "37148481"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a>機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する

機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。たとえば、機密ラベルに対応する暗号化の設定によって、次のようにコンテンツを保護できます。

- 組織内のユーザーのみが機密ドキュメントや電子メールを開けるようにする。
- 宣伝広告用のドキュメントや電子メールは、マーケティング部門のユーザーのみが編集および印刷できるようにして、その他の組織内のユーザーは閲覧のみできるようにする。
- 内部の再編成に関するニュースが含まれている電子メールは、ユーザーが転送や情報のコピーをできないようにする。
- ビジネス パートナーに送信する現行の価格リストは、指定した日付以降は開けないようにする。

ドキュメントや電子メールを暗号化するときには、次のようにしてコンテンツへのアクセスが制限されます。

- 暗号化の解除は、ラベルの暗号化設定で許可されているユーザーのみが可能です。
- 暗号化は、ファイルの場所 (組織内外) を問わず、ファイル名が変更されていても維持されます。
- 保存中 (OneDrive アカウントなど) と転送中 (送信中の電子メールなど) の両方で暗号化されています。

最後に、管理者として、秘密度ラベルを作成するときに、次のいずれかを選択できます。

- **アクセス許可を割り当てます**。これにより、どのユーザーがそのラベルのコンテンツにどのアクセス許可を取得するかを正確に決定します。
- ラベルをコンテンツに適用するときに、**ユーザーがアクセス許可を割り当てる**ことができます。 このようにして、組織内のユーザーに、共同作業を行って作業を完了するために必要な柔軟性を与えることができます。

暗号化の設定は、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、または Office 365 セキュリティ/コンプライアンス センターで機密ラベルを作成するときに使用できます。 左側のナビゲーションで、[**分類**]  >  [**秘密度ラベル**]  >  [**ラベルの作成**] の順に選択します。

## <a name="how-encryption-works"></a>暗号化のしくみ

暗号化には、Azure Rights Management (Azure RMS) を使用します。Azure RMS は、暗号化ポリシー、ID ポリシー、および認証ポリシーを使用します。詳細については、「[Azure Rights Management とは](https://docs.microsoft.com/ja-JP/azure/information-protection/what-is-azure-rms)」を参照してください。

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a>機密ラベルに対する暗号化を有効にする方法

開始するには、単に [**暗号化**] を [**オン**] に切り替えてから、次のいずれかを選択します。

- **アクセス許可を割り当てます**。これにより、どのユーザーがそのラベルのコンテンツにどのアクセス許可を取得するかを正確に決定することができます。 詳細については、次のセクション「[アクセス許可を割り当てる](#assign-permissions-now)」を参照してください。
- ラベルをコンテンツに適用するときに、**ユーザーがアクセス許可を割り当てる**ことができます。 このようにして、組織内のユーザーに、共同作業を行って作業を完了するために必要な柔軟性を与えることができます。 詳細については、次のセクション「[ユーザーがアクセス許可を割り当てる](#let-users-assign-permissions)」を参照してください。

たとえば、最も機密性の高いコンテンツに適用される**極秘**という名前の秘密度ラベルがある場合、誰がそのコンテンツに対してどのタイプのアクセス許可を取得するかを決定することができます。

あるいは、**業務契約**という名前の秘密度ラベルがあり、組織のワークフローで従業員がこのコンテンツでアドホック ベースで異なるユーザーと共同作業する必要がある場合、ラベルを割り当てるときに従業員にアクセス許可を与えるユーザーを決定できるようにすることができます。 この柔軟性により、ユーザーの生産性が向上し、特定のシナリオに対処するために管理者に新しい機密度ラベルを更新または作成を要求することを減らすことができます。

![ユーザーまたは管理者が定義したアクセス許可を追加するオプション](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a>アクセス許可を割り当てる

以下のオプションを使用して、このラベルが適用される電子メールやドキュメントにアクセスできるユーザーを制御します。 次の操作を実行できます:

1. **ラベル付けされたコンテンツへのアクセスに有効期限を設定します。** 指定の日付または指定の日数 (ラベル適用後の経過日数) で有効期限が切れます。この期限が切れると、ユーザーはラベル付きのアイテムを開けなくなります。日付を指定すると、現在のタイム ゾーンでその日付の午前 0 時まで有効になります (一部のメール クライアントでは、キャッシュ メカニズムがあるため、有効期限が適用されず、有効期限を過ぎたメールが表示されることがある点に注意してください)。

2. **オフライン アクセス**を禁止、常に許可、または指定の日数 (ラベル適用後の経過日数) で許可します。オフライン アクセスを禁止または日数で制限すると、そのしきい値に達したときに、ユーザーは再認証される必要があり、ユーザーのアクセスがログに記録されます。詳細については、Rights Management 使用ライセンスに関する次のセクションを参照してください。

![管理者が定義したアクセス許可の設定](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a>オフライン アクセスのための Rights Management 使用ライセンス

ユーザーが機密ラベルで保護されているドキュメントや電子メールをオフラインで開くと、そのコンテンツの Azure Rights Management 使用ライセンスがユーザーに付与されます。この使用ライセンスは、ドキュメントまたは電子メールに対するユーザーの使用権とコンテンツの暗号化に使用された暗号化キーが含まれている証明書です。この使用ライセンスには、有効期限日 (設定されている場合) と使用ライセンスの有効期間も含まれています。

有効期限日が設定されていない場合、テナントに対する使用ライセンスの既定の有効期間は 30 日間です。使用ライセンスの有効期間中は、そのコンテンツに対してユーザーが再認証または再承認されることはありません。これにより、ユーザーは保護されたドキュメントまたは電子メールをインターネット接続なしで継続して開くことができます。使用ライセンスの有効期間が切れると、保護されたドキュメントまたは電子メールの次回のユーザー アクセス時に、ユーザーの再認証または再承認が必要になります。

再認証だけでなく、ポリシーとユーザー グループ メンバーシップの再評価も実行されます。そのため、ユーザーが最後にコンテンツにアクセスした後でポリシーやグループ メンバーシップに変更が加えられていると、同じドキュメントや電子メールに対して異なるアクセス結果がユーザーに示されることがあります。

既定の 30 日の設定を変更する方法については、「[Rights Management 使用ライセンス](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-management-use-license)」を参照してください。

### <a name="assign-permissions-to-specific-users-or-groups"></a>特定のユーザーまたはグループにアクセス許可を割り当てる

特定のユーザーにアクセス許可を付与することで、ラベル付きコンテンツの操作を特定のユーザーにのみ許可することができます。

そのようにするには、次の簡単な 2 段階の手順を実行します。

1. まず、ラベル付きコンテンツへのアクセス許可を割り当てるユーザーまたはグループを追加します。
2. 次に、該当するユーザーに付与するラベル付きコンテンツへのアクセス許可を選択します。

![ユーザーにアクセス許可を割り当てる際のオプション](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a>ユーザーまたはグループの追加

アクセス許可を割り当てるときには、次の選択が可能です。

- 組織内のすべてのユーザー (すべてのテナント メンバー)。この設定ではゲスト アカウントが除外されます。
- 特定のユーザーまたは電子メールが有効なセキュリティ グループ、配布グループ、Office 365 グループ、または動的配布グループ。 
- 組織外の電子メール アドレスまたはドメイン (gmail.com、hotmail.com、outlook.com など)。

すべてのテナント メンバーを選択する場合やディレクトリを参照する場合は、ユーザーまたはグループに電子メール アドレスが必要になります。

ベスト プラクティスとして、ユーザーではなくグループを使用します。この方針により、シンプルな構成を維持できます。

#### <a name="choose-permissions"></a>アクセス許可の選択

該当するユーザーまたはグループに付与するアクセス許可を選択するときには、次のいずれかを選択できます。

- 既定の権限のグループ (「共同制作者」や「レビュー担当者」など) で[事前定義されたアクセス許可レベル](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)。
- カスタムの権限のグループ。この場合は任意のアクセス許可を選択できます。

それぞれの具体的なアクセス許可に関する詳細については、「[使用権限と説明](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)」を参照してください。  

![既定またはカスタムのアクセス許可を選択する際のオプション](media/Sensitivity-Choose-permissions-settings.png)

同じラベルで異なるユーザーに異なるアクセス許可を付与できます。たとえば、次に示すように、単一のラベルで一部のユーザーを「レビュー担当者」として割り当てて、別のユーザーを「共同作成者」として割り当てることができます。

このようにするには、ユーザーまたはグループを追加し、それらにアクセス許可を割り当てて、その設定を保存します。その後で、この手順 (ユーザーの追加とアクセス許可の割り当て) を繰り返して、そのたびに保存します。この手順は、異なるユーザーに異なるアクセス許可を定義することが必要になるたびに実行できます。

![異なるアクセス許可を持つ異なるユーザー](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>常にフル コントロールを持つ Rights Management 発行者 (機密ラベルを適用するユーザー)

機密ラベルに対する暗号化には Azure RMS が使用されます。ユーザーがドキュメントや電子メールを保護するために Azure RMS を使用して機密ラベルを適用すると、そのユーザーはそのコンテンツに対する Rights Management 発行者になります。

Rights Management 発行者には、常に、ドキュメントや電子メールに対するフル コントロールのアクセス許可が付与されます。さらに、次のことが可能になります。

- 保護設定に有効期限日が含まれている場合、Rights Management 発行者は、その期日が過ぎていてもドキュメントや電子メールを開いて編集できます。
- Rights Management 発行者は、常に、オフラインでドキュメントや電子メールにアクセスできます。
- Rights Management 発行者は、失効後のドキュメントも開くことができます。

詳細については、「[Rights Management 発行者と Rights Management 所有者](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)」を参照してください。

## <a name="let-users-assign-permissions"></a>ユーザーがアクセス許可を割り当てる

これらのオプションを使用すると、ユーザーがコンテンツに機密度ラベルを手動で適用するときにアクセス許可を割り当てることができます。

- Outlook では、ユーザーは [**転送不可**] オプションと同等の制限を適用することができます。 このオプションは Windows での Outlook でネイティブにサポートされており、Azure Information Protection 統合ラベル付けクライアントをインストールする必要はありません。
- Word、PowerPoint、Excel で、ユーザーは特定のユーザー、グループ、または組織のアクセス許可レベルを選択するよう求められます。 このオプションはこれらの Office アプリではネイティブにサポートされていないため、ユーザーは Azure Information Protection 統合ラベル付けクライアントをインストールする必要があります。

これらのオプションは、機密度ラベルが表示されるアプリを決定します。

- 機密度ラベルで Outlook オプションのみが有効になっている場合、ラベルは Outlook でのみユーザーに表示されます。
- 機密度ラベルで Word、PowerPoint、Excel オプションのみが有効になっている場合、ラベルはこれらのアプリでのみユーザーに表示されます。
- 機密度ラベルの両方のオプションが有効になっている場合、利用可能なすべてのアプリ (Outlook、Word、PowerPoint、Excel) のユーザーにラベルが表示されます。

ユーザーがアクセス許可を割り当てることができる機密度ラベルは、ユーザーが手動でのみコンテンツに適用できます。自動適用したり、推奨ラベルとして使用したりすることはできません。

> [!NOTE]
> ユーザーがアクセス許可を割り当てることができるようになるには、Azure Information Protection サブスクリプションが必要です。 この機能を Word、PowerPoint、Excel で使用するには、[Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)をダウンロードしてインストールする必要があります。 これらの Office アプリでは、Azure Information Protection クライアントを必要としないように、この機能のネイティブ サポートに取り組んでいます。 また、クライアントは Windows でのみ実行されるため、この機能は Mac、iOS、Android、または Web 用 Office ではまだサポートされていません。

![ユーザー定義のアクセス許可の暗号化設定](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a>Outlook の制限

Outlook では、ユーザーがメッセージにアクセス許可を割り当てることができる機密度ラベルを適用する場合、制限は [転送不可] オプションと同じです。 メッセージの上部にラベル名と説明が表示されます。これは、コンテンツが保護されていることを示します。 Word、PowerPoint、Excel ([次のセクション](#word-powerpoint-and-excel-permissions)参照) とは異なり、ユーザーは特定のアクセス許可を選択するよう求められません。

![Outlook のメッセージに適用される機密度ラベル](media/sensitivity-label-outlook-protection-applied.png)

[転送不可] オプションがメールに適用されると、メールは暗号化され、受信者は認証する必要があります。 それにより、受信者はそれを転送したり、印刷したり、コピーしたりすることができなくなります。 たとえば、Outlook クライアントでは、[転送] ボタン、[名前を付けて保存] および [印刷] メニュー オプションは使用できず、[宛先]、[CC]、または [BCC] ボックスで受信者を追加または変更することはできません。

メールに添付されている保護されていない Office ドキュメントは、自動的に同じ制限を継承します。 これらのドキュメントに適用される使用権は、[コンテンツの編集]、[編集]、[保存]、[表示]、[開く]、[読み取り]、および [マクロの許可] です。 ユーザーが添付ファイルに別の使用権を要求する場合、または添付ファイルがこの継承された保護をサポートする Office ドキュメントでない場合は、メールに添付する前にファイルを保護する必要があります。

### <a name="word-powerpoint-and-excel-permissions"></a>Word、PowerPoint、および Excel のアクセス許可

Word、PowerPoint、および Excel では、ユーザーがドキュメントにアクセス許可を割り当てることができる機密度ラベルを適用すると、次のようにコンテンツを保護するように求められます。

その場合、ユーザーは次のことを行うことができます。

- ビューアー ([表示のみ] アクセス許可を割り当てる) または共同作成者 ([表示]、[編集]、[コピー]、および [印刷] アクセス許可を割り当てる) などのアクセス許可レベルを選択します。
- ユーザー、グループ、または組織を選択します。 これには、組織内外のユーザーが含まれます。
- 選択したユーザがコンテンツにアクセスできなくなる有効期限を設定します。 詳細については、上記のセクション「[オフライン アクセスのための Rights Management 使用ライセンス](#rights-management-use-license-for-offline-access)」を参照してください。

![ユーザーがカスタムのアクセス許可で保護するためのオプション](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a>ラベルが適用された場合の既存の暗号化

機密ラベルをコンテンツに適用する前に、ユーザーが他の保護設定を適用してコンテンツを既に暗号化している場合があります。 たとえば、ユーザーが以下を適用している場合があります。

- **転送不可**オプション。
- Azure Information Protection の統合ラベル付けクライアントを使用したカスタム保護。
- ラベルには関連付けされずにコンテンツを暗号化する Azure Rights Management Service (RMS) テンプレート。

次の表は、機密ラベルがコンテンツに適用されたときに既存の暗号化がどうなるかについての説明です。
<br/>
<br/>

| |**ユーザーが暗号化をオフにして機密ラベルを適用する**|**ユーザーが暗号化をオンにして機密ラベルを適用する**|**ユーザーが保護を解除してラベルを適用する**<sup>1</sup>|
|:-----|:-----|:-----|:-----|
|**転送不可**|メール - 保護が解除されます<br/>ドキュメント - 保護が維持されます|ラベルの保護が適用されます|**転送不可**が削除されます|
|**カスタム保護**<sup>1</sup>|保護が維持されます|ラベルの保護が適用されます|カスタム保護が解除されます|
|**Azure RMS テンプレート**|保護が維持されます|ラベルの保護が適用されます|カスタム保護が解除されます|

<sup>1</sup>これらは、Azure Information Protection のラベル付けクライアントでのみサポートされています。

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a>OneDrive および SharePoint に暗号化されたコンテンツを保存する

OneDrive および SharePoint に保存されているファイルに暗号化を適用すると、サービスは該当するファイルのコンテンツを処理できなくなります。そのため、共同編集、電子情報開示、検索、Delve などの共同作業機能が動作しなくなります。さらに、データ損失防止 (DLP) ポリシーはメタデータ (Office 365 のラベルを含む) にのみ作用し、暗号化されたファイルのコンテンツ (ファイル内のクレジット カード番号など) には作用しなくなります。

これは、OneDrive および SharePoint に保存されているコンテンツにのみ当てはまります。Exchange Online では、メール フロー ルール (トランスポート ルールとも呼ばれる) で[スーパー ユーザー アカウント](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-super-users)が使用されるため、暗号化されたコンテンツのスキャンと DLP ポリシーの強制適用が可能です。

## <a name="important-prerequisites"></a>重要な前提条件

暗号化を使用する前に、次のタスクの実行が必要になることがあります。

### <a name="activating-azure-rights-management"></a>Azure Rights Management を有効化する

機密ラベルでの暗号化を使用する場合は、Azure Rights Management サービスがテナントで有効化されている必要があります。新しいテナントでは、このサービスが既定でオンになっていますが、手動で有効化することが必要になる場合もあります。詳細については、「[Rights Management をアクティブにする](https://docs.microsoft.com/ja-JP/azure/information-protection/activate-service)」を参照してください。

### <a name="configure-exchange-for-azure-information-protection"></a>Azure Information Protection 用に Exchange を構成する

ユーザーが Outlook で電子メールの保護のためにラベルを適用するまでは、Azure Information Protection 用に Exchange を構成する必要はありません。ただし、Exchange が Azure Information Protection 用に構成されるまで、Exchange には Azure Rights Management 保護の使用よる完全な機能が備わりません。
 
たとえば、ユーザーは保護された電子メールを携帯電話や Outlook on the web で表示できません。また、保護された電子メールは検索用のインデックスを作成できません。さらに、Rights Management 保護用に Exchange Online DLP を構成することもできません。 

このような追加のシナリオを Exchange でサポートする場合は、次の項目を参照してください。

- Exchange Online の場合は、「[Exchange Online: IRM 構成](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-office365#exchange-online-irm-configuration)」の説明を参照してください。
- Exchange On-Premises の場合は、[RMS コネクタを展開して Exchange サーバーを構成する](https://docs.microsoft.com/ja-JP/azure/information-protection/deploy-rms-connector)必要があります。 