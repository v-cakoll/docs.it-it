---
title: "Novità di .NET Standard"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="9a8ed-102">Novità di .NET Standard</span><span class="sxs-lookup"><span data-stu-id="9a8ed-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="9a8ed-103">.NET Standard è una specifica formale che definisce un set di API con versioni specifiche che devono essere disponibili nelle implementazioni .NET conformi a tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="9a8ed-104">.NET Standard è destinato agli sviluppatori di librerie.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="9a8ed-105">Una libreria che ha come destinazione una versione di .NET Standard è utilizzabile in qualsiasi implementazione di .NET Framework, .NET Core o Xamarin che supporta tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="9a8ed-106">La versione più recente di .NET Standard è la versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="9a8ed-107">Questa versione è inclusa con .NET Core 2.0 SDK e con Visual Studio 2017 versione 15.3 con il carico di lavoro .NET Core installato.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="9a8ed-108">Implementazioni di .NET supportate</span><span class="sxs-lookup"><span data-stu-id="9a8ed-108">Supported .NET implementations</span></span>

<span data-ttu-id="9a8ed-109">.NET Standard 2.0 è supportato dalle implementazioni .NET seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a8ed-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="9a8ed-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9a8ed-110">.NET Core 2.0</span></span>
- <span data-ttu-id="9a8ed-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="9a8ed-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="9a8ed-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="9a8ed-112">Mono 5.4</span></span>
- <span data-ttu-id="9a8ed-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="9a8ed-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="9a8ed-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="9a8ed-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="9a8ed-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="9a8ed-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="9a8ed-116">Piattaforma UWP (Universal Windows Platform) 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="9a8ed-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="9a8ed-117">Novità di .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="9a8ed-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="9a8ed-118">.NET Standard 2.0 include le nuove funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a8ed-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="9a8ed-119">**Un set di API notevolmente ampliato**</span><span class="sxs-lookup"><span data-stu-id="9a8ed-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="9a8ed-120">Nella versione 1.6 .NET Standard includeva un subset relativamente ridotto di API.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="9a8ed-121">Molte API escluse erano tra quelle comunemente usate in .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="9a8ed-122">Ciò rende lo sviluppo più complesso, poiché gli sviluppatori devono trovare sostituzioni appropriate per le API a loro ben note durante lo sviluppo di applicazioni e librerie destinate a più implementazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="9a8ed-123">.NET 2.0 Standard risolve questa limitazione rendendo disponibili più di 20.000 API rispetto a quelle disponibili in .NET Standard 1.6, la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="9a8ed-124">Per un elenco delle API aggiunte a .NET Standard 2.0, vedere [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md) (Confronto tra le versioni 2.0 e 1.6 di .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="9a8ed-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="9a8ed-125">Ecco alcune delle funzionalità aggiunte allo spazio dei nomi <xref:System> in .NET 2.0 Standard:</span><span class="sxs-lookup"><span data-stu-id="9a8ed-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="9a8ed-126">Supporto della classe <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="9a8ed-127">Supporto più efficiente dell'uso delle matrici da altri membri della classe <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="9a8ed-128">Supporto più efficiente per l'uso degli attributi da altri membri della classe <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="9a8ed-129">Supporto più efficiente del calendario e opzioni di formattazione aggiuntive per i valori <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="9a8ed-130">Funzionalità di arrotondamento <xref:System.Decimal> aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="9a8ed-131">Funzionalità aggiuntive nella classe <xref:System.Environment>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="9a8ed-132">Miglioramento del controllo sul Garbage Collector tramite la classe <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="9a8ed-133">Supporto più efficiente del confronto tra stringhe, dell'enumerazione e della normalizzazione nella classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="9a8ed-134">Supporto della rettifica relativa all'ora legale e dei tempi di transizione nelle classi <xref:System.TimeZoneInfo.AdjustmentRule> e <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="9a8ed-135">Sensibile miglioramento delle funzionalità nella classe <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="9a8ed-136">Supporto più efficiente della deserializzazione degli oggetti eccezione tramite l'aggiunta di un costruttore di eccezioni con parametri <xref:System.Runtime.Serialization.SerializationInfo> e <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="9a8ed-137">**Supporto delle librerie di .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9a8ed-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="9a8ed-138">La stragrande maggioranza delle librerie è destinata a .NET Framework anziché a .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="9a8ed-139">La maggior parte delle chiamate in tali librerie, tuttavia, riguardano API incluse in .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="9a8ed-140">A partire da .NET Standard 2.0, è possibile accedere alle librerie .NET Framework da una libreria .NET Standard tramite uno [shim di compatibilità](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="9a8ed-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="9a8ed-141">Questo livello di compatibilità è trasparente per gli sviluppatori. Non è necessario eseguire alcuna operazione per sfruttare i vantaggi delle librerie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="9a8ed-142">L'unico requisito è che le API chiamate dalla libreria di classi di .NET Framework siano incluse in .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="9a8ed-143">**Supporto per Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="9a8ed-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="9a8ed-144">È ora possibile sviluppare librerie .NET Standard in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="9a8ed-145">Per gli sviluppatori Visual Basic che usano Visual Studio 2017 versione 15.3 o versioni successive con il carico di lavoro di .NET Core installato, Visual Studio ora include un modello di librerie di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="9a8ed-146">Per gli sviluppatori Visual Basic che usano altri strumenti e ambienti di sviluppo, è possibile usare il comando [dotnet new](../../core/tools/dotnet-new.md) per creare un progetto di libreria .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="9a8ed-147">Per altre informazioni, vedere [Supporto degli strumenti per librerie .NET Standard](#tooling).</span><span class="sxs-lookup"><span data-stu-id="9a8ed-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="9a8ed-148"><a name="tooling" />**Supporto degli strumenti per librerie .NET Standard**</span><span class="sxs-lookup"><span data-stu-id="9a8ed-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="9a8ed-149">Con la versione 2.0 di .NET Core e .NET Standard, sia Visual Studio 2017 che l'[interfaccia della riga di comando di .NET Core](../../core/tools/index.md) includono il supporto degli strumenti per la creazione di librerie .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="9a8ed-150">Se si installa Visual Studio con il carico di lavoro **Sviluppo multipiattaforma .NET Core**, è possibile creare un progetto di libreria .NET Standard 2.0 usando un modello di progetto, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="9a8ed-151">C#</span><span class="sxs-lookup"><span data-stu-id="9a8ed-151">C#</span></span>](#tab/csharp)
![Aggiungere un nuovo progetto di libreria .NET Standard](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9a8ed-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a8ed-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Aggiungere un nuovo progetto di libreria .NET Standard](./media/std-project-vb.png)
---

<span data-ttu-id="9a8ed-155">Se si usa l'interfaccia della riga di comando di .NET Core, il comando [dotnet new](../../core/tools/dotnet-new.md) seguente crea un progetto di libreria di classi destinata a .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a8ed-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="9a8ed-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a8ed-156">See Also</span></span>
<span data-ttu-id="9a8ed-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/) (Presentazione di .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="9a8ed-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
