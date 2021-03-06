---
title: コンテンツ検索を再試行してコンテンツの場所のエラーを解決する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 調査中に、[再試行] ボタンを使用して、コンテンツの場所にエラーがあるコンテンツ検索を解決できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b2d26cd51c30f2c273abb59199cf4a89f5b7a37
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034631"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>コンテンツ検索を再試行してコンテンツの場所のエラーを解決する

セキュリティ/コンプライアンスセンターでコンテンツ検索を使用して多数のメールボックスを検索すると、次のような検索エラーが表示されることがあります。

```text
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

これらのエラー (エラーコード CS001-002、CS003-002、CS008-009、CS012-002、および CS0XX-0XX の他のエラー) は、コンテンツ検索で特定のコンテンツの場所を検索できなかったことを示しています。この例では、2つのメールボックスが検索されませんでした。 これらのエラーは、コンテンツ検索の [状態の詳細] ポップアップページに表示されます。

## <a name="cause-of-content-location-errors"></a>コンテンツの場所にエラーが発生する原因

多数のメールボックスを検索する場合、検索は Microsoft データセンター内の数千人のサーバーに分散されます。 いつでも、特定のサーバーが再起動状態になったり、冗長コピーにフェールオーバーするプロセスであったりする可能性があります。 どちらの場合も、データを取得するためのコンテンツ検索要求がタイムアウトになります。 前の例では、失敗したメールボックスのエラーは、検索がタイムアウトした結果です。

## <a name="resolving-content-location-errors"></a>コンテンツの場所のエラーを解決する

検索を再起動すると、複数のサーバーで同様のエラーが発生することがよくあります。 検索を再起動する代わりに、検索結果ページの上部に表示される [**再試行**] ボタンをクリックします。

![[再試行] ボタンをクリックしてコンテンツの場所のエラーを解決する](../media/retrycontentsearch3.png)

これにより、失敗したメールボックスに対してのみ検索を再試行します。 検索を再試行すると、正常に返されたその他の結果は保持されます。

## <a name="tips-to-avoid-content-location-errors"></a>コンテンツの場所エラーを回避するためのヒント

ここでは、コンテンツの場所に関するエラーの原因と、多数のメールボックスを検索するときに回避するためのヒントについて説明します。

- 検索されているメールボックスが、ユーザーのアクティビティのためにビジー状態である可能性があります。 この場合、検索サービスでは、メールボックスが使用できなくなるように調整されることがあります。 この問題を回避するには、勤務時間外に検索を実行するようにします。

- 検索クエリがメールボックスから大量のコンテンツを取得している可能性があります。 可能であれば、キーワード、日付の範囲、および検索条件を使用して、検索範囲を絞るようにしてください。

- キーワード[リスト](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)を使用して検索クエリを作成するときに、キーワードやキーワード語句が多すぎます。 キーワードリストを使用する検索クエリを実行すると、基本的には、統計が生成されるように、キーワードリストの各行に対して個別に検索を実行します。 検索クエリでキーワードリストを使用している場合は、キーワードリストの行数を最小にするか、数字のキーワードを小さなリストに分割して、各キーワードリストに対して異なる検索を作成します。

  > [!NOTE]
  > 大規模なキーワード リストによって生じる問題を軽減するため、検索クエリのキーワード リストの行は最大 20 行に設定されています。

- 同じメールボックスで同時に実行されている検索が多すぎます。 可能であれば、1つのメールボックスで一度に1つずつ検索を実行します。

- 単一の検索で大量のメールボックスを検索しています。 非常に多くのメールボックスを検索すると、コンテンツの場所エラーが発生する可能性が高くなります。 可能であれば、各検索で組織内のメールボックスのサブセットが含まれるように、複数の検索を実行してみてください。

- メールボックスで必要なメンテナンスが実行されている。 この原因はほとんどありませんが、コンテンツの場所エラーを受け取ってからしばらく待ってから、検索を再試行してください。
