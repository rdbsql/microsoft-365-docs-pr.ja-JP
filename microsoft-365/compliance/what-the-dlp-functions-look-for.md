---
title: DLP 関数の検索対象
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 定義済みの機密情報の種類がどのように機能するかを理解するために、データ損失防止 (DLP) 関数がどのような意味を持つかを説明します。
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819277"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 関数の検索対象

データ損失防止 (DLP) には、クレジットカード番号、EU デビットカード番号などの機密情報の種類が含まれています。これは、DLP ポリシーで使用する準備ができています。 これらの機密情報の種類では、特定のパターンが検索され、適切な書式設定とチェックサムを適用し、関連するキーワードまたはその他の情報を検索することによって、corroborate します。 この機能の一部は、内部機能によって実行されます。 たとえば、クレジットカード番号の機密情報の種類では、有効期限として書式設定された日付を検索するために関数を使用しています。これは、corroborate がクレジットカード番号であることを示すために役立ちます。
  
このトピックでは、定義済みの機密情報の種類がどのように機能するかを理解するために、これらの関数がどのようなものかを説明します。 詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。
  
## <a name="func_us_date"></a>Func_us_date

この関数は、米国でよく使用される形式の日付を検索します。これには、"月/日/年"、"月-日-年"、"月間年月日" の形式が含まれます。 月の名前または省略形は、大文字と小文字を区別しません。 
  
例:
  
- 2016年12月2日
    
- 2016年12月2
    
- 02 2016 年12月
    
- 12/2/2016
    
- 12/02/16
    
- 2-2016 年12月
    
- 12-2-16
    
受諾された月の名前:
  
- English
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - Jan 7 月2日5月5日5月5日5月5日。
    
## <a name="func_eu_date"></a>Func_eu_date

この関数は、E.U. でよく使用される形式で日付を検索します。 (米国以外の場所)。 これには、"日/月/年"、"年月日"、"day month" の形式が含まれます。 月の名前または省略形は、大文字と小文字を区別しません。
  
例:
  
- 2016年12月2時
    
- 02 dec 2016
    
- 2月16時
    
- 2/12/2016
    
- 02/12/16
    
- 2016年12月2時
    
- 2-12-16
    
受諾された月の名前:
  
- English
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - Jan 7 月2日5月5日5月5日5月5日。
    
- オランダ語
    
  - januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月
    
  - 1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)
    
- フランス語
    
  - janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv. févr. mars avril mai juin juil。 août 9 月 oct. 年11月. déc.
    
- ドイツ語
    
  - jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember
    
  - Jan./Jän。 März Mai Juni Juli 年8月9日。 11月. Dez。
    
- イタリア語
    
  - gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn。 febbr。 年. 4. magg giluglio ag はありません。 設定. ott。 年11月. .dic.
    
- ポルトガル語
    
  - ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev 3 月 abr mai 6 月5日前にセットアップする
    
- スペイン語
    
  - enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero feb marzo abr。 6月 o 日 年. /set. 年9月. oct. 年11月. .dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (非推奨)

> [!NOTE]
> この関数は、上記の関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました `Func_eu_date` 。 
  
この関数は、ポルトガル語でよく使用される形式で日付を検索します。 この関数の形式は、使用されている `Func_eu_date` 言語でのみ異なります。
  
例:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
受諾された月の名前:
  
- ポルトガル語
    
  - ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev 3 月 abr mai 6 月5日前にセットアップする
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (非推奨)

> [!NOTE]
> この関数は、上の関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました `Func_eu_date` 。 
  
この関数は、オランダ語でよく使用される形式で日付を検索します。 この関数の形式は、使用されている `Func_eu_date` 言語でのみ異なります。
  
例:
  
- 2 mei 2016
    
- 02 mei 2016
    
- 2 mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-mei-2016
    
- 2-12-16
    
受諾された月の名前:
  
- オランダ語
    
  - januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月
    
  - 1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)
    
## <a name="func_expiration_date"></a>Func_expiration_date

この関数は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。これにより、月の代わりに日付が除外されます。 この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。 月の名前または省略形は、大文字と小文字を区別しません。
  
例:
  
- MM/YY--たとえば、01/11 または1/11
    
- MM/YYYY--たとえば、01/2011 または1/2011
    
- MM-YY--たとえば、01-22 または1-11
    
- MM-YYYY--たとえば、01-2000 または1-2000
    
次の形式では、YY または YYYY がサポートされています。
  
- 月-YYYY--たとえば、のようになります。2010または2010または1月10日または1月10日
    
- 月 YYYY--たとえば、' january 2010 ' または ' Jan 2010 ' または ' Jan 10 ' または ' Jan 10 ' のようになります。
    
- 月 Yyyy--たとえば、' january2010 ' または ' Jan2010 ' または ' january10 ' または ' Jan10 '
    
- Month/YYYY--たとえば、' january/2010 '、' Jan/2010 '、' jan/10 '、または ' Jan/10 '
    
受諾された月の名前:
  
- English
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - 1月2日から4月5日 (年7月)
    
## <a name="func_us_address"></a>Func_us_address

この関数は、米国の都道府県名または郵便省略形の後に、郵便番号で使用されるのと同様に、有効な郵便番号を検索します。 郵便番号は、米国の州名または略語に関連付けられている正しい zip コードのいずれかである必要があります。 米国の都道府県名と郵便番号は、句読点または文字で区切ることはできません。
  
例:
  
- ワシントン98052
    
- ワシントン98052-9998
    
- WA 98052
    
- WA 98052-9998
    

