---
title: 組織のサービスとしてのソフトウェアアプリを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft 365 管理センターでサードパーティ製アプリをアクティブ化および管理する方法について説明します。
ms.openlocfilehash: ed1a88345ae5cc135a43f4297ce518b444eaabe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402584"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a>組織のサードパーティ製アプリのサブスクリプションを管理する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

プレビューモードがオンになっている Microsoft 365 管理センターで、サードパーティ製アプリのライセンスと請求を管理することができます。 更新された機能には、サブスクリプション管理の強化、請求情報へのアクセスの向上、請求書管理の柔軟性の向上などがあります。 サブスクリプション管理は、Microsoft の更新された commerce プラットフォームに基づいています。 これは、顧客が直接購入した、またはサードパーティプロバイダーからの、サービスとしてのソフトウェアアプリに適用されます。

## <a name="how-to-get-software-as-a-service-apps"></a>サービスとしてのソフトウェアアプリを入手する方法

サードパーティ製アプリを購入するには、いくつかの方法があります。

- **直接購入**–お客様は、 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)または[appsource](https://www.appsource.com/)からサブスクリプションを直接購入できます。
- **パートナー購入**–パートナーと協力してサブスクリプションを購入します。
- **Microsoft 提案**: サードパーティ製のアプリを含む microsoft Sales からの提案に対応します。

お客様は、お客様がアプリを購入し、microsoft のカスタマーアグリーメントに同意すると、Microsoft 365 管理センターまたは Microsoft Store for Business でそれらを管理することができます。

アプリプロバイダーは、フラットなレートで、またはユーザーのライセンスを購入することで、アプリを販売します。

- **一律レート**–サイトベースの価格とも呼ばれ、アプリの価格は月または年間の価格になります。 [アプリ] ページで、ライセンスの数量が無制限に一覧表示されます。
- **ライセンス**–アプリの価格はライセンスによるものです。 顧客が組織内の各ユーザーにライセンスを割り当てる

## <a name="supported-regions"></a>サポートされる地域

サードパーティ製アプリのサポートは、次の地域で利用できます。

- アルゼンチン
- オーストラリア
- カナダ
- チリ
- フランス
- ドイツ
- ギリシャ
- プエルトリコ
- 南アフリカ
- 英国
- 米国
- 西ヨーロッパ

## <a name="activate-third-party-apps"></a>サードパーティ製アプリをアクティブ化する

管理者は、ユーザーに割り当てる前にサードパーティ製アプリをアクティブ化する必要があります。 これらのアプリは、サードパーティの発行元のポータルでアクティブ化されます。

1. 管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。
2. 管理するアプリを検索して選択します。
3. [**設定 & アクション**] で、[**パブリッシャーのポータルで管理**] を選択します。

アプリをアクティブ化できるアプリの発行元のサイトが表示されます。

## <a name="manage-third-party-apps"></a>サードパーティ製のアプリを管理する

管理者は、サードパーティ製アプリを2か所で管理します。 Microsoft 365 管理センター、およびサードパーティのアプリプロバイダーのポータル。

各ポータルで実行できる操作は次のとおりです。

| Microsoft 365 管理センター | アプリ発行元ポータル |
| --- | --- |
| ライセンス数を変更する <br> 支払い方法を管理する <br> 支払い方法を管理する <br> 支払い方法の変更 (クレジットカード) <br> 請求書の表示 <br> アプリのサブスクリプションをキャンセルする | アプリをセットアップする (アプリごとに1回) <br> ユーザーにライセンスを割り当てる <br> テクニカル サポート |

アプリがアクティブ化されると、そのアプリはキャンセルされるか、期限切れになるか、または支払いが最新の状態に保たれない限り、アクティブのままになります。 これらのイベントは、アプリの状態を無効に変更します。 アプリを無効にすると、再度アクティブにすることはできません。 アプリを引き続き使用するには、別のコピーを購入してください。

## <a name="assign-licenses"></a>ライセンスを割り当てる

管理者は、ユーザーに割り当てる前に、サードパーティ製のアプリをアクティブ化する必要があります。 これらは、サードパーティの発行元のポータルでアクティブ化されています。 [アプリ] ページの [**設定 & アクション**] で、ライセンスを割り当てるリンクを選択します。

1. 管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。
2. 管理するアプリを検索して選択します。
3. **[設定とアクション]** で、**[発行元のポータルで管理する]** へのリンクを選択します。

## <a name="change-license-quantity"></a>ライセンス数を変更する

管理者は、組織によって所有されているライセンスの数を変更できます。 これは、座席ベースの価格設定を使用して購入したアプリにのみ適用されます。

1. 管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。
2. 管理するアプリを検索して選択します。
3. [**ライセンス数量の変更**] を選択します。

## <a name="manage-payment-methods"></a>支払方法を管理する

サービスとしてのソフトウェアアプリにはそれぞれ、請求プロファイルが割り当てられています。 請求プロファイルを使用すると、請求書に含める製品をカスタマイズしたり、請求書に支払いを行ったりすることができます。 これには以下の関係者が含まれます。

- **支払い方法**–クレジットカードまたは小切手/ワイヤ転送
- **連絡先情報**-請求先住所と連絡先の名前
- **役割**–請求プロファイルを変更したり、支払いを行ったり、購入するために請求書プロファイルの支払い方法を使用したりできるようにする役割。

請求プロファイルの詳細については、「[課金プロファイル](https://docs.microsoft.com/microsoft-store/billing-profile)について」を参照してください。

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a>サービスとしてのソフトウェアアプリサブスクリプションの課金プロファイルを変更する

1. 管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。
2. 管理するアプリを検索して選択します。
3. [**課金プロファイル**] の横にある [**編集**] を選択します。

請求書の詳細について[は、「bill または請求書](billing-and-payments/understand-your-invoice.md)について」を参照してください。

## <a name="cancel-a-software-as-a-service-app-subscription"></a>サービスとしてのソフトウェアアプリのサブスクリプションをキャンセルする

アプリページから、サービスとしてのソフトウェアアプリを取り消すことができます。

1. 管理センターで、[製品アプリの**課金**] ページに移動し  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a>ます。
2. 管理するアプリを検索して選択します。
3. [**設定とアクション**] の下で、[**サブスクリプションのキャンセル**] を選択します。
