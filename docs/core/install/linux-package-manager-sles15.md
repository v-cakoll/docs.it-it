---
title: Installare .NET Core in SLES 15 - gestione pacchetti - .NET CoreInstall .NET Core on SLES 15 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in SLES 15.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: f48c131b4250bd04fffc0d815a3500732caacb7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76921039"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="b7701-103">Gestione pacchetti SLES 15 - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="b7701-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="b7701-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in SLES 15.</span><span class="sxs-lookup"><span data-stu-id="b7701-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span> <span data-ttu-id="b7701-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), in quanto include runtime .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7701-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="b7701-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="b7701-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="b7701-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="b7701-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="b7701-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7701-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="b7701-109">Registrare l'archivio prodotti.</span><span class="sxs-lookup"><span data-stu-id="b7701-109">Register the product repository.</span></span>
- <span data-ttu-id="b7701-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="b7701-110">Install required dependencies.</span></span>

<span data-ttu-id="b7701-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="b7701-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="b7701-112">Aprire un terminale ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="b7701-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="b7701-113">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b7701-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="b7701-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b7701-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="b7701-115">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="b7701-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="b7701-116">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="b7701-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="b7701-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="b7701-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="b7701-118">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="b7701-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="b7701-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="b7701-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="b7701-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="b7701-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="b7701-121">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="b7701-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b7701-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="b7701-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b7701-123">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="b7701-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="b7701-124">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7701-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="b7701-125">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="b7701-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
