---
title: 管理センターの microsoft 365 レポート-Microsoft Teams デバイスの使用状況
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Microsoft 365 レポートから Microsoft Teams アプリの使用状況レポートを取得することによって、組織で使用される Microsoft Teams アプリの洞察を得ることができます。
ms.openlocfilehash: c2070f13c790f2a66c5849e68fc2fe3579ffa3e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387720"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>管理センターの microsoft 365 レポート-Microsoft Teams デバイスの使用状況

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams アプリの使用状況レポートでは、組織で使用されている Microsoft Teams アプリについての洞察を得ることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

    
2. **[レポートの選択**] ドロップダウンから、[ **Microsoft Teams** \> **デバイスの使用状況**] を選択します。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポートを解釈する

[ **ユーザー**] グラフと [ **分布**] グラフを確認すると、Microsoft Teams アプリの使用状況を把握することができます。 
  
![Microsoft 365 レポート-Microsoft Teams アプリの使用状況](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |[ **Microsoft Teams デバイスの使用状況**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。  <br/> |
|2.  <br/> |各レポートのデータは、通常、過去 24 - 48 時間まで表示されます。  <br/> |
|3.  <br/> |[ **ユーザー**] ビューには、アプリごとの日単位の一意のユーザーの数が表示されます。  <br/> |
|4.  <br/> |[ **分布**] ビューには、選択した期間におけるアプリごとの一意のユーザーの数が表示されます。  <br/> |
|5.  <br/> | [ **ユーザー**] グラフの Y 軸は、アプリごとのユーザー数です。  <br/>  [ **分布**] グラフの Y 軸は、指定されたアプリを使用したユーザーの数です。  <br/>  グラフの X 軸は、特定のレポートに対して選択した日付範囲です。  <br/> |
|6.  <br/> |凡例の項目を選択して、グラフに表示する系列をフィルター処理できます。 たとえば、[**ユーザー** ] グラフで、それぞれに関連する情報のみを表示するには、[ **windows**]、[ **Mac**]、[**呼び出し**]、[ **Web**]、[ **Android phone**]、または [ **windows phone** ] を選択します。 この選択を変更しても、グリッド テーブルの情報は変更されません。  <br/> ![アプリの種類を選択することによって、Microsoft Teams のアプリの利用状況グラフをフィルター処理できます。](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | 表示されるグループのリストは、最も長い (180 日) レポート期間にわたって存在した (削除されなかった) すべてのグループのセットによって決まります。アクティビティ数は、日付の選択によって異なります。  <br/> 注: 次の一覧のすべての項目は、追加するまで列に表示されないことがあります。<br/> [ **ユーザー名**] はユーザーのメール アドレスです。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> [ **最終活動日 (UTC)**] は、ユーザーがアプリで Microsoft Teams アクティビティに参加した最後の日付を指します。  <br/> [ **削除済み**] は、チームが削除されたかどうかを示します。レポート期間中にアクティビティがあるチームが削除されると、[削除済み] が true に設定された状態でグリッドに表示されます。  <br/> [ **削除日**] は、チームが削除された日付です。  <br/> [ **Windows**] では、指定された期間中にユーザーが Windows アプリでアクティブになったかどうかがチェックされます。  <br/> [ **Mac**] では、指定された期間中にユーザーが Mac アプリでアクティブになったかどうかがチェックされます。  <br/> [ **Web**] では、指定された期間中にユーザーが Web アプリでアクティブになったかどうかがチェックされます。  <br/> [ **iOS**] では、指定された期間中にユーザーが iOS アプリでアクティブになったかどうかがチェックされます。  <br/> [ **Android スマートフォン**] では、指定された期間中にユーザーが Android スマートフォン アプリでアクティブになったかどうかがチェックされます。  <br/> [ **Windows Phone**] では、指定された期間中にユーザーが Windows Phone アプリでアクティブになったかどうかがチェックされます。  <br/>  組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 「**Microsoft 365 管理センターのアクティビティ レポート**」の「[ユーザー レベルの詳細を非表示にする方法](activity-reports.md)」セクションを参照してください。  <br/> |
|8.  <br/> |レポートに列を追加または削除する**列**を選択します。  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |**エクスポート**リンクを選択して、レポートデータを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。  <br/> |
|||
   
  

