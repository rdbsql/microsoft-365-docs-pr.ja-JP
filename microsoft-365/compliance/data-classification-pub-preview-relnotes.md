---
title: データ分類のリリース ノート
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: データ分類についてのリリース ノート。
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127142"
---
# <a name="data-classification-release-notes"></a>データ分類のリリース ノート

データ分類について最高の体験ができるように、これらのリリース ノートをご確認ください。

## <a name="exchange-mailbox-count"></a>Exchange メールボックス数

Exchange メールボックスに移動すると、小さなツール ヒントが表示されます。 これは、機密情報の種類、機密ラベル、および保持ラベルに表示される集計数が、メールボックス内にあるアイテムの数と正確に一致しない場合があることを示すためです。 これは、集計された数が計算されている間に、フォルダへのドリルダウンが分類されたコンテンツのライブ ビューをフェッチするためです。


## <a name="rendering-of-encrypted-documents"></a>暗号化されたドキュメントのレンダリング

暗号化された SharePoint、Exchange、および OneDrive ファイルは、コンテンツ エクスプローラーにレンダリングされません。 これは、コンテンツ エクスプローラーでファイル コンテンツを表示する必要性とコンテンツを暗号化しておく必要性とのバランスを必要とする、慎重を期する問題です。 **コンテンツ エクスプローラーのリスト ビューアー**、および **コンテンツ エクスプローラーのコンテンツ ビューアー** の役割グループによってアクセス許可が付与されると、ファイルのリスト ビュー、ファイルのメタデータ、および Web クライアント経由でコンテンツにアクセスするために使用できるリンクが表示されます。

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 検索の保持ラベル名でサポートされている文字

SharePoint検索では、`-` または `_` を含む保持ラベル名はサポートされていません。 たとえば、`Label-MIP` や `Label_MIP` はサポートされていません。 SharePoint 検索は、機密ラベル名および機密情報の種類の名前に含まれるこれらの文字はサポートします。

## <a name="onedrive-remains-in-preview"></a>OneDrive はプレビューのまま

プレビュープログラム中に、OneDrive との統合に関する貴重なフィードバックをいただきました。 具体的に作業を進めていくと、一貫性がないデータ/フローに遭遇する場合があります。 すべての修正が行われるまでは、引き続き OneDrive をプレビューとして紹介し続けます。 今後ともサポートをよろしくお願いいたします。


## <a name="see-also"></a>関連項目

- [データ分類の使用を開始する (プレビュー)](data-classification-overview.md)
- [ラベル アクティビティを表示する (プレビュー)](data-classification-activity-explorer.md)
- [ラベル付きコンテンツの表示 (プレビュー)](data-classification-content-explorer.md)
- [機密ラベルについて詳しく見る](sensitivity-labels.md)
- [保持ポリシーおよび保持ラベルについて詳しく見る](retention.md)
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)