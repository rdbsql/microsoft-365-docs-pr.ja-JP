---
title: コンプライアンススコアとコンプライアンスマネージャーを使用して改善アクションを管理する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: コンプライアンススコアとコンプライアンスマネージャーを使用して、個人データの保護レベルを向上させる方法について説明します。
ms.openlocfilehash: d3730f7a91876befc05f749497540fbe9abe9641
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126553"
---
# <a name="use-compliance-score-and-compliance-manager-to-manage-improvement-actions"></a>コンプライアンススコアとコンプライアンスマネージャーを使用して改善アクションを管理する

Microsoft コンプライアンスのスコアとコンプライアンスマネージャーを一緒に使用して、欧州連合の[一般的なデータ保護規則 (GDPR)](../compliance/gdpr.md)、[カリフォルニア消費者保護法 ccpa](../compliance/ccpa-faq.md)、HIPAA (米国医療保険法)、ブラジルのデータ保護法 (LGPD) などのデータプライバシー規制に関連する改善を管理することができます。 

この記事では、データのプライバシー保護のためにこれらのツールを使用するためのガイダンスを示します。

![改善アクションを管理するためのコンプライアンススコアとコンプライアンスマネージャー](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-grid.png)

>[!Note]
>コンプライアンスマネージャーで提供されるお客様のアクションは推奨事項です。 実装する前に、これらの推奨事項の有効性を規制環境で評価する必要があります。 コンプライアンスマネージャーの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。
>

## <a name="planned-updates-for-compliance-score-and-compliance-manager"></a>コンプライアンススコアとコンプライアンスマネージャーの計画された更新プログラム

[コンプライアンススコア](../compliance/compliance-score.md)(現時点ではプレビュー中) には、[コンプライアンスマネージャー](../compliance/compliance-manager-overview.md)から規制 (GDPR など) のターゲット評価を追加する必要があります。 今後のリリースでは、コンプライアンスマネージャーの機能の多くが統合コンプライアンススコアに統合され、複数のツールの必要性が減少します。

ご利用のサブスクリプションのツールを次に示します。このツールは、サインインする必要があります。

- [Microsoft コンプライアンス管理センターのコンプライアンススコア](https://compliance.microsoft.com/compliancescore)
- [Microsoft サービス信頼ポータルのコンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager/V3)

## <a name="getting-started-with-compliance-manager"></a>コンプライアンスマネージャーの概要 

[コンプライアンスマネージャー](../compliance/working-with-compliance-manager.md) (現在はプレビュー段階) は、microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを管理するための、Microsoft Service Trust Portal の無料ワークフローベースのリスク評価ツールです。 Microsoft 365 または Azure Active Directory (Azure AD) サブスクリプションの一部として、コンプライアンスマネージャーは、Microsoft クラウドサービスの共有責任モデル内の法令遵守を管理するのに役に立ちます。

コンプライアンスセンターの [**コンプライアンススコア**] ページで、全体的なコンプライアンススコアを表示したり、その他のさまざまな機能を実行したりすることができますが、最初にサービスの信頼ポータルを使用してコンプライアンスマネージャーを使用して、データのプライバシー規制の評価を構成する必要があります。 これらの評価からのデータは、さらに表示とフィルター処理を行うためにコンプライアンススコアに表示されます。 

コンプライアンスマネージャーインターフェイスを使用すると、1つまたは複数のデータプライバシー関連の規制テンプレートを選択し、それらをグループ化して、そのセットに対して必要な改善アクションを評価および追跡することができます。 また、対象のサービスに固有の各規制呼び出しの情報を、Microsoft とカスタマー管理のコントロールで分けて表示することもできます。

ここで選択した評価と改善の状態は、Microsoft コンプライアンスセンターのコンプライアンススコアにも表示されます。これは、コンプライアンスマネージャーでの初期設定の重要性を強調します。 この図は、これらの関係を示しています。
 
![Microsoft コンプライアンスセンターにおけるコンプライアンススコアの関係](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-ui.png)

開始する際に役立つ重要な手順を以下に示します。

### <a name="1-assessment-templates"></a>1. 評価テンプレート

コンプライアンスマネージャーからは、最初の手順として、重要なデータプライバシー規制に固有の評価を追加し、定義された「データプライバシー規制」グループに含めることをお勧めします。

[グループ](../compliance/working-with-compliance-manager.md#groups)は、評価を組織化し、同じまたは関連する顧客管理のコントロールを持つ評価間で共通情報とワークフロータスクを共有できるようにするコンテナーです。 同じグループ内の2つの異なる評価がカスタマー管理コントロールを共有する場合、コントロールの実装の詳細、テスト、および状態の完了は、グループ内の他の評価の同じコントロールに自動的に同期されます。 これにより、グループ全体の各コントロールに割り当てられたアクションアイテムが統一され、作業の重複が減少します。 

グループを使用して整理することもできます。 コンプライアンス作業を整理するのに役立つ、年、地域、コンプライアンス標準、またはその他のグループによる評価。


### <a name="2-action-items"></a>2. アクションアイテム

評価が追加されると、各グループまたは個々の規則に固有のアクションアイテムを表示できるようになります。

- **改善アクションリスト。** [アクションアイテム] リストに移動して、グループに含まれるすべての規制に関連付けられている改善アクションを表示します。 多くのアクションは、1つのリストアイテムが複数の規制を表すことができるように、さまざまな規則に及びます。 
 
- **改善アクションフィルター。** 多くのデータプライバシーに関する規制や規制のグループでは、改善アクションの一覧が非常に大きくなる可能性があるので、[フィルター] ドロップダウンを使用してリストにフィルターを適用することを検討してください。 たとえば、"テクニカルコントロール" を選択すると、多くのアクションは、コンプライアンスマネージャーにも記載されているビジネスのさまざまな側面における管理操作に関連しているため、組織内で技術実装があるものだけに限定されます。 この記事では、技術的な制御について説明するので、このフィルター方法をお勧めします。
 
- **詳細については、「」を参照してください。** アクションごとに、リンクをクリックして**詳細**を確認できます。これにより、推奨されるアクティビティの詳細がわかります **。または、次**の操作を実行するためのフォームが開きます。
 
   - 組織内のユーザーにアクションを割り当てて管理する
   - アクションのアドレス指定に関連するドキュメントを管理する
   - アイテムの状態を指定する
   - 実装とテストの日付を指定する
   - 件名アクションの追加情報、実装メモ、およびテスト計画メモを記録する
  
- **適用できないアイテムがスコープ外です。** [アクションアイテム] ボックスの一覧に含まれる改善アクションは、計画した実装には適用されない場合があります。 コンプライアンスマネージャーの範囲外であることを指定し、その操作とその証拠を、コンプライアンススコアの値の計算から削除することができます。 

たとえば、組織で Microsoft のマネージキーを使用することを選択した場合、顧客キーを使用することをお勧めしますが、展開には適用されません。 この場合、組織では、該当する規制テンプレートの**制御アクション**の**範囲内ではない**とマークされます。
 
### <a name="3-controls-info"></a>3. コントロール情報

評価固有のビューの場合は、各評価グループの [[コントロール] 情報](../compliance/compliance-manager-overview.md#controls)を表示します。 これにより、評価固有のビューが提供されます。これは、技術統制固有のビューを提供する [アクションアイテム] リストとは異なります。
 
![項目を制御するための評価の関係](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-control.png)

[ **Controls Info** ] リストに移動して、対象とする規制のスコープ内サービスの一覧を表示します。 
 
規制固有の制御のグループ化各サービス領域のコントロール領域で提供されるアクションを一覧表示します。 一連のアクションについては、コンプライアンスマネージャーによって処理に関する詳細情報が提供されます。また、制御方法を選択する際に組織を支援するためのレビューオプションを提案または提供することもあります。
 
このインターフェイスには、技術的なアクションに固有の詳細、およびそのコントロールに関連するアクションの状態と、アクションに関連する規制に関する補足コンテキストを表示する機能が用意されています。

### <a name="4-template-download"></a>4. テンプレートのダウンロード

スプレッドシートベースの規制分析に精通している場合は、テンプレートリストを使用して、それぞれの評価のテンプレートをダウンロードする方法があります。 ダウンロードされたテンプレートには、規制に加えて、各テンプレートの技術管理情報が一覧表示されるため、特定の役割を使用して移動/フィルター処理を行ったり、ビジネス固有のビューを生成したりする方が簡単な場合があります。
 
[**テンプレートの追加**] を使用して、既存のテンプレートに基づいて組織用にカスタマイズした新しいテンプレートを追加することもできます。 そのためには、選択したテンプレート (HIPAA/ヒット回数など)) をダウンロードし、目的に合わせて変更してから、コンプライアンスマネージャーツールにアップロードし直す必要があります。これで、コンプライアンスマネージャーとコンプライアンススコアツールの全体の一部として、他のテンプレートや評価に似た評価と評価を実行できるようになります。
 
>[!Tip]
>多数の規制または重複した改善アクションを処理する場合は、それぞれのテンプレートをダウンロードして、データセットを結合したり、組織に適用されない改善アクションやコントロールの種類を削除したり、再アップロードしたりすることを検討してください。 これは、[すべてのコントロール情報] セクションに移動し、それぞれをスコープ外としてマークするよりも簡単な場合があります。
>

## <a name="compliance-score"></a>コンプライアンス スコア

コンプライアンスマネージャーで評価およびレビューの仕様が実行されると、[コンプライアンススコア](../compliance/compliance-score.md)ツールに移動し、スコアとスライスを確認して、コントロールエリアによるデータのダイスを追加できるようになります。

Microsoft 365 コンプライアンス管理センターのコンプライアンススコアツールは、コンプライアンスマネージャーおよびさまざまな Microsoft 365 サービスから取得したコンプライアンスデータを確認およびフィルター処理するためのいくつかのアプローチを提供します。 このツールは、さまざまな構成設定が実装されている場合に自動的に更新され、多くの改善アクションが両方のスコアで表示されるように、通知を Microsoft のセキュリティで保護されたスコアと共有します。 
 
コンプライアンススコアは次の機能を提供します。

- Microsoft とお客様が管理する統制によって分類された、収集されたスコア
- 改善アクションと完了状態のロールアップ
- スコアに影響を与える Microsoft 365 ソリューションの一覧

### <a name="how-the-compliance-score-gets-calculated"></a>コンプライアンススコアを計算する方法

つまり、microsoft の[コンプライアンススコア計算の記事](../compliance/compliance-score-methodology.md)で詳しく説明されているように、microsoft とお客様が管理する統制の組み合わせに基づいてスコアが計算されます。

コントロールには、必須か任意かを基準にしたスコア値、および予防的、検出、または是正のいずれであるかに基づいて、スコア値が割り当てられます。 これらは、他のコントロールに関連して実装されていないリスクをまとめたものです。

「Microsoft コンプライアンススコアの計算」の記事に記載されているように、予防的制御は検出と修正されたものよりも高いスコアを取得し、固定のコントロールは任意のスコアより高いスコアを取得します。
 
コンプライアンススコア管理 UI では、これらのパラメーターは表示されません。また、これらのパラメーターを使用してフィルター処理することもできないことに注意してください。 ただし、関連付けられているテンプレートをコンプライアンスマネージャーツールからダウンロードした場合は、その結果として得られるデータセットには、ほとんどの規制に関するこれらのパラメーターが表示されます。

テクニカルコントロールの場合、関連付けられている機能がアクティブ化されると、コンプライアンススコアは向上アクションのスコアを自動的に更新します。 その他の技術以外の操作、 &mdash; またはドキュメントに関連付けられている操作は、 &mdash; サービス信頼ポータルのコンプライアンスマネージャーツールで手動で記録する必要があります。 

また、データプライバシー規制へのコンプライアンス以外の理由で保持ラベルを使用するなど、他の目的のために特定の改善アクションを実装することもあります。このような機能は、 &mdash; &mdash; 他の目的で使用されている場合でも、意図的な法令遵守アクションの一部ではありません。

コンプライアンススコアは、幅広い規模で改善を追跡するための相対的な指標として考慮する必要があります。 完全なスコアを追求する必要はありません。 

### <a name="additional-guidance"></a>追加のガイダンス

コンプライアンススコアとコンプライアンスマネージャーを使用してデータプライバシー規制へのコンプライアンスを実現するための、いくつかの重要なヒントを紹介します。

- 各データプライバシー規制には、技術統制、ドキュメント仕様、運用、プロセス、およびレポートの要件の組み合わせがあります。 これらのすべてが向上アクションに表示されます。 

- この記事では、コンプライアンスマネージャーおよびコンプライアンススコアでデータのプライバシーを保護するために指定されている技術コントロールのサブセットに焦点を当てます。 非技術的な管理コントロールの詳細については、コンプライアンスマネージャーツールと[ドキュメント](../compliance/compliance-score.md)を参照してください。

- 改善アクションの表示を関心のある領域に絞り込むには、コンプライアンススコア管理の [**ソリューション**] タブで、アクションの種類によってフィルター処理できます。

- コンプライアンススコアで特定された改善アクションの相対的な重要性と優先度は、組織が管理する必要があると判断した、より広範なリスクレビューの一環として考慮する必要があります。 

- グローバルな組織の場合、複数のデータプライバシーに関する規制テンプレートを評価としてコンプライアンスマネージャーに追加すると、各改善アクションのフィールドリストに適用されている各機能が統合されます。
 
- 複数の規制要件に対する改善アクションの集約がある場合でも、GDPR、LGPD、CCPA、および HIPAA ヒットの規則の評価テンプレートが選択されている場合、400の向上アクションのほとんどがコンプライアンススコアに表示されます。 この長いリストをより適切に処理するには、向上アクションフィルターを使用して、結果セットをより扱いやすいリストに絞り込みます。

- [カテゴリ] フィルターは、この総合的なソリューション内の記事を追跡、禁止、保護、保持、および調査する論理グループによって改善アクションをフィルター処理する手段を提供します。 

- 向上アクションに記載されているコントロールの中には、特定の規制に関する記事に直接関連しているものがありますが、他のコントロールは規制の精神により間接的に関連付けられている可能性があります。

