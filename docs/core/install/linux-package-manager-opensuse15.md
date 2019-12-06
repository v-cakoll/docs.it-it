---
title: Installare .NET Core in openSUSE 15-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 0ea232438aa4c61e2064d0323dc706dffac15039
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74836969"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="d6903-103">Gestione pacchetti openSUSE 15-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="d6903-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="d6903-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="d6903-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="d6903-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="d6903-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="d6903-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="d6903-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="d6903-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="d6903-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="d6903-108">Registrare la chiave Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6903-108">Register the Microsoft key</span></span>
- <span data-ttu-id="d6903-109">registrare il repository del prodotto</span><span class="sxs-lookup"><span data-stu-id="d6903-109">register the product repository</span></span>
- <span data-ttu-id="d6903-110">Installare le dipendenze necessarie</span><span class="sxs-lookup"><span data-stu-id="d6903-110">Install required dependencies</span></span>

<span data-ttu-id="d6903-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="d6903-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="d6903-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d6903-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="d6903-113">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="d6903-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="d6903-114">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="d6903-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="d6903-115">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d6903-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="d6903-116">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d6903-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="d6903-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d6903-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="d6903-118">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d6903-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="d6903-119">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d6903-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="d6903-120">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d6903-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="d6903-121">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d6903-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d6903-122">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="d6903-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
