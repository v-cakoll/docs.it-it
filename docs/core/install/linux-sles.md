---
title: Installare .NET Core in SLES-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in SLES.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 8f64efcc8206b47855871104e5b6914570c06da0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619416"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="df919-103">Installare .NET Core SDK o runtime di .NET Core in SLES</span><span class="sxs-lookup"><span data-stu-id="df919-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="df919-104">.NET Core è supportato in SLES.</span><span class="sxs-lookup"><span data-stu-id="df919-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="df919-105">Questo articolo descrive come installare .NET Core in SLES.</span><span class="sxs-lookup"><span data-stu-id="df919-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="df919-106">Distribuzioni supportate</span><span class="sxs-lookup"><span data-stu-id="df919-106">Supported distributions</span></span>

<span data-ttu-id="df919-107">La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in SLES 12 SP2 e SLES 15.</span><span class="sxs-lookup"><span data-stu-id="df919-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="df919-108">Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di SLES non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="df919-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="df919-109">Un ✔️ indica che la versione di SLES o .NET Core è ancora supportata.</span><span class="sxs-lookup"><span data-stu-id="df919-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="df919-110">❌Indica che la versione di SLES o .NET Core non è supportata nella versione SLES.</span><span class="sxs-lookup"><span data-stu-id="df919-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="df919-111">Quando una versione di SLES e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.</span><span class="sxs-lookup"><span data-stu-id="df919-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="df919-112">SLES</span><span class="sxs-lookup"><span data-stu-id="df919-112">SLES</span></span>                   | <span data-ttu-id="df919-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="df919-113">.NET Core 2.1</span></span> | <span data-ttu-id="df919-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="df919-114">.NET Core 3.1</span></span> | <span data-ttu-id="df919-115">.NET 5 Preview (solo installazione manuale)</span><span class="sxs-lookup"><span data-stu-id="df919-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="df919-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="df919-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="df919-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="df919-117">✔️ 2.1</span></span>        | <span data-ttu-id="df919-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="df919-118">✔️ 3.1</span></span>        | <span data-ttu-id="df919-119">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="df919-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="df919-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="df919-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="df919-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="df919-121">✔️ 2.1</span></span>        | <span data-ttu-id="df919-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="df919-122">✔️ 3.1</span></span>        | <span data-ttu-id="df919-123">Anteprima di ✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="df919-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="df919-124">Le versioni seguenti di .NET Core non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="df919-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="df919-125">I download per questi ancora rimangono pubblicati:</span><span class="sxs-lookup"><span data-stu-id="df919-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="df919-126">3.0</span><span class="sxs-lookup"><span data-stu-id="df919-126">3.0</span></span>
- <span data-ttu-id="df919-127">2.2</span><span class="sxs-lookup"><span data-stu-id="df919-127">2.2</span></span>
- <span data-ttu-id="df919-128">2.0</span><span class="sxs-lookup"><span data-stu-id="df919-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="df919-129">Come installare altre versioni</span><span class="sxs-lookup"><span data-stu-id="df919-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="df919-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="df919-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="df919-131">Attualmente, il pacchetto di installazione del repository Microsoft SLES 15 installa il file *Microsoft-prod. repo* nella directory errata, impedendo a zypper di trovare i pacchetti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df919-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="df919-132">Per risolvere il problema, creare un collegamento simbolico nella directory corretta.</span><span class="sxs-lookup"><span data-stu-id="df919-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="df919-133">✔️ SLES 12</span><span class="sxs-lookup"><span data-stu-id="df919-133">SLES 12 ✔️</span></span>

<span data-ttu-id="df919-134">.NET Core richiede almeno SP2 per la famiglia SLES 12.</span><span class="sxs-lookup"><span data-stu-id="df919-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="df919-135">Risolvere i problemi relativi a gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="df919-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="df919-136">Questa sezione fornisce informazioni sugli errori comuni che possono verificarsi durante l'uso di gestione pacchetti per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df919-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="df919-137">Non è stato possibile recuperare</span><span class="sxs-lookup"><span data-stu-id="df919-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="df919-138">Dependencies</span><span class="sxs-lookup"><span data-stu-id="df919-138">Dependencies</span></span>

<span data-ttu-id="df919-139">Quando si installa con una gestione pacchetti, queste librerie vengono installate.</span><span class="sxs-lookup"><span data-stu-id="df919-139">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="df919-140">Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="df919-140">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="df919-141">krb5</span><span class="sxs-lookup"><span data-stu-id="df919-141">krb5</span></span>
- <span data-ttu-id="df919-142">libicu</span><span class="sxs-lookup"><span data-stu-id="df919-142">libicu</span></span>
- <span data-ttu-id="df919-143">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="df919-143">libopenssl1_1</span></span>

<span data-ttu-id="df919-144">Se la versione OpenSSL dell'ambiente di runtime di destinazione è 1,1 o successiva, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="df919-144">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="df919-145">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="df919-145">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="df919-146">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="df919-146">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="df919-147">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="df919-147">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="df919-148">È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="df919-148">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="df919-149">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="df919-149">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="df919-150">Installazione tramite script</span><span class="sxs-lookup"><span data-stu-id="df919-150">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="df919-151">Installazione manuale</span><span class="sxs-lookup"><span data-stu-id="df919-151">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="df919-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="df919-152">Next steps</span></span>

- [<span data-ttu-id="df919-153">Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="df919-153">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
