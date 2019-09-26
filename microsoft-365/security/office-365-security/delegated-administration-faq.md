---
title: 代理管理の FAQ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: このトピックでは、代理で Office 365 の管理タスクを実行する (他のテナント (企業) のために Exchange Online Protection (EOP) を管理する機能を含む) Microsoft パートナーとリセラーを対象に、よく寄せられる質問とその答えを取り上げます。
ms.openlocfilehash: 8fcc409c9a5705ad824f7f74b3370afa07e650e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086740"
---
# <a name="delegated-administration-faq"></a>代理管理の FAQ

このトピックでは、代理で Office 365 の管理タスクを実行する (他のテナント (企業) のために Exchange Online Protection (EOP) を管理する機能を含む) Microsoft パートナーとリセラーを対象に、よく寄せられる質問とその答えを取り上げます。
  
 **Q. わたしはリセラーで、お客様のテナントを管理する必要があります。どのようにしたらいいですか？**
  
A. Microsoft のパートナーまたは販売店で、Microsoft advisor にサインアップする場合は、管理センター内でテナントを管理するためのアクセス許可を要求できます。 これは委任された管理と呼ばれ、組織内の管理者であるかのように、Office 365 テナント (EOP 設定を含む) を管理することができます。 委任された管理を実行する手順は次のとおりです。
  
1. [Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。

2. Office 365 の代理管理を行うためにサインアップします。カスタマーのアカウント管理を開始する前に、カスタマーから代理管理者としての承認を得る必要があります。承認を得るには、最初に[代理管理の提供をカスタマーに送ります](https://go.microsoft.com/fwlink/?LinkId=396829)。(後でカスタマーに代理管理を提供することもできます。)

3. 「[代理管理者を追加または削除する](https://go.microsoft.com/fwlink/?LinkId=396831)」の手順に従って、委任された管理者アカウントを作成します。

Office 365 代理管理のセットアップ方法について詳しくは、「[パートナー: ビジネスを構築して Office 365 パートナー アカウントを管理する](https://go.microsoft.com/fwlink/?LinkId=301485)」を参照してください。
  
 **Q. わたしはリセラーではなく顧客です。どのようにすれば、自分のサブ テナントの代理管理者をセットアップできますか？**
  
A. 現時点で、代理管理が行えるのはリセラーとパートナーのみです。しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。
  
 **Q. サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？**
  
A. 現在、Office 365 にその機能はありません。
  
 **Q. 自分のすべてのサブ テナントを統合したレポートを取得できますか？**
  
A. この時点では、管理している会社を超えた統合レポートを Microsoft 365 管理センターのレポートで使用することはできません。 ただし、これは、リモート Windows PowerShell または[Office 365 Reporting web サービス](https://go.microsoft.com/fwlink/?LinkId=279926)を使用して行うことができます。
