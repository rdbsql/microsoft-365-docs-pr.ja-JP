---
title: Microsoft Threat Protection の高度な捜索のベスト プラクティス
description: 高度な検索を使用する場合に、迅速かつ効率的で、エラーのない脅威検索クエリを作成する方法について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、検索、クエリ、テレメトリ、カスタム検出、スキーマkusto、タイムアウト回避、コマンド ライン、プロセス ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ceb8679ccdd5c1fb41772a8b48d9474665922f39
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911306"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="d7d66-104">高度な検索クエリのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d7d66-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="d7d66-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d7d66-105">**Applies to:**</span></span>
- <span data-ttu-id="d7d66-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d7d66-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="d7d66-107">クエリのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="d7d66-107">Optimize query performance</span></span>
<span data-ttu-id="d7d66-108">次の推奨事項を適用すると、複雑なクエリを実行する際に結果をすばやく表示し、タイムアウトを回避することができます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="d7d66-109">新しいクエリを試行するときは、結果セットが大きくなり過ぎないよう、常に `limit` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="d7d66-110">`count` を使用して結果セットのサイズを最初に判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="d7d66-111">最初に時間フィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-111">Use time filters first.</span></span> <span data-ttu-id="d7d66-112">クエリを偶数の日数に制限するのが理想です。</span><span class="sxs-lookup"><span data-stu-id="d7d66-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="d7d66-113">時間フィルターの適用直後に、ほとんどのデータがクエリの開始時に除外されるようなフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="d7d66-114">完全なトークンを検索する場合の演算子として、`contains` ではなく `has` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="d7d66-115">すべての列に対して全文検索を実行するのではなく、特定の列を検索します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="d7d66-116">テーブルを結合するときは、最初は行数が少ないテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="d7d66-117">`project` は、結合したテーブルの必要な列に対してのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="d7d66-118">クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7d66-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="d7d66-119">クエリのヒントと落とし穴</span><span class="sxs-lookup"><span data-stu-id="d7d66-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="d7d66-120">プロセス ID を使用するクエリ</span><span class="sxs-lookup"><span data-stu-id="d7d66-120">Queries with process IDs</span></span>
<span data-ttu-id="d7d66-121">Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="d7d66-122">そのため、それ単体では特定のプロセスの一意の識別子として機能しません。</span><span class="sxs-lookup"><span data-stu-id="d7d66-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="d7d66-123">特定のコンピューター上のプロセスの一意の識別子を取得するには、プロセス ID をプロセスの作成日時と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="d7d66-124">プロセスに関するデータを結合または集計する際は、コンピューターの識別子の列 (`MachineId` または `ComputerName`)、プロセス ID (`ProcessId` または `InitiatingProcessId`)、およびプロセスの作成日時 (`ProcessCreationTime` または `InitiatingProcessCreationTime`) を含めます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-124">When you join or summarize data around processes, include columns for the machine identifier (either `MachineId` or `ComputerName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="d7d66-125">次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="d7d66-126">クエリ例:</span><span class="sxs-lookup"><span data-stu-id="d7d66-126">Example query:</span></span>
```
NetworkCommunicationEvents
| where RemotePort == 445 and EventTime > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by ComputerName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="d7d66-127">このクエリでは `InitiatingProcessId` と `InitiatingProcessCreationTime` の両方を使用して集計が行われるため、同一のプロセス ID を持つ複数のプロセスを混ぜることなく単一のプロセスのみがクエリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="d7d66-128">コマンド ラインを使用したクエリ</span><span class="sxs-lookup"><span data-stu-id="d7d66-128">Queries with command lines</span></span>

<span data-ttu-id="d7d66-129">さまざまなコマンド ラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-129">Command lines can vary.</span></span> <span data-ttu-id="d7d66-130">該当する場合は、ファイル名をフィルター処理し、あいまい一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="d7d66-131">タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="d7d66-132">たとえば、攻撃者が画像ファイルを参照する際に、パスを使用する場合、パスを使用しない場合、ファイル拡張子を使用しない場合、環境変数を使用する場合、または引用符を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7d66-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="d7d66-133">また、攻撃者はパラメーターの順序を変更したり、複数の引用符やスペースを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d7d66-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="d7d66-134">コマンドラインを使用してより強力なクエリを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="d7d66-135">コマンド ライン フィールドを使用してフィルター処理をするのではなく、filename フィールドを一致させることにより既知のプロセス (*net.exe* または *psexec.exe*) を特定します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="d7d66-136">コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d7d66-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="d7d66-137">代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="d7d66-138">大文字と小文字を区別しない一致を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-138">Use case insensitive matches.</span></span> <span data-ttu-id="d7d66-139">たとえば、`==`、`in`、`contains_cs` の代わりに `=~`、`in~`、`contains` を使用します。 </span><span class="sxs-lookup"><span data-stu-id="d7d66-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="d7d66-140">DOS コマンドラインの難読化手法に対処するには、引用符を削除し、コンマをスペースで置き換え、連続する複数のスペースをスペース 1 つで置き換えることを検討します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="d7d66-141">他の方法を使用しないと対処することが難しいより複雑な DOS 難読化手法がありますが、上記の対処法は、最も一般的な手法に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="d7d66-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="d7d66-142">以下の例では、Windows Defender ファイアウォール サービスを停止させる *net.exe* というファイルを検索するクエリを作成するためのさまざまな方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7d66-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```
// Non-durable query - do not use
ProcessCreationEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
ProcessCreationEvents
| where EventTime > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
ProcessCreationEvents
| where EventTime > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="d7d66-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7d66-143">Related topics</span></span>
- [<span data-ttu-id="d7d66-144">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="d7d66-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d7d66-145">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d7d66-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d7d66-146">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="d7d66-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d7d66-147">デバイスとメール全体で脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="d7d66-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d7d66-148">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d7d66-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)