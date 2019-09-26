---
title: Office 365 の非アクティブなメールボックスの概要
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: メールボックスを非アクティブなメールボックスに変換することにより、元従業員のメールボックスの内容を保持する方法について説明します。 メールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーをメールボックスに適用してから、対応する Office 365 アカウントを削除することによって、これを行うことができます。
ms.openlocfilehash: acfe0a3d8f3865cf0e30a938970235bf31dfbce4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085074"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Office 365 の非アクティブなメールボックスの概要

組織では、退職後も元従業員の電子メールを保持しなければならないことがあります。 組織が定める保存要件に応じて、メールボックスの内容を、雇用が終了してから数か月、数年、または無期限に保持しなければならないことがあります。 メールを保持する期間に関係なく、Office 365 で非アクティブなメールボックスを作成して、元従業員のメールボックスを保持することができます。 
  
## <a name="what-are-inactive-mailboxes"></a>非アクティブなメールボックスとは

従業員が組織を退職した場合 (または、延長された休暇が発生した場合)、自分の Office 365 アカウントを削除することができます。 従業員のメールボックスデータは、アカウントが削除された後、30日間保持されます。 この期間中は、アカウントを復元することによってメールボックスのデータを回復することができます。 30日後、データは完全に削除されます。
  
ただし、組織で元従業員のメールボックスの内容を保持する必要がある場合は、メールボックスを訴訟ホールドの対象にするか、セキュリティ & コンプライアンスセンターのメールボックスに Office 365 アイテム保持ポリシーを適用することによって、メールボックスを非アクティブなメールボックスに変更できます。次に、対応する Office 365 アカウントを削除します。 The contents of an inactive mailbox are retained for the duration of the Litigation Hold placed on the mailbox or the retention period of the Office 365 retention policy applied to it before the mailbox was deleted. You can still recover the corresponding user account for a 30-day period. ただし、30日が経過すると、非アクティブなメールボックスは、保持ポリシーまたはアイテム保持ポリシーが削除されるまで、Office 365 に保持されます。 
  
> [!NOTE]
> 2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>非アクティブなメールボックスと Office 365 アイテム保持ポリシー

訴訟ホールドに加えて、セキュリティ & コンプライアンスセンターで新しい Office 365 アイテム保持ポリシー機能を使用することで、メールボックスを非アクティブにすることもできます。 To use a retention policy to make an inactive mailbox: 
  
- コンテンツを保持するか、コンテンツを保持してから削除するように構成する必要があります。 単にコンテンツを削除するようにアイテム保持ポリシーが構成されている場合、ポリシーが適用されるメールボックスは、メールボックスの削除の際に非アクティブになりません。

- (Skype 関連のコンテンツがユーザーのメールボックスに保管されるため) アイテム保持ポリシーを Exchange メールボックスまたは Skype for Business の場所に適用する必要があります。 
    
- 検索クエリに合致するアイテムだけを保持するように、クエリ ベースにすることができます。 
    
Office 365 アイテム保持ポリシーの構成の詳細については、[アイテム保持ポリシーの概要](retention-policies.md)を参照してください。
  
アイテム保持ポリシーを使用して非アクティブなメールボックスを作成すると、Office 365 は非アクティブなメールボックスに対するアイテム保持ポリシーの処理を続行します。 つまり、コンテンツを保持した後に削除するようにアイテム保持ポリシーが構成されている場合には、保持期間が期限切れになるとアイテムは [回復可能なアイテム] フォルダーに移され、最終的に非アクティブなメールボックスから消去されます。 Office 365 アイテム保持ポリシーがアイテムを削除するように構成されていない場合には、(メールボックスが非アクティブになる前に) ユーザーによって完全に削除されていないアイテムは [回復可能なアイテム] フォルダーに移されず、メールボックスが非アクティブになった後、無期限に保持されます。 
  
特に、非アクティブなメールボックスのために Office 365 アイテム保持ポリシーを作成することを考慮できます。そうすべきいくつかの理由と留意点を次に示します。
  
- 元従業員に関する組織の要件に合致させるため、必要な長さの期間だけメールボックスの内容を保持するように、アイテム保持ポリシーを構成できます。
    
- 非アクティブなメールボックスを特定するには、アイテム保持ポリシーが非アクティブなメールボックスにのみ適用されるため、この方法を使用することをお勧めします。
    
- 組織内の非アクティブなメールボックスに割り当てられているアイテム保持ポリシーをすばやく識別することができます。 This will make it easier to change the retention (or deletion) settings if necessary. また、セキュリティ & コンプライアンスセンターを使用してポリシーから削除するだけで済むため、非アクティブなメールボックスを完全に削除することも容易になります。 それ以外の場合は、Exchange Online PowerShell を使用して、非アクティブなメールボックスから訴訟ホールドを削除するか、セキュリティ & コンプライアンスセンターの PowerShell を使用して、組織全体の Office 365 アイテム保持ポリシーから非アクティブなメールボックスを除外する必要があります。
    
- Office 365 アイテム保持ポリシーを専ら非アクティブなメールボックスのために作成する場合、最大 1,000 個のメールボックスをポリシーに追加できます。非常に大規模な組織の場合には、非アクティブなメールボックスのために使用する Office 365 アイテム保持ポリシーを複数作成する必要があるかもしれません。

> [!CAUTION]
> アイテム保持ポリシーを使用してメールボックスを非アクティブにする場合は、対応する Office 365 ユーザーアカウントを削除する前に、メールボックスのユーザープリンシパル名 (UPN) を変更または削除しないでください。 また、メールボックスを非アクティブにする前に、プライマリ SMTP アドレス (UPN から派生したもの) を変更したり、メールボックスに関連付けられているセカンダリ SMTP アドレスのリストからこの電子メールアドレスを削除したりしないでください。 保持ポリシーが適用された時点でメールボックスに割り当てられていた UPN または電子メールアドレスを変更してから、そのユーザーアカウントを削除してメールボックスを非アクティブにした場合、そのメールボックスを保持する必要がなくなった場合に、非アクティブなメールボックスを削除することはできません。なく. これは、非アクティブなメールボックスを、アイテム保持ポリシーが最初にメールボックスに適用されたときに存在したものとは異なる UPN または電子メールアドレスを使用してアイテム保持ポリシーから削除できないためです。 非アクティブなメールボックスの削除の詳細については、「 [Office の非アクティブなメールボックスを削除する 365](delete-an-inactive-mailbox.md)」を参照してください。
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>非アクティブなメールボックスと電子情報開示のケース保持

セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられたホールドがメールボックスに配置されている場合、メールボックスまたはユーザーの Office 365 アカウントが削除されると、メールボックスは非アクティブなメールボックスになります。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Additionally, you can't create a time-based eDiscovery hold. That's means content in an inactive mailbox will be retained forever or until the hold is removed and the inactive mailbox is deleted. Therefore, we recommend using a Litigation Hold or an Office 365 retention policy for inactive mailboxes.
  
電子情報開示ケースと保留リストの詳細については、「[電子情報開示ケース](ediscovery-cases.md)」を参照してください。
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>非アクティブなメールボックスと Office 365 のラベル

Office 365 のラベルは、ガバナンスのために組織内の電子メール データを分類し、その分類に基づいて保持ルールを実施するのに役立ちます。 ユーザーが手動で、または管理者が自動的に、電子メール アイテムにラベルを適用することができ、電子メール アイテムはそれに割り当てられている 1 つのラベルだけを保持できます。 ユーザーのメールボックス内の1つの電子メールアイテムにラベルが割り当てられている場合 (アイテムを保持または保持してから削除するように構成されている場合)、メールボックスまたはユーザーの Office 365 アカウントが削除されると、メールボックスは非アクティブなメールボックスになります。 電子情報開示ケース保持の場合と同様に、ラベルを使用してメールボックスを非アクティブにすることは推奨されません。 代わりに、訴訟ホールド、または Office 365 アイテム保持ポリシーを使用することが推奨されています。 ラベルのケースでは、ラベルが電子メール アイテムに適用されていることに気づかずに、ユーザーのアカウントを削除すると、誤ってメールボックスを非アクティブにしてしまう可能性があるので注意してください。 
  
ラベルの詳細については、[ラベルの概要](labels.md)を参照してください。
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非アクティブなメールボックスと Exchange MRM アイテム保持ポリシー

非アクティブになったときに Exchange アイテム保持ポリシー (メッセージングレコード管理または MRM 機能) がメールボックスに適用された場合、削除ポリシー (**削除**保持アクションで構成された保持タグ) は、非アクティブなメールボックスで引き続き処理されます。 つまり、保持期間を過ぎると、削除ポリシーのタグが付けられたアイテムは [回復可能なアイテム] フォルダーに移動されます。 それらのアイテムは保持期間を過ぎると非アクティブなメールボックスから消去されます。 非アクティブなメールボックスの保持期間が指定されていない場合、[回復可能なアイテム] フォルダー内のアイテムは無期限に保持されます。 
  
逆に、非アクティブなメールボックスに割り当てられた保持ポリシーにアーカイブ ポリシー ( **MoveToArchive** 保持アクションが設定された保持タグ) が含まれている場合、それらはすべて無視されます。つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。無期限に保持されます。 
  
## <a name="creating-an-inactive-mailbox"></a>非アクティブなメールボックスの作成

メールボックスを非アクティブにするには、メールボックスに Exchange Online (プラン 2) ライセンスを割り当て、メールボックスに訴訟ホールドまたは Office 365 アイテム保持ポリシーを設定してからメールボックスを削除できるようにする必要があります。 メールボックスが削除されると、それに関連付けられていた Exchange Online ライセンスを新しいユーザーに割り当てることができるようになります。 非アクティブなメールボックスは、継続的なライセンスを必要としません。
  
次の表は、各種の保持シナリオについて、非アクティブなメールボックスを作成するプロセスを要約しています。 詳細については、「 [Office 365 で非アクティブなメールボックスを管理](create-and-manage-inactive-mailboxes.md)する」を参照してください。
  
|**目的**|**操作**|**結果**|
|:-----|:-----|:-----|
|従業員の退職後にメールボックスの内容を無期限に保持する  <br/> | メールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシー (コンテンツを保持するように構成されている) をメールボックスに適用します。  <br/>  訴訟ホールドには保持期間を指定しません。また、アイテムを削除するために Office 365 アイテム保持ポリシーを構成することはありません。代わりに、アイテムを永久に保持するアイテム保持ポリシーを使用することができます。  <br/>  ユーザーの Office 365 アカウントを削除する。  <br/> |非アクティブなメールボックス内のすべてのコンテンツ (回復可能なアイテムフォルダー内のアイテムを含む) は、無期限に保持されます。  <br/> |
|従業員が退職した後の特定の期間、メールボックスの内容を保持し、その後それを削除する  <br/> | Office 365 アイテム保持ポリシーをメールボックスに適用します。  <br/>  保持期間の期限が切れたときにアイテムを保持し、削除するには、アイテム保持ポリシーを構成します。  <br/>  ユーザーの Office 365 アカウントを削除する。  <br/> |メールボックスアイテムの保持期間が経過すると、アイテムは [回復可能なアイテム] フォルダーに移動され、削除済みアイテムの保存期間 (Exchange メールボックスの場合) の有効期限が切れたときに非アクティブなメールボックスから完全に削除 (パージ) されます。 Office 365 アイテム保持ポリシーの保存期間は、メールボックスアイテムが受信または作成された元の日付、または最後に変更された日付に基づいて構成できます。  <br/> |
   
**注:** メールボックスに既に訴訟ホールドが設定されている場合、または Office 365 アイテム保持ポリシー (コンテンツを保持または保存してから削除するように設定されている) がメールボックスに既に適用されている場合は、対応する Office 365 ユーザーアカウントを削除するだけで済みます。非アクティブなメールボックスを作成します。 
  
## <a name="managing-inactive-mailboxes"></a>非アクティブなメールボックスを管理する

メールボックスを非アクティブにした後、非アクティブなメールボックスにさまざまな管理タスクを行うことができます。
  
- **非アクティブなメールボックスの保持期間を変更する** メールボックスが非アクティブになった後、非アクティブなメールボックスに適用される訴訟ホールドまたは Office 365 アイテム保持ポリシーの保持期間を変更することができます。 詳細な手順については、「 [Office 365 の非アクティブなメールボックスの保持期間を変更](change-the-hold-duration-for-an-inactive-mailbox.md)する」を参照してください。

  > [!NOTE]
  > 非アクティブなメールボックスに他のアイテム保持ポリシーを適用することはできません。 非アクティブなメールボックスに適用されている既存のアイテム保持ポリシーの保持期間のみを変更できます。
    
- **非アクティブなメールボックスを回復する** 元従業員 (または長期間離職中の従業員) が組織に復帰する場合、または新しい従業員が元従業員の職責を引き継ぐ場合には、非アクティブなメールボックスのコンテンツを回復できます。 非アクティブなメールボックスを回復すると、そのメールボックスは新しいメールボックスに変換され、非アクティブなメールボックスのコンテンツとフォルダー構造が保持されて、メールボックスが新しいユーザー アカウントにリンクされます。 回復された後、非アクティブなメールボックスは存在しなくなります。 ステップごとの手順、および非アクティブなメールボックスを回復するときに行われる処理については、「 [Office 365 の非アクティブなメールボックスを回復](recover-an-inactive-mailbox.md)する」を参照してください。
    
- **非アクティブなメールボックスを復元する** 別の従業員が元従業員の職責を引き継ぐ場合、または別のユーザーが非アクティブなメールボックスのコンテンツにアクセスする必要がある場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。 非アクティブなメールボックスを復元すると、そのコンテンツは別のメールボックスにコピーされます。 非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして残ります。 非アクティブなメールボックスは、電子情報開示ツールを使用して検索すること、そのコンテンツを別のメールボックスに復元すること、それを後に回復したり削除したりすることが引き続き可能です。 詳細な手順については、「 [Office 365 の非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)」を参照してください。
    
- **非アクティブなメールボックスを削除する** 非アクティブなメールボックスの内容を保持する必要がなくなった場合、すべてのホールドを解除するか、非アクティブなメールボックスに適用されているすべての Office 365 アイテム保持ポリシーを除去することにより、完全に削除できます。 メールボックスが 30 日以上前に非アクティブにされた場合、ホールドを解除した後、完全に削除するようメールボックスにマークが付けられます。 メールボックスが過去 30 日以内に非アクティブにされた場合には、ホールドを解除するかアイテム保持ポリシーを除去した後もメールボックスを再びアクティブにすることができます。 詳細な手順については、「 [Office 365 の非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)」を参照してください。