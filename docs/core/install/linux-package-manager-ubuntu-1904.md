---
title: Installare .NET Core in Ubuntu 19,04 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Ubuntu 19,04.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 69bfc3395f5cd92ed54850e5ea8b76eba7f27d83
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959746"
---
# <a name="ubuntu-1904-package-manager---install-net-core"></a><span data-ttu-id="dbaf7-103">Gestione pacchetti Ubuntu 19,04-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="dbaf7-103">Ubuntu 19.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="dbaf7-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Ubuntu 19,04.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.04.</span></span> <span data-ttu-id="dbaf7-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="dbaf7-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="dbaf7-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="dbaf7-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="dbaf7-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="dbaf7-108">Registrare la chiave Microsoft</span><span class="sxs-lookup"><span data-stu-id="dbaf7-108">Register the Microsoft key</span></span>
- <span data-ttu-id="dbaf7-109">registrare il repository del prodotto</span><span class="sxs-lookup"><span data-stu-id="dbaf7-109">register the product repository</span></span>
- <span data-ttu-id="dbaf7-110">Installare le dipendenze necessarie</span><span class="sxs-lookup"><span data-stu-id="dbaf7-110">Install required dependencies</span></span>

<span data-ttu-id="dbaf7-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="dbaf7-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="dbaf7-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="dbaf7-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="dbaf7-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="dbaf7-115">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="dbaf7-116">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-SDK-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="dbaf7-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="dbaf7-117">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dbaf7-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="dbaf7-118">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="dbaf7-119">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-119">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="dbaf7-120">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto aspnetcore-runtime-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="dbaf7-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="dbaf7-121">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="dbaf7-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="dbaf7-122">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="dbaf7-123">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-123">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="dbaf7-124">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-runtime-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="dbaf7-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="dbaf7-125">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="dbaf7-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="dbaf7-126">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="dbaf7-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="dbaf7-127">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto {il pacchetto .NET Core}** , eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-127">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="dbaf7-128">Se questa operazione non funziona, è possibile eseguire un'installazione manuale con i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbaf7-128">If that doesn't work, you can run a manual install with the following commands.</span></span>

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
