---
title: 検索と分析の設定を構成する-電子情報開示
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
ms.custom: seo-marvel-mar2020
description: ケースのすべてのレビューセットに適用される高度な電子情報開示設定を構成します。 これには、分析と OCR の設定が含まれます。
ms.openlocfilehash: eb934146b065454b54d797e47f7a643b95be546d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033677"
---
# <a name="configure-search-and-analytics-settings"></a>検索と分析の設定を構成する

次の機能を制御するために、高度な電子情報開示ケースごとに設定を構成できます。

- ほぼ重複、電子メールスレッド

- テーマ

- 自動生成されたレビューセットクエリ

- テキストを無視する

- 光学式文字認識

ケースの検索と分析の設定を構成するには:

1. [**高度な電子情報開示**] ページで、ケースを選択します。

2. [**設定**] タブの [**検索 & 分析**] で、[**選択**] をクリックします。

   [ケースの設定] ページが表示されます。 これらの設定は、ケースのすべてのレビューセットに適用されます。

   ![高度な電子情報開示ケースの分析と検索の設定を構成する](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>ほぼ重複、電子メールスレッド

このセクションでは、重複データ検出、重複の検出、電子メールのスレッド処理のパラメーターを設定できます。 詳細については、「[重複の検出](near-duplicates.md)と[電子メールのスレッド処理](email-threading.md)」を参照してください。

- **重複の近辺/電子メールスレッド:** オンにすると、分析セット内のデータに対して分析を実行するときに、重複の検出、重複の検出、電子メールスレッドがワークフローの一部として含まれます。

- **ドキュメントと電子メールの類似性のしきい値:** 2つのドキュメントの類似性レベルがしきい値を超えている場合、両方のドキュメントは同じほぼ重複セットに配置されます。

- **最小/最大単語数:** これらの設定により、重複した部分と電子メールのスレッド分析が、少なくとも単語の最小数が少なく、最大で単語数であるドキュメントに対してのみ実行されることを指定します。

## <a name="themes"></a>テーマ

このセクションでは、テーマのパラメーターを設定できます。 詳細については、「 [Themes](themes-in-advanced-ediscovery.md)」を参照してください。

- **テーマ:** オンにすると、レビューセット内のデータに対して分析を実行するときに、テーマのクラスタリングがワークフローの一部として実行されます。

- **テーマの最大数:** レビューセット内のデータに対して分析を実行するときに生成できるテーマの最大数を指定します。

- **テーマに数字を含める:** 有効にすると、テーマを生成するときに、テーマを識別する番号が含まれます。 

- **テーマの最大数を動的に調整します。** 特定の状況では、必要な数のテーマを作成するのに十分な数のドキュメントがレビューセットにないことがあります。 この設定が有効になっている場合、高度な電子情報開示では、テーマの最大数を適用するのではなく、テーマの最大数を動的に調整します。

## <a name="review-set-query"></a>レビューセットクエリ

[**分析後に保存された検索の確認を自動的に作成**する] チェックボックスをオンにすると、[上級電子情報開示] Autogenerates**に対して**という名前のレビュー設定クエリが生成されます。 

![のレビュー用に自動生成されたクエリ](../media/AeDForReviewQuery.png)

このクエリは、基本的に、重複アイテムをレビューセットから除外します。 これにより、レビューセット内の一意のアイテムを確認できます。 このクエリは、ケースのレビューセットに対して分析を実行した場合にのみ作成されます。 詳細については、「レビュー[セットのクエリ](review-set-search.md)の概要」を参照してください。

## <a name="ignore-text"></a>テキストを無視する

特定のテキストによっては、電子メールの内容に関係なく、電子メールメッセージに追加される長期の免責事項など、分析の品質を低下させる場合があります。 無視する必要があるテキストがわかっている場合は、テキスト文字列と分析機能 (重複、電子メールスレッド、テーマ、および関連性) を指定して分析から除外することができます。 正規表現 (RegEx) を無視されるテキストとして使用することもサポートされています。 

## <a name="optical-character-recognition-ocr"></a>光学式文字認識 (OCR)

この設定をオンにすると、イメージのテキストをレビュー、検索、タグ付け、および分析できるように、OCR がイメージファイルに対して実行されます。 抽出されたテキストは、校閲セットの選択したイメージファイルのテキストビューアーに表示できます。 詳細については、以下を参照してください。

- [検索結果をレビュー セットに追加する](add-data-to-review-set.md#optical-character-recognition)

- [サポートされているイメージファイルの種類](supported-filetypes-ediscovery20.md#image)
