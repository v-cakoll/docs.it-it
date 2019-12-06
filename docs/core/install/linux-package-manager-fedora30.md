---
title: Installare .NET Core in Fedora 30-Gestione pacchetti-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Fedora 30.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 7996cd74a250370c2212ca1977cb8c44ad0bd078
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74836976"
---
# <a name="fedora-30-package-manager---install-net-core"></a><span data-ttu-id="f6823-103">Gestione pacchetti Fedora 30-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="f6823-103">Fedora 30 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f6823-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Fedora 30.</span><span class="sxs-lookup"><span data-stu-id="f6823-104">This article describes how to use a package manager to install .NET Core on Fedora 30.</span></span> <span data-ttu-id="f6823-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6823-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="f6823-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="f6823-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="f6823-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f6823-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f6823-108">Registrare la chiave Microsoft</span><span class="sxs-lookup"><span data-stu-id="f6823-108">Register the Microsoft key</span></span>
- <span data-ttu-id="f6823-109">registrare il repository del prodotto</span><span class="sxs-lookup"><span data-stu-id="f6823-109">register the product repository</span></span>
- <span data-ttu-id="f6823-110">Installare le dipendenze necessarie</span><span class="sxs-lookup"><span data-stu-id="f6823-110">Install required dependencies</span></span>

<span data-ttu-id="f6823-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="f6823-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f6823-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f6823-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f6823-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f6823-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="f6823-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f6823-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f6823-115">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f6823-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f6823-116">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f6823-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f6823-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f6823-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f6823-118">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f6823-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f6823-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f6823-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="f6823-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6823-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f6823-121">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f6823-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f6823-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="f6823-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
