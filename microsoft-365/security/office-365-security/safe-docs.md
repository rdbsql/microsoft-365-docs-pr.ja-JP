---
title: Office 365 ATP の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 または Microsoft 365 E5 セキュリティの安全なドキュメントについて説明します。
ms.openlocfilehash: c574e28a01dc961d898638184afe9ece90e31133
ms.sourcegitcommit: aa7f7350d1342ff9713bb840b2cc96d1a4234ef4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2020
ms.locfileid: "44835353"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 の安全なドキュメント

「安全なドキュメント」は、microsoft [Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して、[保護ビュー](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)で開かれたドキュメントやファイルをスキャンする、microsoft 365 e5 または microsoft 365 E5 セキュリティの機能です。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Office バージョン 2004 (12730) を使用しているユーザーが、安全なドキュメントを使用できるようになりました。 この機能は既定でオフになっており、セキュリティ管理者が有効にする必要があります。

- この機能は、 *microsoft 365 E5*または*Microsoft 365 E5 セキュリティ*ライセンスを持つユーザーのみが使用できます (Office 365 ATP プランには含まれていません)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行するには、あらかじめアクセス許可を割り当てる必要があります。 安全なドキュメントを有効にして構成するには、組織の**管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

## <a name="how-does-microsoft-handle-your-data"></a>Microsoft はどのようにデータを処理していますか?

保護された状態を維持するために、安全なドキュメントは、分析のために[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)クラウドにファイルを送信します。

- Microsoft Defender Advanced Threat Protection がデータをどのように処理するかの詳細については、[こちら](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)を参照してください。
- 上記のガイドラインに加えて、安全なドキュメントによって送信されたファイルは、分析に必要な時間を超えて (通常は24時間未満)、Defender に保持されません。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>セキュリティ & コンプライアンスセンターを使用して安全なドキュメントを構成する

1. のセキュリティ & コンプライアンスセンター] を開き <https://protection.office.com> ます。

2. [**脅威管理** \> **ポリシー** \> **ATP 安全な添付ファイル**] に移動します。

3. [ **Office アプリケーションで保護されたビューの外部で開くファイルを信頼する**] セクションで、次のどちらかの設定を構成します。

   - **Office クライアントの安全なドキュメントを有効にする**

   - **安全なドキュメントが悪意のあるファイルを識別している場合でも、保護されたビューのクリックをユーザーに許可**します。このオプションは有効にしないことをお勧めします。

4. 完了したら、**[保存]** をクリックします。

![ATP の「安全な添付ファイル」ページ](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Exchange Online の PowerShell またはスタンドアロンの EOP PowerShell を使用して安全なドキュメントを構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _Enablesafedocs_パラメーターは、組織全体に対して安全なドキュメントを有効または無効にします。

- _Allowsafedocsopen_パラメーターを使用すると、ドキュメントが悪意のあるものとして識別された場合に、保護されたビュー (ドキュメントを開く操作) をユーザーが終了できないようにすることができます。

この例では、組織全体に対して安全なドキュメントを有効にし、保護されたビューから悪意があると識別されたドキュメントをユーザーが開くことができないようにします。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

安全なドキュメントを有効にして構成したことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動して、[ **Office アプリケーションの外部で保護されたビューの外部で開くファイルを信頼する際**に、ユーザーが安全に実行できるようにする] セクションの選択内容を確認します。

- Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
