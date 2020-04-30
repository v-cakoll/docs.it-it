---
title: Installare .NET Core in Debian 10-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Debian 10.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 038f5579f99f700ce47dc67be2fd344f01cf800c
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595620"
---
# <a name="debian-10-package-manager---install-net-core"></a><span data-ttu-id="70061-103">Gestione pacchetti Debian 10-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="70061-103">Debian 10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="70061-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Debian 10.</span><span class="sxs-lookup"><span data-stu-id="70061-104">This article describes how to use a package manager to install .NET Core on Debian 10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="70061-105">Aggiungere la chiave e il feed del repository Microsoft</span><span class="sxs-lookup"><span data-stu-id="70061-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="70061-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="70061-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="70061-107">Aggiungere la chiave di firma del pacchetto Microsoft all'elenco di chiavi attendibili.</span><span class="sxs-lookup"><span data-stu-id="70061-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="70061-108">Aggiungere il repository a gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="70061-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="70061-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="70061-109">Install required dependencies.</span></span>

<span data-ttu-id="70061-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="70061-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="70061-111">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="70061-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="70061-112">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="70061-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="70061-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="70061-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="70061-114">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="70061-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="70061-115">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="70061-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="70061-116">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="70061-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="70061-117">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="70061-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="70061-118">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="70061-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="70061-119">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="70061-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="70061-120">Nel terminale eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="70061-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="70061-121">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="70061-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="70061-122">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="70061-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="70061-123">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="70061-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="70061-124">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="70061-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
