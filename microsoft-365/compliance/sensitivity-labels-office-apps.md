---
title: Office アプリで秘密度ラベルを使用する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: ユーザーがデスクトップ、モバイル、および web 用の Office アプリで機密ラベルを操作する方法と、機密ラベルをサポートするアプリについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9ed6e163915bd8cdf63e7f37bf92065943d71fb
ms.sourcegitcommit: e6bf1af2d5cf54c3fcc3fa916abe268fc96bdd4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45189468"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Office アプリで秘密度ラベルを使用する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft 365 コンプライアンスセンターまたは同等のラベル付けセンターから機密ラベルが[公開](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)されている場合は、作成または編集時にデータを分類して保護するために、ユーザーが Office アプリに表示され始めます。

この記事の情報を使用して、Office アプリの機密ラベルを正常に管理するのに役立ちます。 たとえば、組み込みのラベルをサポートするために必要な最小限のバージョンのアプリを特定し、Azure Information Protection のユニファイドラベルクライアントと他のアプリやサービスとの互換性について理解します。

## <a name="labeling-client-for-desktop-apps"></a>デスクトップアプリ用のクライアントにラベルを付ける

Windows と Mac 用の Office デスクトップアプリに組み込まれている機密ラベルを使用するには、サブスクリプション版の Office を使用する必要があります。 このラベル付けクライアントは、office 2016 または Office 2019 などのスタンドアロンエディションの Office をサポートしていません。

これらのスタンドアロンエディションの Windows コンピューターで機密ラベルを使用するには、 [Azure Information Protection のユニファイドラベルクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)をインストールします。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>アプリでの機密ラベル機能のサポート

各機能について、次の表に、組み込みのラベル付けを使用して機密ラベルをサポートするために、そのアプリに必要な最小バージョンを示します。 または、ラベル機能がパブリックプレビューであるか、今後のリリースのレビューの下にある場合。

新しいバージョンのアプリは、異なる更新プログラムチャネルに対してさまざまなタイミングで利用可能になります。 必要な新しいラベル機能をテストできるように、更新プログラムチャネルを構成する方法などの詳細については、「 [Microsoft 365 アプリの更新プログラムチャネルの概要](https://docs.microsoft.com/DeployOffice/overview-update-channels)」を参照してください。 プライベートプレビューの新機能は表に含まれていませんが、 [Microsoft Information Protection のプライベートプレビュープログラム](https://aka.ms/mip-preview)を使用するように組織を nominating すれば、これらのプレビューに参加できます。

> [!NOTE]
> Office アプリの更新プログラムチャネルの名前が最近変更されました。 たとえば、月次 Channel が現在のチャネルで、Office Insider がベータチャネルになっています。 詳細については、「 [Microsoft 365 アプリの更新プログラムチャネルの変更点](https://docs.microsoft.com/deployoffice/update-channels-changes)」を参照してください。

Windows コンピューター上でのみ実行される Azure Information Protection のユニファイドラベルクライアントをインストールすると、追加機能を利用できるようになります。 詳細については、「 [Windows コンピューターのラベルクライアントを比較する](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)」を参照してください。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel、PowerPoint の機密ラベル機能

IOS および Android の場合: これらの最小バージョンが表示されている場合は、 [Office アプリ](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)でも機密ラベル機能をサポートしています。

|機能                                                                                                        |Windows デスクトップ |Mac デスクトップ |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[ラベルを変更する場合は、根拠を設定する必要があります。](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[カスタムヘルプページへのヘルプリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[コンテンツをマークする](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上          | 16.21 +     | 2.21以上 | 16.0.11231以上 | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | [現在のチャネル](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview)(2003 以降) | 16.35 +   | レビュー   | レビュー         | レビュー                                                        |
|[ラベル分析を使用](label-analytics.md)してラベルの使用を表示し、管理者向けにデータを送信する                      | レビュー            | レビュー        | レビュー   | レビュー         | レビュー                                                        |
|[ユーザーが電子メールとドキュメントにラベルを適用することを必須にする](sensitivity-labels.md#what-label-policies-can-do)   | レビュー            | レビュー        | レビュー   | レビュー         | レビュー                                                        |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | [現在のチャネル](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview)へのロールアウト (2006 以降)                                  | レビュー | レビュー | レビュー | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|ラベル付きおよび保護されたドキュメントでの[自動保存](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)と[共同編集](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4)をサポートする | レビュー | レビュー | レビュー | レビュー | [はい-オプトイン](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook の機密ラベル機能

|機能                                                                                                        |Windows デスクトップ上の Outlook |Outlook on Mac デスクトップ  |Outlook on iOS |Outlook on Android |Outlook on the web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[ラベルを手動で適用、変更、または削除する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[既定のラベルを適用する](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[ラベルを変更する場合は、根拠を設定する必要があります。](sensitivity-labels.md#what-label-policies-can-do)                     | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[カスタムヘルプページへのヘルプリンクを提供する](sensitivity-labels.md#what-label-policies-can-do)                       | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[コンテンツをマークする](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[アクセス許可を今すぐ割り当てる](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[ユーザーがアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910以上                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | はい               |
|[ラベル分析を使用](label-analytics.md)してラベルの使用を表示し、管理者向けにデータを送信する                      | レビュー                       | レビュー                    | レビュー           | レビュー               | レビュー               |
|[ユーザーが電子メールとドキュメントにラベルを適用することを必須にする](sensitivity-labels.md#what-label-policies-can-do)   | レビュー                       | レビュー                    | レビュー           | レビュー               | レビュー               |
|[機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)                    | プレビュー:[ベータチャネル](https://office.com/insider)と現在のチャネルへのロールアウト[(プレビュー)](https://office.com/insider)                      | レビュー                    | レビュー           | レビュー               | はい |
|

## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 組み込みのラベルクライアントとその他のラベルソリューション

Office 組み込みのラベルクライアントは、次の管理センターから、機密ラベルと機密ラベルポリシー設定をダウンロードします。

- Microsoft 365 コンプライアンス センター
- Microsoft 365 セキュリティ センター
- Office 365 セキュリティ/コンプライアンス センター

Office 組み込みのラベルクライアントを使用するには、リストされた管理センターの1つと、[サポートされているバージョンの office](#support-for-sensitivity-label-capabilities-in-apps)に対して、1つ以上の[ラベルポリシーを発行](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)する必要があります。

これらの条件の両方が満たされている場合に、Office の組み込みラベルクライアントを無効にする必要がある場合は、次のグループポリシー設定を使用します。

1. [**ユーザーの構成]/[管理用テンプレート]、[Microsoft Office 2016** ]、[セキュリティ設定] の順に移動します。

2. [ **Office の秘密度] 機能を使用して、機密ラベルを適用して0に表示するように設定し**ます。 **0** 
 
グループポリシーまたは[Office cloud Policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)を使用して、この設定を展開します。 この設定は、Office アプリが再起動されたときに有効になります。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 組み込みのラベルクライアントと Azure Information Protection クライアント

ユーザーが Azure Information Protection クライアントのいずれか ([ユニファイドラベルクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)または[クラシッククライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)) をインストールしている場合、既定では、組み込みのラベルクライアントは Office アプリで無効になっています。 

Office アプリ用の Azure Information Protection クライアントではなく、組み込みのラベルを使用するには、前のセクションの手順を使用しますが、グループポリシー設定を設定するには、 **office の秘密度機能を使用**して、機密ラベルを**1**に適用および表示します。 

または、Office アドイン、 **Azure Information Protection**を無効化または削除します。 この方法は、単一のコンピューターとアドホックテストに適しています。 手順については、「 [Office プログラムでアドインを表示、管理、およびインストール](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)する」を参照してください。 

この Office アドインを無効にするか削除すると、Office アプリの外部でファイルに引き続きラベルを付けることができるように、Azure Information Protection クライアントがインストールされたままになります。 たとえば、ファイルエクスプローラーや PowerShell を使用します。

Azure Information Protection クライアントおよび Office 組み込みのラベルクライアントによってサポートされる機能については、「Azure Information Protection のドキュメントで[Windows コンピューターに使用するラベル付けクライアントを選択する](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)」を参照してください。

## <a name="protection-templates-and-sensitivity-labels"></a>保護テンプレートと機密ラベル

Office 365 メッセージの暗号化に対して定義するような管理者定義の[保護テンプレート](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)は、組み込みのラベル付けを使用している場合、office アプリでは表示されません。 この単純化された操作性は、暗号化が有効になっている機密ラベルに同じ設定が含まれるため、保護テンプレートを選択する必要がないことを反映しています。

既存の保護テンプレートをラベルに変換する必要がある場合は、Azure ポータルと、次の手順を使用します。[テンプレートをラベルに変換するに](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)は、次の手順を実行します。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Information Rights Management (IRM) のオプションと機密ラベル

暗号化を適用するように構成した機密ラベルユーザーが独自の暗号化設定を指定するために、複雑さを排除します。 多くの Office アプリでは、Information Rights Management (IRM) のオプションを使用して、ユーザーがこれらの個々の暗号化設定を手動で構成することができます。 たとえば、Windows アプリの場合は次のようになります。

- ドキュメントの場合:**ファイル**  >  **情報**  >  **保護ドキュメント**に  >  **よるアクセスの制限**
- 電子メールの場合: [**オプション**] タブから [**暗号化**] を > 
  
ユーザーが最初にドキュメントまたは電子メールにラベルを付けると、独自の暗号化設定を使用して、ラベルの構成設定をいつでも変更できます。 例:

- ユーザーが**機密 \ All Employees**ラベルをドキュメントに適用します。このラベルは、組織内のすべてのユーザーの暗号化設定を適用するように構成されています。 このユーザーは、組織外のユーザーへのアクセスを制限するように IRM 設定を手動で構成します。 最終的には、"**社外秘**" というラベルが付けられた文書が作成されますが、組織内のユーザーは意図したとおりに開くことができません。

- ユーザーが [**社外秘**] のラベルを電子メールに適用し、この電子メールは、[**転送不可**] の暗号化設定を適用するように設定されています。 このユーザーは、電子メールが無制限になるように IRM 設定を手動で構成します。 最終的には、電子メールが送信者によって転送されることがありますが、**機密 \ 受信者のみ**のラベルがある場合があります。

- ユーザーがドキュメントに **[全般**] ラベルを適用します。このラベルは、暗号化を適用するように構成されていません。 このユーザーは、ドキュメントへのアクセスを制限するように IRM 設定を手動で構成します。 最終的には、 **[General** ] というラベルの付いたドキュメントが生成されますが、暗号化も適用されるため、一部のユーザーは意図したとおりに開くことができません。

ドキュメントまたは電子メールに既にラベルが付けられている場合、ユーザーはこれらの操作を実行できます。コンテンツが暗号化されていない場合、または[利用状況](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)のエクスポートまたはフルコントロールがある場合です。 

有用なレポートで一貫したラベルを使用するには、ユーザーがドキュメントを保護するためのラベルのみを適用するための適切なラベルとガイダンスを提供します。 例:

- ユーザーが自分のアクセス許可を割り当てる必要がある例外の場合は、[ユーザーが自分のアクセス許可を割り当てる](encryption-sensitivity-labels.md#let-users-assign-permissions)ためのラベルを提供します。 

- 暗号化を適用するラベルを選択した後、ユーザーが手動で暗号化を削除するのではなく、ユーザーが同じ分類のラベルを必要とするが暗号化を必要としない場合は、sublabel の代替手段を提供します。 次に例を示します。
    - **社外秘すべての従業員**
    - **機密情報 (すべての暗号化なし)**

> [!NOTE]
> ユーザーが SharePoint または OneDrive に格納されているラベル付きドキュメントから手動で暗号化を削除し、 [sharepoint と onedrive で Office ファイルの機密ラベルを有効に](sensitivity-labels-sharepoint-onedrive-files.md)している場合は、次回ドキュメントにアクセスまたはダウンロードしたときに、ラベルの暗号化が自動的に復元されます。 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>ファイル、電子メール、および添付ファイルに機密ラベルを適用する

ユーザーは、ドキュメントまたは電子メールごとに、一度に1つのラベルだけを適用できます。

添付ファイルが含まれている電子メールメッセージにラベルを付けると、添付ファイルはラベルを継承しません。1つの例外があります。

- 添付ファイルは、暗号化を適用しないラベル付きの Office ドキュメントで、電子メールメッセージに適用するラベルは暗号化を適用します。 この場合、メールで送信された Office ドキュメントは、その電子メールのラベルを暗号化設定で継承します。

無視しない場合は: 

- 添付ファイルにラベルがある場合は、元のラベルが適用されたままになります。
- 添付ファイルがラベルなしで暗号化されている場合、暗号化は保持されますが、ラベルは付けられません。
- 添付ファイルにラベルが付いていない場合は、ラベルが付いていないままになります。

## <a name="sensitivity-label-compatibility"></a>機密ラベルの互換性

**Rms-なりアプリ**の場合: 機密ラベルをサポートしていない[rms なりアプリケーション](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)で、ラベル付きの暗号化されたドキュメントまたは電子メールを開くと、そのアプリは暗号化と権限の管理を引き続き適用します。

**Azure Information protection クライアントを使用**すると、ドキュメントやメールに適用する機密ラベルを、Azure information protection クライアントを使用して Office 組み込みのラベルクライアントを使用して表示および変更できます。また、その他の方法もあります。

**他のバージョンの office**の場合: 承認されたユーザーは、他のバージョンの office でラベル付きドキュメントとメールを開くことができます。 ただし、サポートされている Office バージョンまたは Azure Information Protection クライアントを使用してのみ、ラベルを表示または変更できます。 サポートされている Office アプリのバージョンは、[前のセクション](#support-for-sensitivity-label-capabilities-in-apps)に一覧表示されています。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>機密ラベルで保護された SharePoint および OneDrive ファイルのサポート

SharePoint または OneDrive のドキュメントに対して web 上の office に office の組み込みラベルクライアントを使用するには、 [sharepoint および onedrive で office ファイルの機密ラベルを有効に](sensitivity-labels-sharepoint-onedrive-files.md)していることを確認してください。

## <a name="support-for-external-users-and-labeled-content"></a>外部ユーザーとラベル付きコンテンツのサポート

ドキュメントまたは電子メールにラベルを付けると、ラベルは、テナントとラベル GUID を含むメタデータとして保存されます。 機密ラベルをサポートする Office アプリによってラベル付きドキュメントまたは電子メールが開かれると、このメタデータが読み込まれ、ユーザーが同じテナントに属している場合に限り、そのラベルがアプリに表示されます。 たとえば、Word、PowerPoint、Excel の組み込みのラベルの場合、ラベル名がステータスバーに表示されます。 

つまり、別のラベル名を使用する別の組織とドキュメントを共有する場合、各組織は、ドキュメントに適用されている独自のラベルを表示できます。 ただし、適用されたラベルの次の要素は、組織外のユーザーに表示されます。

- コンテンツのマーキング。 ヘッダー、フッター、またはウォーターマークを適用すると、ラベルはコンテンツに直接追加され、他のユーザーが変更または削除するまでは表示されたままになります。

- 暗号化を適用したラベルの基になる保護テンプレートの名前と説明。 この情報は、ドキュメントの上部にあるメッセージバーに表示され、ドキュメントを開くことが承認されたユーザーと、そのドキュメントの使用権限に関する情報を提供します。

### <a name="sharing-encrypted-documents-with-external-users"></a>外部ユーザーとの暗号化されたドキュメントの共有

組織内のユーザーへのアクセスを制限するだけでなく、Azure Active Directory にアカウントを持つ他のすべてのユーザーへのアクセスを拡張することもできます。 すべての Office アプリとその他の[なりアプリケーション](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)は、ユーザーが正常に認証された後に、暗号化されたドキュメントを開くことができます。

外部ユーザーが Azure Active Directory にアカウントを持っていない場合は、テナントでそれらのユーザーのゲストアカウントを作成できます。 電子メールアドレスの場合は、既に使用されている電子メールアドレスを指定できます。 たとえば、Gmail のアドレスです。 [Sharepoint および onedrive で Office ファイルの機密ラベルを有効](sensitivity-labels-sharepoint-onedrive-files.md)にしている場合は、このゲストアカウントを使用して、sharepoint または onedrive で共有ドキュメントにアクセスすることもできます。

外部ユーザーは、Windows で Microsoft 365 アプリ ([以前の Office 365 アプリ](https://docs.microsoft.com/deployoffice/name-change)) を使用している場合に、暗号化されたドキュメントの microsoft アカウントを使用して作成することもできます。 この機能は、macOS、Android、iOS ではまだサポートされていません。 たとえば、あるユーザーが暗号化されたドキュメントを共有し、暗号化設定でその Gmail 電子メールアドレスを指定したとします。 このユーザーは、自分の Gmail 電子メールアドレスを使用する独自の Microsoft アカウントを作成できます。 その後、このアカウントを使用してサインインすると、そのユーザーに指定されている使用制限に従って、ドキュメントを開いて編集できるようになります。 このシナリオのチュートリアルの例については、「[保護されたドキュメントを開いて編集する](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)」を参照してください。

> [!NOTE]
> Microsoft アカウントの電子メールアドレスは、暗号化設定のアクセスを制限するために指定された電子メールアドレスと一致している必要があります。

Microsoft アカウントを持つユーザーが、この方法で暗号化されたドキュメントを開くと、同じ名前のゲストアカウントが存在しない場合、テナントのゲストアカウントが自動的に作成されます。 ゲストアカウントが存在する場合は、Windows デスクトップアプリから暗号化されたドキュメントを開くことに加えて、ブラウザー (web 上の Office) を使用して SharePoint および OneDrive でドキュメントを開くことができます。 

ただし、レプリケーションの待ち時間があるため、自動ゲストアカウントはすぐには作成されません。 ラベル暗号化設定の一部として個人の電子メールアドレスを指定する場合は、Azure Active Directory に対応するゲストアカウントを作成することをお勧めします。 その後、ユーザーがこのアカウントを使用して組織から暗号化されたドキュメントを開く必要があることを知らせます。

> [!TIP]
> 外部ユーザーがサポートされている Office クライアントアプリを使用していることを確認できないため、ゲストアカウントを作成した後に SharePoint と OneDrive からリンクを共有する方法は、外部ユーザーとのセキュリティで保護されたグループ作業をサポートするためのより信頼性の高い方法です。

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office アプリがコンテンツのマーキングと暗号化を適用するとき

Office アプリは、使用するアプリによっては、機密ラベル付きのコンテンツマーキングと暗号化を異なる方法で適用します。

| アプリ | コンテンツのマーケティング | 暗号化 |
| --- | --- | --- |
| すべてのプラットフォームの Word、Excel、PowerPoint | 直ちに | 直ちに |
| Outlook for PC と Outlook for Mac | Exchange Online が電子メールを送信した後 | 直ちに |
| Outlook on the web、iOS、および Android | Exchange Online が電子メールを送信した後 | Exchange Online が電子メールを送信した後 |
|

Office アプリの外部のファイルに機密ラベルを適用するソリューションは、ファイルにラベル付きメタデータを適用します。 このシナリオでは、ラベルの構成からのコンテンツマークはファイルに挿入されませんが、暗号化が適用されます。 

これらのファイルが Office デスクトップアプリで開かれると、コンテンツマーキングは Azure Information Protection のユニファイドラベルクライアントによって自動的に適用されます。 デスクトップ、モバイル、または web アプリに組み込みのラベル付けを使用しても、コンテンツマーキングは自動的には適用されません。

Office アプリの外部に機密ラベルを適用する方法には、次のようなシナリオがあります。

- Azure Information Protection の統一されたラベル付けクライアントからのスキャナー、ファイルエクスプローラー、および PowerShell 

- SharePoint および OneDrive の自動ラベル付けポリシー

- Power BI からラベル付きで暗号化されたデータのエクスポート

- Microsoft Cloud App Security

これらのシナリオでは、Office アプリを使用することにより、組み込みのラベルを持つユーザーは、一時的に現在のラベルを削除または置換してから、元のラベルを再適用することで、ラベルのコンテンツマーキングを適用できます。

## <a name="end-user-documentation"></a>エンドユーザードキュメント

- [Office 内の文書やメールに機密ラベルを適用する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office ファイルに機密ラベルを適用した場合の既知の問題](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)