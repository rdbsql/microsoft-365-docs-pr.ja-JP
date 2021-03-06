---
title: SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルの機密ラベルサポートを有効にすることができます。
ms.openlocfilehash: a6826be5cccf89d3b2e48e0e37df9a9263e4a8a7
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201511"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にする前に、web 上の Office に[機密ラベル](sensitivity-labels.md)を適用することはできません。 リボンに [**秘密度**] ボタン、またはステータスバーに適用されるラベル名が表示されません。 さらに、デスクトップアプリを使用してファイルにラベルを付け、それらを SharePoint または OneDrive に保存する場合、ラベルが暗号化を適用した場合、サービスはこれらのファイルのコンテンツを処理できません。 共同編集、電子情報開示、データ損失防止、検索、およびその他の共同作業機能は、これらの状況では機能しません。

SharePoint および OneDrive で Office ファイルの機密ラベルを有効にする場合、これらすべての機能が有効になります。 機密ラベルをユーザーに表示するだけでなく、クラウドベースのキーを使用した暗号化を含む新しいファイルと変更されたファイルに対して ([二重キー暗号化](double-key-encryption.md)を使用しない)。

- Word、Excel、PowerPoint のファイルでは、SharePoint がラベルを認識し、暗号化されたファイルのコンテンツを処理できるようになりました。

- これらのファイルを SharePoint または OneDrive からダウンロードまたはアクセスすると、ラベルの機密ラベルと任意の暗号化設定が適用され、保存されているすべての場所でファイルが保持されます。 ラベルのみを使用してドキュメントを保護するように、ユーザーガイダンスを提供します。 詳細については、「 [Information Rights Management (IRM) のオプション」および「機密ラベル](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)」を参照してください。

- ラベル付きで暗号化されたファイルをユーザーが SharePoint にアップロードする場合は、少なくともそれらのファイルに対する表示権限が必要です。 たとえば、SharePoint の外部にあるファイルを開くことができます。 この最小使用率が適切でない場合は、アップロードは成功しますが、SharePoint はラベルを認識しないため、ファイルの内容を処理できません。

- Web 上の Office (Word、Excel、PowerPoint) を使用して、暗号化を適用する機密ラベルが設定された Office ファイルを開いて編集します。 暗号化によって割り当てられたアクセス許可が適用されます。 Word on the web では、これらの文書を編集するときに自動ラベルを使用することもできます。

- 外部ユーザーは、ゲストアカウントを使用して、暗号化のラベルが付けられたドキュメントにアクセスできます。 詳細については、「[サポートの外部ユーザーとラベル付きコンテンツ](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)」を参照してください。 

- Office 365 電子情報開示では、これらのファイルのフルテキスト検索がサポートされています。 データ損失防止 (DLP) ポリシーは、これらのファイルのコンテンツをサポートします。

> [!NOTE]
> オンプレミスキーで暗号化が適用されている場合、キー管理トポロジ (HYOK)、または[二重キー暗号化](double-key-encryption.md)を使用している場合、ファイルコンテンツを処理するための SharePoint の動作は変わりません。
>
> Sharepoint の動作は、SharePoint の既存のラベル付きファイルと暗号化されたファイルに対しても変わりません。 これらのファイルが新しい機能を利用できるようにするには、コマンドを実行して SharePoint と OneDrive の機密ラベルを有効にした後、それらのファイルをダウンロードしてアップロードするか、または編集する必要があります。 その後、SharePoint はこれらのファイルを処理できます。 たとえば、それらは検索と電子情報開示の結果として返されます。

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にした後、次の3つの新しい[監査イベント](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)を使用して、Sharepoint と onedrive のドキュメントに適用される機密ラベルを監視できます。
- **ファイルに適用された機密ラベル**
- **ファイルに適用された機密ラベルの変更**
- **ファイルから削除された機密ラベル**

次のビデオ (オーディオなし) を見て、新しい機能を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

SharePoint および OneDrive では、Office ファイルの機密ラベルを無効にするかどうかをいつでも選択できます ([オプトアウト)](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 。

Sharepoint Information Rights Management (IRM) を使用して SharePoint でドキュメントを現在保護している場合は、このページの「 [Sharepoint Information Rights management (irm) と [秘密度ラベル](#sharepoint-information-rights-management-irm-and-sensitivity-labels)] セクションを確認してください。 

## <a name="requirements"></a>要件

これらの新機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。 現在 Azure Information Protection のラベルがある場合は、それらを機密ラベルに移行してから、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。 手順については、「 [Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)」を参照してください。

OneDrive sync app バージョン19.002.0121.0008 以降、またはバージョン19.002.0107.0008 以降の Mac を使用します。 これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。 詳細については、 [OneDrive リリースノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。 SharePoint と OneDrive で Office ファイルの機密ラベルを有効にした後、古いバージョンの同期アプリを実行しているユーザーには、更新を求めるメッセージが表示されます。

## <a name="limitations"></a>制限事項

- SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに機密ラベルが自動的に適用されることはありません。 代わりに、SharePoint および OneDrive で Office ファイルの機密ラベルを有効にした後に機能を動作させるには、次のタスクを実行します。
    
    1. [Azure Information Protection ラベル](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)を機密ラベルに移行し、Microsoft 365 コンプライアンスセンター (または同等のラベル付き管理センター) から[公開](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)していることを確認してください。
    
    2. ファイルをダウンロードしてから、それらを SharePoint にアップロードします。

- 暗号化を適用したラベルが[暗号化に対し](encryption-sensitivity-labels.md#configure-encryption-settings)て次のいずれかの構成を持っている場合、SharePoint は暗号化ファイルを処理できません。
    - ユーザーがラベルと Word、PowerPoint、Excel のチェックボックスを**適用するときにアクセス許可を割り当てること**ができるようにし **、[アクセス許可を指定するようユーザーに要求する]** を選択します。 この設定は、"ユーザー定義の権限" と呼ばれることがあります。
    - **コンテンツへのユーザーアクセスの有効期限**が、 **Never**以外の値に設定されています。
    - **二重キー暗号化**が選択されています。
    
    これらの暗号化構成のいずれかを使用したラベルの場合、web 上の Office のユーザーにはラベルが表示されません。 また、これらの暗号化設定を既に持っているラベル付きドキュメントでは、新しい機能を使用できません。 たとえば、これらのドキュメントは、更新された場合でも、検索結果では返されません。

- ユーザーに編集権限を付与する暗号化されたドキュメントの場合、Office アプリの web 版ではコピーをブロックすることはできません。

- Azure Information Protection ドキュメント追跡サイトはサポートされていません。

- Office デスクトップアプリとモバイルアプリは、暗号化によってラベルが付けられたファイルの共同編集をサポートしていません。 これらのアプリは、ラベル付きで暗号化されたファイルを排他編集モードで引き続き開きます。

- ユーザーの同期クライアントにダウンロードしたファイルに既に適用されている発行済みのラベルの設定が管理者によって変更された場合、ユーザーが OneDrive Sync フォルダーのファイルに加えた変更を保存できないことがあります。 このシナリオは、暗号化のラベルが付けられたファイルに適用されます。また、暗号化を適用したラベルに暗号化が適用されなかったラベルからラベルが変更された場合にも適用されます。 [白い十字アイコンのエラー](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示された赤い円が表示され、新しい変更内容を別のコピーとして保存するように求められます。 代わりに、ファイルを閉じて開き直すことができます。また、web 上の Office を使用することもできます。

- ラベル付きのドキュメントが SharePoint にアップロードされ、そのラベルがサービスプリンシパル名のアカウントを使用して暗号化されている場合、そのドキュメントを web 上の Office で開くことはできません。 シナリオの例としては、Microsoft Cloud App Security と、電子メールで Teams に送信されるファイルがあります。

- ユーザーは、web 用の Office を使用する代わりに、オフラインまたはスリープモードに移行した後に、Word、Excel、または PowerPoint 用のデスクトップおよびモバイルアプリを使用して、保存の問題を発生させることができます。 これらのユーザーは、Office アプリセッションを再開して変更を保存しようとすると、元のファイルを保存するのではなく、コピーを保存するためのオプションを含むアップロードエラーメッセージが表示されます。 

- 次の方法で暗号化されたドキュメントは、web 上の Office で開くことができません。
    - オンプレミスキー ("自分のキーを保持する" または HYOK) を使用する暗号化
    - [二重キー暗号化](double-key-encryption.md)を使用して適用された暗号化 
    - ラベルとは独立して適用された暗号化。たとえば、Rights Management protection テンプレートを直接適用します。

- SharePoint でドキュメントに適用されているラベルを削除する場合、該当するラベルポリシーからラベルを削除するのではなく、ダウンロードしたドキュメントがラベル付けまたは暗号化されないようにします。 比較すると、ラベル付きドキュメントが SharePoint の外部に保存されている場合、ラベルが削除されてもドキュメントは暗号化されたままになります。 テストフェーズではラベルを削除することもできますが、運用環境でラベルを削除するのは非常にまれです。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint および OneDrive の機密ラベルを有効にする方法 (オプトイン)

新しい機能は、Microsoft 365 コンプライアンスセンターまたは PowerShell を使用して有効にすることができます。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>コンプライアンスセンターを使用して機密ラベルのサポートを有効にする

このオプションは、SharePoint と OneDrive の機密ラベルを有効にする最も簡単な方法です。

組織のグローバル管理者には、秘密度ラベルのすべての側面を作成および管理するための完全な権限があります。 グローバル管理者としてサインインしていない場合は、「[機密ラベルの作成と管理に必要なアクセス許可](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)」を参照してください。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)にサインインし、[**ソリューション**  >  **情報保護**] に移動します。
    
    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。 

2. Office online ファイルのコンテンツを処理する機能を有効にするメッセージが表示された場合は、[**今すぐ有効**にする] を選択します。
    
    ![[今すぐ開始] ボタンをオンにして、Office Online の機密ラベルを有効にする](../media/sensitivity-labels-turn-on-banner.png)
    
    コマンドはすぐに実行され、ページが次に更新されるときに、メッセージまたはボタンが表示されなくなります。 

> [!NOTE]
> Microsoft 365 複数地域を使用している場合は、PowerShell を使用して、すべての地域の場所に対してこれらの機能を有効にする必要があります。 詳細については、次のセクションを参照してください。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell を使用して機密ラベルのサポートを有効にする

コンプライアンスセンターを使用する代わりに、SharePoint Online PowerShell から[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを使用して、機密ラベルのサポートを有効にすることができます。 

Microsoft 365 複数地域を使用している場合は、すべての地域の場所でこのサポートを有効にするために PowerShell を使用する必要があります。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 管理シェルの準備

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にするために PowerShell コマンドを実行する前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。 最新バージョンが既にインストールされている場合は、[次の手順](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)に進んで PowerShell コマンドを実行できます。

1. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。

3. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 言語を選択し、[**ダウンロード**] をクリックします。

5. x64 および x86 の .msi ファイルのいずれかを選択します。 64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。 不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。

6. ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell コマンドを実行して機密ラベルのサポートを有効にする

新機能を有効にするには、 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを*EnableAIPIntegration*パラメーターと共に使用します。

1. Microsoft 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。
    
    注: Microsoft 365 複数地域を使用している場合は、-Url パラメーターと[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)を使用して、地理的な場所の1つに対して SharePoint Online 管理センターサイトの Url を指定します。

2. 次のコマンドを実行し、 **Y**キーを押して確認します。

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. Microsoft 365 複数地域の場合: 残りの geo の場所ごとに手順1と2を繰り返します。

## <a name="publishing-and-changing-sensitivity-labels"></a>機密ラベルの発行と変更

SharePoint と OneDrive で機密ラベルを使用する場合は、新しい機密ラベルを発行するか、既存の機密ラベルを更新するときにレプリケーション時間を許可する必要があることに注意してください。 これは、暗号化を適用する新しいラベルにとって特に重要です。

例: 暗号化を適用する新しい機密ラベルを作成して発行すると、ユーザーのデスクトップアプリにすぐに表示されます。 ユーザーがこのラベルをドキュメントに適用し、それを SharePoint または OneDrive にアップロードします。 サービスのラベルのレプリケーションが完了していない場合、新しい機能はアップロード時にそのドキュメントに適用されません。 その結果、ドキュメントは検索では返されず、電子情報開示のために Office でドキュメントを開くことができません。

- 次の変更は、1時間以内にレプリケートされます。新規および削除された機密情報ラベル、およびポリシーに含まれるラベルを含む機密ラベルポリシー設定。

- 次の変更は24時間以内にレプリケートされます。既存のラベルの機密ラベルの設定を変更します。

新しい機密ラベルに対してレプリケーションの遅延が1時間になるため、この例のシナリオでは実行できない可能性が高くなります。 しかし、安全策として、新しいラベルを少数のテストユーザーのみに公開し、1時間待ってから、SharePoint と OneDrive でラベルの動作を確認することをお勧めします。 最後の手順として、既存のラベルポリシーにユーザーを追加するか、または標準ユーザーの既存のラベルポリシーにラベルを追加することによって、より多くのユーザーがラベルを使用できるようにします。 標準ユーザーがラベルを表示しているときに、SharePoint と OneDrive に既に同期されています。


## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) と機密ラベル

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md)は、ファイルをダウンロードするときに暗号化と制限を適用することによって、リストおよびライブラリレベルでファイルを保護する古いテクノロジです。 この古い保護テクノロジは、権限のないユーザーが SharePoint の外部でファイルを開くことを防止するように設計されています。

一方、機密ラベルは、暗号化に加えて、視覚的なマーキング (ヘッダー、フッター、ウォーターマーク) の保護設定を提供します。 暗号化設定では、ユーザーがコンテンツに対して実行できる操作を制限する[使用権限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights)の範囲全体がサポートされており、[多くのシナリオ](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)で同じ機密ラベルがサポートされています。 同じ保護方法をワークロードおよびアプリ間で一貫した設定で使用すると、一貫性のある保護戦略が得られます。

ただし、両方の保護ソリューションを一緒に使用することができ、その動作は次のようになります。 

- 暗号化を適用する機密ラベルを含むファイルをアップロードすると、SharePoint はこのファイルを処理できないため、このファイルに対して共同編集、電子情報開示、DLP、検索が機能しなくなります。

- Web 上の Office を使用してファイルにラベルを付けると、そのラベルの暗号化設定が適用されます。 これらのファイルでは、共同編集、電子情報開示、DLP、検索がサポートされています。

- Web 上の Office を使用してラベル付けされたファイルをダウンロードすると、ラベルは保持され、IRM 制限の設定ではなく、ラベルの暗号化設定が適用されます。

- 機密ラベルを使用して暗号化されていない Office ファイルまたは PDF ファイルをダウンロードすると、IRM 設定が適用されます。

- Irm をサポートしていないドキュメントをユーザーがアップロードできないようにする追加の IRM ライブラリ設定を有効にしている場合は、これらの設定が適用されます。

この動作を使用すると、すべての Office および PDF ファイルがダウンロードされた場合でも、ラベル付けされていない場合でも、そのアクセスが許可されないことが保証されます。 ただし、アップロードされたファイルには、新しい機能のメリットはありません。

## <a name="search-for-documents-by-sensitivity-label"></a>ドキュメントを機密ラベルで検索する

管理プロパティの情報保護**ラボ**を使用して、特定の機密ラベルが設定されている SharePoint または OneDrive 内のすべてのドキュメントを検索します。 次の構文を使用します。`InformationProtectionLabelId:<GUID>`

たとえば、"Confidential" というラベルが付けられていて、そのラベルの GUID が "8faca7b8-8d20-48a3-8ea2-0f96310a848e" のすべてのドキュメントを検索するには、検索ボックスに次のように入力します。

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

機密ラベルの Guid を取得するには、次[のコマンドレットを使用します](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps)。
    
1. まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
    
    たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. その後、次のコマンドを実行します。
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

管理プロパティの使用の詳細については、「 [SharePoint で検索スキーマを管理](https://docs.microsoft.com/sharepoint/manage-search-schema)する」を参照してください。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint と OneDrive の機密ラベルを無効にする方法 (オプトアウト)

これらの新機能を無効にした場合、SharePoint と OneDrive の機密ラベルを有効にした後にアップロードしたファイルは、ラベル設定が引き続き適用されるため、ラベルによって保護されます。 これらの新機能を無効にした後、機密ラベルを新しいファイルに適用すると、フルテキスト検索、電子情報開示、共同編集は機能しなくなります。

これらの新機能を無効にするには、PowerShell を使用する必要があります。 SharePoint Online 管理シェルと[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)コマンドレットを使用して、「PowerShell を使用して[機密ラベルのサポートを有効にする](#use-powershell-to-enable-support-for-sensitivity-labels)」の説明に従って、同じ*EnableAIPIntegration*パラメーターを指定します。 しかし、今回はパラメーター値を false に設定し、 **Y**キーを押して確認します。

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Microsoft 365 複数地域を使用している場合は、各地域の場所に対してこのコマンドを実行する必要があります。

## <a name="next-steps"></a>次の手順

SharePoint と OneDrive で Office ファイルの機密ラベルを有効にした後、自動ラベル付けポリシーを使用して、これらのファイルに自動的にラベル付けすることを検討してください。 詳細については、「[コンテンツに機密ラベルを自動的に適用する](apply-sensitivity-label-automatically.md)」を参照してください。