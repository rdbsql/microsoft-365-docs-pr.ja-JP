---
title: スパム対策メッセージ ヘッダー
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Exchange Online Protection は、受信メール メッセージをスキャンするときに **X-Forefront-Antispam-Report** ヘッダーを各メッセージに挿入します。
ms.openlocfilehash: bb0db43e9bfb4be565576bf57cc5d52eb17a0946
ms.sourcegitcommit: 18b5f6e9913147cea911c0fd347fcd880fb86f17
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2019
ms.locfileid: "37167123"
---
# <a name="anti-spam-message-headers"></a>スパム対策メッセージ ヘッダー

Exchange Online Protection では、受信電子メール メッセージをスキャンするときに、 **X-Forefront-Antispam-Report** ヘッダーをそれぞれのメッセージに挿入します。このヘッダー内のフィールドは、そのメッセージに関する情報やそれがどのように処理されたかに関する情報を管理者に提供できます。 **X-Microsoft-Antispam** ヘッダー内のフィールドは、バルク メールやフィッシングについての追加情報を提供します。これら 2 つのヘッダーのほかに、Exchange Online Protection も電子メール認証の結果を **Authentication-results** ヘッダーで処理する各メッセージに挿入します。

さまざまなメール クライアントでメール メッセージ ヘッダーを表示する方法については、「[メッセージ ヘッダー アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」を参照してください。 
  
> [!TIP]
>  メッセージ ヘッダーの内容は、[メッセージ アナライザー](https://testconnectivity.microsoft.com/?tabid=mha) ツールにコピーして貼り付けることができます。 このツールは、ヘッダーを解析し、より読みやすい形式にします。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report メッセージ ヘッダー フィールド

メッセージ ヘッダー情報にアクセスしたら、**X-Forefront-Antispam-Report** を検索して、次に示すフィールドを確認します。このヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。

|**ヘッダー フィールド**|**説明**|
|:-----|:-----|
|CIP:[IP アドレス]|接続 IP アドレス接続フィルターで IP 許可一覧と IP 禁止一覧を作成する際、この IP アドレスを指定することができます。詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。  |
|CTRY|サービスに接続されたメッセージの発信国。これは、接続先 IP アドレスから特定されます。そのため、発信元の送信先 IP アドレスとは異なる可能性があります。|
|LANG|メッセージが作成された言語であり、国番号 (たとえば、ロシア語は ru_RU) で指定されます。|
|SCL|メッセージの Spam Confidence Level (SCL) 値。これらの値の解釈方法については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。  |
|PCL|メッセージの Phishing Confidence Level (PCL) 値。|
|SRV:BULK|メッセージが一括電子メール メッセージとして識別されました。**[バルクメール メッセージをすべてブロックする]** 詳細スパム フィルター オプションが有効になっている場合、このメッセージがスパムとしてマークされます。このオプションが有効になっていない場合は、残りのフィルター処理ルールでそのメッセージがスパンであると判断された場合にのみスパムとしてマークされます。|
|SFV:SFE|メッセージが個人の差出人セーフ リスト上のアドレスから送信されているため、フィルター処理が省略され、メッセージはそのまま配信されました。|
|SFV:BLK|メッセージが個人の受信拒否リスト上のアドレスから送信されているため、フィルター処理が省略され、メッセージはブロックされました。  <br/> **ヒント**: エンド ユーザーが安全な送信者リストと受信拒否リストを作成する方法については、「[ブロックまたは許可 (迷惑メール設定) ](https://go.microsoft.com/fwlink/p/?LinkId=294862)」 (Outlook on the web) と「[迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/p/?LinkId=270065)」(Outlook) を参照してください。|
|IPV:CAL|このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。|
|IPV:NLI|IP アドレスが IP 評価リストに掲載されていませんでした。|
|SFV:SPM|コンテンツ フィルターによって、メッセージがスパムとしてマークされました。|
|SFV:SKS|コンテンツ フィルターによって処理される前に、メッセージがスパムとしてマークされました。 これには、メッセージを自動的にスパムメールとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに一致するメッセージが含まれます。|
|SFV:SKA|メッセージは、スパム フィルター ポリシーの許可リスト (**送信者の許可**リストなど) と一致したため、フィルタリングをスキップして受信トレイに配信されました。|
|SFV:SKB|メッセージは、スパム フィルター ポリシーの拒否リスト (**送信者の拒否**リストなど) と一致したため、スパムとしてマークされました。|
|SFV:SKN|コンテンツ フィルターによって処理される前に、メッセージが非スパムとしてマークされました。 これには、メッセージを自動的に非スパム メールとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに一致するメッセージが含まれます。|
|SFV:SKI|SFV:SKN と同様に、メッセージはテナント内の組織内電子メールであるなどの別の理由でフィルター処理が省略されました。|
|SFV:SKQ|メッセージは検疫から解放され、目的の受信者に送信されました。|
|SFV:NSPM|メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。|
|H:[helostring]|接続元のメール サーバーの HELO または EHLO 文字列。|
|PTR:[ReverseDNS]|逆引き DNS アドレスとも呼ばれる、送信元の IP アドレスの PTR レコード (またはポインター レコード)。|
|CAT:|メッセージに適用される保護ポリシーです。 <br/>MALW: マルウェア <br/>PHSH: フィッシング <br/>HSPM: 高確度スパム <br/>SPOOF: なりすまし <br/>SPM: スパム <br/>BULK: バルク <br/>DIMP: ドメイン偽装 <br/>UIMP: ユーザー偽装 <br/>受信メッセージには、複数の種類の保護と複数の検出スキャンによりフラグが付けられる場合があります。 ポリシーの優先度はそれぞれ異なり、優先度が最も高いポリシーが適用されます。 詳細については、「[複数の保護方法および検出スキャンがメールで実行される場合に適用されるポリシー](https://docs.microsoft.com/microsoft365/securitycompliance/how-policies-and-protections-are-combined)」を参照してください。|
|SFTY|メッセージはフィッシングとして識別され、次のいずれかの値が付けられます。 <br/>9.1: 既定値。 メッセージにフィッシングの URL が含まれているか、他のフィッシングコンテンツが含まれている可能性があります。または、Office 365 にメッセージを送る前に Exchange Server のオンプレミス バージョン などの別のメール フィルターによってフィッシングとしてマークされていた可能性があります。 <br/>9.11: 差出人: ヘッダー内の送信ドメインが、受信ドメインと同じ組織であるか、または同じ組織の一部であるため、メッセージのスプーフィング対策チェックに失敗しました。 これは、組織内のスプーフィングの安全性に関するヒントがメッセージに追加されることを意味します。 <br/>9.19: 送信ドメインが、受信者の所有するドメインまたはフィッシング詐欺対策ポリシーによって保護されているカスタム ドメインの偽装を試みているため、メッセージのドメイン偽装チェックに失敗しました。 これは、フィッシング詐欺対策ポリシーによって有効化されている場合、偽装の安全性に関するヒントがメッセージに追加されることを意味します。 <br/>9.20: 送信ドメインが、受信者の組織内のユーザーまたはフィッシング詐欺対策ポリシーによって保護されているカスタム ユーザーの偽装を試みているため、メッセージのユーザー偽装チェックに失敗しました。 これは、フィッシング詐欺対策ポリシーによって有効化されている場合、偽装の安全性に関するヒントがメッセージに追加されることを意味します。 <br/>9.21: メッセージのスプーフィング対策チェックに失敗しました。差出人: ヘッダー内の送信ドメインの認証ができず、送信ドメインは外部ドメインです。 CompAuth を組み合わせて使用します (認証結果を参照してください)。 <br/>9.22: ユーザーが、オーバーライドされた差出人セーフ リストを持っている点を除き、9.21 と同じです。  <br/>9.23: ただし、組織が、オーバーライドされた許可された送信者またはドメインを持っている点を除き、9.22 と同じです。 <br/>9.24: ユーザーが、オーバーライドされた Exchange メール フロー ルールを持っている点を除き、9.23 と同じです。|
|X-CustomSpam: [ASF オプション]|このメッセージは、高度なスパム フィルター オプションに一致しました。 たとえば、 **X-CustomSpam: リモート サイトへの画像のリンク** は、**リモート サイトへの画像のリンク** ASF オプションが一致したことを表します。 どの X ヘッダー テキストが特定の ASF オプションに追加されたかを確認するには、「[高度なスパム フィルター オプション](advanced-spam-filtering-asf-options.md)」を参照してください。|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam メッセージ ヘッダー フィールド

次の表に、**X-Microsoft-Antispam** メッセージ ヘッダー内の便利なフィールドを示します。このヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。
  
|**ヘッダー フィールド**|**説明**|
|:-----|:-----|
|BCL|メッセージの Bulk Complaint Level (BCL)。詳細については、「[バルク苦情レベルの値](bulk-complaint-level-values.md)」を参照してください。  |
|PCL|メッセージの Phishing Confidence Level (PCL)。これは、そのメッセージがフィッシング メッセージかどうかを示します。     この状態は、次のいずれかの数値として返されます。 <br/>**0-3**: メッセージの内容がフィッシングである可能性が低いことを示します。 <br/>**4-8**: メッセージの内容がフィッシングである可能性が高いことを示します。 <br/>**-9990**: メッセージの内容がフィッシングである可能性が高いことを示します (Exchange Online Protection のみ)。  <br/>  これらの値は、メール クライアントがメッセージに対して実行するアクションを決めるために使用されます。 たとえば、Outlook は PCL スタンプを使用し、疑わしいメッセージの内容をブロックします。 フィッシングおよび Outlook がフィッシング メッセージを処理する方法の詳細については、[「メール メッセージのリンクを設定する」](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8) を参照してください。|
|

## <a name="authentication-results-message-header"></a>Authentication-results メッセージ ヘッダー

メール サーバーが電子メール メッセージを受信すると、SPF、DKIM、および DMARC に対するチェックの結果が Office 365 によって、**Authentication-results** メッセージ ヘッダーに記録またはスタンプされます。
  
### <a name="check-stamp-syntax-and-examples"></a>check stamp 構文と例

次に示す構文の例では、Office 365 がメール サーバーでの受信時に電子メールの認証チェックを受ける各メールのメッセージ ヘッダーに適用するテキスト "スタンプ" の一部を示しています。このスタンプは **Authentication-Results** ヘッダーに追加されます。
  
**構文:SPF check stamp**
  
SPF の場合は、次の構文を適用します。
  
```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**例:SPF check stamp**
  
```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

**構文:DKIM check stamp**
  
DKIM の場合は、次の構文を適用します。
  
```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**例:DKIM check stamp**
  
```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

**構文:DMARC check stamp**
  
DMARC の場合は、次の構文を適用します。
  
```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

**例:DMARC check stamp**
  
```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Office 365 の電子メールの認証で使用される Authentication-results メッセージ ヘッダー フィールド

フィールドと各電子メールの認証チェックに使用できる値を次の表に示します。
  
|**ヘッダー フィールド**|**説明**|
|:-----|:-----|
|spf|メッセージの SPF チェックの結果についての説明。次の値を指定できます。 <br/>**pass (IP アドレス)**: メッセージの SPF チェックにパスしたことを示します。送信者の IP アドレスが含まれます。 送信者のドメインに代わってメールを送信または中継する許可がクライアントに与えられています。 <br/>**fail (IP アドレス)**: メッセージの SPF チェックに失敗したことを示します。送信者の IP アドレスが含まれます。 _hard fail_ と呼ばれることもあります。 <br/>**softfail (理由)**: SPF レコードにより、ホストには送信する許可がないと指定されたことを示しますが、SPF レコードが展開中であることも示します。 <br/>**neutral**: IP アドレスが許可されているかどうかをアサートしていないことを、SPF レコードが明示的に宣言したことを示します。 <br/>**none**: ドメインに SPF レコードがないか、SPF レコードが結果に対して評価されないことを示します。 <br/>**temperror**: DNS エラーなど、一時的なエラーが発生した可能性があることを示します。 時間をおいて再試行すれば、管理者がアクションを実行しなくても、成功する場合があります。 <br/>**permerror**: 永続的なエラーが発生したことを示します。 これは、ドメインに不正な形式の SPF レコードがある場合に発生します。|
|smtp.mailfrom|メッセージが送信された送信元のドメインを含みます。この電子メール メッセージに関するすべてのエラーは、ポスト マスターまたはドメインを担当するエンティティに送信されます。これは、メッセージ エンベロープの 5321.MailFrom アドレスまたはリバースパス アドレスとも呼ばれます。|
|dkim|メッセージの DKIM チェックの結果についての説明。次の値を指定できます。 <br/>**pass**: メッセージの DKIM チェックにパスしたことを示します。 <br/>**fail (理由)**: メッセージの DKIM チェックに失敗したことと、その理由を示します。 たとえば、メッセージが署名されていない場合、署名を認証できない場合などです。 <br/>**none**: メッセージが署名されていないことを示します。 これは、ドメインに DKIM レコードがあるかどうかや、DKIM レコードが結果を評価しない (このメッセージが署名されていない点のみ) ことを示しますが、これらを示さない場合もあります。|
|header.d|DKIM 署名で識別されるドメイン (存在する場合)。 これは、公開キーを照会するドメインです。|
|dmarc|メッセージの DMARC チェックの結果についての説明。次の値を指定できます。 <br/>**pass**: メッセージの DMARC チェックにパスしたことを示します。 <br/>**fail**: メッセージの DMARC チェックに失敗したことを示します。 <br/>**bestguesspass**: ドメインの DMARC TXT レコードが存在しないことを示します。ただし、レコードが存在していた場合、メッセージの DMARC チェックはパスしていたことになります。 これは、5321.MailFrom アドレスのドメインが、5322.From アドレスのドメインと一致するためです。 <br/>**none**: DNS に送信側ドメインの DKIM TXT レコードが存在していないことを示します。|
|action|DMARC チェックの結果に基づいて、スパム フィルターが実行するアクションを示します。例: <br/>**permerror**: DMARC の評価時に永続的なエラーが発生したことを示します (DNS で正しくない形式の DMARC TXT レコードが見つかった場合など)。 このメッセージを再送信しようとしても、結果が異なる可能性はほとんどありません。 その代わりに、ドメインの所有者に問い合わせて問題を解決する必要があります。 <br/>**temperror**: DMARC の評価時に一時的なエラーが発生したことを示します。 メールが正しく処理されるように、少し時間をおいてからメッセージを送信するように、送信者に要求することもできます。 <br/>**oreject** または **o.reject**: 拒否の上書き (override reject) の略語。 この場合、Office 365 は、ポリシーが p=reject に設定されている DMARC TXT レコードを持つドメインからの DMARC チェックに失敗したメッセージを受信したときに、このアクションを使用します。 Office 365 はメッセージを削除または拒否する代わりに、スパムとしてメッセージにマークを付けます。 このように Office 365 が構成されている理由の詳細については、「[Office 365 が DMARC に失敗した受信メールを処理する方法](use-dmarc-to-validate-email.md#inbounddmarcfail)」を参照してください。 <br/>**pct.quarantine**: DMARC をパスしないメッセージのうち、100% 未満のある割合のメッセージはいずれにせよ配信されることを示します。 これは、メッセージが DMARC に失敗してポリシーが検疫に設定されますが、pct フィールドは 100% に設定されず、システムは指定されたドメインのポリシーに従って、DMARC アクションを適用しないことをランダムに判断しているということです。 <br/>**pct.reject**: DMARC をパスしないメッセージのうち、100% 未満のある割合のメッセージはいずれにせよ配信されることを示します。 これは、メッセージが DMARC に失敗してポリシーが拒否に設定されますが、pct フィールドは 100% に設定されず、システムは指定されたドメインのポリシーに従って、DMARC アクションを適用しないことをランダムに判断しているということです。|
|header.from|メール メッセージ ヘッダーの From アドレスのドメイン。 _5322.From_ アドレスともいいます。|
|compauth|複合認証の結果。 Office 365 が、SPF、DKIM、DMARC などのさまざまな種類の認証を組み合わせて、メッセージが認証されているかどうかを判断するために使用されます。 評価の基準として、差出人: ドメインを使用します。|
|理由|複合認証にパスした、または失敗した理由。 理由の値は 3 桁の数字で構成されます。 <br/>**000**: メッセージの認証が明示的に失敗しました。 たとえば、メッセージが DMARC をパスせず、検疫または却下のアクションが適用された場合などです。 <br/>**001**: メッセージの認証が暗黙的に失敗し、送信ドメインにより認証ポリシーが発行されませんでした。 たとえば、p = none の DMARC ポリシーなどです。 <br/>**1xx**: メッセージが認証をパスしました。 2 桁目は Office 365 で使用される内部コードです。 <br/>**2xx**: メッセージが認証を soft-pass しました。 2 桁目は Office 365 で使用される内部コードです。 <br/>**3xx**: メッセージに対して複合認証のチェックが実行されませんでした。 <br/>**4xx**: メッセージに対する複合認証が省略されました。 2 桁目は Office 365 で使用される内部コードです。|
|