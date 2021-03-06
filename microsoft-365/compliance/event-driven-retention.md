---
title: イベントの発生時に保持を開始する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 通常、レコード管理ソリューションの一部として、特定したイベントに基づいて保持期間を開始するように保持ラベルを構成することができます。
ms.openlocfilehash: a3760feafa5307c8c71e83dcc72b988258b94a2a
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391509"
---
# <a name="start-retention-when-an-event-occurs"></a>イベントの発生時に保持を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

コンテンツを保持する際、保持期間は多くの場合、コンテンツの経過日数に基づいています。たとえば、ドキュメントを作成してから 7 年間保持をし、それから削除することができます。ただし、[保持ラベル](labels.md) を構成することで、特定の種類のイベントの発生を保持期間の基準として設定することもできます。イベントによって保持期間の開始がトリガーされ、その種類のイベントに保持ラベルが適用されているすべてのコンテンツに、ラベルの保持アクションが適用されます。
  
イベントドリブンの保持を使用する場合の例:
  
- **従業員が組織を離れる場合**、従業員が組織を離れてから 10 年間は、その従業員のレコードを保持する必要があるとします。 10 年が経過した後、その従業員の採用、業績、および退職に関するすべてのドキュメントを廃棄する必要があります。 10 年の保持期間をトリガーするイベントは、組織を離れる従業員となります。 
    
- **契約満了の場合**、契約に関連するすべてのレコードは、契約満了後 5 年間は保持する必要があります。 5 年間の保持期間をトリガーするイベントは、契約の満了です。 
    
- **製品の有効期間**: たとえば、組織に、技術仕様などのコンテンツに関して、最終製品製造日に関する保持要件があるとします。この場合、最後に製造された日が、保存期間をトリガーするイベントとなります。 
    
イベント ベースの保持は通常、レコード管理プロセスの一環として使用します。これは以下のことを意味します:
  
- イベントに基づくラベルでは、通常、レコードとしてコンテンツを分類します。 詳細については、「[レコードの詳細](records.md)」を参照してください。

- レコードとして分類されているもののイベント トリガーがまだ発生していない文書は、イベントがそのドキュメントの保存期間をトリガーするまで無期限に保持されます (レコードを完全に削除することはできません)。
    
- イベントに基づく保持ラベルは、通常、保持期間の最後に廃棄レビューをトリガーするため、レコード管理者はコンテンツを手動で確認して廃棄できます。 詳細については、「[コンテンツの廃棄](disposition.md)」を参照してください。
    

イベントに基づくラベルには、Microsoft 365 の他の保持ラベルと同じ機能があります。 詳細については、「[アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>イベントの種類、ラベル、イベント、アセット ID の関係を理解する

イベント ベースの保持を活用するには、図と以下の説明に示すように、イベントの種類、保持ラベル、イベント、アセット ID の関係を理解することが重要です。 
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![イベントの種類、ラベル、イベント、アセット ID の図](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. さまざまな種類のコンテンツの保持ラベルを作成してから、イベントの種類に関連付けます。 たとえば、さまざまな種類の製品ファイルとレコードの保持ラベルは、製品を使用しなくなった時点からレコードを 10 年間保持する必要があるため、Product Lifetime という名前のイベントの種類に関連付けられます。
    
2. ユーザー (通常はレコード管理者) はコンテンツにこれらの保持ラベルを適用し、(SharePoint と OneDrive のドキュメントの場合) アイテムごとに資産 ID を入力します。 この例では、資産 ID は組織で使用される製品名またはコードです。 したがって、各製品のレコードには保持ラベルが割り当てられ、各レコードには資産 ID を含むプロパティが含まれます。 この図は組織内のすべての製品レコードの**すべてのコンテンツ**を表しており、各アイテムにはそのレコードに該当する製品の資産 ID が含まれます。 
    
3. 製品の有効期限がイベントの種類であり、有効期限が切れた特定の製品がイベントになります。そのイベントの種類のイベントが発生したら (この場合、製品の有効期限が切れるとき)、以下を指定するイベントを作成します。
    
   - (SharePoint および OneDrive のドキュメントの) アセット ID。
    
   - (Exchange アイテムの) キーワード。上の例において組織は、製品レコードを含むメッセージで製品コードを使用するため、Exchange アイテムのキーワードは  SharePoint および OneDrive ドキュメントのアセット  ID と同じになります。
    
   - イベントが発生した日付。この日付は、保持期間の開始日として使用されます。この日付には、現在、過去、または将来の日付を使用できます。

4. イベントの作成後、イベントの日付は、そのイベントの種類の保持ラベルを持ち、指定された資産 ID またはキーワードを含むすべてのコンテンツに同期されます。 他の保持ラベルと同様に、この同期には最大で 7 日間かかります。 前の図では、赤で囲まれているアイテムはすべて、このイベントによって保持期間がトリガーされています。 言い換えれば、この製品の期限が切れたとき、そのイベントがその製品のレコードの保持期間のトリガーとなります。

イベントに資産 ID またはキーワードを指定しない場合、そのイベントの種類のラベルの付いた**すべてのコンテンツ**はイベントによってトリガーされる保持期間を持つことを理解することが重要です。 つまり、前の図の場合であれば、すべてのコンテンツの保持が開始されます。 これは、意図したものとは異なる可能性があります。 

最後に、それぞれの保持ラベルにはそれぞれの保持設定があることにご注意ください。 この例では、すべて 10 年間に指定されていますが、それぞれのラベルが異なる保持期間を持つ保持ラベルを、1 つのイベントでトリガーすることができます。
  
## <a name="how-to-set-up-event-driven-retention"></a>イベント ドリブンの保持のセットアップ方法

イベント ドリブンの保持のワークフロー概要:
  
![イベント ベースの保持をセットアップするワークフローの図](../media/event-based-retention-process.png)
  
> [!TIP]
> SharePont の管理プロパティを使用して保持ラベルを自動適用し、イベント ドリブンの保持を実装する詳細なシナリオについては、「[保持ラベルを使用して SharePoint ドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)」を参照してください。

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>手順 1: 保持期間がイベントに基づくラベルを作成する

保持ラベルを作成して構成するには、[[保持ラベルを作成して構成する](create-retention-labels.md#create-and-configure-retention-labels)] の手順で [保持] をオンにして、イベントに基づいてコンテンツを保持または削除するオプションを選択します。 つまり、この設定では、保持設定は手順 5 の [**イベント**] ページでイベントを作成するまで有効になりません。 
  
通常、イベントドリブンの保持は、レコードとして分類されているコンテンツに使用されるので、コンテンツをレコードとしてマークするオプションも選択する必要があるかどうかを確認することをお勧めします。
  
イベントドリブンの保持には、次のような保持の設定が必要になります。
  
- コンテンツを保持する。
    
- 保存期間の終わりに、コンテンツの自動削除または廃棄レビューのトリガーを行う。
    
![ベースにするイベントのラベルのオプション](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a>手順 2: そのラベルのイベントの種類を選択する

ラベルの設定で、**イベント**に基づいてラベルを設定するオプションを選ぶと、**[イベントの種類の選択]** というオプションが表示されます。 イベントの種類とは、ラベルを関連付けるイベントの単なる一般的な説明です。
  
たとえば、Product Lifetime という名前のイベントの種類を作成する場合は、"製品開発ファイル" や "製品の経営的意思決定" など、ラベルを適用するコンテンツの種類が分かるような名前でイベント ベースの保持ラベルを作成する必要があります。

組み込みのイベントタイプのいずれかを選択するか、独自のイベントタイプを作成して選択します。

イベントの種類を選択して保持ラベルを保存すると、イベントの種類の変更はできませんので、ご注意ください。
  
![イベントの種類を作成または選択するオプション](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>手順 3: イベント ベースの保持ラベルを発行または自動適用する

他の保持ラベルと同じように、イベント ベースのラベルを発行するか自動適用して、コンテンツに手動または自動で適用されるようにする必要があります。
- [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
- [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)


> [!NOTE]
> [**レコード管理**] > [**ファイル計画**] タブまたは [**データ ガバナンス**] > [**ラベル**] タブからイベント ベースの保持ラベルを選択した場合、[**ラベルの自動適用**] ボタンは使用できません。
> 
> このボタンの代わりに、次のいずれかの場所からのラベルまたはポリシーのリストの上にある [**ラベルを自動適用**] オプションを使用します。
> - [**レコード管理**] > [**ラベル ポリシー**] タブ
> - [**データ ガバナンス**] > [**ラベル**] タブまたは [**ラベル ポリシー**] タブ


![保持ラベルの発行または自動適用のオプション](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>手順 4: アセット ID を入力する

イベント ベースのラベルがコンテンツに適用されたら、アイテムごとに資産 ID を入力できます。 たとえば、組織では以下のものを使用する場合があります。
  
- 特定の製品のみのコンテンツ保持に使用する製品コード。
    
- 特定の製品のみのコンテンツ保持に使用するプロジェクト コード。
    
- 特定の製品のみのコンテンツ保持に使用する従業員 ID。
    
資産 ID は、SharePoint と OneDrive で利用できる別のドキュメント プロパティです。 組織では既に別のドキュメント プロパティや ID を使用してコンテンツを分類している可能性があります。 その場合、イベントの作成時にそれらのプロパティおよび値を使用することもできます (後述する手順 6 を参照してください)。 重要な点は、ドキュメント プロパティで *property:value* の組み合わせを使用して、そのアイテムをイベントの種類に関連付ける必要があるということです。
  
![アセット ID を入力するテキスト ボックス](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>手順 5: イベントを作成する

製品の使用を終えるなど、イベントの種類に関する特定のインスタンスが発生するときは、Microsoft 365 コンプライアンス センターで **[レコード管理]** > **[イベント]** ページの順に移動し、イベントを作成します。 イベントを作成し、トリガーします。
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>手順 6: 手順 2 でのラベルを使用したイベントの種類と同じものを選択する

イベントを作成するときには、手順 2 の保持ラベルで使用したものと同じイベントの種類 (製品の有効期限など) を選択します。 そのイベントの種類が選択されたイベントに適用されている保持ラベルの付いたコンテンツのみが、トリガーされる保持期間を持ちます。
  
![イベントの種類を選択するイベント設定のオプション](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>手順 7: キーワードまたはアセット ID を入力する

ここで、資産 ID (SharePoint および OneDrive コンテンツの場合) またはキーワード (Exchange コンテンツの場合) を指定して、コンテンツの範囲を絞り込みます。 資産 ID の場合、保持は指定された *property:value* ペアを持つコンテンツにのみ適用されます。 資産 ID が入力されていない場合は、そのイベントの種類のラベルの付いたすべてのコンテンツに同じ保持期限が適用されます。

例えば、資産 ID プロパティを使用する場合は、下に示される資産 ID のボックスに 「`ComplianceAssetID:<value>`」 と入力します。
  
組織は、このイベントの種類に関するドキュメントに他のプロパティと ID を適用している場合があります。 たとえば、特定の製品のレコードを検出する必要がある場合、ID はカスタム プロパティ製品 ID とその値 "XYZ" の組み合わせである可能性があります。 この場合は、次の図に示されるアセット ID のボックスに 「`ProductID:XYZ`」 と入力します。
  
Exchange アイテムの場合、キーワード を使用します。 AND、OR、NOT などの検索演算子を使用して、クエリを使うことができます。 詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
最後に、イベントが発生した日付を選択します。この日付が、保持期間の開始日として使用されます。 イベントの作成後、そのイベントの日付は、そのイベントの種類の保持ラベル、資産 ID、キーワードを持つすべてのコンテンツに同期されます。 その他の保持ラベルと同様に、この同期には最大で 7 日間かかる可能性があります。
  
![[イベントの設定] ページ](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

イベントを作成すると、既にラベル付けされてインデックスが作成されているコンテンツの保持設定が有効になります。 イベントが作成された後に保持ラベルが新しいコンテンツに追加された場合は、同じ詳細を使用して新しいイベントを作成する必要があります。

イベントを削除しても、既にラベル付けされているコンテンツに対して現在有効になっている保持設定は取り消されません。 それを行うには、同じ詳細を使用して新しいイベントを作成しますが、日付は空白のままにします。 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>コンテンツ検索を使用して、特定のラベルまたはアセット ID が適用されたすべてのコンテンツを検索する

保持ラベルをコンテンツに割り当てた後は、特定の保持ラベルで分類されている、または特定のアセット ID を含むすべてのコンテンツをコンテンツ検索を使用して検索することができます。
  
- 特定の保持ラベルを持つすべてのコンテンツを検索するには、 **保持ラベル**の条件を選択した後、完全なラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。 
    
- 特定のアセット ID を持つすべてのコンテンツを検索するには、**ComplianceAssetID** プロパティと `ComplianceAssetID:<value>` のフォーマットを使用した値を入力します。 
    
詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
## <a name="permissions"></a>アクセス許可

**[イベント]** ページにアクセスするには、レビュー担当者は、**廃棄管理**の役割と**監査ログの閲覧限定**の役割を持つ、役割グループのメンバーである必要があります。Disposition Reviewers という新しい役割グループを作成し、これら 2 つの役割をその役割グループに追加して、それからメンバーをその役割グループに追加することをお勧めします。 
  
詳細については、「[ユーザーに Office 365 セキュリティ&amp;コンプライアンス センターへのアクセス権を付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。
  
## <a name="automate-events-by-using-powershell"></a>PowerShell を使用してイベントを自動化する

PowerShell スクリプトを使用して、ビジネス アプリケーションからイベント ベースの保持を自動化することができます。 イベント ベースの保持で利用可能な PowerShell コマンドレットは、次のとおりです。
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a>REST API を使用してイベントを自動化する

REST API を使用して、保持期間の開始をトリガーするイベントを自動的に作成できます。

REST API は一連の HTTP 操作 (HTTP メソッド) をサポートするサービス エンドポイントで、サービス リソースへのアクセス権の作成/取得/更新/削除をできるようにします。 詳細については、「[REST API 要求/応答のコンポーネント](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)」を参照してください。 Microsoft 365 REST API を使用することにより、POST および GET メソッドを使用してイベントを作成および取得できます。

REST API を使用するには、2 つのオプションがあります。

- イベントの発生を自動的にトリガーする **Microsoft Power Automate または同様のアプリケーション**。 Microsoft Power Automate は、他のシステムに接続するためのオーケストレーターなので、カスタム ソリューションを作成する必要はありません。 詳細については、[Power Automate Web サイト](https://flow.microsoft.com/ja-JP/) を参照してください。

- **PowerShell または HTTP クライアントで REST API** を呼び出して、カスタム ソリューションの一部である PowerShell (バージョン 6 以降) を使用してイベントを作成します。

REST API を使用する前に、グローバル管理者として、保持イベント呼び出しに使用する URL を確認します。 これを行うには、REST API の URL を使用して、保持イベント呼び出しの取得を実行します。

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

応答コードを確認します。 302 の場合は、応答ヘッダーの Location プロパティからリダイレクトされた URL を取得し、以下の手順で `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` の代わりにその URL を使用します。

自動作成されたイベントは、Microsoft 365 コンプライアンス センター > **レコード管理** >  **イベント** で表示することで確認できます。

### <a name="use-microsoft-power-automate-to-create-the-event"></a>Microsoft Power Automate を使用してイベントを作成する

Microsoft 365 REST API を使用してイベントを作成するフローを作成します

![Flow を使用してイベントを作成する](../media/automate-event-driven-retention-flow-1.png)

![Flow を使用して REST API を呼び出す](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a>イベントを作成する

REST API を呼び出すサンプル コード

- **方法**: 投稿
- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **ヘッダー**: キー = Content-Type、値 = application/atom+xml
- **本文**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- **認証**: 基本
- **ユーザー名**: 「Complianceuser」
- **パスワード**: 「Compliancepassword」


##### <a name="available-parameters"></a>利用可能なパラメーター


|パラメーター|説明|Notes|
|--- |--- |--- |
|<d:Name></d:Name>|イベントの一意の名前を入力します。|末尾のスペースおよび以下の文字は使用できません。% * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|イベントの種類の名前 (または GUID) を入力します。|例: 「従業員の退職」。 イベントの種類を保持ラベルに関連付ける必要があります。|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|「ComplianceAssetId:」 と従業員 ID を入力します|例: 「ComplianceAssetId: 12345」|
|<d:EventDateTime></d:EventDateTime>|イベントの日時|形式: yyyy-MM-ddTHH:mm:ssZ、例: 2018-12-01T00:00:00Z
|

###### <a name="response-codes"></a>応答コード

| 応答コード | 説明       |
| ----------------- | --------------------- |
| 302               | リダイレクト              |
| 201               | 作成済み               |
| 403               | 承認に失敗しました  |
| 401               | 認証に失敗しました |

##### <a name="get-events-based-on-a-time-range"></a>時間範囲に基づいてイベントを取得する

- **メソッド**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **ヘッダー**: キー = Content-Type、値 = application/atom+xml

- **認証**: 基本

- **ユーザー名**: 「Complianceuser」

- **パスワード**: 「Compliancepassword」


###### <a name="response-codes"></a>応答コード

| 応答コード | 説明                   |
| ----------------- | --------------------------------- |
| 200               | 問題ありません。イベントの一覧は atom+ xml 形式です |
| 404               | 見つかりません                         |
| 302               | リダイレクト                          |
| 401               | 承認に失敗しました              |
| 403               | 認証に失敗しました             |

##### <a name="get-an-event-by-id"></a>ID でイベントを取得する

- **メソッド**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **ヘッダー**: キー = Content-Type、値 = application/atom+xml

- **認証**: 基本

- **ユーザー名**: 「Complianceuser」

- **パスワード**: 「Compliancepassword」

###### <a name="response-codes"></a>応答コード

| 応答コード | 説明                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 問題ありません。応答本体に atom+xml 形式のイベントが含まれています |
| 404               | 見つかりません                                            |
| 302               | リダイレクト                                             |
| 401               | 承認に失敗しました                                 |
| 403               | 認証に失敗しました                                |

##### <a name="get-an-event-by-name"></a>名前でイベントを取得する

- **メソッド**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **ヘッダー**: キー = Content-Type、値 = application/atom+xml

- **認証**: 基本

- **ユーザー名**: 「Complianceuser」

- **パスワード**: 「Compliancepassword」


###### <a name="response-codes"></a>応答コード

| 応答コード | 説明                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 問題ありません。応答本体に atom+xml 形式のイベントが含まれています |
| 404               | 見つかりません                                            |
| 302               | リダイレクト                                             |
| 401               | 承認に失敗しました                                 |
| 403               | 認証に失敗しました                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a>PowerShell または HTTP クライアントを使用してイベントを作成する

PowerShell はバージョン 6 以降がインストールされている必要があります。

PowerShell セッションで、次のスクリプトを実行します。

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

