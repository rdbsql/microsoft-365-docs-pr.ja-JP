---
title: GDPR に関する Azure アカウンタビリティ対応準備チェックリスト
description: Microsoft Azure を使用する際に、GDPR をサポートしなければならない可能性のある情報にアクセスする便利な方法を提供します。
keywords: ARC Azure、Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
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
hideEdit: true
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: df6e1e48feff77feb86e2e7c0791a655403cee6b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817686"
---
# <a name="azure-accountability-readiness-checklist-for-the-gdpr"></a>GDPR に関する Azure アカウンタビリティ対応準備チェックリスト

## <a name="1-introduction"></a>1. はじめに

このアカウンタビリティ対応準備チェックリストは、Microsoft Azure を使用する際に EU 一般データ保護規則 (GDPR) をサポートしなければならない可能性のある情報にアクセスする便利な方法を提供します。チェックリストは、以下に基づいた個人データ プロセスに関する一連のプライバシーとセキュリティ コントロールのタイトルと参照番号 (各チェックリスト トピックに対してかっこで示す) を使用して編成されています。

- [ISO/IEC CD 27701](https://shop.bsigroup.com/ProductDetail/?pid=000000000030351736) セキュリティ技術の要件。
- プライバシー管理要件に関連する [ISO/IEC 27001](https://shop.bsigroup.com/ProductDetail?pid=000000000030347472)。

コンプライアンス スコア [16] で、GDPR タイル内の顧客管理のコントロールの下にあるコントロール ID とコントロール タイトルを参照することによって、このチェックリストの項目を管理できます。 GDPR をサポートするために Microsoft Azure が実装する内部コントロールのプレゼンテーションを編成するためにもこのコントロール構造は使用されます ([Service Trust Center](https://servicetrust.microsoft.com/ViewPage/TrustDocuments) でダウンロードすることができます)。

[GDPR をサポートするために Microsoft Dynamics 365 が実装する内部コントロール](https://aka.ms/GDPRControls)のプレゼンテーションを編成するためにもこのコントロール構造は使用されます。

GDPR 関連のドキュメントの詳細については、「[https://aka.ms/gdprgetstarted](https://aka.ms/gdprgetstarted)」を参照してください。

## <a name="2-conditions-for-collection-and-processing"></a>2. 収集と処理の条件

|||||
|:----|:----|:-----|:-----|
|**分類**|**お客様の考慮事項**|**参照できる Microsoft ドキュメント**|**GDPR 条項への取り組み**|
| ***法的基準の識別 (7.2.2)*** | お客様は、最初に同意を得る必要があるかどうかなど、処理の法的基準に関連するすべての要件を理解する必要があります。 | Windows Azure では、ユーザーの同意を得るための直接的なサポートは提供していません。アカウンタビリティ ドキュメントに記載される Microsoft サービスによる個人データの取り扱いに関する説明は、ここで入手できます。<br>* *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)] | (5)(1)(a)、(6)(1)(a)、(6)(1)(b)、(6)(1)(c)、(6)(1)(d)、(6)(1)(e)、(6)(1)(f)、(6)(3)、(6)4)(a)、(6)(4)(b)、(6)(4)(c)、(6)(4)(d)、 (6)(4)(e)、(8)(3)、(9)(1)、(9)(2)(b)、(9)(2)(c)、(9)(2)(d)、(9)(2)(e)、(9)(2)(f)、(9)(2)(g)、(9)(2)(h)、(9)(2)(i)、(9)(2)(j)、(9)(3)、(9)(4)、(10)、(17)(3)(a)、(17)(3)(b)、(17)(3)(c)、(17)(3)(d)、(17)(3)(e)、(18)(2)、(22)(2)(a)、(22)(2)(b)、(22)(2)(c)、(22)(4) |
| ***いつ同意を取るべきかの判断 (7.2.3)*** | お客様は、個人データを処理する前に、各ユーザーから同意を得るための法的要件または規制要件 (同意が必要な場合、その種の処理が要件から除外される場合など) を理解しておく必要があります。これには、同意の収集方法も含まれます。 | Windows Azure では、ユーザーの同意を得るための直接的なサポートは提供していません。 | (8)(1)、(8)(2) |
| ***同意の取得と記録 (7.2.4)*** | 同意が必要であると判明した場合、お客様は適切な仕方で同意を得る必要があります。また、お客様は、同意を求める提示方法および収集方法に関する要件を理解しておく必要があります。 | Windows Azure では、ユーザーの同意を得るための直接的なサポートは提供していません。 | (7)(1)、(7)(2)、(9)(2)(a) |
| ***プライバシー影響評価 (7.2.5)*** | お客様はプライバシー影響評価を実施するための要件 (どのような場合に実施すべきか、実施する必要があるデータのカテゴリ、評価を実施するタイミング) を理解しておく必要があります。 | Microsoft サービスが DPIA を実施するタイミングを判断する方法、および DPO の関与を含む Microsoft で実施される DPIA プログラムの概要については、Service Trust Portal の「[データ保護影響評価 (DPIA)](https://servicetrust.microsoft.com/ViewPage/GDPRDPIA)」ページを参照してください。DPIA のサポートに関しては、次の部分をご覧ください。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)] | 条項 (35) |
| ***PII プロセッサに関する契約 (7.2.6)*** | お客様は、プロセッサに関する契約に、個人データの取り扱いと保護に関連する法律や規制義務に準拠するための要件を含める必要があります。 | GDPR に基づいてお客様が義務を遂行するうえで弊社が支援することを規定する Microsoft の契約 (データ主体の権利のサポートを含む)。<br> *Microsoft Online Services の使用条件およびデータ保護条件。「個人データの取り扱い」の「GDPR」を参照* [[1](gdpr-arc-Azure.md#1)] | (5)(2)、(28)(3)(e)、(28)(9) |
| ***PII の処理に関連する記録 (7.2.7)*** | お客様は、個人データの処理に関するすべての必要および必須の記録を保持する必要があります (たとえば、目的、セキュリティ対策など)。 これらの記録の一部がサブプロセッサによって提供される必要がある場合は、お客様はそのような記録を取得できるようにする必要があります。 | Microsoft サービスが提供するツールは、お客様が GDPR に基づいてコンプライアンスを実証し、アカウンタビリティを果たすために必要な記録を維持するのに役立ちます。[アクティビティと診断ログ](https://docs.microsoft.com/azure/security/blueprints/fedramp-iaaswa-overview#logging-and-auditing)および[個人データの取り扱い](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools)に関するログについては、*Azure セキュリティのドキュメント* [[2](gdpr-arc-Azure.md#2)] を参照。 | (5)(2)、(24)(1)、(30)(1)(a)、(30)(1)(b)、(30)(1)(c)、(30)(1)(d)、(30)(1)(g)、(30)(1)(f)、(30)(3)、(30)(4)、(30)(5) |

## <a name="3-rights-of-data-subjects"></a>3. データ主体の権利

|||||
|:-----|:-----|:-----|:-----|
|**分類**|**お客様の考慮事項**|**参照できる Microsoft ドキュメント**|**GDPR 条項への取り組み**|
|***PII プリンシパルの権利を認め行使できるようにする (7.3.1)***|お客様は、個人データの処理に関連する個人の権利に関する要件を理解する必要があります。 これらの権利には、アクセス、訂正、消去などが含まれます。 お客様がサードパーティ製システムを使用している場合は、システムのどの部分 (存在する場合) が個人の権利を行使できるツール (たとえば、データへのアクセスなど) を提供するかを判断する必要があります。 システムがそのような機能を提供する場合、お客様は必要に応じてそれらを利用する必要があります。|Microsoft が提供する機能は、データ主体の権利をサポートするのに役立ちます。「*GDPR のための Azure データ主体要求*」[[9](gdpr-arc-Azure.md#9)] を参照してください。Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント。「ISO/IEC 27018 コントロール A.1.1」を参照してください。|(12)(2)|
|***PII プリンシパル (データ主体) に関する情報の判別 (7.3.2)***|お客様は、個別のユーザーに提供できるようにしておくべき、取り扱う個人データに関する情報の種類に関する要件を理解する必要があります。これには、次の内容が含まれます。<br>- 管理者または担当者に関する契約の詳細。<br>- 処理に関する情報 (目的、国外への転送と関連する保護措置、保存期間など)<br>- プリンシパルが個人データにアクセスしたり、修正したりする方法、消去または取り扱いの制限の要求、個人データのコピーの受け取り、および個人データの移植性に関する情報<br>- 個人データを取得した方法と出所 (プリンシパルから直接取得したわけではない場合)<br>- 苦情を申し立てる権利や、どこに申し立てればよいかに関する情報<br>- 個人データの修正に関する情報<br>- データ処理においてデータ主体の ID 情報を必要としなくなった場合、その組織がデータ主体 (PII プリンシパル) を特定する立場にはいなくなったことを知らせる通知<br>- 個人データの転送や開示<br>- 個人データの自動処理だけに基づいた自動的意思決定の有無<br>- 情報が更新されデータ主体に提供される頻度に関する情報 (たとえば、「ジャストインタイム」の通知、組織が定義した頻度、など)。<p>お客様がサードパーティ製システムまたはプロセッサを使用している場合、お客様が提供しなければならない可能性のある情報 (存在する場合) をお客様で決定し、必要な情報をサードパーティから取得できるようにしておく必要があります。</p>|データ主体に提供するデータに含めることができる Microsoft サービスに関する情報。「*GDPR のための Azure データ主体要求*」[[9](gdpr-arc-Azure.md#9)]、「*顧客データ保護影響評価に関する Azure からの重要な情報*」[[11](gdpr-arc-Azure.md#11)]、および「*誰がどのような条件でデータにアクセスできるか*」[[7](gdpr-arc-Azure.md#7)] を参照してください。|(11)(2)、(13)(1)(a)、(13)(1)(b)、(13)(1)(c)、(13)(1)(d)、(13)(1)(e)、(13)(1)(f)、(13)(2)(c)、(13)(2)(d)、(13)(2)(e)、(13)(3)、(13)(4)、(14)(1)(a)、(14)(1)(b)、(14)(1)(c)、(14)(1)(d)、(14)(1)(e)、(14)(1)(f)、(14)(2)(b)、(14)(2)(e)、(14)(2)(f)、(14)(3)(a)、(14)(3)(b)、(14)(3)(c)、(14)(4)、(14)(5)(a)、(14)(5)(b)、(14)(5)(c)、(14)(5)(d)、(15)(1)(a)、(15)(1)(b)、(15)(1)(c)、(15)(1)(d)、(15)(1)(e)、(15)(1)(f)、(15)(1)(g)、(15)(1)(h)、(15)(2)、(18)(3)、(21)(4)|
|***PII プリンシパルへの情報の提供 (7.3. 3)***|お客様は、個人データの処理に関連して、必要な情報を個人にどのように、いつ、どのような形式で提供するかについてのあらゆる要件を遵守する必要があります。 サードパーティが必要な情報を提供している場合は、お客様は GDPR によって要求されるパラメーター内にそれがあることを確認する必要があります。|データ主体に提供するデータに含めることができる Microsoft サービスに関するテンプレート情報。「*GDPR のための Azure データ主体要求*」[[9](gdpr-arc-Azure.md#9)] および「*顧客データ保護影響評価に関する Azure からの重要な情報*」[[11](gdpr-arc-Azure.md#11)] を参照してください。|(11)(2)、(12)(1)、(12)(7)、(13)(3)、(21)(4)|
|***同意を修正または撤回するメカニズムの提供 (7.3.4)***|お客様は、個人データにアクセス、修正、および/または消去する権利についてユーザーに通知すること、およびユーザーがそれらを実行できるメカニズムを提供することに関する要件を理解する必要があります。サードパーティ製システムが使用されていて、その機能の一部としてこのメカニズムが提供される場合、お客様は必要に応じてその機能を利用する必要があります。|同意を求める際にデータ主体に提供する情報を定義する目的で使用できる Microsoft サービスの機能に関する情報。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]|(7)(3)、(13)(2)(c)、(14)(2)(d)、(18)(1)(a)、(18)(1)(b)、(18)(1)(c)、(18)(1)(d)|
|***取り扱いに異議を唱えるメカニズムの提供 (7.3.5)***|お客様は、データ主体の権利に関する要件を理解する必要があります。個別のユーザーが取り扱いに異議を唱える権利を有する場合、お客様はそのことをユーザーに知らせ、その異議を登録する手段を個別のユーザーに提供する必要があります。|データ主体に提供するデータに含めることができる、取り扱いへの異議に関連した Microsoft サービスに関する情報。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]「*手順 4: 制限*」を参照|(13)(2)(b)、(14)(2)(c)、(21)(1)、(21)(2)、(21)(3)、(21)(5)、(21)(6)|
|***PII プリンシパルの権利の行使の共有 (7.3.6)***|お客様は、個別のユーザーが権利を行使してデータ修正が行われた事例 (消去または修正を要求しているユーザーなど) について、個人データが共有されているサードパーティへ通知する要件を理解する必要があります。|サードパーティと共有した個人データを見つけ出すことを可能にする Microsoft サービスの機能に関する情報。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]|(19)|
|***修正または消去 (7.3.7)***|お客様は、個人データにアクセス、修正、および/または消去する権利についてユーザーに通知すること、およびユーザーがそれらを実行できるメカニズムを提供することに関する要件を理解する必要があります。サードパーティ製システムが使用されていて、その機能の一部としてこのメカニズムが提供される場合、お客様は必要に応じてその機能を利用する必要があります。|データ主体に提供するデータに含めることができる個人データをアクセス、修正、または消去する機能に関連する Microsoft サービスに関するテンプレート化された情報。<br>-*GDPR のための Azure データ 主体要求* [[9](gdpr-arc-Azure.md#9)]「ステップ 5: 削除」を参照<br>- *Intune でのプライバシーおよび個人データ* [[15](gdpr-arc-Azure.md#15)]「個人データの表示と修正および Intune での個人データの監査、エクスポート、または削除」を参照|(5)(1)(d)、(13)(2)(b)、(14)(2)(c)、(16)、(17)(1)(a)、(17)(1)(b)、(17)(1)(c)、(17)(1)(d)、(17)(1)(e)、(17)(1)(f)、(17)(2)|
|***処理した PII のコピーの提供 (7.3.8)***|お客様は、処理中の個人データのコピーを個別のユーザーに提供することに関する要件を理解する必要があります。 これらには、コピーの形式 (コンピューターが読み取り可能であるなど)、コピーの転送などに関する要件が含まれる場合があります。コピーを提供する機能を備えたサードパーティ製システムを使用している場合、必要に応じてその機能を利用する必要があります。|データ主体に提供するデータに含めることができる個人データのコピーを取得することを可能にする Microsoft サービスの機能に関する情報。<br>*  *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)] 「ステップ 6: エクスポート」を参照<br>*   *Intune でのプライバシーおよび個人データ* [[15](gdpr-arc-Azure.md#15)] 「Intune での個人データの監査、エクスポート、または削除」を参照|(15)(3)、(15)(4)、(20)(1)、(20)(2)、(20)(3)、(20)(4)|
|***要求管理 (7.3.9)***|お客様は、個人データの取り扱いに関連して個別のユーザーからの正当な要求を受け入れ、応答することに関する要件を理解する必要があります。お客様がサードパーティ製システムを使用している場合、お客様は、そのシステムがそのような要求処理を行う機能を備えているかどうかを理解している必要があります。そして、そのような機能を備えている場合、お客様は必要に応じてそのようなメカニズムを利用して要求を処理する必要があります。|データ主体の要求を管理する際にデータ主体に提供する情報を定義する目的で使用できる Microsoft サービスの機能に関する情報。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]|(12)(3)、(12)(4)、(12)(5)、(12)(6)、(15)(1)(a)、(15)(1)(b)、(15)(1)(c)、(15)(1)(d)、(15)(1)(e)、(15)(1)(f)、(15)(1)(g)、(15)(1)(h)|
|***自動化された意思決定 (7.3.10)***|お客様は、個人データの自動処理、およびそのような自動化によって行われる意思決定に関する要件を理解する必要があります。これらの要件には、処理に関する情報を個別のユーザーに提供すること、そのような処理に異議を唱えること、または人の介入を求めることが含まれる場合があります。サードパーティ製システムによってそのような機能が提供されている場合、お客様はそのサードパーティ製システムが必要な情報すべてを提供またはサポートしていることを確認する必要があります。|アカウンタビリティ ドキュメントで使用できる、自動化された意思決定をサポートする Microsoft サービスの機能に関する情報、およびそれらの機能に関してデータ主体に提供するテンプレート情報。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)]|(13)(2)(f)、(14)(2)(g)、(22)(1)、(22)(3)|

## <a name="4-privacy-by-design-and-default"></a>4. 意図的な既定のプライバシー

|||||
|:-----|:-----|:-----|:-----|
|**分類**|**お客様の考慮事項**|**参照できる Microsoft ドキュメント**|**GDPR 条項への取り組み**|
| ***収集の制限 (7.4.1)*** | お客様は、個人データの収集の制限に関する要件を理解する必要があります (収集を特定の目的に合わせて制限される必要がある、など)。 | Microsoft サービスによって収集されたデータの説明。<br>- *Microsoft Online Services の使用条件およびデータ保護条件。「個人データの取り扱い」の「GDPR」を参照* [[1](gdpr-arc-Azure.md#1)]<br>- 顧客データ保護影響評価に関する Azure からの重要な情報 [[11](gdpr-arc-Azure.md#11)]<br>- *Intune でのプライバシーおよび個人データ*[[15](gdpr-arc-Azure.md#15)]「Intune でのデータ収集」を参照 | (5)(1)(b)、(5)(1)(c) |
| ***処理の制限 (7.4.2)*** | お客様には、特定の目的にかなった内容に限定されるように個人データの取り扱いを制限する責任があります。 | Microsoft サービスによって収集されたデータの説明。<br>- Microsoft Online Services の使用条件およびデータ保護条件。「個人データの取り扱い」の「GDPR」を参照 [[1](gdpr-arc-Azure.md#1)]<br>- 顧客データ保護影響評価に関する Azure からの重要な情報 [[11](gdpr-arc-Azure.md#11)]<br>- *Intune でのプライバシーおよび個人データ* [[15](gdpr-arc-Azure.md#15)]。「Intune でのデータの格納と処理」を参照 | (25)(2) |
| ***PII 最小化と非特定化の目標に関する定義と文書化 (7.4.3)*** | お客様は、個人データの非特定化に関する要件を理解する必要があります。これには、使用すべき時期、非特定化する範囲、および使用できない事例が含まれる場合があります。 | Microsoft では、個人データのプライバシー保護を強化するため、該当する場合に、非特定化と仮名化を内部で採用しています。 | (5)(1)(c) |
| ***識別レベルへの準拠 (7.4.4)*** | お客様は、社内で取り決められた非特定化の目標と手段を活用し、準拠する必要があります。 | Microsoft では、個人データのプライバシー保護を強化するため、該当する場合に、非特定化と仮名化を内部で採用しています。 | (5)(1)(c) |
| ***PII 非特定化と削除 (7.4.5)*** | お客様は、過去の個人データの保持、およびそれらを特定の目的にのみ使用することに関する要件を理解する必要があります。システムによってツールが提供されている場合、お客様は必要に応じて、これらのツールを利用して消去または削除する必要があります。 | お客様のデータ保持ポリシーをサポートするために Microsoft サービスによって提供される機能。<br>- *GDPR のための Azure データ 主体要求* [[9](gdpr-arc-Azure.md#9)]「ステップ 5: 削除」を参照 | (5)(1)(c)、(5)(1)(e)、(6)(4)(e)、(11)(1)、(32)(1)(a) |
| ***一時ファイル (7.4.6)*** | お客様は、個人データの取り扱いに関するポリシー違反を引き起こす恐れのある、システムによって作成される可能性がある一時ファイルについて認識しておく必要があります (たとえば、個人データを必要な期間または許可されている期間よりも長く一時ファイルに保持してしまうなど)。 システムが一時的なファイルの削除またはチェックするツールを提供する場合は、お客様はそのツールを利用して要件を遵守する必要があります。 | 個人データを識別して一時ファイルに関するポリシーをサポートするためにサービスによって提供される機能の説明。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]「ステップ 1: 発見」を参照 | (5)(1)(c) |
| ***保持期間 (7.4.7)*** | お客様は、特定の目的を考慮に入れつつ、個人データの保持期間を決定する必要があります。 | データ主体に提供するドキュメントに含めることができる Microsoft サービスによる個人データの保持に関する情報。<br>- *Microsoft Online Services の使用条件およびデータ保護条件。「データ セキュリティ、保持」を参照* [[1](gdpr-arc-Azure.md#1)] | (13)(2)(a)、(14)(2)(a) |
| ***廃棄 (7.4.8)*** | お客様は、個人データを削除するため、システムによって提供される削除または廃棄メカニズムがあれば、それらを利用する必要があります。 | お客様のデータ削除ポリシーをサポートする Microsoft サービスで提供される機能。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]「*ステップ 5： 削除*」を参照 | (5)(1)(f) |
| ***収集手順 (7.4.9)*** | お客様は、個人データの正確さに関する要件を認識している必要があります (収集に関する正確さ、データを最新の状態に保つ精度など)。また、そのようなシステムによって提供されるメカニズムを使用する必要があります。 | Microsoft サービスが個人データを正確に扱う方法、およびデータの正確さを規定するお客様のポリシーをサポートするために提供する機能。<br>- *GDPR のための Azure データ主体要求* [[9](gdpr-arc-Azure.md#9)]*「ステップ 3: 修正」を参照* | (5)(1)(d) |
| ***転送コントロール (7.4.10)***  | お客様は、転送メカニズム、転送記録に誰がアクセスできるかなど、個人データの転送の保護に関する要件を理解する必要があります。 | Microsoft サービスによって転送される個人データの種類、データが転送される場所、および転送に関する法的保護についての説明。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)] | (5)(1)(f) |
| ***PII 転送基盤の識別 (7.5.1)*** | お客様は、個人情報 (PII) の地理的に異なる場所への転送、およびそのような要件を満たすための手段の文書化に関する要件を認識している必要があります。 | Microsoft サービスによって転送される個人データの種類、データが転送される場所、および転送に関する法的保護についての説明。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)] | 条項 (44)、(45)、(46)、(47)、(48)、(49) |
| ***PII を転送する可能性がある国と組織 (7.5.2)*** | お客様は、個人データを転送する、またはその可能性のある国について理解し、そのことを個別のユーザーに提示できる必要があります。サードパーティ/処理者によってこの転送が実行される場合、お客様はその処理者からこの情報を入手する必要があります。   | Microsoft サービスによって転送される個人データの種類、データが転送される場所、および転送に関する法的保護についての説明。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)]<br>- 誰がどのような条件でデータにアクセスできるか [[7](gdpr-arc-Azure.md#7)] | (30)(1)(e)  |
| ***PII (個人データ) の転送の記録 (7.5.3)*** | お客様は、個人データの転送に関連するすべての必要な記録を維持する必要があります。サードパーティ/処理者が転送を行う場合、お客様は、それらの処理者が記録を適切に維持し、必要に応じてそれらを取得していることを確認する必要があります。 | Microsoft サービスによって転送される個人データの種類、データが転送される場所、および転送に関する法的保護についての説明。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報*[[11](gdpr-arc-Azure.md#11)]<br>- 誰がどのような条件でデータにアクセスできるか [[7](gdpr-arc-Azure.md#7)] | (30)(1)(e) |
| ***サードパーティへの PII 情報開示に関する記録 (7.5.4)*** | お客様は、個人データが誰に開示されたかについての記録に関する要件を理解する必要があります。これには、法執行機関などへの情報開示が含まれる場合があります。サードパーティ/処理者がデータが開示する場合、お客様は、それらの処理者が記録を適切に維持し、必要に応じてそれらを取得していることを確認する必要があります。 | 情報開示についての入手可能な記録を含め、個人データの開示情報の受信者のカテゴリに関して提供されるドキュメント。<br>- 誰がどのような条件でデータにアクセスできるか [[7](gdpr-arc-Azure.md#7)] <br>- Intune でのプライバシーおよび個人データ [[15](gdpr-arc-Azure.md#15)] *「Intune でのデータのセキュリティと共有」を参照* | (30)(1)(d) |
| ***共同管理者 (7.5.5)*** | お客様は、他の組織と共同管理者になるかどうかを決定し、責任について適切に文書化し、責任を割り当てる必要があります。 | オンライン サービスの使用条件 (OST) に定められているように、Microsoft はデータ処理者として、お客様 (データ管理者) に対し要求されたサービスを提供する目的でのみ顧客データを処理します。<br>- *Microsoft Online Services の使用条件およびデータ保護条件。「個人データの取り扱い」の「GDPR」を参照* [[1](gdpr-arc-Azure.md#1)] | (26)(1)、(26)(2) |

## <a name="5-data-protection--security"></a>5. データの保護とセキュリティ

|||||
|:-----|:-----|:-----|:-----|
|**分類**|**お客様の考慮事項**|**参照できる Microsoft ドキュメント**|**GDPR 条項への取り組み**|
| ***組織とそのコンテキストについての理解 (5.2.1)*** | お客様は、個人データの取り扱いに関する該当する要件 (規制など) を識別するために、個人データの取り扱いにおける役割 (管理者、処理者、共同管理者など) を決定する必要があります。 | 個人データを取り扱う際に、Microsoft がどのサービスを管理者または処理者が果たすサービスとしてみなすかについての説明。<br>- *Microsoft Online Services の使用条件およびデータ保護条件*。「個人データの取り扱い」の「GDPR」、「処理者および管理者の役割と責任」を参照 [[1](gdpr-arc-Azure.md#1)] | (24)(3)、(28)(10)、(28)(5)、(28)(6)、(32)(3)、(40)(1)、(40)(2)(a)、(40)(2)(b)、(40)(2)(c)、(40)(2)(d)、(40)(2)(e)、(40)(2)(f)、(40)(2)(g)、(40)(2)(h)、(40)(2)(i)、(40)(2)(j)、(40)(2)(k)、(40)(3)、(40)(4)、(40)(5)、(40)(6)、(40)(7)、(40)(8)、(40)(9)、(40)(10)、(40)(11)、(41)(1)、(41)(2)(a)、(41)(2)(b)、(41)(2)(c)、(41)(2)(d)、(41)(3)、(41)(4)、(41)(5)、(41)(6)、(42)(1)、(42)(2)、(42)(3)、(42)(4)、(42)(5)、(42)(6)、(42)(7)、(42)(8) |
| ***関係者が必要とするものと期待するものについての理解 (5.2.2)*** | お客様は、個人データの取り扱いにおいて役割または関心のある関係者 (規制機関、監査担当者、データ主体、個人データ契約処理者など) を識別する必要があります。また、必要に応じてそのような関係者を従事させるための要件について認識する必要があります。 | 個人データの取り扱いに関係するリスクを考慮しつつ、すべての利害関係者について Microsoft がどのような見解を持っているかについての説明。<br>- *顧客データ保護影響評価に関する Azure からの重要な情報* [[11](gdpr-arc-Azure.md#11)] | (35)(9)、(36)(1)、(36)(3)(a)、(36)(3)(b)、(36)(3)(c)、(36)(3)(d)、(36)(3)(e)、(36)(3)(f)、(36)(5) |
| ***情報セキュリティ管理システムの範囲に関する決定 (5.2.3、5.2.4)*** | お客様が持つ全体のセキュリティまたはプライバシー プログラムの一環として、個人データの取り扱いとそれに関連する要件を含める必要があります。 | Microsoft サービスで、情報セキュリティ管理およびプライバシー プログラムに個人データの取り扱いがどのように組み込まれているについての説明。<br>* *Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント* [[13](gdpr-arc-Azure.md#13)] A.19-A.29 を参照<br>* SOC 2 タイプ 2 監査レポート [[12](gdpr-arc-Azure.md#12)] | (32)(2) |
| ***計画 (5.3)*** | お客様は、実行するリスク評価の一部として個人データの取り扱いについて考慮し、制御する個人データに関連するリスクを軽減するために必要とする管理を適用しなければなりません。 | Microsoft サービスが個人データの取り扱いに固有のリスクを、全体のセキュリティおよびプライバシー プログラムの一部としてどのように見なしているかについての説明。<br>- *Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント* [[13](gdpr-arc-Azure.md#13)] A.19-A.29 を参照 | (32)(1)(b)、(32)(2) |
| ***情報セキュリティ ポリシー (6.2)*** | お客様は、個人データの保護が含まれるように既存の情報セキュリティ ポリシーを強化する必要があります。これには、該当する法律に準拠するために必要なポリシーも含まれます。 | 個人情報を保護するための情報セキュリティや特定の方策についての Microsoft のポリシー。<br>- *Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント* [13] A.19-A.29 を参照<br>- SOC 2 タイプ 2 監査レポート [[12](gdpr-arc-Azure.md#12)] | (24)(2) |
| ***情報セキュリティの組織、お客様の考慮事項 (6.3)*** | お客様は組織内で、セキュリティと個人データの保護に関する責任を定義する必要があります。これには、DPO など、プライバシーの問題を監督する特定の役割の設定が含まれる場合があります。これらの役割をサポートするために、適切なトレーニングや管理サポートを提供する必要があります。 | Microsoft のデータ保護責任者の役割、その責任の性質、レポート構造、および連絡先情報の概要。<br>- Microsoft DPO 情報 [[17](gdpr-arc-Azure.md#17)] | (37)(1)(a)、(37)(1)(b)、(37)(1)(c)、(37)(2)、(37)(3)、(37)(4)、(37)(5)、(37)(6)、(37)(7)、(38)(1)、(38)(2)、(38)(3)、(38)(4)、(38)(5)、(38)(6)、(39)(1)(a)、(39)(1)(b)、(39)(1)(c)、(39)(1)(d)、(39)(1)(e)、(39)(2) |
| ***人事管理セキュリティ (6.4)*** | お客様は、個人データの保護に関連するトレーニングを提供する責任を決定し、割り当てる必要があります。 | Microsoft のデータ保護責任者の役割、その責任の性質、レポート構造、および連絡先情報の概要。<br>- *Microsoft Cloud のセキュリティ ポリシー* [[4](gdpr-arc-Azure.md#4)]「03. 人事管理セキュリティ」を参照<br>- *FedRAMP Moderate FedRAMP システム セキュリティ プラン* [[3](gdpr-arc-Azure.md#3)]「13.2 認識とトレーニング (AT)」 を参照 | (39)(1)(b) |
| ***情報の分類 (6.5.1)*** | お客様は、個人データをデータ分類方式の一部として明確に考慮する必要があります。 | Microsoft で個人データをデータ分類で考慮する方法。情報のタグ付けと追跡。<br>-*Windows を使用するデータ管理者についての GDPR 考慮事項* [[11](gdpr-arc-Azure.md#11)] 「データのタグ付けと追跡」を参照 | (39)(1)(b) |
| ***リムーバブル メディアの管理 (6.5.2)*** | お客様は、リムーバブル メディアの使用に関する内部ポリシーを決定する必要があります。これは、個人データの保護 (暗号化デバイスなど) に関連しています。 | Microsoft サービスがリムーバブル メディア上で個人情報のセキュリティを保護する方法。<br>- *FedRAMP Moderate FedRAMP システム セキュリティ プラン* [[3](gdpr-arc-Azure.md#3)]「13.10 メディア保護 (MP)」を参照 | (32)(1)(a)、(5)(1)(f) |
| ***物理メディア転送 (6.5.3)*** | お客様は、物理メディアを移動する際に個人データを保護するための内部ポリシーを決定する必要があります (暗号化など)。 | Microsoft サービスで、物理メディアの移動中に個人データを保護する方法。<br>- FedRAMP Moderate FedRAMP システム セキュリティ プラン [[3](gdpr-arc-Azure.md#3)]「13.10 メディア保護 (MP)」参照<br> | (32)(1)(a)、(5)(1)(f) |
| ***ユーザー アクセスの管理 (6.6.1)*** | お客様は、使用するサービス内でアクセスを制御する責任について認識し、利用可能なツールを使用してそれらの責任を適切に管理する必要があります。 | アクセス制御を実施するための Microsoft サービスによって提供されるツール。<br>- Azure セキュリティのドキュメントのユーザー登録。<br>- Azure セキュリティの ドキュメント [[2](gdpr-arc-Azure.md#2)]「[ID とアクセス制御を用いた個人データ保護](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls)」を参照 | (5)(1)(f) |
| ***ユーザー登録と登録解除 (6.6.2)*** | お客様は、利用可能なツールを使用して、利用するサービス内でのユーザー登録および登録解除を管理する必要があります。 | アクセス制御を実施するための Microsoft サービスによって提供されるツール。<br>- Azure セキュリティのドキュメントのユーザー登録。<br>- Azure セキュリティの ドキュメント [[2](gdpr-arc-Azure.md#2)]「[ID とアクセス制御を用いた個人データ保護](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls)」を参照 | (5)(1)(f) |
| ***ユーザー アクセスのプロビジョニング (6.6.3)*** | お客様は、利用可能なツールを使用して、利用するサービス内での特に個人データへの許可されたアクセスに関するユーザー プロファイルを管理する必要があります。 | Microsoft サービスで個人データへの正式なアクセス制御をサポートする方法。これには、ユーザー ID、役割、ユーザーの登録と登録解除などが含まれます。<br>- Azure セキュリティの ドキュメント [[2](gdpr-arc-Azure.md#2)]「[ID とアクセス制御を用いた個人データ保護](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls)」を参照 | (5)(1)(f) |
| ***特権アクセスの管理 (6.6.4)*** | お客様は、利用可能なツールを使用して、利用するサービス内での (特に個人データへの) アクセスの追跡を容易にするユーザー ID を管理する必要があります。 | Microsoft サービスで個人データへの正式なアクセス制御をサポートする方法。これには、ユーザー ID、役割、ユーザーの登録と登録解除などが含まれます。<br>- Azure セキュリティの ドキュメント [[2](gdpr-arc-Azure.md#2)]「[ID とアクセス制御を用いた個人データ保護](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls)」を参照 | (5)(1)(f) |
| ***安全なログオン手順 (6.6.5)*** | お客様は、サービス内で提供されるメカニズムを使用して、必要に応じてユーザーが安全なログオン機能を利用できるようにする必要があります。 | Microsoft サービスで個人データに関連する内部アクセス制御ポリシーをサポートする方法。<br>- 誰がどのような条件でデータにアクセスできるか [[7](gdpr-arc-Azure.md#7)] | (5)(1)(f) |
| ***暗号化 (6.7)*** | お客様は、どのデータを暗号化する必要があるか、利用しているサービスがこの機能を提供しているかどうかを判断する必要があります。お客様は、利用可能なツールを使用して、必要に応じて暗号化を使用する必要があります。 | 個人データの取り扱いに関するリスクを低減するために Microsoft サービスが暗号化および仮名化をサポートする方法。<br>- Azure セキュリティのドキュメント [[2](gdpr-arc-Azure.md#2)] 「[停止中に暗号化によって個人データを保護する](https://docs.microsoft.com/azure/security/protect-personal-data-at-rest)」、「[輸送中に暗号化で個人データを保護する](https://docs.microsoft.com/azure/security/protect-personal-data-in-transit-encryption)」、および「[Azure 暗号化の概要](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)」を参照 | (32)(1)(a) |
| ***備品の安全な廃棄または再利用 (6.8.1)*** | お客様がクラウド コンピューティング サービス (PaaS、SaaS、IaaS) 使用している場合、クラウド プロバイダーが、お客様が利用していた記憶領域を別の顧客に割り当てる前に、その記憶領域から個人データをどのように削除するかについて理解しておく必要があります。 | Microsoft サービスで、記憶装置が移動または再利用される前に、その装置から確実に個人データが消去されるようにする方法。<br>- Microsoft Azure データ セキュリティ (データ クレンジングと漏洩) [[5](gdpr-arc-Azure.md#5)] | (5)(1)(f) |
| ***デスクの清掃および画面のクリアに関するポリシー (6.8.2)*** | お客様は、個人データを印刷した資料に関するリスクについて考慮し、潜在的なリスクを考慮してそのような資料の作成を制限する必要があります。使用中のシステムがこれらを制限する機能を備えている場合 (機密性の高いデータの印刷またはコピー/貼り付けを行えないようにする設定など)、お客様はそれらの機能を利用する必要性について考慮する必要があります。 | ハードコピーを管理するために Microsoft が実装している機能。<br>- Microsoft では、これらの管理を内部で維持しています。 「*Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント*」[[15](gdpr-arc-Azure.md#13)]  A.11.2.9 を参照 | (5)(1)(f) |
| ***開発、テスト、運用環境の分離 (6.9.1)*** | お客様は、組織内の開発環境およびテスト環境での個人データの使用について関連事項を考慮する必要があります。 | Microsoft が個人データを開発/テスト環境で確実に保護する方法。<br>- *Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント* [[13](gdpr-arc-Azure.md#13)] A.12.1.4 を参照<br>- セキュリティ、プライバシー、およびコンプライアンスに関する RFI への Azure 標準対応 [6]。<br>-Azure コントロール 530: 運用環境は、開発/テスト環境[[16](gdpr-arc-Azure.md#16)]から分離されています。 | 5(1)(f) |
| ***情報のバックアップ (6.9.2)*** | お客様は、必要に応じてデータの冗長性を確保してからテストを実行するために、システムに用意されている機能が使用されていることを確認する必要があります。 | Microsoft が個人データを含んでいる可能性のあるデータの可用性を確保する方法、復元データの正確性の保証方法、データのバックアップと復元を実行するために Microsoft サービスが提供するツールと手段。<br>- FedRAMP Moderate FedRAMP システム セキュリティ プラン [[3](gdpr-arc-Azure.md#3)]「10.9 可用性」を参照 | (32)(1)(c)、(5)(1)(f) |
| ***イベント ログ収集 (6.9.3)*** | お客様は、システムによって提供されるログ機能について理解し、そのような機能を利用して、必要だと思われる個人データに関連する処理が確実にログに記録されることを確認する必要があります。 | お客様のために Microsoft サービスが記録するデータ (これにはユーザーの操作、例外、障害、情報セキュリティ イベントが含まれます)。レコード保持の一環としてそれらのログにアクセスする方法。<br>- Azure セキュリティのドキュメントのユーザー登録。<br>- Azure セキュリティのドキュメント [[2](gdpr-arc-Azure.md#2)]「[Azure レポート ツールを使用した個人データの保護の文書化](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools)」を参照 | (5)(1)(f) |
| ***ログ情報の保護 (6.9.4)***  | お客様は、個人データを含んでいる可能性のあるログ情報、または個人データの処理に関する記録を含んでいる可能性のあるログ情報の保護に関する要件について考慮する必要があります。使用中のシステムがログを保護する機能を提供している場合、お客様は必要に応じてそれらの機能を利用する必要があります。 | Microsoft が個人データを含むログを保護する方法。<br>- Azure セキュリティのドキュメント [[2](gdpr-arc-Azure.md#2)]「[Azure レポート ツールを使用した個人データの保護の文書化](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools)」を参照 | (5)(1)(f) |
| ***情報転送のポリシーおよび手順 (6.10.1)*** | お客様は、物理メディア上の個人データを移動する (ハード ドライブをサーバーや施設の間で移動するなど) 場合に備えて手段を用意しておく必要があります。これらには、ログ、承認、追跡が含まれる場合があります。サードパーティまたは他の処理者によって物理メディアを移動する可能性がある場合、お客様はその組織が個人データのセキュリティを適正に確保する手順を設けていることを確認する必要があります。 | Microsoft サービスが個人データを含んでいる可能性のある物理メディアを移動する方法。移動が発生する可能性がある状況を含む。データを保護するために取る対策。<br>- *FedRAMP Moderate FedRAMP システム セキュリティ プラン* [[3](gdpr-arc-Azure.md#3)]「13.10 メディア保護 (MP)」を参照 | (5)(1)(f) |
| ***機密保持契約 (6.10.2)*** | お客様は、秘密保持契約の必要性について、あるいは個別のユーザーの個人データへのアクセスまたは個人データに関連する責任に関して同等のものが必要か判断する必要があります。  | 個人データへのアクセスを許可された個別のユーザーが秘密保持契約を結んでいることを Microsoft サービスが確認する方法。<br>- *SOC 2 タイプ 2 監査レポート* [[12](gdpr-arc-Azure.md#12)] CC1.4 pp72、SOC2 - 13 を参照 | (5)(1)(f)、(28)(3)(b)、(38)(5) |
| ***パブリック ネットワークでのアプリケーション サービスの保護 (6.11.1)*** | お客様は、特にパブリック ネットワークで送信を行う場合に、個人データの暗号化に関する要件について理解する必要があります。システムがデータを暗号化するメカニズムを提供する場合、お客様は必要に応じてそれらのメカニズムを利用する必要があります。 | 転送中にデータを保護するために Microsoft サービス が取る手段の説明 (データの暗号化を含む)。データがパブリック データ ネットワークを通過する際、個人データが含まれている可能性のあるデータを Microsoft サービス が保護する方法 (あらゆる暗号化の方法を含む)。<br>- Azure セキュリティのドキュメント [[2](gdpr-arc-Azure.md#2)]「[転送中に暗号化によって個人データを保護する](https://docs.microsoft.com/azure/security/protect-personal-data-in-transit-encryption)」を参照 | (5)(1)(f)、(32)(1)(a) |
| ***安全なシステム エンジニアリングの原則 (6.11.2)*** | お客様は、個人データの保護を考慮するにあたり、システムがどのように設計されているかを理解する必要があります。お客様がサードパーティによって設計されたシステムを使用している場合、お客様は、そのような保護が考慮に入れられていることを確認する責任があります。 | Microsoft サービスが安全な設計/エンジニアリングの原則の必須の部分として個人データ保護原則を組み込んでいる方法。<br>- SOC 2 タイプ 2 監査レポート [12] CC7.1 pp90 および「[セキュリティ開発ライフサイクルとは](https://www.microsoft.com/sdl/)」を参照 | (25)(1) |
| ***サプライヤーとの関係 (6.12)*** | お客様は、情報セキュリティおよび個人データの保護の要件、およびサードパーティの責任について契約またはその他の合意で規定されていることを確認する必要があります。また、それらの合意事項で処理の指示についても対処している必要があります。 | Microsoft サービスがサプライヤーとの契約でセキュリティおよびデータ保護を規定する方法と、それらの契約が効果的に実施されていることを確認する方法。<br>- 誰がどのような条件でデータにアクセスできるか [[7](gdpr-arc-Azure.md#7)] | (5)(1)(f)、(28)(1)、(28)(3)(a)、(28)(3)(b)、(28)(3)(c)、(28)(3)(d)、(28)(3)(e)、(28)(3)(f)、(28)(3)(g)、(28)(3)(h)、(30)(2)(d)、(32)(1)(b) |
| ***情報セキュリティ インシデントと改善の管理 (6.13.1)*** | お客様は、個人データ違反が発生した場合に究明するためのプロセスを構築しておく必要があります。 | Microsoft サービスが、セキュリティ インシデントが個人データに関する違反であるかどうかを判断する方法。違反についてお客様に伝達する方法。<br>-*Azure と GDPR の下での違反の通知* [[10](gdpr-arc-Azure.md#10)] | (33)(2) |
| ***責任と手順 (情報セキュリティ インシデントが発生した場合) (6.13.2)*** | お客様は、データ違反または個人データが関係したセキュリティ インシデントが発生した際の責任について理解し、それらを文書化しておく必要があります。責任には、必要な関係者に通知すること、処理者または他のサードパーティに伝達すること、およびお客様の組織内での責任が含まれる場合があります。 | セキュリティ インシデントまたは個人データの違反を検出した場合に Microsoft サービスに通知する方法。<br>-*Azure と GDPR の下での違反の通知* [[10](gdpr-arc-Azure.md#10)] | (5)(1)(f)、(33)(1)、(33)(3)(a)、(33)(3)(b)、(33)(3)(c)、(33)(3)(d)、(33)(4)、(33)(5)、(34)(1)、(34)(2)、(34)(3)(a)、(34)(3)(b)、(34)(3)(c)、(34)(4) |
| ***情報セキュリティ インシデントへの対応 (6.13.3)*** | お客様は、個人データ違反が発生した場合に究明するためのプロセスを構築しておく必要があります。 | 個人データの侵害が発生したかどうかをお客様が判断できるようにするため、 Microsoft サービス が提供する情報の説明。<br>- *Azure と GDPR の下での違反の通知* [[10](gdpr-arc-Azure.md#10)] | (33)(1)、(33)(2)、(33)(3)(a)、(33)(3)(b)、(33)(3)(c)、(33)(3)(d)、(33)(4)、(33)(5)、(34)(1)、(34)(2) |
| ***記録の保護 (6.15.1)*** | お客様は、維持する必要がある、個人データの取り扱いに関連する記録の要件を理解する必要があります。 | Microsoft サービスが個人データの取り扱いに関連する記録を保存する方法。<br>- Azure セキュリティのドキュメントのユーザー登録。<br>- Azure セキュリティのドキュメント [[2](gdpr-arc-Azure.md#2)]「[Azure レポート ツールを使用した個人データの保護の文書化](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools)」を参照 | (5)(2)、(24)(2)  |
| ***情報セキュリティの独立したレビュー (6.15.2)*** | お客様は、個人データの取り扱いに関するセキュリティ評価の要件を認識している必要があります。これには、内部または外部の監査、または処理のセキュリティを評価するその他の手段が含まれる場合があります。お客様が処理の一部またはすべてについて第三者にあたる別の組織に依存している場合、お客様は自分たちで行った評価に関する情報を収集する必要があります。 | データの取り扱いのセキュリティを確保するために、Microsoft サービスが技術的および組織的手段の効果性をテスト/評価する方法 (サード パーティによる任意の監査を含む)。<br/>*Microsoft Online Services の使用条件およびデータ保護条件。「データ セキュリティ」、「コンプライアンスの監査」を参照* [[1](gdpr-arc-Azure.md#1)] | (32)(1)(d)、(32)(2) |
| ***技術的なコンプライアンス レビュー (6.15.3)*** | お客様は、個人データの取り扱いに関するセキュリティのテストおよび評価についての要件を理解する必要があります。これには侵入テストなどの技術的なテストが含まれる場合があります。お客様がサードパーティ製システムまたはプロセッサを使用している場合、お客様は、セキュリティの確保およびセキュリティのテストに関して自身にどのような責任があるか (データを保護するための構成の管理やそれらの構成設定のテストなど) を理解している必要があります。サードパーティに処理のセキュリティに関するすべてまたは一部の責任がある場合、お客様は処理のセキュリティを確保するためにサードパーティが実施しているテストや評価の内容を理解する必要があります。 | Microsoft サービスで、インシデント リスクに基づいてセキュリティをテストする方法。これにはサードパーティによるテスト、技術テスト、これらのテストから得られるレポートが含まれます。<br>- *Microsoft Online Services の使用条件およびデータ保護条件。「データ セキュリティ」、「コンプライアンスの監査」を参照* [[1](gdpr-arc-Azure.md#1)]<br>- 外部証明の一覧については、「**Microsoft Trust Center コンプライアンスの提供 [** 14[]](gdpr-arc-Azure.md#14)」を参照してください。<br>- アプリケーションへの侵入テストの詳細については、*Azure セキュリティのドキュメント* [[2](gdpr-arc-Azure.md#2)]「[侵入テスト](https://docs.microsoft.com/azure/security/azure-security-pen-testing)」を参照 | (32)(1)(d)、(32)(2) |

## <a name="6-bibliography-of-resources-and-links"></a>6. リソースおよびリンクの文献目録

||||
|:-----|:-----|:-------|
|**ID**|**説明/リンク**|
| 1 <a name="1"> </a> | [オンライン サービスの使用条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
| 2 <a name="2"></a>  | [Azure セキュリティのドキュメント](https://docs.microsoft.com/azure/security/)。「ガバナンスとコンプライアンス」、「GDPR」を参照 |
| 3 <a name="3"> </a> | [FedRAMP Moderate FedRAMP システム セキュリティ プラン (SSP)](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=e46a519a-bcf6-4dc2-8f60-6d0e4e00a85e&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_FedRAMP_Reports) |
| 4 <a name="4"> </a>   | [Microsoft Cloud のセキュリティ ポリシー](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)  |
| 5 <a name="5"> </a>   | [Microsoft Azure データ セキュリティ (データ クレンジングと漏洩)](https://blogs.msdn.microsoft.com/walterm/2014/09/04/microsoft-azure-data-security-data-cleansing-and-leakage/) |
| 6 <a name="6"> </a>   | [セキュリティ、プライバシー、およびコンプライアンスに関する RFI への Azure 標準対応](https://gallery.technet.microsoft.com/Azure-Standard-Response-to-5de19cb6) |
| 7 <a name="7"> </a>   | [誰がどのような条件でデータにアクセスできるか](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms) |
| 8 <a name="8"> </a>   | [代理管理者の契約: Microsoft との契約](https://www.microsoft.com/procurement/supplier-contracting.aspx#SSPA) |
| 9 <a name="9"> </a>   | [GDPR のための Azure データ主体要求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) |
| 10 <a name="10"> </a> | [GDRP の下での Azure および Dynamics 365 の侵害通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics) |
| 11 <a name="11"> </a> | [顧客データ保護影響評価に関する Azure からの重要な情報](https://aka.ms/DPIAAzure) |
| 12 <a name="12"> </a> | [SOC 2 タイプ 2 監査レポート [12]](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=3c7123a5-f507-48b7-8dce-cd948e6150e6&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC_%2F_SSAE_16_Reports) |
| 13 <a name="13"> </a> | [Microsoft Azure (全体) ISO/IEC 27001:2013 ISMS の適用性に関するステートメント](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=47d89200-b24b-491d-b657-7c523ddfb6f9&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports) |
| 14 <a name="14"> </a> | [Microsoft Trust Center コンプライアンスで提供されるサービス](offering-home.md)  |
| 15 <a name="15"> </a> | [Intune でのプライバシーおよび個人データ](https://docs.microsoft.com/intune/privacy-personal-data) |
| 16 <a name="16"> </a> | [ダウンロード可能な、完全な Azure GDPR 管理セット](https://aka.ms/GDPRControls)または[コンプライアンス スコア](compliance-score.md) |
| 17 <a name="17"> </a> | [Microsoft DPO 情報](https://aka.ms/GDPRDPO) |

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [Secure Trust Portal](https://aka.ms/gdprgetstarted)
