---
title: Dipendenze di runtime e sdiche di .NET Core - .NET Core
description: Vengono descritti in dettaglio i prerequisiti del sistema operativo e dell'architettura della CPU per installare .NET Core SDK e runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157810"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="014e3-103">Dipendenze e requisiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="014e3-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="014e3-104">Questo articolo descrive in dettaglio quali sistemi operativi e architettura della CPU sono supportati da .NET Core.This article details which operating systems and CPU architecture are supported by .NET Core.</span><span class="sxs-lookup"><span data-stu-id="014e3-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="014e3-105">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="014e3-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="014e3-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="014e3-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="014e3-107">Le seguenti versioni di Windows sono supportate con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="014e3-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-108">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-109">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-109">OS</span></span>                            | <span data-ttu-id="014e3-110">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-110">Version</span></span>                        | <span data-ttu-id="014e3-111">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="014e3-112">Client Windows</span><span class="sxs-lookup"><span data-stu-id="014e3-112">Windows Client</span></span>                | <span data-ttu-id="014e3-113">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="014e3-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="014e3-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-114">x64, x86</span></span>        |
| <span data-ttu-id="014e3-115">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="014e3-115">Windows 10 Client</span></span>             | <span data-ttu-id="014e3-116">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="014e3-116">Version 1607+</span></span>                  | <span data-ttu-id="014e3-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-117">x64, x86</span></span>        |
| <span data-ttu-id="014e3-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="014e3-118">Windows Server</span></span>                | <span data-ttu-id="014e3-119">2012 R2</span><span class="sxs-lookup"><span data-stu-id="014e3-119">2012 R2+</span></span>                       | <span data-ttu-id="014e3-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-120">x64, x86</span></span>        |
| <span data-ttu-id="014e3-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="014e3-121">Nano Server</span></span>                   | <span data-ttu-id="014e3-122">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="014e3-122">Version 1803+</span></span>                  | <span data-ttu-id="014e3-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-123">x64, ARM32</span></span>      |

<span data-ttu-id="014e3-124">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.1, vedere Versioni del sistema operativo supportate di [.NET Core 3.1.](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="014e3-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="014e3-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="014e3-126">Le seguenti versioni di Windows sono supportate con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="014e3-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-127">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-128">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-128">OS</span></span>                            | <span data-ttu-id="014e3-129">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-129">Version</span></span>                        | <span data-ttu-id="014e3-130">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="014e3-131">Client Windows</span><span class="sxs-lookup"><span data-stu-id="014e3-131">Windows Client</span></span>                | <span data-ttu-id="014e3-132">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="014e3-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="014e3-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-133">x64, x86</span></span>        |
| <span data-ttu-id="014e3-134">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="014e3-134">Windows 10 Client</span></span>             | <span data-ttu-id="014e3-135">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="014e3-135">Version 1607+</span></span>                  | <span data-ttu-id="014e3-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-136">x64, x86</span></span>        |
| <span data-ttu-id="014e3-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="014e3-137">Windows Server</span></span>                | <span data-ttu-id="014e3-138">2012 R2</span><span class="sxs-lookup"><span data-stu-id="014e3-138">2012 R2+</span></span>                       | <span data-ttu-id="014e3-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-139">x64, x86</span></span>        |
| <span data-ttu-id="014e3-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="014e3-140">Nano Server</span></span>                   | <span data-ttu-id="014e3-141">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="014e3-141">Version 1803+</span></span>                  | <span data-ttu-id="014e3-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-142">x64, ARM32</span></span>      |

<span data-ttu-id="014e3-143">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.0, vedere Versioni del sistema operativo supportate di [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="014e3-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="014e3-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="014e3-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="014e3-145">Le seguenti versioni di Windows sono supportate con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="014e3-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-146">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-147">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-147">OS</span></span>                            | <span data-ttu-id="014e3-148">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-148">Version</span></span>                        | <span data-ttu-id="014e3-149">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="014e3-150">Client Windows</span><span class="sxs-lookup"><span data-stu-id="014e3-150">Windows Client</span></span>                | <span data-ttu-id="014e3-151">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="014e3-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="014e3-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-152">x64, x86</span></span>        |
| <span data-ttu-id="014e3-153">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="014e3-153">Windows 10 Client</span></span>             | <span data-ttu-id="014e3-154">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="014e3-154">Version 1607+</span></span>                  | <span data-ttu-id="014e3-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-155">x64, x86</span></span>        |
| <span data-ttu-id="014e3-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="014e3-156">Windows Server</span></span>                | <span data-ttu-id="014e3-157">2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="014e3-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="014e3-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-158">x64, x86</span></span>        |
| <span data-ttu-id="014e3-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="014e3-159">Nano Server</span></span>                   | <span data-ttu-id="014e3-160">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="014e3-160">Version 1803+</span></span>                   | <span data-ttu-id="014e3-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-161">x64, ARM32</span></span>      |

<span data-ttu-id="014e3-162">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.2, vedere Versioni del sistema operativo supportate di [.NET Core 2.2.](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="014e3-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="014e3-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="014e3-164">Le seguenti versioni di Windows sono supportate con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="014e3-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-165">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-166">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-166">OS</span></span>                            | <span data-ttu-id="014e3-167">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-167">Version</span></span>                        | <span data-ttu-id="014e3-168">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="014e3-169">Client Windows</span><span class="sxs-lookup"><span data-stu-id="014e3-169">Windows Client</span></span>                | <span data-ttu-id="014e3-170">7 SP1, 8,1</span><span class="sxs-lookup"><span data-stu-id="014e3-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="014e3-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-171">x64, x86</span></span>        |
| <span data-ttu-id="014e3-172">Windows 10 Client</span><span class="sxs-lookup"><span data-stu-id="014e3-172">Windows 10 Client</span></span>             | <span data-ttu-id="014e3-173">Versione 1607</span><span class="sxs-lookup"><span data-stu-id="014e3-173">Version 1607+</span></span>                  | <span data-ttu-id="014e3-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-174">x64, x86</span></span>        |
| <span data-ttu-id="014e3-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="014e3-175">Windows Server</span></span>                | <span data-ttu-id="014e3-176">2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="014e3-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="014e3-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="014e3-177">x64, x86</span></span>        |
| <span data-ttu-id="014e3-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="014e3-178">Nano Server</span></span>                   | <span data-ttu-id="014e3-179">Versione 1803</span><span class="sxs-lookup"><span data-stu-id="014e3-179">Version 1803+</span></span>                  | <span data-ttu-id="014e3-180">x64,</span><span class="sxs-lookup"><span data-stu-id="014e3-180">x64,</span></span>            |

<span data-ttu-id="014e3-181">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.1, vedere Versioni del sistema operativo supportate di [.NET Core 2.1.](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="014e3-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="014e3-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="014e3-183">Ulteriori dipendenze sono necessarie se si installa .NET SDK o runtime nelle seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="014e3-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="014e3-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="014e3-184">Windows 7 SP1</span></span>
- <span data-ttu-id="014e3-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="014e3-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="014e3-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="014e3-186">Windows 8.1</span></span>
- <span data-ttu-id="014e3-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="014e3-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="014e3-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="014e3-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="014e3-189">Installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="014e3-189">Install the following:</span></span>

- <span data-ttu-id="014e3-190">[Aggiornamento ridistribuibile 3](https://www.microsoft.com/download/details.aspx?id=52685)di Microsoft Visual C</span><span class="sxs-lookup"><span data-stu-id="014e3-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="014e3-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="014e3-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="014e3-192">I requisiti di cui sopra sono necessari anche se si verifica uno dei seguenti errori:</span><span class="sxs-lookup"><span data-stu-id="014e3-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="014e3-193">Impossibile avviare il programma perché *api-ms-win-crt-runtime-l1-1-0.dll* non è presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="014e3-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="014e3-194">Provare a reinstallare il programma per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="014e3-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="014e3-195">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="014e3-195">\- or -</span></span>
>
> <span data-ttu-id="014e3-196">La libreria *hostfxr.dll* è stata trovata, ma il caricamento da *C:\\\<path_to_app>hostfxr.dll \\* non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="014e3-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="014e3-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="014e3-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="014e3-198">.NET Core 3.1 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="014e3-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="014e3-199">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="014e3-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="014e3-200">.NET Core 3.1 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="014e3-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-201">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-202">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-202">OS</span></span>                             | <span data-ttu-id="014e3-203">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-203">Version</span></span>               | <span data-ttu-id="014e3-204">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="014e3-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="014e3-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="014e3-206">6, 7, 8</span></span>               | <span data-ttu-id="014e3-207">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-207">x64</span></span> |
| <span data-ttu-id="014e3-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="014e3-208">CentOS</span></span>                         | <span data-ttu-id="014e3-209">7+</span><span class="sxs-lookup"><span data-stu-id="014e3-209">7+</span></span>                    | <span data-ttu-id="014e3-210">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-210">x64</span></span> |
| <span data-ttu-id="014e3-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-211">Oracle Linux</span></span>                   | <span data-ttu-id="014e3-212">7+</span><span class="sxs-lookup"><span data-stu-id="014e3-212">7+</span></span>                    | <span data-ttu-id="014e3-213">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-213">x64</span></span> |
| <span data-ttu-id="014e3-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="014e3-214">Fedora</span></span>                         | <span data-ttu-id="014e3-215">Più di 29 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-215">29+</span></span>                   | <span data-ttu-id="014e3-216">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-216">x64</span></span> |
| <span data-ttu-id="014e3-217">Debian</span><span class="sxs-lookup"><span data-stu-id="014e3-217">Debian</span></span>                         | <span data-ttu-id="014e3-218">9+</span><span class="sxs-lookup"><span data-stu-id="014e3-218">9+</span></span>                    | <span data-ttu-id="014e3-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="014e3-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="014e3-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="014e3-220">Ubuntu</span></span>                         | <span data-ttu-id="014e3-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="014e3-221">16.04+</span></span>                | <span data-ttu-id="014e3-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="014e3-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="014e3-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="014e3-223">Linux Mint</span></span>                     | <span data-ttu-id="014e3-224">PIÙ di 18 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-224">18+</span></span>                   | <span data-ttu-id="014e3-225">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-225">x64</span></span> |
| <span data-ttu-id="014e3-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="014e3-226">openSUSE</span></span>                       | <span data-ttu-id="014e3-227">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-227">15+</span></span>                   | <span data-ttu-id="014e3-228">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-228">x64</span></span> |
| <span data-ttu-id="014e3-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="014e3-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="014e3-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="014e3-230">12 SP2+</span></span>               | <span data-ttu-id="014e3-231">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-231">x64</span></span> |
| <span data-ttu-id="014e3-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-232">Alpine Linux</span></span>                   | <span data-ttu-id="014e3-233">3.10 o più</span><span class="sxs-lookup"><span data-stu-id="014e3-233">3.10+</span></span>                 | <span data-ttu-id="014e3-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="014e3-234">x64, ARM64</span></span> |

<span data-ttu-id="014e3-235">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.1, vedere Versioni del sistema operativo supportate di [.NET Core 3.1.](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="014e3-236">Per ulteriori informazioni su come installare .NET Core 3.1 in ARM64 (kernel 4.14), vedere Installazione di [.NET Core 3.0 su Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="014e3-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="014e3-237">Il supporto ARM64 richiede kernel Linux 4.14 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="014e3-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="014e3-238">Alcune distribuzioni linux soddisfano questo requisito, mentre altre no.</span><span class="sxs-lookup"><span data-stu-id="014e3-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="014e3-239">Ad esempio, Ubuntu 18.04 è supportato, ma Ubuntu 16.04 non lo è.</span><span class="sxs-lookup"><span data-stu-id="014e3-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="014e3-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="014e3-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="014e3-241">.NET Core 3.0 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="014e3-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="014e3-242">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="014e3-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="014e3-243">.NET Core 3.0 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="014e3-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-244">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-245">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-245">OS</span></span>                             | <span data-ttu-id="014e3-246">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-246">Version</span></span>               | <span data-ttu-id="014e3-247">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="014e3-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="014e3-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="014e3-249">6, 7, 8</span></span>               | <span data-ttu-id="014e3-250">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-250">x64</span></span> |
| <span data-ttu-id="014e3-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="014e3-251">CentOS</span></span>                         | <span data-ttu-id="014e3-252">7+</span><span class="sxs-lookup"><span data-stu-id="014e3-252">7+</span></span>                    | <span data-ttu-id="014e3-253">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-253">x64</span></span> |
| <span data-ttu-id="014e3-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-254">Oracle Linux</span></span>                   | <span data-ttu-id="014e3-255">7+</span><span class="sxs-lookup"><span data-stu-id="014e3-255">7+</span></span>                    | <span data-ttu-id="014e3-256">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-256">x64</span></span> |
| <span data-ttu-id="014e3-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="014e3-257">Fedora</span></span>                         | <span data-ttu-id="014e3-258">Più di 29 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-258">29+</span></span>                   | <span data-ttu-id="014e3-259">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-259">x64</span></span> |
| <span data-ttu-id="014e3-260">Debian</span><span class="sxs-lookup"><span data-stu-id="014e3-260">Debian</span></span>                         | <span data-ttu-id="014e3-261">9+</span><span class="sxs-lookup"><span data-stu-id="014e3-261">9+</span></span>                    | <span data-ttu-id="014e3-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="014e3-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="014e3-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="014e3-263">Ubuntu</span></span>                         | <span data-ttu-id="014e3-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="014e3-264">16.04+</span></span>                | <span data-ttu-id="014e3-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="014e3-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="014e3-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="014e3-266">Linux Mint</span></span>                     | <span data-ttu-id="014e3-267">PIÙ di 18 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-267">18+</span></span>                   | <span data-ttu-id="014e3-268">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-268">x64</span></span> |
| <span data-ttu-id="014e3-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="014e3-269">openSUSE</span></span>                       | <span data-ttu-id="014e3-270">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-270">15+</span></span>                   | <span data-ttu-id="014e3-271">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-271">x64</span></span> |
| <span data-ttu-id="014e3-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="014e3-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="014e3-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="014e3-273">12 SP2+</span></span>               | <span data-ttu-id="014e3-274">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-274">x64</span></span> |
| <span data-ttu-id="014e3-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-275">Alpine Linux</span></span>                   | <span data-ttu-id="014e3-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="014e3-276">3.8+</span></span>                  | <span data-ttu-id="014e3-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="014e3-277">x64, ARM64</span></span> |

<span data-ttu-id="014e3-278">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.0, vedere Versioni del sistema operativo supportate di [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="014e3-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="014e3-279">Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="014e3-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="014e3-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="014e3-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="014e3-281">.NET Core 2.2 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="014e3-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="014e3-282">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="014e3-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="014e3-283">.NET Core 2.2 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="014e3-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-284">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-285">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-285">OS</span></span>                             |  <span data-ttu-id="014e3-286">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-286">Version</span></span>                |  <span data-ttu-id="014e3-287">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="014e3-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="014e3-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="014e3-289">6, 7</span></span>                   | <span data-ttu-id="014e3-290">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-290">x64</span></span> |
| <span data-ttu-id="014e3-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="014e3-291">CentOS</span></span>                         |  <span data-ttu-id="014e3-292">7</span><span class="sxs-lookup"><span data-stu-id="014e3-292">7</span></span>                      | <span data-ttu-id="014e3-293">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-293">x64</span></span> |
| <span data-ttu-id="014e3-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-294">Oracle Linux</span></span>                   |  <span data-ttu-id="014e3-295">7</span><span class="sxs-lookup"><span data-stu-id="014e3-295">7</span></span>                      | <span data-ttu-id="014e3-296">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-296">x64</span></span> |
| <span data-ttu-id="014e3-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="014e3-297">Fedora</span></span>                         |  <span data-ttu-id="014e3-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="014e3-298">29, 30</span></span>                 | <span data-ttu-id="014e3-299">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-299">x64</span></span> |
| <span data-ttu-id="014e3-300">Debian</span><span class="sxs-lookup"><span data-stu-id="014e3-300">Debian</span></span>                         |  <span data-ttu-id="014e3-301">9</span><span class="sxs-lookup"><span data-stu-id="014e3-301">9</span></span>                      | <span data-ttu-id="014e3-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-302">x64, ARM32</span></span> |
| <span data-ttu-id="014e3-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="014e3-303">Ubuntu</span></span>                         |  <span data-ttu-id="014e3-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="014e3-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="014e3-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-305">x64, ARM32</span></span> |
| <span data-ttu-id="014e3-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="014e3-306">Linux Mint</span></span>                     |  <span data-ttu-id="014e3-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="014e3-307">17, 18</span></span>                 | <span data-ttu-id="014e3-308">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-308">x64</span></span> |
| <span data-ttu-id="014e3-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="014e3-309">openSUSE</span></span>                       |  <span data-ttu-id="014e3-310">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-310">15+</span></span>                    | <span data-ttu-id="014e3-311">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-311">x64</span></span> |
| <span data-ttu-id="014e3-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="014e3-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="014e3-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="014e3-313">12 SP2+</span></span>                | <span data-ttu-id="014e3-314">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-314">x64</span></span> |
| <span data-ttu-id="014e3-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-315">Alpine Linux</span></span>                   |  <span data-ttu-id="014e3-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="014e3-316">3.8+</span></span>                   | <span data-ttu-id="014e3-317">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-317">x64</span></span> |

<span data-ttu-id="014e3-318">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.2, vedere Versioni del sistema operativo supportate di [.NET Core 2.2.](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="014e3-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="014e3-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="014e3-320">.NET Core 2.1 considera Linux come un unico sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="014e3-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="014e3-321">Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="014e3-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="014e3-322">.NET Core 2.1 è supportato nelle seguenti distribuzioni/versioni Linux:</span><span class="sxs-lookup"><span data-stu-id="014e3-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-323">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-324">OS</span><span class="sxs-lookup"><span data-stu-id="014e3-324">OS</span></span>                             |  <span data-ttu-id="014e3-325">Versione</span><span class="sxs-lookup"><span data-stu-id="014e3-325">Version</span></span>                |  <span data-ttu-id="014e3-326">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="014e3-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="014e3-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="014e3-328">6, 7, 8</span></span>                | <span data-ttu-id="014e3-329">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-329">x64</span></span> |
| <span data-ttu-id="014e3-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="014e3-330">CentOS</span></span>                         |  <span data-ttu-id="014e3-331">7+</span><span class="sxs-lookup"><span data-stu-id="014e3-331">7+</span></span>                     | <span data-ttu-id="014e3-332">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-332">x64</span></span> |
| <span data-ttu-id="014e3-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-333">Oracle Linux</span></span>                   |  <span data-ttu-id="014e3-334">7+</span><span class="sxs-lookup"><span data-stu-id="014e3-334">7+</span></span>                     | <span data-ttu-id="014e3-335">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-335">x64</span></span> |
| <span data-ttu-id="014e3-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="014e3-336">Fedora</span></span>                         |  <span data-ttu-id="014e3-337">Più di 29 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-337">29+</span></span>                    | <span data-ttu-id="014e3-338">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-338">x64</span></span> |
| <span data-ttu-id="014e3-339">Debian</span><span class="sxs-lookup"><span data-stu-id="014e3-339">Debian</span></span>                         |  <span data-ttu-id="014e3-340">9</span><span class="sxs-lookup"><span data-stu-id="014e3-340">9</span></span>                      | <span data-ttu-id="014e3-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-341">x64, ARM32</span></span> |
| <span data-ttu-id="014e3-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="014e3-342">Ubuntu</span></span>                         |  <span data-ttu-id="014e3-343">16.04, 18.04, 19.04, 19.10</span><span class="sxs-lookup"><span data-stu-id="014e3-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="014e3-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="014e3-344">x64, ARM32</span></span> |
| <span data-ttu-id="014e3-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="014e3-345">Linux Mint</span></span>                     |  <span data-ttu-id="014e3-346">17+</span><span class="sxs-lookup"><span data-stu-id="014e3-346">17+</span></span>                    | <span data-ttu-id="014e3-347">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-347">x64</span></span> |
| <span data-ttu-id="014e3-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="014e3-348">openSUSE</span></span>                       |  <span data-ttu-id="014e3-349">PIÙ di 15 anni</span><span class="sxs-lookup"><span data-stu-id="014e3-349">15+</span></span>                    | <span data-ttu-id="014e3-350">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-350">x64</span></span> |
| <span data-ttu-id="014e3-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="014e3-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="014e3-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="014e3-352">12 SP2+</span></span>                | <span data-ttu-id="014e3-353">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-353">x64</span></span> |
| <span data-ttu-id="014e3-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-354">Alpine Linux</span></span>                   |  <span data-ttu-id="014e3-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="014e3-355">3.8+</span></span>                   | <span data-ttu-id="014e3-356">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-356">x64</span></span> |

<span data-ttu-id="014e3-357">Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.1, vedere Versioni del sistema operativo supportate di [.NET Core 2.1.](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="014e3-358">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="014e3-358">Linux distribution dependencies</span></span>

<span data-ttu-id="014e3-359">In base alla distribuzione linux, potrebbe essere necessario installare dipendenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="014e3-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="014e3-360">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="014e3-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="014e3-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="014e3-361">Ubuntu</span></span>

<span data-ttu-id="014e3-362">Le distribuzioni Di Ubuntu richiedono l'installazione delle seguenti librerie:</span><span class="sxs-lookup"><span data-stu-id="014e3-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="014e3-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="014e3-363">liblttng-ust0</span></span>
- <span data-ttu-id="014e3-364">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="014e3-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="014e3-365">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="014e3-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="014e3-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="014e3-366">libssl1.0.0</span></span>
- <span data-ttu-id="014e3-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="014e3-367">libkrb5-3</span></span>
- <span data-ttu-id="014e3-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="014e3-368">zlib1g</span></span>
- <span data-ttu-id="014e3-369">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="014e3-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="014e3-370">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="014e3-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="014e3-371">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="014e3-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="014e3-372">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="014e3-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="014e3-373">Per le app .NET Core che usano l'assembly *System.Drawing.Common,* è necessaria anche la dipendenza seguente:For .NET Core apps that use the System.Drawing.Common assembly, you also need the following dependency:</span><span class="sxs-lookup"><span data-stu-id="014e3-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="014e3-374">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="014e3-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="014e3-375">La maggior parte delle versioni di Ubuntu includono una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="014e3-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="014e3-376">È possibile installare una versione recente di libgdiplus aggiungendo il repository Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="014e3-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="014e3-377">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="014e3-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="014e3-378">CentOS e Fedora</span><span class="sxs-lookup"><span data-stu-id="014e3-378">CentOS and Fedora</span></span>

<span data-ttu-id="014e3-379">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="014e3-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="014e3-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="014e3-380">lttng-ust</span></span>
- <span data-ttu-id="014e3-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="014e3-381">libcurl</span></span>
- <span data-ttu-id="014e3-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="014e3-382">openssl-libs</span></span>
- <span data-ttu-id="014e3-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="014e3-383">krb5-libs</span></span>
- <span data-ttu-id="014e3-384">libicu</span><span class="sxs-lookup"><span data-stu-id="014e3-384">libicu</span></span>
- <span data-ttu-id="014e3-385">zlib</span><span class="sxs-lookup"><span data-stu-id="014e3-385">zlib</span></span>

<span data-ttu-id="014e3-386">Utenti Fedora: se la versione di OpenSSL >1,1, dovrai installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="014e3-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="014e3-387">Per .NET Core 2.0, sono necessarie anche le dipendenze seguenti:For .NET Core 2.0, also the following dependencies are required:</span><span class="sxs-lookup"><span data-stu-id="014e3-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="014e3-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="014e3-388">libunwind</span></span>
- <span data-ttu-id="014e3-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="014e3-389">libuuid</span></span>

<span data-ttu-id="014e3-390">Per altre informazioni sulle dipendenze, vedere [App Linux autonome](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="014e3-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="014e3-391">Per le app .NET Core che usano l'assembly *System.Drawing.Common,* è inoltre necessaria la dipendenza seguente:For .NET Core apps that use the System.Drawing.Common assembly, you'll also need the following dependency:</span><span class="sxs-lookup"><span data-stu-id="014e3-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="014e3-392">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="014e3-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="014e3-393">La maggior parte delle versioni di CentOS e Fedora includono una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="014e3-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="014e3-394">È possibile installare una versione recente di libgdiplus aggiungendo il repository Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="014e3-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="014e3-395">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="014e3-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="014e3-396">.NET Core è supportato nelle seguenti versioni di macOS:</span><span class="sxs-lookup"><span data-stu-id="014e3-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="014e3-397">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="014e3-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="014e3-398">Versione .NET Core</span><span class="sxs-lookup"><span data-stu-id="014e3-398">.NET Core Version</span></span> | <span data-ttu-id="014e3-399">macOS</span><span class="sxs-lookup"><span data-stu-id="014e3-399">macOS</span></span>                 | <span data-ttu-id="014e3-400">Architetture</span><span class="sxs-lookup"><span data-stu-id="014e3-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="014e3-401">3.1</span><span class="sxs-lookup"><span data-stu-id="014e3-401">3.1</span></span>               | <span data-ttu-id="014e3-402">Alta Sierra (10.13)</span><span class="sxs-lookup"><span data-stu-id="014e3-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="014e3-403">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-403">x64</span></span> | [<span data-ttu-id="014e3-404">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="014e3-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="014e3-405">3.0</span><span class="sxs-lookup"><span data-stu-id="014e3-405">3.0</span></span>               | <span data-ttu-id="014e3-406">Alta Sierra (10.13)</span><span class="sxs-lookup"><span data-stu-id="014e3-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="014e3-407">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-407">x64</span></span> | [<span data-ttu-id="014e3-408">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="014e3-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="014e3-409">2.2</span><span class="sxs-lookup"><span data-stu-id="014e3-409">2.2</span></span>               | <span data-ttu-id="014e3-410">Sierra (10.12)</span><span class="sxs-lookup"><span data-stu-id="014e3-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="014e3-411">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-411">x64</span></span> | [<span data-ttu-id="014e3-412">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="014e3-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="014e3-413">2.1</span><span class="sxs-lookup"><span data-stu-id="014e3-413">2.1</span></span>               | <span data-ttu-id="014e3-414">Sierra (10.12)</span><span class="sxs-lookup"><span data-stu-id="014e3-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="014e3-415">x64</span><span class="sxs-lookup"><span data-stu-id="014e3-415">x64</span></span> | [<span data-ttu-id="014e3-416">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="014e3-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="014e3-417">A partire da macOS Catalina (versione 10.15), tutti i software creati dopo il 1 giugno 2019 distribuito con l'ID sviluppatore devono essere notarizzati.</span><span class="sxs-lookup"><span data-stu-id="014e3-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="014e3-418">Questo requisito si applica al runtime .NET Core, a .NET Core SDK e al software creato con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="014e3-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="014e3-419">I programmi di installazione per .NET Core (sia runtime che SDK) versioni 3.1, 3.0 e 2.1, sono stati notarizzati dal 18 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="014e3-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="014e3-420">Le versioni rilasciate precedenti non sono notificate.</span><span class="sxs-lookup"><span data-stu-id="014e3-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="014e3-421">Se esegui un'app non notarizzata, verrà visualizzato un errore simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="014e3-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![avviso di notarizzazione catalina macOS](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="014e3-423">Per altre informazioni su come la notarizzazione applicata influisce su .NET Core (e sulle app .NET Core), vedere [Utilizzo della notarizzazione catalina di macOS](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="014e3-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="014e3-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="014e3-424">libgdiplus</span></span>

<span data-ttu-id="014e3-425">Le applicazioni .NET Core che utilizzano l'assembly *System.Drawing.Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="014e3-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="014e3-426">Un modo semplice per ottenere libgdiplus consiste nell'utilizzare il gestore di pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS.</span><span class="sxs-lookup"><span data-stu-id="014e3-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="014e3-427">Dopo aver installato *brew*, installare libgdiplus eseguendo i seguenti comandi al prompt Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="014e3-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="014e3-428">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="014e3-428">Next steps</span></span>

- <span data-ttu-id="014e3-429">Per sviluppare ed eseguire app, installare [.NET Core SDK](sdk.md) (include il runtime).</span><span class="sxs-lookup"><span data-stu-id="014e3-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="014e3-430">Per eseguire le app create da altri, installare il [runtime di .NET Core.](runtime.md)</span><span class="sxs-lookup"><span data-stu-id="014e3-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
