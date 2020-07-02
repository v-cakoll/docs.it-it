---
title: Installare .NET Core in CentOS-.NET Core
description: Illustra le varie modalità di installazione di .NET Core SDK e runtime di .NET Core su CentOS.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 6b1bad3a6c967483bb683866de84c9e5077a336f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619507"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-centos"></a><span data-ttu-id="d256d-103">Installare .NET Core SDK o runtime di .NET Core su CentOS</span><span class="sxs-lookup"><span data-stu-id="d256d-103">Install .NET Core SDK or .NET Core Runtime on CentOS</span></span>

<span data-ttu-id="d256d-104">.NET Core è supportato in CentOS.</span><span class="sxs-lookup"><span data-stu-id="d256d-104">.NET Core is supported on CentOS.</span></span> <span data-ttu-id="d256d-105">Questo articolo descrive come installare .NET Core in CentOS.</span><span class="sxs-lookup"><span data-stu-id="d256d-105">This article describes how to install .NET Core on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="d256d-106">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="d256d-106">Supported distributions</span></span>

<span data-ttu-id="d256d-107">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in CentOS 7 e CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="d256d-107">The following table is a list of currently supported .NET Core releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="d256d-108">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di CentOS non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="d256d-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="d256d-109">Un ✔️ indica che la versione di CentOS o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="d256d-109">A ✔️ indicates that the version of CentOS or .NET Core is still supported.</span></span>
- <span data-ttu-id="d256d-110">❌Indica che la versione di CentOS o .NET Core non è supportata nella versione CentOS.</span><span class="sxs-lookup"><span data-stu-id="d256d-110">A ❌ indicates that the version of CentOS or .NET Core isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="d256d-111">Quando una versione di CentOS e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="d256d-111">When both a version of CentOS and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="d256d-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="d256d-112">CentOS</span></span>                   | <span data-ttu-id="d256d-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d256d-113">.NET Core 2.1</span></span> | <span data-ttu-id="d256d-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d256d-114">.NET Core 3.1</span></span> | <span data-ttu-id="d256d-115">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="d256d-115">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="d256d-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="d256d-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="d256d-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="d256d-117">✔️ 2.1</span></span>        | <span data-ttu-id="d256d-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="d256d-118">✔️ 3.1</span></span>        | <span data-ttu-id="d256d-119">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="d256d-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="d256d-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="d256d-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="d256d-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="d256d-121">✔️ 2.1</span></span>        | <span data-ttu-id="d256d-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="d256d-122">✔️ 3.1</span></span>        | <span data-ttu-id="d256d-123">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="d256d-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="d256d-124">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="d256d-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="d256d-125">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="d256d-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="d256d-126">3.0</span><span class="sxs-lookup"><span data-stu-id="d256d-126">3.0</span></span>
- <span data-ttu-id="d256d-127">2.2</span><span class="sxs-lookup"><span data-stu-id="d256d-127">2.2</span></span>
- <span data-ttu-id="d256d-128">2.0</span><span class="sxs-lookup"><span data-stu-id="d256d-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d256d-129">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="d256d-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="d256d-130">✔️ CentOS 8</span><span class="sxs-lookup"><span data-stu-id="d256d-130">CentOS 8 ✔️</span></span>

<span data-ttu-id="d256d-131">.NET Core 3,1 è disponibile nei repository dei pacchetti predefiniti per CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="d256d-131">.NET Core 3.1 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="d256d-132">✔️ CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d256d-132">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-31](includes/linux-install-31-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d256d-133">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="d256d-133">Troubleshoot the package manager</span></span>

<span data-ttu-id="d256d-134">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d256d-134">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="d256d-135">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="d256d-135">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="d256d-136">Snap</span><span class="sxs-lookup"><span data-stu-id="d256d-136">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="d256d-137">Dependencies</span><span class="sxs-lookup"><span data-stu-id="d256d-137">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="d256d-138">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="d256d-138">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="d256d-139">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="d256d-139">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="d256d-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d256d-140">Next steps</span></span>

- [<span data-ttu-id="d256d-141">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d256d-141">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
