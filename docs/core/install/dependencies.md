---
title: Dipendenze di .NET Core SDK e Runtime-.NET Core
description: Informazioni dettagliate sui prerequisiti per l'architettura del sistema operativo e della CPU per installare il .NET Core SDK e il runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157810"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="6a575-103">Dipendenze e requisiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a575-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="6a575-104">In questo articolo vengono illustrati i sistemi operativi e l'architettura della CPU supportati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a575-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="6a575-105">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="6a575-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="6a575-106">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="6a575-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="6a575-107">Con .NET Core 3,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="6a575-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-108">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-109">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-109">OS</span></span>                            | <span data-ttu-id="6a575-110">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-110">Version</span></span>                        | <span data-ttu-id="6a575-111">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6a575-112">Client Windows</span><span class="sxs-lookup"><span data-stu-id="6a575-112">Windows Client</span></span>                | <span data-ttu-id="6a575-113">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="6a575-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6a575-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-114">x64, x86</span></span>        |
| <span data-ttu-id="6a575-115">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="6a575-115">Windows 10 Client</span></span>             | <span data-ttu-id="6a575-116">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="6a575-116">Version 1607+</span></span>                  | <span data-ttu-id="6a575-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-117">x64, x86</span></span>        |
| <span data-ttu-id="6a575-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6a575-118">Windows Server</span></span>                | <span data-ttu-id="6a575-119">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="6a575-119">2012 R2+</span></span>                       | <span data-ttu-id="6a575-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-120">x64, x86</span></span>        |
| <span data-ttu-id="6a575-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6a575-121">Nano Server</span></span>                   | <span data-ttu-id="6a575-122">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="6a575-122">Version 1803+</span></span>                  | <span data-ttu-id="6a575-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-123">x64, ARM32</span></span>      |

<span data-ttu-id="6a575-124">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="6a575-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6a575-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="6a575-126">Con .NET Core 3,0 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="6a575-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-127">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-128">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-128">OS</span></span>                            | <span data-ttu-id="6a575-129">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-129">Version</span></span>                        | <span data-ttu-id="6a575-130">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6a575-131">Client Windows</span><span class="sxs-lookup"><span data-stu-id="6a575-131">Windows Client</span></span>                | <span data-ttu-id="6a575-132">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="6a575-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6a575-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-133">x64, x86</span></span>        |
| <span data-ttu-id="6a575-134">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="6a575-134">Windows 10 Client</span></span>             | <span data-ttu-id="6a575-135">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="6a575-135">Version 1607+</span></span>                  | <span data-ttu-id="6a575-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-136">x64, x86</span></span>        |
| <span data-ttu-id="6a575-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6a575-137">Windows Server</span></span>                | <span data-ttu-id="6a575-138">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="6a575-138">2012 R2+</span></span>                       | <span data-ttu-id="6a575-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-139">x64, x86</span></span>        |
| <span data-ttu-id="6a575-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6a575-140">Nano Server</span></span>                   | <span data-ttu-id="6a575-141">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="6a575-141">Version 1803+</span></span>                  | <span data-ttu-id="6a575-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-142">x64, ARM32</span></span>      |

<span data-ttu-id="6a575-143">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="6a575-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6a575-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6a575-145">Con .NET Core 2,2 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="6a575-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-146">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-147">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-147">OS</span></span>                            | <span data-ttu-id="6a575-148">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-148">Version</span></span>                        | <span data-ttu-id="6a575-149">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6a575-150">Client Windows</span><span class="sxs-lookup"><span data-stu-id="6a575-150">Windows Client</span></span>                | <span data-ttu-id="6a575-151">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="6a575-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6a575-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-152">x64, x86</span></span>        |
| <span data-ttu-id="6a575-153">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="6a575-153">Windows 10 Client</span></span>             | <span data-ttu-id="6a575-154">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="6a575-154">Version 1607+</span></span>                  | <span data-ttu-id="6a575-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-155">x64, x86</span></span>        |
| <span data-ttu-id="6a575-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6a575-156">Windows Server</span></span>                | <span data-ttu-id="6a575-157">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="6a575-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="6a575-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-158">x64, x86</span></span>        |
| <span data-ttu-id="6a575-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6a575-159">Nano Server</span></span>                   | <span data-ttu-id="6a575-160">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="6a575-160">Version 1803+</span></span>                   | <span data-ttu-id="6a575-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-161">x64, ARM32</span></span>      |

<span data-ttu-id="6a575-162">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="6a575-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6a575-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6a575-164">Con .NET Core 2,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="6a575-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-165">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-166">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-166">OS</span></span>                            | <span data-ttu-id="6a575-167">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-167">Version</span></span>                        | <span data-ttu-id="6a575-168">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6a575-169">Client Windows</span><span class="sxs-lookup"><span data-stu-id="6a575-169">Windows Client</span></span>                | <span data-ttu-id="6a575-170">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="6a575-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6a575-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-171">x64, x86</span></span>        |
| <span data-ttu-id="6a575-172">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="6a575-172">Windows 10 Client</span></span>             | <span data-ttu-id="6a575-173">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="6a575-173">Version 1607+</span></span>                  | <span data-ttu-id="6a575-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-174">x64, x86</span></span>        |
| <span data-ttu-id="6a575-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6a575-175">Windows Server</span></span>                | <span data-ttu-id="6a575-176">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="6a575-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="6a575-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6a575-177">x64, x86</span></span>        |
| <span data-ttu-id="6a575-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6a575-178">Nano Server</span></span>                   | <span data-ttu-id="6a575-179">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="6a575-179">Version 1803+</span></span>                  | <span data-ttu-id="6a575-180">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-180">x64,</span></span>            |

<span data-ttu-id="6a575-181">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="6a575-182">Windows 7/Vista/8,1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6a575-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="6a575-183">Sono necessarie dipendenze aggiuntive se si sta installando .NET SDK o Runtime nelle versioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="6a575-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="6a575-184">Windows 7 SP1</span></span>
- <span data-ttu-id="6a575-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="6a575-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="6a575-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6a575-186">Windows 8.1</span></span>
- <span data-ttu-id="6a575-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6a575-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="6a575-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6a575-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="6a575-189">Installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-189">Install the following:</span></span>

- <span data-ttu-id="6a575-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="6a575-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="6a575-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="6a575-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="6a575-192">I requisiti indicati sopra sono necessari anche se si verifica uno degli errori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="6a575-193">Non è possibile avviare il programma perché non è presente alcuna *API-MS-Win-CRT-Runtime-L1-1-0. dll* nel computer.</span><span class="sxs-lookup"><span data-stu-id="6a575-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="6a575-194">Per risolvere il problema, provare a reinstallare il programma.</span><span class="sxs-lookup"><span data-stu-id="6a575-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="6a575-195">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="6a575-195">\- or -</span></span>
>
> <span data-ttu-id="6a575-196">La libreria *hostfxr. dll* è stata trovata, ma il caricamento da *C:\\\<path_to_app >\\hostfxr. dll* non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6a575-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="6a575-197">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="6a575-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="6a575-198">.NET Core 3,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6a575-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="6a575-199">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="6a575-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6a575-200">.NET Core 3,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="6a575-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-201">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-202">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-202">OS</span></span>                             | <span data-ttu-id="6a575-203">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-203">Version</span></span>               | <span data-ttu-id="6a575-204">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="6a575-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="6a575-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="6a575-206">6, 7, 8</span></span>               | <span data-ttu-id="6a575-207">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-207">x64</span></span> |
| <span data-ttu-id="6a575-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="6a575-208">CentOS</span></span>                         | <span data-ttu-id="6a575-209">7+</span><span class="sxs-lookup"><span data-stu-id="6a575-209">7+</span></span>                    | <span data-ttu-id="6a575-210">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-210">x64</span></span> |
| <span data-ttu-id="6a575-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-211">Oracle Linux</span></span>                   | <span data-ttu-id="6a575-212">7+</span><span class="sxs-lookup"><span data-stu-id="6a575-212">7+</span></span>                    | <span data-ttu-id="6a575-213">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-213">x64</span></span> |
| <span data-ttu-id="6a575-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="6a575-214">Fedora</span></span>                         | <span data-ttu-id="6a575-215">29 +</span><span class="sxs-lookup"><span data-stu-id="6a575-215">29+</span></span>                   | <span data-ttu-id="6a575-216">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-216">x64</span></span> |
| <span data-ttu-id="6a575-217">Debian</span><span class="sxs-lookup"><span data-stu-id="6a575-217">Debian</span></span>                         | <span data-ttu-id="6a575-218">9+</span><span class="sxs-lookup"><span data-stu-id="6a575-218">9+</span></span>                    | <span data-ttu-id="6a575-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6a575-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6a575-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6a575-220">Ubuntu</span></span>                         | <span data-ttu-id="6a575-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="6a575-221">16.04+</span></span>                | <span data-ttu-id="6a575-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6a575-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6a575-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6a575-223">Linux Mint</span></span>                     | <span data-ttu-id="6a575-224">18 +</span><span class="sxs-lookup"><span data-stu-id="6a575-224">18+</span></span>                   | <span data-ttu-id="6a575-225">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-225">x64</span></span> |
| <span data-ttu-id="6a575-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6a575-226">openSUSE</span></span>                       | <span data-ttu-id="6a575-227">15 +</span><span class="sxs-lookup"><span data-stu-id="6a575-227">15+</span></span>                   | <span data-ttu-id="6a575-228">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-228">x64</span></span> |
| <span data-ttu-id="6a575-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6a575-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="6a575-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6a575-230">12 SP2+</span></span>               | <span data-ttu-id="6a575-231">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-231">x64</span></span> |
| <span data-ttu-id="6a575-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-232">Alpine Linux</span></span>                   | <span data-ttu-id="6a575-233">3.10 +</span><span class="sxs-lookup"><span data-stu-id="6a575-233">3.10+</span></span>                 | <span data-ttu-id="6a575-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="6a575-234">x64, ARM64</span></span> |

<span data-ttu-id="6a575-235">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="6a575-236">Per altre informazioni su come installare .NET Core 3,1 in ARM64 (kernel 4.14 +), vedere [installazione di .net core 3,0 in Linux arm64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="6a575-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a575-237">Il supporto di ARM64 richiede il kernel Linux 4,14 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="6a575-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="6a575-238">Alcune distribuzioni Linux soddisfano questo requisito mentre altre no.</span><span class="sxs-lookup"><span data-stu-id="6a575-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="6a575-239">Ubuntu 18,04, ad esempio, è supportato, ma Ubuntu 16,04 non lo è.</span><span class="sxs-lookup"><span data-stu-id="6a575-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="6a575-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6a575-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="6a575-241">.NET Core 3,0 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6a575-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="6a575-242">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="6a575-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6a575-243">.NET Core 3,0 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="6a575-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-244">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-245">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-245">OS</span></span>                             | <span data-ttu-id="6a575-246">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-246">Version</span></span>               | <span data-ttu-id="6a575-247">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="6a575-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="6a575-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="6a575-249">6, 7, 8</span></span>               | <span data-ttu-id="6a575-250">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-250">x64</span></span> |
| <span data-ttu-id="6a575-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="6a575-251">CentOS</span></span>                         | <span data-ttu-id="6a575-252">7+</span><span class="sxs-lookup"><span data-stu-id="6a575-252">7+</span></span>                    | <span data-ttu-id="6a575-253">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-253">x64</span></span> |
| <span data-ttu-id="6a575-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-254">Oracle Linux</span></span>                   | <span data-ttu-id="6a575-255">7+</span><span class="sxs-lookup"><span data-stu-id="6a575-255">7+</span></span>                    | <span data-ttu-id="6a575-256">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-256">x64</span></span> |
| <span data-ttu-id="6a575-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="6a575-257">Fedora</span></span>                         | <span data-ttu-id="6a575-258">29 +</span><span class="sxs-lookup"><span data-stu-id="6a575-258">29+</span></span>                   | <span data-ttu-id="6a575-259">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-259">x64</span></span> |
| <span data-ttu-id="6a575-260">Debian</span><span class="sxs-lookup"><span data-stu-id="6a575-260">Debian</span></span>                         | <span data-ttu-id="6a575-261">9+</span><span class="sxs-lookup"><span data-stu-id="6a575-261">9+</span></span>                    | <span data-ttu-id="6a575-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6a575-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6a575-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6a575-263">Ubuntu</span></span>                         | <span data-ttu-id="6a575-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="6a575-264">16.04+</span></span>                | <span data-ttu-id="6a575-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6a575-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6a575-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6a575-266">Linux Mint</span></span>                     | <span data-ttu-id="6a575-267">18 +</span><span class="sxs-lookup"><span data-stu-id="6a575-267">18+</span></span>                   | <span data-ttu-id="6a575-268">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-268">x64</span></span> |
| <span data-ttu-id="6a575-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6a575-269">openSUSE</span></span>                       | <span data-ttu-id="6a575-270">15 +</span><span class="sxs-lookup"><span data-stu-id="6a575-270">15+</span></span>                   | <span data-ttu-id="6a575-271">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-271">x64</span></span> |
| <span data-ttu-id="6a575-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6a575-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="6a575-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6a575-273">12 SP2+</span></span>               | <span data-ttu-id="6a575-274">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-274">x64</span></span> |
| <span data-ttu-id="6a575-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-275">Alpine Linux</span></span>                   | <span data-ttu-id="6a575-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="6a575-276">3.8+</span></span>                  | <span data-ttu-id="6a575-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="6a575-277">x64, ARM64</span></span> |

<span data-ttu-id="6a575-278">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="6a575-279">Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="6a575-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="6a575-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6a575-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6a575-281">.NET Core 2,2 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6a575-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="6a575-282">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="6a575-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6a575-283">.NET Core 2,2 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="6a575-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-284">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-285">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-285">OS</span></span>                             |  <span data-ttu-id="6a575-286">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-286">Version</span></span>                |  <span data-ttu-id="6a575-287">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="6a575-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="6a575-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="6a575-289">6, 7</span></span>                   | <span data-ttu-id="6a575-290">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-290">x64</span></span> |
| <span data-ttu-id="6a575-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="6a575-291">CentOS</span></span>                         |  <span data-ttu-id="6a575-292">7</span><span class="sxs-lookup"><span data-stu-id="6a575-292">7</span></span>                      | <span data-ttu-id="6a575-293">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-293">x64</span></span> |
| <span data-ttu-id="6a575-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-294">Oracle Linux</span></span>                   |  <span data-ttu-id="6a575-295">7</span><span class="sxs-lookup"><span data-stu-id="6a575-295">7</span></span>                      | <span data-ttu-id="6a575-296">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-296">x64</span></span> |
| <span data-ttu-id="6a575-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="6a575-297">Fedora</span></span>                         |  <span data-ttu-id="6a575-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="6a575-298">29, 30</span></span>                 | <span data-ttu-id="6a575-299">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-299">x64</span></span> |
| <span data-ttu-id="6a575-300">Debian</span><span class="sxs-lookup"><span data-stu-id="6a575-300">Debian</span></span>                         |  <span data-ttu-id="6a575-301">9</span><span class="sxs-lookup"><span data-stu-id="6a575-301">9</span></span>                      | <span data-ttu-id="6a575-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-302">x64, ARM32</span></span> |
| <span data-ttu-id="6a575-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6a575-303">Ubuntu</span></span>                         |  <span data-ttu-id="6a575-304">16,04, 18,04, 18,10</span><span class="sxs-lookup"><span data-stu-id="6a575-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="6a575-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-305">x64, ARM32</span></span> |
| <span data-ttu-id="6a575-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6a575-306">Linux Mint</span></span>                     |  <span data-ttu-id="6a575-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="6a575-307">17, 18</span></span>                 | <span data-ttu-id="6a575-308">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-308">x64</span></span> |
| <span data-ttu-id="6a575-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6a575-309">openSUSE</span></span>                       |  <span data-ttu-id="6a575-310">15 +</span><span class="sxs-lookup"><span data-stu-id="6a575-310">15+</span></span>                    | <span data-ttu-id="6a575-311">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-311">x64</span></span> |
| <span data-ttu-id="6a575-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6a575-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="6a575-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6a575-313">12 SP2+</span></span>                | <span data-ttu-id="6a575-314">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-314">x64</span></span> |
| <span data-ttu-id="6a575-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-315">Alpine Linux</span></span>                   |  <span data-ttu-id="6a575-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="6a575-316">3.8+</span></span>                   | <span data-ttu-id="6a575-317">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-317">x64</span></span> |

<span data-ttu-id="6a575-318">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="6a575-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6a575-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6a575-320">.NET Core 2,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6a575-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="6a575-321">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="6a575-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6a575-322">.NET Core 2,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="6a575-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-323">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-324">OS</span><span class="sxs-lookup"><span data-stu-id="6a575-324">OS</span></span>                             |  <span data-ttu-id="6a575-325">Versione</span><span class="sxs-lookup"><span data-stu-id="6a575-325">Version</span></span>                |  <span data-ttu-id="6a575-326">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="6a575-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="6a575-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="6a575-328">6, 7, 8</span></span>                | <span data-ttu-id="6a575-329">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-329">x64</span></span> |
| <span data-ttu-id="6a575-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="6a575-330">CentOS</span></span>                         |  <span data-ttu-id="6a575-331">7+</span><span class="sxs-lookup"><span data-stu-id="6a575-331">7+</span></span>                     | <span data-ttu-id="6a575-332">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-332">x64</span></span> |
| <span data-ttu-id="6a575-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-333">Oracle Linux</span></span>                   |  <span data-ttu-id="6a575-334">7+</span><span class="sxs-lookup"><span data-stu-id="6a575-334">7+</span></span>                     | <span data-ttu-id="6a575-335">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-335">x64</span></span> |
| <span data-ttu-id="6a575-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="6a575-336">Fedora</span></span>                         |  <span data-ttu-id="6a575-337">29 +</span><span class="sxs-lookup"><span data-stu-id="6a575-337">29+</span></span>                    | <span data-ttu-id="6a575-338">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-338">x64</span></span> |
| <span data-ttu-id="6a575-339">Debian</span><span class="sxs-lookup"><span data-stu-id="6a575-339">Debian</span></span>                         |  <span data-ttu-id="6a575-340">9</span><span class="sxs-lookup"><span data-stu-id="6a575-340">9</span></span>                      | <span data-ttu-id="6a575-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-341">x64, ARM32</span></span> |
| <span data-ttu-id="6a575-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6a575-342">Ubuntu</span></span>                         |  <span data-ttu-id="6a575-343">16,04, 18,04, 19,04, 19,10</span><span class="sxs-lookup"><span data-stu-id="6a575-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="6a575-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6a575-344">x64, ARM32</span></span> |
| <span data-ttu-id="6a575-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6a575-345">Linux Mint</span></span>                     |  <span data-ttu-id="6a575-346">17+</span><span class="sxs-lookup"><span data-stu-id="6a575-346">17+</span></span>                    | <span data-ttu-id="6a575-347">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-347">x64</span></span> |
| <span data-ttu-id="6a575-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6a575-348">openSUSE</span></span>                       |  <span data-ttu-id="6a575-349">15 +</span><span class="sxs-lookup"><span data-stu-id="6a575-349">15+</span></span>                    | <span data-ttu-id="6a575-350">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-350">x64</span></span> |
| <span data-ttu-id="6a575-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6a575-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="6a575-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6a575-352">12 SP2+</span></span>                | <span data-ttu-id="6a575-353">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-353">x64</span></span> |
| <span data-ttu-id="6a575-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-354">Alpine Linux</span></span>                   |  <span data-ttu-id="6a575-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="6a575-355">3.8+</span></span>                   | <span data-ttu-id="6a575-356">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-356">x64</span></span> |

<span data-ttu-id="6a575-357">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="6a575-358">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="6a575-358">Linux distribution dependencies</span></span>

<span data-ttu-id="6a575-359">In base alla distribuzione Linux, potrebbe essere necessario installare dipendenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6a575-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a575-360">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="6a575-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="6a575-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6a575-361">Ubuntu</span></span>

<span data-ttu-id="6a575-362">Per le distribuzioni di Ubuntu è necessario installare le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="6a575-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="6a575-363">liblttng-ust0</span></span>
- <span data-ttu-id="6a575-364">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="6a575-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="6a575-365">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="6a575-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="6a575-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="6a575-366">libssl1.0.0</span></span>
- <span data-ttu-id="6a575-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="6a575-367">libkrb5-3</span></span>
- <span data-ttu-id="6a575-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="6a575-368">zlib1g</span></span>
- <span data-ttu-id="6a575-369">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="6a575-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="6a575-370">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="6a575-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="6a575-371">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="6a575-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="6a575-372">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="6a575-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="6a575-373">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="6a575-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="6a575-374">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="6a575-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="6a575-375">La maggior parte delle versioni di Ubuntu include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="6a575-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="6a575-376">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="6a575-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="6a575-377">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="6a575-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="6a575-378">CentOS e Fedora</span><span class="sxs-lookup"><span data-stu-id="6a575-378">CentOS and Fedora</span></span>

<span data-ttu-id="6a575-379">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="6a575-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="6a575-380">lttng-ust</span></span>
- <span data-ttu-id="6a575-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="6a575-381">libcurl</span></span>
- <span data-ttu-id="6a575-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="6a575-382">openssl-libs</span></span>
- <span data-ttu-id="6a575-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="6a575-383">krb5-libs</span></span>
- <span data-ttu-id="6a575-384">libicu</span><span class="sxs-lookup"><span data-stu-id="6a575-384">libicu</span></span>
- <span data-ttu-id="6a575-385">zlib</span><span class="sxs-lookup"><span data-stu-id="6a575-385">zlib</span></span>

<span data-ttu-id="6a575-386">Utenti Fedora: se la versione di OpenSSL > = 1,1, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="6a575-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="6a575-387">Per .NET Core 2,0, sono necessarie anche le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="6a575-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="6a575-388">libunwind</span></span>
- <span data-ttu-id="6a575-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="6a575-389">libuuid</span></span>

<span data-ttu-id="6a575-390">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="6a575-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="6a575-391">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="6a575-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="6a575-392">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="6a575-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="6a575-393">La maggior parte delle versioni di CentOS e Fedora include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="6a575-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="6a575-394">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="6a575-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="6a575-395">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="6a575-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="6a575-396">.NET Core è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a575-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="6a575-397">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="6a575-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6a575-398">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a575-398">.NET Core Version</span></span> | <span data-ttu-id="6a575-399">macOS</span><span class="sxs-lookup"><span data-stu-id="6a575-399">macOS</span></span>                 | <span data-ttu-id="6a575-400">Architetture</span><span class="sxs-lookup"><span data-stu-id="6a575-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="6a575-401">3.1</span><span class="sxs-lookup"><span data-stu-id="6a575-401">3.1</span></span>               | <span data-ttu-id="6a575-402">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="6a575-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="6a575-403">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-403">x64</span></span> | [<span data-ttu-id="6a575-404">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6a575-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="6a575-405">3.0</span><span class="sxs-lookup"><span data-stu-id="6a575-405">3.0</span></span>               | <span data-ttu-id="6a575-406">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="6a575-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="6a575-407">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-407">x64</span></span> | [<span data-ttu-id="6a575-408">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6a575-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="6a575-409">2.2</span><span class="sxs-lookup"><span data-stu-id="6a575-409">2.2</span></span>               | <span data-ttu-id="6a575-410">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="6a575-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="6a575-411">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-411">x64</span></span> | [<span data-ttu-id="6a575-412">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6a575-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="6a575-413">2.1</span><span class="sxs-lookup"><span data-stu-id="6a575-413">2.1</span></span>               | <span data-ttu-id="6a575-414">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="6a575-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="6a575-415">x64</span><span class="sxs-lookup"><span data-stu-id="6a575-415">x64</span></span> | [<span data-ttu-id="6a575-416">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6a575-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="6a575-417">A partire da macOS Catalina (versione 10,15), tutto il software creato dopo il 1 ° giugno 2019 distribuito con ID sviluppatore, deve essere autenticato.</span><span class="sxs-lookup"><span data-stu-id="6a575-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="6a575-418">Questo requisito si applica al runtime di .NET Core, alla .NET Core SDK e al software creato con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a575-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="6a575-419">I programmi di installazione per .NET Core (Runtime e SDK) versioni 3,1, 3,0 e 2,1 sono stati autenticati dal 18 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="6a575-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="6a575-420">Le versioni precedenti rilasciate non vengono autenticate.</span><span class="sxs-lookup"><span data-stu-id="6a575-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="6a575-421">Se si esegue un'app non autenticata, verrà visualizzato un errore simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="6a575-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![avviso di autenticazione di macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="6a575-423">Per altre informazioni sul modo in cui l'autenticazione applicata a .NET Core (e sulle app .NET Core), vedere [Working with MacOS Catalina notariation](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="6a575-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="6a575-424">libgdiplus</span></span>

<span data-ttu-id="6a575-425">Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="6a575-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="6a575-426">Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS.</span><span class="sxs-lookup"><span data-stu-id="6a575-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="6a575-427">Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:</span><span class="sxs-lookup"><span data-stu-id="6a575-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="6a575-428">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6a575-428">Next steps</span></span>

- <span data-ttu-id="6a575-429">Per sviluppare ed eseguire app, installare il [.NET Core SDK](sdk.md) (include il Runtime).</span><span class="sxs-lookup"><span data-stu-id="6a575-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="6a575-430">Per eseguire le app create da altri utenti, installare il [runtime di .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="6a575-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
