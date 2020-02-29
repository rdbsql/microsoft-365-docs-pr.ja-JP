---
title: 管理センターの Microsoft 365 レポート-SharePoint サイトの使用状況
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'Sharepoint サイトの利用状況レポートを取得して、ユーザーが SharePoint サイトに格納しているファイルの数、アクティブに使用されている数、および使用されている記憶域の合計量を把握します。 '
ms.openlocfilehash: 3e5ef1bb909bf14d775940615fa15293ed6161b2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241781"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>管理センターの Microsoft 365 レポート-SharePoint サイトの使用状況

Microsoft 365 管理者としての**レポート**ダッシュボードには、組織内のさまざまな製品におけるアクティビティの概要が表示されます。 これにより、各製品に固有のアクティビティについてより詳しく知ることができます。 たとえば、ユーザーが SharePoint サイトに保存するファイルの合計数、アクティブに使用されているファイルの数、およびこれらすべてのサイトにわたって使用される記憶域の観点から、SharePoint から得られる価値の概要をとらえることができます。 その後、[SharePoint サイトの利用状況] レポートを詳細に確認して、すべてのサイトの傾向およびサイトごとのレベル詳細を把握できます。 
  
> 注: Microsoft 365 または Exchange、SharePoint、Skype for business の管理者がレポートを表示するには、グローバル管理者、グローバルリーダーまたはレポート閲覧者である必要があります。 
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>[SharePoint サイトの利用状況] レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

    
2. **[レポートの選択**] ドロップダウンから、[ **SharePoint** \> **サイトの利用状況**] を選択します。
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>[SharePoint サイトの利用状況] レポートの解釈

![SharePoint Site Usage Report](../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |[ **SharePoint サイトの利用状況**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。  <br/> |
|2.  <br/> |各レポートのデータは、通常、過去 24 - 48 時間まで表示されます。 <br/> |
|3.  <br/> |[ **サイト**] グラフは、サイトの合計数とアクティブなサイトの数を示します。ユーザーがレポート期間内にファイルを表示、変更、アップロード、ダウンロード、共有、または同期したサイトまたはページを表示したサイトすべてです。  <br/> |
|4.  <br/> |[ **ファイル**] グラフは、サイト全体のファイルの総数と、アクティブなファイルの数を示します。ファイルの総数には、ユーザー ファイルとシステム ファイルの両方が含まれます。ファイルは、一定の期間内に保存、同期、変更、または共有されている場合にアクティブと見なされます。  <br/> 注: ファイルアクティビティは1つのファイルに対して複数回発生することがありますが、1つのアクティブなファイルとしてカウントされます。 たとえば、一定の期間に複数回、同じファイルを保存して同期することができますが、データには単独のアクティブなファイルと、単独の同期されたファイルとしてカウントされます。           |
|5.  <br/> |[ **記憶域**] グラフは、レポート期間中に割り当てられて使用される記憶域の傾向を示します。  <br/> |
|6.  <br/> |[ **ページ**] グラフは、すべてのサイトで表示されたページ数を示します。  <br/> |
|7.  <br/> |凡例の項目を選択すると、表示されるグラフにフィルターを適用することができます。 たとえば、[**ファイル**] グラフで、[**ファイル**] または [**アクティブなファイル**] を選択します。 [**サイト**] グラフでは、[**サイトの合計**] または [**アクティブなサイト**] を選択できます。 [**記憶域**] グラフでは、**割り当て済み記憶域**または記憶域が消費されているものを選択でき**ます。** この選択を変更しても、グリッド テーブルの情報は変更されません。  <br/> |
|8.  <br/> | テーブルには、サイト レベルでのアクティビティの内訳が表示されます。  <br/> ![利用状況レポートの列オプション](../media/sharepointsite-usage.png)           <br/> [ **サイトの URL**] は、サイトの完全な URL です。  <br/> [ **削除済み**] は、サイトの削除ステータスです。サイトを削除済みとしてマークするには、少なくとも 7 日かかります。  <br/> [ **サイトの所有者**] は、サイトのプライマリ所有者のユーザー名です。  <br/>**サイト所有者のプリンシパル名**は、サイトの所有者の電子メールアドレスです。  <br/> [ **最後のアクティビティの日付 (UTC)**] は、サイトでファイル アクティビティが最後に検出されたまたはページが表示された日付を指します。  <br/> [ **ファイル**] は、サイト上のファイルの数です。  <br/> **Active files**は、サイト上のアクティブなファイルの数です。 ファイルは、一定の期間内に保存、同期、変更、または共有されている場合にアクティブと見なされます。  <br/> 注: ファイルアクティビティは1つのファイルに対して複数回発生することがありますが、1つのアクティブなファイルとしてカウントされます。 たとえば、一定の期間に複数回、同じファイルを保存して同期することができますが、データには単独のアクティブなファイルと、単独の同期されたファイルとしてカウントされます。 >  特定の期間中、レポート内のファイルが削除された場合、レポートに表示されるアクティブ ファイルの数は、サイト上の現在あるファイルの数よりも多いことがあります。<br/>[ **使用済み記憶域 (MB)**] は、サイトで現在使用されている記憶域の容量です。  <br/> [ **割り当て済み記憶域 (MB)**] は、サイトに割り当てられた記憶域の最大容量です。  <br/> [ **ページ ビュー**] は、サイトでページが表示された回数です。  <br/> [ **訪問されたページ**] は、サイトで固有のページが表示された回数です。  <br/> [ **ルート Web テンプレート**] は、サイトを作成するために使用されるテンプレートです。  <br/> 注: 異なるサイトの種類でデータをフィルター処理する場合は、データをエクスポートし、[ルート Web テンプレート] 列を使用します。 <br/>ユーザー情報を特定できるレポートの閲覧が組織のポリシーで禁止されている場合は、これらすべてのレポートのプライバシー設定を変更できます。 「**Microsoft 365 管理センターのアクティビティ レポート**」の「[ユーザー レベルの詳細を非表示にする方法](activity-reports.md)」セクションを参照してください。  <br/> |
|9.  <br/> |[列の**管理**![]](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png)を選択して、レポートの列を追加または削除します。    <br/> |
|10.  <br/> |**エクスポート** ![エクスポート](../media/4dc548cc-8061-48d5-9240-6793affca43a.png)リンクを選択して、レポートデータを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのサイトのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 サイトが 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 サイトが 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。  <br/> 注: データが Excel ファイルにエクスポートされるときに、コンテンツレポートが生成された日付が、列**のデータ**内のファイルに反映されることに注意してください。      <br/>   |
|||
   
