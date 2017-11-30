---
title: "Novità di .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="4d966-102">Novità di .NET Standard</span><span class="sxs-lookup"><span data-stu-id="4d966-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="4d966-103">.NET Standard è una specifica formale che definisce un set di API che devono essere disponibile nelle implementazioni .NET conformi con tale versione dello standard con controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="4d966-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="4d966-104">.NET Standard è destinato agli sviluppatori di librerie.</span><span class="sxs-lookup"><span data-stu-id="4d966-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="4d966-105">Una libreria che ha come destinazione una versione .NET Standard è utilizzabile in qualsiasi implementazione di .NET Framework, .NET Core o Xamarin che supporta tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="4d966-106">La versione più recente di .NET Standard è 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d966-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="4d966-107">È inclusa con il SDK 2.0 di .NET Core e con versione 15.3 2017 di Visual Studio con il carico di lavoro di .NET Core installato.</span><span class="sxs-lookup"><span data-stu-id="4d966-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="4d966-108">Implementazioni di .NET supportate</span><span class="sxs-lookup"><span data-stu-id="4d966-108">Supported .NET implementations</span></span>

<span data-ttu-id="4d966-109">Standard di .NET 2.0 è supportata tramite le implementazioni .NET seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d966-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="4d966-110">.NET core 2.0</span><span class="sxs-lookup"><span data-stu-id="4d966-110">.NET Core 2.0</span></span>
- <span data-ttu-id="4d966-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="4d966-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="4d966-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="4d966-112">Mono 5.4</span></span>
- <span data-ttu-id="4d966-113">Xamarin 10.14</span><span class="sxs-lookup"><span data-stu-id="4d966-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="4d966-114">3.8 Xamarin.Mac</span><span class="sxs-lookup"><span data-stu-id="4d966-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="4d966-115">Xamarin 8.0</span><span class="sxs-lookup"><span data-stu-id="4d966-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="4d966-116">Piattaforma Windows universale 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="4d966-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="4d966-117">Novità di .NET 2.0 Standard</span><span class="sxs-lookup"><span data-stu-id="4d966-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="4d966-118">Standard di .NET 2.0 include le nuove funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d966-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="4d966-119">**Un vasto set di API**</span><span class="sxs-lookup"><span data-stu-id="4d966-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="4d966-120">Alla versione 1.6, .NET Standard incluso un subset relativamente ridotto di API.</span><span class="sxs-lookup"><span data-stu-id="4d966-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="4d966-121">Tra quelli esclusi sono state molte API comunemente usati in .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="4d966-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="4d966-122">Ciò complica lo sviluppo, poiché richiede che gli sviluppatori troveranno sostituzioni appropriate per le API familiarità durante lo sviluppo di applicazioni e librerie destinate a più implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="4d966-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="4d966-123">.NET 2.0 Standard risolve questa limitazione aggiungendo le API più oltre 20.000 che erano disponibili in .NET Standard 1.6, la versione precedente dello standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="4d966-124">Per un elenco delle API che sono stati aggiunti a Standard di .NET 2.0, vedere [Visual Studio .NET 2.0 Standard 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="4d966-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="4d966-125">Alcune delle aggiunte di <xref:System> dello spazio dei nomi .NET 2.0 Standard includono:</span><span class="sxs-lookup"><span data-stu-id="4d966-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="4d966-126">Supporto per la <xref:System.AppDomain> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="4d966-127">Supporto migliorato per l'utilizzo di matrici da altri membri di <xref:System.Array> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="4d966-128">Supporto migliorato per lavorare con gli attributi da altri membri di <xref:System.Attribute> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="4d966-129">Calendario migliore supporto e le opzioni di formattazione aggiuntive per <xref:System.DateTime> valori.</span><span class="sxs-lookup"><span data-stu-id="4d966-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="4d966-130">Ulteriori <xref:System.Decimal> arrotondamento funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4d966-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="4d966-131">Funzionalità aggiuntive di <xref:System.Environment> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="4d966-132">Il controllo tramite il garbage collector tramite avanzato di <xref:System.GC> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="4d966-133">Supporto migliorato per confronto tra stringhe, enumerazione e la normalizzazione nel <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="4d966-134">Supporto per legale rettifiche e tempi di transizione nel <xref:System.TimeZoneInfo.AdjustmentRule> e <xref:System.TimeZoneInfo.TransitionTime> classi.</span><span class="sxs-lookup"><span data-stu-id="4d966-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="4d966-135">Sensibilmente migliorata e ora funzionalità di <xref:System.Type> classe.</span><span class="sxs-lookup"><span data-stu-id="4d966-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="4d966-136">Supporto migliorato per la deserializzazione di oggetti eccezione mediante l'aggiunta di un costruttore di eccezione con <xref:System.Runtime.Serialization.SerializationInfo> e <xref:System.Runtime.Serialization.StreamingContext> parametri.</span><span class="sxs-lookup"><span data-stu-id="4d966-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="4d966-137">**Supporto per le librerie .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4d966-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="4d966-138">La maggior parte delle librerie di destinazione di .NET Framework anziché .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="4d966-139">Tuttavia, la maggior parte delle chiamate in tali raccolte sono alle API incluse in .NET 2.0 Standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="4d966-140">A partire da .NET 2.0 Standard, è possibile accedere alle librerie .NET Framework da una libreria .NET Standard con un [shim di compatibilità](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="4d966-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="4d966-141">Questo livello di compatibilità è trasparente per gli sviluppatori; non è necessario eseguire alcuna operazione per sfruttare i vantaggi delle librerie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d966-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="4d966-142">L'unico requisito è che le API chiamate dalla libreria di classi .NET Framework devono essere incluso in .NET 2.0 Standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="4d966-143">**Supporto per Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="4d966-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="4d966-144">È ora possibile sviluppare le librerie Standard di .NET in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d966-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="4d966-145">Per gli sviluppatori di Visual Basic in Visual Studio 2017 versione 15.3 o versioni successive con il carico di lavoro di .NET Core installata, Visual Studio ora include un modello di libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="4d966-146">Per gli sviluppatori di Visual Basic che utilizzano altri strumenti di sviluppo e gli ambienti, è possibile utilizzare il [dotnet nuovo](../../core/tools/dotnet-new.md) comando per creare un progetto di libreria Standard di .NET.</span><span class="sxs-lookup"><span data-stu-id="4d966-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="4d966-147">Per ulteriori informazioni, vedere il [gli strumenti di supporto per le librerie .NET Standard](#tooling).</span><span class="sxs-lookup"><span data-stu-id="4d966-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="4d966-148"><a name="tooling" />**Strumenti di supporto per le librerie .NET Standard**</span><span class="sxs-lookup"><span data-stu-id="4d966-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="4d966-149">Con la versione di .NET Core 2.0 e .NET 2.0 Standard, entrambi 2017 Studio Visual e [.NET Core interfaccia della riga di comando (CLI)](../../core/tools/index.md) includono gli strumenti di supporto per la creazione di librerie .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="4d966-150">Se si installa Visual Studio con il **lo sviluppo multipiattaforma con .NET Core** carico di lavoro, è possibile creare un progetto di libreria .NET 2.0 Standard utilizzando un modello di progetto, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="4d966-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="4d966-151">C#</span><span class="sxs-lookup"><span data-stu-id="4d966-151">C#</span></span>](#tab/csharp)
![Aggiungere il progetto di libreria Standard di nuovo .NET](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="4d966-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d966-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Aggiungere il progetto di libreria Standard di nuovo .NET](./media/std-project-vb.png)
---

<span data-ttu-id="4d966-155">Se si utilizza l'interfaccia CLI Core .NET, le operazioni seguenti [dotnet nuovo](../../core/tools/dotnet-new.md) comando crea un progetto libreria di classi destinate a .NET 2.0 Standard.</span><span class="sxs-lookup"><span data-stu-id="4d966-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="4d966-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d966-156">See Also</span></span>
<span data-ttu-id="4d966-157">[.NET standard](../net-standard.md)
[Introduzione a .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="4d966-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
