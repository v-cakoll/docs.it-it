---
title: Installare .NET Core in Debian-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 68a3e848b3d80806e875dfb2fb7e2cbf223f8ad5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619494"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="b31ed-103">Installare .NET Core SDK o runtime di .NET Core in Debian</span><span class="sxs-lookup"><span data-stu-id="b31ed-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="b31ed-104">Questo articolo descrive come installare .NET Core in Debian.</span><span class="sxs-lookup"><span data-stu-id="b31ed-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="b31ed-105">Quando una versione di Debian non è supportata, .NET Core non è più supportato con tale versione.</span><span class="sxs-lookup"><span data-stu-id="b31ed-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="b31ed-106">Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b31ed-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b31ed-107">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="b31ed-107">Supported distributions</span></span>

<span data-ttu-id="b31ed-108">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Debian su cui sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b31ed-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="b31ed-109">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Debian raggiunge la fine del ciclo di vita](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="b31ed-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="b31ed-110">Un ✔️ indica che la versione di Debian o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="b31ed-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="b31ed-111">❌Indica che la versione di Debian o .NET Core non è supportata in questa versione Debian.</span><span class="sxs-lookup"><span data-stu-id="b31ed-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="b31ed-112">Quando una versione di Debian e una versione di .NET Core sono ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="b31ed-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="b31ed-113">Debian</span><span class="sxs-lookup"><span data-stu-id="b31ed-113">Debian</span></span>                   | <span data-ttu-id="b31ed-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b31ed-114">.NET Core 2.1</span></span> | <span data-ttu-id="b31ed-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b31ed-115">.NET Core 3.1</span></span> | <span data-ttu-id="b31ed-116">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="b31ed-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b31ed-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="b31ed-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="b31ed-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b31ed-118">✔️ 2.1</span></span>        | <span data-ttu-id="b31ed-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b31ed-119">✔️ 3.1</span></span>        | <span data-ttu-id="b31ed-120">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b31ed-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b31ed-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="b31ed-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="b31ed-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b31ed-122">✔️ 2.1</span></span>        | <span data-ttu-id="b31ed-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="b31ed-123">✔️ 3.1</span></span>        | <span data-ttu-id="b31ed-124">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="b31ed-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b31ed-125">❌[8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="b31ed-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="b31ed-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="b31ed-126">✔️ 2.1</span></span>        | <span data-ttu-id="b31ed-127">❌3,1</span><span class="sxs-lookup"><span data-stu-id="b31ed-127">❌ 3.1</span></span>        | <span data-ttu-id="b31ed-128">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="b31ed-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="b31ed-129">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="b31ed-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="b31ed-130">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="b31ed-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b31ed-131">3.0</span><span class="sxs-lookup"><span data-stu-id="b31ed-131">3.0</span></span>
- <span data-ttu-id="b31ed-132">2.2</span><span class="sxs-lookup"><span data-stu-id="b31ed-132">2.2</span></span>
- <span data-ttu-id="b31ed-133">2.0</span><span class="sxs-lookup"><span data-stu-id="b31ed-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b31ed-134">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="b31ed-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="b31ed-135">✔️ Debian 10</span><span class="sxs-lookup"><span data-stu-id="b31ed-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="b31ed-136">✔️ Debian 9</span><span class="sxs-lookup"><span data-stu-id="b31ed-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="b31ed-137">Debian 8❌</span><span class="sxs-lookup"><span data-stu-id="b31ed-137">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="b31ed-138">SDK o runtime di aggiornamento APT</span><span class="sxs-lookup"><span data-stu-id="b31ed-138">APT update SDK or runtime</span></span>

<span data-ttu-id="b31ed-139">Quando è disponibile una nuova versione patch per .NET Core, è possibile aggiornarla semplicemente tramite APT con i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b31ed-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="b31ed-140">Risoluzione dei problemi di APT</span><span class="sxs-lookup"><span data-stu-id="b31ed-140">APT troubleshooting</span></span>

<span data-ttu-id="b31ed-141">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di APT per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b31ed-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="b31ed-142">Impossibile individuare</span><span class="sxs-lookup"><span data-stu-id="b31ed-142">Unable to locate</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="b31ed-143">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="b31ed-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="b31ed-144">Snap</span><span class="sxs-lookup"><span data-stu-id="b31ed-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="b31ed-145">Dependencies</span><span class="sxs-lookup"><span data-stu-id="b31ed-145">Dependencies</span></span>

<span data-ttu-id="b31ed-146">Quando si installa con una gestione pacchetti, queste librerie vengono installate.</span><span class="sxs-lookup"><span data-stu-id="b31ed-146">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="b31ed-147">Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="b31ed-147">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="b31ed-148">libc6</span><span class="sxs-lookup"><span data-stu-id="b31ed-148">libc6</span></span>
- <span data-ttu-id="b31ed-149">libgcc1</span><span class="sxs-lookup"><span data-stu-id="b31ed-149">libgcc1</span></span>
- <span data-ttu-id="b31ed-150">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="b31ed-150">libgssapi-krb5-2</span></span>
- <span data-ttu-id="b31ed-151">libicu52 (per 8. x)</span><span class="sxs-lookup"><span data-stu-id="b31ed-151">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="b31ed-152">libicu57 (per 9. x)</span><span class="sxs-lookup"><span data-stu-id="b31ed-152">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="b31ed-153">libicu63 (per 10. x)</span><span class="sxs-lookup"><span data-stu-id="b31ed-153">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="b31ed-154">libicu67 (per 11. x)</span><span class="sxs-lookup"><span data-stu-id="b31ed-154">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="b31ed-155">libssl 1.0.0 (per 8. x)</span><span class="sxs-lookup"><span data-stu-id="b31ed-155">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="b31ed-156">libssl 1.1 (per 9. x-11. x)</span><span class="sxs-lookup"><span data-stu-id="b31ed-156">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="b31ed-157">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="b31ed-157">libstdc++6</span></span>
- <span data-ttu-id="b31ed-158">zlib1g</span><span class="sxs-lookup"><span data-stu-id="b31ed-158">zlib1g</span></span>

<span data-ttu-id="b31ed-159">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="b31ed-159">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="b31ed-160">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="b31ed-160">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="b31ed-161">È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="b31ed-161">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="b31ed-162">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="b31ed-162">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="b31ed-163">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="b31ed-163">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b31ed-164">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="b31ed-164">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b31ed-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b31ed-165">Next steps</span></span>

- [<span data-ttu-id="b31ed-166">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b31ed-166">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
