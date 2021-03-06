---
title: コンテンツ検索を使用してサードパーティのインポートされたデータを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: コンテンツ検索電子情報開示ツールを使用して、Microsoft 365 のメールボックスにインポートされたアイテムを、サードパーティのデータソースからクエリを作成して検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 916a780bccc3f24d509991e8ac72f31b374757d4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819097"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>コンテンツ検索を使用して、カスタムパートナーコネクタによってインポートされたサードパーティデータを検索する

セキュリティ & コンプライアンスセンターの[コンテンツ検索電子情報開示ツール](content-search.md)を使用して、サードパーティのデータソースから Microsoft 365 のメールボックスにインポートされたアイテムを検索することができます。 インポートされたサードパーティのすべてのデータアイテムを検索するクエリを作成するか、特定のサードパーティデータアイテムを検索するためのクエリを作成することができます。 また、サードパーティのデータを保持するために、クエリベースのアイテム保持ポリシーまたはクエリベースの電子情報開示の保持を作成することもできます。
  
サードパーティのデータをインポートするパートナーとの作業の詳細と、Microsoft 365 にインポートできるサードパーティのデータ型の一覧については、「365 Office を使用してサードパーティのデータ[をアーカイブする](work-with-partner-to-archive-third-party-data.md)」を参照してください。

> [!IMPORTANT]
> この記事のガイダンスは、カスタムパートナーコネクタによってインポートされたサードパーティデータにのみ適用されます。 この記事は、Microsoft コンプライアンスセンターで[サードパーティのデータコネクタ](archiving-third-party-data.md#third-party-data-connectors)を使用してインポートされたサードパーティのデータには適用されません。
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>すべてのサードパーティデータを検索するクエリを作成する

Office 365 にインポートしたすべての種類のサードパーティデータを検索 (または保留) するには、[ `kind:externaldata` キーワード] ボックスで [メッセージのプロパティと値のペア] を使用して、コンテンツ検索を実行するか、クエリベースのホールドを作成します。 たとえば、インポートされたアイテムの Subject プロパティに "contoso" という単語を含む、サードパーティのデータソースからインポートされたアイテムを検索するには、次のクエリを使用します。 
  
```powershell
kind:externaldata AND subject:contoso
```

前述のキーワードクエリの例には、subject プロパティが含まれています。 キーワードクエリに含めることができるサードパーティのデータアイテムに関するその他のプロパティの一覧については、「 [partner と連携してサードパーティのデータを Office 365 でアーカイブする](work-with-partner-to-archive-third-party-data.md#more-information)」の「詳細情報」セクションを参照してください。
  
サードパーティのデータを検索して保持するためのクエリを作成するときに、条件を使用して検索結果を絞り込むこともできます。 コンテンツ検索クエリの作成の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>特定の種類のサードパーティデータを検索するためのクエリを作成する

すべての種類のサードパーティデータを検索するのではなく、次のメッセージ*プロパティ*を使用して、サードパーティデータの種類のみを検索するクエリを作成できます。
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データを検索するには、次のクエリを使用します。
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

次の表に、検索可能なサードパーティのデータ型と、 `itemclass:` そのサードパーティデータの種類を特定するためにメッセージプロパティに対して使用する値を示します。 クエリ構文では大文字と小文字が区別されません。 
  
|**サードパーティのデータ型**|**プロパティの値 `itemclass:`**|
|:-----|:-----|
|目的  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot クライアント  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|アレス  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|を持つ (Placeholder) プレースホルダー  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 呼び出しログ  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry メッセンジャー  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg メール  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|検索ボックス  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; プレゼンスサーバー  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google +  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM 接続  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE チャット  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|マインド揃え  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|ウェブ  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|ピボット  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|終わり  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS チャット  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
