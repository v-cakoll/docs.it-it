---
title: Installare .NET Core in Ubuntu 20,04 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Ubuntu 20,04.
author: thraka
ms.author: adegeo
ms.date: 05/13/2020
ms.openlocfilehash: 4d7d7ee9117314ef360097fee929f24943c7a7f2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83619288"
---
# <a name="ubuntu-2004-package-manager---install-net-core"></a><span data-ttu-id="2e11e-103">Gestione pacchetti Ubuntu 20,04-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e11e-103">Ubuntu 20.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="2e11e-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Ubuntu 20,04.</span><span class="sxs-lookup"><span data-stu-id="2e11e-104">This article describes how to use a package manager to install .NET Core on Ubuntu 20.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="2e11e-105">Aggiungere la chiave e il feed del repository Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e11e-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="2e11e-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="2e11e-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="2e11e-107">Aggiungere la chiave di firma del pacchetto Microsoft all'elenco di chiavi attendibili.</span><span class="sxs-lookup"><span data-stu-id="2e11e-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="2e11e-108">Aggiungere il repository a gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="2e11e-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="2e11e-109">Install required dependencies.</span></span>

<span data-ttu-id="2e11e-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="2e11e-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="2e11e-111">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="2e11e-112">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2e11e-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="2e11e-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="2e11e-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="2e11e-114">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="2e11e-115">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-SDK-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="2e11e-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="2e11e-116">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2e11e-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="2e11e-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="2e11e-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="2e11e-118">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="2e11e-119">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto aspnetcore-runtime-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="2e11e-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="2e11e-120">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e11e-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="2e11e-121">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e11e-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="2e11e-122">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-122">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="2e11e-123">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-runtime-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="2e11e-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2e11e-124">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="2e11e-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="2e11e-125">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="2e11e-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="2e11e-126">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e11e-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="2e11e-127">Impossibile individuare</span><span class="sxs-lookup"><span data-stu-id="2e11e-127">Unable to locate</span></span>

<span data-ttu-id="2e11e-128">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto {il pacchetto .NET Core}**, eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="2e11e-129">Se questa operazione non funziona, è possibile eseguire un'installazione manuale con i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e11e-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/20.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="2e11e-130">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="2e11e-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
