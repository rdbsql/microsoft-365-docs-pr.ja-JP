---
title: Microsoft Dynamics 365 での暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Microsoft が暗号化テクノロジを使用して、microsoft データベース内および送信中の microsoft Dynamics 365 の顧客データを保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd349890fc7fc1ae7f1f7eaf07f90c22423637cf
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031414"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 での暗号化

Microsoft では、暗号化テクノロジを使用して、Microsoft データベースの保存期間中に、また、ユーザーのデバイスとデータセンター間で転送中の Dynamics 365 で顧客データを保護しています。 お客様と Microsoft データセンターの間で確立された接続は暗号化され、業界標準の TLS を使用してすべてのパブリックエンドポイントがセキュリティ保護されます。 TLS は、デスクトップとデータセンター間のデータの機密性と整合性を確保するために、セキュリティが強化されたブラウザーからサーバーへの接続を効果的に確立します。 データ暗号化がアクティブ化された後は、無効にすることはできません。 詳細については、「[フィールドレベルのデータ暗号化](https://msdn.microsoft.com/library/dn481562.aspx)」を参照してください。

Dynamics 365 は、ユーザー名や電子メールのパスワードなどの機密情報を含む既定のエンティティ属性のセットに対して、Microsoft SQL Server の標準のセルレベルの暗号化を使用します。 この機能は、組織が FIPS 140-2 に関連するコンプライアンス要件を満たすのに役立ちます。 フィールドレベルのデータ暗号化は、 [Microsoft DYNAMICS CRM 電子メールルーター](https://technet.microsoft.com/library/hh699800.aspx)を活用するシナリオで特に重要です。これには、dynamics 365 インスタンスと電子メールサービスの統合を可能にするためにユーザー名とパスワードを格納する必要があります。 

Dynamics 365 のすべてのインスタンスは、 [MICROSOFT SQL Server 透過的データ暗号化](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)(tde) を使用して、ディスクへの書き込み時にデータのリアルタイム暗号化 (rest) を実行します。 TDE は、SQL Server、Azure SQL Database、および Azure SQL Data Warehouse のデータファイルを暗号化します。 既定では、Microsoft は Dynamics 365 のインスタンスのデータベース暗号化キーを格納して管理します。 (Dynamics 365 で財務用に使用されるキーは、.NET Framework データ保護 API によって生成されます)。 

Dynamics 365 管理センターのキーの管理機能を使用すると、管理者は Dynamics 365 のインスタンスに関連付けられているデータベース暗号化キーを自己管理することができます。 (自己管理データベース暗号化キーは、Microsoft Dynamics 365 の2017年1月の更新プログラムでのみ使用可能で、以降のバージョンでは使用できない場合があります。 詳細については、「 [Dynamics の暗号化キーを Dynamics 365 (online) インスタンスで管理する](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)」を参照してください。キー管理機能は、HSM に格納されているものなど、PFX および BYOK 暗号化キーファイルの両方をサポートしています。 (HSM で保護されたキーをインターネット経由で生成して転送する方法の詳細については、「 [Azure Key Vault 用に hsm で保護されたキーを生成して転送する方法](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)」を参照してください)。 

[暗号化キーのアップロード] オプションを使用するには、公開キーと秘密暗号化キーの両方が必要です。

キー管理機能は、Azure Key Vault を使用して暗号化キーを安全に格納することで、暗号化キーの管理の複雑さを軽減します。 Azure Key Vault は、クラウドアプリケーションとサービスで使用される暗号化キーと機密情報を保護するのに役に立ちます。 キー管理機能では、Azure Key Vault サブスクリプションを必要としないため、ほとんどの状況では、コンテナー内で Dynamics 365 に使用される暗号化キーにアクセスする必要はありません。
