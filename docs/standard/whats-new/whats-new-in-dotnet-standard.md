---
title: Novità di .NET Standard
description: Questo articolo riepiloga le nuove funzionalità e i miglioramenti disponibili in ogni nuova versione di .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 28d6a3546e08bbc3a7d4a26f08ba9cc5e16a901b
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438196"
---
# <a name="whats-new-in-net-standard"></a><span data-ttu-id="39d97-103">Novità di .NET Standard</span><span class="sxs-lookup"><span data-stu-id="39d97-103">What's new in .NET Standard</span></span>

<span data-ttu-id="39d97-104">.NET Standard è una specifica formale che definisce un set di API con controllo delle versioni che deve essere disponibile nelle implementazioni .NET conformi a tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="39d97-104">.NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="39d97-105">.NET Standard è destinato agli sviluppatori di librerie.</span><span class="sxs-lookup"><span data-stu-id="39d97-105">.NET Standard is targeted at library developers.</span></span> <span data-ttu-id="39d97-106">Una libreria che ha come destinazione una versione di .NET Standard è utilizzabile in qualsiasi implementazione di .NET Framework, .NET Core o Xamarin che supporta tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="39d97-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="39d97-107">.NET Standard è incluso in .NET Core SDK, nonché con Visual Studio quando si seleziona il carico di lavoro di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="39d97-107">.NET Standard is included with the .NET Core SDK, as well as with Visual Studio when you select the .NET Core workload.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="39d97-108">Implementazioni di .NET supportate</span><span class="sxs-lookup"><span data-stu-id="39d97-108">Supported .NET implementations</span></span>

<span data-ttu-id="39d97-109">.NET Standard 2.0 è supportato dalle seguenti implementazioni di .NET:</span><span class="sxs-lookup"><span data-stu-id="39d97-109">.NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="39d97-110">.NET Core 2.0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-110">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="39d97-111">.NET Framework 4.6.1 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-111">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="39d97-112">Mono 5.4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-112">Mono 5.4 or later</span></span>
- <span data-ttu-id="39d97-113">Xamarin.iOS 10.14 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-113">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="39d97-114">Xamarin.Mac 3.8 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-114">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="39d97-115">Xamarin.Android 8.0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-115">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="39d97-116">Piattaforma UWP (Universal Windows Platform) 10.0.16299 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="39d97-116">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-net-standard-20"></a><span data-ttu-id="39d97-117">Novità di .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="39d97-117">What's new in .NET Standard 2.0</span></span>

<span data-ttu-id="39d97-118">.NET Standard 2.0 include le seguenti nuove funzionalità:</span><span class="sxs-lookup"><span data-stu-id="39d97-118">.NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="39d97-119">Un set di API notevolmente ampliato</span><span class="sxs-lookup"><span data-stu-id="39d97-119">A vastly expanded set of APIs</span></span>

<span data-ttu-id="39d97-120">Tramite la versione 1.6, .NET Standard includeva un sottoinsieme relativamente piccolo di API.</span><span class="sxs-lookup"><span data-stu-id="39d97-120">Through version 1.6, .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="39d97-121">Molte API escluse erano tra quelle comunemente usate in .NET Framework o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="39d97-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="39d97-122">Ciò rende lo sviluppo più complesso, poiché gli sviluppatori devono trovare sostituzioni appropriate per le API a loro ben note durante lo sviluppo di applicazioni e librerie destinate a più implementazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="39d97-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="39d97-123">.NET Standard 2.0 risolve questa limitazione aggiungendo oltre 20.000 API in più rispetto a quelle disponibili in .NET Standard 1.6, la versione precedente dello standard.</span><span class="sxs-lookup"><span data-stu-id="39d97-123">.NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="39d97-124">Per un elenco delle API aggiunte a .NET Standard 2.0, vedere [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="39d97-124">For a list of the APIs that have been added to .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="39d97-125">Ecco alcune delle funzionalità aggiunte allo spazio dei nomi <xref:System> in .NET 2.0 Standard:</span><span class="sxs-lookup"><span data-stu-id="39d97-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="39d97-126">Supporto della classe <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="39d97-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="39d97-127">Supporto più efficiente dell'uso delle matrici da altri membri della classe <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="39d97-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="39d97-128">Supporto più efficiente per l'uso degli attributi da altri membri della classe <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="39d97-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="39d97-129">Supporto più efficiente del calendario e opzioni di formattazione aggiuntive per i valori <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="39d97-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="39d97-130">Funzionalità di arrotondamento <xref:System.Decimal> aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="39d97-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="39d97-131">Funzionalità aggiuntive nella classe <xref:System.Environment>.</span><span class="sxs-lookup"><span data-stu-id="39d97-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="39d97-132">Miglioramento del controllo sul Garbage Collector tramite la classe <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="39d97-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="39d97-133">Supporto più efficiente del confronto tra stringhe, dell'enumerazione e della normalizzazione nella classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="39d97-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="39d97-134">Supporto della rettifica relativa all'ora legale e dei tempi di transizione nelle classi <xref:System.TimeZoneInfo.AdjustmentRule> e <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="39d97-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="39d97-135">Sensibile miglioramento delle funzionalità nella classe <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="39d97-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="39d97-136">Supporto più efficiente della deserializzazione degli oggetti eccezione tramite l'aggiunta di un costruttore di eccezioni con parametri <xref:System.Runtime.Serialization.SerializationInfo> e <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="39d97-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="39d97-137">Supporto delle librerie di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="39d97-137">Support for .NET Framework libraries</span></span>

<span data-ttu-id="39d97-138">La stragrande maggioranza delle librerie è destinata a .NET Framework anziché a .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="39d97-138">The overwhelming majority of libraries target .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="39d97-139">Tuttavia, la maggior parte delle chiamate in tali librerie sono alle API incluse in .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="39d97-139">However, most of the calls in those libraries are to APIs that are included in .NET Standard 2.0.</span></span> <span data-ttu-id="39d97-140">A partire da .NET Standard 2.0, è possibile accedere alle librerie di .NET Framework da una libreria .NET Standard utilizzando uno shim di [compatibilità.](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification)</span><span class="sxs-lookup"><span data-stu-id="39d97-140">Starting with .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="39d97-141">Questo livello di compatibilità è trasparente per gli sviluppatori. Non è necessario eseguire alcuna operazione per sfruttare i vantaggi delle librerie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39d97-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="39d97-142">Il requisito unico è che le API chiamate dalla libreria di classi .NET Framework devono essere incluse in .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="39d97-142">The single requirement is that the APIs called by the .NET Framework class library must be included in .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="39d97-143">Supporto per Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39d97-143">Support for Visual Basic</span></span>

<span data-ttu-id="39d97-144">È ora possibile sviluppare librerie .NET Standard in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="39d97-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="39d97-145">Visual Studio 2019 e Visual Studio 2017 versione 15.3 o successiva con il carico di lavoro .NET Core installato includono un modello di libreria di classi standard .NET.</span><span class="sxs-lookup"><span data-stu-id="39d97-145">Visual Studio 2019 and Visual Studio 2017 version 15.3 or later with the .NET Core workload installed include a .NET Standard Class Library template.</span></span> <span data-ttu-id="39d97-146">Per gli sviluppatori Visual Basic che usano altri strumenti e ambienti di sviluppo, è possibile usare il comando [dotnet new](../../core/tools/dotnet-new.md) per creare un progetto di libreria .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="39d97-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="39d97-147">Per altre informazioni, vedere [Supporto degli strumenti per librerie .NET Standard](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="39d97-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="39d97-148">Supporto degli strumenti per librerie .NET Standard</span><span class="sxs-lookup"><span data-stu-id="39d97-148">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="39d97-149">Con il rilascio di .NET Core 2.0 e .NET Standard 2.0, sia Visual Studio 2017 [che .NET Core CLI](../../core/tools/index.md) includono il supporto degli strumenti per la creazione di librerie .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="39d97-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core CLI](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="39d97-150">Se si installa Visual Studio con il carico di lavoro di **sviluppo multipiattaforma .NET Core,** è possibile creare un progetto di libreria .NET Standard 2.0 utilizzando un modello di progetto, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="39d97-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="39d97-151">C #</span><span class="sxs-lookup"><span data-stu-id="39d97-151">C#</span></span>](#tab/csharp)

![Aggiungere un nuovo progetto di libreria .NET Standard](./media/std-project-cs.png)

<span data-ttu-id="39d97-153">Se si utilizza l'interfaccia della riga di comando di .NET Core, il [comando dotnet new](../../core/tools/dotnet-new.md) seguente crea un progetto di libreria di classi destinato a .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="39d97-153">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[<span data-ttu-id="39d97-154">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39d97-154">Visual Basic</span></span>](#tab/vb)

![Aggiungere un nuovo progetto di libreria .NET Standard](./media/std-project-vb.png)

<span data-ttu-id="39d97-156">Se si utilizza l'interfaccia della riga di comando di .NET Core, il [comando dotnet new](../../core/tools/dotnet-new.md) seguente crea un progetto di libreria di classi destinato a .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="39d97-156">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="39d97-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39d97-157">See also</span></span>

- [<span data-ttu-id="39d97-158">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="39d97-158">.NET Standard</span></span>](../net-standard.md)
- <span data-ttu-id="39d97-159">[Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/) (Introduzione a .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="39d97-159">[Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)</span></span>
