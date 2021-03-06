---
title: 一般データ保護規則
description: 一般データ保護規則 (GDPR) に役立つ情報を参照しながら、Microsoft 技術ガイダンスについて説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d1e6730d215fcef6bd0cad6244c82b960ed39ce
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44800022"
---
# <a name="general-data-protection-regulation-summary"></a>一般データ保護規則の概要

一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。 このドキュメントでは、Microsoft の製品とサービスを使用する際の GDPR に基づく権利の尊重と義務の履行に役立つ情報を提供します。 「[GDPR の推奨アクション プラン](gdpr-action-plan.md)」および「[アカウンタビリティ対応準備チェックリスト](gdpr-arc.md)」では、GDPR コンプライアンスの評価と実装のための追加リソースを参照できます。

## <a name="terminology"></a>用語

このドキュメントで使用されている GDPR 用語の役に立つ定義:

- **データ コントローラー (コントローラー)**: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。  
- **個人データとデータ主体**: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。  
- **処理者**: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。  
- **顧客データ**: ビジネス運営における日々の業務で作成および保存されるデータ。

## <a name="what-is-the-gdpr"></a>GDPR とは?

GDPR では、組織によって収集された個人データを管理する権利が人々に付与されます。 これらの権利は、データ主体の要求 (DSR) 経由で行使できます。 組織は、DSR およびデータ違反に関する情報をタイムリーに提供し、データ保護影響評価 (DPIA) を実行する必要があります。

GDPR 要件を実装または評価する場合は、いくつかの事項について考慮する必要があります。

- GDPR コンプライアンスのデータ プライバシー ポリシーの開発または評価。
- 組織のデータ セキュリティの評価。
- データ コントローラーとなる人は?
- どのようなデータ セキュリティ プロセスを実行する必要があるか?

「[GDPR の推奨アクション プラン](gdpr-action-plan.md)」と「[アカウンタビリティ対応準備チェックリスト](gdpr-arc.md)」では、考慮するポイントがさらに示される場合があります。

GDPR 基準を満たすには、次のタスクが必要です。 実装に関する詳細については、リスト内のリンクを参照してください。  

- **[データ主体の要求 (DSR)](gdpr-data-subject-requests.md)**。 個人データに関するアクション (変更、制限、アクセス) を実行するように、データ主体がコントローラーに対して行う正式な要求。
- **[違反の通知](gdpr-breach-notification.md)**。 GDPR における個人データ違反とは、「送信、保存、またはその他の方法で処理される個人データの偶発的または違法の破損、損失、改変、不正漏洩、またはアクセスを引き起こすセキュリティ違反」のことです。
- **[データ保護影響評価 (DPIA)](gdpr-data-protection-impact-assessments.md)**。 データ管理者は、GDPR に基づいて「自然人の権利と自由を危険にさらす可能性が高い」データ操作に関して DPIA を準備する必要があります。

上記で説明したように、GDPR の推奨アクション プランとアカウンタビリティ対応準備チェックリストでは、Microsoft の製品とサービスの使用において GDPR 準拠を実装または評価するためのガイドが提供されています。

## <a name="data-subject-request-dsr"></a>データ主体の要求 (DSR)

GDPR では、個人 (またはデータ主体) に対して、個人データの処理に関連した特定の権利が付与されます。それには、不正確なデータを修正する権利、データを抹消する権利、処理を制限する権利、自分のデータを受け取る権利、および自分のデータを別の管理者に送信するという要求を実行する権利が含まれます。 コントローラーには、タイムリーで一貫性のある GDPR 応答を提供する責任があります。 技術的な詳細については、「[データ主体の要求](gdpr-data-subject-requests.md)」を参照してください。  

### <a name="dsr-faqs"></a>DSR についてよく寄せられる質問

**DSR の完了のためには、どのようなアクションが必要ですか?**

DSR には、検出、アクセス、修正、制限、エクスポート、削除の 6 つのアクティビティが含まれています。

**データ ソースとは?**

組織のデータの大部分は、Excel や Outlook などの [Office アプリケーション](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)で生成されます。 また、DSR に関連するデータは、Microsoft の製品とサービスによって生成された[分析情報](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)、および[システム生成ログ](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)でも検索することもできます。

**どのような種類のデータを検索する必要がありますか?**

個人データは、顧客データ、Microsoft の製品とサービスによって生成された分析情報、システム生成ログに含まれていることがあります。

**個人データは、どのように検索するのですか?**

個人データの検索は、Microsoft の製品とサービスによって異なる場合があります。 検索ツールには、[コンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)、または[アプリ内検索](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs)能力が用意されています。 管理者は、ユーザーのアクティビティに関連する[システム生成ログ](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)にアクセスできます。  

**個人データは、どのような形式で利用できるようにする必要がありますか?**

GDPR の「データの移植の権利」により、データ主体は、「構造化された一般的に使用されているコンピューターが読み取り可能な形式」で個人データのコピーを要求できます。また、そうしたファイルを別のデータ管理者に送信するように組織に要求することもできます。

**GDPR で求められていること、および管理者の責任は何ですか?**

GDPR で、管理者に求められる実行項目:

- 前述したように、権利を行使するデータ主体からの要求に対する支援のため、Microsoft は、技術的また組織的に適切な措置を実施する必要があります。
- 各個人が、不正確な個人データを修正したり、データを抹消したり、その処理を制限したり、可読形式でデータを受け取ったり、また該当する場合には別の管理者にそのデータを送信したりする権利の行使を支援します。

**GDPR では何が求められていますか、また処理者としての Microsoft にはどんな責任がありますか?**

前述の権利を行使するデータ主体からの要求に対する支援のために、当社には、技術的また組織的に適切な手段を用意する責任があります。

**オンプレミスのサーバーに関する GDPR の関連情報は、どこにありますか?**

GDPR に関連する一連の記事については、こちらを参照してください。 これらの記事は Microsoft が作成したものであり、SharePoint Server、Exchange Server、Skype for Business Server、Project Server、Office Web Apps Server、Office Online Server のオンプレミス ワークロードと、オンプレミスのファイル共有について推奨されるアプローチを紹介しています。

**Microsoft はデータ主体要求にどのように対応できるのでしょうか?**

オンライン サービスは、管理者であるお客様がデータ主体の要求に対応できるようにする多数の機能を提供しています。 Microsoft のエンタープライズ オンライン サービスと管理コントロールは、データ主体の権利要求に応じた個人データの処理に役立ちます。これにより、Microsoft のクラウドに保管された、管理者の管理対象データに含まれる個人データの検出、アクセス、修正、制限、削除、エクスポートが可能になります。 また、オンライン サービスでは、必要に応じて機械可読形式のデータも提供します。

## <a name="data-protection-impact-assessment"></a>データ保護影響評価

GDPR では、データ管理者は「自然人の権利と自由を危険にさらす可能性が高い」操作処理に関して[データ保護影響評価](gdpr-data-protection-impact-assessments.md) (DPIA) を準備する必要があります。 DPIA の作成を必要とする Microsoft の製品とサービスに固有のものはありません。 むしろ、Microsoft 構成の詳細に依存しています。 Office での考慮事項に関する詳細のリストは、「[DPIA の内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)」を参照してください

### <a name="dpia-faqs"></a>DPIA についてよく寄せられる質問

**DPIA はいつ実施する必要がありますか?**

コントローラーは、個人データのセキュリティに対するリスク、またはデータ侵害から生じるリスクに対処する DPIA を実行する必要があります。 Office のリスク要因の具体例は、「[DPIA が必要であるかどうかの判断](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed)」で説明されています。  

**DPIA の完了には何が必要ですか?**

GDPR では、DPIA に次の事項を含めるよう規定されています。

- DPIA の目的に関するデータ処理作業の必要性および比例性の評価。
- データ主体の権利および自由に関するリスクの評価。
- リスク、セーフガード、セキュリティ対策、メカニズムに対処して、個人データを確実に保護し、GDPR 準拠を実証するための想定された対策。

**管理者としてには、どのような責任がありますか?**

GDPR における管理者は、個人の権利と自由に対して高いリスクをもたらす可能性のあるデータ処理 (特に新しいテクノロジを使用した処理) を実行する前に、DPIA を実施する必要があります。 GDPR には、どのような場合に DPIA を実行する必要があるかに関してて、その一部を示した次のリストが用意されています。

- データ主体への大きな影響 (法的な影響など) があるプロファイリングなどのアクティビティのために実行される自動化処理。  
- 特殊なカテゴリの個人データ (人種や民族、政治的見解などを明らかするデータ) や有罪判決や違反に関するデータを対象とした大規模な処理。  
- 公開アクセス可能な地域での体系的な大規模監視。  

GDPR は、データ主体に対する高いリスクを最低限にするための十分な処理を特定できない場合は、何らかの処理を開始する前に、データ保護機関 (DPA) に相談することも求めています。

**Microsoft は、どのような責任がありますか?**

Microsoft は、エンジニアリング部門および業務部門でプライバシー バイ デザインとプライバシー バイ デフォルトを実施しています。 これらの取り組みの一環として、Microsoft はデータ主体の権利および自由に影響を与える可能性のあるデータ処理操作について、包括的なプライバシー レビューを実行しています。 サービス グループ内に組み込まれているプライバシー チームは、国際法、ユーザーの期待、および当社が明示する方針に沿った敬意ある方法で個人データが処理されるよう、サービスの設計と実装のレビューを実施します。

そうしたプライバシー レビューは細分化される傾向が強く、1 つのサービスに対して数十または数百のレビューが実施されることがあります。 Microsoft では、こうした詳細なプライバシー レビューを、処理グループの大半を網羅するデータ保護影響評価 (DPIA) にまとめ、そのレビューを Microsoft EU データ保護責任者 (DPO) が実施します。 DPO は、データ処理に関連するリスクを評価して、十分な軽減策が講じられるようにします。 DPO は軽減されていないリスクを検出すると、エンジニアリング グループに変更を勧告します。 データ保護リスクが変化すると、DPIA に対するレビューが実行され、更新されます。


処理者としての Microsoft には、GDPR に示されている DPIA 要件へのコンプライアンスを確保するよう、管理者を支援する責任があります。 お客様をサポートするために、将来の更新では、このセクションで Microsoft の DPIA 関連セクションの要約が提供される予定です。その目的は、Microsoft サービスを利用している管理者が、提供された要約を活用して独自の DPIA を作成できるようにするためです。

## <a name="breach-notification"></a>違反の通知

GDPR では、個人データ違反が発生した場合のデータの管理者と処理者のための通知要件が規定されています。 データ処理者として、Microsoft は、必ずお客様が GDPR の違反通知要件を満たせるようにしています。 データ コントローラーは、データ プライバシーに対するリスクを評価し、お客様の DPA に通知する必要がある違反かどうかを判断する責任があります。 Microsoft は、その評価に必要な情報を提供しています。 Microsoft が個人データの侵害を検出して対応する方法の詳細については、「[GDPR の下での違反の通知](gdpr-breach-notification.md)」を参照してください。

### <a name="breach-notification-faqs"></a>違反の通知についてよく寄せられる質問

**GDPR における個人データ違反とは何ですか?**

個人データは、個人に関連する情報のうち、直接的または間接的に個人を特定するために使用できるものを意味します。 個人データ違反とは、「送信、保管またはその他の方法で処理される個人データに対して偶発的または違法な破壊、消失、改変、無断公開、またはアクセスを引き起こすセキュリティ違反」です。

**管理者には、どのような責任がありますか?**

個人の権利と自由に高い危機 (差別、個人情報盗難、詐欺、金銭的損失、名誉毀損など) をもたらす可能性のある個人データ違反が発生した場合、GDPR では次の行動を求めています。

- Microsoft からの通知などによる認識後、72 時間以内に該当するデータ保護機関 (DPA) に通知する。 所定の時間内に DPA に通知していない場合は、その理由を DPA に説明する必要があります。 DPA に対するこの通知は、個人情報リスクが高いリスクに至りそうにない場合でも必要です。
- 違反のデータ主体を過度の遅延なく通知する。

- 違反について文書化し、その中に違反の性質についての説明を含める (影響を受けた人の数、影響を受けたデータ レコードの数、違反の結果、組織として提案する、または実施した是正措置など)。

**処理者としての Microsoft には、どのような責任がありますか?**

個人データ違反の認識後、GDPR に基づいて当社は過度の遅延なく通知する義務があります。 Microsoft が処理者である場合、その義務には、GDPR の要件と共に Microsoft の標準である世界的な契約規定の両方が反映されます。 当社では、確認されたすべての個人データ違反を対象とみなします。危害リスクのしきい値はありません。 お客様に対しては、データ違反の危害を Microsoft が直接受けたか、副処理者が受けたかを通知します。 Microsoft では、お客様の組織で指定されたセキュリティ インシデント担当者を速やかに特定して連絡を取るための態勢を整えています。 さらに、すべての副処理者には、それぞれの違反を Microsoft に報告し、その影響を保証することが契約で義務付けられています。

**MIcrosoft はデータ違反をどのように検出しますか?**

当社のすべてのサービスと担当者は、社内インシデント管理手順に従い、何よりもまずデータ違反を回避するための予防手段を講じます。 さらに、オンライン サービスには、複数のプラットフォームに渡る固有のセキュリティ管制が実施されていて、たとえデータ違反があったとしても検出できるようになっています。

**Microsoft はデータ違反にどのように対応しますか?**

個人データ違反の発生時にお客様をサポートするために、Microsoft は次のように対応しています。
    - 特定の手順を実行するように訓練を受けたセキュリティ担当者。
    - Microsoft が確実に詳細な記録を維持するためのポリシー、手順、管理。 この対応には、インシデントの事実、その影響、および対策について記録したドキュメンテーション、またインシデント管理システムでの情報の追跡と保存が含まれます。

**データ違反発生時に、Microsoft からどのように通知されるのですか?**

Microsoft は、お客様に速やかに通知するためのポリシーと手順を規定しています。 お客様の DPA への通知要件に応じるため、当社は、個人データ違反が発生したかどうかを判別するために使用したプロセスの説明、違反の性質に関する説明、違反軽減のために行った措置についての説明を提供します。

## <a name="accountability-readiness-checklists-for-the-gdpr"></a>GDPR に関するアカウンタビリティ対応準備チェックリスト

これらの[チェックリスト](gdpr-arc.md)は、Microsoft 製品の使用において、GDPR をサポートしなければならない可能性のある情報にアクセスする便利な方法を提供します。 [Microsoft コンプライアンス スコア](compliance-score.md)で、GDPR タイル内の顧客管理コントロールの下にあるコントロール ID とコントロール タイトルを参照することによって、チェックリスト項目を管理できます。

## <a name="gdpr-faqs"></a>GDPR についてよく寄せられる質問

**GDPR に関して、Microsoft はお客様に確約することはありますか?**

はい。 GDPR では、管理者 (Microsoft のエンタープライズ オンライン サービスを利用している組織など) に対し、GDPR の主要な要件を満たす上で十分な保証を提供する処理者 (Microsoft など) のみを採用することを義務付けています。 Microsoft は、ボリューム ライセンスをご利用のすべてのお客様に、こうした義務を契約の一環として提供するために、積極的な取り組みを実施しています。

**準拠のために、どのような支援が Microsoft から得られますか?**

Microsoft は、GDPR のアカウンタビリティをサポートするためのツールとドキュメントを提供しています。 これには、データ主体の権利に関するサポートや、お客様のデータ保護影響評価の実施が含まれています。また、個人データ違反が発生した場合は協力して解決に当たります。

**GDPR 条項には、どのような義務が記されていますか?**

Microsoft の GDPR 条項は、第 28 条で処理者に求められる義務を反映しています。 第 28 条では、次の項目を処理者に義務付けています。

- 副処理者を従事させる場合は、必ず管理者の承諾を得ること。また、その副処理者に対する責任を負うこと。
- 個人データの処理は、移転に関する処理を含め、管理者からの指示によってのみ実施すること。
- 個人データの処理担当者に守秘義務を遵守させること。
- 個人データのリスクに応じたセキュリティ レベルを保証するために、適切な技術的対策と組織的対策を実施すること。
- GDPR の権利を行使するためのデータ主体の要求に対応するという管理者の義務を支援すること。
- 違反の通知とその支援に関する要件を満たすこと。
- データ保護影響評価を実施する際、および監査機関と相談する際に管理者を支援すること。
- サービス提供の終了時に個人データを削除または返却すること。
- GDPR への準拠の証拠に関して管理者を支援すること。

**Microsoft は、何を基準にして EU 域外への個人データの転送を支援しますか?**

Microsoft では長年にわたり、企業向けオンライン サービスのデータ移転の基準として、標準契約条項 (モデル条項とも呼ばれる) に従っています。 標準契約条項は、欧州委員会によって規定されている標準的な条件であり、規定に準拠した方法でデータを欧州経済地域外に移転するために使用できます。 Microsoft は、[オンライン サービス使用条件](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)を通じて、この標準契約条項をすべてのボリューム ライセンス契約に採用しています。 Microsoft による標準契約条項の実装は、第 29 条作業部会により、規定への準拠が確認されています。 Microsoft は、EU-US プライバシー シールドの発効時に最初に認定を取得した企業です。 [プライバシー シールドに対する Microsoft の認定](https://www.privacyshield.gov/participant?id=a2zt0000000KzNaAAK&status=Active)を参照してください。また、[オンライン サービスの使用条件](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)についても確認してください。 EU-US プライバシー シールドは、データ保護上の義務に沿った方法で、米国にデータを移転する必要があるお客様に役立つものです。

**その他の Microsoft のコンプライアンス サービスには、どのようなものがありますか?**

世界中のほとんどすべての国で事業を営むグローバル企業として、Microsoft はお客様を支援するための堅牢なコンプライアンス ポートフォリオを用意しています。 コンプライアンス サービス (FedRamp、HIPAA/HITECH、ISO 27001、ISO 27002、ISO 27018、NIST 800-171、UK G-Cloud など多数) の完全なリストは、[コンプライアンス サービスのトピック](offering-home.md)を参照してください。

**GDPR は、どのように私の会社に影響するのですか?**

GDPR は、個人データを収集または処理する組織に対して、幅広い要件を課しています。これには、次の 6 つの主要な原則に準拠する要件が含まれています。

- 個人データの処理と使用における、*透明性*、*公平性*、*合法性*。 個人データの使用方法を個人に対して明確にする必要があります。また、そのデータを処理する "法的根拠" も必要です。
- 個人データの処理を*指定*された*明示的*で*正当な目的*に制限すること。 本来の収集目的と "合致" しない目的のために個人データを再利用または開示することはできません。
- 目的に適った範囲で、*個人データの収集と保管を最小限に抑えること*。
- *個人データの正確性*を確保し、*削除または訂正*を可能にすること。 保持する個人データは正確性を確保して、誤りが発生した場合には訂正できるようにする手順を踏む必要があります。
- *個人データの保管を制限すること*。 データ収集の目的を達成するために必要な期間のみ、個人データが保持されるようにする必要があります。
- 個人データの*セキュリティ*、*整合性*、*機密性*を確保すること。 組織は、個人データの安全性を維持するため、技術的および組織的なセキュリティ対策の手順を踏む必要があります。

お客様は、GDPR に対応するための組織固有の義務と、その義務を果たす方法を理解する必要があります。Microsoft は、GDPR に準拠するための対応を支援します。

**GDPR において企業が認めなければならない権利は何ですか?**

GDPR では、EU 域内の居住者に、一連の「データ主体の権利」を通じて自分の個人データを管理する権利が付与されています。 この権利には、次のものが含まれます。

- 個人データの使用方法に関する情報にアクセスする。
- 組織が保有している個人データにアクセスする。
- 誤った個人データを削除または訂正させる。
- 特定の状況で個人データを修正および削除させる (「忘れられる権利」とも呼ばれます)。
- 個人データの自動処理に対して制限または異議を申し立てる。
- 個人データのコピーを受け取る。

**処理者および管理者とは何ですか?**

管理者とは、単独でまたは他者と共同で個人データを処理する目的と手段を決定する、自然人、法人、公共機関、行政機関またはその他の団体を意味します。 処理者とは、管理者の代わりに個人データを処理する、自然人、法人、公共機関、行政機関、またはその他の団体を意味します。

**GDPR は処理者と管理者に適用されますか?**

はい。GDPR は、管理者と処理者の両方に適用されます。 管理者は、GDPR の要件を満たすための措置を講じる処理者のみを採用する必要があります。 GDPR では、管理者の指示に従わない行動または管理者の指示以外の行動に対して、処理者はデータ保護指令にない追加の責務を負います。 処理者の責務には、次のものが含まれますが、この限りではありません。

- 管理者による指示に従ってのみデータを処理する。
- 個人データを保護するための適切な技術的および組織的な措置を講じる。
- データ主体の要求に関して管理者を支援する。
- 処理を委託する副処理者が、これらの要件を確実に満たすようにする。

**企業は、違反に対してどのくらいの罰金を科せられますか?**

企業は、特定の GDPR 要件を満たすことができなかった場合、2,000 万 &euro; または年間売上高の 4% のいずれか大きい方の金額を上限とする制裁金を科せられる可能性があります。 個別の救済策が追加されると、GDPR の要件を満たせなかった場合のリスクが高くなることがあります。

**私の事業にはデータ保護責任者 (DPO) の任命が必要になりますか?**

これは、この規制の範囲内で特定されている複数の要因によって決まります。 GDPR の第 37 条では、次のいずれかに該当する場合、管理者と処理者がデータ保護責任者を指名するように義務付けています。(a) 裁判所がその司法上の権限を行使する場合を除いて、処理が公的機関または公的組織によって行われる場合、(b) 管理者または処理者の中心的な行為が、その処理の性質、範囲または目的のために、データ主体の定期的かつ系統的な監視を大規模に必要とする処理業務で構成される場合、または (c) 管理者または処理者の中心的な行為が、第 9 条に基づく特別な種類のデータと、第 10 条で言及された有罪判決および犯罪に関連する個人データの大規模な処理で構成される場合。

**GDPR に準拠するために、どれくらいのコストがかかりますか?**

ほとんどの組織では、GDPR に準拠するために時間と費用が必要になります。ただし、適切に設計されたクラウド サービス モデルを運用していて、効果的なデータ ガバナンス プログラムを実施している組織の方が円滑に移行できます。

**自分の組織が処理するデータが GDPR の対象になるかどうかは、どのようにして確認しますか?**

GDPR は、「個人データ」の収集、保管、使用、共有を規制しています。 GDPR における個人データは、特定された自然人または特定可能な自然人に関連するすべてのデータとして広範囲に定義されています。

個人データには、オンライン識別子 (IP アドレスなど)、従業員情報、販売データベース、カスタマー サービス データ、カスタマー フィードバック フォーム、位置データ、生体認証データ、CCTV ビデオ映像、ロイヤルティ スキームの記録、医療情報および財務情報などが含まれますが、この限りではありません。 個人データとは見えない情報も含まれる場合があります。たとえば、人物を含まない風景写真であっても、識別可能な個人の口座番号や一意のコードに結び付く情報は個人データになります。 また、仮名化された個人データであっても、その仮名が特定の個人に結び付く場合は個人データになります。 

「特殊な」カテゴリの個人データ (人種的または民族的出自を明らかにする個人データや、健康状態や性的指向に関する個人データなど) の処理は、「通常」の個人データの処理よりも厳格な規制の対象になります。 このような個人データに関する評価は現実に依存する部分が大きいため、具体的な状況の評価については、専門家に相談することをお勧めします。

**私の組織は別の組織の代わりにデータを処理しているだけですが、それでも GDPR に準拠する必要がありますか?**

はい。 規則は多少異なりますが、GDPR はそれぞれの目的のためにデータを収集および処理する組織 (「管理者」) だけでなく、別の組織の代わりにデータを処理する組織 (「処理者」) にも適用されます。 この要件は、これまでの管理者に適用されるデータ保護指令からの変更です。

**具体的に何が個人情報とみなされますか?**

個人データとは、識別された人物、または識別可能な人物に関するあらゆる情報のことです。 個人の私的、公的、または職務上の役割による区別はありません。 次の情報は個人データに含まれます。

- 名前
- 自宅の住所
- 勤務先の住所
- 電話番号
- 携帯電話番号
- メール アドレス
- パスポート番号
- 国が発行する身分証明書
- 社会保障番号 (またはこれに相当するもの)
- 運転免許証
- 身体的、生理学的、または遺伝学的な情報
- 医療情報
- 文化的アイデンティティ
- 銀行に関する詳細情報/口座番号
- 納税者番号
- 勤務先の住所
- クレジット カード/デビット カードの番号
- ソーシャル メディアの投稿
- IP アドレス (EU 地域)
- 位置/GPS データ
- Cookie

**EU 域外にデータを転送することは可能ですか?**

はい。ただし、GDPR は、欧州居住者の個人データを欧州経済域外の場所に転送することを厳重に規制しています。 こうした転送を可能にするには、契約などの特定の法的メカニズムを構築するか、認証メカニズムに従う必要があります。 Microsoft は、オンライン サービス使用条件内で、使用するメカニズムを詳細に規定しています。

**法令遵守のためのデータ保持要件があります。こうした要件は削除の権利よりも優先されますか?**

継続的な処理とデータ保持の正当な理由がある場合、たとえば、「管理者が従うべき EU または加盟国の法律に基づく法的義務を遵守するためにデータの処理が必要である」(第 17 条 3 項 (b)) 場合、GDPR は、組織によるデータ保持の必要性を認めています。 ただし、データ主体の権利と自由、データ収集時点でのデータ主体の期待などよりも保持の根拠が重視されることを確認するために、法律顧問に相談する必要があります。

**GDPR では暗号化について取り上げられていますか?**

GDPR では、個人データの違反があったときに、そのデータを判読不能にする保護手段として暗号化を認定しています。 そのため、暗号化が使用されているかどうかは、個人データ違反の通知要件に影響する可能性があります。 GDPR では、暗号化を、一部のリスクに対処する適切な技術的または組織的手段としても指摘しています。 暗号化は、クレジット カード業界 (PCI) データ セキュリティ スタンダード (DSS) による要件でもあり、金融サービス業界に固有の厳格なコンプライアンス ガイドラインの一部でもあります。 Azure、Dynamics 365、Enterprise Mobility + Security、Office Microsoft 365、SQL Server/Azure SQL データベース、Windows 10 などの Microsoft の製品とサービスでは、転送中のデータと保存中のデータに対する堅牢な暗号化を実現します。

**GDPR によって、個人データ違反に対する組織の対応はどのように変わりますか?**

GDPR によりデータ保護の要件が変わり、処理者と管理者には、個人データ違反の通知に関してより厳格な義務が課せられます。 この新しい規制において、個人データ違反に気付いた処理者は、過度の遅滞なく、データ管理者に通知する必要があります。 管理者は、個人データ違反に気付いた場合、72 時間以内に所定のデータ保護機関に通知する必要があります。 データ違反が個人の権利と自由に高いリスクをもたらす可能性がある場合、管理者は影響を受ける個人に対して、過度の遅滞なく、その旨を通知する必要があります。 この項目に関する追加のガイダンスは、EU の第 29 条作業部会で策定中です。

Microsoft 製品およびサービス (Azure、Dynamics 365、Enterprise Mobility + Security、Microsoft Office 365、Windows 10 など) には、セキュリティの脅威と侵害を検出して評価し、GDPR のデータ違反通知に関する義務を果たすために、今すぐ利用できるソリューションが揃っています。

## <a name="additional-resources"></a>その他のリソース

- [Microsoft ベースのソリューションを提供しているグローバル パートナーと共に GDPR に関するニーズに対応します](https://aka.ms/findgdprpartner)
- [Microsoft がお客様のデータをどのように管理し、そのデータをどこに配置して、誰にアクセスを許可するか、および条件について説明します。](https://www.microsoft.com/trust-center/privacy)
- [Microsoft が EU-U.S. プライバシー シールド フレームワークの原則にどのように準拠しているかについて説明します](https://blogs.microsoft.com/eupolicy/2016/07/11/eu-u-s-privacy-shield-progress-for-privacy-rights/)
- [Microsoft が GDPR の下でどのように個人データの違反を検出し、対応し、お客様に通知するかを説明します](https://www.microsoft.com/trust-center/privacy/gdpr-data-breach)
- [現在の GDPR 準備状況を評価する](https://discover.microsoft.com/gdpr-readiness-assessment/)
