---
title: Installare .NET Core in Fedora-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in Fedora.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 52aa9409ec876e0d1eaef22fb739046941fda897
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84603090"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="ae110-103">Installare .NET Core SDK o runtime di .NET Core in Fedora</span><span class="sxs-lookup"><span data-stu-id="ae110-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="ae110-104">.NET Core è supportato in Fedora.</span><span class="sxs-lookup"><span data-stu-id="ae110-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="ae110-105">Questo articolo descrive come installare .NET Core in Fedora.</span><span class="sxs-lookup"><span data-stu-id="ae110-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="ae110-106">Quando una versione di Fedora non è più supportata, .NET Core non è più supportato con tale versione.</span><span class="sxs-lookup"><span data-stu-id="ae110-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="ae110-107">Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="ae110-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="ae110-108">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="ae110-108">Supported distributions</span></span>

<span data-ttu-id="ae110-109">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Fedora su cui sono supportate.</span><span class="sxs-lookup"><span data-stu-id="ae110-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="ae110-110">Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Fedora raggiunge la fine del ciclo di vita](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="ae110-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="ae110-111">Un ✔️ indica che la versione di Fedora o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="ae110-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="ae110-112">❌Indica che la versione di Fedora o .NET Core non è supportata nella versione Fedora.</span><span class="sxs-lookup"><span data-stu-id="ae110-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="ae110-113">Quando una versione di Fedora e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="ae110-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="ae110-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="ae110-114">Fedora</span></span>                   | <span data-ttu-id="ae110-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ae110-115">.NET Core 2.1</span></span> | <span data-ttu-id="ae110-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ae110-116">.NET Core 3.1</span></span> | <span data-ttu-id="ae110-117">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="ae110-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="ae110-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="ae110-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="ae110-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ae110-119">✔️ 2.1</span></span>        | <span data-ttu-id="ae110-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ae110-120">✔️ 3.1</span></span>        | <span data-ttu-id="ae110-121">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="ae110-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="ae110-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="ae110-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="ae110-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ae110-123">✔️ 2.1</span></span>        | <span data-ttu-id="ae110-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ae110-124">✔️ 3.1</span></span>        | <span data-ttu-id="ae110-125">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="ae110-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="ae110-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="ae110-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="ae110-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ae110-127">✔️ 2.1</span></span>        | <span data-ttu-id="ae110-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ae110-128">✔️ 3.1</span></span>        | <span data-ttu-id="ae110-129">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="ae110-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="ae110-130">❌[29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="ae110-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="ae110-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ae110-131">✔️ 2.1</span></span>        | <span data-ttu-id="ae110-132">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ae110-132">✔️ 3.1</span></span>        | <span data-ttu-id="ae110-133">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="ae110-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="ae110-134">❌[28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="ae110-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="ae110-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ae110-135">✔️ 2.1</span></span>        | <span data-ttu-id="ae110-136">❌3,1</span><span class="sxs-lookup"><span data-stu-id="ae110-136">❌ 3.1</span></span>        | <span data-ttu-id="ae110-137">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="ae110-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="ae110-138">❌[27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="ae110-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="ae110-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ae110-139">✔️ 2.1</span></span>        | <span data-ttu-id="ae110-140">❌3,1</span><span class="sxs-lookup"><span data-stu-id="ae110-140">❌ 3.1</span></span>        | <span data-ttu-id="ae110-141">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="ae110-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="ae110-142">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="ae110-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="ae110-143">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="ae110-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="ae110-144">3.0</span><span class="sxs-lookup"><span data-stu-id="ae110-144">3.0</span></span>
- <span data-ttu-id="ae110-145">2.2</span><span class="sxs-lookup"><span data-stu-id="ae110-145">2.2</span></span>
- <span data-ttu-id="ae110-146">2.0</span><span class="sxs-lookup"><span data-stu-id="ae110-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ae110-147">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="ae110-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="ae110-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="ae110-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="ae110-149">.NET Core 3,1 è disponibile nei repository dei pacchetti predefiniti per Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="ae110-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="ae110-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="ae110-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="ae110-151">Fedora 30❌</span><span class="sxs-lookup"><span data-stu-id="ae110-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="ae110-152">Fedora 29❌</span><span class="sxs-lookup"><span data-stu-id="ae110-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="ae110-153">Fedora 28❌</span><span class="sxs-lookup"><span data-stu-id="ae110-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="ae110-154">Fedora 27❌</span><span class="sxs-lookup"><span data-stu-id="ae110-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ae110-155">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="ae110-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="ae110-156">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae110-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="ae110-157">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="ae110-157">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="ae110-158">Snap</span><span class="sxs-lookup"><span data-stu-id="ae110-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="ae110-159">Dependencies</span><span class="sxs-lookup"><span data-stu-id="ae110-159">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="ae110-160">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="ae110-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="ae110-161">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="ae110-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="ae110-162">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ae110-162">Next steps</span></span>

- [<span data-ttu-id="ae110-163">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ae110-163">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)