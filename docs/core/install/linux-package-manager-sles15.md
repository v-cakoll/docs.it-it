---
title: Installare .NET Core in SLES 15-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in SLES 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595616"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="4682c-103">Gestione pacchetti SLES 15-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="4682c-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="4682c-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in SLES 15.</span><span class="sxs-lookup"><span data-stu-id="4682c-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="4682c-105">Aggiungere la chiave e il feed del repository Microsoft</span><span class="sxs-lookup"><span data-stu-id="4682c-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="4682c-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="4682c-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="4682c-107">Aggiungere la chiave di firma del pacchetto Microsoft all'elenco di chiavi attendibili.</span><span class="sxs-lookup"><span data-stu-id="4682c-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="4682c-108">Aggiungere il repository a gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="4682c-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="4682c-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="4682c-109">Install required dependencies.</span></span>

<span data-ttu-id="4682c-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="4682c-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="4682c-111">Aprire un terminale ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4682c-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="4682c-112">Attualmente, il pacchetto di installazione del repository Microsoft SLES 15 installa il file *Microsoft-prod. repo* nella directory errata, impedendo a zypper di trovare i pacchetti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4682c-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="4682c-113">Per risolvere il problema, creare un collegamento simbolico nella directory corretta.</span><span class="sxs-lookup"><span data-stu-id="4682c-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="4682c-114">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="4682c-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="4682c-115">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="4682c-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="4682c-116">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4682c-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="4682c-117">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4682c-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="4682c-118">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4682c-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="4682c-119">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4682c-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="4682c-120">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="4682c-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="4682c-121">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4682c-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="4682c-122">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="4682c-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="4682c-123">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="4682c-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="4682c-124">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="4682c-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="4682c-125">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4682c-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="4682c-126">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="4682c-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
