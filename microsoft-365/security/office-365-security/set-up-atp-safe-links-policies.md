---
title: Office 365 の ATP の安全なリンクポリシーを設定する
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 安全なリンクポリシーを設定して、Word、Excel、PowerPoint、および Visio ファイル内の悪意のあるリンクや、電子メールメッセージだけで組織を保護します。
ms.openlocfilehash: 54b896616cf09c84525b812fed6fb3f35b07bf10
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617220"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Office 365 の ATP の安全なリンクポリシーを設定する

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[Atp の安全なリンク](atp-safe-links.md)は、 [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) の機能で、フィッシングやその他の攻撃で使用されている悪意のあるリンクから組織を保護するのに役立ちます。 [セキュリティ &amp; コンプライアンスセンターに必要なアクセス許可](permissions-in-the-security-and-compliance-center.md)がある場合は、ユーザーが Web アドレス (url) をクリックしたときに組織が保護されるようにするために、ATP の安全なリンクポリシーを設定することができます。 ATP の安全なリンクポリシーを構成して、Office ドキュメント内の電子メールと Url の Url をスキャンできます。

ATP の安全なリンクが有効になっている場合、ユーザーが電子メール内のリンクをクリックすると、その URL が組織のカスタムブロックされた URL リストによってブロックされるか、URL が悪意のあるものと判断されると、警告ページが表示されます。
  
[新機能は ATP に継続的に追加](office-365-atp.md#new-features-in-office-365-atp)されています。 新機能が追加されたときに、既存の ATP の安全なリンクポリシーを調整する必要がある場合があります。

## <a name="what-to-do"></a>行うこと 
  
1. 前提条件を確認します。
    
2. すべてのユーザーに適用される既定の ATP の安全なリンクポリシーを確認して編集します。 たとえば、 [ATP の安全なリンクに対し](set-up-a-custom-blocked-urls-list-atp.md)て、カスタムのブロックされた url リストを設定できます。
    
3. 特定の電子メール受信者のポリシーを追加または編集します。これには、 [ATP の安全なリンクのためのカスタムの "リライト not リライト" url リストの設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)が含まれます。
    
4. 最近の変更の設定を含む、ATP の安全なリンクのポリシーオプション (この記事では) について説明します。
    
## <a name="step-1-review-the-prerequisites"></a>手順 1: 前提条件を確認する

- 組織に[Office 365 Advanced Threat Protection](office-365-atp.md)があることを確認します。
    
- 必要なアクセス許可を持っていることを確認してください。 ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。 次の表では、いくつかの例について説明します。 <br>

    |役割  |参照先/割り当て方法  |
    |---------|---------|
    |グローバル管理者 |Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。 (詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)てを参照してください)。         |
    |セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください) |

    役割とアクセス許可の詳細については、「[セキュリティ/ &amp; コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- Office クライアントが[先進認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用するように構成されていることを確認します (これは、office ドキュメントの ATP の安全なリンク保護に対して行われます)。
    
- [ATP の安全なリンクポリシーオプション](#step-4-learn-about-atp-safe-links-policy-options)(この記事では) について説明します。 

- 新規または更新されたポリシーがすべての Microsoft 365 データセンターに蔓延するまで最大30分かかります。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>手順 2: すべてのユーザーに適用される ATP の安全なリンクポリシーを定義 (または確認) します。

[Office 365 Advanced Threat Protection](office-365-atp.md)を使用している場合は、組織内のすべてのユーザーに適用される既定の ATP 安全なリンクポリシーがあります。 必ず確認してください。必要に応じて、既定のポリシーを編集します。
  
1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。 
    
2. 左側のナビゲーションで、[**脅威の管理**] の下にある [ ** \> ポリシー** **セーフリンク**] を選択します。
    
3. **[組織全体に適用されるポリシー]** セクションで、**[既定]**、**[編集]** (編集ボタンは鉛筆に似ています) の順に選びます。<br/>![[編集] をクリックして安全なリンクの保護に関する既定のポリシーを編集する](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. [**次の url をブロック**する] セクションで、組織内のユーザーが閲覧できないようにする1つ以上の url を指定します。 (「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-atp.md)」を参照してください)。
    
5. [**電子メール以外のコンテンツに適用する設定**] セクションで、使用するオプションを選択 (またはクリア) します。 (すべてのオプションを選択することをお勧めします)。 
    
6. **[保存]** を選択します。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>手順 3: 特定の電子メール受信者に適用される ATP の安全なリンクポリシーを追加 (または編集) します。

すべてのユーザーに適用される既定の ATP の安全なリンクポリシーを確認 (または編集) した後、次の手順として、特定の受信者に適用する追加のポリシーを定義します。 たとえば、追加のポリシーを定義することによって、既定のポリシーに対する例外を指定できます。 
  
1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。 
    
2. 左側のナビゲーションで、[**脅威の管理**] の下にある [**ポリシー**] を選択します。
    
3. [**安全なリンク**] を選択します。
    
4. [**特定の受信者に適用されるポリシー** ] セクションで、[**新規**] を選択します (新しいボタンは、プラス記号 () に似て **+** います)。<br/>![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. ポリシーの名前、説明、設定を指定します。<br/>**例:**"直接クリックしない" というポリシーを設定するには、組織内の特定のグループのユーザーが、ATP の安全なリンク保護を行わずに特定の web サイトをクリックすることを許可しないようにします。次の推奨設定を指定することができます。 
    
    - [**名前**] ボックスに「直接クリックしない」と入力します。

    - [**説明**] ボックスに、次のような説明を入力します。特定のグループのユーザーが、ATP の安全なリンク確認を行わずに web サイトをクリックするのを防ぐことができます。

    - **[アクションの選択**] セクションで、[**オン**] を選択します。

    - 疑わしい url およびファイルを参照する url に対して URL 分析を有効にする場合は、[**不審なリンクおよびファイルを指すリンクに対してリアルタイム URL スキャンを適用**する] を選択します (推奨)。 さらに、url が完全にスキャンされた後にのみユーザーにメッセージを受信させたい場合は、[ **url のスキャンが完了するのを待機する**] を選択して、メッセージを配信します。

    - 組織内のユーザー間で送信されるメッセージの安全なリンクを有効にする場合は **、[組織内で送信されるメッセージに対して安全なリンクを適用**する] を選択します (推奨)。

    - 個々のユーザーによる*スキャンの進行*または*url ブロック*された通知ページを上書きしたくない場合は、[**ユーザーが元の url に**移動できないようにする] を選択します。

    - (オプション)[**次の url を書き換えない**] セクションで、組織に対して安全と見なされる1つ以上の url を指定します。 (「 [ATP Safe Links を使用して、ユーザー設定の "書き込み不可" url リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください)

    - [**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。 [**追加**] を選択し、[ **OK]** を選択します。
    
6. **[保存]** を選択します。

> [!NOTE]
> ATP の安全なリンクポリシー優先度の高いポリシーが優先されます。 ユーザーが2つ以上のポリシーの対象になっている場合は、優先度の高いポリシーのみが有効になります。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>手順 4: ATP の安全なリンクポリシーのオプションについて学習する

ATP の安全なリンクポリシーを設定または編集すると、いくつかのオプションが表示されます。 これらのオプションがどのようなものかがわからない場合は、次の表で各オプションとその影響について説明します。 次の2種類の ATP 安全なリンクポリシーを定義または編集することに注意してください。
- すべてのユーザーに適用される[既定のポリシー](#default-policy-options) 。そして  
- [特定の受信者の追加ポリシー](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>既定のポリシーオプション

既定のポリシーオプションは、組織内のすべてのユーザーに適用されます。

|このオプション  |機能  |
|---------|---------|
| **次の Url をブロックする** <br/>    | 自動でブロックされる Url のカスタムリストを組織で使用できるようにします。 ユーザーがこのリストの URL をクリックすると、URL がブロックされる理由を説明する[警告ページ](atp-safe-links-warning-pages.md)が表示されます。 詳細については、「 [Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-atp.md)」を参照してください。 |
| **Microsoft 365 Apps for enterprise、Office for iOS、および Android** <br/>    | このオプションを選択すると、ATP の安全なリンク保護は、ユーザーが Office 365 にサインインしている場合に、Windows または Mac OS 上の Word、Excel、および PowerPoint ファイル、Outlook の電子メールメッセージ、iOS または Android デバイス上の Office ドキュメント、Windows の Visio 2016 ファイル、および web バージョンの Office アプリ (Word、PowerPoint、Excel、Outlook、および OneNote) で開かれている |
| **ユーザーが ATP の安全なリンクをクリックしたときに追跡しない** <br/>  | このオプションが選択されている場合は、[Word、Excel、PowerPoint、Visio ドキュメント、および Outlook の電子メールメッセージのデータは保存されません] をクリックします。  <br/> |
|**ユーザーが元の URL に対して ATP の安全なリンクをクリックできないようにします。** <br/> |このオプションが選択されている場合、ユーザーは、悪意があると判断された URL に[警告ページ](atp-safe-links-warning-pages.md)をスキップすることはできません。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>特定の電子メールの受信者に適用されるポリシー

|このオプション  |機能  |
|---------|---------|
|**オフ** <br/> |電子メールメッセージ内の Url はスキャンされません。  <br/> 特定の受信者グループの電子メールメッセージ内の Url をスキャンしないルールなどの例外ルールを定義できます。  <br/> |
|**On** <br/> |ユーザーが電子メールメッセージ内の Url をクリックして、Windows 上の Outlook (C2R) 内で ATP の安全なリンクを有効にする際に、ATP の安全なリンク保護を通じてユーザーをルーティングするために Url を書き換えます。  <br/> ブロックされた url または悪意のある Url の一覧に対してクリックしたときに URL をチェックし、URL の評価が有効でない場合は、バックグラウンドで URL の分析を非同期的にトリガーします。  <br/> |
|**疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用する** <br/> |このオプションを選択すると、ダウンロード可能なコンテンツを参照する疑わしい Url とリンクがスキャンされます。  <br/> |
|**メッセージを配信する前に URL スキャンが完了するまで待機する** <br/> |このオプションが選択されている場合、スキャンする Url が含まれているメッセージは、Url がスキャンを終了し、メッセージが配信される前に安全であることが確認されるまで保持されます。  <br/> |
|**組織内で送信されるメッセージに安全なリンクを適用する** <br/> | このオプションを選択して選択すると、電子メールアカウントが Office 365 でホストされている場合に、組織内のユーザー間で送信される電子メールメッセージに対して ATP の安全なリンク保護が適用されます。  <br/> |
|**ユーザーのクリックを追跡しない** <br/> |このオプションが選択されている場合は、[外部送信者からの電子メール] の [データ] をクリックします。 URL [組織内で送信された電子メールメッセージ内のリンクの追跡] [現在サポートされていません]。  <br/> |
|**ユーザーが元の URL にクリックできないようにする** <br/> |このオプションが選択されている場合、ユーザーは、悪意があると判断された URL に[警告ページ](atp-safe-links-warning-pages.md)をスキップすることはできません。  <br/> |
|**次の Url を書き換えないでください。** <br/> |Url をそのまま残します。 組織内の特定の電子メール受信者グループに対して、スキャンを必要としない安全な Url のカスタムリストを保持します。  追加の詳細については、「 [ATP Safe Links を使用してカスタムの url リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください。これには、ワイルドカードのアスタリスク () のサポートに関する最新の変更が含まれてい \* ます。  <br/> |
   
## <a name="next-steps"></a>次の手順

ATP の安全なリンクポリシーを設定すると、レポートを表示することによって、ATP が組織でどのように機能するかを確認できます。 詳細については、以下のリソースを参照してください。

- [Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)

- [セキュリティ/コンプライアンスセンターのエクスプローラーを使用する &amp;](threat-explorer.md)

ATP に関する新機能を常に活用してください。 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を参照してください。
