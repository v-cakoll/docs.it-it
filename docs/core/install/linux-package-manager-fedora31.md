---
title: Installare .NET Core in Fedora 31-gestione pacchetti-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Fedora 31.
author: thraka
ms.author: adegeo
ms.date: 12/17/2019
ms.openlocfilehash: 25c670694ed2d9e89fe37cedf0b06efd8bc93293
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116966"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="f137b-103">Gestione pacchetti Fedora 31-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="f137b-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f137b-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Fedora 31.</span><span class="sxs-lookup"><span data-stu-id="f137b-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span> <span data-ttu-id="f137b-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="f137b-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="f137b-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="f137b-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="f137b-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f137b-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f137b-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f137b-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="f137b-109">Registrare il repository del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f137b-109">Register the product repository.</span></span>
- <span data-ttu-id="f137b-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="f137b-110">Install required dependencies.</span></span>

<span data-ttu-id="f137b-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="f137b-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f137b-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f137b-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f137b-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f137b-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="f137b-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f137b-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f137b-115">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f137b-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f137b-116">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f137b-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f137b-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f137b-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f137b-118">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f137b-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f137b-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f137b-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="f137b-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f137b-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f137b-121">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f137b-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f137b-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="f137b-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
