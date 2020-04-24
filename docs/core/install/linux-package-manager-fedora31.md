---
title: Installare .NET Core su Fedora 31 - gestore di pacchetti - .NET CoreInstall .NET Core on Fedora 31 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in Fedora 31.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 56e5789132af2aa1171ea51698ae55d1eea5d457
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645303"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="3cc0f-103">Fedora 31 Gestione pacchetti - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="3cc0f-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="3cc0f-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in Fedora 31.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="3cc0f-105">Aggiungere la chiave e il feed del repository Microsoft</span><span class="sxs-lookup"><span data-stu-id="3cc0f-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="3cc0f-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3cc0f-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="3cc0f-107">Aggiungere la chiave di firma del pacchetto Microsoft all'elenco delle chiavi attendibili.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="3cc0f-108">Aggiungere il repository al gestore di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="3cc0f-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-109">Install required dependencies.</span></span>

<span data-ttu-id="3cc0f-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="3cc0f-111">Aprire un terminale ed eseguire i seguenti comandi.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="3cc0f-112">Installare .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="3cc0f-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="3cc0f-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="3cc0f-114">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="3cc0f-115">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="3cc0f-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="3cc0f-116">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="3cc0f-117">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="3cc0f-118">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="3cc0f-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="3cc0f-119">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="3cc0f-120">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3cc0f-121">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="3cc0f-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="3cc0f-122">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="3cc0f-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="3cc0f-123">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3cc0f-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="3cc0f-124">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="3cc0f-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
