---
title: セキュリティ センターとコンプライアンス センターのレポート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: セキュリティ & コンプライアンスセンターを使用して、SharePoint Online および Exchange Online 組織のさまざまなレポートと、Azure Active Directory レポートを取得します。
ms.openlocfilehash: 8762c1bbb23d2b9f3840076f0ffa465cf7ab264b
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936180"
---
# <a name="reports-in-the-security--compliance-center"></a>セキュリティ センターとコンプライアンス センターのレポート

セキュリティ & コンプライアンスセンターの [**レポートの表示**] ページを使用して、SharePoint online 組織および Exchange online 組織の監査レポートにすばやくアクセスできます。 [**レポートの表示**] ページから、Azure Active DIRECTORY (AD) ユーザーのサインインレポート、ユーザーアクティビティレポート、および azure AD 監査ログにアクセスすることもできます。 これは、有料の Microsoft 365 サブスクリプションに Microsoft Azure への無料サブスクリプションが含まれているためです。 初めてこれらの Azure レポートにアクセスするときには、1回限りの登録プロセスを完了する必要があります。 
  
> [!TIP]
> 組織内のアクティビティに関するその他のレポートを表示するには、「 [Microsoft 365 管理センターのアクティビティレポート](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)」を参照してください。 
  
 **はじめに**
  
セキュリティ & コンプライアンスセンターでレポートを表示するには、次のアクセス許可が必要です。
  
- セキュリティ & コンプライアンスセンターでレポートを表示するには、Exchange 管理センター (EAC) でセキュリティリーダーの役割が割り当てられている必要があります。 既定では、この役割は EAC の [組織の管理] および [セキュリティリーダー] 役割グループに割り当てられます。
    
- セキュリティ & コンプライアンスセンターで DLP レポートを表示するには、セキュリティ & コンプライアンスセンターで、表示専用 DLP コンプライアンス管理役割が割り当てられている必要があります。 既定では、この役割は、セキュリティ & コンプライアンスセンターの [コンプライアンス管理者]、[組織の管理]、[セキュリティ管理者]、および [セキュリティリーダー] 役割グループに割り当てられます。

- また、EAC で DLP レポートを表示するには、EAC の表示専用の受信者の役割が割り当てられている必要があります。 既定では、この役割は、EAC の [コンプライアンス管理]、[組織の管理]、および [表示のみの組織の管理] 役割グループに割り当てられます。
  
 **セキュリティ & コンプライアンスセンターで [レポートの表示] ページを開くには、次のようにします。**
  
1. [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports) に移動します。
    
2. 組織内のユーザーアカウントの資格情報を使用してサインインします。
    
[**レポートの表示**] ページでは、次の種類のレポートを表示できます。 
  
- [監査レポート](#auditing-reports)
- [監督レビューレポート](#supervisory-review-report)
- [データ損失防止レポート](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>監査レポート

次の表では、セキュリティ & コンプライアンスセンターの [**レポートの表示**] ページの [**監査**] セクションのレポートについて説明します。 
  
|**レポート**|**説明**|
|:-----|:-----|
|**監査ログレポート** <br/> |組織内のユーザーと管理者のアクティビティについては、監査ログを検索できます。 このレポートには、Office 365 のディレクトリサービスである Exchange Online、SharePoint Online、OneDrive for Business、および Azure Active Directory のユーザーと管理者のアクティビティのエントリが含まれています。 詳細については、「[Search the audit log in the Office 365 (Office 365 での監査ログの検索)](search-the-audit-log-in-security-and-compliance.md)」を参照してください。  <br/> |
|**Azure AD レポート** <br/> |組織内での通常または疑わしいサインインアクティビティを検索するには、Microsoft Azure でサインインとアクティビティレポートを使用できます。 Azure AD 監査ログのイベントを表示することもできます。 Azure でレポートを表示するには、[ **AZURE AD レポートの表示**] のみをクリックします。 詳しくは、次のトピックを参照してください。 <br/><br/>[Office 365 で無料の Azure Active Directory サブスクリプションを使用](use-your-free-azure-ad-subscription-in-office-365.md)します。 <br/> [アクセスと使用状況レポートを表示](https://go.microsoft.com/fwlink/p/?LinkId=506902)します。  <br/> |
|**Exchange 監査レポート** <br/> | Microsoft 365 の監査機能を使用して、組織の管理者によって Exchange Online の構成に加えられた変更を追跡できます。 Microsoft データセンター管理者または代理管理者によって Exchange Online 組織に加えられた変更も記録されます。 Exchange Online では、管理者監査ログは既定で有効になっているので、これを有効にするために何もする必要はありません。 Exchange Online ではメールボックス監査ログも提供されており、メールボックスの所有者以外のユーザーによるメールボックスへのアクセスを追跡できます。 所有者以外のアクセスを追跡する各メールボックスでメールボックス監査ログを有効にする必要があります。  <br/>  管理者監査ログとメールボックス監査ログの両方で、監査ログ エントリを表示する監査レポートを実行することができます。 また、メールボックス監査ログおよび管理者監査ログをエクスポートし、24 時間以内にメールに添付された XML ファイル形式で受信することができます。 <br/><br/>監査ログのエクスポートについては、以下を参照してください。  <br/><br/> [メールボックス監査ログのエクスポート](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [データセンター管理者監査ログの表示とエクスポート](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [役割グループの変更または管理者監査ログを検索する](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 監査レポート](https://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>監督レビューレポート

監督レビューレポートを使用すると、組織内のすべての監督レビューポリシーの状態を確認できます。 詳細については、「[組織の監督レビューポリシーを構成する](configure-supervision-policies.md)」を参照してください。
  
## <a name="data-loss-prevention-reports"></a>データ損失防止レポート

データ損失防止 (DLP) レポートには、コンテンツに適用されている、組織内の機密データが含まれている DLP ポリシーとルールに関する情報が含まれています。 DLP ポリシーおよび規則に基づいて実行した DLP 操作に関する情報を表示するようレポートを構成することもできます。 詳細については、「[データ損失防止のレポートの表示](view-the-dlp-reports.md)」を参照してください。
