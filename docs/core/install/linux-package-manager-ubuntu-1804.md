---
title: Installare .NET Core in Ubuntu 18.04 Package Manager - .NET CoreInstall .NET Core on Ubuntu 18.04 package manager - .NET Core
description: Usare un gestore di pacchetti per installare .NET Core SDK e runtime in Ubuntu 18.04.Use a package manager to install .NET Core SDK and runtime on Ubuntu 18.04.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: ea01c324335c5e0eb120b72fd6384df640f0997e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645620"
---
# <a name="ubuntu-1804-package-manager---install-net-core"></a><span data-ttu-id="848e0-103">Ubuntu 18.04 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="848e0-103">Ubuntu 18.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="848e0-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Ubuntu 18.04.This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span><span class="sxs-lookup"><span data-stu-id="848e0-104">This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="848e0-105">Aggiungere la chiave e il feed del repository Microsoft</span><span class="sxs-lookup"><span data-stu-id="848e0-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="848e0-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="848e0-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="848e0-107">Aggiungere la chiave di firma del pacchetto Microsoft all'elenco delle chiavi attendibili.</span><span class="sxs-lookup"><span data-stu-id="848e0-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="848e0-108">Aggiungere il repository al gestore di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="848e0-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="848e0-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="848e0-109">Install required dependencies.</span></span>

<span data-ttu-id="848e0-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="848e0-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="848e0-111">Aprire un terminale ed eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="848e0-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="848e0-112">Installare .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="848e0-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="848e0-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="848e0-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="848e0-114">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="848e0-114">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="848e0-115">Se viene visualizzato un messaggio di errore simile a Impossibile individuare il **pacchetto dotnet-sdk-3.1,** vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="848e0-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="848e0-116">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="848e0-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="848e0-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="848e0-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="848e0-118">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="848e0-118">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="848e0-119">Se viene visualizzato un messaggio di errore simile a Impossibile individuare il **pacchetto aspnetcore-runtime-3.1,** vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="848e0-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="848e0-120">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="848e0-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="848e0-121">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="848e0-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="848e0-122">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="848e0-122">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="848e0-123">Se viene visualizzato un messaggio di errore simile **a Impossibile individuare il pacchetto dotnet-runtime-3.1**, vedere la sezione [Risoluzione dei problemi relativi al gestore](#troubleshoot-the-package-manager) di pacchetti .</span><span class="sxs-lookup"><span data-stu-id="848e0-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="848e0-124">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="848e0-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="848e0-125">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="848e0-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="848e0-126">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="848e0-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="848e0-127">Impossibile individuare</span><span class="sxs-lookup"><span data-stu-id="848e0-127">Unable to locate</span></span>

<span data-ttu-id="848e0-128">Se viene visualizzato un messaggio di errore simile **a Impossibile individuare il pacchetto .**</span><span class="sxs-lookup"><span data-stu-id="848e0-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="848e0-129">Se il sistema non funziona, è possibile eseguire un'installazione manuale con i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="848e0-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/18.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="848e0-130">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="848e0-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
