---
title: Installare .NET Core in Debian-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: ded9d2be72e8ec476d5ace752e44d92eb0ee1028
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324917"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="015ab-103">Installare .NET Core SDK o runtime di .NET Core in Debian</span><span class="sxs-lookup"><span data-stu-id="015ab-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="015ab-104">Questo articolo descrive come installare .NET Core in Debian.</span><span class="sxs-lookup"><span data-stu-id="015ab-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="015ab-105">Quando una versione di Debian non è supportata, .NET Core non è più supportato con tale versione.</span><span class="sxs-lookup"><span data-stu-id="015ab-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="015ab-106">Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="015ab-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="015ab-107">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="015ab-107">Supported distributions</span></span>

<span data-ttu-id="015ab-108">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Debian su cui sono supportate.</span><span class="sxs-lookup"><span data-stu-id="015ab-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="015ab-109">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Debian raggiunge la fine del ciclo di vita](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="015ab-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="015ab-110">Un ✔️ indica che la versione di Debian o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="015ab-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="015ab-111">❌Indica che la versione di Debian o .NET Core non è supportata in questa versione Debian.</span><span class="sxs-lookup"><span data-stu-id="015ab-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="015ab-112">Quando una versione di Debian e una versione di .NET Core sono ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="015ab-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="015ab-113">Debian</span><span class="sxs-lookup"><span data-stu-id="015ab-113">Debian</span></span>                   | <span data-ttu-id="015ab-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="015ab-114">.NET Core 2.1</span></span> | <span data-ttu-id="015ab-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="015ab-115">.NET Core 3.1</span></span> | <span data-ttu-id="015ab-116">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="015ab-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="015ab-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="015ab-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="015ab-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="015ab-118">✔️ 2.1</span></span>        | <span data-ttu-id="015ab-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="015ab-119">✔️ 3.1</span></span>        | <span data-ttu-id="015ab-120">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="015ab-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="015ab-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="015ab-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="015ab-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="015ab-122">✔️ 2.1</span></span>        | <span data-ttu-id="015ab-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="015ab-123">✔️ 3.1</span></span>        | <span data-ttu-id="015ab-124">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="015ab-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="015ab-125">❌[8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="015ab-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="015ab-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="015ab-126">✔️ 2.1</span></span>        | <span data-ttu-id="015ab-127">❌3,1</span><span class="sxs-lookup"><span data-stu-id="015ab-127">❌ 3.1</span></span>        | <span data-ttu-id="015ab-128">❌Anteprima 5,0</span><span class="sxs-lookup"><span data-stu-id="015ab-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="015ab-129">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="015ab-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="015ab-130">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="015ab-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="015ab-131">3.0</span><span class="sxs-lookup"><span data-stu-id="015ab-131">3.0</span></span>
- <span data-ttu-id="015ab-132">2.2</span><span class="sxs-lookup"><span data-stu-id="015ab-132">2.2</span></span>
- <span data-ttu-id="015ab-133">2.0</span><span class="sxs-lookup"><span data-stu-id="015ab-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="015ab-134">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="015ab-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="015ab-135">✔️ Debian 10</span><span class="sxs-lookup"><span data-stu-id="015ab-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="015ab-136">✔️ Debian 9</span><span class="sxs-lookup"><span data-stu-id="015ab-136">Debian 9 ✔️</span></span>

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

## <a name="debian-8-"></a><span data-ttu-id="015ab-137">Debian 8❌</span><span class="sxs-lookup"><span data-stu-id="015ab-137">Debian 8 ❌</span></span>

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

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="015ab-138">SDK o runtime di aggiornamento APT</span><span class="sxs-lookup"><span data-stu-id="015ab-138">APT update SDK or runtime</span></span>

<span data-ttu-id="015ab-139">Quando è disponibile una nuova versione patch per .NET Core, è possibile aggiornarla semplicemente tramite APT con i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="015ab-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="015ab-140">Risoluzione dei problemi di APT</span><span class="sxs-lookup"><span data-stu-id="015ab-140">APT troubleshooting</span></span>

<span data-ttu-id="015ab-141">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di APT per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="015ab-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="015ab-142">Impossibile individuare</span><span class="sxs-lookup"><span data-stu-id="015ab-142">Unable to locate</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="015ab-143">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="015ab-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="015ab-144">Snap</span><span class="sxs-lookup"><span data-stu-id="015ab-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="015ab-145">Dependencies</span><span class="sxs-lookup"><span data-stu-id="015ab-145">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="015ab-146">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="015ab-146">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="015ab-147">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="015ab-147">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="015ab-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="015ab-148">Next steps</span></span>

- [<span data-ttu-id="015ab-149">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="015ab-149">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
