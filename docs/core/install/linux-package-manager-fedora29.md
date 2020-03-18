---
title: Installare .NET Core in Fedora 29 - gestore di pacchetti - .NET CoreInstall .NET Core on Fedora 29 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in Fedora 29.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: d917c867e0d8cdb066b7dee64a9dbd767b56072d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920812"
---
# <a name="fedora-29-package-manager---install-net-core"></a><span data-ttu-id="f3c08-103">Fedora 29 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="f3c08-103">Fedora 29 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f3c08-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Fedora 29.This article describes how to use a package manager to install .NET Core on Fedora 29.</span><span class="sxs-lookup"><span data-stu-id="f3c08-104">This article describes how to use a package manager to install .NET Core on Fedora 29.</span></span> <span data-ttu-id="f3c08-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), in quanto include runtime .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3c08-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="f3c08-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="f3c08-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="f3c08-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f3c08-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f3c08-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3c08-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="f3c08-109">Registrare l'archivio prodotti.</span><span class="sxs-lookup"><span data-stu-id="f3c08-109">Register the product repository.</span></span>
- <span data-ttu-id="f3c08-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="f3c08-110">Install required dependencies.</span></span>

<span data-ttu-id="f3c08-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="f3c08-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f3c08-112">Aprire un terminale ed eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="f3c08-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f3c08-113">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f3c08-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="f3c08-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f3c08-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f3c08-115">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="f3c08-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f3c08-116">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="f3c08-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f3c08-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="f3c08-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f3c08-118">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="f3c08-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f3c08-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f3c08-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="f3c08-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="f3c08-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f3c08-121">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="f3c08-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f3c08-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="f3c08-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f3c08-123">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="f3c08-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="f3c08-124">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3c08-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="f3c08-125">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="f3c08-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
