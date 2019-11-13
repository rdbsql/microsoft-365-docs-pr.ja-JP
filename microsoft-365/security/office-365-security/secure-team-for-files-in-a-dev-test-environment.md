---
title: 開発/テスト環境のファイルのために Teams の安全を強化する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: '概要: 開発/テスト環境のファイルのために、Microsoft Teams で機密チームと高機密チームを作成します。'
ms.openlocfilehash: f22b3b1fbe07af6866206034ad6c9a90ced8a268
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37929267"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a>開発/テスト環境のファイルのために Teams の安全を強化する

この記事では、「[Microsoft Teams のファイルを保護する](secure-files-in-teams.md)」ソリューションとして、機密チームや高機密チームが含まれる開発/テスト環境を作成するための詳しい手順を説明します。
  
![ファイルのための Microsoft Teams の機密チームと高機密チーム。](../media/sensitive-highly-confidential-teams-dev-test.png)
  
こうしたチームを運用環境に展開する前に、この開発/テスト環境を使用して、特定のニーズに合わせて設定を検証し、微調整します。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小要件で機密チームと高機密チームを簡易な方法でテストする場合は、「[軽量な基本構成](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)」の手順に従ってください。

シミュレーションのエンタープライズで機密チームと高機密チームをテストするには、「[パスワード ハッシュの同期](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)」の手順に従ってください。

>[!Note]
>機密チームと高機密チームのテストには、シミュレーションのエンタープライズ テスト環境は必要ありません。シミュレーションのエンタープライズ テスト環境には、インターネットに接続されたシミュレーションのイントラネット、Active Directory Domain Services (AD DS) フォレスト用のディレクトリ同期が含まれています。 この指示は、一般的な組織と類似した環境で機密チームと高機密チームをテストしてお試しいただけるようオプションとしてここで提供しています。
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>フェーズ 2: Azure Active Directory (AD) グループとユーザーを作成して構成する

このフェーズでは、架空の組織用の Azure AD のグループとユーザーを作成して構成します。
  
最初に、Azure portal で一般的な組織のグループを 2 つ作成します。
  
1. ブラウザーで新しいタブを開き、Azure portal ([https://portal.azure.com](https://portal.azure.com)) に移動します。 必要に応じて、Microsoft 365 E5 の試用版または有料サブスクリプション用の全体管理者アカウントの資格情報でサインインします。
    
2. Azure Portal で **[Azure Active Directory] > [グループ]** の順にクリックします。
    
3. **[グループ] - [すべてのグループ]** ブレードで、**[+ 新しいグループ]** をクリックします。
    
4. **[グループ]** ブレードでの手順:
    
  - **[グループの種類]** で **[セキュリティ]** を選択します。
    
  - **[名前]** に「**C スイート**」と入力します。
    
  - **[メンバーシップの種類]** で **[割り当て済み]** を選択します。
      
5. **[作成]** をクリックして、 **[グループ]** ブレードを閉じます。
    
6.  「**Marketing staff (マーケティング スタッフ)**」という名前の新しい次のグループに対して、ステップ 3 から 5 を繰り返します。
    
次に、グループのメンバーが、Office 365 と EMS のサブスクリプションのライセンスを自動的に割り当てられるように、自動ライセンスを構成します。
  
1. Azure Portal で **[Azure Active Directory] > [ライセンス] > [すべての製品]** の順にクリックします。
    
2. 一覧で、「**Microsoft 365 Enterprise E5**」を選択し、**[割り当て]** をクリックします。
    
3. **[ライセンスの割り当て]** ブレードで、 **[ユーザーとグループ]** をクリックします。
    
4. グループの一覧で、以下を選択します。
    
  - C-Suite (C スイート)
    
  - Marketing staff (マーケティング スタッフ)
    
5. **[選択]** をクリックし、 **[割り当て]** をクリックします。
    
6. ブラウザーの [Azure Portal] タブを閉じます。
    
次に、[Graph 用 Azure Active Directory PowerShell モジュールに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)します。
  
組織名、場所、および共通のパスワードを入力し、PowerShell コマンド プロンプトまたは Integrated Script Environment (ISE) からこれらのコマンドを実行し、ユーザー アカウントを作成し、それぞれのグループに追加します。
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> ここで共通のパスワードを使用することで、自動化と、開発/テスト環境の構成を容易にします。 運用環境のサブスクリプションは避けるように強くお勧めします。 
  
次の手順を使用して、グループ ベースのライセンスが正しく機能していることを確認します。
  
1. ブラウザーの **[Microsoft Office Home]** タブで、 **[管理者]** タイルをクリックします。
    
2. ブラウザーの新しい **[Microsoft 365 管理センター]** タブで、**[ユーザー]** をクリックします。
    
3. ユーザーの一覧で、**[CEO]** をクリックします。
    
4. **CEO** ユーザー アカウントのプロパティが一覧表示されているウィンドウで、**Microsoft 365 Enterprise E5** のライセンスが割り当てられている (**製品ライセンス**内) ことを確認します。
    
## <a name="phase-3-create-office-365-retention-labels"></a>フェーズ 3: Office 365 保持ラベルを作成する

このフェーズでは、基となる SharePoint サイトのドキュメント フォルダーに対してさまざまなセキュリティ レベルの保持ラベルを作成します。

1. 全体管理者アカウントで、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com)にサインインします。
    
2. ブラウザーの **[ホーム - Microsoft 365 コンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。
    
3. **[保持ラベル] > [ラベルの作成]** をクリックします。
    
4. **[ラベルに名前をつける]** ウィンドウで、**[ラベルに名前をつける]** のところに「**機密**」と入力してから、**[次へ]** をクリックします。

5. **[ファイル計画記述子]** ウィンドウで **[次へ]** をクリックします。
    
6. **[ラベルの設定]** ウィンドウで、必要に応じて **[保持]** を **[オン]** にして **[次へ]** をクリックします。
    
7. **[設定の確認]** ウィンドウで、**[ラベルを作成する]** をクリックします。
    
8. ステップ 3 から 7 を繰り返して、「**高機密**」という名前の追加の保持ラベルを作成します。
    
9. **[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。
    
10. **[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。
    
11. **[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。
    
12. [ **完了**] をクリックします。
    
13. **[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。
    
14. **[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。
    
15. **[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。
    
16. **[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。
    
## <a name="phase-4-create-your-teams"></a>フェーズ 4: チームを作成する

このフェーズでは、サンプル組織の機密チームと高機密チームを作成し、構成します。

### <a name="sensitive-team-for-marketing-campaigns"></a>マーケティング キャンペーン向けの機密チーム

進行中のマーケティング キャンペーンで共同作業を行えるように、マーケティング グループのメンバーを対象とした機密レベルのチームを作成するには、次のようにします。

1. 「**マーケティング キャンペーン**」という名前の[プライベート チームを新規作成](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)します。
2. 「**マーケティング キャンペーン**」チームを開きます。
3.  チームのツール バーで、**[ファイル]** をクリックします。
4.  省略記号をクリックし、**[SharePoint で開く]** をクリックします。
5.  基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。
6.  **[サイトの権限]** ウィンドウで、**[共有の設定]** の **[共有設定を変更します]** をクリックします。
7.  **[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。

次に、基となるマーケティング キャンペーン SharePoint サイトのドキュメント フォルダーを [機密] ラベル用に構成します。

1.  ブラウザーの **[マーケティング キャンペーン - ホーム]** タブで、**[ドキュメント]** をクリックします。
2.  設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。
3.  **[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。
4.  **[設定 - ラベルの適用]** で **[機密]** をクリックし、 **[保存]** をクリックします。 

次に、機密ラベルのある、基となる SharePoint サイト上のドキュメントを共有しようとしているユーザーに通知を行うデータ損失防止 (DLP) ポリシーを構成します。このサイトには、組織外部のマーケティング キャンペーン サイトが含まれます。

1. 全体管理者アカウントで、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。
    
2. ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。
    
3. **[ホーム] > [データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。
    
4. **[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、 **[カスタム]** をクリックしてから、 **[次へ]** をクリックします。
    
5. **[ポリシーに名前をつける]** ウィンドウで、**[名前]** に「**機密ラベル SharePoint サイト**」と入力してから、**[次へ]** をクリックします。
    
6. **[場所の選択]** ウィンドウで、 **[自分で特定の場所を選択する]** をクリックしてから、 **[次へ]** をクリックします。
    
7. 場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。
    
8. **[保護するコンテンツの種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。
    
9. **[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。
    
10. **[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。
    
11. **[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。
    
12. **保護するコンテンツの種類をカスタマイズする** ウィンドウで、**[次へ]** をクリックします。

13. **機密性の高い情報が検出された場合に実行する操作** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。
    
14. **ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。
    
15. 次の内容をテキスト ボックスに入力するか、貼り付けます。
    
  - 組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。
    
16. **[OK]** をクリックします。
    
17. **[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。
    
18. **[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。
    
19. **[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。

「マーケティング キャンペーン」チームの最終的な構成をここに示します。

![「マーケティング キャンペーン」チームの構成。](../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a>会社戦略チーム サイト

会社戦略に基づいて共同作業を行うために、上級リーダーシップ チームのメンバーを対象にした高機密チームを作成するには、次のようにします。

1. 「**会社戦略**」という名前の[プライベート チームを新規作成](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)します。
2. 「**会社戦略**」チームを開きます。
3.  チームのツール バーで、**[ファイル]** をクリックします。
4.  省略記号をクリックし、**[SharePoint で開く]** をクリックします。
5.  基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。
6.  [**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。
7.  [**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。
8.  [**アクセス要求の許可**] をオフにし、[**保存**] をクリックします。

次に、基となる会社戦略 SharePoint サイトのドキュメント フォルダーを [高機密] ラベル用に構成します。

1.  ブラウザーの **[会社戦略 - ホーム]** タブで、**[ドキュメント]** をクリックします。
2.  設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。
3.  **[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。
4.  **[設定 - ラベルの適用]** で **[高機密]** をクリックし、 **[保存]** をクリックします。 

次に、高機密ラベルのある、基となる SharePoint サイト上のドキュメントをユーザーが共有するのをブロックする DLP ポリシーを構成します。このサイトには、組織外部の会社戦略サイトが含まれます。
  
1. 全体管理者で、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。
    
2. ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。
    
3. **[ホーム] > [データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。
    
4. **[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、 **[カスタム]** をクリックしてから、 **[次へ]** をクリックします。
    
5. **[ポリシーに名前をつける]** ウィンドウで、**[名前]** に「**高機密ラベル SharePoint サイト**」と入力してから、**[次へ]** をクリックします。
    
6. **[場所の選択]** ウィンドウで、 **[自分で特定の場所を選択する]** をクリックしてから、 **[次へ]** をクリックします。
    
7. 場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。
    
8. **[保護するコンテンツの種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。
    
9. **[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。
    
10. **[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[高機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。
    
11. **[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。
    
12. **保護するコンテンツの種類をカスタマイズする** ウィンドウで、**[次へ]** をクリックします。

13. **機密性の高い情報が検出された場合に実行する操作** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。
    
14. **ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。
    
15. 次の内容をテキスト ボックスに入力するか、貼り付けます。
    
  - 組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。
    
16. **[OK]** をクリックします。
    
17. **[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。

18. **[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。
    
19. **[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。

[こちらの手順](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)を使用して、秘密度ラベルを次の設定で構成します。

- ラベルの名前は「会社戦略」です
- 暗号化が有効になっています
- 会社戦略グループには、共同編集のアクセス許可があります

作成したら、新しいラベルを発行します。 会社戦略グループのメンバーとしてサインインすると、Word、Excel、PowerPoint のホーム ツール バーの [秘密度] オプションに新しいラベルが表示されています。 ラベルをファイルに割り当てるには、[秘密度] オプションから会社戦略ラベルを選択します。

会社戦略チームの最終的な構成をここに示します。

![会社戦略チームの構成。](../media/highlyconfidential-team-config-dev-test.png) 

基となる会社戦略 SharePoint サイトの [ドキュメント] セクションにあるファイルには、高機密保持ラベルが割り当てられ、構成されている DLP ポリシーが適用されます。 ファイルには、会社戦略の秘密度ラベルを割り当てることもできます。    
  
## <a name="next-step"></a>次の手順

本番展開の準備が整ったら、「[Microsoft Teams のファイルを保護する](secure-files-in-teams.md)」を参照して、詳細情報と、展開を順を追って説明した記事へのリンクをご確認ください。
  
## <a name="see-also"></a>関連項目

[クラウド導入およびハイブリッド ソリューション](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)