---
title: DLP ポリシーを作成、テスト、調整する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: この記事では、組織のニーズに応じて DLP ポリシーを作成、テスト、および調整する方法について説明します。
ms.openlocfilehash: 3405fc99f4d12715972b1fd18a9c20dd9334382b
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45092007"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>DLP ポリシーを作成、テスト、調整する

データ損失防止 (DLP) は、組織が偶発的または偶発的で不要な機密情報を他者に公開しないようにするために設計されたコンプライアンス機能です。 DLP のルーツは Exchange Server および Exchange Online にあり、SharePoint Online および OneDrive for Business にも適用できます。

DLP は、コンテンツ分析エンジンを使用してメール メッセージおよびファイルのコンテンツを調べ、クレジット カード番号や個人を特定できる情報 (PII) などの機密情報を探します。 通常、機密情報はメール メッセージやファイルの暗号化などの追加の手順を実行せずにメールで送信したり、ドキュメントに含めたりするべきではありません。 DLP を使用することで機密情報を検出し、次のようなアクションを実行できます。

- 監査目的でイベントを記録する
- 電子メールを送信またはファイルを共有しているエンド ユーザーに警告を表示する
- メールまたはファイルの共有の実行を積極的にブロックする

保護が必要な種類のデータを持っていると自分が考えていないために、顧客が DLP を却下する場合があります。 医療記録や財務情報などの機密データは、ヘルスケアなどの業界またはオンライン ストアを運営する企業にのみ存在するという前提があります。 しかし、どんなビジネスでも、たとえ気付いていなくても定期的に機密情報を扱う場合があります。 従業員の名前および生年月日のスプレッドシートは、顧客名およびクレジット カードの詳細情報のスプレッドシートと同じくらい重要です。 そして、従業員は日々のタスクを静かに行っており、システムから CSV ファイルをエクスポートして誰かにメールで送信することに関して何も考えていないため、このタイプの情報は予想以上に多く出回っています。 また、従業員がクレジット カードまたは銀行の詳細情報を含むメールを結果を考慮せずに送信する頻度にも驚かれるかもしれません。

## <a name="how-sensitive-information-is-detected-by-dlp"></a>DLP による機密情報の検出方法

機密情報は、一致パターンに対する特定のキーワードの近接度など、他のインジケーターと組み合わせて、正規表現 (RegEx) パターンマッチングで識別されます。 この例として、クレジット カード番号が挙げられます。 VISA のクレジット カード番号は 16 桁です。 しかしながら、これらの数字は 1111-1111-1111-1111、1111 1111 1111 1111、または 1111111111111111 など、さまざまな方法で記述することができます。

16 桁の数字列は必ずしもクレジット カード番号とは限らず、ヘルプ デスク システムのチケット番号、またはハードウェアのシリアル番号である可能性があります。 クレジット カード番号と無害な 16 桁の数字列の違いを判断するために計算が実行され (チェックサム)、番号がさまざまなクレジット カード ブランドの既知のパターンに一致することを確認します。

さらに、"VISA" や "AMEX" などのキーワードと、クレジットカードの有効期限が切れる日付の間の類似性は、データがクレジットカード番号であるかどうかを決定することも検討しています。

言い換えれば、DLP は通常メール内のこれら 2 つのテキストの違いを認識するのに十分なほどスマートです。

- "新しいラップトップをご注文いただくことができます。 VISA カード1111-1111-1111-1111、有効期限11/22、および自分が所有しているときに送信する予定の日付を送信する
- "My ラップトップのシリアル番号は2222-2222-2222-2222 で、11/2010 で購入されました。 ところで、旅行 visa は承認されていますか?

ブックマークを保持するための適切な参照は、[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)で、各情報の種類が検出される方法を説明しています。

## <a name="where-to-start-with-data-loss-prevention"></a>データ損失防止を開始する場所

データ漏洩のリスクが完全に明らかではない場合、DLP の実装をどこから始めるべきかを正確に判断することは困難です。 さいわい、DLP ポリシーを "テストモード" で実行して、有効にする前に、その実効性と正確性を測定できます。

Exchange Online の DLP ポリシーは、Exchange 管理センターを介して管理できます。 ただし、セキュリティ/コンプライアンス センターを介してすべてのワークロードの DLP ポリシーを構成できるため、この記事のデモではこれを使用します。 セキュリティ/コンプライアンス センターでは、[**データ損失防止**] >  [**ポリシー**] の下に DLP ポリシーがあります。 [**ポリシーの作成**] をクリックして開始します。

Microsoft 365 には、DLP ポリシーの作成に使用できる一連の[dlp ポリシーテンプレート](what-the-dlp-policy-templates-include.md)が用意されています。 例えば、ここがオーストラリアの企業だとしましょう。 ポリシー テンプレートをフィルター処理し、オーストラリアに関連するもののみを表示できます。これらは金融、医療、健康、プライバシーの一般カテゴリに分類されます。

![国または地域を選択するオプション](../media/DLP-create-test-tune-choose-country.png)

このデモンストレーションでは、オーストラリアの個人を特定できる情報 (PII) データを選択します。これには、オーストラリアのタックス ファイル ナンバー (TFN) および運転免許証番号の情報の種類が含まれます。

![ポリシー テンプレートを選択するオプション](../media/DLP-create-test-tune-choose-policy-template.png)

新しい DLP ポリシーに名前を付けます。 規定の名前は DLP ポリシー テンプレートと一致しますが、同じテンプレートから複数のポリシーを作成できるため、よりわかりやすい独自の名前を選択する必要があります。

![ポリシーに名前を付けるオプション](../media/DLP-create-test-tune-name-policy.png)

ポリシーを適用する場所を選択します。 DLP ポリシーは Exchange Online、SharePoint Online、および OneDrive for Business に適用できます。 このポリシーは、すべての場所に適用されるように構成したまま残します。

![すべての場所を選択するオプション](../media/DLP-create-test-tune-choose-locations.png)

最初の**ポリシー設定**手順では、今のところは規定値をそのまま使用します。 DLP ポリシーでは行うことができるカスタマイズが非常に多くありますが、規定値は開始するのに適しています。

![保護するコンテンツの種類をカスタマイズするオプション](../media/DLP-create-test-tune-default-customization-settings.png)

[**次へ**] をクリックすると、カスタマイズ オプションが増えた追加の [**ポリシー設定**] ページが表示されます。 テストしているポリシーの場合、ここから調整を開始できます。

- 現時点ではポリシー ヒントをオフにしています。これは、テストを行っているだけであってまだユーザーに何も表示したくない場合に行う合理的な手順です。 ポリシー ヒントは、ユーザーに対して DLP ポリシーに違反しようとしているという警告を表示します。 たとえば Outlook ユーザーには添付したファイルにクレジット カード番号が含まれているという警告が表示され、メールが拒否されます。 ポリシー ヒントの目標は、非準拠の動作を発生前に停止することです。
- また、インスタンスの数を 10 から 1 に減らすことで、このポリシーがデータの一括共有だけでなくオーストラリアの PII データの共有を検出できるようにしました。
- また、インシデント レポートのメールに別の受信者を追加しました。

![追加のポリシー設定](../media/DLP-create-test-tune-more-policy-settings.png)

最後に、最初はテスト モードで実行するようにこのポリシーを構成しました。 ここには、テスト モード中にポリシー ヒントを無効にするオプションもあります。 これにより、ポリシー内でポリシー ヒントを有効にする柔軟性が得られますが、それらを表示するか非表示にするかをテスト中に決定します。

![最初にポリシーをテストするオプション](../media/DLP-create-test-tune-test-mode.png)

最終確認画面で [**作成**] をクリックして、ポリシーの作成を完了します。

## <a name="test-a-dlp-policy"></a>DLP ポリシーをテストする

新しい DLP ポリシーは、約 1 時間以内に有効になります。 通常のユーザー アクティビティによってトリガーされるのを待つことも、試しに自分でトリガーすることもできます。 前述の[「機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」にリンクされており、DLP 一致をトリガーする方法に関する情報を提供します。

例として、この記事のために作成した DLP ポリシーはオーストラリアのタックス ファイル ナンバー (TFN) を検出します。 ドキュメントによると、一致は以下の基準に基づいています。

![オーストラリアのタックス ファイル ナンバーに関するドキュメント](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Blunt のように、TFN の検出をデモンストレーションするために、"税ファイル番号" という単語を持つ電子メールと、近接している9桁の文字列は、問題を発生させることなく sail ます。 DLP ポリシーがトリガーされない理由は、9 桁の数字列が無害な数字の文字列ではなく有効な TFN であることを示すチェックサムに合格する必要があるためです。

![チェックサムに合格しないオーストラリアのタックス ファイル ナンバー](../media/DLP-create-test-tune-email-test1.png)

これに対して、"税ファイル番号" という語句を持つ電子メールと、チェックサムを渡す有効な TFN がポリシーをトリガーします。 実際には、私が使用している TFN は有効ではあるものの本物ではない TFN を生成する Web サイトから取得したものです。 DLP ポリシーをテストする際の最も一般的な間違いの 1 つは、有効ではなくチェックサムを渡さない (したがってポリシーをトリガーしない) 偽の番号を使用することです。したがって、そういったサイトはとても便利です。

![チェックサムに合格したオーストラリアのタックス ファイル ナンバー](../media/DLP-create-test-tune-email-test2.png)

インシデント レポートのメールには、検出された機密情報の種類、検出されたインスタンスの数、および検出の信頼レベルが含まれています。

![検出されたタックス ファイル ナンバーを示すインシデント レポート](../media/DLP-create-test-tune-email-incident-report.png)

DLP ポリシーをテスト モードのままにしてインシデント レポートのメールを分析すると、DLP ポリシーの正確性およびそれが適用されたときの効果について感触をつかむことができます。 インシデント レポートに加えて、[DLP レポートを使用](view-the-dlp-reports.md)してテナント全体でのポリシーの一致の集計ビューを表示できます。

## <a name="tune-a-dlp-policy"></a>DLP ポリシーを調整する

ポリシーのヒットを分析する際に、ポリシーの動作を調整する必要があるかもしれません。 簡単な例として、メール内に 1 つ TFN がある場合には問題がないと判断するとします (もちろん問題があるとは思いますが、デモのためにこの方法を使います)。しかし、問題は 2 つ以上のインスタンスです。 複数のインスタンスは、従業員が HR データベースから外部パーティ (外部会計サービスなど) に CSV エクスポートをメールで送信するなどの危険性を持ったシナリオである可能性があります。 間違いなく、検出してブロックしたいはずです。

セキュリティ/コンプライアンス センターでは、既存のポリシーを編集して動作を調整できます。

![ポリシーを編集するオプション](../media/DLP-create-test-tune-edit-policy.png)
 
ポリシーが特定のワークロードまたは特定のサイトおよびアカウントにのみ適用されるように、場所の設定を調整できます。

![特定の場所を選択するオプション](../media/DLP-create-test-tune-edit-locations.png)

また、ポリシー設定を調整し、ニーズに合わせてルールを編集することもできます。

![ルールを編集するオプション](../media/DLP-create-test-tune-edit-rule.png)

DLP ポリシー内のルールを編集する際、以下を変更できます。

- ルールをトリガーする機密データのインスタンスの種類および数を含む条件。
- コンテンツへのアクセス制限などの、実行されるアクション。
- ユーザー通知。メール クライアントまたは Web ブラウザーでユーザーに表示されるポリシー ヒントです。
- ユーザーによる上書き。ユーザーがメールまたはファイル共有を続行するかどうかを決定します。
- 管理者に通知するためのインシデント レポート。

![ルールの一部を編集するオプション](../media/DLP-create-test-tune-editing-options.png)

このデモンストレーションでは、ポリシーにユーザー通知を追加し (適切なユーザー認識トレーニングなしで行う場合には注意してください)、ユーザーがビジネス上の理由または誤検知としてフラグを立てることでポリシーを上書きすることを許可しました。 組織のポリシーに関する追加情報を含める場合にはメールおよびポリシー ヒントのテキストをカスタマイズしたり、質問がある場合にはサポートに連絡するようユーザーに促したりすることもできることに注意してください。

![ユーザー通知および上書きのオプション](../media/DLP-create-test-tune-user-notifications.png)

このポリシーには高ボリュームおよび低ボリュームの処理に関する 2 つのルールが含まれているため、必要なアクションでは必ず両方を編集してください。 これは、その特性に応じてケースを異なる方法で処理する機会となっています。 たとえば、低ボリューム違反への上書きは許可しても、高ボリューム違反への上書きは許可しない場合などです。

![高ボリューム用の 1 つのルールおよび低ボリューム用の 1 つのルール](../media/DLP-create-test-tune-two-rules.png)

また、ポリシーに違反しているコンテンツへのアクセスを実際にブロックまたは制限したい場合には、そうするようにルールでアクションを構成する必要があります。

![コンテンツへのアクセスを制限するオプション](../media/DLP-create-test-tune-restrict-access-action.png)

ポリシー設定へのこれらの変更を保存した後、ポリシーのメイン設定ページに戻り、ポリシーがテスト モードのときにユーザーにポリシー ヒントを表示するオプションを有効にする必要もあります。 これは、エンド ユーザーに DLP ポリシーを紹介し、生産性に影響を与える多数の誤検知のリスクを負うことなくユーザーの意識向上トレーニングを行う効果的な方法です。

![テスト モードでポリシー ヒントを表示するオプション](../media/DLP-create-test-tune-show-policy-tips.png)

サーバー側 (または必要に応じてクラウド側) では、さまざまな処理間隔により、変更がすぐに有効にならない場合があります。 ユーザーに新しいポリシー ヒントを表示する DLP ポリシーの変更を行っている場合、Outlook クライアントは 24 時間ごとにポリシーの変更をチェックするのでユーザーには変更がすぐに反映されない場合があります。 テストのためにスピードを上げたい場合には、このレジストリ修正を使用して [PolicyNudges キーから最終ダウンロードのタイムスタンプをクリア](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)できます。 Outlook は次回再起動してメール メッセージの作成を開始する際に、最新のポリシー情報をダウンロードします。

ポリシー ヒントを有効にしている場合、ユーザーは Outlook でヒントの表示を開始し、誤検知が発生した場合に報告することができます。

![誤検知を報告するオプションを備えたポリシー ヒント](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>誤検知を調査する

DLP ポリシー テンプレートは、そのままでは完璧ではありません。 自身の環境で誤検出が発生する可能性は高いため、DLP 展開への道を容易にし、適切なポリシーのテストおよび調整に時間をかけることが非常に重要です。

これが誤検知の例です。 このメールは、まったくの無害です。 ユーザーは自分の携帯電話番号を誰かに提供し、メールに署名を含めています。

![誤検知情報を示すメール](../media/DLP-create-test-tune-false-positive-email.png)
 
しかしユーザーには、メールに機密情報、具体的にはオーストラリアの運転免許証番号が含まれていることを警告するポリシー ヒントが表示されます。

![ポリシー ヒントで誤検知を報告するオプション](../media/DLP-create-test-tune-policy-tip-closeup.png)

ユーザーは誤検知を報告でき、管理者はそれが発生した理由を調べることができます。 インシデント レポートのメールには、誤検知のフラグが設定されています。

![誤検知を示すインシデント レポート](../media/DLP-create-test-tune-false-positive-incident-report.png)

この運転免許証のケースは、掘り下げるにはちょうど良い例です。 この誤検知が発生した理由は、"オーストラリアのドライバーのライセンス" の種類が、キーワード "シドニー nsw" (大文字と小文字を区別しない) の300文字以内の9桁の文字列でトリガーされるためです。 そのため、ユーザーがたまたまシドニーにいるという理由だけで、電話番号とメール署名によってトリガーされます。


1 つのオプションは、オーストラリアの運転免許証の情報の種類をポリシーから削除することです。 DLP ポリシー テンプレートの一部なのでそこに含まれていますが、強制的に使用する必要はありません。 運転免許証ではなくタックス ファイル ナンバーのみに関心がある場合には、削除して構いません。 たとえば、ポリシーの低ボリューム ルールからそれを削除しながらも、複数の運転免許証のリストがまだ検出されるように高ボリューム ルールにはそのままそれを残しておくことができます。

![機密情報の種類をルールから削除するオプション](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
別のオプションとしては、単純にインスタンス数を増やすことが挙げられます。これにより、複数のインスタンスがある場合にのみ少量の運転免許証が検出されます。

![インスタンス数を編集するオプション](../media/DLP-create-test-tune-edit-instance-count.png)

インスタンス数の変更に加えて、一致の精度 (または信頼レベル) を調整することもできます。 機密情報の種類に複数のパターンがある場合、ルールが特定のパターンのみに一致するように、ルールの一致の精度を調整できます。 たとえば、誤検出を減らすためにルールの一致の精度を設定して、最も高い信頼レベルを持つパターンのみと一致するようにできます。 信頼レベルの計算方法を理解することは少し難しい (そしてこの投稿の範囲を超えている) のですが、ここに[信頼レベルを使用してルールを調整する方法](data-loss-prevention-policies.md#match-accuracy)の良い説明があります。

さらに高度な機能を利用する場合は、機密情報の種類をカスタマイズすることができます。たとえば、[オーストラリアドライバーのライセンス番号](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)のキーワードの一覧から "シドニー NSW" を削除して、上記の誤検知を排除することができます。 XML および PowerShell を使用してこれを行う方法については、[組み込みの機密情報の種類のカスタマイズ](customize-a-built-in-sensitive-information-type.md)に関するこのトピックを参照してください。

## <a name="turn-on-a-dlp-policy"></a>DLP ポリシーを有効にする

DLP ポリシーが機密情報の種類を正確かつ効果的に検出し、エンド ユーザーが設定されたポリシーに対処する準備ができていることに満足したら、ポリシーを有効にできます。

![ポリシーをオンにするオプション](../media/DLP-create-test-tune-turn-on-policy.png)
 
ポリシーを有効にする時期を待っている場合には、[セキュリティ/コンプライアンス センターの PowerShell に接続し](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)、[Get-DlpCompliancePolicy コマンドレット](https://docs.microsoft.com/powershell/module/exchange/get-dlpcompliancepolicy?view=exchange-ps)を実行して DistributionStatus を確認します。

![PowerShell でコマンドレットを実行する](../media/DLP-create-test-tune-PowerShell.png)

DLP ポリシーをオンにした後、独自の最終テストをいくつか実行し、予想されるポリシー アクションが発生していることを確認する必要があります。 クレジット カード データなどをテストしようとしている場合、チェックサムを通過しポリシーをトリガーするサンプルのクレジット カードやその他の個人情報を生成する方法についての情報を掲載した Web サイトがオンラインにあります。

ユーザーによる上書きを許可するポリシーは、ポリシー ヒントの一部としてユーザーにそのオプションを提示します。

![ユーザーによる上書きを許可するポリシー ヒント](../media/DLP-create-test-tune-override-option.png)

コンテンツを制限するポリシーは、ポリシー ヒントの一部としてユーザーに警告を表示しユーザーがメールを送信できないようにします。

![コンテンツが制限されているポリシー ヒント](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>概要

データ損失防止ポリシーは、あらゆるタイプの組織に役立ちます。 一部の DLP ポリシーのテストは、ポリシー ヒント、エンド ユーザーによる上書き、インシデント レポートなどを制御できるため、リスクの低い演習です。 一部の DLP ポリシーを静かにテストし、組織で既に発生している違反の種類を確認し、誤検知率の低いポリシーを作成し、許可されているものと許可されていないものについてユーザーを教育し、DLP ポリシーを組織へとロールアウトします。
