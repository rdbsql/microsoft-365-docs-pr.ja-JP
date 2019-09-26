---
title: Microsoft コンプライアンスマネージャーの概要
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーは、Microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールです。 コンプライアンスマネージャーを使用すると、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。
ms.openlocfilehash: c88b45fb568b0fe29bc967676ea09e89e9084a62
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085431"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft コンプライアンスマネージャー (プレビュー)

> [!IMPORTANT]
> コンプライアンス マネージャーは、21Vianet が運用している Office 365、Office 365 Germany、Office 365 U.S. Government Community High (GCC High)、Office 365 Department of Defense では使用できません。

[Microsoft コンプライアンスマネージャー (プレビュー)](https://servicetrust.microsoft.com/ComplianceManager)は、無料のワークフローベースのリスク評価ツールであり、microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証できます。 Microsoft 365、Office 365、または Azure Active Directory サブスクリプションの一部であるコンプライアンスマネージャーは、Microsoft クラウドサービスの共有責任モデルにおける法令遵守の管理をサポートしています。 コンプライアンスマネージャーは、標準、規制、統制の実装の詳細と Microsoft サービス評価のテスト結果を表示するための一元的なダッシュボードを提供します。 また、カスタムコントロールの実装と組織に固有のコンプライアンスの追跡を管理するためのツールも含まれています。

コンプライアンスマネージャーを使用すると、組織は次のことを行うことができます。
  
- 監査者に提供された詳細なコンプライアンス情報と、組織に適用される標準および規制に関するコンプライアンス自己評価を統合して、監査者や規制機関に提供します。 これには、国際標準化機構 (ISO)、米国標準技術局 (NIST)、健康保険の携行性と責任に関する法律 (HIPAA)、一般的なデータ保護規則 (GDPR) とその他の多数のもの。
- コンプライアンスおよび評価に関連するアクティビティの割り当て、追跡、記録を行うことができます。これにより、組織がチームの障壁を超えてコンプライアンス目標を達成できるようになります。
- コンプライアンススコアを提供して、進捗状況を追跡したり、組織のリスクを軽減するための監査制御を優先順位付けしたりできます。
- セキュリティで保護されたリポジトリを提供して、コンプライアンスアクティビティに関連する証拠およびその他の成果物をアップロードして管理します。
- 監査、監督、およびその他のコンプライアンスレビュー担当者に対して、Microsoft と組織で実施されたコンプライアンスアクティビティを文書化する詳細な Microsoft Excel レポートを作成します。

> [!NOTE]
> コンプライアンスマネージャーで提供されるお客様のアクションは推奨事項です。実装の前に、それぞれの規制環境でこれらの推奨事項の有効性を評価することは、組織によって行われます。 コンプライアンスマネージャーの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。

## <a name="compliance-manager-relationships"></a>コンプライアンスマネージャーの関係

コンプライアンスマネージャーは、コンプライアンス管理アクティビティを支援するために、いくつかのコンポーネントを使用します。 これらのコンポーネントは連携して、監査者のための完全な管理ワークフローと煩わしさのないコンプライアンスレポートを提供します。

次の図は、コンプライアンスマネージャーの主要なコンポーネント間の関係を示しています。

![コンプライアンスマネージャーバージョン3のリレーションシップ](media/compliance-manager-relationships.png)

## <a name="groups"></a>グループ

[グループ](working-with-compliance-manager.md#groups)は、評価を組織化し、同じまたは関連する顧客管理のコントロールを持つ評価間で共通情報とワークフロータスクを共有できるようにするコンテナーです。 同じグループ内の2つの異なる評価がカスタマー管理コントロールを共有する場合、コントロールの実装の詳細、テスト、および状態の完了は、グループ内の他の評価の同じコントロールに自動的に同期されます。 これにより、グループ全体の各コントロールに割り当てられたアクションアイテムが統一され、作業の重複が減少します。 グループを使用して整理することもできます。 コンプライアンス作業を整理するのに役立つ、年、地域、コンプライアンス標準、またはその他のグループによる評価。

## <a name="assessments"></a>講習

[評価](working-with-compliance-manager.md#assessments)は、クラウドサービスのセキュリティとコンプライアンスのリスクを評価するために、Microsoft と組織の間で共有される責任に基づいて統制できるコンテナーです。 評価は、コンプライアンス標準、適用可能なデータ保護標準、規制、法によって規定されるデータ保護保護を実装するのに役立ちます。 選択された Microsoft cloud service の選択された業界標準に対して、データの保護とコンプライアンスの状況を識別するのに役立ちます。 評価は、認定基準に対応する評価に含まれるコントロールの実装によって完了します。

既定では、コンプライアンスマネージャーは組織に対して次の評価を作成します。

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

評価には、いくつかのコンポーネントが含まれます。
  
- **スコープ内サービス**: 各評価は、Microsoft サービスの特定のセットに適用されます。
- **Microsoft 管理コントロール**: 各クラウドサービスについて、microsoft は、適用される標準および規制に関する一連のコンプライアンス制御を実装して管理します。
- **顧客管理コントロール**: これは、各コントロールに対してアクションを実行するときに、組織によって実装されたコントロールのコレクションです。
- **評価スコア**: 評価での顧客管理コントロールの可能なスコアの合計の割合です。 これにより、各コントロールに割り当てられたアクションの実装を追跡できます。

## <a name="controls"></a>コントロール

[統制](working-with-compliance-manager.md#controls-and-actions)はコンプライアンスマネージャーのコンプライアンスプロセスコンテナーで、コンプライアンスアクティビティを管理する方法を定義します。 これらのコントロールは、対応する認定資格または規制の評価構造と一致するように、コントロールファミリ内に整理されています。

- **コントロール ID**: 対応する証明書または規制から選択したコントロールの名前。
- **コントロールのタイトル**: 対応する証明書または規制からのコントロール ID のタイトル。
- **記事 ID**: このフィールドは GDPR の評価にのみ使用され、対応する GDPR の記事番号を指定します。
- **説明**: 対応する証明書または規制からのコントロールのテキスト。 著作権制限により、ISO 標準に関連する情報へのリンクが記載されています。

![コンプライアンスマネージャーバージョン3のコントロール](media/compliance-manager-controls.png)

コンプライアンスマネージャー、 **Microsoft 管理コントロール**、**顧客管理**コントロール、および**共有管理コントロール**には、3種類のコントロールがあります。

### <a name="microsoft-managed-controls"></a>Microsoft 管理コントロール

Microsoft は、各クラウドサービスについて、さまざまな標準および規制への Microsoft のコンプライアンスの一環として、一連の制御を実装して管理しています。 各コントロールは、Microsoft がどのように実装されたか、およびその実装が Microsoft および/または独立したサードパーティの監査者によってテストおよび検証された方法についての詳細を提供します。

### <a name="customer-managed-controls"></a>顧客管理のコントロール

これは、組織で管理されているコントロールのコレクションです。 組織は、特定の標準または規制のコンプライアンスプロセスの一環として、お客様が管理する統制の実装を担当しています。 お客様が管理するコントロールは、対応する認定資格または規制の制御ファミリに分類されます。 顧客管理コントロールを使用して、コンプライアンスアクティビティの一部として Microsoft が提案する推奨される処置を実施します。 組織は、各カスタマー管理コントロールで規範的なガイダンスおよび推奨されるお客様のアクションを使用して、そのコントロールの実装と評価のプロセスを管理できます。

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

組織内のユーザーは、コンプライアンスマネージャーを使用して、割り当てられているすべての評価からお客様が管理するコントロールを確認できます。 ユーザーがコンプライアンスマネージャーにサインインし、**アクションアイテム**ダッシュボードを開くと、それらに割り当てられているアクションアイテムのリストが表示されます。 ユーザーに割り当てられたコンプライアンスマネージャーの役割に応じて、実装またはテストの詳細を提供したり、状態を更新したり、アクションアイテムを割り当てたりすることができます。

通常、証明書コントロールは、ある人物によって実装され、別のユーザーによってテストされます。 たとえば、実装のために1人のユーザーに対して最初に割り当てられたアクションアイテムが完了すると、次の担当者にアクションアイテムが割り当てられ、証拠をテストしてアップロードできます。 コントロール割り当てに十分な権限を持つユーザーは、アクションアイテムを割り当てて再割り当てすることができます。 これにより、コントロールの割り当ての集中管理が可能になり、実装とテスト担当者との間のアクションアイテムのルーティングが分散化されます。

## <a name="permissions"></a>アクセス許可

コンプライアンスマネージャーは、役割ベースのアクセス制御のアクセス[許可モデル](working-with-compliance-manager.md#permissions)を使用します。 既定では、Azure Active Directory (Azure AD) アカウントを持つ組織内のすべてのユーザーは、完全なアクセス権を持ち、コンプライアンスマネージャーで任意のアクションを実行できます。 組織によって役割ベースのアクセス制御が実装されている場合、定義されたコンプライアンスマネージャーの役割に割り当てられていないすべてのユーザーにはゲストアクセスが割り当てられます。 Microsoft サービス担当者は、入力またはアップロードするデータへの継続的なアクセス権を持っていません。

既定のアクセス許可から変更し、完全な役割ベースのアクセス制御モデルを実装するには、各コンプライアンスマネージャーの役割に少なくとも1人のユーザーを追加する必要があります。 ユーザーが役割に追加されると、その役割に割り当てられた操作を実行するためのアクセス許可が、すべてのユーザーが使用できる既定のアクセス許可のセットから削除されます。 この役割を使用してプロビジョニングされたユーザーのみが、コンプライアンスマネージャーにアクセスして、その役割によって許可されるアクションを実行できます。

評価を管理するための役割にユーザーを追加した場合、その役割のメンバーのみが評価を管理できます。 ユーザーが評価でデータを読み取ることを許可する役割にユーザーを追加しない場合は、組織内のすべてのユーザーがコンプライアンスマネージャーにアクセスして、任意の評価でデータを読み取ることができます。
  
## <a name="manage-evidence"></a>証拠を管理する

コンプライアンスマネージャーは、顧客管理のコントロールのテストと検証を実行するための実装タスクの証拠を格納できます。 証拠には、ドキュメント、スプレッドシート、スクリーンショット、画像、スクリプト、スクリプト出力ファイル、およびその他のファイルが含まれます。 また、コンプライアンスマネージャーはテレメトリを自動的に取得し、セキュリティで保護されたスコアと統合されたアクションアイテムの証拠レコードを作成します。 コンプライアンスマネージャーに証拠としてアップロードされたデータは、Microsoft クラウドストレージサイト上の米国に保存されます。 このデータは、東南アジアおよび西ヨーロッパにある Azure 地域間でレプリケートされます。

## <a name="templates"></a>テンプレート

コンプライアンスマネージャーには、評価用に事前に構成された[テンプレート](working-with-compliance-manager.md#templates)が用意されており、コンプライアンスのニーズに合わせて顧客管理のコントロール用のカスタマイズされたテンプレートを作成できます。 新しいテンプレートは、Excel ファイルからコントロールの情報をインポートして作成するか、既存のテンプレートのコピーからテンプレートを作成することができます。

コンプライアンスマネージャーに含まれる事前構成済みテンプレートは次のとおりです。
 
- [ISO 27001:2013](https://www.iso.org/obp/ui/#iso:std:iso-iec:27001:ed-2:v1:en)
- [ISO 27018:2019](https://www.iso.org/obp/ui/#iso:std:iso-iec:27018:ed-2:v1:en)
- [NIST 800-53](https://csrc.nist.gov/publications/detail/sp/800-53/rev-4/final)
- [NIST 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)
- [NIST Cybersecurity Framework (CSF)](https://www.nist.gov/cyberframework)
- [Cloud Security アライアンス (CSA) Cloud Control Matrix (CCM) 3.0.1](https://cloudsecurityalliance.org/working-groups/cloud-controls-matrix/#_overview)
- [連邦金融機関調査協議会 (FFIEC) Information Security ブックレット](https://ithandbook.ffiec.gov/it-booklets/information-security.aspx) 
- [HIPAA](https://www.hhs.gov/hipaa/for-professionals/index.html) / の[ヒット](https://www.hhs.gov/hipaa/for-professionals/special-topics/hitech-act-enforcement-interim-final-rule/index.html)
- [FedRAMP モデレート](https://www.fedramp.gov/documents/)
- [欧州連合 GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN)

## <a name="compliance-score"></a>コンプライアンススコア

コンプライアンス[スコア](compliance-score-methodology.md)は、組織がコンプライアンスを理解し管理するのに役立つコンプライアンスマネージャーのコアコンポーネントです。 Microsoft の[セキュリティで保護さ](../security/mtp/microsoft-secure-score.md)れたスコアと同様に、コンプライアンススコアは、組織内のデータ保護、プライバシー、およびセキュリティに関連するアクティビティの動作ベースのスコアリングシステムです。 評価のコンプライアンススコアは、特定の標準または規制に準拠したものです。 数値スコアが大きいほど、評価のコンプライアンス状況が改善されます。 コンプライアンススコアの方法論を理解することは、必要な顧客管理の制御アクションに優先順位を指定する上で重要です。
  
> [!IMPORTANT]
> 組織が特定の標準や規制を遵守しているかの絶対的測定値は、コンプライアンス スコアでは表せません。ユーザーが設定した、個人のデータやプライバシーに関するリスクを軽減できるコントロールをどの程度採用したかがコンプライアンス スコアによって表されます。標準や規制に準じていることを保証するサービスは提供されておらず、コンプライアンス スコアも何かを保証するものではありませんので、ご注意ください。

## <a name="secure-score-integration"></a>セキュリティで保護されたスコアの統合

コンプライアンスマネージャーは[Microsoft セキュリティスコア](../security/mtp/microsoft-secure-score.md)と統合されており、同期されたアクションアイテムのコンプライアンススコアに、安全スコアクレジットを自動的に適用します。 これは個別のアクションアイテムに対して構成でき、アイテム間の継続的な更新が提供されます。

たとえば、組織内の Azure Rights Management をアクティブ化するためのセキュリティ関連の要件があります。これは、コンプライアンス関連のアクションアイテムにも適用されます。 Secure Score によって Azure Rights Management がアクティブ化されて処理されると、コンプライアンスマネージャーは更新の通知を受け取り、アクションアイテムのスコアは完了クレジットで自動的に更新されます。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

[コンプライアンスマネージャーの作業](working-with-compliance-manager.md)を開始して、組織の法令遵守活動を管理します。

## <a name="resources"></a>リソース

- [対話型ガイド: コンプライアンスマネージャーを使用してデータ保護コントロールを評価し、強化します。](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft Security、プライバシー、コンプライアンスの技術コミュニティ](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)