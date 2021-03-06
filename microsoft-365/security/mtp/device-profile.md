---
title: Microsoft 365 セキュリティポータルのデバイスプロファイル
description: 組織内のデバイスのリスクと露出レベルを表示します。 過去および現在の脅威を分析し、デバイスを最新の更新プログラムで保護します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、Microsoft Threat Protection、MTP、セキュリティセンター、Microsoft Defender ATP、Office 365 ATP、Azure ATP、デバイスページ、デバイスプロファイル、コンピューターページ、コンピュータープロファイル
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "43517038"
---
# <a name="device-profile-page"></a>デバイスプロファイルページ

Microsoft 365 セキュリティポータルはデバイスプロファイルページを提供するので、ネットワーク上のデバイスの正常性と状態をすばやく評価できます。

> [!IMPORTANT]
> デバイスが Microsoft Defender ATP、Azure ATP、またはその両方に登録されているかどうかによって、デバイスプロファイルページがわずかに異なる場合があります。

デバイスが Microsoft Defender ATP に登録されている場合は、[デバイスプロファイル] ページを使用して、いくつかの一般的なセキュリティタスクを実行することもできます。

## <a name="navigating-the-device-profile-page"></a>デバイスプロファイルページのナビゲーション

プロファイルページは、さまざまなセクションに分かれています。

![(1) タブ領域 (2) サイドバーと (3) アクションが赤で強調表示されているデバイスプロファイルページのイメージ](../../media/mtp-device-profile/hybrid-device-overall.png)

サイドバー (1) には、デバイスに関する基本的な詳細が表示されます。

メインコンテンツ領域 (2) には、デバイスに関するさまざまな種類の情報を表示するために切り替えることができるタブが含まれています。

デバイスが Microsoft Defender ATP に登録されている場合は、応答アクションの一覧も表示されます (3)。 応答アクションを使用すると、セキュリティ関連の一般的なタスクを実行できます。

## <a name="sidebar"></a>サイドバー

[デバイスプロファイル] ページのメインコンテンツ領域の横に、サイドバーがあります。

![デバイスプロファイルの [サイドバー] タブのイメージ](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

サイドバーには、デバイスの完全な名前と露出レベルが一覧表示されます。 また、以下のように、次のようないくつかの重要な基本的な情報を、開いた場合と閉じて設定したサブセクションで提供することもできます。

* **タグ**-デバイスに関連付けられている MICROSOFT Defender Atp、Azure atp、またはカスタムタグ。 Azure ATP からのタグは編集できません。
* **セキュリティ情報**-インシデントとアクティブなアラートを開きます。 Microsoft Defender ATP に登録されているデバイスには、露出レベルとリスクレベルも表示されます。

> [!TIP]
> 露出レベルは、デバイスがセキュリティ上の推奨事項とどの程度準拠しているかに関係していますが、リスクレベルは、アクティブな通知の種類や重要度など、さまざまな要因に基づいて計算されます。

* **デバイスの詳細**-デバイスが最初に表示されたときのドメイン、OS、タイムスタンプ、IP アドレス、リソース。 Microsoft Defender ATP に登録されているデバイスには、正常性の状態も表示されます。 Azure ATP に登録されたデバイスは、最初にデバイスが作成されたときの SAM 名とタイムスタンプを表示します。
* **ネットワークアクティビティ**-最初の時点でのタイムスタンプ、およびデバイスがネットワーク上で最後に表示された時刻。
* **ディレクトリデータ**(*Azure ATP に登録されているデバイス専用*)- [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview)のフラグ、 [spn](https://docs.microsoft.com/windows/win32/ad/service-principal-names)、およびグループメンバーシップ。

## <a name="response-actions"></a>応答アクション

応答アクションは、脅威を迅速に防御して分析する方法を提供します。

![デバイスプロファイルのアクションバーの画像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [応答アクション](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)は、デバイスが MICROSOFT Defender ATP に登録されている場合にのみ使用できます。
> * Microsoft Defender ATP に登録されているデバイスでは、デバイスの OS とバージョン番号に基づいて、異なる数の応答アクションが表示されることがあります。

[デバイスプロファイル] ページで使用可能なアクションは次のとおりです。

* **タグの管理**-このデバイスに適用したカスタムタグを更新します。
* **デバイスの分離**-Microsoft Defender Advanced Threat Protection に接続された状態を維持したまま、組織のネットワークからデバイスを分離します。 通信目的で、デバイスが分離されている間、Outlook、Teams、および Skype for Business を実行することを選択できます。
* **アクションセンター** -送信されたアクションの状態を表示します。 別のアクションが既に選択されている場合にのみ使用できます。
* **アプリの実行を制限**する-Microsoft によって署名されていないアプリケーションが実行されないようにします。
* **ウイルス対策スキャンを実行**する-Windows Defender ウイルス対策の定義を更新し、すぐにウイルス対策スキャンを実行します。 クイックスキャンまたはフルスキャンのどちらかを選択します。
* **収集調査パッケージ**-デバイスに関する情報を収集します。 調査が完了したら、ダウンロードすることができます。
* [ **Live Response Session を開始**する-[詳細なセキュリティ調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)のためにデバイス上のリモートシェルをロードします。
* **自動化**された調査を開始します。脅威を自動的に調査[し、remediates](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)します。 自動調査を手動でトリガーしてこのページから実行することもできますが、[特定のアラートポリシーによっ](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies)て自動的に調査がトリガーされます。
* **アクションセンター** -現在実行されているすべての応答アクションに関する情報を表示します。

## <a name="tabs-section"></a>[タブ] セクション

[デバイスプロファイル] タブを使用すると、デバイスに関するセキュリティ詳細の概要と、通知のリストを含むテーブルを切り替えることができます。

Microsoft Defender ATP に登録されているデバイスには、タイムラインを機能するタブ、セキュリティに関する推奨事項の一覧、ソフトウェアインベントリ、検出された脆弱性の一覧、および KBs (セキュリティ更新プログラム) が表示されます。

### <a name="overview-tab"></a>[概要] タブ

既定のタブは**概要**です。 これにより、デバイスに関する最も重要なセキュリティの事実をすばやく確認できます。

![デバイスプロファイルの [概要] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

ここでは、デバイスのアクティブな通知と、現在ログオンしているユーザーを簡単に確認できます。

デバイスが Microsoft Defender ATP に登録されている場合は、デバイスのリスクレベルとセキュリティ評価に関する利用可能なデータも表示されます。 セキュリティ評価では、デバイスの公開レベルについて説明し、セキュリティに関する推奨事項を提示し、影響を受けるソフトウェアと検出された脆弱性を一覧表示します。

### <a name="alerts-tab"></a>[通知] タブ

[**通知**] タブには、Azure Atp と MICROSOFT Defender atp の両方から、デバイス上で発生した通知の一覧が含まれています。

![デバイスプロファイルの [通知] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

表示されるアイテムの数、およびアイテムごとに表示される列をカスタマイズできます。 既定の動作は、ページごとに30個のアイテムを一覧表示することです。

このタブの列には、アラートをトリガーした脅威の重要度、状態、調査状態、およびアラートが割り当てられている人物に関する情報が含まれています。

[*影響を受けるエンティティ*] 列は、現在表示されているプロファイルを含むデバイス (エンティティ)、および影響を受けるネットワーク内の他のデバイスを参照します。

このリストからアイテムを選択すると、選択した通知に関する詳細情報が含まれているフライアウトが開きます。

このリストは、重要度、状態、または通知の割り当て先によってフィルター処理できます。

### <a name="timeline-tab"></a>[タイムライン] タブ

[**タイムライン**] タブには、デバイス上で発生したすべてのイベントを示す対話的な時系列のグラフが含まれています。 グラフの強調表示された領域を左または右に移動すると、さまざまな期間にわたるイベントを表示できます。 対話型のグラフとイベントの一覧の間にあるドロップダウンメニューから、ユーザー設定の日付の範囲を選択することもできます。

グラフの下に、選択した日付範囲のイベントの一覧が表示されます。

![デバイスプロファイルの [タイムライン] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

表示されるアイテムの数とリストの列の両方をカスタマイズできます。 既定の列には、イベント時間、アクティブなユーザー、アクションの種類、エンティティ (プロセス)、およびイベントに関する追加情報が表示されます。

このリストから項目を選択すると、イベントエンティティグラフが表示されたフライアウトが開き、イベントに含まれる親と子のプロセスが示されます。

リストは特定の種類のイベントによってフィルター処理できます。たとえば、レジストリイベントや Smart Screen イベントなどがあります。

また、リストを CSV ファイルにエクスポートして、ダウンロードすることもできます。 ファイルはイベント数によって制限されませんが、エクスポートできる最大時間は7日です。

### <a name="security-recommendations-tab"></a>[セキュリティの推奨事項] タブ

[**セキュリティの推奨事項**] タブには、デバイスを保護するために実行できるアクションが一覧表示されます。 このリストで項目を選択すると、推奨事項の適用方法を説明するポップアップが表示されます。

![デバイスプロファイルの [セキュリティの推奨事項] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

前のタブと同様に、ページごとに表示されるアイテムの数と、表示されている列もカスタマイズできます。

既定のビューには、セキュリティの弱点の詳細、関連する脅威、脅威の影響を受ける関連コンポーネントまたはソフトウェアなどの列が含まれています。 アイテムは、推奨の状態によってフィルター処理できます。

### <a name="software-inventory"></a>ソフトウェア インベントリ

[**ソフトウェアインベントリ**] タブには、デバイスにインストールされているソフトウェアが表示されます。

![デバイスプロファイルの [ソフトウェアインベントリ] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

既定の表示では、ソフトウェアベンダー、インストールされているバージョン番号、既知のソフトウェアの弱点の数、脅威の insights、製品コード、およびタグが表示されます。 表示されるアイテムの数と表示される列の両方をカスタマイズできます。

この一覧から項目を選択すると、選択したソフトウェアの詳細と、ソフトウェアが最後に検出されたときのパスとタイムスタンプを含むフライアウトが開きます。

このリストは、製品コードによってフィルター処理できます。

### <a name="discovered-vulnerabilities-tab"></a>[検出された脆弱性] タブ

[**検出**された脆弱性] タブには、デバイスに影響を与える可能性のある一般的な脆弱性と悪用 (cves) が一覧表示されます。

![デバイスプロファイルの [検出された脆弱性] タブの画像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

既定のビューには、CVE の重要度、共通の脆弱性スコア (CVS)、CVE に関連するソフトウェア、cve が発行されたとき、CVE が最後に更新された日時、および CVE に関連付けられている脅威が表示されます。

前のタブと同様に、表示されるアイテムの数と表示される列はカスタマイズできます。

この一覧から項目を選択すると、CVE を説明するフライアウトが開きます。

### <a name="missing-kbs"></a>KBs がありません

[ **Kb がありません**] タブには、デバイスにまだ適用されていない Microsoft 更新プログラムが一覧表示されます。 質問の "KBs" は、これらの更新を説明する[サポート技術情報の記事](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query)です。たとえば、 [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)のようになります。

![デバイスプロファイル用に [不足] タブのイメージ](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

既定の表示では、更新プログラム、OS バージョン、影響を受けた製品、CVEs アドレス、KB 番号、タグを含むセキュリティ情報が一覧表示されます。

ページごとに表示されるアイテムの数と表示される列は、カスタマイズできます。

アイテムを選択すると、更新プログラムにリンクするポップアップが開きます。

## <a name="related-topics"></a>関連項目

* [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
* [Microsoft Threat Protection を有効にする](mtp-enable.md)
* [Live response を使用してデバイスのエンティティを調査する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Office 365 での自動調査および対応 (AIR)](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
