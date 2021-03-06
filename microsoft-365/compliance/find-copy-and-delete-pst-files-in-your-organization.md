---
title: PST コレクション ツールを使用して、PST ファイルの検索、コピー、および を削除をする
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
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Microsoft PST コレクションツールを使用して、組織のネットワークを検索し、組織全体に散在している PST ファイルのインベントリを取得します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4f1ac7b0bfe30ec2d8a11b4882a29c064d22ef78
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817716"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>PST コレクションツールを使用して、組織内の PST ファイルを検索、コピー、および削除する

> [!IMPORTANT]
> この記事に記載されている PST コレクションツールは、Microsoft の標準サポートプログラムやサービスではサポートされていません。 このツールは、あらゆる種類の保証なしで提供されます。 Microsoft は、商品性の保証および特定目的への適合性の保証を含むいかなる明示もしくは黙示の保証責任を負いません。 ツールやドキュメントの使用やパフォーマンスの問題が発生した場合は、そのリスク全体が維持されます。 イベントなしでは、Microsoft は、その作成者、また、ツールまたはドキュメントの使用または使用できない損害に関して、Microsoft が損害を受ける可能性があると判断された場合であっても、このツールの作成、運用、または配布に関与するすべての損害について、そのツールまたはドキュメントを使用していないこと、またはそのような損害に対する損害 (

Microsoft PST コレクションツールを使用して、組織のネットワークで PST ファイルを検索することができます。 このツールは、組織全体に散在している PST ファイルのインベントリを取得するのに役に立ちます。 PST ファイルを見つけたら、PST コレクションツールを使用して、それらを1か所にまとめてコピーできます。 次に Pst を1か所に配置すると、それらを Exchange Online メールボックス (または単一の Exchange Online メールボックス) にインポートできるようになります。これにより、Office 365 で豊富なコンプライアンス機能セットを適用することができます。 これには、ユーザーのアーカイブメールボックスへの Pst のインポート、電子情報開示検索ツールを使用してインポートした PST ファイル内の特定のメッセージの検索、電子情報開示の保持とアイテム保持ポリシーを使用したメッセージの保持、Exchange Online のメッセージングレコード管理機能を使用したこれらのメッセージのライフサイクルの管理が含まれます。 収集した PST ファイルが Office 365 に正常にインポートされたことを確認したら、ツールを使用して、ネットワーク上の元の場所から削除することができます。 
  
PST コレクションツールを使用して、ユーザーが新しい PST ファイルを作成したり、ネットワーク上で見つけた既存の PST ファイルを変更したりできないようにすることができます。 これらの "ブロック" 機能を使用すると、既存の PST ファイルのセットを Microsoft 365 に検索、収集、およびインポートして、組織内の PST ファイルが将来的に急増しないようにすることができます。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST コレクションツールのしくみ

PST コレクションツールを使用して、組織内の PST ファイルを検索、制御、収集、および削除するプロセスの概要を次に示します。
  
![PST コレクションツールのプロセスの概要](../media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[手順 1: ネットワーク上の pst ファイルを検索](#step-1-find-pst-files-on-your-network)** する-ツールを実行して pst ファイルを検索する場合、クライアントおよびサーバーコンピューターの Active Directory オブジェクトを含む組織単位などの場所を指定します。 特定のコンピューターまたはネットワークファイル共有を検索することもできます。 ツールを実行すると、ターゲットコンピューターに "ライトウェイト" コレクションエージェントがインストールされます。 このエージェントは、送信先のコンピューターで PST ファイルを検索し、見つかった PST ファイルに関する情報を PST コレクションツールに送り返します。 このツールは、指定した場所に見つかった PST ファイルに関する情報を含むログファイルを作成します。 これらのファイルは、後の手順でツールを実行するときに使用されます。 
    
2. **[(省略可能) 手順 2: pst ファイルへのアクセスを制御](#optional-step-2-control-access-to-pst-files)** する-このツールは、ユーザーが pst ファイルを作成または変更できないようにする設定を使用してグループポリシーオブジェクト (GPO) を作成します。 この GPO は、ドメイン内のすべてのユーザーに適用されます。 このオプションの手順により、手順1で検出された PST ファイルを "ロックダウン" して、新しい PST ファイルを作成したり、既存の PST ファイルを変更したりせずに、収集、インポート、および削除できるようにすることができます。 
    
3. **[手順 3: pst ファイルをコレクションの場所にコピー](#step-3-copy-the-pst-files-to-a-collection-location)** します。これにより、1つの場所で pst ファイルを収集することができます。これにより、手順4で Office 365 インポートサービスを使用して Exchange Online メールボックスにインポートできるようになります。 このツールを "収集" モードで実行すると、各コレクションエージェントは、エージェントがインストールされているターゲットマシンから、コレクションの場所に PST ファイルをコピーします。 
    
4. **[手順 4: pst ファイルを Office 365 にインポート](#step-4-import-the-pst-files-to-office-365)** します。 pst ファイルを1つの場所にコピーしたら、それらを Exchange Online メールボックスにインポートする準備ができました。 
    
5. **[手順 5: ネットワーク上の pst ファイルを削除](#step-5-delete-the-pst-files-found-on-your-network)** する-見つけて収集した pst ファイルを Office 365 の Exchange Online メールボックスにインポートした後、pst コレクションツールを使用して、手順1で見つかった pst ファイルを元の場所から削除できます。 

## <a name="before-you-begin"></a>はじめに

- PST コレクションツールをローカルコンピューターにダウンロードするには、次の手順を実行します。 
    
    1. [PST コレクションツールをダウンロード](https://aka.ms/pstcollectiontool)します。
    
    2. ポップアップウィンドウで **、[名前**を付けて保存] をクリックして、 \> **Save as** PSTCollectionTool.zip ファイルをローカルコンピューター上のフォルダーに保存します。 
    
    3. PSTCollectionTool.zip ファイルをローカルコンピューター上のフォルダーに抽出します。既定のフォルダー名は PSTCollectionTool です。
    
- PST コレクションツールを任意のモード (検索、ブロック、コピー、または削除) で実行するには、Active Directory ドメインのドメイン管理者グループのメンバーである必要があります。 

## <a name="step-1-find-pst-files-on-your-network"></a>手順 1: ネットワーク上の PST ファイルを検索する

最初の手順として、PST コレクションツールを実行して、組織内の PST ファイルを検索します。 このツールを使用して、次の種類の場所を検索できます。 
  
- 社内の Active Directory ドメイン内の組織単位 (Ou)。 このツールは、指定された OU に含まれるすべてのコンピューターを検索します。 
    
- クライアントおよびサーバーのコンピューター。 ツールは、指定されたコンピューターを検索します。 
    
- ネットワークファイル共有。 ツールは、指定されたネットワークファイル共有を検索します。 
    
`Locations`これらの各場所の種類に使用する構文の例については、次の表の表のパラメーターの説明を参照してください。 
  
> [!IMPORTANT]
> Pst ファイルのブロック、収集、削除など、他の操作を実行する前に、PST コレクションツールを検索モードで実行する必要があります。 
  
1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PSTCollectionTool フォルダー (または PSTCollectionTool.zip ファイルを抽出したフォルダー) に移動します。
    
3. DataCollectorMaster ディレクトリに移動します。
    
4. 指定した場所に PST ファイルを検索するには、次のコマンドを実行します。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    次の表では、DataCollectorMaster.exe コマンドを実行して PST ファイルを検索するときのパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して PST ファイルを検索できます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 値を使用し `Find` て、指定した場所に PST ファイルを検索します。 このツールは、outlook プロファイルに接続されている Outlook ファイルおよび PST ファイルで開いている PST ファイルに関する情報を検索して取得することができることに注意してください。  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |PST コレクションジョブの名前を指定します。 この同じジョブ名は、ツールを実行して PST ファイルを検索するときに、pst コレクションツールを実行して検出された PST ファイルをブロック、収集、および削除するときに使用します。 ジョブ名は、ログおよび構成ファイル名にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | PST ファイルを検索する1つまたは複数の場所を指定します。 複数の場所を指定する場合は、セミコロン (;) を使用します。個別の場所を区切ります。 このパラメーターの個々の値は二重引用符 ("") で囲むようにしてください。  <br/><br/>   以下は、検索できる場所の種類に必要な id 値の形式です。  <br/><br/>        **Ou** -識別名 (DN) を使用して ou を識別します。例えば：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> 組み込みのコンピューターコンテナー (たとえば、CN = Computers, DC = contoso, DC = com ") は、組織単位ではないため、指定することはできません。<br/> <br/> [**コンピューター** ]-DN または完全修飾ドメイン名 (FQDN) を使用して、ネットワーク上のクライアントおよびサーバーコンピューターを識別します。例えば：  <br/>  ティ`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  または  <br/>  FQDN`"FILESERVER01.contoso.com"` <br/><br/>  **ネットワークファイル共有**: UNC 名を使用してネットワークファイル共有を識別します。例えば`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |ログファイルのコピー先となるフォルダーを指定します。 フォルダーが存在しない場合は、ツールの実行時に作成されます。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |.Xml 構成ファイルのコピー先となるフォルダーを指定します。 このファイルには、ツールの実行時に見つかった各 PST ファイルに関する情報が含まれています。 このファイルは、手順3でツールを実行して検出された PST ファイルをコピーするときに使用されます。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |このオプションパラメーターは、検索操作中にスキップする場所を指定します。 特定の Ou、コンピューター、およびネットワークファイル共有を除外することができます。 たとえば、ユーザーがアクセス権を持っていない SQL server (または他の種類のアプリケーションサーバー) などのマシンを除外することができます。 除外する場所を複数指定する場合は、セミコロン (;) を使用します。個別の場所を区切ります。 このパラメーターの個々の値は二重引用符 ("") で囲むようにしてください。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |このオプションスイッチを使用すると、既存の PST コレクションジョブの検索モードでツールを実行できます。 スイッチを使用すると `ForceRestart` 、ジョブの前の検索操作からの結果が破棄され、ツールによって指定された場所が再スキャンされ、新しいログおよび構成ファイルが作成されます。  <br/> | `-ForceRestart` <br/> |
   
    各パラメーターに実際の値を使用して DataCollectorMaster.exe コマンドの構文の例を次に示します。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    コマンドを実行すると、指定した場所に PST ファイルを検索する処理の進行状況を示す詳細な状態メッセージが表示されます。 しばらくすると、最後の状態メッセージに、見つかった PST ファイルの合計数、ジョブが完了したかどうか、およびエラーがあったかどうかが表示されます。 同じ状態メッセージが .log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>検索モードで DataCollectorMaster.exe を実行した結果

PST コレクションツールを検索モードで正常に実行した後、次のファイルが作成され、and パラメーターで指定されたフォルダーに格納され `LogLocation` `ConfigurationLocation` ます。 
  
- [ ** \<JobName\> _Find_ \<DateTimeStamp\> .Log** -ログファイルには、表示された状態メッセージが含まれています。 このファイルは、パラメーターで指定されたフォルダー内に作成され `LogLocation` ます。 
    
- .Csv-csv ファイルには、検出された各 PST ファイルの行が含まれてい** \<JobName\> _Find_ \<DateTimeStamp\> **ます。 各 PST の情報には、pst ファイルが検出されたコンピューター、pst ファイルの完全なファイルパスの場所、pst ファイルの所有者、PST ファイルのサイズ (キロバイト、kb 単位) が含まれています。 このファイルは、パラメーターで指定されたフォルダー内に作成され `LogLocation` ます。 
    
    > [!TIP]
    > Excel の [オート Sum] ツールを使用して、CSV ファイルに記載されているすべての PST ファイルの合計サイズ (KB 単位) を計算します。 その後、変換ツールを使用して合計サイズをメガバイト (MB) またはギガバイト (GB) に変換できます。 
  
- ** \<JobName\> _検索_ \<DateTimeStamp\> xml** -xml ファイルには、ツールを検索モードで実行したときに使用されたパラメーター値に関する情報が含まれています。 このファイルには、検出されたすべての PST ファイルに関する情報も含まれています。 このファイル内のデータは、同じジョブに対してツールを再実行して、見つかった PST ファイルをブロック、収集、または削除するときに使用されます。 このファイルは、パラメーターで指定されたフォルダー内に作成され `ConfigurationLocation` ます。 
    
    > [!IMPORTANT]
    > このファイルの名前を変更、変更、または移動しないでください。 このツールは、同じジョブのブロック、コピー、または削除モードでツールを再実行するときに PST コレクションツールによって使用されます。 

## <a name="optional-step-2-control-access-to-pst-files"></a>オプション手順 2: PST ファイルへのアクセスを制御する

このオプションの手順により、手順1で見つかった PST ファイルを "ロックダウン" して、既知の PST ファイルのセットを収集して Office 365 にインポートできるようにします。 PST コレクションツールをブロックモードで実行すると、次の処理が行われます。 
  
- このツールは、 *PST 使用法コントロール*という名前のグループポリシーオブジェクト (GPO) を作成します。 この GPO はドメインにリンクされており、組織内のすべての認証済みユーザーに適用されます。 
    
- [PST 使用状況] コントロール GPO は、組織内のコンピューターにレジストリ設定を作成します。 使用するパラメーターに応じて、ユーザーが新しい PST ファイルを作成できないようにするレジストリ設定を作成し、ユーザーが既存の PST ファイルを変更できないようにするレジストリ設定を作成することができます。
    
> [!NOTE]
> PST ファイルへのアクセスを管理することが組織にとってより破壊的な場合は、この手順を省略して、手順3を実行して PST ファイルを中央の場所にコピーすることを検討してください。 その後、同じジョブに対して (パラメーターを使用して) 手順1を繰り返し、 `ForceRestart` pst ファイルをコレクションの場所にコピーした後に作成されたその他の pst ファイルを検索できます。 新しい PST ファイルが見つかった場合は、それらをコレクションの場所にコピーできます。 この `ForceRestart` ツールを検索モードで再実行するときにパラメーターを使用すると、ジョブに対する以前の検索操作からの結果は破棄され、ツールによって指定された場所が再スキャンされます。 

PST ファイルへのアクセスをブロックするには、次のようにします。

1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PST コレクションツールをダウンロードしたディレクトリに移動します。
    
3. 手順1で見つかった PST ファイルへのアクセスをブロックするには、次のコマンドを実行します。

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    次の表では、DataCollectorMaster.exe コマンドを実行して PST ファイルの作成と変更をブロックする場合のパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して PST ファイルを検索できます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 この値を使用し `Block` て、ユーザーが新しい pst ファイルを作成したり、既存の pst ファイルに変更を加えたりできないようにします。  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |既存の PST コレクションジョブの名前を指定します。 手順1でツールを検索モードで実行したときに使用したものと同じジョブ名を使用する必要があります。 このジョブ名は、ブロックモードでツールを実行するときに作成されるログファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |検索モードでツールを実行したときに作成された .xml 構成ファイルがフォルダーに含まれていることを指定します。 手順1でこのパラメーターに使用したのと同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |ブロック操作のログファイルがコピーされるフォルダーを指定します。 このパラメーターは省略可能です。 このファイルを含めない場合、ログファイルは PST コレクションツールをダウンロードしたフォルダーにコピーされます。 手順1の検索モードでツールを実行したときに使用したのと同じログの場所を使用して、すべてのログファイルが同じフォルダーに保存されるようにしてください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |ユーザーが PST ファイルを変更できないようにするには、このスイッチを使用します。 このスイッチを使用すると、次のレジストリエントリが作成され、 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` データ値は1に設定されます。 このレジストリ設定は、ブロックモードで PST コレクションツールを実行するときに作成される GPO によって、組織内のコンピューターに作成されます。  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |このスイッチを使用すると、ユーザーは新しい PST ファイルを作成したり、PST ファイルを Outlook にインポートしたり、Outlook から PST ファイルをエクスポートしたりすることができなくなります。 このスイッチを使用すると、次のレジストリエントリが作成され、 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` データ値は1に設定されます。 このレジストリ設定は、ブロックモードで PST コレクションツールを実行するときに作成される GPO によって、組織内のコンピューターに作成されます。  <br/> | `-BlockNewFiles` <br/> |
   
    各パラメーターに実際の値を使用して DataCollectorMaster.exe コマンドの構文の例を次に示します。

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```

    新しい PST ファイルまたは既存の PST ファイルへの変更をブロックするかどうかを確認するメッセージが表示されます。 続行することを確認し、コマンドが正常に実行されると、"PST Usage Controls" という名前の新しい GPO が作成されたことを示すメッセージが表示されます。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>手順 3: PST ファイルをコレクションの場所にコピーする

次の手順では、PST コレクションツールを実行したときに見つかった PST ファイルを検索モードでコピーします。 これにより、後で Office 365 にインポートできるように PST ファイルを1か所で収集できます。 PST ファイルをコレクションの場所にコピーする前に、必要な記憶域の容量の合計を決定することを検討してください。 これは、手順1で作成した CSV ファイルを使用して、すべての PST ファイルの合計サイズを計算することができます。
  
> [!NOTE]
> PST ファイルを Microsoft 365 にインポートして元の場所から削除した後、この手順でコピーしたコレクションの場所から PST ファイルを削除する必要がある場合があります。 
  
1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PST コレクションツールをダウンロードしたディレクトリに移動します。
    
3. 次のコマンドを実行して、PST ファイルを指定した場所にコピーします。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    次の表では、DataCollectorMaster.exe コマンドを実行して PST ファイルをコピーするときのパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して PST ファイルを検索できます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 この値を使用して、 `Collect` 検索モードでツールを実行したときに検出された PST ファイルをコピーします。 このツールは、Outlook で開いている PST ファイルをコピーして、Outlook プロファイルに接続された PST ファイルをコピーできることに注意してください。  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |既存の PST コレクションジョブの名前を指定します。 手順1でツールを検索モードで実行したときに使用したものと同じジョブ名を使用する必要があります。 このジョブ名は、収集モードでツールを実行するときに作成されるログファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |手順1でパラメーターに使用したのと同じ値を使用し `Locations` ます。 ツールを再実行して、手順5で元の場所から PST ファイルを削除する場合は、このツールを Collect モードで実行するときに、このパラメーターを含めます。  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |検索モードでツールを実行したときに作成された .xml 構成ファイルが格納されているフォルダーを指定します。 手順1でこのパラメーターに使用したのと同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |PST ファイルのコピー先となるコレクションの場所を指定します。 ファイルをファイルサーバー、ネットワークファイル共有、またはハードドライブにコピーすることができます。 この場所は、収集モードでツールを実行する前に存在している必要があります。 このツールは場所を作成せず、存在しないというエラーが返されます。  <br/> また、このパラメーターで指定されたコレクションの場所にアクセス許可を書き込む必要があります。  <br/><br/>PST ファイルのコピー先のデバイスが構文を使用して表示されない場合は、 `\\SERVER\SHARE` ドライブ文字をデバイスにマップし、このパラメーターの値にマップされたドライブ文字を使用します。 | `-CopyLocation "\\FILESERVER03\PSTs"` <br/>または<br/>`-CopyLocation "z:\"`|
    | `LogLocation` <br/> |収集モードのログファイルがコピーされるフォルダーを指定します。 このパラメーターは省略可能です。 このファイルを含めない場合、ログファイルは PST コレクションツールをダウンロードしたフォルダーにコピーされます。 手順1の検索モードでツールを実行したときに使用したのと同じログの場所を使用して、すべてのログファイルが同じフォルダーに保存されるようにしてください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |このオプションのスイッチを使用すると、既存の PST コレクションジョブのコレクションモードでツールを再実行できます。 以前に Collect モードでツールを実行していて、PST ファイルの場所を再スキャンするスイッチを使用して、このツールを検索モードで再度実行した場合 `ForceRestart` は、このスイッチを使用して、コレクションモードでツールを再実行し、場所を再スキャンしたときに見つかった PST ファイルを再コピーできます。 `ForceRestart`コレクションモードでスイッチを使用する場合、このツールは以前のすべてのコレクション操作を無視し、PST ファイルを最初からコピーしようとします。  <br/> | `-ForceRestart` <br/> |
   
    各パラメーターに実際の値を使用して、DataCollectorMaster.exe ツールの構文の例を次に示します。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    コマンドを実行すると、手順1で見つかった PST ファイルの収集の進行状況を示す詳細な状態メッセージが表示されます。 しばらくすると、最後の状態メッセージにエラーがあるかどうかと、ログのコピー先が表示されます。 同じ状態メッセージが .log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>収集モードで DataCollectorMaster.exe を実行した結果

Collect モードで DataCollectorMaster.exe を正常に実行すると、次のファイルが作成され、and パラメーターで指定されたフォルダーに格納され `LogLocation` `ConfigurationLocation` ます。 
  
- [ ** \<JobName\> _Collect_ \<DateTimeStamp\> ログの収集**-ログファイルには、表示された状態メッセージが含まれています。 このファイルは、パラメーターで指定されたフォルダー内に作成され `LogLocation` ます。 
    
- ** \<JobName\> _Collect_ \<DateTimeStamp\> ** -xml ファイルには、ツールで使用されたものが収集モードで実行されたパラメーター値に関する情報のみが含まれています。 このファイル内のデータは、DataCollectorMaster.exe ツールを再実行して PST ファイルを削除するときに使用されます。[手順 5](#step-5-delete-the-pst-files-found-on-your-network)を参照してください。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>手順 4: Office 365 に PST ファイルをインポートする

手順1で見つかった PST ファイルを収集した後、次の手順では、それらを Office 365 のメールボックスにインポートします。 一部またはインポートプロセスでは、インポートする各 PST ファイルの行を含む CSV マッピングファイルを作成する必要があります。 各行の情報 PST ファイルの名前、ユーザーの電子メールアドレス、および PST ファイルをユーザーのプライマリメールボックスまたはアーカイブメールボックスにインポートするかどうかを指定します。 CSV マッピングファイルを作成するために、 **JobName \> _Find_ \<DateTimeStamp.csv**ファイル (手順1で作成) の情報を使用します。 
  
PST ファイルを Office 365 にインポートするための詳細な手順については、以下のいずれかのトピックを参照してください。
  
- [ネットワーク アップロードを使用して PST ファイルを Office 365 にインストールする](use-network-upload-to-import-pst-files.md)
    
- [ドライブの送付を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>手順 5: ネットワーク上で見つかった PST ファイルを削除する

見つけて収集した PST ファイルを Office 365 の Exchange Online メールボックスにインポートした後で、PST コレクションツールを使用して、手順1で見つけた元の場所から PST ファイルを削除できます。 
  
1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PST コレクションツールをダウンロードしたディレクトリに移動します。
    
3. PST ファイルを削除するには、次のコマンドを実行します。

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    次の表では、DataCollectorMaster.exe コマンドを実行して PST ファイルを削除するときのパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して PST ファイルを検索できます。 ![空ける](../media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 `Delete`検索モードでツールを実行したときに検出された PST ファイルを削除するには、値を使用します。  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |既存の PST コレクションジョブの名前を指定します。 この同じジョブ名を使用する必要があります。この名前は、このツールを検索モードで実行したときと、手順1および手順3で使用したものと同じです。 このジョブ名は、ツールを削除モードで実行するときに作成されるログファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |収集モードでツールを実行したときに作成された .xml 構成ファイルが格納されているフォルダーを指定します。 手順3でこのパラメーターに使用したのと同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |削除モードのログファイルがコピーされるフォルダーを指定します。 このパラメーターは省略可能です。 このファイルを含めない場合、ログファイルは PST コレクションツールをダウンロードしたフォルダーにコピーされます。 手順1と手順3でツールを実行したときと同じログの場所を使用して、すべてのログファイルが同じフォルダーに保存されるようにしてください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |このオプションスイッチを使用すると、既存の PST コレクションジョブの削除モードでツールを再実行できます。 以前に削除モードでツールを実行していて、PST ファイルの場所を再スキャンするためにスイッチを使用してツールを再度検索モードで実行した場合 `ForceRestart` は、このスイッチを使用して削除モードでツールを再実行し、場所を再スキャンしたときに検出された PST ファイルを削除できます。 スイッチを削除モードで使用すると、 `ForceRestart` 以前の削除操作は無視され、PST ファイルの削除が再試行されます。  <br/> | `-ForceRestart` <br/> 

    各パラメーターに実際の値を使用して、DataCollectorMaster.exe ツールの構文の例を次に示します。
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    コマンドを実行すると、手順1で検出され、手順3で収集された PST ファイルの削除の進行状況を示す詳細な状態メッセージが表示されます。 しばらくすると、最後の状態メッセージにエラーがあるかどうかと、ログのコピー先が表示されます。 同じ状態メッセージが .log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>削除モードで DataCollectorMaster.exe を実行した結果

削除モードで DataCollectorMaster.exe を正常に実行すると、次のファイルが作成され、and パラメーターで指定されたフォルダーに格納され `LogLocation` `ConfigurationLocation` ます。 
  
- ** \<JobName\> _Delete_ \<DateTimeStamp\> .Log** -ログファイルには、表示された状態メッセージが含まれています。 このファイルは、パラメーターで指定されたフォルダー内に作成され `LogLocation` ます。 
    
- ** \<JobName\> _削除_ \<DateTimeStamp\> ** -xml ファイルには、ツールが削除モードで実行されたパラメーター値に関する情報のみが含まれています。 また、削除された各 PST ファイルの名前とファイルパスも一覧表示します。 このファイルは、パラメーターで指定されたフォルダー内に作成され `ConfigurationLocation` ます。 
