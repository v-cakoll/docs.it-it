---
title: Installare .NET Core in CentOS 7-Gestione pacchetti-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in CentOS 7.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 66e78aadf933d3e10b99e3d2c7258733e96164f6
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920859"
---
# <a name="centos-7-package-manager---install-net-core"></a><span data-ttu-id="164eb-103">Gestione pacchetti CentOS 7-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="164eb-103">CentOS 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="164eb-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in CentOS 7.</span><span class="sxs-lookup"><span data-stu-id="164eb-104">This article describes how to use a package manager to install .NET Core on CentOS 7.</span></span> <span data-ttu-id="164eb-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="164eb-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="164eb-106">Registrare la chiave e il feed Microsoft</span><span class="sxs-lookup"><span data-stu-id="164eb-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="164eb-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="164eb-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="164eb-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="164eb-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="164eb-109">Registrare il repository del prodotto.</span><span class="sxs-lookup"><span data-stu-id="164eb-109">Register the product repository.</span></span>
- <span data-ttu-id="164eb-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="164eb-110">Install required dependencies.</span></span>

<span data-ttu-id="164eb-111">Questa operazione deve essere eseguita solo una volta per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="164eb-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="164eb-112">Aprire un terminale ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="164eb-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="164eb-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="164eb-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="164eb-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="164eb-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="164eb-115">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="164eb-115">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="164eb-116">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="164eb-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="164eb-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="164eb-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="164eb-118">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="164eb-118">In your terminal, run the following command.</span></span>

```bash
sudo yum install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="164eb-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="164eb-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="164eb-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="164eb-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="164eb-121">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="164eb-121">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="164eb-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="164eb-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="164eb-123">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="164eb-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="164eb-124">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="164eb-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="164eb-125">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="164eb-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
