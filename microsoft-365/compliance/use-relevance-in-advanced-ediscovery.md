---
title: Office 365 の詳細な電子情報開示の関連モジュールを使用する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 'Office 365 Advanced eDiscovery の関連性モジュールについて説明します。これには、ワークフロー、ガイドライン、トレーニングとファイルレビューの手順が含まれます。  '
ms.openlocfilehash: f5b585008dca58f95b0f3b932b2ee4b82a1ae731
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37087073"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a>Office 365 の詳細な電子情報開示の関連モジュールを使用する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
詳細な電子情報開示では、関連性に関するトレーニングと、ケースに関連するファイルのレビューが関連モジュールに含まれています。 関連性ワークフローが表示され、次のように説明されています。
  
![関連性のワークフロー](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **評価と追跡のサイクル**:
    
  - **評価**: Advanced eDiscovery は、無作為なファイルのサンプルに基づく事前評価を有効にし、この評価を使用して、予測コーディングプロセスのパフォーマンスを判断するために決定を適用します。 
    
  - **追跡**: Advanced eDiscovery は、プロセスの統計的な有効性を監視しながら、評価の一時的な結果を計算して表示します。 
    
- **トレーニングと追跡のサイクル**:
    
  - **タグ**: 上級電子情報開示では、専門家による個々のファイルの反復的なレビューとタグ付けに基づいて、各問題に固有の関連性基準を学習します。
    
  - **追跡**: 高度な電子情報開示は、プロセスの統計的な有効性を監視しながら、関連性トレーニングの一時的な結果を計算して表示します。 
    
- **バッチ計算**: 高度な電子情報開示は、累積および学習した関連性の条件を取得し、ファイルコレクション全体に適用して、各ファイルの関連性スコアを生成します。
    
- **決定**: Advanced eDiscovery は、バッチ計算後にケース全体に適用される分析の結果を表示し、ドキュメントレビューの決定に使用するデータを表示します。
    
- **テスト**: 高度な電子情報開示の結果は、高度な電子情報開示処理の有効性と効果を確認するためにテストできます。
    
## <a name="guidelines-for-relevance-training-and-review"></a>関連性のトレーニングとレビューに関するガイドライン

関連のトレーニングとレビューのガイドラインの概要を次に示します。
  
- **エラーと不整合**: トレーニング中にタグ付けエラーが発生した場合は、以前のファイルサンプルに戻って修正してください。 修正するエラーが多すぎる場合や、ケースまたは問題の新しいパースペクティブがある場合は、管理者が関連性の条件を再定義して、関連性トレーニングを再開する必要があります。
    
- **タグ付けとトレーニング**: 
    
  - ファイルは、コンテンツのみに基づいてタグ付けする必要があります。 保管担当者、日付、ファイルパスなどのメタデータは考慮しません。 
    
  - ファイルにタグ付けするときに、テキストに日付範囲が表示されないようにします。
    
  - ファイルへのタグ付け時に埋め込まれた画像を考慮しません。
    
  - タグ付けの際に**書式付きのテキストビュー**アイコンを使用してファイルを表示する場合は、テキストの書式設定を考慮しません。 たとえば、取り消し線を使用して表示された単語 (削除を示す水平線) は、解析されたテキストの一部としても関連性があると見なされます。 
    
  - (ケースマネージャーまたは管理者が設定した) 関連性に適用されたテキストは、[関連性] のテキストビューに表示されているファイルコンテンツから削除されます。 関連性トレーニングが既に開始された後に、Ignore text の値が定義されていた場合、新しい無視されたテキストは、定義された時点から作成されたサンプルファイルに適用されます。 ファイル分析のパフォーマンスが低下する可能性があるため、[テキストを無視する] 機能は慎重に使用する必要があります。
    
  - [**タグをスキップ**する] オプションは必要な場合にのみ使用してください。 上級電子情報開示は、スキップされたファイルに基づいてトレーニングを行いません。 評価では、ファイルが関連しているかどうかを判断するのが難しい場合は、 **Skip**を選択するのではなく、可能な限り、関連性のある (R) または関連していない (NR) を使用することをお勧めします。 高度な電子情報開示でトレーニングを評価すると、これらの種類のファイルがどのように処理されたかを確認できます。
    
  - 抽出されたテキストが非常に小さいファイルでも、可能な場合は "Skip" ではなく、R/NR としてのトレーニングでタグ付けする必要があります。 
    
  - タグ付けは、ファイルが読みやすく、R/NR としてタグ付けできる限り、分類子に影響を与える可能性があります。
    
  - [**タグ**] タブの表示されているサンプルファイルの一覧のファイルシーケンス番号を使用すると、ユーザーは、表示されている元のファイルの順序に戻すことができます。 
    
  - すべてのサンプルに戻って、評価およびトレーニングセットファイルのタグ付けを変更できます。 変更は、次のサンプルを作成するときに適用されます。
    
  - PDF 形式でスキャンした Excel ファイルは、ファイルにタグ付けするときに、ネイティブの Excel ファイルと同じように処理されます。
    
  - ファイルの関連性のタグ付けに関して疑わしい場合は、専門家に相談してください。 関連性トレーニング中に誤ったタグ付けを行うと、プロセスの後期に時間が失われることがあり、結果全体の品質に悪影響を及ぼす可能性があります。
    
  - キーワードリストで定義されたキーワードは、タグ付け中にユーザーが関連ファイルを識別するのに役立つ色で表示されます。
    
- **バッチ計算**: 専門家による R/NR としてタグ付けされたファイルのスコアは0または100のいずれかとなります。 これは、バッチ計算前に行われるタグ付けに適用されます。 上級者が一括計算した後に問題をアイドルに切り替えて、この問題のタグ付けを続行した場合、新しくタグ付けされたスコアは100/0 にならず、元のスコアになります。
    
- **問題とサンプリングモード**: 問題が発生した場合は、その作業が完了し、問題が取り消されたとき、または他のユーザーが問題に対処しているときに、通常はオフになっています。
    
## <a name="steps-in-relevance-training"></a>関連性トレーニングの手順

[**関連性\>の追跡**] タブで、Advanced eDiscovery は処理を進める方法に関する推奨事項を提供し、次の手順を実行します。 関連トレーニングプロセスで以下の各手順を実行する場合は、次に示す影響について説明します。 
  
- タグ付け/続行のタグ付け: サンプル内のファイルと問題について、エキスパートによってファイルのレビューと関連性のタグ付けが実行されます。
    
  - 暗黙: 既存のサンプルは、タグ付けする必要があります。
    
- 評価/続行評価: ケース上の問題の関連性と、現在のケースに対してインポートされたファイルの作成の関連性を事前に検証できるようにします。
    
  - 暗示: より多くの評価が必要または推奨されています。
    
- トレーニング/続行トレーニング: 上級電子情報開示がファイルのサンプルにタグ付けされているエキスパートから学習し、各ケースのコンテキスト内で各問題に関連する関連性基準を特定する機能を取得するプロセス。
    
  - 意味: 問題により多くのトレーニングが必要になります。次のサンプルを作成し、タグを付ける必要があります。 
    
- バッチ計算: 高度な電子情報開示がトレーニング段階で取得したナレッジを取得し、ファイルの作成全体に適用する関連性プロセス。 関連するファイルグループ内のすべてのファイルに関連性があることが評価され、関連性スコアが割り当てられます。
    
  - 意味: 問題が安定しており、バッチ計算を実行できます。
    
- キャッチアップ: 関連性は、エキスパートが、ローリングロードシナリオで追加のファイルロードから選択されたファイルのサンプルをレビューし、タグ付けするタイミングを示します。
    
  - 暗黙: 新しい読み込みが追加され、作業を続行するにはキャッチアップが必要です。
    
- タグの不整合: プロセスは、高度な電子情報開示アルゴリズムを使用して、分析に悪影響を及ぼす可能性のあるファイルのタグ付けプロセスの不整合を識別します。
    
  - 意味: 次のサンプルには、前のサンプルでタグ付けされたファイルが含まれており、タグ付けをやり直す必要があります。
    
- Update クラシファイア: ユーザーがタグ付けまたはシード変更を適用できるようにします。
    
  - 暗黙: 別の関連性サンプルを手動で実行しなくても、タグ付けとシードによる変更を適用できます。
    
- 保留中: 関連トレーニングプロセスが完了します。
    
  - 意味: この時点では、関連性トレーニングは必要ありません。
    
詳細な電子情報開示では、さまざまな段階で推奨される次の手順を使用してプロセスを進めることができますが、タブとページ間を移動したり、個別のケース、問題、またはの状況に関係する状況に対処するための選択を行ったりすることもできます。ドキュメントレビュープロセス。 
  
高度な電子情報開示の次のステップ処理の選択を承諾または無効にすることができます。 次の推奨手順以外の手順を実行する場合は、ダイアログボックスの展開された問題の表示で**次の手順**をクリックし、次の手順の横にある [**変更**] ボタンをクリックして、別の [次の手順] オプションを選択します。 
  
> [!NOTE]
> 一部のオプションは、プロセスのその時点で使用することがサポートされていないため、ロックを解除した後も無効になることがあります。 
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[関連性の評価について](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けと評価](tagging-and-assessment-in-advanced-ediscovery.md)
  
[タグ付けと関連性トレーニング](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[関連性分析の追跡](track-relevance-analysis-in-advanced-ediscovery.md)
  
[結果に基づいて決定する](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[関連性分析のテスト](test-relevance-analysis-in-advanced-ediscovery.md)
