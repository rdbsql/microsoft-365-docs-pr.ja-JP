---
title: AllowSelfServicePurchase を使用してセルフサービス購入を有効または無効にする
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell コマンドレットを使用して、セルフサービスの購入をオンまたはオフにする方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9093e018ed24a9e9735f5b6b71084246967cb59d
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676271"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="3aa59-103">MSCommerce PowerShell モジュールで AllowSelfServicePurchase を使用する</span><span class="sxs-lookup"><span data-stu-id="3aa59-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="3aa59-104">[Powershell ギャラリー](https://aka.ms/allowselfservicepurchase-powershell-gallery)で**MSCommerce** powershell モジュールを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3aa59-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="3aa59-105">このモジュールには、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御できる、 **Allowselfservicepurchase**の**policyid**パラメーターの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3aa59-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="3aa59-106">**MSCommerce** PowerShell モジュールを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3aa59-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="3aa59-107">**Allowselfservicepurchase**パラメーター値の既定の状態を表示する (有効または無効)</span><span class="sxs-lookup"><span data-stu-id="3aa59-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="3aa59-108">適用可能な製品の一覧、およびセルフサービス購入が有効か無効かを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa59-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="3aa59-109">特定の製品の現在の設定を表示または変更して、有効にするか無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="3aa59-110">要件</span><span class="sxs-lookup"><span data-stu-id="3aa59-110">Requirements</span></span>

<span data-ttu-id="3aa59-111">**MSCommerce** PowerShell モジュールを使用するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="3aa59-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="3aa59-112">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="3aa59-112">A Windows 10 device</span></span>
- <span data-ttu-id="3aa59-113">デバイスに対する管理者のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3aa59-113">Administrator permission for the device</span></span>
- <span data-ttu-id="3aa59-114">テナントのグローバルまたは課金管理者の役割</span><span class="sxs-lookup"><span data-stu-id="3aa59-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="3aa59-115">MSCommerce PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="3aa59-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="3aa59-116">**MSCommerce** powershell モジュールを Windows 10 デバイスに1回インストールしてから、開始する各 powershell セッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="3aa59-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="3aa59-117">[Powershell ギャラリー](https://aka.ms/allowselfservicepurchase-powershell-gallery)から**MSCommerce** powershell モジュールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3aa59-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="3aa59-118">**PowerShellGet**を使用して**MSCommerce** PowerShell モジュールをインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="3aa59-119">PowerShell セッションに MSCommerce をインポートする</span><span class="sxs-lookup"><span data-stu-id="3aa59-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="3aa59-120">Windows 10 デバイスにモジュールをインストールしたら、開始する各 PowerShell セッションにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3aa59-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="3aa59-121">PowerShell セッションにインポートするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="3aa59-122">資格情報を使用して MSCommerce に接続する</span><span class="sxs-lookup"><span data-stu-id="3aa59-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="3aa59-123">資格情報を使用して PowerShell モジュールに接続するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="3aa59-124">このコマンドは、現在の PowerShell セッションを Azure Active Directory テナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="3aa59-125">このコマンドを実行すると、接続先のテナントのユーザー名とパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="3aa59-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="3aa59-126">資格情報に対して多要素認証が有効になっている場合は、interactive オプションを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="3aa59-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="3aa59-127">AllowSelfServicePurchase の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="3aa59-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="3aa59-128">組織に基づいて**Allowselfservicepurchase**パラメーター値と既定の状態の説明を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="3aa59-129">セルフサービス購入製品とその状態の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="3aa59-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="3aa59-130">利用可能なすべてのセルフサービス購入製品と各の状態の一覧を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="3aa59-131">次の表に、使用可能な製品とその**ProductId**を示します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="3aa59-132">製品</span><span class="sxs-lookup"><span data-stu-id="3aa59-132">Product</span></span> | <span data-ttu-id="3aa59-133">△</span><span class="sxs-lookup"><span data-stu-id="3aa59-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="3aa59-134">ユーザーあたりの電源アプリ</span><span class="sxs-lookup"><span data-stu-id="3aa59-134">Power Apps per user</span></span> | <span data-ttu-id="3aa59-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="3aa59-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="3aa59-136">ユーザーごとの電源自動化</span><span class="sxs-lookup"><span data-stu-id="3aa59-136">Power Automate per user</span></span> | <span data-ttu-id="3aa59-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="3aa59-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="3aa59-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="3aa59-138">Power BI Pro</span></span> | <span data-ttu-id="3aa59-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="3aa59-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="3aa59-140">AllowSelfServicePurchase の状態を表示または設定する</span><span class="sxs-lookup"><span data-stu-id="3aa59-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="3aa59-141">セルフサービス購入可能な製品の一覧を表示した後、特定の製品の設定を表示または変更できます。</span><span class="sxs-lookup"><span data-stu-id="3aa59-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="3aa59-142">特定の製品のポリシー設定を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="3aa59-143">特定の製品のポリシー設定を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="3aa59-144">特定の製品のポリシー設定を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="3aa59-145">AllowSelfServicePurchase を無効にするスクリプトの例</span><span class="sxs-lookup"><span data-stu-id="3aa59-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="3aa59-146">次の例では、 **MSCommerce**モジュールをインポートする方法、自分のアカウントでサインインする方法、および製品の電源自動化のために**ProductId**を取得する方法、およびその製品の**allowselfservicepurchase**を無効にする方法について順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="3aa59-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->