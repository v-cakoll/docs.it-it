---
title: Catalogo dei RID (Runtime IDentifier) di .NET Core
description: Informazioni sull'identificatore di runtime (RID) e su come vengono usati i RID in .NET Core.
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3490fb639efd223dc36190324bdf3a06bc23c10e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-runtime-identifier-rid-catalog"></a><span data-ttu-id="f43cf-104">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f43cf-104">.NET Core Runtime IDentifier (RID) catalog</span></span>

## <a name="what-are-rids"></a><span data-ttu-id="f43cf-105">Caratteristiche dei RID</span><span class="sxs-lookup"><span data-stu-id="f43cf-105">What are RIDs?</span></span>
<span data-ttu-id="f43cf-106">RID è l'acronimo di *Runtime IDentifier*.</span><span class="sxs-lookup"><span data-stu-id="f43cf-106">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="f43cf-107">I RID vengono usati per identificare i sistemi operativi di destinazione in cui verrà eseguita un'applicazione o una risorsa, ad esempio un assembly.</span><span class="sxs-lookup"><span data-stu-id="f43cf-107">RIDs are used to identify target operating systems where an application or asset (that is, assembly) will run.</span></span> <span data-ttu-id="f43cf-108">I RID hanno l'aspetto seguente: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span><span class="sxs-lookup"><span data-stu-id="f43cf-108">They look like this: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span></span> <span data-ttu-id="f43cf-109">Per i pacchetti con dipendenze native, il RID specifica le piattaforme su cui verrà ripristinato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f43cf-109">For the packages with native dependencies, it will designate on which platforms the package can be restored.</span></span> 

<span data-ttu-id="f43cf-110">È importante sottolineare che i RID sono stringhe molto opache.</span><span class="sxs-lookup"><span data-stu-id="f43cf-110">It is important to note that RIDs are really opaque strings.</span></span> <span data-ttu-id="f43cf-111">Questo significa che, per funzionare, devono corrispondere esattamente alle operazioni che li usano.</span><span class="sxs-lookup"><span data-stu-id="f43cf-111">This means that they have to match exactly for operations using them to work.</span></span> <span data-ttu-id="f43cf-112">Si consideri ad esempio il caso di [Elementary OS](https://elementary.io/), che è un clone diretto di Ubuntu 14.04.</span><span class="sxs-lookup"><span data-stu-id="f43cf-112">As an example, let us consider the case of [Elementary OS](https://elementary.io/), which is a straightforward clone of Ubuntu 14.04.</span></span> <span data-ttu-id="f43cf-113">Anche se .NET Core e l'interfaccia della riga di comando funzionano correttamente in questa versione di Ubuntu, se si tenta di usarli in Elementary OS senza alcuna modifica, il ripristino di un qualsiasi pacchetto avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f43cf-113">Although .NET Core and CLI work on top of that version of Ubuntu, if you try to use them on Elementary OS without any modifications, the restore operation for any package will fail.</span></span> <span data-ttu-id="f43cf-114">Questo problema si verifica perché attualmente non è disponibile un RID che designi Elementary OS come piattaforma.</span><span class="sxs-lookup"><span data-stu-id="f43cf-114">This is because we currently don't have a RID that designates Elementary OS as a platform.</span></span> 

<span data-ttu-id="f43cf-115">I RID che rappresentano un sistema operativo reale seguono in genere il modello seguente: `[os].[version]-[arch]` dove:</span><span class="sxs-lookup"><span data-stu-id="f43cf-115">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[arch]` where:</span></span>
- <span data-ttu-id="f43cf-116">`[os]` è il sistema operativo moniker, ad esempio `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="f43cf-116">`[os]` is the operating system moniker, for example, `ubuntu`.</span></span>
- <span data-ttu-id="f43cf-117">`[version]` è la versione del sistema operativo indicata da un numero separato da punti (`.`), ad esempio `15.10`, e sufficientemente accurata da consentire ragionevolmente alle risorse di avere come destinazione le API della piattaforma del sistema operativo rappresentate dalla versione in oggetto.</span><span class="sxs-lookup"><span data-stu-id="f43cf-117">`[version]` is the operating system version in the form of a dot (`.`) separated version number, for example, `15.10`, accurate enough to reasonably enable assets to target operating system platform APIs represented by that version.</span></span>
  - <span data-ttu-id="f43cf-118">**Non deve** trattarsi di versioni di marketing, poiché tali versioni rappresentano spesso più versioni discrete del sistema operativo con una superficie di attacco delle API della piattaforma differente.</span><span class="sxs-lookup"><span data-stu-id="f43cf-118">This **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>
- <span data-ttu-id="f43cf-119">`[arch]` è l'architettura del processore, ad esempio `x86`, `x64`, `arm`, `arm64` e così via.</span><span class="sxs-lookup"><span data-stu-id="f43cf-119">`[arch]` is the processor architecture, for example, `x86`, `x64`, `arm`, `arm64`, etc.</span></span>

<span data-ttu-id="f43cf-120">Il grafico RID viene definito in un pacchetto denominato `Microsoft.NETCore.Platforms` in un file denominato `runtime.json`, che è possibile vedere l'[archivio CoreFX](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span><span class="sxs-lookup"><span data-stu-id="f43cf-120">The RID graph is defined in a package called `Microsoft.NETCore.Platforms` in a file called `runtime.json`, which you can see on the [CoreFX repo](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span></span> <span data-ttu-id="f43cf-121">Se si usa questo file, si noterà che alcuni dei RID contengono un'istruzione `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="f43cf-121">If you use this file, you will notice that some of the RIDs have an `"#import"` statement in them.</span></span> <span data-ttu-id="f43cf-122">Si tratta di istruzioni di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="f43cf-122">These statements are compatibility statements.</span></span> <span data-ttu-id="f43cf-123">Questo significa che un RID contenente un RID importato può rappresentare una destinazione per il ripristino di pacchetti per tale RID.</span><span class="sxs-lookup"><span data-stu-id="f43cf-123">That means that a RID that has an imported RID in it can be a target for restoring packages for that RID.</span></span> <span data-ttu-id="f43cf-124">L'affermazione precedente è poco chiara. Per questo motivo, di seguito è riportato un esempio</span><span class="sxs-lookup"><span data-stu-id="f43cf-124">Slightly confusing, but let's look at an example.</span></span> <span data-ttu-id="f43cf-125">riguardante MacOS:</span><span class="sxs-lookup"><span data-stu-id="f43cf-125">Let's take a look at macOS:</span></span>

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
<span data-ttu-id="f43cf-126">Il RID sopra riportato specifica che `osx.10.11-x64` importa `osx.10.10-x64`.</span><span class="sxs-lookup"><span data-stu-id="f43cf-126">The above RID specifies that `osx.10.11-x64` imports `osx.10.10-x64`.</span></span> <span data-ttu-id="f43cf-127">Questo significa che, durante il ripristino di pacchetti, NuGet sarà in grado di ripristinare quelli che specificano di richiedere `osx.10.10-x64` su `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="f43cf-127">This means that when restoring packages, NuGet will be able to restore packages that specify that they need `osx.10.10-x64` on `osx.10.11-x64`.</span></span>

<span data-ttu-id="f43cf-128">Di seguito è riportato un grafico RID di esempio di dimensioni leggermente maggiori:</span><span class="sxs-lookup"><span data-stu-id="f43cf-128">A slightly bigger example RID graph:</span></span>  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

<span data-ttu-id="f43cf-129">Tutti i RID finiscono per mappare nuovamente al RID `any` radice.</span><span class="sxs-lookup"><span data-stu-id="f43cf-129">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="f43cf-130">Anche se i RID sembrano semplici da usare, è necessario tenere presenti alcuni aspetti importanti:</span><span class="sxs-lookup"><span data-stu-id="f43cf-130">Although they look easy enough to use, there are some special things about RIDs that you have to keep in mind when working with them:</span></span>

* <span data-ttu-id="f43cf-131">Sono **stringhe opache** e devono essere trattati come black box</span><span class="sxs-lookup"><span data-stu-id="f43cf-131">They are **opaque strings** and should be treated as black boxes</span></span>
    * <span data-ttu-id="f43cf-132">Non si devono creare RID a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f43cf-132">You should not construct RIDs programmatically</span></span>
* <span data-ttu-id="f43cf-133">È necessario usare i RID già definiti nella piattaforma in uso, come mostrato in questo documento</span><span class="sxs-lookup"><span data-stu-id="f43cf-133">You need to use the RIDs that are already defined for the platform and this document shows that</span></span>
* <span data-ttu-id="f43cf-134">Non è necessario che i RID siano specifici, motivo per cui non bisogna presupporre nulla in base al valore effettivo del RID. Consultare questo documento per stabilire quali RID sono necessari per una determinata piattaforma</span><span class="sxs-lookup"><span data-stu-id="f43cf-134">The RIDs do need to be specific so don't assume anything from the actual RID value; please consult this document to determine which RID(s) you need for a given platform</span></span>

## <a name="using-rids"></a><span data-ttu-id="f43cf-135">Uso dei RID</span><span class="sxs-lookup"><span data-stu-id="f43cf-135">Using RIDs</span></span>
<span data-ttu-id="f43cf-136">Per usare i RID, è necessario sapere quali sono quelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="f43cf-136">In order to use RIDs, you have to know which RIDs there are.</span></span> <span data-ttu-id="f43cf-137">Alla piattaforma vengono regolarmente aggiunti nuovi RID.</span><span class="sxs-lookup"><span data-stu-id="f43cf-137">New RIDs are added regularly to the platform.</span></span> <span data-ttu-id="f43cf-138">Per la versione più recente, verificare il file [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) nell'archivio CoreFX.</span><span class="sxs-lookup"><span data-stu-id="f43cf-138">For the latest version, please check the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

> [!NOTE]
> <span data-ttu-id="f43cf-139">Microsoft sta lavorando per rendere disponibili queste informazioni in forma più interattiva.</span><span class="sxs-lookup"><span data-stu-id="f43cf-139">We are working towards getting this information into a more interactive form.</span></span> <span data-ttu-id="f43cf-140">Quando tale risultato sarà raggiunto, questa pagina verrà aggiornata in modo da puntare allo strumento in questione e/o alla documentazione sull'utilizzo dello stesso.</span><span class="sxs-lookup"><span data-stu-id="f43cf-140">When that happens, this page will be updated to point to that tool and/or its usage documentation.</span></span> 

## <a name="windows-rids"></a><span data-ttu-id="f43cf-141">RID Windows</span><span class="sxs-lookup"><span data-stu-id="f43cf-141">Windows RIDs</span></span>

* <span data-ttu-id="f43cf-142">Windows 7/Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f43cf-142">Windows 7 / Windows Server 2008 R2</span></span>
    * `win7-x64`
    * `win7-x86`
* <span data-ttu-id="f43cf-143">Windows 8/Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f43cf-143">Windows 8 / Windows Server 2012</span></span>
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* <span data-ttu-id="f43cf-144">Windows 8.1/Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f43cf-144">Windows 8.1 / Windows Server 2012 R2</span></span>
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* <span data-ttu-id="f43cf-145">Windows 10/Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f43cf-145">Windows 10 / Windows Server 2016</span></span>
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

## <a name="linux-rids"></a><span data-ttu-id="f43cf-146">RID Linux</span><span class="sxs-lookup"><span data-stu-id="f43cf-146">Linux RIDs</span></span>

* <span data-ttu-id="f43cf-147">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="f43cf-147">Red Hat Enterprise Linux</span></span>
    * `rhel.7-x64`
* <span data-ttu-id="f43cf-148">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f43cf-148">Ubuntu</span></span>
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* <span data-ttu-id="f43cf-149">CentOS</span><span class="sxs-lookup"><span data-stu-id="f43cf-149">CentOS</span></span>
    * `centos.7-x64`
* <span data-ttu-id="f43cf-150">Debian</span><span class="sxs-lookup"><span data-stu-id="f43cf-150">Debian</span></span>
    * `debian.8-x64`
* <span data-ttu-id="f43cf-151">Fedora</span><span class="sxs-lookup"><span data-stu-id="f43cf-151">Fedora</span></span>
    * `fedora.23-x64`
    * `fedora.24-x64`
* <span data-ttu-id="f43cf-152">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="f43cf-152">OpenSUSE</span></span>
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* <span data-ttu-id="f43cf-153">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="f43cf-153">Oracle Linux</span></span>
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* <span data-ttu-id="f43cf-154">Derivati Ubuntu attualmente supportati</span><span class="sxs-lookup"><span data-stu-id="f43cf-154">Currently supported Ubuntu derivatives</span></span> 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

## <a name="os-x-rids"></a><span data-ttu-id="f43cf-155">RID OS X</span><span class="sxs-lookup"><span data-stu-id="f43cf-155">OS X RIDs</span></span>

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`

