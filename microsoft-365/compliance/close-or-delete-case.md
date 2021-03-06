---
title: ケースを閉じるか、ケースを削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: 高度な電子情報開示ケースでサポートされている調査または訴訟のケースがクローズまたは削除されたときに行われる処理について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419063"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>高度な電子情報開示ケースをクローズまたは削除する

高度な電子情報開示ケースでサポートされている訴訟や調査が完了すると、ケースをクローズまたは削除することができます。 クローズしたケースを再度開くこともできます。

## <a name="close-a-case"></a>ケースをクローズする

高度な電子情報開示ケースをクローズすると、次のような結果になります。

- ケースに、保留中のコンテンツの場所が含まれている場合は、それらの保持がオフになります。 保留がオフになると、保留中のコンテンツの場所に対して30日間の猶予期間 (*遅延ホールド*と呼ばれます) が適用されます。 これにより、コンテンツがすぐに削除されないようにすることができ、遅延保持期間が経過した後に完全に削除されるコンテンツを検索したり、復元したりする機会を管理者に与えることができます。 詳細については、「[電子情報開示の保留リストからコンテンツの場所を削除する](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)」を参照してください。

- ケースを閉じるだけで、そのケースに関連付けられている保留がオフになります。 他のホールドがコンテンツの場所 (訴訟ホールド、コア電子情報開示の保持、または別の高度な電子情報開示ケースからの保留など) に設定されている場合でも、その保持は保持されます。

- ケースは、Microsoft 365 コンプライアンスセンターの [電子情報開示] ページに表示されたままになっています。 クローズしたケースの詳細、保持、検索、メンバーは保持されます。

- クローズされた case を編集できます。 たとえば、メンバーを追加または削除したり、検索を作成したり、検索結果をエクスポートしたり、高度な電子情報開示で分析のために検索結果を準備したりできます。 アクティブなケースとクローズケースの主な違いは、ケースがクローズされたときに保留がオフになっていることです。

ケースを閉じるには、次のようにします。

1. [**高度な電子情報開示**] ページで、クローズするケースを選択します。

2. [**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。

3. [ **Case を閉じる**] をクリックします。

   決算プロセスが完了するまでに最大60分かかる場合があります。

## <a name="reopen-a-closed-case"></a>クローズしたケースを再度開く

高度な電子情報開示ケースを再度開くと、ケースが閉じられたときに行われていた保留リストは自動的に再開されません。 ケースを再度開いた後、[**保留**] タブに移動し、前のホールドをオンにする必要があります。 保留リストを有効にするには、それを選択して、フライアウトページを表示した後、**状態**の切り替えを **[オン**] に設定します。

クローズしたケースを再度開くには:

1. [**高度な電子情報開示**] ページで、再開するケースを選択します。

2. [**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。

3. [再**オープンケース**] をクリックします。

   再起動プロセスが完了するまでに最大60分かかる場合があります。

## <a name="delete-a-case"></a>ケースを削除する

アクティブおよびクローズされた上級電子情報開示ケースの両方を削除できます。 ケースを削除すると、保管担当者、通信、検索、レビューセット、エクスポートジョブのリストなど、ケースに関連付けられているすべてのコンポーネントが削除されます。 ケースは、Microsoft 365 コンプライアンスセンターの **[高度な電子情報開示**] ページのケースのリストから削除されています。 削除したケースを回復したり、再度開くことはできません。

> [!NOTE]
> データ流出のシナリオでは、レビューセット内のアイテムを削除する唯一の方法は、高度な電子情報開示ケースを削除することです。 他の「検索と削除」の方法では、レビューセットからアイテムが削除されることはありません。

ケース (アクティブかクローズか) を削除するには、まず、ケースに関連付けられている*すべて*の保留リストを削除する必要があります。 これには、状態が**Off**のホールドの削除が含まれます。

ケースに関連付けられている保留リストを削除するには:

1. 削除するアドバンスド電子情報開示ケースの [**保留**] タブに移動します。

2. 削除するホールドをクリックします。

3. [フライアウト] ページで、[**ホールドの削除**] をクリックします。

ケースを削除するには:

1. [**高度な電子情報開示**] ページで、削除するケースを選択します。

2. [**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。

3. [ **Case の削除**] をクリックします。
