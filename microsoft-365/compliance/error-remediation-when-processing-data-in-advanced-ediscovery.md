---
title: データ処理中のエラー修復
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
description: ''
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085967"
---
# <a name="error-remediation-when-processing-data"></a>データ処理中のエラー修復

エラー修復により、電子情報開示管理者は、コンテンツを適切に処理できなくなるデータの問題を修正することができます。 たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。 エラー修復を使用すると、電子情報開示管理者は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復したファイルをアップロードできます。

次のワークフローを使用して、高度な電子情報開示ケースでエラーが発生したファイルを修復します。

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>エラー修復セッションを作成して処理エラーが発生したファイルを修復する

>[!NOTE]
>次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューの [ **Remediations** ] を選択して、[**処理**] タブのエラー修復セッションに戻ることができます。

1. 高度な電子情報開示ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択し、[**範囲**] ドロップダウンメニューからレビューセットまたはケース全体を選択します。 このセクションでは、特定のレビューセットのケースまたはエラーに関するすべてのエラーを表示します。

   ![エラーの修復](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。  次の例では、パスワードで保護されたファイルを修復しています。

3. [**新しいエラーの修復**] をクリックします。

    エラー修復ワークフローは、エラーが発生したファイルを Microsoft 提供の Azure ストレージの場所にコピーして、それをローカルコンピューターにダウンロードして修復できるようにする準備段階から始まります。

    ![エラー修復の準備](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。

    ![ファイルをダウンロードする](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。 これは、ファイルがダウンロードされるローカルコンピューター上の親フォルダーへのパスです。  既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。 このパスは必要に応じて変更できます。 これを変更する場合は、最適なパフォーマンスを得るためにローカルファイルパスを使用することをお勧めします。 リモートネットワークパスは使用しないでください。 たとえば、path **c 修復**を使用できます。 

   親フォルダーへのパスは、自動的に AzCopy コマンドに追加されます ( **/Dest**パラメーターの値として)。

6. [**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを開き、[AzCopy] コマンドを貼り付けて、 **enter**キーを押します。  

    ![エラー修復の準備](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > [**ファイルのダウンロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。 また、手順10でファイルをアップロードするには、AzCopy v1.1 を使用する必要があります。 このバージョンの AzCopy をインストールするには、「 [Transfer data With AzCopy v2.0 On Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)」を参照してください。 指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。

    選択したファイルは、手順5で指定した場所にダウンロードされます。 親フォルダー ( **C:\windows 修復**など) で、次のサブフォルダー構造が自動的に作成されます。

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *サブフォルダー 1*には、手順1で選択した範囲に応じて、ケースまたはレビューセットの ID で名前が付けられます。

    - *サブフォルダー 2*には、ダウンロードしたファイルのファイル ID が指定されています。

    - ダウンロードされたファイルは*サブフォルダー 2*にあり、ファイル ID とも呼ばれます。

    次に、アイテムが**C:\ 修復**親フォルダーにダウンロードされたときに作成されるフォルダーパスとエラーファイル名の例を示します。

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    複数のファイルがダウンロードされている場合は、ファイル ID を指定したサブフォルダーに各ファイルがダウンロードされます。

    > [!IMPORTANT]
    > 手順9と手順10でファイルをアップロードする場合、修復済みのファイルは同じファイル名を持っている必要があり、同じサブフォルダー構造に配置されている必要があります。 サブフォルダーとファイル名を使用して、修復されたファイルを元のエラーファイルに関連付けます。 フォルダー構造またはファイル名が変更されると、次のエラーが表示`Cannot apply Error Remediation to the current Workingset`されます。 問題を回避するために、修復されたファイルを同じ親フォルダーとサブフォルダー構造に保持することをお勧めします。

7. ファイルをダウンロードした後、適切なツールを使用して修復できます。 パスワードで保護されたファイルでは、いくつかのパスワードクラッキングツールを使用できます。 ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。

8. [高度な電子情報開示とエラー修復ウィザード] に戻り、[**次へ: ファイルのアップロード**] をクリックします。  これで、ファイルをアップロードできる次のページに移動します。

    ![ファイルをアップロードする](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 修復したファイルが配置されている親フォルダーを、[**ファイルの場所へのパス**] テキストボックスで指定します。 この場合も、親フォルダーには、ファイルをダウンロードしたときに作成されたのと同じサブフォルダー構造を設定する必要があります。

    親フォルダーへのパスは、( **/source**パラメーターの値として) azcopy コマンドに自動的に追加されます。

10. [**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを開き、[AzCopy] コマンドを貼り付けて、 **enter**キーを押します。 ファイルをアップロードします。

    ![ff2ff691-629f-4065-9b37-5333f937daf6](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. AzCopy コマンドを実行した後、[**次へ: ファイルの処理**] をクリックします。

    処理が完了すると、「review set」に進み、修復されたファイルを表示することができます。 

## <a name="what-happens-when-files-are-remediated"></a>ファイルが修復されたときの処理

修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- テキスト
- WordCount
- WorkingsetId

Advanced eDiscovery のすべてのメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。