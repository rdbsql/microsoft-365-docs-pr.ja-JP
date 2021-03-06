---
title: ドライブの送付を使用して組織の PST ファイルをインポートする
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
ms.custom: seo-marvel-apr2020
description: 管理者は、pst ファイルをハードドライブにコピーしてから Microsoft に配布することによって PST ファイルを Microsoft 365 メールボックスに一括インポートする方法を学習できます。
ms.openlocfilehash: e94a59b19271af275f74a08355a017533f8ef45d
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127344"
---
# <a name="use-drive-shipping-to-import-your-organizations-pst-files"></a>ドライブの送付を使用して組織の PST ファイルをインポートする

**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしようとしていますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**
   
Office 365 インポートサービスとドライブ配送を使用して、PST ファイルをユーザーのメールボックスに一括インポートします。 ドライブ送付とは、PST ファイルをハード ディスク ドライブにコピーし、Microsoft にドライブを物理的に送付することを意味します。 Microsoft がハードドライブを受け取ると、データセンターの担当者は、そのデータをハードドライブから Microsoft クラウドのストレージ領域にコピーします。 次に、インポートするデータを制御するフィルターを設定して、対象のメールボックスにインポートされた PST データをトリミングする機会があります。 インポートジョブを開始すると、インポートサービスはストレージ領域の PST データをユーザーのメールボックスにインポートします。 ドライブの送付を使用して PST ファイルをユーザーのメールボックスにインポートする方法は、組織の電子メールを Office 365 に移行する方法の1つです。
  
ドライブの配送を使用して PST ファイルを Microsoft 365 メールボックスにインポートするには、次の手順を実行する必要があります。
  
[手順 1: セキュリティで保護されたストレージキーおよび PST インポートツールをダウンロードする](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[手順 2: PST ファイルをハードドライブにコピーする](#step-2-copy-the-pst-files-to-the-hard-drive)

[手順 3: PST インポートのマッピングファイルを作成する](#step-3-create-the-pst-import-mapping-file)

[手順 4:Office 365 で PST インポート ジョブを作成する](#step-4-create-a-pst-import-job-in-office-365)

[手順 5:Microsoft にハード ドライブを送付する](#step-5-ship-the-hard-drive-to-microsoft)

[手順 6: データをフィルター処理して、PST インポート ジョブを開始する](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> セキュリティで保護されたストレージキーとインポートツールを読み込むには、手順1を実行する必要があります。 これらの手順を実行した後、ハードドライブを Microsoft に出荷するたびに、手順 2 ~ 手順6に従います。 
  
ドライブの送付を使用して PST ファイルを Office 365 にインポートする方法についてよく寄せられる質問については、「[ドライブ出荷を使用して pst ファイルをインポートする](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)」を参照してください。 
  
## <a name="before-you-import-pst-files"></a>PST ファイルをインポートする前に

- PST ファイルを Microsoft 365 メールボックスにインポートするには、Exchange Online で Mailbox Import Export の役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Mailbox Import Export の役割は組織の管理の役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export の役割を割り当て、ユーザー自身をメンバーとして追加できます。 詳細については、「[役割グループを管理する](https://go.microsoft.com/fwlink/p/?LinkId=730688)」で「役割グループに役割を追加する」または「役割グループを作成する」のセクションを参照してください。
    
    さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。
    
  - Exchange Online で Mail Recipients の役割が割り当てられている必要があります。 既定では、この役割は Organization Management 役割グループと Recipient Management 役割グループに割り当てられます。
    
    または
    
  - 組織の全体管理者である必要があります。
    
    > [!TIP]
    > PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討します。 PST ファイルをインポートするのに必要な最小レベルの権限では、新しい役割グループに Mailbox Import Export の役割および Mail Recipients の役割を割り当て、メンバーを追加します。 
  
- ハード ドライブにコピーする PST ファイルは、組織内のファイル サーバーまたは共有フォルダーに保存する必要があります。 手順2では、このファイルサーバーまたは共有フォルダーに格納されている PST ファイルをハードドライブにコピーする Azure インポートエクスポートツール (WAImportExport.exe) を実行します。

- PST ファイルが大きい場合、PST のインポート プロセスのパフォーマンスに影響を与える場合があります。 そのため、手順2でハードドライブにコピーする各 PST ファイルのサイズは、20 GB 以下にすることをお勧めします。
    
- Office 365 インポートサービスでの使用には、2.5 インチのソリッドステートドライブ (Ssd) または 2.5-インチまたは3.5 インチの SATA II/III の内部ハードドライブのみがサポートされています。 最大で 10 TB のハード ドライブを使用できます。 インポート ジョブでは、ハード ドライブの最初のデータ ボリュームのみが処理されます。 このデータ ボリュームは、NTFS でフォーマットする必要があります。 データをハードドライブにコピーする場合は、2.5 インチの SSD または 2.5-インチまたは3.5 インチの SATA II/III コネクタを使用して直接接続できます。または、外部の2.5 インチ SSD または2.5 インチまたは 3.5 SATA II/III USB アダプターを使用して外部に接続することもできます。
    
    > [!IMPORTANT]
    > Office 365 インポート サービスでは、USB アダプターが内蔵されている外部ハード ドライブはサポートされていません。 また、外部ハード ドライブのケース内にあるディスクは使用できません 外部ハード ドライブは発送しないでください。 
  
- PST ファイルをコピーするハード ドライブは、BitLocker で暗号化する必要があります。 手順 2 で実行する WAImportExport.exe ツールを使用すると、BitLocker をセットアップできます。 また、microsoft データセンターの担当者が、Microsoft クラウド内の Azure ストレージ領域に PST ファイルをアップロードするドライブにアクセスするために使用する BitLocker 暗号化キーを生成します。
    
- ドライブの配送は、Microsoft エンタープライズアグリーメント (EA) を通じて利用できます。 Microsoft Products and Services Agreement (MPSA) では、ドライブ送付はご利用いただけません。
    
- ドライブの配送を使用して PST ファイルを Microsoft 365 メールボックスにインポートするためのコストは、1 GB あたり $2 米ドルです。 たとえば、1,000 GB (1 TB) の PST ファイルを含むハード ディスク ドライブを発送する場合のコストは、2,000 米ドルです。 インポート手数料は、パートナーと分担して支払うことができます。 パートナーを探す方法については、「[Microsoft パートナーまたは販売店を探す](https://go.microsoft.com/fwlink/p/?LinkId=785197)」を参照してください。
    
- お客様またはお客様の組織は、FedEx または DHL のアカウントを持っている必要があります。 
    
  - 米国、ブラジル、ヨーロッパの組織には、FedEx アカウントが必要です。
    
  - 東アジア、東南アジア、日本、韓国共和国、オーストラリアの組織には、DHL アカウントが必要です。
    
    Microsoft では、このアカウントを使用して (および料金を請求する)、ハードドライブを返却しています。
    
- Microsoft に出荷したハードドライブは、国際的な国境を越えることができます。 この場合は、該当する法律に従ってハードドライブとそれに含まれるデータがインポートまたはエクスポートされていることを確認する責任があります。 ハード ドライブを送付する前に、指定された Microsoft データ センターにハード ドライブとデータを合法的に送付できるか法律顧問と一緒に確認してください。 これにより、適切なタイミングで Microsoft に到達できるようになります。
    
- この手順では、セキュリティで保護されたストレージ キーと BitLocker 暗号化キーをコピーして保存します。 パスワードやその他のセキュリティ関連情報を保護するように、これらのキーを保護するための予防策を必ず講じてください。 たとえば、パスワードで保護された Microsoft Word 文書に保存する、または暗号化された USB ドライブに保存することができます。 これらのキーの例については、「 [More information](#more-information) 」セクションを参照してください。 
    
- PST ファイルが Microsoft 365 メールボックスにインポートされると、メールボックスの保持ホールドの設定が無期限に有効になります。 つまり、メールボックスに割り当てられたアイテム保持ポリシーは、アイテム保持ホールドをオフにするか、またはホールドをオフにする日付を設定するまで処理されません。 このようにした理由は次のとおりです。 メールボックスにインポートされたメッセージは古くなると、完全に削除 (パージ) される可能性があります。これは、メッセージの保持期限がメールボックスに対して構成されたアイテム保持設定に基づいているためです。 メールボックスに対してアイテム保持ホールドが設定されると、メールボックスの所有者は、新たにインポートされたメッセージを管理する時間、またはメールボックスのアイテム保持設定を変更する時間を確保できます。 保持ホールドの管理に関する提案については、「 [More information](#more-information) 」セクションを参照してください。 
    
- 既定では、Microsoft 365 メールボックスで受信できるメッセージの最大サイズは 35 MB です。 これは、メールボックスの *MaxReceiveSize* プロパティの既定値が 35 MB に設定されているためです。 ただし、Microsoft 365 のメッセージ受信最大サイズの上限は 150 MB です。 そのため、35 MB より大きいアイテムを含む PST ファイルをインポートすると、Office 365 インポート サービスにより、対象メールボックスの *MaxReceiveSize* プロパティの値が 150 MB に自動的に変更されます。 これにより、最大 150 MB のメッセージをユーザーのメールボックスにインポートできます。 
    
    > [!TIP]
    > メッセージ受信サイズを識別するには、Exchange Online PowerShell で次のコマンドを実行します: `Get-Mailbox <user mailbox> | FL MaxReceiveSize` 
  
- PST ファイルを Office 365 の非アクティブなメールボックスにインポートできます。 PST インポート マッピング ファイルの `Mailbox` パラメーターで非アクティブなメールボックスの GUID を指定して、この操作を行います。 詳細については[、「ステップ 3: PST インポートのマッピングファイルを作成](#step-3-create-the-pst-import-mapping-file)する」を参照してください。 
    
- Exchange ハイブリッド展開では、オンプレミスのプライマリ メールボックスを持つユーザーのために、PST ファイルをクラウド ベースのアーカイブ メールボックスにインポートすることができます。 PST インポート マッピング ファイルに次を指定して、この操作を行います。
    
  - `Mailbox` パラメーターに、ユーザーのオンプレミス メールボックス用のメール アドレスを指定します。 
    
  - `IsArchive` パラメーターに、**TRUE** 値を指定します。 
    
    詳細については[、「ステップ 3: PST インポートのマッピングファイルを作成](#step-3-create-the-pst-import-mapping-file)する」を参照してください。 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>手順 1: セキュリティで保護されたストレージキーおよび PST インポートツールをダウンロードする

最初の手順では、セキュリティで保護されたストレージキーとツールをダウンロードし、手順2で使用して PST ファイルをハードドライブにコピーします。
  
> [!IMPORTANT]
> Drive 送付方法を使用して PST ファイルを正常にインポートするには、Azure インポート/エクスポートツールのバージョン 1 (WAimportExportV1) を使用する必要があります。 Azure インポート/エクスポートツールのバージョン2はサポートされていません。これを使用すると、インポートジョブのハードドライブが正しく準備されない可能性があります。 この手順の手順に従って、セキュリティ & コンプライアンスセンターから Azure インポート/エクスポートツールをダウンロードしてください。 
  
1. [https://protection.office.com/](https://protection.office.com/) に移動し、組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ/コンプライアンスセンターの左側のウィンドウで、[**情報ガバナンス**] \> [**インポート**] \> [**PST ファイルのインポート**] の順にクリックします。
    
    > [!NOTE]
    > 前述したように、セキュリティ & コンプライアンスセンターの [**インポート**] ページにアクセスするには、適切なアクセス許可が割り当てられている必要があります。 
  
3. [**PST ファイルのインポート**] ページで、[![追加](../media/ITPro-EAC-AddIcon.gif)] アイコン、[**新規インポート ジョブ**] の順にクリックします。
    
4. [ジョブのインポート] ウィザードで、PST インポートジョブの名前を入力し、[**次へ**] をクリックします。 小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。 大文字を使用したり、名前にスペースを含めたりすることはできません。
    
5. [**インポートジョブの種類の選択**] ページで、[**ハードドライブを物理的な場所の1つに出荷する**] をクリックし、[**次へ**] をクリックします。
    
    ![ドライブ送付インポートジョブを作成するには、[ハードドライブを物理的な場所の1つに出荷] をクリックします。](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. [**データのインポート**] ページで、次の 2 つの操作を行います。 
    
    ![セキュリティで保護されたストレージキーをコピーして、[データのインポート] ページに Azure インポートエクスポートツールをダウンロードする](../media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. 手順2で、[**セキュリティで保護されたストレージキーをコピー**] をクリックします。 ストレージキーが表示されたら、[**クリップボードにコピー** ] をクリックして貼り付け、ファイルに保存し、後でアクセスできるようにします。
    
    b. 手順3では、azure インポート/エクスポート**ツール**をダウンロードして、azure インポート/エクスポート (バージョン 1) ツールをダウンロードしてインストールします。
    
    - ポップアップウィンドウで **、[名前**を付けて保存] をクリックして、 \> **Save as** WaImportExportV1.zip ファイルをローカルコンピューター上のフォルダーに保存します。 
    
    - WaImportExportV1.zip ファイルを抽出します。
    
7. ウィザードを閉じるには、[**キャンセル**] をクリックします。 
    
    手順4でインポートジョブを作成するときに、セキュリティ & コンプライアンスセンターの [**インポート**] ページに戻ります。 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>手順 2: PST ファイルをハードドライブにコピーする

次の手順で、WAImportExport.exe ツールを使用して、PST ファイルをハード ドライブにコピーします。 このツールを使用して、ハード ドライブを BitLocker で暗号化して、PST をハード ドライブにコピーし、コピー プロセスに関する情報を保存するジャーナル ファイルを作成します。 この手順を完了するには、PST ファイルを組織内のファイル共有またはファイル サーバーに配置する必要があります。 これは、次の手順でソース ディレクトリと呼ばれます。 

 前述したように、ハードドライブにコピーする PST ファイルのサイズは 20 GB 以下にする必要があります。 PST ファイルが 20 GB を超える場合、手順 6 で開始する PST インポートプロセスのパフォーマンスに影響を与える可能性があります。
  
> [!IMPORTANT]
> ハード ドライブで初めて WAImportExport.exe ツールを実行した後は、実行するたびに異なる構文を使用する必要があります。 この構文については、この手順のステップ4で、PST ファイルをハードドライブにコピーする方法について説明します。 
  
1. ローカル コンピューター上でコマンド プロンプトを開く。
    
    > [!TIP]
    > 管理者としてコマンド プロンプトを実行する場合 (コマンド プロンプトを開く際に [管理者として実行] を選択する)、コマンド プロンプト ウィンドウにエラー メッセージが表示されます。これにより、WAImportExport.exe ツールの実行に関する問題のトラブルシューティングが行えます。 
  
2. 手順 1 で WAImportExport ツールをインストールしたディレクトリに移動する。
    
3. 初めて WAImportExport.exe を使用してハード ドライブに PST ファイルをコピーする場合は、次のコマンドを実行する。

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>
    ```

    次の表は、パラメーターとそれに必要な値を説明したものです。
    
    |**パラメーター**|**Description**|**例**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |ジャーナル ファイルの名前を指定します。 このファイルは、WAImportExport.exe ツールがあるフォルダーと同じフォルダーに保存されます。 Microsoft に送付するハード ドライブごとに 1 つのジャーナル ファイルが必要です。 WAImportTool.exe を実行して PST ファイルをハード ドライブにコピーするたびに、そのドライブのジャーナル ファイルに情報が追加されます。  <br/> Microsoft データセンターの担当者は、ジャーナルファイルの情報を使用して、手順4で作成したインポートジョブにハードドライブを関連付け、PST ファイルを Microsoft クラウドの Azure ストレージ領域にアップロードします。  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |ローカル コンピューターに接続されている場合は、ハード ドライブのドライブ文字を指定します。  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |コピー セッションの名前を指定します。WAImportExport.exe ツールを実行してファイルをハード ドライブにコピーするたびに、セッションが定義されます。PST ファイルは、このパラメーターで指定されたセッション名の名前が付けられたフォルダーにコピーされます。   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |セッション中にコピーされる PST ファイルを含む組織内のソース ディレクトリを指定します。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Pst がアップロードされる Microsoft クラウドの Azure ストレージ領域で、宛先ディレクトリを指定します。 値を使用する必要があり `ingestiondata/` ます。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> 必要に応じて、このパラメーターの値に追加のファイルパスを追加することもできます。 たとえば、ハードドライブ上のソースディレクトリのファイルパス (URL 形式に変換される) を使用できます。これは、パラメーターで指定されてい `/srcdir:` ます。 たとえば、 `\\FILESERVER01\PSTs` はに変更され `FILESERVER01/PSTs` ます。 この場合も、ファイルパスに含める必要があり `ingestiondata` ます。 そのため、この例では、パラメーターの値はになり `/dstdir:` `"ingestiondata/FILESERVER01/PSTs"` ます。  <br/> 同じファイル名の PST ファイルがある場合は、追加のファイルのパスを追加する理由の 1 つになります。  <br/> > [!NOTE]> オプションのパス名を指定した場合、PST ファイルの名前空間には、Azure ストレージ領域にアップロードされた後に、パス名と PST ファイルの名前が含まれます。たとえば、のように `FILESERVER01/PSTs/annb.pst` なります。 Pathname を指定しない場合、名前空間は PST ファイル名のみになります。例を示し `annb.pst` ます。           | `/dstdir:"ingestiondata/"` <br/> または  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |手順 1 で取得したストレージ アカウント キーを指定します。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/blobtype:` <br/> |PST ファイルのインポート先となる Azure Storage 領域内の blob の種類を指定します。 PST ファイルをインポートする場合は、値**Blockblob**を使用します。 このパラメーターは必須です。   <br/> | `/blobtype:BlockBlob` <br/> |
    | `/encrypt` <br/> |このスイッチは、ハード ドライブの BitLocker を有効にします。 このパラメーターは、WAImportExport.exe ツールを初めて実行する際に必要です。  <br/> BitLocker 暗号化キーは、ジャーナルファイルと、パラメーターを使用した場合に作成されるログファイルにコピーされ `/logfile:` ます。 前述のように、ジャーナル ファイルは、WAImportExport.exe ツールがあるフォルダーと同じフォルダーに保存されます。  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |この省略可能なパラメーターは、ログ ファイルの保存先のフォルダーを指定します。 指定しない場合、ログファイルは WAImportExport.exe ツールが配置されているのと同じフォルダーに保存されます。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    各パラメーターの実際の値を使用する WAImportExport.exe ツールの構文の例を以下に示します。
    
    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    コマンドを実行すると、ハード ドライブへの PST ファイルのコピーの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、正常にコピーされたファイルの合計数を示しています。 
    
4. このコマンドを、WAImportExport.ext ツールを 2 回目以降に実行するたびに実行して、PST ファイルを同じハード ドライブにコピーする。

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 
    ```

    以降のセッションを実行して PST ファイルを同じハード ドライブにコピーするための構文の例は、以下の通りです。  

    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>手順 3: PST インポートのマッピングファイルを作成する

Microsoft データセンターの担当者がハードドライブから Azure ストレージ領域に PST ファイルをアップロードした後、インポートサービスは、pst ファイルがインポートされるユーザーメールボックスを指定する PST インポートマッピングファイルの情報をコンマ区切り値 (CSV) ファイルで使用します。 PST インポート ジョブを作成する場合は、次の手順でこの CSV ファイルを送信します。
  
1. [PST インポート マッピング ファイルのコピーをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
2. CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。

    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    CSV ファイルの先頭行やヘッダー行には、PST ファイルをユーザー メールボックスにインポートするために PST インポート サービスで使うパラメーターが一覧表示されます。 各パラメーター名はコンマで区切られています。 ヘッダー行の下の各行は、特定のメールボックスに PST ファイルをインポートするためのパラメーター値を表します。 ハードディスクドライブにコピーされた PST ファイルごとに行が必要です。 必ずマッピング ファイル内のプレースホルダーのデータを実際のデータに置き換えてください。

    > [!NOTE]
    > SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。 
  
3. 次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。
    
    |**パラメーター**|**Description**|**例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |データのインポート先のサービスを指定します。 ユーザー メールボックスに PST ファイルをインポートするには、`Exchange` を使用します。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | ハードドライブが Microsoft に出荷されたときに PST ファイルがコピーされる Azure ストレージ領域内のフォルダーの場所を指定します。  <br/>  CSV ファイルのこの列に追加する内容は、前の手順でパラメーターに指定した内容によって異なり `/dstdir:` ます。 移動元の場所にサブフォルダーがある場合は、パラメーターの値に `FilePath` サブフォルダーの相対パスを含める必要があります。たとえば、/フォルダー名を指定します。  <br/>  を使用した場合は `/dstdir:"ingestiondata/"` 、CSV ファイルでこのパラメーターを空白のままにします。  <br/>  パラメーターの値の省略可能なパス名 (たとえば、) を指定した場合、 `/dstdir:` `/dstdir:"ingestiondata/FILESERVER01/PSTs"` CSV ファイルのこのパラメーターにはその pathname ("ingestiondata" を含まない) を使用します。 このパラメーターの値には、大文字と小文字の区別があります。  <br/>  どちらの場合でも、`FilePath` パラメーターの値に "ingestiondata" を含め*ない*でください。 このパラメーターを空白のままにしておくか、省略可能なパス名のみを指定します。  <br/> > [!IMPORTANT]> ファイルパス名の大文字と小文字は、前の手順でパラメーターで指定したものと同じである必要があり `/dstdir:` ます。 たとえば、 `"ingestiondata/FILESERVER01/PSTs"` 前の手順でサブフォルダー名を使用していて、CSV ファイルのパラメーターで使用した場合、 `fileserver01/psts` `FilePath` PST ファイルのインポートは失敗します。 必ず、両方のインスタンスの大文字と小文字を同じにしてください。           |(空白のまま)  <br/> または  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |ユーザー メールボックスにインポートする PST ファイルの名前を指定します。 このパラメーターの値には、大文字と小文字の区別があります。  <br/> > [!IMPORTANT]CSV ファイル内の PST ファイル名の大文字/小文字の> は、手順2で Azure ストレージの場所にアップロードされた PST ファイルと同じである必要があります。 たとえば、CSV ファイル内の `Name` パラメーターでは `annb.pst` を使用していますが、実際の PST ファイルの名前は `AnnB.pst` である場合、その PST ファイルのインポートは失敗します。 CSV ファイル内の PST の名前の大文字小文字は、実際の PST ファイルの場合と同じである必要があります。           | `annb.pst` <br/> |
    | `Mailbox` <br/> |PST ファイルのインポート先になるメールボックスのメールアドレスを指定します。 PST インポート サービスは、PST ファイルのパブリック フォルダーへのインポートをサポートしていないため、パブリック フォルダーを指定できません。  <br/> PST ファイルを非アクティブなメールボックスにインポートするには、このパラメーターにメールボックスの GUID を指定する必要があります。 この GUID を取得するには、Exchange Online で `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` の PowerShell コマンドを実行します。 <br/> > [!NOTE]>、1つのメールボックスがアクティブなメールボックスであり、もう一方のメールボックスが削除済み (または非アクティブ) 状態にある場合に、同じメールアドレスを持つ複数のメールボックスを持つことがあります。 このような状況で、PST ファイルのインポート先のメールボックスを一意に識別するには、メールボックスの GUID を指定する必要があります。 アクティブなメールボックスの GUID を取得するには、次の PowerShell コマンドを実行します: `Get-Mailbox <identity of active mailbox> | FL Guid` 回復可能な削除 (または非アクティブ) のメールボックスの GUID を取得するには、次のコマンドを実行 `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid` します。           | `annb@contoso.onmicrosoft.com` <br/> または  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。 次のような 2 つのオプションがあります。  <br/> **FALSE**PST ファイルをユーザーのプライマリメールボックスにインポートします。  <br/> **TRUE**PST ファイルをユーザーのアーカイブメールボックスにインポートします。 これは、[ユーザーのアーカイブ メールボックスが有効である](enable-archive-mailboxes.md)ことが前提です。 このパラメーターが `TRUE` に設定されている場合に、ユーザーのアーカイブ メールボックスが有効になっていない場合は、そのユーザーのインポートは失敗します。 アーカイブが有効化されていないにもかかわらずこのプロパティが `TRUE` に設定されたことが原因で、あるユーザーのインポートが失敗しても、そのインポート ジョブ内の他のユーザーが影響を受けることはありません。  <br/>  このパラメーターを空白のままにすると、PST ファイルはユーザーのプライマリ メールボックスにインポートされます。  <br/> **注:** PST ファイルをクラウド ベースのアーカイブ メールボックスにインポートするときに、そのユーザーのプライマリ メールボックスがオンプレミスの場合は、このパラメーターに対して `TRUE` を指定し、そのユーザーのオンプレミスのメールボックスのメール アドレスを `Mailbox` パラメーターで指定してください。  <br/> | `FALSE` <br/> または  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | PST ファイルのインポート先のメールボックス フォルダーを指定します。  <br/>  このパラメーターを空白のままにした場合、PST はメールボックスのルートレベル (受信トレイフォルダーとその他の既定のメールボックスフォルダーと同じレベル) にある**インポート**された新しいフォルダーにインポートされます。  <br/>  を指定した場合 `/` 、PST ファイル内のアイテムは、ユーザーの受信トレイフォルダーに直接インポートされます。  <br/>  を指定した場合 `/<foldername>` 、PST ファイルのアイテムはという名前のフォルダーにインポートされ *\<foldername\>* ます。 たとえば、`/ImportedPst` を使用した場合、アイテムは **ImportedPst** というフォルダーにインポートされます。 このフォルダーは、ユーザーのメールボックスの受信トレイ フォルダーと同じレベルにあります。  <br/> |(空白のまま)  <br/> または  <br/>  `/` <br/> または  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |この省略可能なパラメーターでは、PST ファイルを ANSI ファイル形式でインポートする場合に使用するコード ページの数値を指定します。 このパラメーターは、中国語、日本語、韓国語 (CJK) を使用する組織から PST ファイルをインポートする場合に使用します。通常、これらの言語は、文字エンコードのために 2 バイト文字セット (DBCS) を使用するからです。 メールボックス フォルダー名に DBCS が使用されている言語については、PST ファイルのインポートの際にこのパラメーターを使用しないと、多くの場合、インポート後にフォルダー名の文字化けが発生します。  <br/> このパラメーターに使用できる値のリストについては、「[Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514)」 (コード ページ識別子) を参照してください。  <br/> > [!NOTE]> 前述のとおり、これはオプションのパラメーターであり、CSV ファイルに含める必要はありません。 または、このパラメーターを含め、1 つまたは複数の行について値を空白のままにしておくこともできます。           |(空白のまま)  <br/> または  <br/>  `932` (ANSI/OEM 日本語のコード ページ ID)  <br/> |
    | `SPFileContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。  <br/> |該当なし  <br/> |
    | `SPManifestContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。  <br/> |該当なし  <br/> |
    | `SPSiteUrl` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。  <br/> |該当なし  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>手順 4:Office 365 で PST インポート ジョブを作成する

次の手順では、Office 365 のインポート サービスで PST インポート ジョブを作成します。 前述のように、手順3で作成した PST インポートマッピングファイルを送信します。 ジョブを作成した後、インポートサービスはマッピングファイルの情報を使用して、pst ファイルをハードドライブから Azure ストレージ領域にコピーした後に、指定されたユーザーメールボックスに PST ファイルをインポートします。その後、インポートジョブを作成して開始します。
  
1. [https://protection.office.com](https://protection.office.com) に移動し、組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ/コンプライアンスセンターの左側のウィンドウで、[**情報ガバナンス**] \> [**インポート**] \> [**PST ファイルのインポート**] の順にクリックします。
    
3. [**PST ファイルのインポート**] ページで、[![追加](../media/ITPro-EAC-AddIcon.gif)] アイコン、[**新規インポート ジョブ**] の順にクリックします。
    
    > [!NOTE]
    > 前述したように、セキュリティ & コンプライアンスセンターの [**インポート**] ページにアクセスするには、適切なアクセス許可が割り当てられている必要があります。 
  
4. PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。 小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。 大文字を使用したり、名前にスペースを含めたりすることはできません。
    
5. [**インポートジョブの種類の選択**] ページで、[**ハードドライブを物理的な場所の1つに出荷する**] をクリックし、[**次へ**] をクリックします。
    
    ![ドライブ送付インポートジョブを作成するには、[ハードドライブを物理的な場所の1つに出荷] をクリックします。](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 手順6で、[自分のハードドライブの準備ができました] をクリックし、**必要なドライブジャーナルファイルにアクセス**して、[**マッピングファイルにアクセス**できる] チェックボックスをオンにして、[**次へ**] をクリックします。
    
    ![手順6で2つのチェックボックスをクリックします。](../media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. [**ドライブファイルの選択**] ページで、[**ドライブファイルの選択**] をクリックし、WAImportExport.exe ツールが配置されているものと同じフォルダーに移動します。 手順 2 で作成したジャーナル ファイルは、このフォルダーにコピーされました。
    
    ![WAImportExport.exe ツールを実行したときに作成されたジャーナルファイルを送信するには、[ドライブファイルの選択] をクリックします。](../media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. ジャーナルファイルを選択します。たとえば、のように `PSTHDD1.jrn` なります。
    
    > [!TIP]
    > 手順2で WAImportExport.exe ツールを実行したときに、ジャーナルファイルの名前がパラメーターによって指定されてい `/j:` ます。 
  
9. ドライブファイルの名前が [**ドライブファイル名**] の下に表示されたら、[**検証**] をクリックして、ドライブファイルにエラーがないかどうかを確認します。 
    
    ![[検証] をクリックして、選択したドライブファイルを検証します。](../media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    PST インポートジョブを作成するには、ドライブファイルが正常に検証されている必要があります。 正常に検証された後にファイル名が緑色に変更されますので注意してください。 検証が失敗した場合は、[**ログの表示**] リンクをクリックします。 検証エラーレポートが開き、ファイルが失敗した理由に関する情報が含まれたエラーメッセージが表示されます。 
    
    > [!NOTE]
    > Microsoft に出荷する各ハードドライブに対して、ジャーナルファイルを追加して検証する必要があります。 
  
10. Microsoft に出荷する各ハードドライブのジャーナルファイルを追加して検証した後、[**次へ**] をクリックします。
    
11. [ ![ 追加] アイコン [ ](../media/ITPro-EAC-AddIcon.gif) **マッピングファイルの選択**] をクリックして、手順3で作成した PST インポートマッピングファイルを送信します。 
    
    ![[マッピング ファイルの選択] をクリックして、インポート ジョブのために作成した CSV ファイルを送信する](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. CSV ファイルの名前が [**マッピング ファイル名**] に表示されたら、[**検証**] をクリックし、CSV ファイルでエラーを確認します。 
    
    ![[検証] をクリックして CSV ファイルでエラーを確認する](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。 正常に検証された後にファイル名が緑色に変更されますので注意してください。 検証が失敗した場合は、[**ログの表示**] リンクをクリックします。 検証エラー レポートを開くと、失敗したファイルの各行にエラー メッセージが表示されます。 
    
13. PST マッピングファイルが正常に検証されたら、[**次へ**] をクリックします。
    
14. [**連絡先情報の入力**] ページで、該当するボックスに連絡先情報を入力します。 
    
    ハードドライブを送付する Microsoft の場所のアドレスが表示されます。 このアドレスは、Microsoft データセンターの場所に基づいて自動生成されます。 この住所をファイルにコピーするか、スクリーン ショットを撮ってください。
    
15. 使用条件ドキュメントを読んで、チェックボックスをクリックし、[**保存**] をクリックしてインポートジョブを送信します。 
    
    インポートジョブが正常に作成されると、ドライブ出荷プロセスの次の手順を説明する状態ページが表示されます。
    
16. [ **PST ファイルのインポート**] ページで、[最新の情報に更新] アイコンの更新をクリックして、 ![ ](../media/O365-MDM-Policy-RefreshIcon.gif) **Refresh**インポートジョブの一覧に新しいドライブ配送インポートジョブが表示されます。 状態は、**トラッキング番号を待機**するように設定されています。 インポートジョブをクリックして、インポートジョブに関する詳細情報を含む状態ポップアップページを表示することもできます。
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>手順 5:Microsoft にハード ドライブを送付する

次の手順では、Microsoft にハードドライブを送付してから、ドライブ出荷ジョブの発送番号と返送情報を提供します。 ドライブは、Microsoft によって受信された後、データセンターの担当者が組織の Azure ストレージ領域に PST ファイルをアップロードするのに 7 ~ 10 営業日かかります。
  
> [!NOTE]
> インポートジョブの作成から14日以内に追跡番号を指定せずに出荷情報を取得した場合、インポートジョブは期限切れになります。 このような状況が発生した場合は、新しいドライブ送付インポートジョブを作成する必要があります (「[手順 4: Office 365 で Pst インポートジョブを作成](#step-4-create-a-pst-import-job-in-office-365)する」を参照し、ドライブファイルと pst インポートマッピングファイルを再送信します。 
  
### <a name="ship-the-hard-drive"></a>ハード ドライブを送付する

Microsoft にハード ドライブを送付する場合は、次の点に注意してください。
  
- シリアルから USB へのアダプターは送付しないでください。ハードドライブを送付するだけで済みます。
    
- ハード ドライブを適切に梱包する。たとえば、静電気防止バッグやクッション材など使用する。
    
- 任意の配送業者を使用して、Microsoft にハード ドライブを送付する。
    
- 手順 4 でインポート ジョブを作成したときに表示された Microsoft の場所の住所に、ハード ドライブを送付する。 送付先アドレスには、"Office 365 インポート サービス" を必ず含めてください。
    
- ハード ドライブの送付後、配送業者の名前と追跡番号を必ず書き留めてください。これらは次の手順で必要になります。
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>追跡番号と他の配送情報を入力する

Microsoft にハード ドライブを送付した後、インポート サービスのページで次の手順を完了します。
  
1. [https://protection.office.com](https://protection.office.com) に移動し、組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. 左側のウィンドウで、[ **Information ガバナンス > インポート > インポート**] をクリックして、PST ファイルをインポートします。
    
3. [ **PST ファイルのインポート**] ページで、追跡番号を入力するドライブの出荷のジョブをクリックします。 
    
4. [状態のポップアップ] ページで、[**追跡番号の入力**] をクリックします。
    
5. 以下の送付情報を入力する。
    
1. **配送業者**ハードドライブを Microsoft に出荷する際に使用した配送業者の名前を入力します。 
    
2. **追跡番号**ハードドライブの出荷の追跡番号を入力します。 
    
3. **返品業者のアカウント番号**[**返品業者**] にリストされている通信業者の組織のアカウント番号を入力します。 Microsoft では、このアカウントを使用して、お客様にハードドライブを送付しています。 米国およびヨーロッパの組織には、FedEx のアカウントが必要です。 アジアおよび世界の他の組織は、DHL のアカウントを持っている必要があります。
    
6. **[保存]** をクリックして、インポート ジョブのこの情報を保存する。 
    
    [ **PST ファイルのインポート**] ページで、[ ![ 更新] アイコンの更新をクリックして、 ](../media/O365-MDM-Policy-RefreshIcon.gif) **Refresh**ドライブの配送インポートジョブの情報を更新します。 ステータスが **[ドライブを送付中]** に設定されていることに注意してください。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>手順 6: データをフィルター処理して、PST インポート ジョブを開始する

Microsoft がハードドライブを受信すると、[ **PST ファイルのインポート**] ページのインポートジョブの状態が [受信した**ドライブ**] に変わります。 データセンターの担当者は、ジャーナルファイルの情報を使用して、組織の Azure ストレージ領域に PST ファイルをアップロードします。 この時点で、状態が [**インポート中**] に変わります。 前述したように、ハードドライブを受け取った後、PST ファイルをアップロードするには、7 ~ 10 営業日かかります。
  
PST ファイルが Azure にアップロードされると、進行中の**分析**に状態が変更されます。 これは、Microsoft 365 が PST ファイル (安全かつ安全な方法) でデータを分析し、PST ファイルに含まれているアイテムの保存期間とさまざまなメッセージの種類を識別することを示しています。 分析が完了し、データをインポートする準備が整ったら、インポートジョブの状態が [**分析完了**] に変更されます。 この時点で、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定することによってインポートされたデータをトリミングするかを選択できます。
  
1. [https://protection.office.com](https://protection.office.com) に移動し、組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. 左側のウィンドウで、[**情報ガバナンス**] [ \> **Import** \> **PST ファイルのインポート**] をクリックします。
    
3. [ **PST ファイルのインポート**] ページで、手順4で作成したインポートジョブについて、[ **Office 365 へ**のインポートの準備完了] をクリックします。 
    
    ![作成したインポート ジョブの横にある [Microsoft 365 にインポートする準備ができました] をクリックする](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    PST ファイルに関する情報とインポート ジョブに関するその他の情報を示すポップアップ ページが表示されます。
    
4. [ **Office 365 へのインポート] を**クリックします。
    
5. [**データのフィルター処理**] ページが表示されます。 ここには、データの使用期間に関する情報など、Office 365 によって実行された PST ファイルの分析の結果のデータ情報が含まれます。 この時点で、インポートされるデータにフィルター処理を適用するか、すべてのデータをそのままインポートするかを選択できます。 
    
    ![PST ファイルのデータをトリミングしたり、そのすべてをインポートしたりすることができる](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. 次のいずれかの操作を行います。
    
    a.  インポートするデータをトリミングする場合は [**はい、インポートする前にフィルター処理します**] をクリックします。
    
    PST ファイル内のデータをフィルター処理してインポート ジョブを開始する手順の詳細については、「[Office 365 に PST ファイルをインポートするときにデータをフィルター処理する](filter-data-when-importing-pst-files.md)」を参照してください。
    
    または
    
    b.  PST ファイル内のすべてのデータをインポートするには、[**いいえ、すべてのアイテムをインポートします**] をクリックして、[**次へ**] をクリックします。
    
7. すべてのデータをインポートする場合は、[**データのインポート**] をクリックしてインポート ジョブを開始します。 
    
    インポートジョブの状態は、[ **PST ファイルのインポート**] ページに表示されます。 ![更新アイコン](../media/O365-MDM-Policy-RefreshIcon.gif) [**更新**] をクリックして、[**ステータス**] 列に表示されるステータス情報を更新します。 インポート ジョブをクリックするとステータス フライアウト ページが表示され、インポートされている各 PST ファイルに関するステータス情報が表示されます。 インポートが完了し、PST ファイルがユーザー メールボックスにインポートされると、ステータスは **[完了]** に変わります。

## <a name="view-a-list-of-the-pst-files-uploaded-to-microsoft-365"></a>Microsoft 365 にアップロードされた PST ファイルの一覧を表示する

Microsoft Azure ストレージエクスプローラー (無償のオープンソースツール) をインストールして使用すると、組織の Azure ストレージ領域に (Microsoft データセンター担当者が) アップロードした PST ファイルの一覧を表示することができます。 これにより、Microsoft に送信したハードドライブの PST ファイルが Azure ストレージ領域に正常にアップロードされたことを確認できます。
  
Microsoft Azure Storage Explorer はプレビュー中です。 
  
 **重要:** Azure ストレージエクスプローラーを使用して PST ファイルをアップロードまたは変更することはできません。 PST ファイルを Microsoft 365 にインポートするためにサポートされている唯一の方法は、AzCopy を使用することです。 また、Azure BLOB にアップロードした PST ファイルを削除することはできません。 PST ファイルを削除しようとすると、必要なアクセス許可がないというエラーが表示されます。 すべての PST ファイルが自動的に Azure ストレージ領域から削除されます。 進行中のインポートジョブがない場合、[* * ingestiondata * *] コンテナー内のすべての PST ファイルは、最新のインポートジョブが作成されてから30日後に削除されます。 
  
Azure Storage Explorer をインストールし、Azure Storage 領域に接続するには:
  
1. 組織の Shared Access Signature (SAS) URL を取得するには、次の手順を実行します。 この URL は、組織および SAS キーで使用される Microsoft クラウド内の Azure ストレージの場所のネットワーク URL の組み合わせです。 このキーは、組織の Azure ストレージの場所にアクセスするために必要なアクセス許可を提供します。
    
1. [https://protection.office.com/](https://protection.office.com/) に移動し、組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ /コンプライアンスセンターの左側のウィンドウで、**[情報ガバナンス]、[インポート]、[PST ファイルのインポート]** の順にクリックします。
    
3. [**PST ファイルのインポート**] ページで、[![追加](../media/ITPro-EAC-AddIcon.gif)] アイコン、[**新規インポート ジョブ**] の順にクリックします。
    
4. [ジョブのインポート] ウィザードで、PST インポートジョブの名前を入力し、[**次へ**] をクリックします。 小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。 大文字を使用したり、名前にスペースを含めたりすることはできません。
    
5. [**インポートジョブの種類の選択**] ページで、[データの**アップロード**] をクリックし、[**次へ**] をクリックします。
    
6. 手順 2 で、[**ネットワーク アップロード SAS URL を表示する**] をクリックします。
    
7. URL が表示されたら、それをコピーしてファイルに保存します。 必ず URL 全体をコピーする。
    
    > [!IMPORTANT]
    > 必ず SAS URL を保護するための予防措置を講じてください。 これは、組織の Azure ストレージ領域にアクセスするすべてのユーザーが使用できます。 
  
8. [**キャンセル**] をクリックして、ジョブのインポートウィザードを終了します。 
    
2. [Microsoft Azure Storage Explorer ツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をダウンロードしてインストールします。
    
3. Microsoft Azure Storage Explorer を起動し、左側のウィンドウで [**ストレージ アカウント**] を右クリックして、[**Azure Storage に接続**] をクリックします。
    
    ![[ストレージ アカウント] を右クリックし、[Azure Storage に接続] をクリックします。](../media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. [**共有アクセス署名 (SAS) URI または接続文字列を使用**] をクリックし、[**次へ**] をクリックします。
    
5. [ **SAS uri を使用**する] をクリックして、手順1で取得した sas URL を [ **uri**] の下のボックスに貼り付け、[**次へ**] をクリックします。
    
6. [**接続の概要**] ページで、接続情報を確認して [**接続**] をクリックします。
    
    **Ingestiondata** コンテナーが開きます。 ハードドライブの PST ファイルが含まれています。 **ingestiondata** コンテナーは、[**ストレージ アカウント**] \> **(SAS 接続サービス)** \> [**BLOB コンテナー**] にあります。
    
    ![Azure Storage Explorer には、アップロードした PST ファイルのリストが表示されます。](../media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Microsoft Azure Storage Explorer の使用が完了したら、**ingestiondata** を右クリックし、[**デタッチ**] をクリックすると Azure Storage 領域から切断されます。 切断しない場合、次に接続しようとするとエラーが表示されます。 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure Storage 領域から切断します。](../media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)

## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント

- **PST インポートの CSV マッピングファイルにエラーがあるためにインポートジョブが失敗した場合はどうなりますか。** マッピングファイルにエラーがあるためにインポートジョブが失敗した場合、インポートジョブを作成するためにハードドライブを再出荷する必要はありません。 これは、ドライブ送付インポートジョブ用に送信したハードドライブからの PST ファイルが、組織の Azure ストレージ領域に既にアップロードされているためです。 この場合、PST インポート CSV マッピングファイルのエラーを修正してから、新しい "network upload" インポートジョブを作成し、改訂された CSV マッピングファイルを送信するだけで済みます。 新しいネットワークアップロードインポートジョブを作成して開始するには、「 [step 5: create a Pst import job In Microsoft 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job) 」および「 [Step 6:](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) Use the NETWORK upload to Import pst files to Office 365」のトピックを参照してください。 
    
    > [!NOTE]
    > PST インポートの CSV マッピングファイルのトラブルシューティングに役立てるために、 [Azure ストレージエクスプローラー](#view-a-list-of-the-pst-files-uploaded-to-microsoft-365)ツールを使用して、azure ストレージ領域にアップロードされたハードディスクドライブからの pst ファイルの**ingestiondata**コンテナーにあるフォルダー構造を表示します。 通常、ファイルのマッピングエラーは FilePath パラメーターの値が正しくないことが原因で発生します。 このパラメーターには、Azure ストレージ領域内の PST ファイルの場所を指定します。 [手順 3](#step-3-create-the-pst-import-mapping-file)の表の FilePath パラメーターの説明を参照してください。 前述のように、 `/dstdir:` [手順 2](#step-2-copy-the-pst-files-to-the-hard-drive)で WAImportExport.exe ツールを実行したときに、パラメーターによって、Azure ストレージ領域内の PST ファイルの場所が指定されていました。 
  
## <a name="more-information"></a>詳細情報

- ドライブの配送は、組織で使用できるコンプライアンス機能を活用するために、大量のアーカイブメッセージングデータを Microsoft 365 にインポートする効果的な方法です。 アーカイブデータをユーザーのメールボックスにインポートした後、次のことを行うことができます。
    
  - [アーカイブメールボックス](enable-archive-mailboxes.md)と[自動拡張アーカイブ](enable-unlimited-archiving.md)を有効にして、ユーザーにデータのためのメールボックス記憶領域を追加します。 
    
  - メールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=856286)の対象にしてデータを保持します。 
    
  - Microsoft[電子情報開示ツール](search-for-content.md)を使用して、データを検索します。 
    
  - [Microsoft 365 の保持ポリシー](retention.md)を適用して、データの保持期間を制御し、保存期間が経過した後に実行するアクションを制御します。 
    
  - このデータに関連するイベントの[監査ログ](search-the-audit-log-in-security-and-compliance.md)を検索します。 
    
  - コンプライアンスを目的として、[非アクティブなメールボックス](create-and-manage-inactive-mailboxes.md)にデータをアーカイブするためのデータをインポートします。 
    
  - 機密情報の[データ損失](data-loss-prevention-policies.md)から組織を保護します。 
    
- セキュリティで保護されたストレージ アカウント キーと BitLocker 暗号化キーの例を、次に示します。この例には、ハード ディスクに PST ファイルをコピーするために実行する WAImportExport.exe コマンドの構文も含まれています。パスワードやその他のセキュリティ関連情報を保護するのと同じように、これらのファイルを保護するための予防策を必ず講じてください。
    

    ```text
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

- 前述したように、Office 365 インポート サービスは PST ファイルがメールボックスにインポートされた後、アイテム保持ホールド設定を (無期限に) オンにします。 つまり、 *RentionHoldEnabled*プロパティはに設定されて `True` いるため、メールボックスに割り当てられたアイテム保持ポリシーは処理されません。 これによりメールボックスの所有者は、古くなったメッセージが削除ポリシーまたはアーカイブ ポリシーによって削除またはアーカイブされるのを回避し、新たにインポートしたメッセージを管理する時間を確保できます。 このアイテム保持ホールドを管理するための手順を以下に示します。 
    
  - 一定の期間が経過した後、コマンドを実行して保存機能を無効にすることができ `Set-Mailbox -RetentionHoldEnabled $false` ます。 手順については、「[メールボックスの保存機能を有効にする](https://go.microsoft.com/fwlink/p/?LinkId=544749)」を参照してください。
    
  - 将来の特定の日付にオフになるようにアイテム保持ホールドを構成することができます。 そのためには、コマンドを実行し `Set-Mailbox -EndDateForRetentionHold <date>` ます。 たとえば、今日の日付が2016年6月1日で、保存機能を30日以内に無効にする場合は、次のコマンドを実行し `Set-Mailbox -EndDateForRetentionHold 7/1/2016` ます。 このシナリオでは、 *RentionHoldEnabled*プロパティを*True*に設定したままにします。 詳細については、「[Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)」を参照してください。
    
  - メールボックスに割り当てられているアイテム保持ポリシーの設定を変更して、インポート済みの古いアイテムがすぐに削除されたり、ユーザーのアーカイブ メールボックスに移動されたりしないようにすることができます。 たとえば、メールボックスに割り当てられた削除ポリシーまたはアーカイブ ポリシーの保持期間を長くすることができます。 このシナリオでは、アイテム保持ポリシーの設定を変更した後で、メールボックスに対するアイテム保持ホールドをオフにします。 詳細については、「[組織のメールボックスのアーカイブと削除ポリシーを設定する](set-up-an-archive-and-deletion-policy-for-mailboxes.md)」を参照してください。
    

  

