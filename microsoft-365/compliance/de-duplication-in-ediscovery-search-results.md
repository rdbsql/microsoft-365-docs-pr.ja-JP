---
title: 電子情報開示検索結果での重複排除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: 同じメッセージの複数のインスタンスが異なるメールボックスで検出された場合でも、エクスポートされる電子情報開示検索結果の重複を除外するオプションがあります。
ms.openlocfilehash: 98639bd23b3d7c99b91a193c2651ff2fad677eeb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085178"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>電子情報開示検索結果での重複排除

この記事では、電子情報開示検索結果の重複除外がどのように機能するかを説明し、重複除外アルゴリズムの制限事項を説明します。
  
Office 365 の電子情報開示ツールを使用して電子情報開示検索の結果をエクスポートする場合、エクスポートされた結果を重複除外するオプションがあります。 シナリオ 重複除去を有効にした場合 (既定では、重複除外は有効になっていません)、同じメッセージの複数のインスタンスが検索されたメールボックスで見つかった場合でも、電子メールメッセージのコピーは1つしかエクスポートされません。 重複除外は、検索結果のエクスポート後にレビューして分析する必要があるアイテムの数を減らすことで、時間を節約するのに便利です。 ただし、重複除外のしくみを理解しておくことは重要であり、エクスポート処理中に一意のアイテムが重複としてマークされる可能性があるアルゴリズムには制限があることに注意してください。
  
## <a name="how-duplicate-messages-are-identified"></a>重複するメッセージの識別方法

Office 365 電子情報開示ツールは、次の電子メールプロパティの組み合わせを使用して、メッセージが重複しているかどうかを判断します。
  
- **Internetmessageid** -このプロパティは、特定のメッセージの特定のバージョンを参照するグローバル一意識別子である、電子メールメッセージのインターネットメッセージ識別子を指定します。 この ID は、送信者の電子メールクライアントプログラム、またはメッセージを送信するホスト電子メールシステムによって生成されます。 ユーザーが複数の受信者にメッセージを送信した場合、そのメッセージの各インスタンスのインターネットメッセージ ID は同じになります。 元のメッセージに対するその後の変更では、別のメッセージ識別子が受信されます。 
    
- **ConversationTopic** -このプロパティは、メッセージの会話スレッドの件名を指定します。 **ConversationTopic**プロパティの値は、会話の全体的なトピックを説明する文字列です。 保護は、初期メッセージと、最初のメッセージへの返信で送信されたすべてのメッセージで構成されます。 同じ会話内のメッセージは、 **ConversationTopic**プロパティの値と同じです。 このプロパティの値は、通常、会話を開始した最初のメッセージの件名行です。 
    
- **Bodytaginfo** -これは内部の Exchange ストアのプロパティです。 このプロパティの値は、メッセージ本文のさまざまな属性をチェックすることによって計算されます。 このプロパティは、メッセージ本文の違いを識別するために使用されます。 
    
電子情報開示のエクスポートプロセスでは、これらの3つのプロパティは、検索条件に一致するすべてのメッセージに対して比較されます。 2つ以上のメッセージでこれらのプロパティが同一である場合、これらのメッセージは重複していると判断され、重複除外が有効になっている場合は、メッセージのコピーが1つだけエクスポートされることになります。 エクスポートされるメッセージは、"ソースアイテム" と呼ばれます。 重複するメッセージに関する情報は、エクスポートされた検索結果に含まれる **.csv**レポートと**manifest.xml**レポートに含まれています。 結果の **.csv**ファイルでは、重複するメッセージは、[**アイテムの複製**] 列に値があることで識別されます。 この列の値は、エクスポートされたメッセージの [**アイテムの id** ] 列の値と一致します。 
  
次の図は、検索結果と共にエクスポートされる**結果の .csv**レポートと**manifest.xml**レポートで重複メッセージがどのように表示されるかを示しています。 これらのレポートには、以前に説明した電子メールのプロパティは含まれません。これは、重複除外のアルゴリズムで使用されます。 代わりに、Exchange ストアによってアイテムに割り当てられる**アイテム id**プロパティがレポートに含まれます。 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>結果の .csv レポート (Excel で表示)
  
![結果 .csv レポートでの重複アイテムに関する情報の表示](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml レポート (Excel で表示)
  
![Manifest.xml レポートでの重複アイテムに関する情報の表示](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
さらに、重複するメッセージからのその他のプロパティがエクスポートレポートに含まれています。 これには、メッセージが配布グループに送信されたかどうか、およびそのメッセージが別のユーザーに対して Cc または Bcc であったかどうかについて、重複しているメッセージが置かれているメールボックスが含まれます。
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>重複除外アルゴリズムの制限事項

重複除外アルゴリズムには、重複しているとマークされた一意のアイテムを引き起こす可能性がある既知の制限がいくつかあります。 オプションの重複除外機能を使用するかどうかを決定できるように、これらの制限事項を理解しておくことが重要です。
  
重複除外機能により、誤ってメッセージを重複として識別し、エクスポートしない場合があります (ただし、エクスポートレポートでは、重複していることを示しています)。 ユーザーが編集するが、送信されないメッセージです。 たとえば、ユーザーが Outlook でメッセージを選択し、メッセージの内容をコピーして、それを新しいメッセージに貼り付けるとします。 その後、ユーザーは添付ファイルを削除または追加するか、件名または本文を変更することによって、いずれかのコピーを変更します。 この2つのメッセージが電子情報開示検索のクエリに一致する場合、検索結果のエクスポート時に重複除去が有効になっている場合は、メッセージのうち1つのみがエクスポートされます。 そのため、元のメッセージまたはコピーされたメッセージが変更された場合でも、変更されたメッセージは送信されていないため、 **Internetmessageid**、 **ConversationTopic** 、 **bodytaginfo**の各プロパティの値は更新されませんでした。 ただし、前述の説明のように、両方のメッセージがエクスポートレポートに表示されます。 
  
メールボックスが訴訟ホールドまたはインプレース保持されている場合のように、重複するページ保護機能が有効になっている場合は、一意のメッセージも重複としてマークされる可能性があることに注意してください。 コピーオンライト機能は、元のメッセージをコピーして (ユーザーの回復可能なアイテムフォルダーの [バージョン] フォルダーに保存します)、元のアイテムのリビジョンを保存します。 この場合、改訂されたコピーと元のメッセージ (回復可能なアイテムフォルダー内) は重複メッセージと見なされるため、エクスポートされるのは1つだけです。
  
> [!IMPORTANT]
> 重複除外アルゴリズムの制限が検索結果の品質に影響する可能性がある場合は、アイテムをエクスポートするときに重複除去を有効にしないでください。 このセクションで説明した状況が検索結果の要因にならない可能性があり、重複している可能性のあるアイテムの数を減らす必要がある場合は、重複除外を有効にすることを検討する必要があります。 
  
## <a name="more-information"></a>詳細情報

- この記事の情報は、次の電子情報開示ツールのいずれかを使用して検索結果をエクスポートする場合に適用されます。
    
  - Office 365 のコンプライアンスセンターでのコンテンツ検索
    
  - Exchange Online のインプレース電子情報開示
    
  - SharePoint Online の電子情報開示センター
    
- 検索結果のエクスポートの詳細については、以下を参照してください。
    
  - [コンテンツ検索をエクスポートする](export-search-results.md)
    
  - [コンテンツ検索のレポートをエクスポートする](export-a-content-search-report.md)
    
  - [インプレース電子情報開示の検索結果を PST ファイルにエクスポートする](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [電子情報開示センターでのコンテンツのエクスポートとレポートの作成](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)