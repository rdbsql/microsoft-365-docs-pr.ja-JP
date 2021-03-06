---
title: Microsoft コンプライアンスマネージャーの概要
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーについて説明します。これには、Microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールがあります。
ms.openlocfilehash: 514ee0e032e378c407713254d5d11fcd41a8d91c
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016130"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft コンプライアンスマネージャー (プレビュー)

> [!IMPORTANT]
> コンプライアンス マネージャーは、21Vianet が運用している Office 365、Office 365 Germany、Office 365 U.S. Government Community High (GCC High)、Office 365 Department of Defense では使用できません。

**この記事の**内容: この記事では、コンプライアンスマネージャーの概要と主要コンポーネントについて説明します。

**更新プログラムについて説明**:[コンプライアンスマネージャーのリリースノート](compliance-manager-release-notes.md)を参照して、新着情報および既知の問題を確認してください。

## <a name="what-is-compliance-manager"></a>コンプライアンスマネージャーとは

Microsoft[コンプライアンスマネージャー (プレビュー)](https://servicetrust.microsoft.com/ComplianceManager)は、microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを管理するための、Microsoft Service Trust Portal の無料ワークフローベースのリスク評価ツールです。 Microsoft 365、Office 365、または Azure Active Directory サブスクリプションの一部であるコンプライアンスマネージャーは、Microsoft クラウドサービスの共有責任モデルにおける法令遵守の管理をサポートしています。

コンプライアンスマネージャーを使用すると、組織は次のことを行うことができます。
  
- 監査者に提供された詳細なコンプライアンス情報と、組織に適用される標準および規制に関するコンプライアンス自己評価を統合して、監査者や規制機関に提供します。 これには、国際標準化機構 (ISO)、米国標準技術局 (NIST)、健康保険の携行性と責任者の法律 (HIPAA)、一般的なデータ保護規則 (GDPR)、その他多くの規制が盛り込まれています。
- コンプライアンスおよび評価に関連するアクティビティの割り当て、追跡、記録を行うことができます。これにより、組織がチームの障壁を超えてコンプライアンス目標を達成できるようになります。
- コンプライアンススコアを提供して、進捗状況を追跡したり、組織のリスクを軽減するための監査制御を優先順位付けしたりできます。
- セキュリティで保護されたリポジトリを提供して、コンプライアンスアクティビティに関連する証拠およびその他の成果物をアップロードして管理します。
- 監査、監督、およびその他のコンプライアンスレビュー担当者に対して、Microsoft と組織で実施されたコンプライアンスアクティビティを文書化する詳細な Microsoft Excel レポートを作成します。

  
> [!IMPORTANT]
> コンプライアンス スコアおよびコンプライアンス マネージャーからの推奨事項は、コンプライアンスの保証として解釈してはいけません。 お客様は、お客様の規制環境に応じて、カスタマーコントロールの有効性を評価および検証することができます。 これらのサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件に従っています。 [セキュリティとコンプライアンスのための Microsoft 365 ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)も参照してください。

## <a name="relationship-to-compliance-score"></a>コンプライアンススコアとの関係

[Microsoft コンプライアンススコア (プレビュー)](compliance-score.md)は、microsoft 365 コンプライアンスセンターの機能の1つで、組織の法令遵守状況についての最上位レベルのビューを提供します。 データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。 総合的なコンプライアンススコアを把握することで、組織はコンプライアンスを理解し管理することができます。 [コンプライアンススコアの計算方法](compliance-score-methodology.md)について理解します。

コンプライアンスマネージャーは、コンプライアンススコアと同じバックエンドを共有します。 両方のツールのパブリックプレビューフェーズでは、コンプライアンスマネージャーがカスタムコントロールの実装を管理します。 [コンプライアンススコアとコンプライアンスマネージャーの関係](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)の詳細については、「」を参照してください。

## <a name="compliance-manager-components"></a>コンプライアンスマネージャーのコンポーネント

コンプライアンスマネージャーは、コンプライアンス管理アクティビティを支援するためにいくつかのコンポーネントを使用します。 これらのコンポーネントは連携して、監査者のための完全な管理ワークフローと煩わしさのないコンプライアンスレポートを提供します。

次の図は、コンプライアンスマネージャーの主要なコンポーネント間の関係を示しています。

![コンプライアンスマネージャーバージョン3のリレーションシップ](../media/compliance-manager-relationships.png)

## <a name="groups"></a>グループ

[グループ](working-with-compliance-manager.md#groups)は、評価を組織化し、同じまたは関連する顧客管理のコントロールを持つ評価間で共通情報とワークフロータスクを共有できるようにするコンテナーです。 同じグループ内の2つの異なる評価がカスタマー管理コントロールを共有する場合、コントロールの実装の詳細、テスト、および状態の完了は、グループ内の他の評価の同じコントロールに自動的に同期されます。 これにより、グループ全体の各コントロールに割り当てられたアクションアイテムが統一され、作業の重複が減少します。 グループを使用して整理することもできます。 コンプライアンス作業を整理するのに役立つ、年、地域、コンプライアンス標準、またはその他のグループによる評価。

## <a name="assessments"></a>講習

[評価](working-with-compliance-manager.md#assessments)は、クラウドサービスのセキュリティとコンプライアンスのリスクを評価するために、Microsoft と組織の間で共有されている責任に基づいて制御を構成できるコンテナーです。 評価は、コンプライアンス標準、適用可能なデータ保護標準、規制、法によって規定されるデータ保護保護を実装するのに役立ちます。 選択された Microsoft cloud service の選択された業界標準に対して、データの保護とコンプライアンスの状況を識別するのに役立ちます。 評価は、認定基準に対応する評価に含まれるコントロールの実装によって完了します。

既定では、コンプライアンスマネージャーは組織に対して次の評価を作成します。

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

評価にはいくつかのコンポーネントがあります。
  
- **スコープ内サービス**: 各評価は、Microsoft サービスの特定のセットに適用されます。
- **Microsoft 管理コントロール**: 各クラウドサービスについて、microsoft は、適用される標準および規制に関する一連のコンプライアンス制御を実装して管理します。
- **顧客管理コントロール**: これらのコントロールは、各コントロールに対してアクションを実行すると、組織によって実装されます。
- **評価スコア**: 評価での顧客管理コントロールの可能なスコアの合計の割合です。 これにより、各コントロールに割り当てられたアクションの実装を追跡できます。

## <a name="controls"></a>コントロール

[統制](working-with-compliance-manager.md#controls-and-actions)はコンプライアンスマネージャーのコンプライアンスプロセスコンテナーで、コンプライアンスアクティビティを管理する方法を定義します。 これらのコントロールは、対応する認定資格または規制の評価構造と一致するように、コントロールファミリ内に整理されています。

- **コントロール ID**: 対応する証明書または規制から選択したコントロールの名前。
- **コントロールのタイトル**: 対応する証明書または規制からのコントロール ID のタイトル。
- **記事 ID**: このフィールドは GDPR の評価にのみ使用され、対応する GDPR の記事番号を指定します。
- **説明**: 対応する証明書または規制からのコントロールのテキスト。 著作権制限により、ISO 標準に関連する情報へのリンクが記載されています。

![コンプライアンスマネージャーバージョン3のコントロール](../media/compliance-manager-controls.png)

コンプライアンスマネージャー、 **Microsoft 管理コントロール**、**顧客管理**コントロール、および**共有管理コントロール**には、3種類のコントロールがあります。

### <a name="microsoft-managed-controls"></a>Microsoft 管理コントロール

Microsoft は、各クラウドサービスについて、さまざまな標準および規制への Microsoft のコンプライアンスの一環として、一連の制御を実装して管理しています。 各コントロールは、Microsoft がどのように実装されたか、およびその実装が Microsoft および/または独立したサードパーティの監査者によってテストおよび検証された方法についての詳細を提供します。

### <a name="customer-managed-controls"></a>顧客管理のコントロール

お客様が管理するコントロールは、組織によって管理されます。 組織は、特定の標準または規制のコンプライアンスプロセスの一環として、お客様が管理する統制の実装を担当しています。 お客様が管理するコントロールは、対応する認定資格または規制の制御ファミリに分類されます。 顧客管理コントロールを使用して、コンプライアンスアクティビティの一部として Microsoft が提案する推奨される処置を実施します。 組織は、各カスタマー管理コントロールで規範的なガイダンスおよび推奨されるお客様のアクションを使用して、そのコントロールの実装と評価のプロセスを管理できます。

評価内の顧客管理コントロールには、ワークフロー管理機能が組み込まれているため、評価の完了に向けた進捗状況の管理と追跡にも使用できます。 このワークフロー機能を使用すると、次のことを行うことができます。

- 各コントロールのアクションアイテムを割り当てる
- 割り当てられたアクションアイテムを追跡する
- コントロールの実装の証拠をアップロードする
- コントロールのテストと検証を文書化する
- アクションアイテムを実装およびテスト済みとしてマークする

たとえば、組織内のコンプライアンス責任者が、推奨されるアクションを実行するために必要な権限とアクセス許可を持つ、アクションアイテムを IT 管理者に割り当てます。 IT 管理者は、実装タスクの証拠 (構成またはポリシー設定のスクリーンショット) をアップロードし、完了した場合に、そのアクションアイテムをコンプライアンスオフィサーに戻します。 コンプライアンス担当者が収集した証拠を評価し、コントロールの実装をテストして、コンプライアンスマネージャーで実装日とテスト結果を記録します。

### <a name="shared-management-controls"></a>共有管理コントロール

共有コントロールとは、Microsoft とお客様の両方が、実装の責任を共有するすべてのコントロールを指します。 たとえば、個人の審査、アカウント、パスワード管理、暗号化に関連するコントロールは、Microsoft とお客様の両方によるアクションを必要とします。

## <a name="action-items"></a>アクションアイテム

[アクションアイテム](working-with-compliance-manager.md#controls-and-actions)は、組み込みのワークフロー管理機能の一部として、お客様が管理するコントロールに含まれています。これを使用すると、評価完了までの進捗状況を管理および追跡できます。

組織内のユーザーは、コンプライアンスマネージャーを使用して、割り当てられているすべての評価からお客様が管理するコントロールを確認できます。 ユーザーがコンプライアンス マネージャーにサインインし、**[アクション アイテム]** ダッシュボードを開くと、割り当てられているアクション アイテムのリストが表示されます。 ユーザーに割り当てられているコンプライアンス マネージャー ロールによっては、実装またはテストの詳細の入力、ステータスの更新、アクション アイテムの割り当てを行うことができます。

通常、証明書コントロールは、ある人物によって実装され、別のユーザーによってテストされます。 たとえば、実装のために1人のユーザーに最初に割り当てられたアクションアイテムが完了した後、それらのアクションアイテムは、証拠をテストおよびアップロードする次の担当者に割り当てられます。 コントロール割り当てに十分な権限を持つユーザーは、アクションアイテムを割り当てて再割り当てすることができます。 これにより、コントロールの割り当ての集中管理が可能になり、実装とテスト担当者との間のアクションアイテムのルーティングが分散化されます。

コンプライアンススコアの**向上アクション**は、コンプライアンスマネージャーの**アクションアイテム**に相当するものであることに注意してください。

## <a name="permissions"></a>アクセス許可

コンプライアンス マネージャーでは、役割に基づくアクセス許可モデルが使用されています。 コンプライアンス マネージャーにはユーザー ロールが割り当てられているユーザーのみがアクセスでき、各ユーザーに許可される操作は役割の種類によって制限されます。 各アクセス許可に対して許可されるアクションを示す[表を表示](working-with-compliance-manager.md#permissions)します。

コンプライアンスマネージャーのポータル管理者は、次の手順に従って、コンプライアンスマネージャー内の他のユーザーに対するアクセス許可を設定できます。

1. [上側の**追加**] ドロップダウンメニューで、[**管理者**]、[**設定**] の順に選択します。
2. ここから、割り当てる役割を選択し、その役割に割り当てる従業員を追加します。 これで、ユーザーは特定のアクションを実行できるようになります。

[Azure Active Directory (AZURE AD) でグローバルリーダーロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)が割り当てられているユーザーには、コンプライアンスマネージャーにアクセスするための読み取り専用のアクセス許可が付与されます。 ただし、コンプライアンスマネージャー内でデータを編集したり、アクションを実行したりすることはできません。

既定の**ゲストアクセス**の役割がなくなりました。 コンプライアン スマネージャーにアクセスして操作するには、各ユーザーは役割を割り当てられている必要があります。
  
## <a name="manage-evidence"></a>証拠を管理する

コンプライアンスマネージャーは、お客様が管理するコントロールのテストと検証に関する実装タスクの証拠を格納できます。 証拠には、ドキュメント、スプレッドシート、スクリーンショット、画像、スクリプト、スクリプト出力ファイル、およびその他のファイルが含まれます。 また、コンプライアンスマネージャーはテレメトリを自動的に取得し、セキュリティで保護されたスコアと統合されたアクションアイテムの証拠レコードを作成します。 コンプライアンスマネージャーに証拠としてアップロードされたデータは、Microsoft クラウドストレージサイト上の米国に保存されます。 このデータは、東南アジアおよび西ヨーロッパにある Azure 地域間でレプリケートされます。

## <a name="templates"></a>テンプレート

コンプライアンスマネージャーには、評価用に事前に構成された[テンプレート](working-with-compliance-manager.md#templates)が用意されており、コンプライアンスのニーズに合わせて顧客管理のコントロール用のカスタマイズされたテンプレートを作成できます。 新しいテンプレートは、Excel ファイルからコントロールの情報をインポートして作成するか、既存のテンプレートのコピーからテンプレートを作成することができます。

事前に構成されたテンプレートは次のとおりです。

1. [ブラジルの一般データ保護法 (LGPD)](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [カリフォルニアコンシューマ Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (プレビュー)
3. [Cloud Security アライアンス (CSA) Cloud Controls Matrix (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [Dubai Information Security Resolution (DGISR)](https://go.microsoft.com/fwlink/?linkid=2131193)
5. [欧州連合 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
6. [連邦金融機関調査協議会 (FFIEC) Information Security ブックレット](https://go.microsoft.com/fwlink/?linkid=2109077)
7. [FedRAMP モデレート](https://go.microsoft.com/fwlink/?linkid=2108869)
8. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078)  / [エコー](https://go.microsoft.com/fwlink/?linkid=2109079)
9. [Irap](https://go.microsoft.com/fwlink/?linkid=2113709)  / [オーストラリア自治体 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (プレビュー)
10. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
11. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
12. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
13. [Microsoft 365 データ保護のベースライン](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
14. [NIST 800-53 リビジョン4](https://go.microsoft.com/fwlink/?linkid=2109075)
15. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
16. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
17. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
18. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

## <a name="secure-score-integration"></a>セキュリティで保護されたスコアの統合

コンプライアンスマネージャーは[Microsoft セキュリティスコア](../security/mtp/microsoft-secure-score.md)と統合されており、同期されたアクションアイテムのコンプライアンススコアに、安全スコアクレジットを自動的に適用します。 これは、個々のアクションアイテムまたはすべてのアクションに対して構成でき、セキュリティで保護されたスコアからの更新を提供します。

たとえば、組織内の Azure Rights Management をアクティブ化するためのセキュリティ関連の要件があります。これは、コンプライアンス関連のアクションアイテムにも適用されます。 Secure Score によって Azure Rights Management がアクティブ化されて処理されると、コンプライアンスマネージャーは更新の通知を受け取り、アクションアイテムのスコアは完了クレジットで自動的に更新されます。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

[コンプライアンスマネージャーの作業](working-with-compliance-manager.md)を開始して、組織の法令遵守活動を管理します。

## <a name="resources"></a>リソース

- [対話型ガイド: コンプライアンスマネージャーを使用してデータ保護コントロールを評価し、強化します。](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft Security、プライバシー、コンプライアンスの技術コミュニティ](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)