---
title: Office 365とMicrosoft 365 Businessプランを安全にする10の方法
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'ランサムウェア、フィッシング、悪意のある添付ファイルを含む、サイバーの脅威からビジネスメールとデータを保護します。 '
ms.openlocfilehash: d3abaa4fef1a50ab5aad4762e688efe451d0a4cf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247986"
---
# <a name="top-10-ways-to-secure-office-365-and-microsoft-365-business-plans"></a>Office 365とMicrosoft 365 Businessプランを安全にする10の方法

マイクロソフトのビジネスプランのいずれかを使用している小規模または中規模の組織で、組織の種類がサイバー犯罪者とハッカーの対象となっている場合は、この記事のガイダンスを使用して組織のセキュリティを強化してください。 このガイダンスは、組織が Harvard ケネディ School [Cybersecurity キャンペーンハンドブック](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)に記載されている目標を達成するのに役立つ情報です。
  
Microsoft では、サービスプランに適用される次の表のタスクを完了することをお勧めします。 
  
||**タスク**|**Office 365 Business Premium**|**Microsoft 365 Business**|
|:-----|:-----|:-----|:-----|
|1-d  <br/> |[多要素認証をセットアップする](secure-your-business-data.md#setup) <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|pbm-2  <br/> |[ユーザーをトレーニングする](secure-your-business-data.md#train) <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|1/3  <br/> |[専用の管理者アカウントを使用する](secure-your-business-data.md#admin) <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|2/4  <br/> |[メールのマルウェアに対する保護レベルを上げる](secure-your-business-data.md#malware) <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|5  <br/> |[ランサムウェアから保護する](secure-your-business-data.md#ransomware) <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|6   <br/> |[電子メールの自動転送を停止する](secure-your-business-data.md#forwarding) <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|7   <br/> |[Office メッセージの暗号化を使用する](secure-your-business-data.md#encryption) <br/> ||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|8   <br/> |[フィッシング攻撃からメールを保護する](secure-your-business-data.md#phishing) <br/> ||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9   <br/> |[ATP の安全な添付ファイルを使用して悪意のある添付ファイルやファイルを保護する](secure-your-business-data.md#atp) <br/> ||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|10   <br/> |[ATP の安全なリンクによるフィッシング攻撃から保護する](secure-your-business-data.md#phishingatp) <br/> ||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
   
開始する前に、Microsoft 365 セキュリティセンターの[microsoft 365 のセキュリティスコア](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)を確認してください。 一元管理されたダッシュボードから、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、強化することができます。 推奨されるセキュリティ機能を構成し、セキュリティ関連のタスク (レポートの表示など) を実行する、またはサードパーティのアプリケーションまたはソフトウェアで推奨事項に対処するためのポイントが用意されています。 より広範な一連の Microsoft 製品とサービスを使用することで、さらに洞察を得て、組織のセキュリティの状態についてのレポートを得ることができます。
  
![Microsoft セキュリティスコアのスクリーンショット](../media/secure-score.png)
  
## <a name="1-set-up-multi-factor-authentication"></a>1: 多要素認証をセットアップする
<a name="setup"> </a>

多要素認証を使用することは、組織のセキュリティを向上させる最も簡単で効果的な方法の1つです。 ログイン時には、多要素認証とは、電話からコードを入力して Microsoft 365 にアクセスするということよりも簡単です。 これにより、ハッカーがパスワードを知っている場合に、ハッカーが侵入するのを防ぐことができます。 多要素認証は、2ステップ認証とも呼ばれます。 各ユーザーは、たとえば Google や Microsoft のアカウントなど、ほとんどのアカウントに2段階の認証を簡単に追加できます。 [2 段階認証を個人の Microsoft アカウントに追加](https://go.microsoft.com/fwlink/?linkid=2016403&amp;clcid=0x409)する方法は次のとおりです。
  
Office 365 と Microsoft 365 を使用している企業の場合は、ユーザーが多要素認証を使用してログインすることを要求する設定を追加します。 この変更を行うと、ユーザーが次回ログインするときに2要素認証を使用するように電話を設定するように求めるメッセージが表示されます。
MFA をセットアップする方法と、ユーザーが設定を完了する方法についてのトレーニングビデオを参照するには、「 [set UP MFA](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) and [user set](https://support.office.com/article/a32541df-079c-420d-9395-9d59354f7225)up」を参照してください。
  
多要素認証をセットアップするには、次のようにします。

1. [管理センター](https://go.microsoft.com/fwlink/p/?linkid=834822)で、[**ユーザー** > の**アクティブなユーザー**] を選択します。

2. [**アクティブなユーザー** ] セクションで、[**多要素認証**] を選択します。

3. [**多要素認証**] ページで、1人のユーザーに対して有効にするか、**一括更新**を実行できる場合は、[**ユーザー** ] を選択します。

4. **クイック操作**の下の [**有効化**] を選択します。

5. ポップアップウィンドウで、[**多要素認証を有効にする**] を選択します。


組織に多要素認証を設定した後、ユーザーはデバイスに 2 段階認証を設定する必要があります。 詳細については、「[Office 365 で 2 段階認証をセットアップする](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。
  
完全な詳細および推奨事項については、「 [Office 365 ユーザー用に多要素認証をセットアップする](set-up-multi-factor-authentication.md)」を参照してください。
  
## <a name="2-train-your-users"></a>2: ユーザーをトレーニングする
<a name="train"> </a>

Harvard ケネディ School [Cybersecurity キャンペーンハンドブック](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)は、フィッシング攻撃を識別するユーザーのトレーニングを含む、組織内でのセキュリティの認知度の強力な文化を確立するための優れたガイダンスを提供します。 
  
このガイダンスに加えて、次の操作を実行することをお勧めします。この記事では、[ハッカーやマルウェアからのアカウントとデバイスの保護](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)について説明します。 それらの操作を次に示します。
  
- 強力なパスワードの使用
    
- デバイスを保護する
    
- Windows 10 および Mac Pc でセキュリティ機能を有効にする
    
また、次の記事で推奨されている操作を実行して、ユーザーが個人のメールアカウントを保護することをお勧めします。
  
- [Outlook.com メールアカウントを保護する](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba.aspx)
    
- [2段階認証を使用して Gmail アカウントを保護する](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
    
## <a name="3-use-dedicated-admin-accounts"></a>3: 専用の管理者アカウントを使用する
<a name="admin"> </a>

Office 365 または Microsoft 365 環境を管理するために使用する管理アカウントには、昇格された特権が含まれています。 これらは、ハッカーおよびサイバー犯罪者にとって重要な目標です。 管理用にのみ管理者アカウントを使用します。 管理者は、管理者ではない通常の使用に対して個別のユーザーアカウントを持っている必要があります。ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ、管理アカウントを使用してください。 追加の推奨事項:
  
- 管理者アカウントが多要素認証にも設定されていることを確認してください。 
    
- 管理者アカウントを使用する前に、個人の電子メールアカウントを含む、関連のないブラウザーセッションとアプリをすべて閉じてください。
    
- 管理タスクを完了したら、ブラウザーセッションからログアウトしてください。
    
## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: メールのマルウェアに対する保護レベルを上げる
<a name="malware"> </a>

Office 365 または Microsoft 365 環境にはマルウェアからの保護が含まれていますが、マルウェアによく使用されるファイルの種類の添付ファイルをブロックすることによって、この保護を向上させることができます。 電子メールでマルウェア保護を強化するには、[簡単なトレーニングビデオ](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)を表示するか、次の手順を実行します。
  
1. に[https://protection.office.com](https://protection.office.com)移動し、管理者アカウントの資格情報でサインインします。 
    
2. Office 365 &amp;セキュリティ/コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー** \> **のマルウェア対策**] を選択します。
    
3. この会社全体のポリシーを編集するには、既定のポリシーをダブルクリックします。
    
4. [**設定**] を選択します。
    
5. [**一般的な添付ファイルの種類のフィルター**] で、 **[オン] を選択し**ます。 ブロックされているファイルの種類は、このコントロールのすぐ下のウィンドウに一覧表示されます。 必要に応じて、後でファイルの種類を追加または削除できます。
    
6. [保存] を選択し**ます。**
    
詳細については、「[マルウェア対策保護](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)」を参照してください。
  
## <a name="5-protect-against-ransomware"></a>5: ランサムウェアから保護する
<a name="ransomware"> </a>

ランサムウェアは、ファイルの暗号化またはコンピューター画面のロックによってデータへのアクセスを制限します。 その後、データにアクセスするために exchange では、通常、ビットコインのような cryptocurrencies のような形式で "ransom" を要求することによって、被害からのデータを組み込みます。 
  
ランサムウェアから保護するには、1つまたは複数のメールフロールールを作成して、ランサムウェアによく使用されるファイル拡張子をブロックするか、またはこれらの添付ファイルを電子メールで受信するユーザーに警告します。 まず、次の2つのルールを作成することをお勧めします。
  
- マクロを含む Office ファイル添付ファイルを開く前に、ユーザーに警告します。 ランサムウェアは、マクロ内で非表示にすることができます。そうしないと、ユーザーが知らないユーザーからこれらのファイルを開かないように警告されます。 
    
- ランサムウェアまたはその他の悪意のあるコードを含む可能性があるファイルの種類をブロックします。 まず、実行可能ファイルの一般的な一覧を示します (次の表を参照)。 これらの実行可能ファイルの種類のいずれかを使用していて、それらが電子メールで送信されることが組織で想定されている場合は、これらを前のルールに追加します (ユーザーに警告します)。
    
メールトランスポートルールを作成するには、[簡単なトレーニングビデオ](https://support.office.com/article/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)を表示するか、次の手順を実行します。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. [**メールフロー** ] カテゴリで、[**ルール**] を選択します。
    
3. [ **+**] を選択し、**新しいルールを作成**します。
    
4. ダイアログボックスの下部にある [* * * *] を選択すると、オプションの完全なセットが表示されます。 
    
5. 各ルールについて、次の表の設定を適用します。 これらの設定を変更しない場合は、既定の設定のままにしておきます。
    
6. [**保存**] を選択します。
    
|**設定**|**Office ファイルの添付ファイルを開く前にユーザーに警告を発する**|**ランサムウェアまたはその他の悪意のあるコードを含む可能性があるファイルの種類をブロックする**|
|:-----|:-----|:-----|
|名前  <br/> |ランサムウェア対策ルール: ユーザーに警告を発する  <br/> |ランサムウェア対策ルール: ファイルの種類をブロックする  <br/> |
|このルールを適用する条件 . .  <br/> |任意の添付ファイル。 . . ファイル拡張子が一致する。 . .  <br/> |任意の添付ファイル。 . . ファイル拡張子が一致する。 . .  <br/> |
|単語または語句を指定する  <br/> |次のファイルの種類を追加します。  <br/> normal.dotm、.docm、.xlsm、sltm、.xla、xlam、xll、pptm、potm、ppam、pptm、sldm  <br/> |次のファイルの種類を追加します。  <br/> ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、ジョブ、js、jse、lnk、pcd、[mdb]、[mde]、[]、[reg]、[shs]、[mst]、[]、[url]、[wsh]、[]、[wsc  <br/> |
|次の手順を実行します。 . .  <br/> |受信者にメッセージで通知します。  <br/> |[メッセージをブロックする。 . . メッセージを拒否して説明を含める  <br/> |
|メッセージテキストを指定する  <br/> |これらの種類のファイルは、悪意のあるコードが含まれている可能性があり、送信者が安全ではないことを認識している場合を除き、開かないでください。  <br/> ||
   
> [!TIP]
> また、[手順 4](#4-raise-the-level-of-protection-against-malware-in-mail)で、ブロックするファイルをマルウェア対策リストに追加することもできます。

詳細については、以下を参照してください。
  
- [ランサムウェアの処理方法](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [OneDrive を復元する](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    
## <a name="6-stop-auto-forwarding-for-email"></a>6: メールの自動転送を停止する
<a name="forwarding"> </a>

ユーザーのメールボックスにアクセスするハッカーは、メールを自動的に転送するようにメールボックスを構成することにより、メールを exfiltrate することができます。 これは、ユーザーの認識なしでも発生する可能性があります。 メールフロールールを構成することによって、このような事態を防ぐことができます。 
  
メールトランスポートルールを作成するには、次のようにします。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. [**メールフロー** ] カテゴリで、[**ルール**] を選択します。
    
3. [ **+**] を選択し、**新しいルールを作成**します。
    
4. ダイアログボックスの下部にある [**その他のオプション**] を選択すると、オプションの完全なセットが表示されます。 
    
5. 次の表の設定を適用します。 これらの設定を変更しない場合は、既定の設定のままにしておきます。
    
6. [**保存**] を選択します。
    
|**設定**|**Office ファイルの添付ファイルを開く前にユーザーに警告を発する**|
|:-----|:-----|
|名前  <br/> |外部ドメインへの電子メールの自動転送を禁止する  <br/> |
|次の場合にこのルールを適用する...  <br/> |送信者。 . . 外部/内部。 . . 組織内  <br/> |
|条件を追加する  <br/> |メッセージのプロパティ。 . . メッセージの種類を含めます。 . . 自動転送  <br/> |
|次の手順を実行します。  <br/> |[メッセージをブロックする。 . . メッセージを拒否し、説明を含めます。  <br/> |
|メッセージテキストを指定する  <br/> |この組織外の電子メールの自動転送は、セキュリティ上の理由から禁止されています。  <br/> |
   
## <a name="7-use-office-message-encryption"></a>7: Office メッセージの暗号化を使用する
<a name="encryption"> </a>

Office メッセージの暗号化は、Microsoft 365 に含まれています。 これは既にセットアップされています。 Office メッセージの暗号化を使用すると、組織は組織内外のユーザー間で暗号化された電子メールメッセージを送受信できます。 Office 365 Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他のメール サービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
Office メッセージの暗号化では、メールを送信するときに2つの保護オプションが提供されます。
  
- 転送不可
    
- 暗号化
    
組織で、社外秘などの電子メールにラベルを適用する追加オプションを構成している場合があります。
  
### <a name="to-send-protected-email"></a>保護された電子メールを送信するには

[PC 用 Outlook] で、電子メールの [**オプション**] を選択し、[**アクセス許可**] を選択します。 
  
![Outlook での電子メールメッセージの暗号化](../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)
  
Outlook.com で、[電子メールで**保護**] を選択します。 既定の保護は**転送されません**。 これを暗号化に変更するには、[**アクセス許可** \>の**暗号化**の変更] を選択します。 
  
![Outlook.com での電子メールメッセージの暗号化](../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)
  
### <a name="to-receive-encrypted-email"></a>暗号化された電子メールを受信するには

受信者が Outlook 2013 または Outlook 2016 および Office 365 電子メールアカウントを持っている場合、閲覧ウィンドウでのアイテムの制限されたアクセス許可についての警告が表示されます。 メッセージを開いた後は、受信者は他のメッセージと同じように表示できます。
  
受信者が別の電子メールクライアントまたはメールアカウント (Gmail、Yahoo など) を使用している場合は、ユーザーが電子メールメッセージを読むためにサインインするか、ワンタイムパスコードを要求して web ブラウザーでメッセージを表示できるようにするリンクが表示されます。 ユーザーが電子メールを受信していない場合は、スパムや迷惑メールフォルダーを確認してもらいます。 
  
詳細については、「 [Outlook FOR PC での暗号化されたメッセージの送信、表示、および返信](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)」を参照してください。
  
## <a name="8-protect-your-email-from-phishing-attacks"></a>8. フィッシング攻撃からメールを保護する
<a name="phishing"> </a>

Office 365 または Microsoft 365 環境用に1つ以上のカスタムドメインを構成した場合は、対象となるフィッシング対策保護を構成できます。 ATP のフィッシング対策保護 (Office 365 Advanced Threat Protection の一部) は、悪意のある偽造ベースのフィッシング攻撃やその他のフィッシング攻撃から組織を保護するのに役立ちます。 カスタムドメインを構成していない場合は、この手順を実行する必要はありません。
  
最も重要なユーザーとカスタムドメインを保護するためのポリシーを作成して、この保護を開始することをお勧めします。 
  
![ATP のフィッシング対策ポリシーを作成する](../media/security-and-compliance-center.png)
  
ATP のフィッシング対策ポリシーを作成するには、[簡単なトレーニングビデオ](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)を参照するか、次の手順を実行します。
  
1. [https://protection.office.com](https://protection.office.com) に移動します。 
    
2. Office 365 セキュリティ&amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下の [**ポリシー**] を選択します。
    
3. [ポリシー] ページで、[ **ATP のフィッシング対策**] を選択します。
    
4. [フィッシング対策] ページで、[ **+ 作成**] を選択します。 ウィザードが起動して、フィッシング対策ポリシーを定義する手順を実行します。
    
5. 下の表に示す推奨事項に従って、ポリシーの名前、説明、および設定を指定します。 詳細については、「 [ATP のフィッシング対策ポリシーのオプションについ](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)て」を参照してください。 
    
6. 設定を確認したら、必要に応じて [**このポリシーを作成**する] または [**保存**] を選択します。
    
| | |**設定またはオプション**|の**推奨設定** <br/>
|拡張子  <br/> |ドメインおよび最も重要なキャンペーンスタッフ  <br/> | |Description  <br/> |最も重要なスタッフとドメインが偽装されていないことを確認します。  <br/> | |保護するユーザーを追加する  <br/> |[ **+ 条件の追加**] を選択すると、受信者はになります。 ユーザー名を入力するか、候補、キャンペーンマネージャー、およびその他の重要なスタッフメンバーの電子メールアドレスを入力します。 偽装から保護する内部および外部アドレスを最大20個まで追加できます。  <br/> | |保護するドメインを追加する  <br/> |[ **+ 条件を追加する] を選択すると、受信者のドメインは**になります。 Microsoft 365 サブスクリプションに関連付けられているカスタムドメインを入力します (定義されている場合)。 複数のドメインを入力できます。  <br/> | |アクションの選択  <br/> |偽装ユーザーによって電子メールが送信される場合: [**メッセージを別の電子メールアドレスにリダイレクトする**] を選択し、セキュリティ管理者の電子メールアドレスを入力します。たとえば、securityadmin@contoso.com のようになります。          偽装ドメインによって電子メールが送信される場合: [**検疫メッセージ**] を選択します。  <br/> | |メールボックスインテリジェンス  <br/> |既定では、新しいフィッシング対策ポリシーを作成すると、メールボックスインテリジェンスが選択されます。 最適な結果が得られるように、この設定は **[オン]** のままにしておいてください。  <br/> | |信頼できる差出人とドメインを追加する  <br/> |この例では、オーバーライドを定義しません。  <br/> | |適用対象  <br/> |[**受信者ドメイン**] を選択します。 **[これらのいずれか]** では、**[選択]** を選択します。 **[+ 追加]** を選択します。 一覧のドメイン名の横にあるチェックボックスをオンにして、[**追加**] を選択します (contoso.com など)。 [**完了**] を選択します。  <br/> |
   
詳細については、「 [Office 365 ATP のフィッシング対策ポリシーを](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)セットアップする」を参照してください。
  
## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9: ATP の安全な添付ファイルを使用して悪意のある添付ファイルやファイルを保護する
<a name="atp"> </a>

ユーザーは、ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを日常的に送信、受信、共有します。 電子メールメッセージを見るだけで、添付ファイルが安全か悪意かを知ることは常に容易ではありません。 Office 365 Advanced Threat Protection には、ATP の安全な添付ファイルの保護が含まれていますが、既定ではこの保護は有効になっていません。 この保護の使用を開始するには、新しいルールを作成することをお勧めします。 この保護は、SharePoint、OneDrive、Microsoft Teams のファイルにまで及びます。
  
ATP の安全な添付ファイルポリシーを作成するには、[簡単なトレーニングビデオ](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)を表示するか、次の手順を実行します。
  
1. に[https://protection.office.com](https://protection.office.com)移動し、管理者アカウントでサインインします。 
    
2. Office 365 セキュリティ&amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下の [**ポリシー**] を選択します。
    
3. [ポリシー] ページで、[ **ATP の安全な添付ファイル**] を選択します。
    
4. [安全な添付ファイル] ページで、[ **SharePoint、OneDrive、Microsoft Teams 用の ATP を有効**にする] チェックボックスをオンにして、この保護を広く適用します。 
    
5. 新しい**+** ポリシーを作成する場合に選択します。 
    
6. 次の表の設定を適用します。 
    
7. 設定を確認したら、必要に応じて [**このポリシーを作成**する] または [**保存**] を選択します。
    
| | |**設定またはオプション**|の**推奨設定** <br/>| |拡張子  <br/> |検出されたマルウェアを含む現在および今後の電子メールをブロックします。  <br/> | |Description  <br/> |検出されたマルウェアを含む、現在および今後の電子メールと添付ファイルをブロックする。  <br/> | |添付ファイルの保存に関する不明なマルウェア応答  <br/> |**検出されたマルウェアを含む現在および今後の電子メールと添付ファイルをブロックする**を選択します。  <br/> | |検出時に添付ファイルをリダイレクトする  <br/> |リダイレクトを有効にする (このボックスをオンにする) 管理者アカウントまたは検疫用のメールボックスのセットアップを入力します。          マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用します (このチェックボックスをオンにします)。  <br/> | |適用対象  <br/> |受信者のドメインはです。 . . ドメインを選びます。  <br/> |
   
詳細については、「 [Office 365 ATP のフィッシング対策ポリシーを](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)セットアップする」を参照してください。
  
## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10: ATP の安全なリンクによるフィッシング攻撃から保護する
<a name="phishingatp"> </a>

ハッカーは、電子メールやその他のファイル内のリンクに悪意のある web サイトを表示しないことがあります。 Office 365 の ATP の安全なリンク (ATP の安全なリンク)、Office 365 Advanced Threat Protection の一部では、電子メールメッセージや Office ドキュメント内の web アドレス (Url) をクリックすると、組織の保護に役立ちます。 保護は、ATP の安全なリンクポリシーによって定義されます。
  
次の手順を実行することをお勧めします。
  
- 既定のポリシーを変更して、保護を強化します。
    
- ドメイン内のすべての受信者を対象とした新しいポリシーを追加します。
    
ATP の安全なリンクを取得するには、[短いトレーニングビデオ](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)を表示するか、次の手順を実行します。
  
1. に[https://protection.office.com](https://protection.office.com)移動し、管理者アカウントでサインインします。 
    
2. Office 365 セキュリティ&amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下の [**ポリシー**] を選択します。
    
3. [ポリシー] ページで、[ **ATP の安全なリンク**] を選択します。
    
既定のポリシーを変更するには、次のようにします。
  
1. [安全なリンク] ページの [**組織全体に適用されるポリシー**] で、[**既定**のポリシー] を選択します。 
    
2. [**電子メール以外のコンテンツに適用する設定**] で、[ **office 365 ProPlus]、[office for IOS、および Android**] を選択します。
    
3. [**保存**] を選択します。 
    
ドメイン内のすべての受信者を対象とした新しいポリシーを作成するには、次のようにします。
  
1. [安全なリンク] ページの [**組織全体に適用されるポリシー**] **+** で、[新しいポリシーの作成] を選択します。 
    
2. 次の表に示す設定を適用します。
    
3. [**保存**] を選択します。 
    
| | |**設定またはオプション**|の**推奨設定** <br/>| |拡張子  <br/> |ドメイン内のすべての受信者に対する安全なリンクポリシー  <br/> | |メッセージ内の不明な潜在的な悪意のある Url に対するアクションを選択する  <br/> |[オン] を選択すると **、ユーザーがリンクをクリックしたときに、既知の悪意のあるリンクの一覧に対して、url が書き換えられ、チェックされ**ます。  <br/> | |安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする  <br/> |このボックスを選択します。  <br/> | |適用対象  <br/> |受信者のドメインはです。 . . ドメインを選びます。  <br/> |
   
詳細については、「 [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)」を参照してください。