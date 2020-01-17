---
title: Installare .NET Core in Ubuntu 19,10 Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Ubuntu 19,10.
author: thraka
ms.author: adegeo
ms.date: 01/16/2020
ms.openlocfilehash: afba761e2237ed84528157841e538a9b44d9a966
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164084"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a><span data-ttu-id="789dc-103">Gestione pacchetti Ubuntu 19,10-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="789dc-103">Ubuntu 19.10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="789dc-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Ubuntu 19,10.</span><span class="sxs-lookup"><span data-stu-id="789dc-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.10.</span></span> <span data-ttu-id="789dc-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="789dc-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="789dc-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="789dc-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="789dc-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="789dc-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="789dc-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="789dc-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="789dc-109">Registrare il repository del prodotto.</span><span class="sxs-lookup"><span data-stu-id="789dc-109">Register the product repository.</span></span>
- <span data-ttu-id="789dc-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="789dc-110">Install required dependencies.</span></span>

<span data-ttu-id="789dc-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="789dc-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="789dc-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="789dc-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="789dc-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="789dc-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="789dc-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="789dc-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="789dc-115">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="789dc-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="789dc-116">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-SDK-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="789dc-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="789dc-117">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="789dc-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="789dc-118">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="789dc-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="789dc-119">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="789dc-119">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="789dc-120">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto aspnetcore-runtime-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="789dc-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="789dc-121">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="789dc-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="789dc-122">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="789dc-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="789dc-123">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="789dc-123">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="789dc-124">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto dotnet-runtime-3,1**, vedere la sezione [risolvere i problemi relativi a gestione pacchetti](#troubleshoot-the-package-manager) .</span><span class="sxs-lookup"><span data-stu-id="789dc-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="789dc-125">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="789dc-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="789dc-126">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="789dc-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="789dc-127">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto {il pacchetto .NET Core}** , eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="789dc-127">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="789dc-128">Se questa operazione non funziona, è possibile eseguire un'installazione manuale con i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="789dc-128">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```
