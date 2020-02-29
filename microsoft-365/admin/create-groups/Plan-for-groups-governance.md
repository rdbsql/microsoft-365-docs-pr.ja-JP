---
title: Office 365 グループのガバナンスを計画する
ms.reviewer: johasand
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Office 365 グループのガバナンスを計画する方法について説明します。
ms.openlocfilehash: 33c6562e85e98570e9f04e7b7ccb6d0fa882669d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241451"
---
# <a name="plan-for-governance-in-office-365-groups"></a>Office 365 グループでのガバナンスを計画する

Office 365 グループには、組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールのセットが用意されています。この記事では、IT プロフェッショナルが、ガバナンスに関する組織の要件と、その要件を組織のプロファイルに基づいて満たす方法を判断する際に適切な質問をするためのガイドを示します。

## <a name="why-office-365-groups"></a>Office 365 グループを使用する理由
![画像の説明](../media/01.png)

現在の組織では、さまざまなツールセットが使用されています。開発者のチームはチーム チャットを使い、幹部はメールを送り、組織全体がエンタープライズ ソーシャルでつながっています。グループごとに独自の機能的ニーズとワークスタイルがあるため、複数の共同作業ツールが使用されています。 メールだけを使う人もいれば、チャットだけを使う人もいます。 

ユーザーは、IT が提供するツールがニーズに合わないと思った場合、自分のシナリオに対応するお気に入りのコンシューマー アプリをダウンロードすることになるでしょう。 このプロセスにより、ユーザーはすぐに使い始めることができますが、複数のログイン、共有の困難さ、コンテンツの閲覧場所の不足など、組織全体でユーザー エクスペリエンスが低下します。 この概念は「シャドウ IT」と呼ばれ、組織に重大なリスクをもたらします。 これにより、ユーザー アクセスを均一に管理し、セキュリティとサービス コンプライアンスのニーズを保証できる機能が減ります。

Office 365 のグループは、共同作業に必要な多くのツールを単一のステップで提供することにより、ユーザーを支援し、シャドウ IT のリスクを軽減します。 Office 365 のグループを使用すると、共同作業するチームメイトを選定し、それらのメンバーが共有するリソースでの共同作業を簡単にセットアップすることができます。 リソースに手動で権限を割り当てることは、過去のことです。グループにメンバーを追加すると、グループが提供するすべてのアセットに必要な権限が自動的に付与されるためです。

## <a name="technical-architecture"></a>テクニカル アーキテクチャ

Office 365 グループがサポートする主なコミュニケーションの方式は 3 つあります。グループは次のエクスペリエンスの範囲内で作成可能であり、Office 365 スイート全体で使用できます。
- [Outlook](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): グループの受信トレイと予定表が共有される電子メールを通じた共同作業
- [Microsoft Teams](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): 特定のサブグループごとに編成された、さまざまなトピックについての非公式でリアルタイムの会話ができる、永続的なチャットベースのワークスペース
- [Yammer](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): 共同作業のためのエンタープライズ ソーシャル エクスペリエンス

> [!NOTE]
> その他のチームワーク アプリケーション (SharePoint、Planner、Stream など) で新しいグループを作成すると、Microsoft Teams に接続する能力を備えた Outlook コミュニケーション方式のグループが作成されます。

グループが作成された場所に応じて、次のような特定のリソースが自動的にプロビジョニングされます。
- [受信トレイ](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22): メンバー間の電子メールによる会話用。この受信トレイには、メール アドレスがあり、従来の配布リストと同じようにグループの部外者 (さらには組織の部外者) からのメッセージも受け入れるように設定できます。
 - [予定表](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a): グループに関連したスケジュール済みイベント用
- [SharePoint チーム サイト](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e): グループに関連する情報、リンクおよびコンテンツの中央リポジトリ
- [SharePoint ドキュメント ライブラリ](https://support.office.com/article/share-group-files-749bc73b-90c9-4760-9b6f-9aa1cf01b403): グループがファイルを保存および共有するための中心的な場所
- [OneNote ノートブック](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97): アイデア、調査結果、および情報の収集用
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc): グループのメンバーへのプロジェクト タスクの割り当ておよび管理用
- [Yammer グループ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): 会話と情報共有のための共通の場所
- Microsoft Teams: Office 365 のチャット ベースのワークスペース

それぞれのグループに対して作成されるリソースの詳細については、「[Office 365 グループの概要](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)」を参照してください。

> [!NOTE]
> Yammer または Teams によって作成された新しい Office 365 グループは、そのグループのユーザー間の主なコミュニケーションが各自の個別のクライアントで行われるため、Outlook やアドレス帳には表示されません。

> [!IMPORTANT]
> 新しい Yammer グループの作成時に、Office 365 グループはグループ メールボックスや予定表リソースを作成しません。そのため、Yammer グループは Microsoft Teams に接続することができません。「[Yammer とグループ](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups)」を参照してください。

## <a name="where-to-start-a-conversation"></a>会話を開始する場所
Office 365 には、会話する場所が複数あります。会話を開始する場所について理解することは、組織がコミュニケーションの戦略を定義する際に役立ちます。

![画像の説明](../media/02.png)

- Teams: チャット ベースのワークスペース (高速なコミュケーション) – 内部ループ
   - 日常的に作業するメンバーとの共同作業のために作成されています
  - 単一のエクスペリエンスでユーザーが簡単に情報を得られるようにします
  - タブ、コネクタおよびボットを追加します
  - ライブ チャット、音声会議/ビデオ会議、記録された会議。

- Yammer: 組織全体をつなぐ (エンタープライズ ソーシャル) – 外部ループ
  - 実践コミュニティ: 共通の関心事項や専門知識を共有しているが、日常的に共同作業するとは限らないメンバーによる部門間交流グループ
  - リーダーのつながり、学習コミュニティ、役割ベースのコミュニティ

- Outlook Groups: 最新の DL (メール ベースの共同作業)
  - 対象とするコミュニケーションにとってユビキタス
  - Office 365 グループに DL をアップグレードする: [アップグレードが必要な理由](https://support.office.com/article/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint: すべての Office 365 グループに対応する中心的なコンテンツ共同作業のエクスペリエンス
  - すべてのグループは、SharePoint チーム サイトに接続されます
  - コンテンツの共有、カスタマイズしたページの作成およびニュースの執筆
  - 既存の SharePoint チーム サイトから新しい Office 365 グループへの[接続](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)

![画像の説明](../media/03.png)

##  <a name="managing-and-governing-office-365-at-scale"></a>大規模な Office 365 の管理とガバナンス

Office 365 グループには、組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールのセットが用意されています。次の各セクションでは、その機能とお勧めのベスト プラクティスについて説明し、ガバナンスに関する組織の要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイドを示します。

**このセクションの内容**:
- [Office 365 グループを作成できるユーザーを制御する](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [グループの論理的な削除と復元](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [グループの名前付けポリシー](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [グループの有効期限ポリシー](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [グループのゲスト アクセス](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [グループのポリシーと情報保護](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [従来の共同作業ツールをアップグレードする](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [グループのレポート](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-office-365-groups"></a>Office 365 グループを作成できるユーザーを制御する
グループは、エンド ユーザーが複数のエンド ポイント (Outlook、SharePoint、Microsoft Teams などの環境) から作成できます。

![画像の説明](../media/04.png)
> [!Tip]
>- グループの所有者に裁量を委ねるセルフサービスについて特に考慮に入れます。
>- グループの要求方法を文書化して伝えます。
>- クラウドへの移行過程でグループを作成できるユーザーについて再考します。
>- グループの作成を制御するセキュリティ グループを構成するために、動的メンバーシップを使用することを検討します。
>- 動的メンバーシップによって管理できるグループ シナリオを評価して、その他のグループにはセルフサービスを許可します。

グループのプロビジョニングには 3 つの主要なモデル (オープン、IT 主導、制御) があります。次の表では、それぞれのモデルの長所について説明します。

| モデル          | 長所                                                   |
| -------------- | ------------------------------------------------------------ |
| オープン (既定) | ユーザーは必要に応じて独自のグループを作成できます。IT 部門の対応を待機したり依頼する必要はありません。 |
| IT 主導         | ユーザーは IT 部門にグループを要求します。IT 部門は、ユーザーのニーズに応じた最適な共同作業ツールを選択するように指導できます。 |
| 制御     | グループの作成は、特定のユーザー、チームまたはサービスに制限されます。詳細については、「[Office 365 グループを作成できるユーザーを管理する](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)」を参照してください。 |

組織には、グループを作成できるユーザーの厳格な管理を実施するための固有の要件がある場合があります。次の表を利用して、それぞれの組織に適したプロビジョニング モデルについて判断してください。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>組織の要件に適したプロビジョニング モデルは何か?</li><li>組織はグループの作成を管理者に限定する必要があるか?</li><li>組織はグループの作成をセキュリティ グループのメンバーに限定する必要があるか?</li><li>組織はユーザーの属性 (所属部署など) に基づいて一部のグループを動的に作成する必要があるか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>グループおよびチームの作成に関する組織の要件を文書化します。</li><li>該当する要件をグループのロールアウトの一部として実装する計画を立てます。</li><li>ユーザーにポリシーについて通達および公開して、ユーザーが要求できる行動を知らせます</li><li>該当する場合は動的メンバーシップを実装する計画を立てます。</li></ul>|

> [!Important]
> グループおよびチームの作成を制限すると、多くの Office 365 サービスは、そのサービスが機能するためのグループの作成が必要になり、ユーザーの生産性が低下することがあります。詳細については、「[Office 365 グループの作成ユーザーを制御する理由](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)」を参照してください。

#### <a name="resources"></a>*資料*
- [Office 365 グループを作成できるユーザーを管理する](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [オブジェクトの属性に基づいて動的にグループを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Outlook 用の Office 365 グループの既定の設定をパブリックまたはプライベートに変更する方法](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [セキュリティ グループとチーム メンバーシップを同期する](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a>グループの論理的な削除と復元
Office 365 グループを削除した場合、既定では、その後 30 日間は保持されます。グループを引き続き復元できるため、この 30 日の期間は "論理的な削除" と呼ばれます。30 日後、グループおよび関連付けられているコンテンツは完全に削除され、復元することはできません。

> [!Tip]
>- ユーザーに復元処理について通達します。
>- ヘルプデスク チームをトレーニングします。
>- PowerShell スクリプトを使用して削除予定のグループの追跡を実行します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>特定の資産を長期保存のためにアーカイブする必要がありますか?</li><li>組織には保持に関する特定の要件がありますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>ユーザーに削除および復元のポリシーについて通達および公開して、ユーザーが要求できる行動を知らせます </li><li> 削除したグループの監視に関する組織の要件を文書化します。</li><li>該当する要件をグループのロールアウトの一部に実装する計画を立てます。</li></ul>|

> [!Important]
>"論理的な削除" 期間中にユーザーがサイトにアクセスしようとすると、403 アクセス不可メッセージが表示されます。 この期間が経過した後、ユーザーがサイトにアクセスしようとすると、404 見つかりませんのメッセージが表示されます。

#### <a name="resources"></a>*資料*
- [削除された Office 365 グループを復元する](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54?ui=en-US&rs=en-001&ad=US)
- [Azure Active Directory で削除された Office 365 グループを復元する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Remove-UnifiedGroup コマンドレットを使用してグループを削除する](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a>グループの名前付けポリシー
名前付けポリシーにより、管理者やユーザーはグループの機能、メンバーシップ、地域、グループの作成者を特定しやすくなります。名前付けポリシーは、アドレス帳のグループの分類にも役立ちます。ポリシーを使用すると、グループの名前やエイリアスに特定の単語が使用されないようにブロックできます。

> [!Tip]
> - 短い文字列をサフィックスとして使用します。
> - 値が指定された属性を使用します。
> - 過度な表現は必要ありません。名前の合計長は最大 264 文字にします。
> - 使用制限する組織固有の禁止単語をアップロードします。


|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>組織はグループに対する特定の命名規則を必要としていますか?</li><li>組織はすべてのワークロードに通用する命名規則を必要としていますか?</li><li>組織にはユーザーが使用できないようにする特定の単語がありますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次の手順|<ul><li>グループの名前付けに関する組織の要件を文書化します。 </li><li> 該当する要件をグループのロールアウトの一部に実装する計画を立てます。</li><li> 名前付けのポリシーと標準を通達および公開して、ユーザーに知らせます。</li></ul>|

> [!Important]
>名前付けポリシーは、すべてのグループのワークロード (Outlook、Microsoft Teams、SharePoint、Planner、Yammer など) で作成されたグループに適用されます。グループ名とグループのエイリアスのどちらにも適用されます。名前付けポリシーは、ユーザーによるグループの作成時、または既存のグループのグループ名やエイリアスの編集時に適用されます。

#### <a name="resources"></a>*資料*
- [Office 365 グループの名前付けポリシー](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Azure Active Directory での Office 365 グループの名前付けポリシーの強制](https://go.microsoft.com/fwlink/?linkid=868340)
- [グループ設定を構成するための Azure Active Directory コマンドレット](https://go.microsoft.com/fwlink/?linkid=868341)
- [グループの名前付けのプレビュー機能](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a>グループの有効期限ポリシー
管理者はグループの有効期間を指定できます。有効期間の終了日に達していて更新されなかったグループは削除されます。有効期間はグループの作成時、または最終更新日から始まります。グループの所有者には、有効期限が切れる前に自動的に電子メールが送信され、グループの有効期間を別の期間に更新できます。

グループを有効期限切れに設定した場合:
- 有効期限が近づくと、グループの所有者にグループを更新するための通知が送られます
- 更新されないグループは削除されます
- 削除されたグループは、30 日以内であれば、グループ所有者または管理者によって復元することできます

> [!Tip]
> - 最初に特定のグループでパイロット運用します。
> - Microsoft 365 管理センターのアクティビティ レポートに基づいてアクティブでないグループを選択します。
> - グループの所有者に更新処理について伝えます。
> - ヘルプ デスクチームを参加させます。
> - グループには複数の所有者がいるようにして、孤立したグループに関する電子メールを構成します。


|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>組織はチームに有効期限日を指定することを必要としていますか?</li><li>孤立したグループの処理に関する戦略を決めますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>グループの有効期限、データ保持、およびアーカイブに関する組織の要件を文書化します。</li><li>該当する要件をグループのロールアウトの一部に実装する計画を立てます。</li><li>所有者が単独または所有者が存在しないグループについてレポートするカスタム ジョブを実装する計画を立てます。 </li></ul>|

> [!Important]
>有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。

#### <a name="resources"></a>*資料*
- [Office 365 グループの有効期限ポリシー](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Office 365 グループの有効期限ポリシーの構成](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a>グループのゲスト アクセス
管理者は、Office 365 グループへのゲスト アクセスを組織全体に対して許可するか、個々の Office 365 グループに対して許可するかを制御できます。また、グループにゲストを追加できるユーザーを制御することもできます。
>[!Tip]
>- ゲスト アクセスはテナント レベルで有効化します。必要に応じて、特定のグループへのゲスト アクセスをブロックします。
>- ゲストの許可/禁止ドメイン、ゲスト招待元ロール、アクセス レビュー、利用規約の使用を管理します。
>- 監査ログでゲスト ユーザーのアクティビティを追跡します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>チームにゲストを追加する機能をグループごとに制限する必要がありますか?</li><li> 組織は法的要件やコンプライアンス要件に関連する免責事項を提示する必要がありますか?</li><li>組織はユーザーの追加と削除にかかわる管理の負担を減らす必要がありますか?</li><li>組織はゲスト アクセス/外部アクセスに関する監査制御を期待していますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>特定の分類されたグループに対するゲスト/外部アクセスの要件 (保持期間や発生回数などを含む) を文書化します。</li><li>利用規約とアクセス レビューが必要になるグループについての組織の要件を文書化します。 </li><li>レビューを実行して、内部ユーザーとゲスト ユーザーの両方のグループ メンバーシップを効率的に管理します。</li></ul>|


#### <a name="resources"></a>*資料*
- [Office 365 グループでゲスト アクセスを管理する](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Office 365 グループのゲスト アクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Office 365 グループのゲスト アクセス: 管理者ヘルプ](https://support.office.com/article/Guest-access-to-Office-365-groups-Admin-Help-7c713d74-a144-4eab-92e7-d50df526ff96)
- [Azure AD アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Azure Active Directory Terms of Use 機能](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google フェデレーション](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)
- [Microsoft Teams でゲスト アクセスを許可する](https://docs.microsoft.com/microsoftteams/teams-dependencies)

### <a name="group-policies--information-protection"></a>グループのポリシーと情報保護
Office 365 グループは、Office 365 の高度なセキュリティ機能とコンプライアンス機能に基づいて構築されていて、分類、監査とレポート作成、コンプライアンス コンテンツ検索、電子情報開示、訴訟ホールド、および保持ポリシーをサポートしています。
>[!Tip]
>- 組織のニーズに合わせて、分類、使用上のガイドライン、およびラベルを構成します。
>- 保持ポリシーは、ラベルとは別に定義できます。
>- 監査グループのアクティビティ: 作成や削除など。
>- 分類に基づいてグループのプライバシーとゲスト アクセスを管理します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>組織には、すべてのユーザーに通達する必要のある特定の使用に関する要件がありますか?</li><li>組織はすべてのコンテンツの分類を必要としていますか?</li><li>組織はコンテンツを一定期間保持することを必要としていますか?</li><li>組織はグループに適用する特定のデータ保持ポリシーを必要としていますか?</li><li>組織は、コンテンツを保持するためにアクティブでないグループをアーカイブする機能を必要としますか?</li><li>グループ作成者は、チームに組織固有の分類を割り当てる機能を必要としますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>グループの使用に関する組織のガイドラインを文書化します</li><li>分類に関する組織の要件を文書化します。</li><li>分類 (秘密度、保持、ゲスト アクセスなど) に基づいて強制適用するポリシーを決定します。</li><li>組織の秘密度のラベルと、それに割り当てる保護設定を定義します。</li><li>ユーザーとグループが確認できるラベルを制御するためのラベル ポリシーを定義します。</li><li>[グループの機密度ラベルのプレビュー](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を設定し、組織内のグループの分類を開始します。</li><li>該当する要件をグループのロールアウトの一部として実装する計画を立てます。</li></ul>|


#### <a name="resources"></a>*資料*
- [Office 365 グループの使用に関するガイドラインへのリンク](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [グループ設定を構成する](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [アイテム保持ポリシーの概要](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [機密ラベルの概要](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)
- [ラベルの概要](https://docs.microsoft.com/office365/securitycompliance/labels)
- [監査ログを検索する](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)
- [インプレース訴訟ホールドを作成または削除する](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [保持ポリシーを作成する](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Office 365 セキュリティ/コンプライアンス センターでコンテンツ検索を実行する](https://docs.microsoft.com/Office365/SecurityCompliance/content-search)
- [PowerShell を使用して保持ラベルを一括で作成および発行する](https://docs.microsoft.com/office365/securitycompliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a>従来の共同作業ツールをアップグレードする
長年にわたり、組織は社内と社外の両方の職員グループとのコミュニケーションおよび共同作業を配布グループに頼ってきました。現在では、Outlook の Office 365 グループによって、これまで以上に強力なコラボレーションのためのソリューションが提供されています。さらに、既存の SharePoint サイトをモダン化するために Office 365 グループをサイトに接続することもできます。

>[!Tip]
>- Exchange 管理センターを介すか、 PowerShell コマンドレットを使用して、すべての対象となる配布リストを数秒で簡単にアップグレードできます。
>- 既存の SharePoint チームサイトを新しい Office 365 グループに接続します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>組織にはアップグレードの[対象にならない](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade)配布リストがありますか?<li>配布リストの最適な移行先としてのグループの種類は判別できていますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>Office 365 グループへのアップグレードの候補になる配布リストを特定します。</li><li>既存の SharePoint チーム サイトを分析して、グループへの接続準備が整っているサイトを確かめます。</li><li>社内の別のチームに配布グループをアップグレードしたことと、そのアップグレードを成功に導いた手順について知らせます。</li></ul>|


#### <a name="resources"></a>*資料*
- [配布リスト (DL) を Outlook のグループにアップグレードする](https://aka.ms/whyupgradedls):
- [DL を Outlook のグループにアップグレードする理由](https://aka.ms/whyupgradedls)
- 1 回のクリックでアップグレードする方法 (Exchange 管理センターまたは [PowerShell スクリプト](https://support.office.com/article/Migrate-distribution-lists-to-Office-365-Groups-Admin-help-787d7a75-e201-46f3-a242-f698162ff09f?ui=en-US&rs=en-US&ad=US)を使用)
- [配布リストを Office 365 グループに移行する: 管理者ヘルプ](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [既存の SharePoint サイトを Office 365 グループに接続する:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [スキャナー データの分析と使用](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint Modernization Scanner](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (GitHub にあるツール)

### <a name="groups-reporting"></a>グループのレポート
Office 365 のレポート ダッシュボードには、組織内の Office 365 製品全体にわたるアクティビティの概要が示されます。これにより、個別の製品レベルのレポートに向けてドリル インして、各製品の範囲内でのアクティビティに関する詳細な所見が得られます。
> [!TIP]
>- グループ アクティビティ レポートを使用して、組織内の Office 365 グループのアクティビティに関する洞察を得て、作成され、使用されているグループの数を確認できます。
>[ Office 365 グループ ] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。
>- グループ メールボックスの会話のすべてにわたるアクティビティ、グループ サイト/ファイルのアクティビティ、グループ メンバーシップに関する詳細 (外部メンバーの数を含む) を監視します。
>- 定期的な監視によってアクティブなグループの所有者を支援し、ユース ケースを調べて、そのユース ケースを内部に広めます。
>- 追加の所見を得るために Power BI コンテンツ パックを活用します。


|         |         |         |
|---------|---------|---------|
|![画像の説明](../media/decision_point.png)|判断のポイント|<ul><li>組織は Office 365 グループの使用状況について把握するための定期レポートを必要としていますか?<li>組織は外部メンバーが参加しているすべてのグループに関するレポートの作成を必要としていますか?</li></ul>|
|![画像の説明](../media/next_steps.png)|次のステップ|<ul><li>グループ アクティビティ レポートの定期的なレビューに関する組織の要件を文書化します。</li></ul>|


#### <a name="resources"></a>*資料*
- [管理センターの Office 365 レポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40)
- [Office 365 の導入コンテンツ パック](https://support.office.com/article/Office-365-Adoption-Content-Pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)
- [Azure AD コンテンツ パック](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph グループ アクティビティ API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Office 365 グループ レポート (統合グループ)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Azure Active Directory ポータルの監査アクティビティ レポート](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph: デルタ クエリを使用して変更を追跡する](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>クラウド導入行程の開始

Office 365 グループは、組織が必要とする可能性のあるガバナンス機能の豊富セットを提供します。ベスト プラクティスを理解したり、ガバナンスの要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイダンスとして、次の組織プロファイルについて検討してください。

**次の組織プロファイルについて検討してください。**
- 小規模企業
- 中規模企業
- 規制下または企業

### <a name="small-business"></a>小規模企業
Exchange Online と SharePoint Online 以上のライセンス (Business Essentials と Business Premium のプラン、および Azure Active Director Premium のライセンスがない Enterprise E1、E3、および E5 のプランを含む) を使用して Office 365 を展開した組織を検討します。

| ステージ | 説明 |
| --------------- | ------------------------------------------------------------ |
| ガイダンス |<ul><li>セルフサービスのプロビジョニング モデルを検討します</li><li> Outlook および SharePoint サイトのグループは、[既定でプライベート](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395)になります。</li><li> グループは、既存の配布リスト (DL) を 1 つずつアップグレードするか、PowerShell を使用して一括でアップグレードすることで作成できます。「[配布リストを Office 365 グループにアップグレードする](https://support.office.com/article/Upgrade-distribution-lists-to-Office-365-Groups-in-Outlook-787D7A75-E201-46F3-A242-F698162FF09F)」を参照してください。</li><li> ゲスト アクセスは有効にしますが、ゲストの許可/禁止ドメインを使用して管理します。</li><li> グループのレポートを使用して、ユーザーによるグループの使用方法に関する所見を得ます。</li><li> 誰もが共同作業のための 1 つのチームの一員になれる手段として、組織全体のチームである Microsoft Teams を作成することを検討します。 </li></ul>|
| 次のステップ      |<ul><li>[JSON スキーマ リファレンス](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)で定義されているアクションを使用するコントロールに、既定のデザインを定義するために [サイト デザインとサイト スクリプト](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)の使用を検討します。</li><li>[グループのレポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40)をレビューします</li><li>すべてのグループおよび非アクティブ/アクティブ グループを追跡します</li><li>使用されている Exchange ストレージと SharePoint ストレージの両方を追跡します</li><li>グループ メールボックスの会話のすべてにわたるアクティビティ、グループのサイト/ファイルのアクティビティなどを表示します。</li></ul> |

### <a name="medium-sized-business"></a>中規模ビジネス
上記の推奨事項のほかに、Azure Active Directory Premium P1 以上のライセンスで Enterprise E3/E5 を使用して Office 365 を展開する中規模ビジネスでは、次の点を考慮します。

| ステージ | 説明 |
| --------------- | ------------------------------------------------------------ |
| ガイダンス |<ul><li>Open または IT 主導のプロビジョニング モデルを決定します。</li><li> 部署などの Azure AD 属性に基づいて、[動的メンバーシップの規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)に関連付けられた特定のグループを作成することを検討します</li><li> 高機密、社外秘 (既定)、一般など、組織内の分類を定義します。</li><li>  保持や機密性などの分類に基づいてポリシーを定義します。</li><li> SharePoint は、すべての Office 365 グループのコンテンツ サービスです。[3 層の保護 (ベースライン、機密、高機密) を目的とした SharePoint Online サイトの設計と展開](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection)を検討します。これら 3 層の保護の詳細については、「[SharePoint Online サイトとファイルをセキュリティで保護する](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)」を参照してください。</li><li> 既定では、パブリック グループとプライベート グループの両方が GAL にリストされます。 GAL に表示するグループ、特に Microsoft Teams の外部で作成されたグループを決定します。  [Set-UnifiedGroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) コマンドレットの「HiddenFromAddressListsEnabled」または「HidefromExchangeClients」を使用して、特定のグループを非表示にする </li></ul> |
| 次のステップ      |<ul><li>[使用方法のガイドライン](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) を定義して、グループを効果的に維持するために役立つベスト プラクティスや、内部コンテンツのポリシーについてユーザーを教育します。たとえば、分類、ポリシー、手順を理解させることなどです。</li><li>グループのライフサイクル期間 (有効期限ポリシー) を定義します。この期間でグループは更新される必要があり、そうでない場合は削除されます。</li><li>分類に基づいてポリシーを実装するために、次に示すカスタム ジョブの作成を検討します。</li><li>プライバシーをプライベートに設定します。</li><li>外部のメンバーシップ/共有を無効にします。 </li><li>電子メールを送信して、[所有者のいない](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)グループのグループ メンバーに通知します。</li><li>所有権ポリシーを強制します (最低 2 人の所有者)。</li><li> 分類に基づいて、グループのアイテム保持ポリシーを定義します。 </li><li>アイテム保持ポリシーの概要。</li><li>PowerShell を使用して、分類と [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps) でグループを識別します。</li><li>[JSON スキーマ リファレンス](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)で定義されているアクションを使ったコントロールを定義するために、サイト デザインとサイト スクリプトの使用を検討します。</li><li>[サイト デザインと Microsoft Flow を使用して簡単なサイト ディレクトリを作成する](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial)ことを検討してください。 このサイト デザインを使用してサイトが作成されると、サイトの詳細情報が取り込まれ、リストに書き込まれます。 </li></ul>|

### <a name="regulated-or-enterprise"></a>規制下または企業
上記の推奨事項のほかに、Azure Active Directory Premium P1/P2 以上のライセンスで Enterprise E3/E5 を使用して Office 365 を展開する、政府、金融サービス、医療など高度な規制下にある組織や大規模な企業では、次の点を考慮します。

| ステージ | 説明 |
| --------------- | ------------------------------------------------------------ |
| ガイダンス |<ul><li> 分類に基づいたグループに関連付けられている SharePoint サイトのデータ ガバナンスのポリシーを定義します。</li><li>[Office 365 ラベルと DLP を使用して SharePoint ファイルを保護します](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。</li><li>[Azure Information Protection を使用して SharePoint Online ファイルを保護します](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</li><li> 地域にプロビジョニングされたグループ サイトは、ユーザーの優先するデータの場所 ([複数地域](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)) に関連付けられます。</li><li> 外部メンバーを含むグループのメンバーシップをレビューします ([アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview))。</li><li>アクセスする前に、従業員またはゲスト ユーザーは関連する法的要件またはコンプライアンス要件の免責事項を確認している必要があります。([利用規約](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou))。</li><li>特定の[外部ユーザーも存在する分類](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)を使用して、Office 365 グループを識別し、報告します。</li><li>メンバーシップを非表示にする必要がある秘密のグループは、グループ作成時に [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) コマンドレット (HiddenGroup-MembershipEnabled スイッチを使用) を使用して作成する必要があります。</li><li>[暗号化を使用してコンテンツへのアクセスを制限](https://docs.microsoft.com/Office365/SecurityCompliance/encryption-sensitivity-labels)して、特定の Office 365 グループに公開するように組織の[機密ラベル](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)を定義します。</li><li>[Windows 情報保護と機密ラベル](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)を使用して、機密性の高いコンテンツが Windows を実行している組織のデバイス上に放置されないようにします。 |
| 次のステップ      | <ul><li> サイト デザインとサイト スクリプトを使用して、新しいサイトの作成時に実行される既定の[アクション](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/)を定義します。たとえば、ネイティブでサポートされていない構成を適用するために、[外部共有設定を構成](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting)したり、[Microsoft Flow を起動して Azure 関数を呼び出す](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function)ようにします。</li><li> [Office 365 のラベルと DLP を使用して、Office 365 グループに関連付けられたサイトから SharePoint Online のファイルを保護する](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)ための要件を文書化します。</li><li>Office 365 グループに接続されている [SharePoint Online サイトとファイルをセキュリティで保護する](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files)ための組織の要件を文書化します。 </li><li>コンテンツを保護するために[機密ラベル](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)を特定のユーザーまたはグループに発行するための組織の要件を文書化します。</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>グループの管理機能の計画チェックリスト

Azure Active Directory を使用して、さまざまなグループに関連するコントロールを管理できます。グループ設定の構成に関する詳細については、「[グループの設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)」を参照してください。

次の表を使用して、組織の要件を展開するために必要な機能を決定できます。これは、計画を進めるために必要なライセンスの決定に役立ちます。

| **機能**      | **詳細**                                    | **Azure AD Premium ライセンスが必要** | **決定事項** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| グループの名前付けポリシー | プレフィックス サフィックスに基づくカスタム ブロックの単語を使用します。 | P1                                    |      TBD     |
| グループの分類 | チームに分類を割り当てます。 | P1                                    |   TBD        |
| グループのゲスト アクセス | ゲストがグループに追加されることを許可または禁止します。 | 不要                                    |  TBD        |
| グループの作成 | チームの作成を管理者に限定します。 | 不要                                    |   TBD        |
| グループの作成 | チームの作成をセキュリティ グループのメンバーに限定します。 | P1                                    |     TBD      |
| グループの使用方法のガイドライン | すべてのグループ作成のエンドポイントに表示される、「グループの使用方法のガイドライン」にリンクを設定します。 | P1                                    |   TBD        |
| 非表示のメンバーシップ | グループのメンバーでないユーザーから、Office 365 グループのメンバーを非表示にします。 | 不要                                    |   TBD        |
| 有効期限ポリシー | 有効期限ポリシーを設定することにより、Office 365 グループのライフ サイクルを管理します。 | P1                                    |  TBD        |
| グループのアクティビティ レポート | 組織内の Office 365 グループのアクティビティに関する詳細を分析したり、作成中および使用中の Office 365 グループの数を確認できます。 | 不要                                    |    TBD       |
| アイテム保持ポリシー | セキュリティ/コンプライアンス センターで Office 365 グループのアイテム保持ポリシーを設定して、特定の期間内のデータを保持または削除します。**注:** この機能を使用するには、Office 365 Enterprise E3 以上のライセンスが必要です。 | 不要                                    |    TBD       |
| データ損失防止ポリシー | Office 365 グループに接続されたサイト全体で機密情報を特定し、偶発的な共有を回避します。**注:** この機能を使用するには、Office 365 Enterprise E3 以上のライセンスが必要です。 | 不要                                    |     TBD      |
| アーカイブと復元 | チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。 | 不要                                    |   TBD        |
| アクセス レビュー | レビューを実行して、内部ユーザーとゲスト ユーザーの両方のグループ メンバーシップを効率的に管理します | P2                                    |   TBD       |
| 利用規約 | エンド ユーザーに情報を提示するために組織が使用できる簡単な方法。このプレゼンテーションにより、ユーザーは法的要件またはコンプライアンス要件に関連する免責事項を確認できます。 | P1                                    |         TBD  |
