---
title: Installare .NET Core in SLES 15 - gestione pacchetti - .NET CoreInstall .NET Core on SLES 15 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in SLES 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b86b97bf17165f2f7a70e80ff581750ba39be375
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134185"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="d7204-103">Gestione pacchetti SLES 15 - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7204-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="d7204-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in SLES 15.</span><span class="sxs-lookup"><span data-stu-id="d7204-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="d7204-105">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="d7204-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="d7204-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="d7204-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="d7204-107">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7204-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="d7204-108">Registrare l'archivio prodotti.</span><span class="sxs-lookup"><span data-stu-id="d7204-108">Register the product repository.</span></span>
- <span data-ttu-id="d7204-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="d7204-109">Install required dependencies.</span></span>

<span data-ttu-id="d7204-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="d7204-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="d7204-111">Aprire un terminale ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d7204-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="d7204-112">Installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="d7204-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="d7204-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="d7204-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="d7204-114">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="d7204-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="d7204-115">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="d7204-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="d7204-116">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="d7204-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="d7204-117">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="d7204-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="d7204-118">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7204-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="d7204-119">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="d7204-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="d7204-120">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="d7204-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d7204-121">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="d7204-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d7204-122">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="d7204-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="d7204-123">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7204-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="d7204-124">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="d7204-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
