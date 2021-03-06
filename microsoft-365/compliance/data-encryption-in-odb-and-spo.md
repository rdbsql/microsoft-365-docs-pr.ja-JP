---
title: OneDrive for Business および SharePoint Online におけるデータ暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817926"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business および SharePoint Online におけるデータ暗号化

OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。
  
## <a name="security-and-data-encryption-in-office-365"></a>Office 365 のセキュリティとデータ暗号化

Microsoft 365 は、高度なセキュリティで保護された環境で、物理データセンターのセキュリティ、ネットワークセキュリティ、アクセスセキュリティ、アプリケーションセキュリティ、およびデータセキュリティがあります。 この記事では特に、OneDrive for Business および SharePoint Online のデータセキュリティの、送信中およびインプレース暗号化側に焦点を当てます。
  
データの暗号化の仕組みについて、次のビデオをご覧ください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>転送中データの暗号化

OneDrive for Business と SharePoint Online では、データを入力してデータセンターを終了する2つのシナリオがあります。
  
- **クライアントとサーバーとの通信**インターネット経由での OneDrive for business への通信では、SSL/TLS 接続が使用されます。 すべての SSL 接続は、2048ビットのキーを使用して確立されます。

- **データセンター間のデータ移動**データセンター間でデータを移動する主な理由は、geo レプリケーションを使用して障害復旧を可能にすることです。 たとえば、SQL Server のトランザクションログと blob ストレージのデルタは、このパイプに沿って移動します。 このデータは、プライベートネットワークを使用して既に送信されていますが、クラス最高の暗号化を使用してさらに保護されています。 

## <a name="encryption-of-data-at-rest"></a>保管中データの暗号化

保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。
  
BitLocker は、OneDrive for business と SharePoint Online のサービス全体に展開されます。 また、ファイルごとの暗号化は、Microsoft 365 マルチテナントと、マルチテナントテクノロジに基づいて構築された新しい専用環境の OneDrive for Business および SharePoint Online にも含まれています。
  
BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。 つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。 保存される前に、暗号化されたコンテンツに対するキーがコンテンツとは物理的に離れた場所に保存されます。 この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。 暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。 これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。
  
FIPS 140-2 準拠の詳細については、「 [fips 140-2 コンプライアンス](https://go.microsoft.com/fwlink/?LinkId=517625)」を参照してください。
  
ファイル レベルでの保管中の暗号化では Blob ストレージを活用し、事実上無制限のストレージ拡張を行ったり、前例のないレベルの保護機能を提供したりできます。 OneDrive for Business と SharePoint Online のすべてのお客様のコンテンツは blob ストレージに移行されます。 データのセキュリティ保護の方法は次のとおりです。
  
1. すべてのコンテンツが暗号化されます。その場合、複数のキーを使用して暗号化されることもあります。暗号化されたデータはデータセンターで分散されます。格納される各ファイルはサイズに応じて 1 つ以上のチャンクに分けられます。その後、各チャンクは固有のキーを使用して暗号化されます。更新作業も同様に処理されます。つまり、ユーザーによって送信された一連の変更または差分がチャンクに分けられ、それぞれが独自のキーで暗号化されます。

2. これらのチャンク ファイル、ファイル セット、更新差分すべては Blob ストア内で Blob として格納されます。これらのファイルはまた、複数の Blob コンテナーでランダムに分散されます。

3. コンポーネントからファイルを再構築するために使用される "マップ" は、コンテンツデータベースに格納されます。

4. それぞれの Blob コンテナーには、アクセスの種類 (読み取り、書き込み、列挙、削除) ごとに独自の資格情報があります。各資格情報セットはセキュリティが確保されたキー ストアで保管され、定期的に更新されます。

つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。
  
- Blob ストアには、コンテンツが暗号化 Blob として格納されます。コンテンツの各チャンクのキーが暗号化されて、コンテンツ データベースに別個に格納されます。コンテンツ自体は、暗号化解除方法に関する糸口を含めずに保持されます。

- コンテンツデータベースは SQL Server データベースです。 Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。

これら 3 つのコンポーネント (Blob ストア、コンテンツ データベース、キー ストア) はそれぞれ物理的に別の場所にあります。いずれかのコンポーネントに保管されている情報は、それ自体では使用できません。それにより、これまでにないレベルのセキュリティが実現します。これら 3 つのすべてのコンポーネントにアクセスしない限りは、チャンクのカギを取得すること、キーを暗号化解除して使用できるようにすること、キーと対応するチャンクを関連付けること、チャンクを暗号化解除すること、構成チャンクからドキュメントを再構築することはいずれも不可能です。
