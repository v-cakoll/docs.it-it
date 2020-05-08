---
title: Dipendenze di .NET Core SDK e Runtime-.NET Core
description: Informazioni dettagliate sui prerequisiti per l'architettura del sistema operativo e della CPU per installare il .NET Core SDK e il runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 04/30/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 280aa1431686ff99257580bb024a84b1e57f85c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895480"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="ab5b0-103">Dipendenze e requisiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="ab5b0-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="ab5b0-104">In questo articolo vengono illustrati i sistemi operativi e l'architettura della CPU supportati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="ab5b0-105">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="ab5b0-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="ab5b0-106">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="ab5b0-107">Con .NET Core 3,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-108">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-109">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-109">OS</span></span>                            | <span data-ttu-id="ab5b0-110">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-110">Version</span></span>                        | <span data-ttu-id="ab5b0-111">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ab5b0-112">Client Windows</span><span class="sxs-lookup"><span data-stu-id="ab5b0-112">Windows Client</span></span>                | <span data-ttu-id="ab5b0-113">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ab5b0-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-114">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-115">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab5b0-115">Windows 10 Client</span></span>             | <span data-ttu-id="ab5b0-116">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-116">Version 1607+</span></span>                  | <span data-ttu-id="ab5b0-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-117">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-118">Windows Server</span></span>                | <span data-ttu-id="ab5b0-119">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-119">2012 R2+</span></span>                       | <span data-ttu-id="ab5b0-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-120">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-121">Nano Server</span></span>                   | <span data-ttu-id="ab5b0-122">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-122">Version 1803+</span></span>                  | <span data-ttu-id="ab5b0-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-123">x64, ARM32</span></span>      |

<span data-ttu-id="ab5b0-124">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="ab5b0-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ab5b0-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="ab5b0-126">*.NET Core 3,0 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="ab5b0-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="ab5b0-127">Con .NET Core 3,0 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-128">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-129">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-129">OS</span></span>                            | <span data-ttu-id="ab5b0-130">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-130">Version</span></span>                        | <span data-ttu-id="ab5b0-131">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ab5b0-132">Client Windows</span><span class="sxs-lookup"><span data-stu-id="ab5b0-132">Windows Client</span></span>                | <span data-ttu-id="ab5b0-133">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ab5b0-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-134">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-135">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab5b0-135">Windows 10 Client</span></span>             | <span data-ttu-id="ab5b0-136">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-136">Version 1607+</span></span>                  | <span data-ttu-id="ab5b0-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-137">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-138">Windows Server</span></span>                | <span data-ttu-id="ab5b0-139">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-139">2012 R2+</span></span>                       | <span data-ttu-id="ab5b0-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-140">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-141">Nano Server</span></span>                   | <span data-ttu-id="ab5b0-142">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-142">Version 1803+</span></span>                  | <span data-ttu-id="ab5b0-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-143">x64, ARM32</span></span>      |

<span data-ttu-id="ab5b0-144">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="ab5b0-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="ab5b0-146">*.NET Core 2,2 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="ab5b0-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="ab5b0-147">Con .NET Core 2,2 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-148">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-149">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-149">OS</span></span>                            | <span data-ttu-id="ab5b0-150">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-150">Version</span></span>                        | <span data-ttu-id="ab5b0-151">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ab5b0-152">Client Windows</span><span class="sxs-lookup"><span data-stu-id="ab5b0-152">Windows Client</span></span>                | <span data-ttu-id="ab5b0-153">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ab5b0-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-154">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-155">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab5b0-155">Windows 10 Client</span></span>             | <span data-ttu-id="ab5b0-156">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-156">Version 1607+</span></span>                  | <span data-ttu-id="ab5b0-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-157">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-158">Windows Server</span></span>                | <span data-ttu-id="ab5b0-159">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="ab5b0-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-160">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-161">Nano Server</span></span>                   | <span data-ttu-id="ab5b0-162">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-162">Version 1803+</span></span>                   | <span data-ttu-id="ab5b0-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-163">x64, ARM32</span></span>      |

<span data-ttu-id="ab5b0-164">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="ab5b0-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="ab5b0-166">Con .NET Core 2,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-167">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-168">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-168">OS</span></span>                            | <span data-ttu-id="ab5b0-169">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-169">Version</span></span>                        | <span data-ttu-id="ab5b0-170">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="ab5b0-171">Client Windows</span><span class="sxs-lookup"><span data-stu-id="ab5b0-171">Windows Client</span></span>                | <span data-ttu-id="ab5b0-172">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="ab5b0-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-173">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-174">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab5b0-174">Windows 10 Client</span></span>             | <span data-ttu-id="ab5b0-175">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-175">Version 1607+</span></span>                  | <span data-ttu-id="ab5b0-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-176">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-177">Windows Server</span></span>                | <span data-ttu-id="ab5b0-178">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="ab5b0-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="ab5b0-179">x64, x86</span></span>        |
| <span data-ttu-id="ab5b0-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="ab5b0-180">Nano Server</span></span>                   | <span data-ttu-id="ab5b0-181">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-181">Version 1803+</span></span>                  | <span data-ttu-id="ab5b0-182">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-182">x64,</span></span>            |

<span data-ttu-id="ab5b0-183">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a><span data-ttu-id="ab5b0-184">Windows 7/Vista/8,1/Server 2008 R2/Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="ab5b0-185">Sono necessarie dipendenze aggiuntive se si sta installando .NET SDK o Runtime nelle versioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="ab5b0-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-186">Windows 7 SP1</span></span>
- <span data-ttu-id="ab5b0-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="ab5b0-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-188">Windows 8.1</span></span>
- <span data-ttu-id="ab5b0-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="ab5b0-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="ab5b0-191">Installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-191">Install the following:</span></span>

- <span data-ttu-id="ab5b0-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="ab5b0-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="ab5b0-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="ab5b0-194">I requisiti indicati sopra sono necessari anche se si verifica uno degli errori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="ab5b0-195">Non è possibile avviare il programma perché non è presente alcuna *API-MS-Win-CRT-Runtime-L1-1-0. dll* nel computer.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="ab5b0-196">Per risolvere il problema, provare a reinstallare il programma.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="ab5b0-197">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="ab5b0-197">\- or -</span></span>
>
> <span data-ttu-id="ab5b0-198">Non è possibile avviare il programma perché l' *API-MS-Win-cor-TimeZone-L1-1-0. dll* non è presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="ab5b0-199">Per risolvere il problema, provare a reinstallare il programma.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="ab5b0-200">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="ab5b0-200">\- or -</span></span>
>
> <span data-ttu-id="ab5b0-201">La libreria *hostfxr. dll* è stata trovata, ma il caricamento da *C\\\<: path_to_app \\>hostfxr. dll* non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="ab5b0-202">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="ab5b0-203">.NET Core 3,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="ab5b0-204">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="ab5b0-205">.NET Core 3,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-206">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-207">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-207">OS</span></span>                             | <span data-ttu-id="ab5b0-208">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-208">Version</span></span>               | <span data-ttu-id="ab5b0-209">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="ab5b0-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="ab5b0-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="ab5b0-211">6, 7, 8</span></span>               | <span data-ttu-id="ab5b0-212">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-212">x64</span></span> |
| <span data-ttu-id="ab5b0-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-213">CentOS</span></span>                         | <span data-ttu-id="ab5b0-214">7+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-214">7+</span></span>                    | <span data-ttu-id="ab5b0-215">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-215">x64</span></span> |
| <span data-ttu-id="ab5b0-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-216">Oracle Linux</span></span>                   | <span data-ttu-id="ab5b0-217">7+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-217">7+</span></span>                    | <span data-ttu-id="ab5b0-218">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-218">x64</span></span> |
| <span data-ttu-id="ab5b0-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="ab5b0-219">Fedora</span></span>                         | <span data-ttu-id="ab5b0-220">30 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-220">30+</span></span>                   | <span data-ttu-id="ab5b0-221">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-221">x64</span></span> |
| <span data-ttu-id="ab5b0-222">Debian</span><span class="sxs-lookup"><span data-stu-id="ab5b0-222">Debian</span></span>                         | <span data-ttu-id="ab5b0-223">9+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-223">9+</span></span>                    | <span data-ttu-id="ab5b0-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="ab5b0-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ab5b0-225">Ubuntu</span></span>                         | <span data-ttu-id="ab5b0-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-226">16.04+</span></span>                | <span data-ttu-id="ab5b0-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="ab5b0-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="ab5b0-228">Linux Mint</span></span>                     | <span data-ttu-id="ab5b0-229">18 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-229">18+</span></span>                   | <span data-ttu-id="ab5b0-230">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-230">x64</span></span> |
| <span data-ttu-id="ab5b0-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="ab5b0-231">openSUSE</span></span>                       | <span data-ttu-id="ab5b0-232">15 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-232">15+</span></span>                   | <span data-ttu-id="ab5b0-233">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-233">x64</span></span> |
| <span data-ttu-id="ab5b0-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="ab5b0-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-235">12 SP2+</span></span>               | <span data-ttu-id="ab5b0-236">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-236">x64</span></span> |
| <span data-ttu-id="ab5b0-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-237">Alpine Linux</span></span>                   | <span data-ttu-id="ab5b0-238">3.10 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-238">3.10+</span></span>                 | <span data-ttu-id="ab5b0-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-239">x64, ARM64</span></span> |

<span data-ttu-id="ab5b0-240">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="ab5b0-241">Per altre informazioni su come installare .NET Core 3,1 in ARM64 (kernel 4.14 +), vedere [installazione di .net core 3,0 in Linux arm64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab5b0-242">Il supporto di ARM64 richiede il kernel Linux 4,14 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="ab5b0-243">Alcune distribuzioni Linux soddisfano questo requisito mentre altre no.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="ab5b0-244">Ubuntu 18,04, ad esempio, è supportato, ma Ubuntu 16,04 non lo è.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="ab5b0-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ab5b0-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="ab5b0-246">*.NET Core 3,0 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="ab5b0-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="ab5b0-247">.NET Core 3,0 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="ab5b0-248">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="ab5b0-249">.NET Core 3,0 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-250">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-251">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-251">OS</span></span>                             | <span data-ttu-id="ab5b0-252">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-252">Version</span></span>               | <span data-ttu-id="ab5b0-253">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="ab5b0-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="ab5b0-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="ab5b0-255">6, 7, 8</span></span>               | <span data-ttu-id="ab5b0-256">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-256">x64</span></span> |
| <span data-ttu-id="ab5b0-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-257">CentOS</span></span>                         | <span data-ttu-id="ab5b0-258">7+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-258">7+</span></span>                    | <span data-ttu-id="ab5b0-259">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-259">x64</span></span> |
| <span data-ttu-id="ab5b0-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-260">Oracle Linux</span></span>                   | <span data-ttu-id="ab5b0-261">7+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-261">7+</span></span>                    | <span data-ttu-id="ab5b0-262">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-262">x64</span></span> |
| <span data-ttu-id="ab5b0-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="ab5b0-263">Fedora</span></span>                         | <span data-ttu-id="ab5b0-264">29 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-264">29+</span></span>                   | <span data-ttu-id="ab5b0-265">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-265">x64</span></span> |
| <span data-ttu-id="ab5b0-266">Debian</span><span class="sxs-lookup"><span data-stu-id="ab5b0-266">Debian</span></span>                         | <span data-ttu-id="ab5b0-267">9+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-267">9+</span></span>                    | <span data-ttu-id="ab5b0-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="ab5b0-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ab5b0-269">Ubuntu</span></span>                         | <span data-ttu-id="ab5b0-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-270">16.04+</span></span>                | <span data-ttu-id="ab5b0-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="ab5b0-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="ab5b0-272">Linux Mint</span></span>                     | <span data-ttu-id="ab5b0-273">18 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-273">18+</span></span>                   | <span data-ttu-id="ab5b0-274">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-274">x64</span></span> |
| <span data-ttu-id="ab5b0-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="ab5b0-275">openSUSE</span></span>                       | <span data-ttu-id="ab5b0-276">15 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-276">15+</span></span>                   | <span data-ttu-id="ab5b0-277">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-277">x64</span></span> |
| <span data-ttu-id="ab5b0-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="ab5b0-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-279">12 SP2+</span></span>               | <span data-ttu-id="ab5b0-280">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-280">x64</span></span> |
| <span data-ttu-id="ab5b0-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-281">Alpine Linux</span></span>                   | <span data-ttu-id="ab5b0-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-282">3.8+</span></span>                  | <span data-ttu-id="ab5b0-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-283">x64, ARM64</span></span> |

<span data-ttu-id="ab5b0-284">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="ab5b0-285">Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="ab5b0-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="ab5b0-287">*.NET Core 2,2 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="ab5b0-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="ab5b0-288">.NET Core 2,2 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="ab5b0-289">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="ab5b0-290">.NET Core 2,2 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-291">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-292">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-292">OS</span></span>                             |  <span data-ttu-id="ab5b0-293">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-293">Version</span></span>                |  <span data-ttu-id="ab5b0-294">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="ab5b0-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="ab5b0-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="ab5b0-296">6, 7</span></span>                   | <span data-ttu-id="ab5b0-297">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-297">x64</span></span> |
| <span data-ttu-id="ab5b0-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-298">CentOS</span></span>                         |  <span data-ttu-id="ab5b0-299">7</span><span class="sxs-lookup"><span data-stu-id="ab5b0-299">7</span></span>                      | <span data-ttu-id="ab5b0-300">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-300">x64</span></span> |
| <span data-ttu-id="ab5b0-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-301">Oracle Linux</span></span>                   |  <span data-ttu-id="ab5b0-302">7</span><span class="sxs-lookup"><span data-stu-id="ab5b0-302">7</span></span>                      | <span data-ttu-id="ab5b0-303">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-303">x64</span></span> |
| <span data-ttu-id="ab5b0-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="ab5b0-304">Fedora</span></span>                         |  <span data-ttu-id="ab5b0-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="ab5b0-305">29, 30</span></span>                 | <span data-ttu-id="ab5b0-306">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-306">x64</span></span> |
| <span data-ttu-id="ab5b0-307">Debian</span><span class="sxs-lookup"><span data-stu-id="ab5b0-307">Debian</span></span>                         |  <span data-ttu-id="ab5b0-308">9</span><span class="sxs-lookup"><span data-stu-id="ab5b0-308">9</span></span>                      | <span data-ttu-id="ab5b0-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-309">x64, ARM32</span></span> |
| <span data-ttu-id="ab5b0-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ab5b0-310">Ubuntu</span></span>                         |  <span data-ttu-id="ab5b0-311">16,04, 18,04, 18,10</span><span class="sxs-lookup"><span data-stu-id="ab5b0-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="ab5b0-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-312">x64, ARM32</span></span> |
| <span data-ttu-id="ab5b0-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="ab5b0-313">Linux Mint</span></span>                     |  <span data-ttu-id="ab5b0-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="ab5b0-314">17, 18</span></span>                 | <span data-ttu-id="ab5b0-315">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-315">x64</span></span> |
| <span data-ttu-id="ab5b0-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="ab5b0-316">openSUSE</span></span>                       |  <span data-ttu-id="ab5b0-317">15 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-317">15+</span></span>                    | <span data-ttu-id="ab5b0-318">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-318">x64</span></span> |
| <span data-ttu-id="ab5b0-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="ab5b0-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-320">12 SP2+</span></span>                | <span data-ttu-id="ab5b0-321">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-321">x64</span></span> |
| <span data-ttu-id="ab5b0-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-322">Alpine Linux</span></span>                   |  <span data-ttu-id="ab5b0-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-323">3.8+</span></span>                   | <span data-ttu-id="ab5b0-324">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-324">x64</span></span> |

<span data-ttu-id="ab5b0-325">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="ab5b0-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="ab5b0-327">.NET Core 2,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="ab5b0-328">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="ab5b0-329">.NET Core 2,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-330">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-331">OS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-331">OS</span></span>                             |  <span data-ttu-id="ab5b0-332">Versione</span><span class="sxs-lookup"><span data-stu-id="ab5b0-332">Version</span></span>                |  <span data-ttu-id="ab5b0-333">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="ab5b0-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="ab5b0-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="ab5b0-335">6, 7, 8</span></span>                | <span data-ttu-id="ab5b0-336">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-336">x64</span></span> |
| <span data-ttu-id="ab5b0-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-337">CentOS</span></span>                         |  <span data-ttu-id="ab5b0-338">7+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-338">7+</span></span>                     | <span data-ttu-id="ab5b0-339">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-339">x64</span></span> |
| <span data-ttu-id="ab5b0-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-340">Oracle Linux</span></span>                   |  <span data-ttu-id="ab5b0-341">7+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-341">7+</span></span>                     | <span data-ttu-id="ab5b0-342">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-342">x64</span></span> |
| <span data-ttu-id="ab5b0-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="ab5b0-343">Fedora</span></span>                         |  <span data-ttu-id="ab5b0-344">30 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-344">30+</span></span>                    | <span data-ttu-id="ab5b0-345">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-345">x64</span></span> |
| <span data-ttu-id="ab5b0-346">Debian</span><span class="sxs-lookup"><span data-stu-id="ab5b0-346">Debian</span></span>                         |  <span data-ttu-id="ab5b0-347">9</span><span class="sxs-lookup"><span data-stu-id="ab5b0-347">9</span></span>                      | <span data-ttu-id="ab5b0-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-348">x64, ARM32</span></span> |
| <span data-ttu-id="ab5b0-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ab5b0-349">Ubuntu</span></span>                         |  <span data-ttu-id="ab5b0-350">16,04, 18,04, 19,04, 19,10</span><span class="sxs-lookup"><span data-stu-id="ab5b0-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="ab5b0-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="ab5b0-351">x64, ARM32</span></span> |
| <span data-ttu-id="ab5b0-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="ab5b0-352">Linux Mint</span></span>                     |  <span data-ttu-id="ab5b0-353">17+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-353">17+</span></span>                    | <span data-ttu-id="ab5b0-354">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-354">x64</span></span> |
| <span data-ttu-id="ab5b0-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="ab5b0-355">openSUSE</span></span>                       |  <span data-ttu-id="ab5b0-356">15 +</span><span class="sxs-lookup"><span data-stu-id="ab5b0-356">15+</span></span>                    | <span data-ttu-id="ab5b0-357">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-357">x64</span></span> |
| <span data-ttu-id="ab5b0-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="ab5b0-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-359">12 SP2+</span></span>                | <span data-ttu-id="ab5b0-360">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-360">x64</span></span> |
| <span data-ttu-id="ab5b0-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-361">Alpine Linux</span></span>                   |  <span data-ttu-id="ab5b0-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="ab5b0-362">3.8+</span></span>                   | <span data-ttu-id="ab5b0-363">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-363">x64</span></span> |

<span data-ttu-id="ab5b0-364">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="ab5b0-365">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="ab5b0-365">Linux distribution dependencies</span></span>

<span data-ttu-id="ab5b0-366">In base alla distribuzione Linux, potrebbe essere necessario installare dipendenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab5b0-367">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="ab5b0-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ab5b0-368">Ubuntu</span></span>

<span data-ttu-id="ab5b0-369">Per le distribuzioni di Ubuntu è necessario installare le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="ab5b0-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="ab5b0-370">liblttng-ust0</span></span>
- <span data-ttu-id="ab5b0-371">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="ab5b0-372">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="ab5b0-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="ab5b0-373">libssl1.0.0</span></span>
- <span data-ttu-id="ab5b0-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="ab5b0-374">libkrb5-3</span></span>
- <span data-ttu-id="ab5b0-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="ab5b0-375">zlib1g</span></span>
- <span data-ttu-id="ab5b0-376">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="ab5b0-377">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="ab5b0-378">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="ab5b0-379">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="ab5b0-380">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="ab5b0-381">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="ab5b0-382">La maggior parte delle versioni di Ubuntu include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="ab5b0-383">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="ab5b0-384">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="ab5b0-385">CentOS e Fedora</span><span class="sxs-lookup"><span data-stu-id="ab5b0-385">CentOS and Fedora</span></span>

<span data-ttu-id="ab5b0-386">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="ab5b0-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="ab5b0-387">lttng-ust</span></span>
- <span data-ttu-id="ab5b0-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="ab5b0-388">libcurl</span></span>
- <span data-ttu-id="ab5b0-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="ab5b0-389">openssl-libs</span></span>
- <span data-ttu-id="ab5b0-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="ab5b0-390">krb5-libs</span></span>
- <span data-ttu-id="ab5b0-391">libicu</span><span class="sxs-lookup"><span data-stu-id="ab5b0-391">libicu</span></span>
- <span data-ttu-id="ab5b0-392">zlib</span><span class="sxs-lookup"><span data-stu-id="ab5b0-392">zlib</span></span>

<span data-ttu-id="ab5b0-393">Utenti Fedora: se la versione di OpenSSL >= 1,1, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="ab5b0-394">Per .NET Core 2,0, sono necessarie anche le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="ab5b0-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="ab5b0-395">libunwind</span></span>
- <span data-ttu-id="ab5b0-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="ab5b0-396">libuuid</span></span>

<span data-ttu-id="ab5b0-397">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="ab5b0-398">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="ab5b0-399">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="ab5b0-400">La maggior parte delle versioni di CentOS e Fedora include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="ab5b0-401">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="ab5b0-402">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="ab5b0-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="ab5b0-403">Alpine</span></span>

<span data-ttu-id="ab5b0-404">Per le distribuzioni Alpine è necessario installare le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="ab5b0-405">ICU-libs (questa operazione non è necessaria se la globalizzazione è disabilitata)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="ab5b0-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="ab5b0-406">krb5-libs</span></span>
- <span data-ttu-id="ab5b0-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="ab5b0-407">libcurl</span></span>
- <span data-ttu-id="ab5b0-408">libintl</span><span class="sxs-lookup"><span data-stu-id="ab5b0-408">libintl</span></span>
- <span data-ttu-id="ab5b0-409">libssl 1.1 (per Alpine 3,9 o versione successiva) o libssl 1.0 (per quelli meno recenti)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="ab5b0-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="ab5b0-410">libstdc++</span></span>
- <span data-ttu-id="ab5b0-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="ab5b0-411">lttng-ust</span></span>
- <span data-ttu-id="ab5b0-412">numactl (facoltativo, utile solo per i dispositivi con NUMA abilitato)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="ab5b0-413">zlib</span><span class="sxs-lookup"><span data-stu-id="ab5b0-413">zlib</span></span>

<span data-ttu-id="ab5b0-414">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="ab5b0-415">libgdiplus (è disponibile solo nel repository Edge/testing)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="ab5b0-416">.NET Core è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b0-417">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="ab5b0-418">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="ab5b0-418">.NET Core Version</span></span> | <span data-ttu-id="ab5b0-419">macOS</span><span class="sxs-lookup"><span data-stu-id="ab5b0-419">macOS</span></span>                 | <span data-ttu-id="ab5b0-420">Architetture</span><span class="sxs-lookup"><span data-stu-id="ab5b0-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="ab5b0-421">3.1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-421">3.1</span></span>               | <span data-ttu-id="ab5b0-422">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="ab5b0-423">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-423">x64</span></span> | [<span data-ttu-id="ab5b0-424">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ab5b0-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="ab5b0-425">3.0</span><span class="sxs-lookup"><span data-stu-id="ab5b0-425">3.0</span></span>               | <span data-ttu-id="ab5b0-426">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="ab5b0-427">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-427">x64</span></span> | [<span data-ttu-id="ab5b0-428">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ab5b0-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="ab5b0-429">2.2</span><span class="sxs-lookup"><span data-stu-id="ab5b0-429">2.2</span></span>               | <span data-ttu-id="ab5b0-430">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="ab5b0-431">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-431">x64</span></span> | [<span data-ttu-id="ab5b0-432">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ab5b0-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="ab5b0-433">2.1</span><span class="sxs-lookup"><span data-stu-id="ab5b0-433">2.1</span></span>               | <span data-ttu-id="ab5b0-434">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="ab5b0-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="ab5b0-435">x64</span><span class="sxs-lookup"><span data-stu-id="ab5b0-435">x64</span></span> | [<span data-ttu-id="ab5b0-436">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ab5b0-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="ab5b0-437">A partire da macOS Catalina (versione 10,15), tutto il software creato dopo il 1 ° giugno 2019 distribuito con ID sviluppatore, deve essere autenticato.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="ab5b0-438">Questo requisito si applica al runtime di .NET Core, alla .NET Core SDK e al software creato con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="ab5b0-439">I programmi di installazione per .NET Core (Runtime e SDK) versioni 3,1, 3,0 e 2,1 sono stati autenticati dal 18 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="ab5b0-440">Le versioni precedenti rilasciate non vengono autenticate.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="ab5b0-441">Se si esegue un'app non autenticata, verrà visualizzato un errore simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![avviso di autenticazione di macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="ab5b0-443">Per altre informazioni sul modo in cui l'autenticazione applicata a .NET Core (e sulle app .NET Core), vedere [Working with MacOS Catalina notariation](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="ab5b0-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="ab5b0-444">libgdiplus</span></span>

<span data-ttu-id="ab5b0-445">Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="ab5b0-446">Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS.</span><span class="sxs-lookup"><span data-stu-id="ab5b0-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="ab5b0-447">Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:</span><span class="sxs-lookup"><span data-stu-id="ab5b0-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="ab5b0-448">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ab5b0-448">Next steps</span></span>

- <span data-ttu-id="ab5b0-449">Per sviluppare ed eseguire app, installare il [.NET Core SDK](sdk.md) (include il Runtime).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="ab5b0-450">Per eseguire le app create da altri utenti, installare il [runtime di .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b0-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
