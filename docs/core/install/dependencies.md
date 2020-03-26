---
title: Dipendenze di runtime e sdiche di .NET Core - .NET Core
description: Vengono descritti in dettaglio i prerequisiti del sistema operativo e dell'architettura della CPU per installare .NET Core SDK e runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546562"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="620f9-103">Dipendenze e requisiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="620f9-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="620f9-104">Questo articolo descrive in dettaglio quali sistemi operativi e architettura della CPU sono supportati da .NET Core.This article details which operating systems and CPU architecture are supported by .NET Core.</span><span class="sxs-lookup"><span data-stu-id="620f9-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="620f9-105">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="620f9-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="620f9-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="620f9-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="620f9-107">Le seguenti versioni di Windows sono supportate con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="620f9-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-108">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-109">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-109">OS</span></span>                            | <span data-ttu-id="620f9-110">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-110">Version</span></span>                        | <span data-ttu-id="620f9-111">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="620f9-112">Client Windows</span><span class="sxs-lookup"><span data-stu-id="620f9-112">Windows Client</span></span>                | <span data-ttu-id="620f9-113">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="620f9-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="620f9-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-114">x64, x86</span></span>        |
| <span data-ttu-id="620f9-115">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="620f9-115">Windows 10 Client</span></span>             | <span data-ttu-id="620f9-116">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="620f9-116">Version 1607+</span></span>                  | <span data-ttu-id="620f9-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-117">x64, x86</span></span>        |
| <span data-ttu-id="620f9-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="620f9-118">Windows Server</span></span>                | <span data-ttu-id="620f9-119">2012 R2</span><span class="sxs-lookup"><span data-stu-id="620f9-119">2012 R2+</span></span>                       | <span data-ttu-id="620f9-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-120">x64, x86</span></span>        |
| <span data-ttu-id="620f9-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="620f9-121">Nano Server</span></span>                   | <span data-ttu-id="620f9-122">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="620f9-122">Version 1803+</span></span>                  | <span data-ttu-id="620f9-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-123">x64, ARM32</span></span>      |

<span data-ttu-id="620f9-124">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.1, vedere Versioni del sistema operativo supportate di [.NET Core 3.1.](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="620f9-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="620f9-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="620f9-126">*.NET Core 3.0 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="620f9-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="620f9-127">Le seguenti versioni di Windows sono supportate con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="620f9-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-128">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-129">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-129">OS</span></span>                            | <span data-ttu-id="620f9-130">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-130">Version</span></span>                        | <span data-ttu-id="620f9-131">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="620f9-132">Client Windows</span><span class="sxs-lookup"><span data-stu-id="620f9-132">Windows Client</span></span>                | <span data-ttu-id="620f9-133">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="620f9-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="620f9-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-134">x64, x86</span></span>        |
| <span data-ttu-id="620f9-135">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="620f9-135">Windows 10 Client</span></span>             | <span data-ttu-id="620f9-136">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="620f9-136">Version 1607+</span></span>                  | <span data-ttu-id="620f9-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-137">x64, x86</span></span>        |
| <span data-ttu-id="620f9-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="620f9-138">Windows Server</span></span>                | <span data-ttu-id="620f9-139">2012 R2</span><span class="sxs-lookup"><span data-stu-id="620f9-139">2012 R2+</span></span>                       | <span data-ttu-id="620f9-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-140">x64, x86</span></span>        |
| <span data-ttu-id="620f9-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="620f9-141">Nano Server</span></span>                   | <span data-ttu-id="620f9-142">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="620f9-142">Version 1803+</span></span>                  | <span data-ttu-id="620f9-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-143">x64, ARM32</span></span>      |

<span data-ttu-id="620f9-144">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.0, vedere Versioni del sistema operativo supportate di [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="620f9-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="620f9-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="620f9-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="620f9-146">*.NET Core 2.2 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="620f9-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="620f9-147">Le seguenti versioni di Windows sono supportate con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="620f9-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-148">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-149">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-149">OS</span></span>                            | <span data-ttu-id="620f9-150">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-150">Version</span></span>                        | <span data-ttu-id="620f9-151">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="620f9-152">Client Windows</span><span class="sxs-lookup"><span data-stu-id="620f9-152">Windows Client</span></span>                | <span data-ttu-id="620f9-153">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="620f9-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="620f9-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-154">x64, x86</span></span>        |
| <span data-ttu-id="620f9-155">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="620f9-155">Windows 10 Client</span></span>             | <span data-ttu-id="620f9-156">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="620f9-156">Version 1607+</span></span>                  | <span data-ttu-id="620f9-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-157">x64, x86</span></span>        |
| <span data-ttu-id="620f9-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="620f9-158">Windows Server</span></span>                | <span data-ttu-id="620f9-159">2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="620f9-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="620f9-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-160">x64, x86</span></span>        |
| <span data-ttu-id="620f9-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="620f9-161">Nano Server</span></span>                   | <span data-ttu-id="620f9-162">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="620f9-162">Version 1803+</span></span>                   | <span data-ttu-id="620f9-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-163">x64, ARM32</span></span>      |

<span data-ttu-id="620f9-164">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.2, vedere Versioni del sistema operativo supportate di [.NET Core 2.2.](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="620f9-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="620f9-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="620f9-166">Le seguenti versioni di Windows sono supportate con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="620f9-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-167">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-168">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-168">OS</span></span>                            | <span data-ttu-id="620f9-169">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-169">Version</span></span>                        | <span data-ttu-id="620f9-170">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="620f9-171">Client Windows</span><span class="sxs-lookup"><span data-stu-id="620f9-171">Windows Client</span></span>                | <span data-ttu-id="620f9-172">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="620f9-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="620f9-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-173">x64, x86</span></span>        |
| <span data-ttu-id="620f9-174">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="620f9-174">Windows 10 Client</span></span>             | <span data-ttu-id="620f9-175">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="620f9-175">Version 1607+</span></span>                  | <span data-ttu-id="620f9-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-176">x64, x86</span></span>        |
| <span data-ttu-id="620f9-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="620f9-177">Windows Server</span></span>                | <span data-ttu-id="620f9-178">2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="620f9-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="620f9-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="620f9-179">x64, x86</span></span>        |
| <span data-ttu-id="620f9-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="620f9-180">Nano Server</span></span>                   | <span data-ttu-id="620f9-181">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="620f9-181">Version 1803+</span></span>                  | <span data-ttu-id="620f9-182">x64,</span><span class="sxs-lookup"><span data-stu-id="620f9-182">x64,</span></span>            |

<span data-ttu-id="620f9-183">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.1, vedere Versioni del sistema operativo supportate di [.NET Core 2.1.](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="620f9-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="620f9-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="620f9-185">Ulteriori dipendenze sono necessarie se si installa .NET SDK o runtime nelle seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="620f9-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="620f9-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="620f9-186">Windows 7 SP1</span></span>
- <span data-ttu-id="620f9-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="620f9-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="620f9-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="620f9-188">Windows 8.1</span></span>
- <span data-ttu-id="620f9-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="620f9-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="620f9-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="620f9-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="620f9-191">Installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="620f9-191">Install the following:</span></span>

- <span data-ttu-id="620f9-192">[Aggiornamento ridistribuibile 3](https://www.microsoft.com/download/details.aspx?id=52685)di Microsoft Visual C</span><span class="sxs-lookup"><span data-stu-id="620f9-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="620f9-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="620f9-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="620f9-194">I requisiti di cui sopra sono necessari anche se si verifica uno dei seguenti errori:</span><span class="sxs-lookup"><span data-stu-id="620f9-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="620f9-195">Impossibile avviare il programma perché *api-ms-win-crt-runtime-l1-1-0.dll* non è presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="620f9-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="620f9-196">Provare a reinstallare il programma per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="620f9-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="620f9-197">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="620f9-197">\- or -</span></span>
>
> <span data-ttu-id="620f9-198">La libreria *hostfxr.dll* è stata trovata, ma il caricamento da *C:\\\<path_to_app>hostfxr.dll \\* non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="620f9-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="620f9-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="620f9-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="620f9-200">.NET Core 3.1 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="620f9-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="620f9-201">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="620f9-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="620f9-202">.NET Core 3.1 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="620f9-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-203">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-204">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-204">OS</span></span>                             | <span data-ttu-id="620f9-205">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-205">Version</span></span>               | <span data-ttu-id="620f9-206">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="620f9-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="620f9-208">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="620f9-208">6, 7, 8</span></span>               | <span data-ttu-id="620f9-209">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-209">x64</span></span> |
| <span data-ttu-id="620f9-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="620f9-210">CentOS</span></span>                         | <span data-ttu-id="620f9-211">7+</span><span class="sxs-lookup"><span data-stu-id="620f9-211">7+</span></span>                    | <span data-ttu-id="620f9-212">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-212">x64</span></span> |
| <span data-ttu-id="620f9-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-213">Oracle Linux</span></span>                   | <span data-ttu-id="620f9-214">7+</span><span class="sxs-lookup"><span data-stu-id="620f9-214">7+</span></span>                    | <span data-ttu-id="620f9-215">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-215">x64</span></span> |
| <span data-ttu-id="620f9-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="620f9-216">Fedora</span></span>                         | <span data-ttu-id="620f9-217">Più di 30 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-217">30+</span></span>                   | <span data-ttu-id="620f9-218">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-218">x64</span></span> |
| <span data-ttu-id="620f9-219">Debian</span><span class="sxs-lookup"><span data-stu-id="620f9-219">Debian</span></span>                         | <span data-ttu-id="620f9-220">9+</span><span class="sxs-lookup"><span data-stu-id="620f9-220">9+</span></span>                    | <span data-ttu-id="620f9-221">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="620f9-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="620f9-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="620f9-222">Ubuntu</span></span>                         | <span data-ttu-id="620f9-223">16.04+</span><span class="sxs-lookup"><span data-stu-id="620f9-223">16.04+</span></span>                | <span data-ttu-id="620f9-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="620f9-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="620f9-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="620f9-225">Linux Mint</span></span>                     | <span data-ttu-id="620f9-226">PIÙ di 18 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-226">18+</span></span>                   | <span data-ttu-id="620f9-227">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-227">x64</span></span> |
| <span data-ttu-id="620f9-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="620f9-228">openSUSE</span></span>                       | <span data-ttu-id="620f9-229">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-229">15+</span></span>                   | <span data-ttu-id="620f9-230">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-230">x64</span></span> |
| <span data-ttu-id="620f9-231">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="620f9-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="620f9-232">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="620f9-232">12 SP2+</span></span>               | <span data-ttu-id="620f9-233">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-233">x64</span></span> |
| <span data-ttu-id="620f9-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-234">Alpine Linux</span></span>                   | <span data-ttu-id="620f9-235">3.10 o più</span><span class="sxs-lookup"><span data-stu-id="620f9-235">3.10+</span></span>                 | <span data-ttu-id="620f9-236">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="620f9-236">x64, ARM64</span></span> |

<span data-ttu-id="620f9-237">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.1, vedere Versioni del sistema operativo supportate di [.NET Core 3.1.](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="620f9-238">Per ulteriori informazioni su come installare .NET Core 3.1 in ARM64 (kernel 4.14), vedere Installazione di [.NET Core 3.0 su Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="620f9-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="620f9-239">Il supporto ARM64 richiede kernel Linux 4.14 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="620f9-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="620f9-240">Alcune distribuzioni linux soddisfano questo requisito, mentre altre no.</span><span class="sxs-lookup"><span data-stu-id="620f9-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="620f9-241">Ad esempio, Ubuntu 18.04 è supportato, ma Ubuntu 16.04 non lo è.</span><span class="sxs-lookup"><span data-stu-id="620f9-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="620f9-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="620f9-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="620f9-243">*.NET Core 3.0 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="620f9-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="620f9-244">.NET Core 3.0 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="620f9-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="620f9-245">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="620f9-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="620f9-246">.NET Core 3.0 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="620f9-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-247">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-248">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-248">OS</span></span>                             | <span data-ttu-id="620f9-249">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-249">Version</span></span>               | <span data-ttu-id="620f9-250">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="620f9-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="620f9-252">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="620f9-252">6, 7, 8</span></span>               | <span data-ttu-id="620f9-253">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-253">x64</span></span> |
| <span data-ttu-id="620f9-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="620f9-254">CentOS</span></span>                         | <span data-ttu-id="620f9-255">7+</span><span class="sxs-lookup"><span data-stu-id="620f9-255">7+</span></span>                    | <span data-ttu-id="620f9-256">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-256">x64</span></span> |
| <span data-ttu-id="620f9-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-257">Oracle Linux</span></span>                   | <span data-ttu-id="620f9-258">7+</span><span class="sxs-lookup"><span data-stu-id="620f9-258">7+</span></span>                    | <span data-ttu-id="620f9-259">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-259">x64</span></span> |
| <span data-ttu-id="620f9-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="620f9-260">Fedora</span></span>                         | <span data-ttu-id="620f9-261">Più di 29 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-261">29+</span></span>                   | <span data-ttu-id="620f9-262">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-262">x64</span></span> |
| <span data-ttu-id="620f9-263">Debian</span><span class="sxs-lookup"><span data-stu-id="620f9-263">Debian</span></span>                         | <span data-ttu-id="620f9-264">9+</span><span class="sxs-lookup"><span data-stu-id="620f9-264">9+</span></span>                    | <span data-ttu-id="620f9-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="620f9-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="620f9-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="620f9-266">Ubuntu</span></span>                         | <span data-ttu-id="620f9-267">16.04+</span><span class="sxs-lookup"><span data-stu-id="620f9-267">16.04+</span></span>                | <span data-ttu-id="620f9-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="620f9-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="620f9-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="620f9-269">Linux Mint</span></span>                     | <span data-ttu-id="620f9-270">PIÙ di 18 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-270">18+</span></span>                   | <span data-ttu-id="620f9-271">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-271">x64</span></span> |
| <span data-ttu-id="620f9-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="620f9-272">openSUSE</span></span>                       | <span data-ttu-id="620f9-273">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-273">15+</span></span>                   | <span data-ttu-id="620f9-274">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-274">x64</span></span> |
| <span data-ttu-id="620f9-275">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="620f9-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="620f9-276">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="620f9-276">12 SP2+</span></span>               | <span data-ttu-id="620f9-277">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-277">x64</span></span> |
| <span data-ttu-id="620f9-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-278">Alpine Linux</span></span>                   | <span data-ttu-id="620f9-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="620f9-279">3.8+</span></span>                  | <span data-ttu-id="620f9-280">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="620f9-280">x64, ARM64</span></span> |

<span data-ttu-id="620f9-281">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.0, vedere Versioni del sistema operativo supportate di [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="620f9-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="620f9-282">Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="620f9-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="620f9-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="620f9-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="620f9-284">*.NET Core 2.2 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="620f9-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="620f9-285">.NET Core 2.2 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="620f9-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="620f9-286">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="620f9-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="620f9-287">.NET Core 2.2 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="620f9-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-288">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-289">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-289">OS</span></span>                             |  <span data-ttu-id="620f9-290">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-290">Version</span></span>                |  <span data-ttu-id="620f9-291">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="620f9-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="620f9-293">6, 7</span><span class="sxs-lookup"><span data-stu-id="620f9-293">6, 7</span></span>                   | <span data-ttu-id="620f9-294">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-294">x64</span></span> |
| <span data-ttu-id="620f9-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="620f9-295">CentOS</span></span>                         |  <span data-ttu-id="620f9-296">7</span><span class="sxs-lookup"><span data-stu-id="620f9-296">7</span></span>                      | <span data-ttu-id="620f9-297">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-297">x64</span></span> |
| <span data-ttu-id="620f9-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-298">Oracle Linux</span></span>                   |  <span data-ttu-id="620f9-299">7</span><span class="sxs-lookup"><span data-stu-id="620f9-299">7</span></span>                      | <span data-ttu-id="620f9-300">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-300">x64</span></span> |
| <span data-ttu-id="620f9-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="620f9-301">Fedora</span></span>                         |  <span data-ttu-id="620f9-302">29, 30</span><span class="sxs-lookup"><span data-stu-id="620f9-302">29, 30</span></span>                 | <span data-ttu-id="620f9-303">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-303">x64</span></span> |
| <span data-ttu-id="620f9-304">Debian</span><span class="sxs-lookup"><span data-stu-id="620f9-304">Debian</span></span>                         |  <span data-ttu-id="620f9-305">9</span><span class="sxs-lookup"><span data-stu-id="620f9-305">9</span></span>                      | <span data-ttu-id="620f9-306">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-306">x64, ARM32</span></span> |
| <span data-ttu-id="620f9-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="620f9-307">Ubuntu</span></span>                         |  <span data-ttu-id="620f9-308">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="620f9-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="620f9-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-309">x64, ARM32</span></span> |
| <span data-ttu-id="620f9-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="620f9-310">Linux Mint</span></span>                     |  <span data-ttu-id="620f9-311">17, 18</span><span class="sxs-lookup"><span data-stu-id="620f9-311">17, 18</span></span>                 | <span data-ttu-id="620f9-312">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-312">x64</span></span> |
| <span data-ttu-id="620f9-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="620f9-313">openSUSE</span></span>                       |  <span data-ttu-id="620f9-314">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-314">15+</span></span>                    | <span data-ttu-id="620f9-315">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-315">x64</span></span> |
| <span data-ttu-id="620f9-316">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="620f9-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="620f9-317">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="620f9-317">12 SP2+</span></span>                | <span data-ttu-id="620f9-318">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-318">x64</span></span> |
| <span data-ttu-id="620f9-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-319">Alpine Linux</span></span>                   |  <span data-ttu-id="620f9-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="620f9-320">3.8+</span></span>                   | <span data-ttu-id="620f9-321">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-321">x64</span></span> |

<span data-ttu-id="620f9-322">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.2, vedere Versioni del sistema operativo supportate di [.NET Core 2.2.](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="620f9-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="620f9-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="620f9-324">.NET Core 2.1 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="620f9-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="620f9-325">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="620f9-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="620f9-326">.NET Core 2.1 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="620f9-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-327">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-328">OS</span><span class="sxs-lookup"><span data-stu-id="620f9-328">OS</span></span>                             |  <span data-ttu-id="620f9-329">Versione</span><span class="sxs-lookup"><span data-stu-id="620f9-329">Version</span></span>                |  <span data-ttu-id="620f9-330">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="620f9-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="620f9-332">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="620f9-332">6, 7, 8</span></span>                | <span data-ttu-id="620f9-333">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-333">x64</span></span> |
| <span data-ttu-id="620f9-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="620f9-334">CentOS</span></span>                         |  <span data-ttu-id="620f9-335">7+</span><span class="sxs-lookup"><span data-stu-id="620f9-335">7+</span></span>                     | <span data-ttu-id="620f9-336">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-336">x64</span></span> |
| <span data-ttu-id="620f9-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-337">Oracle Linux</span></span>                   |  <span data-ttu-id="620f9-338">7+</span><span class="sxs-lookup"><span data-stu-id="620f9-338">7+</span></span>                     | <span data-ttu-id="620f9-339">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-339">x64</span></span> |
| <span data-ttu-id="620f9-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="620f9-340">Fedora</span></span>                         |  <span data-ttu-id="620f9-341">Più di 30 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-341">30+</span></span>                    | <span data-ttu-id="620f9-342">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-342">x64</span></span> |
| <span data-ttu-id="620f9-343">Debian</span><span class="sxs-lookup"><span data-stu-id="620f9-343">Debian</span></span>                         |  <span data-ttu-id="620f9-344">9</span><span class="sxs-lookup"><span data-stu-id="620f9-344">9</span></span>                      | <span data-ttu-id="620f9-345">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-345">x64, ARM32</span></span> |
| <span data-ttu-id="620f9-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="620f9-346">Ubuntu</span></span>                         |  <span data-ttu-id="620f9-347">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="620f9-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="620f9-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="620f9-348">x64, ARM32</span></span> |
| <span data-ttu-id="620f9-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="620f9-349">Linux Mint</span></span>                     |  <span data-ttu-id="620f9-350">17+</span><span class="sxs-lookup"><span data-stu-id="620f9-350">17+</span></span>                    | <span data-ttu-id="620f9-351">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-351">x64</span></span> |
| <span data-ttu-id="620f9-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="620f9-352">openSUSE</span></span>                       |  <span data-ttu-id="620f9-353">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="620f9-353">15+</span></span>                    | <span data-ttu-id="620f9-354">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-354">x64</span></span> |
| <span data-ttu-id="620f9-355">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="620f9-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="620f9-356">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="620f9-356">12 SP2+</span></span>                | <span data-ttu-id="620f9-357">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-357">x64</span></span> |
| <span data-ttu-id="620f9-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-358">Alpine Linux</span></span>                   |  <span data-ttu-id="620f9-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="620f9-359">3.8+</span></span>                   | <span data-ttu-id="620f9-360">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-360">x64</span></span> |

<span data-ttu-id="620f9-361">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.1, vedere Versioni del sistema operativo supportate di [.NET Core 2.1.](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="620f9-362">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="620f9-362">Linux distribution dependencies</span></span>

<span data-ttu-id="620f9-363">In base alla distribuzione linux, potrebbe essere necessario installare dipendenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="620f9-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="620f9-364">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="620f9-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="620f9-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="620f9-365">Ubuntu</span></span>

<span data-ttu-id="620f9-366">Le distribuzioni Di Ubuntu richiedono l'installazione delle seguenti librerie:</span><span class="sxs-lookup"><span data-stu-id="620f9-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="620f9-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="620f9-367">liblttng-ust0</span></span>
- <span data-ttu-id="620f9-368">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="620f9-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="620f9-369">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="620f9-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="620f9-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="620f9-370">libssl1.0.0</span></span>
- <span data-ttu-id="620f9-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="620f9-371">libkrb5-3</span></span>
- <span data-ttu-id="620f9-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="620f9-372">zlib1g</span></span>
- <span data-ttu-id="620f9-373">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="620f9-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="620f9-374">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="620f9-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="620f9-375">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="620f9-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="620f9-376">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="620f9-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="620f9-377">Per le app .NET Core che usano l'assembly *System.Drawing.Common,* è necessaria anche la dipendenza seguente:For .NET Core apps that use the System.Drawing.Common assembly, you also need the following dependency:</span><span class="sxs-lookup"><span data-stu-id="620f9-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="620f9-378">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="620f9-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="620f9-379">La maggior parte delle versioni di Ubuntu includono una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="620f9-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="620f9-380">È possibile installare una versione recente di libgdiplus aggiungendo il repository Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="620f9-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="620f9-381">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="620f9-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="620f9-382">CentOS e Fedora</span><span class="sxs-lookup"><span data-stu-id="620f9-382">CentOS and Fedora</span></span>

<span data-ttu-id="620f9-383">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="620f9-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="620f9-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="620f9-384">lttng-ust</span></span>
- <span data-ttu-id="620f9-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="620f9-385">libcurl</span></span>
- <span data-ttu-id="620f9-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="620f9-386">openssl-libs</span></span>
- <span data-ttu-id="620f9-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="620f9-387">krb5-libs</span></span>
- <span data-ttu-id="620f9-388">libicu</span><span class="sxs-lookup"><span data-stu-id="620f9-388">libicu</span></span>
- <span data-ttu-id="620f9-389">zlib</span><span class="sxs-lookup"><span data-stu-id="620f9-389">zlib</span></span>

<span data-ttu-id="620f9-390">Utenti Fedora: se la versione di OpenSSL >1,1, dovrai installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="620f9-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="620f9-391">Per .NET Core 2.0, sono necessarie anche le dipendenze seguenti:For .NET Core 2.0, also the following dependencies are required:</span><span class="sxs-lookup"><span data-stu-id="620f9-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="620f9-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="620f9-392">libunwind</span></span>
- <span data-ttu-id="620f9-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="620f9-393">libuuid</span></span>

<span data-ttu-id="620f9-394">Per altre informazioni sulle dipendenze, vedere [App Linux autonome](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="620f9-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="620f9-395">Per le app .NET Core che usano l'assembly *System.Drawing.Common,* è inoltre necessaria la dipendenza seguente:For .NET Core apps that use the System.Drawing.Common assembly, you'll also need the following dependency:</span><span class="sxs-lookup"><span data-stu-id="620f9-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="620f9-396">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="620f9-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="620f9-397">La maggior parte delle versioni di CentOS e Fedora includono una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="620f9-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="620f9-398">È possibile installare una versione recente di libgdiplus aggiungendo il repository Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="620f9-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="620f9-399">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="620f9-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="620f9-400">.NET Core è supportato nelle seguenti versioni di macOS:</span><span class="sxs-lookup"><span data-stu-id="620f9-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="620f9-401">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="620f9-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="620f9-402">Versione .NET Core</span><span class="sxs-lookup"><span data-stu-id="620f9-402">.NET Core Version</span></span> | <span data-ttu-id="620f9-403">macOS</span><span class="sxs-lookup"><span data-stu-id="620f9-403">macOS</span></span>                 | <span data-ttu-id="620f9-404">Architetture</span><span class="sxs-lookup"><span data-stu-id="620f9-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="620f9-405">3.1</span><span class="sxs-lookup"><span data-stu-id="620f9-405">3.1</span></span>               | <span data-ttu-id="620f9-406">Alta Sierra (10.13)</span><span class="sxs-lookup"><span data-stu-id="620f9-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="620f9-407">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-407">x64</span></span> | [<span data-ttu-id="620f9-408">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="620f9-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="620f9-409">3.0</span><span class="sxs-lookup"><span data-stu-id="620f9-409">3.0</span></span>               | <span data-ttu-id="620f9-410">Alta Sierra (10.13)</span><span class="sxs-lookup"><span data-stu-id="620f9-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="620f9-411">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-411">x64</span></span> | [<span data-ttu-id="620f9-412">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="620f9-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="620f9-413">2.2</span><span class="sxs-lookup"><span data-stu-id="620f9-413">2.2</span></span>               | <span data-ttu-id="620f9-414">Sierra (10.12)</span><span class="sxs-lookup"><span data-stu-id="620f9-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="620f9-415">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-415">x64</span></span> | [<span data-ttu-id="620f9-416">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="620f9-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="620f9-417">2.1</span><span class="sxs-lookup"><span data-stu-id="620f9-417">2.1</span></span>               | <span data-ttu-id="620f9-418">Sierra (10.12)</span><span class="sxs-lookup"><span data-stu-id="620f9-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="620f9-419">x64</span><span class="sxs-lookup"><span data-stu-id="620f9-419">x64</span></span> | [<span data-ttu-id="620f9-420">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="620f9-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="620f9-421">A partire da macOS Catalina (versione 10.15), tutti i software creati dopo il 1 giugno 2019 distribuito con l'ID sviluppatore devono essere notarizzati.</span><span class="sxs-lookup"><span data-stu-id="620f9-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="620f9-422">Questo requisito si applica al runtime .NET Core, a .NET Core SDK e al software creato con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="620f9-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="620f9-423">I programmi di installazione per .NET Core (sia runtime che SDK) versioni 3.1, 3.0 e 2.1, sono stati notarizzati dal 18 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="620f9-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="620f9-424">Le versioni rilasciate precedenti non sono notificate.</span><span class="sxs-lookup"><span data-stu-id="620f9-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="620f9-425">Se esegui un'app non notarizzata, verrà visualizzato un errore simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="620f9-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![avviso di notarizzazione catalina macOS](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="620f9-427">Per altre informazioni su come la notarizzazione applicata influisce su .NET Core (e sulle app .NET Core), vedere [Utilizzo della notarizzazione catalina di macOS](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="620f9-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="620f9-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="620f9-428">libgdiplus</span></span>

<span data-ttu-id="620f9-429">Le applicazioni .NET Core che utilizzano l'assembly *System.Drawing.Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="620f9-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="620f9-430">Un modo semplice per ottenere libgdiplus consiste nell'utilizzare il gestore di pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS.</span><span class="sxs-lookup"><span data-stu-id="620f9-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="620f9-431">Dopo aver installato *brew*, installare libgdiplus eseguendo i seguenti comandi al prompt Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="620f9-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="620f9-432">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="620f9-432">Next steps</span></span>

- <span data-ttu-id="620f9-433">Per sviluppare ed eseguire app, installare [.NET Core SDK](sdk.md) (include il runtime).</span><span class="sxs-lookup"><span data-stu-id="620f9-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="620f9-434">Per eseguire le app create da altri, installare il [runtime di .NET Core.](runtime.md)</span><span class="sxs-lookup"><span data-stu-id="620f9-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
