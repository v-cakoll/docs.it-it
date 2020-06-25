---
title: Installare .NET Core in Ubuntu-.NET Core
description: Illustra le varie modalità di installazione di .NET Core SDK e del runtime di .NET Core in Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: eef724138f2b908bf8601a509d298a06e55fb13e
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324743"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="43dbe-103">Installare .NET Core SDK o runtime di .NET Core in Ubuntu</span><span class="sxs-lookup"><span data-stu-id="43dbe-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="43dbe-104">.NET Core è supportato in Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="43dbe-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="43dbe-105">Questo articolo descrive come installare .NET Core in Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="43dbe-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="43dbe-106">Quando una versione di Ubuntu non è supportata, .NET Core non è più supportato con tale versione.</span><span class="sxs-lookup"><span data-stu-id="43dbe-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="43dbe-107">Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="43dbe-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="43dbe-108">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="43dbe-108">Supported distributions</span></span>

<span data-ttu-id="43dbe-109">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Ubuntu su cui sono supportate.</span><span class="sxs-lookup"><span data-stu-id="43dbe-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="43dbe-110">Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Ubuntu raggiunge la fine del ciclo di vita](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="43dbe-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="43dbe-111">Un ✔️ indica che la versione di Ubuntu o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="43dbe-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="43dbe-112">❌Indica che la versione di Ubuntu o .NET Core non è supportata in questa versione di Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="43dbe-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="43dbe-113">Quando una versione di Ubuntu e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="43dbe-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="43dbe-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="43dbe-114">Ubuntu</span></span>                   | <span data-ttu-id="43dbe-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="43dbe-115">.NET Core 2.1</span></span> | <span data-ttu-id="43dbe-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="43dbe-116">.NET Core 3.1</span></span> | <span data-ttu-id="43dbe-117">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="43dbe-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="43dbe-118">✔️ [20,04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="43dbe-119">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-119">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-120">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-120">✔️ 3.1</span></span>        | <span data-ttu-id="43dbe-121">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-122">✔️ [19,10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-122">✔️ [19.10](#1910-)</span></span>       | <span data-ttu-id="43dbe-123">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-123">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-124">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-124">✔️ 3.1</span></span>        | <span data-ttu-id="43dbe-125">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-126">❌[19,04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="43dbe-127">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-127">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-128">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-128">✔️ 3.1</span></span>        | <span data-ttu-id="43dbe-129">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-130">❌[18,10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="43dbe-131">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-131">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-132">❌3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-132">❌ 3.1</span></span>        | <span data-ttu-id="43dbe-133">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-134">✔️ [18,04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="43dbe-135">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-135">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-136">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-136">✔️ 3.1</span></span>        | <span data-ttu-id="43dbe-137">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="43dbe-139">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-139">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-140">❌3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-140">❌ 3.1</span></span>        | <span data-ttu-id="43dbe-141">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="43dbe-143">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-143">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-144">❌3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-144">❌ 3.1</span></span>        | <span data-ttu-id="43dbe-145">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-146">❌[16,10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="43dbe-147">❌2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-147">❌ 2.1</span></span>        | <span data-ttu-id="43dbe-148">❌3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-148">❌ 3.1</span></span>        | <span data-ttu-id="43dbe-149">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="43dbe-150">✔️ [16,04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="43dbe-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="43dbe-151">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-151">✔️ 2.1</span></span>        | <span data-ttu-id="43dbe-152">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="43dbe-152">✔️ 3.1</span></span>        | <span data-ttu-id="43dbe-153">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="43dbe-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="43dbe-154">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="43dbe-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="43dbe-155">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="43dbe-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="43dbe-156">3.0</span><span class="sxs-lookup"><span data-stu-id="43dbe-156">3.0</span></span>
- <span data-ttu-id="43dbe-157">2.2</span><span class="sxs-lookup"><span data-stu-id="43dbe-157">2.2</span></span>
- <span data-ttu-id="43dbe-158">2.0</span><span class="sxs-lookup"><span data-stu-id="43dbe-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="43dbe-159">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="43dbe-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="43dbe-160">20,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="43dbe-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="43dbe-161">19,10 ✔️</span><span class="sxs-lookup"><span data-stu-id="43dbe-161">19.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="43dbe-162">19,04❌</span><span class="sxs-lookup"><span data-stu-id="43dbe-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="43dbe-163">18,10❌</span><span class="sxs-lookup"><span data-stu-id="43dbe-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="43dbe-164">18,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="43dbe-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="43dbe-165">17,10❌</span><span class="sxs-lookup"><span data-stu-id="43dbe-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="43dbe-166">17,04❌</span><span class="sxs-lookup"><span data-stu-id="43dbe-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="43dbe-167">16,10❌</span><span class="sxs-lookup"><span data-stu-id="43dbe-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="43dbe-168">16,04 ✔️</span><span class="sxs-lookup"><span data-stu-id="43dbe-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="43dbe-169">SDK o runtime di aggiornamento APT</span><span class="sxs-lookup"><span data-stu-id="43dbe-169">APT update SDK or runtime</span></span>

<span data-ttu-id="43dbe-170">Quando è disponibile una nuova versione patch per .NET Core, è possibile aggiornarla semplicemente tramite APT con i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="43dbe-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="43dbe-171">Risoluzione dei problemi di APT</span><span class="sxs-lookup"><span data-stu-id="43dbe-171">APT troubleshooting</span></span>

<span data-ttu-id="43dbe-172">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di APT per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="43dbe-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="43dbe-173">Impossibile individuare</span><span class="sxs-lookup"><span data-stu-id="43dbe-173">Unable to locate</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="43dbe-174">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="43dbe-174">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="43dbe-175">Snap</span><span class="sxs-lookup"><span data-stu-id="43dbe-175">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="43dbe-176">Dependencies</span><span class="sxs-lookup"><span data-stu-id="43dbe-176">Dependencies</span></span>

<span data-ttu-id="43dbe-177">Quando si installa con una gestione pacchetti, queste librerie vengono installate.</span><span class="sxs-lookup"><span data-stu-id="43dbe-177">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="43dbe-178">Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="43dbe-178">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="43dbe-179">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="43dbe-179">liblttng-ust0</span></span>
- <span data-ttu-id="43dbe-180">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="43dbe-180">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="43dbe-181">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="43dbe-181">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="43dbe-182">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="43dbe-182">libssl1.0.0</span></span>
- <span data-ttu-id="43dbe-183">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="43dbe-183">libkrb5-3</span></span>
- <span data-ttu-id="43dbe-184">zlib1g</span><span class="sxs-lookup"><span data-stu-id="43dbe-184">zlib1g</span></span>
- <span data-ttu-id="43dbe-185">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="43dbe-185">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="43dbe-186">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="43dbe-186">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="43dbe-187">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="43dbe-187">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="43dbe-188">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="43dbe-188">libicu60 (for 18.x)</span></span>

<span data-ttu-id="43dbe-189">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="43dbe-189">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="43dbe-190">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="43dbe-190">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="43dbe-191">È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="43dbe-191">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="43dbe-192">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="43dbe-192">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="43dbe-193">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="43dbe-193">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="43dbe-194">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="43dbe-194">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="43dbe-195">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="43dbe-195">Next steps</span></span>

- [<span data-ttu-id="43dbe-196">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="43dbe-196">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
