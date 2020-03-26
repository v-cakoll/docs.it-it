---
title: Installare .NET Core in Debian 9 - gestione pacchetti - .NET CoreInstall .NET Core on Debian 9 - package manager - .NET Core
description: Usare un gestore di pacchetti per installare .NET Core SDK e runtime in Debian 9.Use a package manager to install .NET Core SDK and runtime on Debian 9.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: cfe28d04edfac97938612537986498636c141be0
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134300"
---
# <a name="debian-9-package-manager---install-net-core"></a><span data-ttu-id="9bc9c-103">Debian 9 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="9bc9c-103">Debian 9 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="9bc9c-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Debian 9.This article describes how to use a package manager to install .NET Core on Debian 9.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-104">This article describes how to use a package manager to install .NET Core on Debian 9.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="9bc9c-105">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="9bc9c-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="9bc9c-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="9bc9c-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="9bc9c-107">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="9bc9c-108">Registrare l'archivio prodotti.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-108">Register the product repository.</span></span>
- <span data-ttu-id="9bc9c-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-109">Install required dependencies.</span></span>

<span data-ttu-id="9bc9c-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="9bc9c-111">Aprire un terminale ed eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9bc9c-112">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="9bc9c-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="9bc9c-114">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9bc9c-115">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="9bc9c-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="9bc9c-116">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="9bc9c-117">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9bc9c-118">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="9bc9c-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="9bc9c-119">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="9bc9c-120">Nel terminale, eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9bc9c-121">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="9bc9c-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="9bc9c-122">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="9bc9c-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="9bc9c-123">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9bc9c-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="9bc9c-124">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="9bc9c-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
