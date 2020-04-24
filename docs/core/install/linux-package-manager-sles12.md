---
title: Installare .NET Core in SLES 12 - gestione pacchetti - .NET CoreInstall .NET Core on SLES 12 - package manager - .NET Core
description: Utilizzare un gestore di pacchetti per installare .NET Core SDK e runtime in SLES 12.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 314688d60fb77e1b569dd037fb1d78c3f1f94dbc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645653"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="f14f7-103">Gestione pacchetti SLES 12 - Installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="f14f7-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f14f7-104">In questo articolo viene descritto come utilizzare un gestore di pacchetti per installare .NET Core in SLES 12.</span><span class="sxs-lookup"><span data-stu-id="f14f7-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="f14f7-105">Aggiungere la chiave e il feed del repository Microsoft</span><span class="sxs-lookup"><span data-stu-id="f14f7-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="f14f7-106">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f14f7-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f14f7-107">Aggiungere la chiave di firma del pacchetto Microsoft all'elenco delle chiavi attendibili.</span><span class="sxs-lookup"><span data-stu-id="f14f7-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="f14f7-108">Aggiungere il repository al gestore di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f14f7-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="f14f7-109">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="f14f7-109">Install required dependencies.</span></span>

<span data-ttu-id="f14f7-110">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="f14f7-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f14f7-111">Aprire un terminale ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f14f7-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f14f7-112">Installare .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f14f7-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="f14f7-113">Aggiornare i prodotti disponibili per l'installazione, quindi installare .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f14f7-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f14f7-114">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="f14f7-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f14f7-115">Installare il runtime di ASP.NET CoreInstall the ASP.NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="f14f7-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f14f7-116">Aggiornare i prodotti disponibili per l'installazione, quindi installare il ASP.NET runtime.</span><span class="sxs-lookup"><span data-stu-id="f14f7-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f14f7-117">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="f14f7-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f14f7-118">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f14f7-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="f14f7-119">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.Update the products available for installation, then install the .NET Core runtime.</span><span class="sxs-lookup"><span data-stu-id="f14f7-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f14f7-120">Nel terminale, eseguire il seguente comando.</span><span class="sxs-lookup"><span data-stu-id="f14f7-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f14f7-121">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="f14f7-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f14f7-122">Risolvere i problemi relativi al gestore di pacchettiTroubleshoot the package manager</span><span class="sxs-lookup"><span data-stu-id="f14f7-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="f14f7-123">In questa sezione vengono fornite informazioni sugli errori comuni che possono verificarsi durante l'utilizzo di Gestione pacchetti per installare .NET Core.This section provides information on common errors you may get while using the package manager to install .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f14f7-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="f14f7-124">Impossibile recuperare</span><span class="sxs-lookup"><span data-stu-id="f14f7-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
