---
title: Installare .NET Core in Ubuntu 19.04 Package Manager - .NET CoreInstall .NET Core on Ubuntu 19.04 package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime su Ubuntu 19.04.Use a package manager to install .NET Core SDK and runtime on Ubuntu 19.04.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: c7b30d2760a0a83a0fdd7ff5fa35b2f3d490494f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920673"
---
# <a name="ubuntu-1904-package-manager---install-net-core"></a><span data-ttu-id="2b473-103">Ubuntu 19.04 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="2b473-103">Ubuntu 19.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="2b473-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Ubuntu 19.04.This article describes how to use a package manager to install .NET Core on Ubuntu 19.04.</span><span class="sxs-lookup"><span data-stu-id="2b473-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.04.</span></span> <span data-ttu-id="2b473-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), in quanto include runtime .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b473-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="2b473-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="2b473-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="2b473-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="2b473-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="2b473-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b473-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="2b473-109">Registrare l'archivio prodotti.</span><span class="sxs-lookup"><span data-stu-id="2b473-109">Register the product repository.</span></span>
- <span data-ttu-id="2b473-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="2b473-110">Install required dependencies.</span></span>

<span data-ttu-id="2b473-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="2b473-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="2b473-112">Aprire un terminale ed eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="2b473-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="2b473-113">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="2b473-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="2b473-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="2b473-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="2b473-115">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="2b473-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="2b473-116">Se viene visualizzato un messaggio di errore simile a Impossibile individuare il **pacchetto dotnet-sdk-3.1,** vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="2b473-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="2b473-117">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="2b473-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="2b473-118">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b473-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="2b473-119">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="2b473-119">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="2b473-120">Se viene visualizzato un messaggio di errore simile a Impossibile individuare il **pacchetto aspnetcore-runtime-3.1,** vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="2b473-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="2b473-121">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="2b473-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="2b473-122">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="2b473-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="2b473-123">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="2b473-123">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="2b473-124">Se viene visualizzato un messaggio di errore simile **a Impossibile individuare il pacchetto dotnet-runtime-3.1**, vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti .</span><span class="sxs-lookup"><span data-stu-id="2b473-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2b473-125">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="2b473-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="2b473-126">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="2b473-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="2b473-127">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b473-127">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="2b473-128">Impossibile individuare</span><span class="sxs-lookup"><span data-stu-id="2b473-128">Unable to locate</span></span>

<span data-ttu-id="2b473-129">Se viene visualizzato un messaggio di errore simile **a Impossibile individuare il pacchetto .**</span><span class="sxs-lookup"><span data-stu-id="2b473-129">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="2b473-130">Se il sistema non funziona, è possibile eseguire un'installazione manuale con i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="2b473-130">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/19.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="2b473-131">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="2b473-131">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
