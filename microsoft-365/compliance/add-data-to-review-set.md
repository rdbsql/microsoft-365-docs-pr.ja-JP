---
title: 検索結果をレビュー セットに追加する
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
ms.custom:
- seo-marvel-apr2020
description: 高度な電子情報開示ケースのレビューセットに検索結果またはこれらの検索結果のサンプルを追加する方法について説明します。
ms.openlocfilehash: 5e0cdb12a34b3b69c41546e6fcb356ed905189dd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034671"
---
# <a name="add-search-results-to-a-review-set"></a>検索結果をレビュー セットに追加する

検索結果に問題がなければ、検索結果を確認して分析する準備ができたら、それらをレビューセットに追加することができます。 元のデータをレビューセットにコピーすると、テーマの検出、ほぼ重複した検出、電子メールスレッドの識別などの高度な分析ツールを提供することにより、レビューと分析のプロセスも容易になります。 Microsoft 以外の365データソースのデータをレビューセットに追加して、Microsoft 365 から収集したデータに加えて、そのデータを確認できるようにすることもできます。 

検索結果をレビューセットに追加すると (ケースのレビューセットが [**レビューセット**] タブに一覧表示されます)、次のことが起こります。

- 検索が再度実行されます。 つまり、レビューセットにコピーされる実際の検索結果は、検索が最後に実行されたときに返された推定結果とは異なる場合があります。

- 検索結果内のすべてのアイテムは、live サービスの元のデータソースからコピーされ、Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所にコピーされます。

- すべてのアイテム (コンテンツとメタデータを含む) が再インデックス化され、ケースデータの確認時にレビューセット内のすべてのデータが完全に検索可能になります。 ケース調査時にレビューセット内のデータを検索するときに、データのインデックスを完全検索と高速検索で再インデックス化します。

レビューセットにデータを追加するには、[**検索**] タブで検索をクリックしてから、ポップアップページの [**レビューセットに結果を追加**する] をクリックします。

![レビューセットへのデータの追加](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

既存のレビューセットに追加したり、新しいレビューセットを作成したりすることができます。  新しいレビューセットにを追加する場合は、名前を指定して [**追加**] をクリックします。

![レビューセットを選択する](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

レビューセットへのデータの追加は、長時間実行されるプロセスです。 このプロセスには、Microsoft 365 の元のデータソースからアイテムを収集する (たとえば、メールボックスやサイトから) アイテムを Azure の保存場所にコピーする (このコピープロセスは、*取り込み*とも呼ばれます) ので、アイテムのインデックスを作成し直します。 [**ジョブ**] タブまたは [**検索**] タブで進行状況を追跡するには、[[**レビューするデータを確認セットに追加しまし**た] 列の状態を監視します。 レビューセット処理が完了した後で、ケースの [**検査セット**] タブをクリックし、[レビュー] セットをクリックして、レビューセットのデータのフィルター、確認、タグ付け、エクスポートのプロセスを開始します。

## <a name="add-a-sample-to-a-review-set"></a>レビューセットにサンプルを追加する

すべてをレビューセットに追加する前に、検索結果をより詳細に検証する場合は、すべてを追加するのではなく、検索結果のサンプルをレビューセットに追加できます。

サンプルをレビューセットに追加するには、[**検索**] タブで検索をクリックして、フライアウトページの [**サンプル**] をクリックします。 [**サンプリングパラメーター** ] ページで、次のいずれかのオプションを選択します。

- [**信頼度レベル%** と**信頼区間%** ]-レビューセットに追加されるアイテムは、設定した統計パラメーターによって決まります。 通常、結果のサンプリング時に信頼度と間隔を使用する場合は、ドロップダウンボックスで指定します。 それ以外の場合は、既定の設定を使用します。

- **ランダムサンプル%** -レビューセットに追加されるアイテムは、検索によって返されるアイテムの総数に対する、指定されたパーセンテージのランダムな選択に基づいています。

前のオプションの1つを選択して構成した後、そのサンプルを追加するレビューセットを選択し、[**送信**] をクリックします。 この場合も、[**ジョブ**] タブまたは [**検索**] タブで進捗状況を追跡するには、[[**レビューするデータをレビューセットに追加しまし**た] 列の状態を監視します。

## <a name="optical-character-recognition"></a>光学式文字認識

検索結果をレビューセットに追加すると、Advanced eDiscovery の光学式文字認識 (OCR) 機能によって画像からテキストが自動的に抽出されます。また、画像テキストには、校閲セットに追加されるデータが含まれています。 抽出されたテキストは、校閲セットの選択したイメージファイルのテキストビューアーに表示できます。 これにより、画像内のテキストに対してさらにレビューと分析を行うことができます。 OCR は、ルースファイル、電子メールの添付ファイル、および埋め込み画像に対してサポートされています。 OCR でサポートされている画像ファイル形式の一覧については、「 [Advanced eDiscovery でサポートされるファイルの種類](supported-filetypes-ediscovery20.md#image)」を参照してください。

詳細な電子情報開示で作成するケースごとに OCR 機能を有効にする必要があります。 詳細については、「 [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)」を参照してください。
