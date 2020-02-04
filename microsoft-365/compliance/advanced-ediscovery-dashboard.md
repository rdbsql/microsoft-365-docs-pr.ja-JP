---
title: レビューセットの高度な電子情報開示ダッシュボード
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
description: ''
ms.openlocfilehash: 127e2c9a04977bf6e902a1ce669fa9e4248e3ef2
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662243"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a><span data-ttu-id="22874-102">レビューセットの高度な電子情報開示ダッシュボード (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="22874-102">Advanced eDiscovery dashboard for review sets (preview)</span></span>

<span data-ttu-id="22874-103">高度な電子情報開示では、確認が必要な大量のドキュメントや電子メールメッセージがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="22874-103">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="22874-104">レビュープロセスを開始する前に、レビュー戦略の開発に役立つ傾向または主要な統計情報を特定するために、コーパスをすばやく分析することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22874-104">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="22874-105">これを行うには、詳細な電子情報開示ダッシュボードをレビューセットに使用して、コーパスを迅速に分析できます。</span><span class="sxs-lookup"><span data-stu-id="22874-105">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="22874-106">手順 1: 校閲セットダッシュボードにウィジェットを作成する</span><span class="sxs-lookup"><span data-stu-id="22874-106">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="22874-107">[セキュリティ & コンプライアンスセンター] で、 **[電子情報開示 > Advanced ediscovery** ] に移動して、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="22874-107">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="22874-108">既存のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="22874-108">Select an existing case.</span></span>
  
3. <span data-ttu-id="22874-109">[**校閲セット**] タブをクリックし、レビューセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="22874-109">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="22874-110">個々の**結果**ドロップダウンリストで、[**検索プロファイルビュー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22874-110">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](media/dashboardpivot.png)

   <span data-ttu-id="22874-112">[**検索プロファイルビュー** ] ページが表示されます。このページを初めて表示するときに、3つの既定のウィジェットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22874-112">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![ダッシュボード](media/dashboardonly.png)
  
5. <span data-ttu-id="22874-114">**新しいウィジェット**をクリックし、次のいずれかの項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="22874-114">Click the **New  widget** and then select one of the following items:</span></span>

   ![新しいウィジェットのドロップダウンリスト](media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="22874-116">**ライブラリから選択:** ウィジェットの既定のライブラリを表示します。</span><span class="sxs-lookup"><span data-stu-id="22874-116">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="22874-117">ウィジェットをクリックし、[**追加**] をクリックして、[**検索プロファイルの表示**] ページのウィジェットに追加します。</span><span class="sxs-lookup"><span data-stu-id="22874-117">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="22874-118">**カスタムウィジェットの作成:** カスタムウィジェットのセットアップに使用できるフライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22874-118">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="22874-119">カスタムウィジェットを作成するには、[**ウィジェットの追加**] ページで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="22874-119">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![ウィジェットの作成](media/addwidget.png)

    <span data-ttu-id="22874-121">a. </span><span class="sxs-lookup"><span data-stu-id="22874-121">a.</span></span> <span data-ttu-id="22874-122">ウィジェットの名前を入力します。ウィジェットのタイトルバーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="22874-122">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="22874-123">ウィジェットの名前付けは必須ですが、ウィジェットのデータを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="22874-123">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="22874-124">b. </span><span class="sxs-lookup"><span data-stu-id="22874-124">b.</span></span> <span data-ttu-id="22874-125">[選択した**ピボット**ドロップダウンリストで、ウィジェットデータに使用されるプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="22874-125">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="22874-126">このリストのアイテムは、レビューセット内のアイテムの検索可能なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="22874-126">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="22874-127">これらのプロパティの詳細については、「 [Advanced eDiscovery のドキュメントメタデータフィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22874-127">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="22874-128">このウィジェットのピボットオプションは、このトピックの「検索可能な**フィールド名**」列に記載されています。</span><span class="sxs-lookup"><span data-stu-id="22874-128">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="22874-129">c.</span><span class="sxs-lookup"><span data-stu-id="22874-129">c.</span></span> <span data-ttu-id="22874-130">グラフの種類を選択して、選択したピボットプロパティのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="22874-130">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="22874-131">[**追加**] をクリックしてカスタムウィジェットを作成し、**検索プロファイルビュー**ページに表示します。</span><span class="sxs-lookup"><span data-stu-id="22874-131">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="22874-132">手順 2: レビューセット検索クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="22874-132">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="22874-133">ウィジェットタイトルバーの [ **...** ] をクリックし、[**条件の適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22874-133">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![ダッシュボード](media/searchprofilehome.png)

2. <span data-ttu-id="22874-135">ポップアップページで、ウィジェットキーまたはウィジェットグラフの要素をクリックして、フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="22874-135">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![CreateFilter](media/applyconditionfilter.png)

3. <span data-ttu-id="22874-137">他のウィジェットの場合は、手順1-2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="22874-137">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="22874-138">完了したら、[**クエリとして保存**] をクリックして、検証セットの新しい検索クエリとして条件を保存します。</span><span class="sxs-lookup"><span data-stu-id="22874-138">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![Query](media/savequery.png)

5. <span data-ttu-id="22874-140">[**検索プロファイル] ビュー**を閉じて、検索結果ビューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="22874-140">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="22874-141">任意のビジュアルフィルターを作成した場合、結果のクエリが表示される検索結果に適用され、手順4で保存した検索クエリが [**保存さ**れたクエリ] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="22874-141">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="22874-142">レビューセットクエリの詳細については、「[レビューセット内のデータを照会する](review-set-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22874-142">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>