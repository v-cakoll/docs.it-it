---
title: Installare .NET Core in openSUSE 15-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740666"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="01cf9-103">Gestione pacchetti openSUSE 15-installare .NET Core</span><span class="sxs-lookup"><span data-stu-id="01cf9-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="01cf9-104">Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="01cf9-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="01cf9-105">Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="01cf9-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="01cf9-106">Registrare la chiave Microsoft e il feed</span><span class="sxs-lookup"><span data-stu-id="01cf9-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="01cf9-107">Prima di installare .NET, è necessario:</span><span class="sxs-lookup"><span data-stu-id="01cf9-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="01cf9-108">Registrare la chiave Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01cf9-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="01cf9-109">Registrare il repository del prodotto.</span><span class="sxs-lookup"><span data-stu-id="01cf9-109">Register the product repository.</span></span>
- <span data-ttu-id="01cf9-110">Installare le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="01cf9-110">Install required dependencies.</span></span>

<span data-ttu-id="01cf9-111">Questa operazione deve essere eseguita una volta sola per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="01cf9-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="01cf9-112">Aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="01cf9-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a><span data-ttu-id="01cf9-113">Errore di dipendenza con .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="01cf9-113">Dependency error with .NET Core 3.1</span></span>

<span data-ttu-id="01cf9-114">Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** .</span><span class="sxs-lookup"><span data-stu-id="01cf9-114">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="01cf9-115">Usare il comando seguente per installare le dipendenze corrette prima di installare .NET Core 3,1 o ASP.NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="01cf9-115">Use the following command to install the correct dependencies prior to installing .NET Core 3.1 or ASP.NET Core 3.1.</span></span>

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="01cf9-116">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="01cf9-116">Install the .NET Core SDK</span></span>

<span data-ttu-id="01cf9-117">Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="01cf9-117">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="01cf9-118">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="01cf9-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="01cf9-119">Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** .</span><span class="sxs-lookup"><span data-stu-id="01cf9-119">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="01cf9-120">Usare il comando seguente per installare le dipendenze corrette, quindi installare .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="01cf9-120">Use the following command to install the correct dependencies, then install the .NET Core 3.1 SDK.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="01cf9-121">Installare il runtime di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="01cf9-121">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="01cf9-122">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="01cf9-122">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="01cf9-123">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="01cf9-123">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="01cf9-124">Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** .</span><span class="sxs-lookup"><span data-stu-id="01cf9-124">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="01cf9-125">Usare il comando seguente per installare le dipendenze corrette, quindi installare il runtime di ASP.NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="01cf9-125">Use the following command to install the correct dependencies, then install the ASP.NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="01cf9-126">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="01cf9-126">Install the .NET Core runtime</span></span>

<span data-ttu-id="01cf9-127">Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="01cf9-127">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="01cf9-128">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="01cf9-128">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="01cf9-129">Il feed di pacchetti di .NET Core 3,1 per openSUSE presenta un problema con la dipendenza **krb5** .</span><span class="sxs-lookup"><span data-stu-id="01cf9-129">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="01cf9-130">Usare il comando seguente per installare le dipendenze corrette, quindi installare il runtime di .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="01cf9-130">Use the following command to install the correct dependencies, then install the .NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="01cf9-131">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="01cf9-131">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
