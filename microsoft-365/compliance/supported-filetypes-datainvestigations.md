---
title: データ調査でサポートされているファイルの種類 (プレビュー)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: サポートされているファイルの種類と、データ調査で閲覧できる閲覧者 (プレビュー) を一覧にした表。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b4aef30c3f2bc15c306a7561bab261bdb0bdcace
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034541"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>データ調査でサポートされているファイルの種類 (プレビュー)

データ調査 (プレビュー) では、さまざまな方法で多くのファイルの種類がサポートされています。次の表で説明します。 この一覧は最終処理されていません。検証テストを続行するときに、新しいファイルの種類を追加します。 この表は、証拠をレビューしているときに、利用可能なビューアーでファイルの種類を表示できるかどうかも示しています。

| Mime の種類 | File クラス | ネイティブビューアー | テキストビューアー | ビューアーに注釈を付ける | コンテナーの抽出 | 拡張機能 |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Document | はい | はい | はい | いいえ | .doc、.dat |
| application/pdf | Document | はい | はい | はい | いいえ | .pdf |
| アプリケーション/rtf | Document | はい | はい | はい | いいえ | .rtf;。.doc |
| application/vnd. が application | Document | はい | はい | はい | いいえ | .xls、.dat |
| アプリケーション/vnd を有効にします。12 | 生産性/オープンドキュメント形式 | はい | はい | 不要 | いいえ | .xlsb |
| アプリケーション/vnd を有効にします。12 | Document | はい | はい | はい | いいえ | .xlsm |
| アプリケーション/が application を有効にします。12 | 生産性/オープンドキュメント形式 | いいえ | はい | 不要 | いいえ | 。 xltm |
| application/vnd. ms-outlook | 生産性 | いいえ | いいえ | いいえ | いいえ | .msg |
| application/vnd. ms-outlook-pst | 生産性/コラボレーション | いいえ | いいえ | いいえ | はい | .pst |
| application/vnd. が application | Document | はい | はい | はい | いいえ | .ppt; .pps;。なべ |
| アプリケーション/vnd を有効にします。12 | Document | はい | はい | はい | いいえ | .docm |
| アプリケーション/が application を有効にします。12 | Document | はい | はい | はい | いいえ | normal.dotm |
| application/vnd. oasis | Document | はい | はい | はい | いいえ | odt  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Document | はい | はい | はい | いいえ | .pptx |
| openxmlformats-officedocument (アプリケーション/vnd) | 生産性/オープンドキュメント形式 | はい | はい | はい | いいえ | . ppsx |
| openxmlformats-officedocument (アプリケーション/vnd) | Document | はい | はい | はい | いいえ | . potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Document | はい | はい | はい | いいえ | .xlsx |
| application/vnd. openxmlformats-officedocument | Document | はい | はい | はい | いいえ | 。 xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Document | はい | はい | はい | いいえ | .docx |
| application/vnd. openxmlformats-officedocument | Document | はい | はい | はい | いいえ | .dotx |
| アプリケーション/vnd visio | Document | はい | はい | はい | いいえ | .vsd |
| アプリケーション/x-7z-圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | . 7z |
| application/xhtml + xml | Document | はい | はい | はい | いいえ | xhtml |
| application/xml | Document | はい | はい | はい | いいえ | .xml |
| アプリケーション/x-msaccess.exe | Document | はい | はい | はい | いいえ | .mdb |
| アプリケーション/x-mspublisher | Document | はい | はい | はい | いいえ | .pub |
| アプリケーション/x-rar 圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | rar |
| アプリケーション/zip | Archive/Container | いいえ | いいえ | いいえ | はい | .zip |
| image/bmp | イメージ | はい | はい | はい | いいえ | .bmp |
| イメージ/emf | イメージ | はい | はい | はい | いいえ | .emf |
| image/gif | Document | はい | はい | はい | いいえ | .gif |
| image/jpeg | イメージ | はい | はい | はい | いいえ | .jpg、.jpeg、...jpgt |
| image/png | イメージ | はい | はい | はい | いいえ | .png |
| image/tiff | イメージ | はい | はい | はい | いいえ | .tif |
| 画像/vnd. .dwg | Document | はい | はい | はい | いいえ | .dwg;。dxf |
| image/wmf | Document | はい | はい | はい | いいえ | .wmf |
| message/rfc822 | 生産性/コラボレーション | いいえ | いいえ | いいえ | いいえ | .eml |
| text/csv | Document | はい | はい | はい | いいえ | .csv |
| text/html | Document | はい | はい | はい | いいえ | .html;。shtml.dll; .htm |
| text/plain | Document | はい | はい | はい | いいえ | .txt、.css、。con; pl; .csv; .dat |
| テキスト/vcard-連絡先 | Document | はい | はい | はい | いいえ | .vcf |
||||||||
