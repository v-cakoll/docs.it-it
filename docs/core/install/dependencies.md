---
title: Dipendenze di .NET Core SDK e Runtime-.NET Core
description: Informazioni dettagliate sui prerequisiti per l'architettura del sistema operativo e della CPU per installare il .NET Core SDK e il runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 42765d4402dfa17d4e962b2ecaf7a83e91853c76
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140985"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="c49a3-103">Dipendenze e requisiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="c49a3-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="c49a3-104">In questo articolo vengono illustrati i sistemi operativi e l'architettura della CPU supportati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c49a3-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="c49a3-105">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="c49a3-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="c49a3-106">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="c49a3-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c49a3-107">Con .NET Core 3,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="c49a3-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-108">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-109">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-109">OS</span></span>                            | <span data-ttu-id="c49a3-110">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-110">Version</span></span>                        | <span data-ttu-id="c49a3-111">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c49a3-112">Client Windows</span><span class="sxs-lookup"><span data-stu-id="c49a3-112">Windows Client</span></span>                | <span data-ttu-id="c49a3-113">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="c49a3-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c49a3-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-114">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-115">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="c49a3-115">Windows 10 Client</span></span>             | <span data-ttu-id="c49a3-116">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-116">Version 1607+</span></span>                  | <span data-ttu-id="c49a3-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-117">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-118">Windows Server</span></span>                | <span data-ttu-id="c49a3-119">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-119">2012 R2+</span></span>                       | <span data-ttu-id="c49a3-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-120">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-121">Nano Server</span></span>                   | <span data-ttu-id="c49a3-122">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-122">Version 1803+</span></span>                  | <span data-ttu-id="c49a3-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-123">x64, ARM32</span></span>      |

<span data-ttu-id="c49a3-124">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c49a3-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c49a3-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c49a3-126">*.NET Core 3,0 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c49a3-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c49a3-127">Con .NET Core 3,0 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="c49a3-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-128">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-129">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-129">OS</span></span>                            | <span data-ttu-id="c49a3-130">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-130">Version</span></span>                        | <span data-ttu-id="c49a3-131">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c49a3-132">Client Windows</span><span class="sxs-lookup"><span data-stu-id="c49a3-132">Windows Client</span></span>                | <span data-ttu-id="c49a3-133">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="c49a3-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c49a3-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-134">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-135">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="c49a3-135">Windows 10 Client</span></span>             | <span data-ttu-id="c49a3-136">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-136">Version 1607+</span></span>                  | <span data-ttu-id="c49a3-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-137">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-138">Windows Server</span></span>                | <span data-ttu-id="c49a3-139">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-139">2012 R2+</span></span>                       | <span data-ttu-id="c49a3-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-140">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-141">Nano Server</span></span>                   | <span data-ttu-id="c49a3-142">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-142">Version 1803+</span></span>                  | <span data-ttu-id="c49a3-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-143">x64, ARM32</span></span>      |

<span data-ttu-id="c49a3-144">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c49a3-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c49a3-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c49a3-146">*.NET Core 2,2 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c49a3-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c49a3-147">Con .NET Core 2,2 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="c49a3-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-148">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-149">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-149">OS</span></span>                            | <span data-ttu-id="c49a3-150">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-150">Version</span></span>                        | <span data-ttu-id="c49a3-151">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c49a3-152">Client Windows</span><span class="sxs-lookup"><span data-stu-id="c49a3-152">Windows Client</span></span>                | <span data-ttu-id="c49a3-153">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="c49a3-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c49a3-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-154">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-155">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="c49a3-155">Windows 10 Client</span></span>             | <span data-ttu-id="c49a3-156">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-156">Version 1607+</span></span>                  | <span data-ttu-id="c49a3-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-157">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-158">Windows Server</span></span>                | <span data-ttu-id="c49a3-159">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c49a3-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-160">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-161">Nano Server</span></span>                   | <span data-ttu-id="c49a3-162">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-162">Version 1803+</span></span>                   | <span data-ttu-id="c49a3-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-163">x64, ARM32</span></span>      |

<span data-ttu-id="c49a3-164">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c49a3-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c49a3-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c49a3-166">Con .NET Core 2,1 sono supportate le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="c49a3-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-167">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-168">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-168">OS</span></span>                            | <span data-ttu-id="c49a3-169">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-169">Version</span></span>                        | <span data-ttu-id="c49a3-170">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c49a3-171">Client Windows</span><span class="sxs-lookup"><span data-stu-id="c49a3-171">Windows Client</span></span>                | <span data-ttu-id="c49a3-172">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="c49a3-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c49a3-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-173">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-174">Client Windows 10</span><span class="sxs-lookup"><span data-stu-id="c49a3-174">Windows 10 Client</span></span>             | <span data-ttu-id="c49a3-175">Versione 1607 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-175">Version 1607+</span></span>                  | <span data-ttu-id="c49a3-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-176">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-177">Windows Server</span></span>                | <span data-ttu-id="c49a3-178">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c49a3-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c49a3-179">x64, x86</span></span>        |
| <span data-ttu-id="c49a3-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c49a3-180">Nano Server</span></span>                   | <span data-ttu-id="c49a3-181">Versione 1803 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-181">Version 1803+</span></span>                  | <span data-ttu-id="c49a3-182">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-182">x64,</span></span>            |

<span data-ttu-id="c49a3-183">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a><span data-ttu-id="c49a3-184">Windows 7/Vista/8,1/Server 2008 R2/Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c49a3-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="c49a3-185">Sono necessarie dipendenze aggiuntive se si sta installando .NET SDK o Runtime nelle versioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="c49a3-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="c49a3-186">Windows 7 SP1</span></span>
- <span data-ttu-id="c49a3-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="c49a3-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="c49a3-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c49a3-188">Windows 8.1</span></span>
- <span data-ttu-id="c49a3-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c49a3-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="c49a3-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c49a3-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="c49a3-191">Installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-191">Install the following:</span></span>

- <span data-ttu-id="c49a3-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="c49a3-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="c49a3-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="c49a3-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="c49a3-194">I requisiti indicati sopra sono necessari anche se si verifica uno degli errori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="c49a3-195">Non è possibile avviare il programma perché non è presente alcuna *API-MS-Win-CRT-Runtime-L1-1-0. dll* nel computer.</span><span class="sxs-lookup"><span data-stu-id="c49a3-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="c49a3-196">Per risolvere il problema, provare a reinstallare il programma.</span><span class="sxs-lookup"><span data-stu-id="c49a3-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="c49a3-197">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="c49a3-197">\- or -</span></span>
>
> <span data-ttu-id="c49a3-198">Non è possibile avviare il programma perché l' *API-MS-Win-cor-TimeZone-L1-1-0. dll* non è presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="c49a3-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="c49a3-199">Per risolvere il problema, provare a reinstallare il programma.</span><span class="sxs-lookup"><span data-stu-id="c49a3-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="c49a3-200">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="c49a3-200">\- or -</span></span>
>
> <span data-ttu-id="c49a3-201">La libreria *hostfxr. dll* è stata trovata, ma il caricamento da *C\\\<: path_to_app \\>hostfxr. dll* non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c49a3-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="c49a3-202">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="c49a3-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c49a3-203">.NET Core 3,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c49a3-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c49a3-204">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="c49a3-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c49a3-205">.NET Core 3,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="c49a3-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-206">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-207">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-207">OS</span></span>                             | <span data-ttu-id="c49a3-208">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-208">Version</span></span>               | <span data-ttu-id="c49a3-209">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c49a3-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c49a3-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c49a3-211">6, 7, 8</span></span>               | <span data-ttu-id="c49a3-212">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-212">x64</span></span> |
| <span data-ttu-id="c49a3-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="c49a3-213">CentOS</span></span>                         | <span data-ttu-id="c49a3-214">7+</span><span class="sxs-lookup"><span data-stu-id="c49a3-214">7+</span></span>                    | <span data-ttu-id="c49a3-215">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-215">x64</span></span> |
| <span data-ttu-id="c49a3-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-216">Oracle Linux</span></span>                   | <span data-ttu-id="c49a3-217">7+</span><span class="sxs-lookup"><span data-stu-id="c49a3-217">7+</span></span>                    | <span data-ttu-id="c49a3-218">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-218">x64</span></span> |
| <span data-ttu-id="c49a3-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="c49a3-219">Fedora</span></span>                         | <span data-ttu-id="c49a3-220">30 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-220">30+</span></span>                   | <span data-ttu-id="c49a3-221">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-221">x64</span></span> |
| <span data-ttu-id="c49a3-222">Debian</span><span class="sxs-lookup"><span data-stu-id="c49a3-222">Debian</span></span>                         | <span data-ttu-id="c49a3-223">9+</span><span class="sxs-lookup"><span data-stu-id="c49a3-223">9+</span></span>                    | <span data-ttu-id="c49a3-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c49a3-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c49a3-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c49a3-225">Ubuntu</span></span>                         | <span data-ttu-id="c49a3-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="c49a3-226">16.04+</span></span>                | <span data-ttu-id="c49a3-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c49a3-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c49a3-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c49a3-228">Linux Mint</span></span>                     | <span data-ttu-id="c49a3-229">18 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-229">18+</span></span>                   | <span data-ttu-id="c49a3-230">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-230">x64</span></span> |
| <span data-ttu-id="c49a3-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c49a3-231">openSUSE</span></span>                       | <span data-ttu-id="c49a3-232">15 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-232">15+</span></span>                   | <span data-ttu-id="c49a3-233">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-233">x64</span></span> |
| <span data-ttu-id="c49a3-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c49a3-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c49a3-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c49a3-235">12 SP2+</span></span>               | <span data-ttu-id="c49a3-236">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-236">x64</span></span> |
| <span data-ttu-id="c49a3-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-237">Alpine Linux</span></span>                   | <span data-ttu-id="c49a3-238">3.10 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-238">3.10+</span></span>                 | <span data-ttu-id="c49a3-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="c49a3-239">x64, ARM64</span></span> |

<span data-ttu-id="c49a3-240">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="c49a3-241">Per altre informazioni su come installare .NET Core 3,1 in ARM64 (kernel 4.14 +), vedere [installazione di .net core 3,0 in Linux arm64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="c49a3-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c49a3-242">Il supporto di ARM64 richiede il kernel Linux 4,14 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c49a3-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="c49a3-243">Alcune distribuzioni Linux soddisfano questo requisito mentre altre no.</span><span class="sxs-lookup"><span data-stu-id="c49a3-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="c49a3-244">Ubuntu 18,04, ad esempio, è supportato, ma Ubuntu 16,04 non lo è.</span><span class="sxs-lookup"><span data-stu-id="c49a3-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c49a3-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c49a3-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c49a3-246">*.NET Core 3,0 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c49a3-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c49a3-247">.NET Core 3,0 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c49a3-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="c49a3-248">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="c49a3-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c49a3-249">.NET Core 3,0 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="c49a3-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-250">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-251">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-251">OS</span></span>                             | <span data-ttu-id="c49a3-252">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-252">Version</span></span>               | <span data-ttu-id="c49a3-253">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c49a3-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c49a3-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c49a3-255">6, 7, 8</span></span>               | <span data-ttu-id="c49a3-256">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-256">x64</span></span> |
| <span data-ttu-id="c49a3-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="c49a3-257">CentOS</span></span>                         | <span data-ttu-id="c49a3-258">7+</span><span class="sxs-lookup"><span data-stu-id="c49a3-258">7+</span></span>                    | <span data-ttu-id="c49a3-259">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-259">x64</span></span> |
| <span data-ttu-id="c49a3-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-260">Oracle Linux</span></span>                   | <span data-ttu-id="c49a3-261">7+</span><span class="sxs-lookup"><span data-stu-id="c49a3-261">7+</span></span>                    | <span data-ttu-id="c49a3-262">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-262">x64</span></span> |
| <span data-ttu-id="c49a3-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="c49a3-263">Fedora</span></span>                         | <span data-ttu-id="c49a3-264">29 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-264">29+</span></span>                   | <span data-ttu-id="c49a3-265">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-265">x64</span></span> |
| <span data-ttu-id="c49a3-266">Debian</span><span class="sxs-lookup"><span data-stu-id="c49a3-266">Debian</span></span>                         | <span data-ttu-id="c49a3-267">9+</span><span class="sxs-lookup"><span data-stu-id="c49a3-267">9+</span></span>                    | <span data-ttu-id="c49a3-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c49a3-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c49a3-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c49a3-269">Ubuntu</span></span>                         | <span data-ttu-id="c49a3-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="c49a3-270">16.04+</span></span>                | <span data-ttu-id="c49a3-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c49a3-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c49a3-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c49a3-272">Linux Mint</span></span>                     | <span data-ttu-id="c49a3-273">18 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-273">18+</span></span>                   | <span data-ttu-id="c49a3-274">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-274">x64</span></span> |
| <span data-ttu-id="c49a3-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c49a3-275">openSUSE</span></span>                       | <span data-ttu-id="c49a3-276">15 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-276">15+</span></span>                   | <span data-ttu-id="c49a3-277">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-277">x64</span></span> |
| <span data-ttu-id="c49a3-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c49a3-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c49a3-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c49a3-279">12 SP2+</span></span>               | <span data-ttu-id="c49a3-280">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-280">x64</span></span> |
| <span data-ttu-id="c49a3-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-281">Alpine Linux</span></span>                   | <span data-ttu-id="c49a3-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="c49a3-282">3.8+</span></span>                  | <span data-ttu-id="c49a3-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="c49a3-283">x64, ARM64</span></span> |

<span data-ttu-id="c49a3-284">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="c49a3-285">Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="c49a3-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c49a3-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c49a3-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c49a3-287">*.NET Core 2,2 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c49a3-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c49a3-288">.NET Core 2,2 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c49a3-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="c49a3-289">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="c49a3-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c49a3-290">.NET Core 2,2 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="c49a3-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-291">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-292">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-292">OS</span></span>                             |  <span data-ttu-id="c49a3-293">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-293">Version</span></span>                |  <span data-ttu-id="c49a3-294">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c49a3-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c49a3-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="c49a3-296">6, 7</span></span>                   | <span data-ttu-id="c49a3-297">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-297">x64</span></span> |
| <span data-ttu-id="c49a3-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="c49a3-298">CentOS</span></span>                         |  <span data-ttu-id="c49a3-299">7</span><span class="sxs-lookup"><span data-stu-id="c49a3-299">7</span></span>                      | <span data-ttu-id="c49a3-300">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-300">x64</span></span> |
| <span data-ttu-id="c49a3-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-301">Oracle Linux</span></span>                   |  <span data-ttu-id="c49a3-302">7</span><span class="sxs-lookup"><span data-stu-id="c49a3-302">7</span></span>                      | <span data-ttu-id="c49a3-303">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-303">x64</span></span> |
| <span data-ttu-id="c49a3-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="c49a3-304">Fedora</span></span>                         |  <span data-ttu-id="c49a3-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="c49a3-305">29, 30</span></span>                 | <span data-ttu-id="c49a3-306">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-306">x64</span></span> |
| <span data-ttu-id="c49a3-307">Debian</span><span class="sxs-lookup"><span data-stu-id="c49a3-307">Debian</span></span>                         |  <span data-ttu-id="c49a3-308">9</span><span class="sxs-lookup"><span data-stu-id="c49a3-308">9</span></span>                      | <span data-ttu-id="c49a3-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-309">x64, ARM32</span></span> |
| <span data-ttu-id="c49a3-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c49a3-310">Ubuntu</span></span>                         |  <span data-ttu-id="c49a3-311">16,04, 18,04, 18,10</span><span class="sxs-lookup"><span data-stu-id="c49a3-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="c49a3-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-312">x64, ARM32</span></span> |
| <span data-ttu-id="c49a3-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c49a3-313">Linux Mint</span></span>                     |  <span data-ttu-id="c49a3-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="c49a3-314">17, 18</span></span>                 | <span data-ttu-id="c49a3-315">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-315">x64</span></span> |
| <span data-ttu-id="c49a3-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c49a3-316">openSUSE</span></span>                       |  <span data-ttu-id="c49a3-317">15 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-317">15+</span></span>                    | <span data-ttu-id="c49a3-318">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-318">x64</span></span> |
| <span data-ttu-id="c49a3-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c49a3-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c49a3-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c49a3-320">12 SP2+</span></span>                | <span data-ttu-id="c49a3-321">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-321">x64</span></span> |
| <span data-ttu-id="c49a3-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-322">Alpine Linux</span></span>                   |  <span data-ttu-id="c49a3-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="c49a3-323">3.8+</span></span>                   | <span data-ttu-id="c49a3-324">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-324">x64</span></span> |

<span data-ttu-id="c49a3-325">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c49a3-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c49a3-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c49a3-327">.NET Core 2,1 considera Linux come un singolo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c49a3-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c49a3-328">È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="c49a3-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c49a3-329">.NET Core 2,1 è supportato nelle seguenti distribuzioni/versioni di Linux:</span><span class="sxs-lookup"><span data-stu-id="c49a3-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-330">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-331">OS</span><span class="sxs-lookup"><span data-stu-id="c49a3-331">OS</span></span>                             |  <span data-ttu-id="c49a3-332">Versione</span><span class="sxs-lookup"><span data-stu-id="c49a3-332">Version</span></span>                |  <span data-ttu-id="c49a3-333">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c49a3-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c49a3-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c49a3-335">6, 7, 8</span></span>                | <span data-ttu-id="c49a3-336">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-336">x64</span></span> |
| <span data-ttu-id="c49a3-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="c49a3-337">CentOS</span></span>                         |  <span data-ttu-id="c49a3-338">7+</span><span class="sxs-lookup"><span data-stu-id="c49a3-338">7+</span></span>                     | <span data-ttu-id="c49a3-339">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-339">x64</span></span> |
| <span data-ttu-id="c49a3-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-340">Oracle Linux</span></span>                   |  <span data-ttu-id="c49a3-341">7+</span><span class="sxs-lookup"><span data-stu-id="c49a3-341">7+</span></span>                     | <span data-ttu-id="c49a3-342">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-342">x64</span></span> |
| <span data-ttu-id="c49a3-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="c49a3-343">Fedora</span></span>                         |  <span data-ttu-id="c49a3-344">30 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-344">30+</span></span>                    | <span data-ttu-id="c49a3-345">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-345">x64</span></span> |
| <span data-ttu-id="c49a3-346">Debian</span><span class="sxs-lookup"><span data-stu-id="c49a3-346">Debian</span></span>                         |  <span data-ttu-id="c49a3-347">9</span><span class="sxs-lookup"><span data-stu-id="c49a3-347">9</span></span>                      | <span data-ttu-id="c49a3-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-348">x64, ARM32</span></span> |
| <span data-ttu-id="c49a3-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c49a3-349">Ubuntu</span></span>                         |  <span data-ttu-id="c49a3-350">16,04, 18,04, 19,04, 19,10</span><span class="sxs-lookup"><span data-stu-id="c49a3-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="c49a3-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c49a3-351">x64, ARM32</span></span> |
| <span data-ttu-id="c49a3-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c49a3-352">Linux Mint</span></span>                     |  <span data-ttu-id="c49a3-353">17+</span><span class="sxs-lookup"><span data-stu-id="c49a3-353">17+</span></span>                    | <span data-ttu-id="c49a3-354">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-354">x64</span></span> |
| <span data-ttu-id="c49a3-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c49a3-355">openSUSE</span></span>                       |  <span data-ttu-id="c49a3-356">15 +</span><span class="sxs-lookup"><span data-stu-id="c49a3-356">15+</span></span>                    | <span data-ttu-id="c49a3-357">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-357">x64</span></span> |
| <span data-ttu-id="c49a3-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c49a3-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c49a3-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c49a3-359">12 SP2+</span></span>                | <span data-ttu-id="c49a3-360">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-360">x64</span></span> |
| <span data-ttu-id="c49a3-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-361">Alpine Linux</span></span>                   |  <span data-ttu-id="c49a3-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="c49a3-362">3.8+</span></span>                   | <span data-ttu-id="c49a3-363">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-363">x64</span></span> |

<span data-ttu-id="c49a3-364">Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="c49a3-365">Dipendenze delle distribuzioni Linux</span><span class="sxs-lookup"><span data-stu-id="c49a3-365">Linux distribution dependencies</span></span>

<span data-ttu-id="c49a3-366">In base alla distribuzione Linux, potrebbe essere necessario installare dipendenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c49a3-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c49a3-367">Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.</span><span class="sxs-lookup"><span data-stu-id="c49a3-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="c49a3-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c49a3-368">Ubuntu</span></span>

<span data-ttu-id="c49a3-369">Per le distribuzioni di Ubuntu è necessario installare le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="c49a3-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="c49a3-370">liblttng-ust0</span></span>
- <span data-ttu-id="c49a3-371">libcurl3 (per 14.x e 16.x)</span><span class="sxs-lookup"><span data-stu-id="c49a3-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="c49a3-372">libcurl4 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="c49a3-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="c49a3-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="c49a3-373">libssl1.0.0</span></span>
- <span data-ttu-id="c49a3-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="c49a3-374">libkrb5-3</span></span>
- <span data-ttu-id="c49a3-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="c49a3-375">zlib1g</span></span>
- <span data-ttu-id="c49a3-376">libicu52 (per 14.X)</span><span class="sxs-lookup"><span data-stu-id="c49a3-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="c49a3-377">libicu55 (per 16.X)</span><span class="sxs-lookup"><span data-stu-id="c49a3-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="c49a3-378">libicu57 (per 17.X)</span><span class="sxs-lookup"><span data-stu-id="c49a3-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="c49a3-379">libicu60 (per 18.x)</span><span class="sxs-lookup"><span data-stu-id="c49a3-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="c49a3-380">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="c49a3-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="c49a3-381">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="c49a3-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c49a3-382">La maggior parte delle versioni di Ubuntu include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c49a3-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c49a3-383">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="c49a3-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c49a3-384">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="c49a3-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="c49a3-385">CentOS e Fedora</span><span class="sxs-lookup"><span data-stu-id="c49a3-385">CentOS and Fedora</span></span>

<span data-ttu-id="c49a3-386">Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="c49a3-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="c49a3-387">lttng-ust</span></span>
- <span data-ttu-id="c49a3-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="c49a3-388">libcurl</span></span>
- <span data-ttu-id="c49a3-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="c49a3-389">openssl-libs</span></span>
- <span data-ttu-id="c49a3-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="c49a3-390">krb5-libs</span></span>
- <span data-ttu-id="c49a3-391">libicu</span><span class="sxs-lookup"><span data-stu-id="c49a3-391">libicu</span></span>
- <span data-ttu-id="c49a3-392">zlib</span><span class="sxs-lookup"><span data-stu-id="c49a3-392">zlib</span></span>

<span data-ttu-id="c49a3-393">Utenti Fedora: se la versione di OpenSSL >= 1,1, è necessario installare **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="c49a3-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="c49a3-394">Per .NET Core 2,0, sono necessarie anche le dipendenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="c49a3-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="c49a3-395">libunwind</span></span>
- <span data-ttu-id="c49a3-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="c49a3-396">libuuid</span></span>

<span data-ttu-id="c49a3-397">Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.</span><span class="sxs-lookup"><span data-stu-id="c49a3-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="c49a3-398">Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:</span><span class="sxs-lookup"><span data-stu-id="c49a3-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="c49a3-399">libgdiplus (versione 6.0.1 o successiva)</span><span class="sxs-lookup"><span data-stu-id="c49a3-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c49a3-400">La maggior parte delle versioni di CentOS e Fedora include una versione precedente di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c49a3-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c49a3-401">È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="c49a3-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c49a3-402">Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="c49a3-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="c49a3-403">.NET Core è supportato nelle versioni di macOS seguenti:</span><span class="sxs-lookup"><span data-stu-id="c49a3-403">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="c49a3-404">Un `+` simbolo rappresenta la versione minima.</span><span class="sxs-lookup"><span data-stu-id="c49a3-404">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c49a3-405">Versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="c49a3-405">.NET Core Version</span></span> | <span data-ttu-id="c49a3-406">macOS</span><span class="sxs-lookup"><span data-stu-id="c49a3-406">macOS</span></span>                 | <span data-ttu-id="c49a3-407">Architetture</span><span class="sxs-lookup"><span data-stu-id="c49a3-407">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="c49a3-408">3.1</span><span class="sxs-lookup"><span data-stu-id="c49a3-408">3.1</span></span>               | <span data-ttu-id="c49a3-409">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="c49a3-409">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c49a3-410">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-410">x64</span></span> | [<span data-ttu-id="c49a3-411">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c49a3-411">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="c49a3-412">3.0</span><span class="sxs-lookup"><span data-stu-id="c49a3-412">3.0</span></span>               | <span data-ttu-id="c49a3-413">Alta Sierra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="c49a3-413">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c49a3-414">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-414">x64</span></span> | [<span data-ttu-id="c49a3-415">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c49a3-415">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="c49a3-416">2.2</span><span class="sxs-lookup"><span data-stu-id="c49a3-416">2.2</span></span>               | <span data-ttu-id="c49a3-417">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="c49a3-417">Sierra (10.12+)</span></span>       | <span data-ttu-id="c49a3-418">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-418">x64</span></span> | [<span data-ttu-id="c49a3-419">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c49a3-419">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="c49a3-420">2.1</span><span class="sxs-lookup"><span data-stu-id="c49a3-420">2.1</span></span>               | <span data-ttu-id="c49a3-421">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="c49a3-421">Sierra (10.12+)</span></span>       | <span data-ttu-id="c49a3-422">x64</span><span class="sxs-lookup"><span data-stu-id="c49a3-422">x64</span></span> | [<span data-ttu-id="c49a3-423">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c49a3-423">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="c49a3-424">A partire da macOS Catalina (versione 10,15), tutto il software creato dopo il 1 ° giugno 2019 distribuito con ID sviluppatore, deve essere autenticato.</span><span class="sxs-lookup"><span data-stu-id="c49a3-424">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="c49a3-425">Questo requisito si applica al runtime di .NET Core, alla .NET Core SDK e al software creato con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c49a3-425">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="c49a3-426">I programmi di installazione per .NET Core (Runtime e SDK) versioni 3,1, 3,0 e 2,1 sono stati autenticati dal 18 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="c49a3-426">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="c49a3-427">Le versioni precedenti rilasciate non vengono autenticate.</span><span class="sxs-lookup"><span data-stu-id="c49a3-427">Prior released versions aren't notarized.</span></span> <span data-ttu-id="c49a3-428">Se si esegue un'app non autenticata, verrà visualizzato un errore simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="c49a3-428">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![avviso di autenticazione di macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="c49a3-430">Per altre informazioni sul modo in cui l'autenticazione applicata a .NET Core (e sulle app .NET Core), vedere [Working with MacOS Catalina notariation](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-430">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="c49a3-431">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="c49a3-431">libgdiplus</span></span>

<span data-ttu-id="c49a3-432">Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c49a3-432">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="c49a3-433">Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS.</span><span class="sxs-lookup"><span data-stu-id="c49a3-433">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="c49a3-434">Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:</span><span class="sxs-lookup"><span data-stu-id="c49a3-434">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="c49a3-435">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c49a3-435">Next steps</span></span>

- <span data-ttu-id="c49a3-436">Per sviluppare ed eseguire app, installare il [.NET Core SDK](sdk.md) (include il Runtime).</span><span class="sxs-lookup"><span data-stu-id="c49a3-436">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="c49a3-437">Per eseguire le app create da altri utenti, installare il [runtime di .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-437">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
