---
title: 検索の統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b7975f5d288348177cbb6edec8002b4ed49de327
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069874"
---
# <a name="search-statistics"></a>検索の統計

検索結果を検証する方法の1つは、結果に関する統計を調べて、期待どおりに配置されるようにすることです。 検索が完了すると、高度な統計情報が検索の詳細ポップアップに表示されます。
- 検索によって取得されたアイテムの数とボリューム
- 検索場所で見つかった、部分的にインデックスまたはインデックスが設定されていないアイテムの数とボリューム
- 検索されたメールボックスと場所の数。
詳細な統計情報を表示するには、検索の詳細ポップアップから [統計] をクリックします。

## <a name="summary"></a>概要

要約ビューでは、検索結果が場所の種類 (例: Exchange) ごとに分類されて表示されます。 場所の種類ごとに、次の情報が表示できます。
- 検索条件に一致したアイテムがある場所の数
- 検索条件に一致したこれらの場所からのアイテムの数
- 検索条件に一致したアイテムの合計量。

## <a name="top-locations"></a>トップの場所

[上部の場所] ビューには、最も一致がある個々の場所が表示されます。 場所ごとに、次の情報が表示されます。
- 場所の名前 (例: SharePoint URL)
- 場所の種類
- 検索条件に一致したアイテムの数
- 検索条件に一致したアイテムの合計量。

## <a name="queries"></a>クエリ

クエリで (c:s) キーワードまたはキーワード行を使用している場合は、場所の種類ごとのクエリビューにクエリのブレークダウンを表示できます。 場所の種類ごとに、次のように表示されます。

- Part: この列には、"Primary" または "Keyword" という単語が表示されます。 "Primary" は、クエリ全体に対して行が統計情報を表示することを意味し、"Keyword" は1つのクエリコンポーネントを表します。

- クエリ: 行が参照している実際のクエリコンポーネントです。 Part が "Primary" の場合、これはクエリ全体になります。Part が "Keyword" であった場合は、クエリコンポーネントのいずれかがここに表示されます。
  
  - キーワードを指定せずにすべての contentin メールボックスを検索すると、実際のクエリは (size >= 0)、すべてのアイテムが返されるようになります。
  
  - SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。
    
    - NOT IsExternalContent: 1-オンプレミスの SharePoint 組織からコンテンツを除外する
    
    - NOT isOneNotePage: 1-すべての OneNote ファイルを除外します。これは、検索クエリに一致するドキュメントと重複する可能性があるためです。

- 検索条件に一致したアイテムがある場所の数。

- 検索条件に一致したこれらの場所からのアイテムの数。

- 検索条件に一致したアイテムの合計量。
