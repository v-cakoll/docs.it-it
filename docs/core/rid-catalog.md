---
title: Catalogo dei RID (Runtime IDentifier) di .NET Core
description: Informazioni sull'identificatore di runtime (RID) e su come vengono usati i RID in .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 9343d475319084ddfe3450b4c1d2bbcbd394ad1f
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="e2a4f-103">Catalogo RID di .NET Core</span><span class="sxs-lookup"><span data-stu-id="e2a4f-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="e2a4f-104">RID è l'acronimo di *Runtime IDentifier*.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="e2a4f-105">I valori RID vengono usati per identificare le piattaforme di destinazione in cui viene eseguita l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e2a4f-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="e2a4f-106">e vengono usati dai pacchetti .NET per rappresentare risorse specifiche della piattaforma in pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="e2a4f-107">I valori seguenti sono esempi di RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` o `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="e2a4f-108">Per i pacchetti con dipendenze native, il RID specifica le piattaforme su cui può essere ripristinato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="e2a4f-109">Un singolo RID può essere impostato nell'elemento `<RuntimeIdentifier>` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="e2a4f-110">Più RID possono essere definiti come elenco delimitato da punto e virgola nell'elemento `<RuntimeIdentifiers>` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="e2a4f-111">Vengono usati anche tramite l'opzione `--runtime` con i [comandi CLI di .NET Core](./tools/index.md) seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2a4f-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="e2a4f-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e2a4f-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="e2a4f-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e2a4f-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="e2a4f-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e2a4f-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="e2a4f-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e2a4f-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="e2a4f-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e2a4f-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="e2a4f-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e2a4f-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="e2a4f-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="e2a4f-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="e2a4f-119">I RID che rappresentano un sistema operativo reale seguono in genere il modello seguente: `[os].[version]-[architecture]-[additional qualifiers]` dove:</span><span class="sxs-lookup"><span data-stu-id="e2a4f-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="e2a4f-120">`[os]` è il moniker di sistema operativo/piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="e2a4f-121">Ad esempio `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="e2a4f-122">`[version]` è il numero di versione del sistema operativo nel formato separato da punti (`.`).</span><span class="sxs-lookup"><span data-stu-id="e2a4f-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="e2a4f-123">Ad esempio `15.10`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="e2a4f-124">**Non deve** trattarsi di versioni marketing, poiché tali versioni rappresentano spesso più versioni discrete del sistema operativo con una superficie delle API della piattaforma variabile.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="e2a4f-125">`[architecture]` indica l'architettura del processore,</span><span class="sxs-lookup"><span data-stu-id="e2a4f-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="e2a4f-126">ad esempio `x86`, `x64`, `arm` o `arm64`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="e2a4f-127">`[additional qualifiers]` differenziano ulteriormente piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="e2a4f-128">Ad esempio: `aot` o `corert`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-128">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="e2a4f-129">Grafico RID</span><span class="sxs-lookup"><span data-stu-id="e2a4f-129">RID graph</span></span>

<span data-ttu-id="e2a4f-130">Il grafico RID o grafico di fallback di runtime è un elenco di RID compatibili tra loro.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="e2a4f-131">I RID sono definiti nel pacchetto [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/).</span><span class="sxs-lookup"><span data-stu-id="e2a4f-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="e2a4f-132">È possibile visualizzare l'elenco di RID supportati e il grafico RID nel file [*runtime.json* ](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json), disponibile nel repository CoreFX.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="e2a4f-133">In questo file, si noterà che tutti i RID, ad eccezione di quello di base, contengono un'istruzione `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="e2a4f-134">Queste istruzioni indicano RID compatibili.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="e2a4f-135">Quando NuGet ripristina i pacchetti, tenta di trovare una corrispondenza esatta per il runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="e2a4f-136">Se non trova una corrispondenza esatta, NuGet ripercorre il grafico a ritroso fino a individuare il sistema compatibile più simile in base al grafico RID.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="e2a4f-137">L'esempio seguente è la voce effettiva per il RID `osx.10.12-x64`:</span><span class="sxs-lookup"><span data-stu-id="e2a4f-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="e2a4f-138">Il RID sopra riportato specifica che `osx.10.12-x64` importa `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="e2a4f-139">Quando NuGet ripristina i pacchetti, quindi, tenta di trovare una corrispondenza esatta per `osx.10.12-x64` nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="e2a4f-140">Se NuGet non riesce a trovare il runtime specifico, può ripristinare i pacchetti che specificano i runtime `osx.10.11-x64`, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="e2a4f-141">L'esempio seguente mostra un grafico RID leggermente più ampio, anch'esso definito nel file *runtime.json*:</span><span class="sxs-lookup"><span data-stu-id="e2a4f-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="e2a4f-142">Tutti i RID finiscono per mappare nuovamente al RID `any` radice.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="e2a4f-143">Esistono alcune considerazioni che è necessario tenere presenti quando si lavora con i RID:</span><span class="sxs-lookup"><span data-stu-id="e2a4f-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="e2a4f-144">I RID sono **stringhe opache** e devono essere trattati come black box.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="e2a4f-145">Non creare i RID a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="e2a4f-146">Usare i RID già definiti per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="e2a4f-147">I RID devono essere specifici, quindi non desumere nulla dal valore RID effettivo.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="e2a4f-148">Uso dei RID</span><span class="sxs-lookup"><span data-stu-id="e2a4f-148">Using RIDs</span></span>

<span data-ttu-id="e2a4f-149">Per usare i RID, è necessario sapere quali sono quelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="e2a4f-150">Alla piattaforma vengono regolarmente aggiunti nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="e2a4f-151">Per la versione più recente e completa, vedere il file [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) nel repository CoreFX.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="e2a4f-152">.NET Core 2.0 SDK introduce il concetto di RID portabili.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="e2a4f-153">Si tratta di nuovi valori aggiunti al grafico RID che non sono associati a una versione specifica o a una distribuzione specifica del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="e2a4f-154">Risultano particolarmente utili quando si lavora con più distribuzioni di Linux.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-154">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="e2a4f-155">L'elenco seguente mostra i RID più comuni usati per ogni sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-155">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="e2a4f-156">Non sono inclusi valori `arm` o `corert`.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-156">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="e2a4f-157">RID Windows</span><span class="sxs-lookup"><span data-stu-id="e2a4f-157">Windows RIDs</span></span>

- <span data-ttu-id="e2a4f-158">Portabile</span><span class="sxs-lookup"><span data-stu-id="e2a4f-158">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="e2a4f-159">Windows 7/Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e2a4f-159">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="e2a4f-160">Windows 8/Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e2a4f-160">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="e2a4f-161">Windows 8.1/Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e2a4f-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="e2a4f-162">Windows 10/Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e2a4f-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="e2a4f-163">Per altre informazioni, vedere [Prerequisiti per .NET Core in Windows](windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e2a4f-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="e2a4f-164">RID Linux</span><span class="sxs-lookup"><span data-stu-id="e2a4f-164">Linux RIDs</span></span>

- <span data-ttu-id="e2a4f-165">Portabile</span><span class="sxs-lookup"><span data-stu-id="e2a4f-165">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="e2a4f-166">CentOS</span><span class="sxs-lookup"><span data-stu-id="e2a4f-166">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="e2a4f-167">Debian</span><span class="sxs-lookup"><span data-stu-id="e2a4f-167">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="e2a4f-168">Fedora</span><span class="sxs-lookup"><span data-stu-id="e2a4f-168">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="e2a4f-169">`fedora.25-x64` (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-169">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="e2a4f-170">`fedora.26-x64` (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-170">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="e2a4f-171">Gentoo (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-171">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="e2a4f-172">openSUSE</span><span class="sxs-lookup"><span data-stu-id="e2a4f-172">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="e2a4f-173">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="e2a4f-173">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="e2a4f-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="e2a4f-174">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="e2a4f-175">`rhel.6-x64` (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="e2a4f-176">`rhel.7.3-x64` (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-176">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="e2a4f-177">`rhel.7.4-x64` (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-177">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="e2a4f-178">Tizen (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-178">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="e2a4f-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e2a4f-179">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="e2a4f-180">Derivati di Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e2a4f-180">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="e2a4f-181">`linuxmint.18.1-x64` (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-181">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="e2a4f-182">Per altre informazioni, vedere [Prerequisiti per .NET Core in Linux](linux-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e2a4f-182">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="e2a4f-183">RID macOS</span><span class="sxs-lookup"><span data-stu-id="e2a4f-183">macOS RIDs</span></span>

<span data-ttu-id="e2a4f-184">I RID macOS usano la personalizzazione "OSX" precedente.</span><span class="sxs-lookup"><span data-stu-id="e2a4f-184">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="e2a4f-185">`osx-x64` (.NET Core 2.0 o versioni successive, la versione minima è `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-185">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="e2a4f-186">`osx.10.12-x64` (.NET Core 1.1 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-186">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="e2a4f-187">Per altre informazioni, vedere [Prerequisiti per .NET Core in macOS](macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e2a4f-187">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="e2a4f-188">RID Android (.NET Core 2.0 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="e2a4f-188">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="e2a4f-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2a4f-189">See also</span></span>

[<span data-ttu-id="e2a4f-190">ID di runtime</span><span class="sxs-lookup"><span data-stu-id="e2a4f-190">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
