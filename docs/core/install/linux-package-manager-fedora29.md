---
title: Installare .NET Core in Fedora 29-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Fedora 29.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 1cd761e323467ef34fdad58de7385c1ca7b2c14a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74836962"
---
# <a name="fedora-29-package-manager---install-net-core"></a><span data-ttu-id="dd320-103">Gestione pacchetti Fedora 29-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="dd320-103">Fedora 29 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="dd320-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Fedora 29.</span><span class="sxs-lookup"><span data-stu-id="dd320-104">This article describes how to use a package manager to install .NET Core on Fedora 29.</span></span> <span data-ttu-id="dd320-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="dd320-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="dd320-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="dd320-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="dd320-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="dd320-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="dd320-108">Registrare la chiave Microsoft</span><span class="sxs-lookup"><span data-stu-id="dd320-108">Register the Microsoft key</span></span>
- <span data-ttu-id="dd320-109">registrare il repository del prodotto</span><span class="sxs-lookup"><span data-stu-id="dd320-109">register the product repository</span></span>
- <span data-ttu-id="dd320-110">Installare le dipendenze necessarie</span><span class="sxs-lookup"><span data-stu-id="dd320-110">Install required dependencies</span></span>

<span data-ttu-id="dd320-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="dd320-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="dd320-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd320-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="dd320-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="dd320-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="dd320-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="dd320-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="dd320-115">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="dd320-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="dd320-116">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dd320-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="dd320-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dd320-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="dd320-118">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="dd320-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="dd320-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="dd320-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="dd320-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dd320-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="dd320-121">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="dd320-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="dd320-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="dd320-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
