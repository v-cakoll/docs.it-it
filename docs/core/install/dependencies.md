---
title: Dipendenze di .NET Core SDK e Runtime-.NET Core
description: Informazioni dettagliate sui prerequisiti per l'architettura del sistema operativo e della CPU per installare il .NET Core SDK e il runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448893"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="7508f-103">Dipendenze e requisiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="7508f-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="7508f-104">In questo articolo vengono illustrati i sistemi operativi e l'architettura della CPU supportati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7508f-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="7508f-105">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="7508f-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="7508f-106">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="7508f-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="7508f-107">Con .NET Core 3,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="7508f-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-108">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-109">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-109">OS</span></span>                            | <span data-ttu-id="7508f-110">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-110">Version</span></span>                        | <span data-ttu-id="7508f-111">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7508f-112">Client Windows</span><span class="sxs-lookup"><span data-stu-id="7508f-112">Windows Client</span></span>                | <span data-ttu-id="7508f-113">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="7508f-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7508f-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-114">x64, x86</span></span>        |
| <span data-ttu-id="7508f-115">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="7508f-115">Windows 10 Client</span></span>             | <span data-ttu-id="7508f-116">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="7508f-116">Version 1607+</span></span>                  | <span data-ttu-id="7508f-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-117">x64, x86</span></span>        |
| <span data-ttu-id="7508f-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7508f-118">Windows Server</span></span>                | <span data-ttu-id="7508f-119">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="7508f-119">2012 R2+</span></span>                       | <span data-ttu-id="7508f-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-120">x64, x86</span></span>        |
| <span data-ttu-id="7508f-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7508f-121">Nano Server</span></span>                   | <span data-ttu-id="7508f-122">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="7508f-122">Version 1803+</span></span>                  | <span data-ttu-id="7508f-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-123">x64, ARM32</span></span>      |

<span data-ttu-id="7508f-124">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="7508f-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7508f-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7508f-126">Con .NET Core 3,0 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="7508f-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-127">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-128">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-128">OS</span></span>                            | <span data-ttu-id="7508f-129">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-129">Version</span></span>                        | <span data-ttu-id="7508f-130">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7508f-131">Client Windows</span><span class="sxs-lookup"><span data-stu-id="7508f-131">Windows Client</span></span>                | <span data-ttu-id="7508f-132">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="7508f-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7508f-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-133">x64, x86</span></span>        |
| <span data-ttu-id="7508f-134">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="7508f-134">Windows 10 Client</span></span>             | <span data-ttu-id="7508f-135">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="7508f-135">Version 1607+</span></span>                  | <span data-ttu-id="7508f-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-136">x64, x86</span></span>        |
| <span data-ttu-id="7508f-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7508f-137">Windows Server</span></span>                | <span data-ttu-id="7508f-138">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="7508f-138">2012 R2+</span></span>                       | <span data-ttu-id="7508f-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-139">x64, x86</span></span>        |
| <span data-ttu-id="7508f-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7508f-140">Nano Server</span></span>                   | <span data-ttu-id="7508f-141">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="7508f-141">Version 1803+</span></span>                  | <span data-ttu-id="7508f-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-142">x64, ARM32</span></span>      |

<span data-ttu-id="7508f-143">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="7508f-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7508f-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7508f-145">Con .NET Core 2,2 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="7508f-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-146">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-147">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-147">OS</span></span>                            | <span data-ttu-id="7508f-148">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-148">Version</span></span>                        | <span data-ttu-id="7508f-149">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7508f-150">Client Windows</span><span class="sxs-lookup"><span data-stu-id="7508f-150">Windows Client</span></span>                | <span data-ttu-id="7508f-151">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="7508f-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7508f-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-152">x64, x86</span></span>        |
| <span data-ttu-id="7508f-153">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="7508f-153">Windows 10 Client</span></span>             | <span data-ttu-id="7508f-154">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="7508f-154">Version 1607+</span></span>                  | <span data-ttu-id="7508f-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-155">x64, x86</span></span>        |
| <span data-ttu-id="7508f-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7508f-156">Windows Server</span></span>                | <span data-ttu-id="7508f-157">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="7508f-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="7508f-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-158">x64, x86</span></span>        |
| <span data-ttu-id="7508f-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7508f-159">Nano Server</span></span>                   | <span data-ttu-id="7508f-160">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="7508f-160">Version 1803+</span></span>                   | <span data-ttu-id="7508f-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-161">x64, ARM32</span></span>      |

<span data-ttu-id="7508f-162">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="7508f-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7508f-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7508f-164">Con .NET Core 2,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="7508f-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-165">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-166">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-166">OS</span></span>                            | <span data-ttu-id="7508f-167">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-167">Version</span></span>                        | <span data-ttu-id="7508f-168">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="7508f-169">Client Windows</span><span class="sxs-lookup"><span data-stu-id="7508f-169">Windows Client</span></span>                | <span data-ttu-id="7508f-170">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="7508f-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="7508f-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-171">x64, x86</span></span>        |
| <span data-ttu-id="7508f-172">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="7508f-172">Windows 10 Client</span></span>             | <span data-ttu-id="7508f-173">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="7508f-173">Version 1607+</span></span>                  | <span data-ttu-id="7508f-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-174">x64, x86</span></span>        |
| <span data-ttu-id="7508f-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="7508f-175">Windows Server</span></span>                | <span data-ttu-id="7508f-176">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="7508f-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="7508f-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="7508f-177">x64, x86</span></span>        |
| <span data-ttu-id="7508f-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="7508f-178">Nano Server</span></span>                   | <span data-ttu-id="7508f-179">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="7508f-179">Version 1803+</span></span>                  | <span data-ttu-id="7508f-180">x64</span><span class="sxs-lookup"><span data-stu-id="7508f-180">x64,</span></span>            |

<span data-ttu-id="7508f-181">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="7508f-182">Windows 7/Vista/8,1/Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7508f-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="7508f-183">Sono necessarie dipendenze aggiuntive se si sta installando .NET SDK o Runtime nelle versioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="7508f-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="7508f-184">Windows 7 SP1</span></span>
- <span data-ttu-id="7508f-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="7508f-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="7508f-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7508f-186">Windows 8.1</span></span>
- <span data-ttu-id="7508f-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7508f-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="7508f-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7508f-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="7508f-189">Installare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-189">Install the following:</span></span>

- <span data-ttu-id="7508f-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="7508f-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="7508f-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="7508f-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="7508f-192">I requisiti indicati sopra sono necessari anche se si verifica uno degli errori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="7508f-193">Non è possibile avviare il programma perché non è presente alcuna *API-MS-Win-CRT-Runtime-L1-1-0. dll* nel computer.</span><span class="sxs-lookup"><span data-stu-id="7508f-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="7508f-194">Per risolvere il problema, provare a reinstallare il programma.</span><span class="sxs-lookup"><span data-stu-id="7508f-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="7508f-195">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="7508f-195">\- or -</span></span>
>
> <span data-ttu-id="7508f-196">La libreria *hostfxr. dll* è stata trovata, ma il caricamento da *C:\\\<path_to_app >\\hostfxr. dll* non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="7508f-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="7508f-197">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="7508f-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="7508f-198">.NET Core 3,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7508f-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="7508f-199">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="7508f-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7508f-200">.NET Core 3,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="7508f-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-201">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-202">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-202">OS</span></span>                             | <span data-ttu-id="7508f-203">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-203">Version</span></span>               | <span data-ttu-id="7508f-204">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="7508f-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="7508f-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="7508f-206">6, 7, 8</span></span>               | <span data-ttu-id="7508f-207">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-207">x64</span></span> |
| <span data-ttu-id="7508f-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="7508f-208">CentOS</span></span>                         | <span data-ttu-id="7508f-209">7+</span><span class="sxs-lookup"><span data-stu-id="7508f-209">7+</span></span>                    | <span data-ttu-id="7508f-210">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-210">x64</span></span> |
| <span data-ttu-id="7508f-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-211">Oracle Linux</span></span>                   | <span data-ttu-id="7508f-212">7+</span><span class="sxs-lookup"><span data-stu-id="7508f-212">7+</span></span>                    | <span data-ttu-id="7508f-213">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-213">x64</span></span> |
| <span data-ttu-id="7508f-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="7508f-214">Fedora</span></span>                         | <span data-ttu-id="7508f-215">29 +</span><span class="sxs-lookup"><span data-stu-id="7508f-215">29+</span></span>                   | <span data-ttu-id="7508f-216">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-216">x64</span></span> |
| <span data-ttu-id="7508f-217">Debian</span><span class="sxs-lookup"><span data-stu-id="7508f-217">Debian</span></span>                         | <span data-ttu-id="7508f-218">9+</span><span class="sxs-lookup"><span data-stu-id="7508f-218">9+</span></span>                    | <span data-ttu-id="7508f-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7508f-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7508f-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7508f-220">Ubuntu</span></span>                         | <span data-ttu-id="7508f-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="7508f-221">16.04+</span></span>                | <span data-ttu-id="7508f-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7508f-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7508f-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7508f-223">Linux Mint</span></span>                     | <span data-ttu-id="7508f-224">18 +</span><span class="sxs-lookup"><span data-stu-id="7508f-224">18+</span></span>                   | <span data-ttu-id="7508f-225">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-225">x64</span></span> |
| <span data-ttu-id="7508f-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7508f-226">openSUSE</span></span>                       | <span data-ttu-id="7508f-227">15 +</span><span class="sxs-lookup"><span data-stu-id="7508f-227">15+</span></span>                   | <span data-ttu-id="7508f-228">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-228">x64</span></span> |
| <span data-ttu-id="7508f-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7508f-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="7508f-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7508f-230">12 SP2+</span></span>               | <span data-ttu-id="7508f-231">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-231">x64</span></span> |
| <span data-ttu-id="7508f-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-232">Alpine Linux</span></span>                   | <span data-ttu-id="7508f-233">3.10 +</span><span class="sxs-lookup"><span data-stu-id="7508f-233">3.10+</span></span>                 | <span data-ttu-id="7508f-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="7508f-234">x64, ARM64</span></span> |

<span data-ttu-id="7508f-235">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="7508f-236">Per altre informazioni su come installare .NET Core 3,1 in ARM64 (kernel 4.14 +), vedere [installazione di .net core 3,0 in Linux arm64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="7508f-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7508f-237">Il supporto di ARM64 richiede il kernel Linux 4,14 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="7508f-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="7508f-238">Alcune distribuzioni Linux soddisfano questo requisito mentre altre no.</span><span class="sxs-lookup"><span data-stu-id="7508f-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="7508f-239">Ubuntu 18,04, ad esempio, è supportato, ma Ubuntu 16,04 non lo è.</span><span class="sxs-lookup"><span data-stu-id="7508f-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="7508f-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7508f-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7508f-241">.NET Core 3,0 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7508f-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="7508f-242">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="7508f-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7508f-243">.NET Core 3,0 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="7508f-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-244">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-245">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-245">OS</span></span>                             | <span data-ttu-id="7508f-246">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-246">Version</span></span>               | <span data-ttu-id="7508f-247">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="7508f-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="7508f-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="7508f-249">6, 7, 8</span></span>               | <span data-ttu-id="7508f-250">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-250">x64</span></span> |
| <span data-ttu-id="7508f-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="7508f-251">CentOS</span></span>                         | <span data-ttu-id="7508f-252">7+</span><span class="sxs-lookup"><span data-stu-id="7508f-252">7+</span></span>                    | <span data-ttu-id="7508f-253">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-253">x64</span></span> |
| <span data-ttu-id="7508f-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-254">Oracle Linux</span></span>                   | <span data-ttu-id="7508f-255">7+</span><span class="sxs-lookup"><span data-stu-id="7508f-255">7+</span></span>                    | <span data-ttu-id="7508f-256">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-256">x64</span></span> |
| <span data-ttu-id="7508f-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="7508f-257">Fedora</span></span>                         | <span data-ttu-id="7508f-258">29 +</span><span class="sxs-lookup"><span data-stu-id="7508f-258">29+</span></span>                   | <span data-ttu-id="7508f-259">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-259">x64</span></span> |
| <span data-ttu-id="7508f-260">Debian</span><span class="sxs-lookup"><span data-stu-id="7508f-260">Debian</span></span>                         | <span data-ttu-id="7508f-261">9+</span><span class="sxs-lookup"><span data-stu-id="7508f-261">9+</span></span>                    | <span data-ttu-id="7508f-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7508f-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7508f-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7508f-263">Ubuntu</span></span>                         | <span data-ttu-id="7508f-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="7508f-264">16.04+</span></span>                | <span data-ttu-id="7508f-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="7508f-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="7508f-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7508f-266">Linux Mint</span></span>                     | <span data-ttu-id="7508f-267">18 +</span><span class="sxs-lookup"><span data-stu-id="7508f-267">18+</span></span>                   | <span data-ttu-id="7508f-268">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-268">x64</span></span> |
| <span data-ttu-id="7508f-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7508f-269">openSUSE</span></span>                       | <span data-ttu-id="7508f-270">15 +</span><span class="sxs-lookup"><span data-stu-id="7508f-270">15+</span></span>                   | <span data-ttu-id="7508f-271">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-271">x64</span></span> |
| <span data-ttu-id="7508f-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7508f-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="7508f-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7508f-273">12 SP2+</span></span>               | <span data-ttu-id="7508f-274">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-274">x64</span></span> |
| <span data-ttu-id="7508f-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-275">Alpine Linux</span></span>                   | <span data-ttu-id="7508f-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="7508f-276">3.8+</span></span>                  | <span data-ttu-id="7508f-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="7508f-277">x64, ARM64</span></span> |

<span data-ttu-id="7508f-278">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="7508f-279">Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="7508f-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="7508f-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7508f-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7508f-281">.NET Core 2,2 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7508f-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="7508f-282">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="7508f-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7508f-283">.NET Core 2,2 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="7508f-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-284">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-285">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-285">OS</span></span>                             |  <span data-ttu-id="7508f-286">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-286">Version</span></span>                |  <span data-ttu-id="7508f-287">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="7508f-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="7508f-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="7508f-289">6, 7</span></span>                   | <span data-ttu-id="7508f-290">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-290">x64</span></span> |
| <span data-ttu-id="7508f-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="7508f-291">CentOS</span></span>                         |  <span data-ttu-id="7508f-292">7</span><span class="sxs-lookup"><span data-stu-id="7508f-292">7</span></span>                      | <span data-ttu-id="7508f-293">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-293">x64</span></span> |
| <span data-ttu-id="7508f-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-294">Oracle Linux</span></span>                   |  <span data-ttu-id="7508f-295">7</span><span class="sxs-lookup"><span data-stu-id="7508f-295">7</span></span>                      | <span data-ttu-id="7508f-296">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-296">x64</span></span> |
| <span data-ttu-id="7508f-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="7508f-297">Fedora</span></span>                         |  <span data-ttu-id="7508f-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="7508f-298">29, 30</span></span>                 | <span data-ttu-id="7508f-299">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-299">x64</span></span> |
| <span data-ttu-id="7508f-300">Debian</span><span class="sxs-lookup"><span data-stu-id="7508f-300">Debian</span></span>                         |  <span data-ttu-id="7508f-301">9</span><span class="sxs-lookup"><span data-stu-id="7508f-301">9</span></span>                      | <span data-ttu-id="7508f-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-302">x64, ARM32</span></span> |
| <span data-ttu-id="7508f-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7508f-303">Ubuntu</span></span>                         |  <span data-ttu-id="7508f-304">16,04, 18,04, 18,10</span><span class="sxs-lookup"><span data-stu-id="7508f-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="7508f-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-305">x64, ARM32</span></span> |
| <span data-ttu-id="7508f-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7508f-306">Linux Mint</span></span>                     |  <span data-ttu-id="7508f-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="7508f-307">17, 18</span></span>                 | <span data-ttu-id="7508f-308">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-308">x64</span></span> |
| <span data-ttu-id="7508f-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7508f-309">openSUSE</span></span>                       |  <span data-ttu-id="7508f-310">15 +</span><span class="sxs-lookup"><span data-stu-id="7508f-310">15+</span></span>                    | <span data-ttu-id="7508f-311">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-311">x64</span></span> |
| <span data-ttu-id="7508f-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7508f-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="7508f-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7508f-313">12 SP2+</span></span>                | <span data-ttu-id="7508f-314">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-314">x64</span></span> |
| <span data-ttu-id="7508f-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-315">Alpine Linux</span></span>                   |  <span data-ttu-id="7508f-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="7508f-316">3.8+</span></span>                   | <span data-ttu-id="7508f-317">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-317">x64</span></span> |

<span data-ttu-id="7508f-318">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="7508f-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7508f-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7508f-320">.NET Core 2,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7508f-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="7508f-321">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="7508f-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="7508f-322">.NET Core 2,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="7508f-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-323">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-324">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7508f-324">OS</span></span>                             |  <span data-ttu-id="7508f-325">Versione</span><span class="sxs-lookup"><span data-stu-id="7508f-325">Version</span></span>                |  <span data-ttu-id="7508f-326">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="7508f-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="7508f-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="7508f-328">6, 7, 8</span></span>                | <span data-ttu-id="7508f-329">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-329">x64</span></span> |
| <span data-ttu-id="7508f-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="7508f-330">CentOS</span></span>                         |  <span data-ttu-id="7508f-331">7+</span><span class="sxs-lookup"><span data-stu-id="7508f-331">7+</span></span>                     | <span data-ttu-id="7508f-332">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-332">x64</span></span> |
| <span data-ttu-id="7508f-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-333">Oracle Linux</span></span>                   |  <span data-ttu-id="7508f-334">7+</span><span class="sxs-lookup"><span data-stu-id="7508f-334">7+</span></span>                     | <span data-ttu-id="7508f-335">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-335">x64</span></span> |
| <span data-ttu-id="7508f-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="7508f-336">Fedora</span></span>                         |  <span data-ttu-id="7508f-337">29 +</span><span class="sxs-lookup"><span data-stu-id="7508f-337">29+</span></span>                    | <span data-ttu-id="7508f-338">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-338">x64</span></span> |
| <span data-ttu-id="7508f-339">Debian</span><span class="sxs-lookup"><span data-stu-id="7508f-339">Debian</span></span>                         |  <span data-ttu-id="7508f-340">9</span><span class="sxs-lookup"><span data-stu-id="7508f-340">9</span></span>                      | <span data-ttu-id="7508f-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-341">x64, ARM32</span></span> |
| <span data-ttu-id="7508f-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7508f-342">Ubuntu</span></span>                         |  <span data-ttu-id="7508f-343">16,04, 18,04, 19,04, 19,10</span><span class="sxs-lookup"><span data-stu-id="7508f-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="7508f-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="7508f-344">x64, ARM32</span></span> |
| <span data-ttu-id="7508f-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="7508f-345">Linux Mint</span></span>                     |  <span data-ttu-id="7508f-346">17 +</span><span class="sxs-lookup"><span data-stu-id="7508f-346">17+</span></span>                    | <span data-ttu-id="7508f-347">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-347">x64</span></span> |
| <span data-ttu-id="7508f-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7508f-348">openSUSE</span></span>                       |  <span data-ttu-id="7508f-349">15 +</span><span class="sxs-lookup"><span data-stu-id="7508f-349">15+</span></span>                    | <span data-ttu-id="7508f-350">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-350">x64</span></span> |
| <span data-ttu-id="7508f-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="7508f-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="7508f-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="7508f-352">12 SP2+</span></span>                | <span data-ttu-id="7508f-353">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-353">x64</span></span> |
| <span data-ttu-id="7508f-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-354">Alpine Linux</span></span>                   |  <span data-ttu-id="7508f-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="7508f-355">3.8+</span></span>                   | <span data-ttu-id="7508f-356">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-356">x64</span></span> |

<span data-ttu-id="7508f-357">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="7508f-358">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="7508f-358">Linux distribution dependencies</span></span>

<span data-ttu-id="7508f-359">In base alla distribuzione Linux, potrebbe essere necessario installare dipendenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7508f-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7508f-360">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="7508f-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="7508f-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7508f-361">Ubuntu</span></span>

<span data-ttu-id="7508f-362">Per le distribuzioni di Ubuntu è necessario installare le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="7508f-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="7508f-363">liblttng-ust0</span></span>
- <span data-ttu-id="7508f-364">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="7508f-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="7508f-365">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="7508f-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="7508f-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="7508f-366">libssl1.0.0</span></span>
- <span data-ttu-id="7508f-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="7508f-367">libkrb5-3</span></span>
- <span data-ttu-id="7508f-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="7508f-368">zlib1g</span></span>
- <span data-ttu-id="7508f-369">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="7508f-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="7508f-370">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="7508f-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="7508f-371">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="7508f-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="7508f-372">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="7508f-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="7508f-373">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="7508f-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="7508f-374">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="7508f-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="7508f-375">La maggior parte delle versioni di Ubuntu include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="7508f-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="7508f-376">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="7508f-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="7508f-377">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="7508f-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="7508f-378">CentOS e Fedora</span><span class="sxs-lookup"><span data-stu-id="7508f-378">CentOS and Fedora</span></span>

<span data-ttu-id="7508f-379">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="7508f-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="7508f-380">lttng-ust</span></span>
- <span data-ttu-id="7508f-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="7508f-381">libcurl</span></span>
- <span data-ttu-id="7508f-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="7508f-382">openssl-libs</span></span>
- <span data-ttu-id="7508f-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7508f-383">krb5-libs</span></span>
- <span data-ttu-id="7508f-384">libicu</span><span class="sxs-lookup"><span data-stu-id="7508f-384">libicu</span></span>
- <span data-ttu-id="7508f-385">zlib</span><span class="sxs-lookup"><span data-stu-id="7508f-385">zlib</span></span>

<span data-ttu-id="7508f-386">Utenti Fedora: se la versione di OpenSSL > = 1,1, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="7508f-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="7508f-387">Per .NET Core 2,0, sono necessarie anche le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="7508f-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="7508f-388">libunwind</span></span>
- <span data-ttu-id="7508f-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="7508f-389">libuuid</span></span>

<span data-ttu-id="7508f-390">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="7508f-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="7508f-391">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="7508f-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="7508f-392">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="7508f-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="7508f-393">La maggior parte delle versioni di CentOS e Fedora include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="7508f-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="7508f-394">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="7508f-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="7508f-395">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="7508f-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="7508f-396">.NET Core è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="7508f-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="7508f-397">Un simbolo di `+` rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="7508f-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="7508f-398">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="7508f-398">.NET Core Version</span></span> | <span data-ttu-id="7508f-399">macOS</span><span class="sxs-lookup"><span data-stu-id="7508f-399">macOS</span></span>                 | <span data-ttu-id="7508f-400">Architetture</span><span class="sxs-lookup"><span data-stu-id="7508f-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="7508f-401">3.1</span><span class="sxs-lookup"><span data-stu-id="7508f-401">3.1</span></span>               | <span data-ttu-id="7508f-402">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="7508f-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="7508f-403">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-403">x64</span></span> | [<span data-ttu-id="7508f-404">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="7508f-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="7508f-405">3.0</span><span class="sxs-lookup"><span data-stu-id="7508f-405">3.0</span></span>               | <span data-ttu-id="7508f-406">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="7508f-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="7508f-407">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-407">x64</span></span> | [<span data-ttu-id="7508f-408">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="7508f-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="7508f-409">2.2</span><span class="sxs-lookup"><span data-stu-id="7508f-409">2.2</span></span>               | <span data-ttu-id="7508f-410">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="7508f-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="7508f-411">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-411">x64</span></span> | [<span data-ttu-id="7508f-412">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="7508f-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="7508f-413">2.1</span><span class="sxs-lookup"><span data-stu-id="7508f-413">2.1</span></span>               | <span data-ttu-id="7508f-414">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="7508f-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="7508f-415">X64</span><span class="sxs-lookup"><span data-stu-id="7508f-415">x64</span></span> | [<span data-ttu-id="7508f-416">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="7508f-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="7508f-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="7508f-417">libgdiplus</span></span>

<span data-ttu-id="7508f-418">Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="7508f-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="7508f-419">Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS.</span><span class="sxs-lookup"><span data-stu-id="7508f-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="7508f-420">Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:</span><span class="sxs-lookup"><span data-stu-id="7508f-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="7508f-421">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7508f-421">Next steps</span></span>

- <span data-ttu-id="7508f-422">Per sviluppare ed eseguire app, installare il [.NET Core SDK](sdk.md) (include il Runtime).</span><span class="sxs-lookup"><span data-stu-id="7508f-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="7508f-423">Per eseguire le app create da altri utenti, installare il [runtime di .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="7508f-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
