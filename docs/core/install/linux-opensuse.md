---
title: Installare .NET Core in openSUSE-.NET Core
description: Illustra le varie modalità di installazione di .NET Core SDK e del runtime di .NET Core in openSUSE.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: a642cee9ae78f81cd671d8745d5ce241be6a3b69
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84603048"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="54795-103">Installare .NET Core SDK o runtime di .NET Core in openSUSE</span><span class="sxs-lookup"><span data-stu-id="54795-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="54795-104">.NET Core è supportato in openSUSE.</span><span class="sxs-lookup"><span data-stu-id="54795-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="54795-105">Questo articolo descrive come installare .NET Core in openSUSE.</span><span class="sxs-lookup"><span data-stu-id="54795-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="54795-106">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="54795-106">Supported distributions</span></span>

<span data-ttu-id="54795-107">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="54795-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="54795-108">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di openSUSE non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="54795-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="54795-109">Un ✔️ indica che la versione di openSUSE o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="54795-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="54795-110">❌Indica che la versione di openSUSE o .NET Core non è supportata nella versione di openSUSE.</span><span class="sxs-lookup"><span data-stu-id="54795-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="54795-111">Quando una versione di openSUSE e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="54795-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="54795-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="54795-112">openSUSE</span></span>                   | <span data-ttu-id="54795-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="54795-113">.NET Core 2.1</span></span> | <span data-ttu-id="54795-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="54795-114">.NET Core 3.1</span></span> | <span data-ttu-id="54795-115">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="54795-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="54795-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="54795-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="54795-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="54795-117">✔️ 2.1</span></span>        | <span data-ttu-id="54795-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="54795-118">✔️ 3.1</span></span>        | <span data-ttu-id="54795-119">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="54795-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="54795-120">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="54795-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="54795-121">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="54795-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="54795-122">3.0</span><span class="sxs-lookup"><span data-stu-id="54795-122">3.0</span></span>
- <span data-ttu-id="54795-123">2.2</span><span class="sxs-lookup"><span data-stu-id="54795-123">2.2</span></span>
- <span data-ttu-id="54795-124">2.0</span><span class="sxs-lookup"><span data-stu-id="54795-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="54795-125">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="54795-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="54795-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="54795-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="54795-127">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="54795-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="54795-128">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="54795-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="54795-129">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="54795-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="54795-130">Snap</span><span class="sxs-lookup"><span data-stu-id="54795-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="54795-131">Dependencies</span><span class="sxs-lookup"><span data-stu-id="54795-131">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="54795-132">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="54795-132">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="54795-133">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="54795-133">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="54795-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="54795-134">Next steps</span></span>

- [<span data-ttu-id="54795-135">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="54795-135">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
