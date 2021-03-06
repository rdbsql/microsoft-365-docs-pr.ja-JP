---
title: 'フェーズ 3: Windows 10 Enterprise のインフラストラクチャの終了条件'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が Microsoft 365 Enterprise の Windows 10 Enterprise の条件を満たしていることを確認します。
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636689"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>フェーズ 3: Windows 10 Enterprise のインフラストラクチャの終了条件

![フェーズ 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 Enterprise インフラストラクチャが次の必須基準を満たすとともに、オプションの基準も考慮済みであることをご確認ください。

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>必須: Microsoft 365 のドメインが追加および検証されている

Office 365 サブスクリプションと Intune サブスクリプション用の Azure AD テナントは、“onmicrosoft.com” を含む単なるドメイン名ではなく、インターネット ドメイン名 (contoso.com など) で構成されます。 

そうしないと、構成可能な認証方法に制限されます。たとえば、パススルー認証とフェデレーション認証では、“onmicrosoft.com” ドメイン名は使用できません。

必要に応じて、[手順 1](windows10-prepare-your-org.md) がこの必須条件を満たす上で役立ちます。

## <a name="optional-your-users-are-added-and-licensed"></a>省略可能: ユーザーが追加およびライセンス付与されている

ユーザーに対応するアカウントは、Office 365 サブスクリプションと Intune サブスクリプション用の Azure AD テナントに直接追加されるか、またはオンプレミスの Active Directory Domain Services (AD DS) のディレクトリ同期から直接追加されます。

ユーザーが追加されると、グローバル管理者またはユーザー管理者として直接、あるいはグループ メンバーシップを通して自動的に、Microsoft 365 Enterprise ライセンスをユーザーに割り当てることができます。

必要に応じて、[手順 1](windows10-prepare-your-org.md) がこのオプション条件を満たす上で役立ちます。

## <a name="optional-diagnostics-are-enabled"></a>オプション: 診断が有効です

グループ ポリシー、Microsoft Intune、レジストリ エディター、またはコマンド プロンプトを使用して診断データの設定を有効にしました。

必要に応じて、[手順 1](windows10-prepare-your-org.md) がこのオプション条件を満たす上で役立ちます。

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>一括アップグレードに必須: オペレーティング システムの展開用に Configuration Manager のタスク シーケンスが作成されている

Windows 7 または Windows 8.1 を実行しているデバイス上で一括アップグレードを行うために Configuration Manager のタスク シーケンスを開始するには、以下の条件を満たしている必要があります。

- 適切な Windows 診断データ レベルを設定する
- Windows のアップグレードの準備状況を確認している
- Windows 10 OS イメージを使用したデバイス コレクションとオペレーティング システムの展開を含む Configuration Manager のタスク シーケンスを作成している

条件が満たされると、Windows のアップグレードの準備ができているデバイス上で一括インストールを実行できます。Microsoft 365 Enterprise のメリットを最大限に得るには、Windows 7 と Windows 8.1 を実行しているデバイスをできるだけ多くアップグレードします。 

Windows 10 Enterprise を実行している各デバイスは、Microsoft 365 Enterprise の統合されたソリューションの特典に参加できます。Windows 7 または Windows 8.1 を実行している他のデバイスでは、クラウドに接続されたテクノロジおよび Windows 10 Enterprise の高度なセキュリティ機能を使用できません。

必要に応じて、[手順 2](windows10-deploy-inplaceupgrade.md) がこの必須条件を満たす上で役立ちます。

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>新しいデバイスに必須: Windows Autopilot が構成されている

Windows Autopilot を使用して、新しいデバイス上で Windows 10 Enterprise を展開してカスタマイズするには、以下の条件を満たしている必要があります。

- 適切な Windows 診断データ レベルを構成している
- Windows Autopilot の前提条件 (以下の条件を含む) を構成している
   - デバイスの登録と OOBE のカスタマイズ
   - OOBE 向けの会社のブランド化
   - Microsoft Intune での MDM の自動登録
   - Windows Autopilot で使用するクラウド サービスへのネットワーク接続
- Windows 10 バージョン 1703 以降を事前にインストールしたデバイス
- 組織の Windows Autopilot Deployment を選択している

Windows Autopilot の構成が完了したら、それを使用して Windows 10 Enterprise を構成およびカスタマイズし、以下の OOBE (Out-of-Box Experience) を実現できます。

- 新しいデバイス
- 組織内の既定のセットアップを既に完了しているデバイス。 

Windows Autopilot は、デバイスを構成し、Azure AD に接続します。

Windows Autopilot を使用しない場合、Azure AD への接続を含む、新しいデバイスを手動で構成する必要があります。

必要に応じて、[手順 3](windows10-deploy-autopilot.md) がこの必須条件を満たす上で役立ちます。

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>省略可能: Windows Analytics デバイスの正常性を利用して、Windows 10 Enterprise ベースのデバイスを監視している

エンド ユーザーに影響を与える問題を検知して、修復するためにデバイスの正常性で、デバイスの正常性の監視の情報を使用しました。エンド ユーザーの問題を迅速に対処することで、サポート コストを削減し、Windows 10 Enterprise への IT コミットメントをユーザーに実証することができます。これにより、組織全体での導入の促進に役立ちます。 

必要に応じて、[手順 4](windows10-enable-windows-analytics.md) がこのオプション条件を満たす上で役立ちます。

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>必須: Windows Defender ウイルス対策または独自のマルウェア対策ソリューションを使用している

Windows 10 Enterprise を実行しているデバイスを悪意のあるソフトウェアから保護するために、Windows Defender ウイルス対策または独自のウイルス対策ソリューションを展開しました。Windows Defender ウイルス対策を展開した場合は、Microsoft Endpoint Configuration Manager または Microsoft Intune などのレポートの方法を実装して、ウイルス対策のイベントとアクティビティを監視します。

必要に応じて、[手順 5](windows10-enable-security-features.md#windows10-sec-av) がこの必須条件を満たす上で役立ちます。

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>必須: Windows Defender Exploit Guard を使用している

Windows 10 Enterprise を実行しているデバイスを侵入から保護するために、Windows Defender Exploit Guard を展開し、Configuration Manager または Microsoft Intune などのレポートの方法を実装しました。

必要に応じて、[手順 5](windows10-enable-security-features.md#windows10-sec-eg) がこの必須条件を満たす上で役立ちます。

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>必須: Microsoft Defender Advanced Threat Protection を使用している (Microsoft 365 E5 のみ)

ネットワークと Windows 10 Enterprise を実行しているデバイスに対する高度な脅威を検出し、調査し、対応するために Microsoft Defender Advanced Threat Protection (ATP) を展開しました。 

オプションとして、Microsoft Defender ATP を他のツールと統合し、その機能を拡張しました。

必要に応じて、[手順 5](windows10-enable-security-features.md#windows10-sec-atp) がこの必須条件を満たす上で役立ちます。

## <a name="results-and-next-steps"></a>結果と次のステップ

Windows 10 Enterprise インフラストラクチャは、新しいデバイスでのインストールと以前のバージョンの Windows を実行しているデバイスでの一括アップグレードを開始する準備ができており、Windows 10 Enterprise の重要なセキュリティ機能を使用しています。

|||
|:-------|:-----|
|![フェーズ 4: Microsoft 365 Apps for enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Microsoft 365 Enterprise のエンド ツー エンド展開のフェーズを実行している場合、次の手順は [Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md) です。 |
