---
title: Installare .NET Core su Fedora 30 - gestore di pacchetti - .NET CoreInstall .NET Core on Fedora 30 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in Fedora 30.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: bce30c9fd3fad8b3a63ef938d7446c2516a756cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920792"
---
# <a name="fedora-30-package-manager---install-net-core"></a><span data-ttu-id="6a6e7-103">Fedora 30 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a6e7-103">Fedora 30 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="6a6e7-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Fedora 30.This article describes how to use a package manager to install .NET Core on Fedora 30.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-104">This article describes how to use a package manager to install .NET Core on Fedora 30.</span></span> <span data-ttu-id="6a6e7-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), in quanto include runtime .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="6a6e7-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="6a6e7-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="6a6e7-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="6a6e7-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="6a6e7-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="6a6e7-109">Registrare l'archivio prodotti.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-109">Register the product repository.</span></span>
- <span data-ttu-id="6a6e7-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-110">Install required dependencies.</span></span>

<span data-ttu-id="6a6e7-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="6a6e7-112">Aprire un terminale ed eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="6a6e7-113">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="6a6e7-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="6a6e7-115">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="6a6e7-116">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="6a6e7-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="6a6e7-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="6a6e7-118">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="6a6e7-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a6e7-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="6a6e7-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="6a6e7-121">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="6a6e7-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="6a6e7-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="6a6e7-123">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="6a6e7-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="6a6e7-124">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a6e7-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="6a6e7-125">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="6a6e7-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
