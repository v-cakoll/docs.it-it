---
title: Specifica di destinazioni multipiattaforma per librerie .NET
description: Procedure consigliate per la creazione di librerie .NET multipiattaforma.
ms.date: 08/12/2019
ms.openlocfilehash: 45eb67837c924558ec51381dd924abf9fd0fa315
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706517"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="91132-103">Specifica di destinazioni multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="91132-103">Cross-platform targeting</span></span>

<span data-ttu-id="91132-104">Il software .NET moderno supporta più sistemi operativi e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="91132-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="91132-105">È importante che le librerie open source .NET offrano supporto per il maggior numero possibile di sviluppatori, che stiano creando un sito Web ASP.NET ospitato in Azure o un gioco .NET in Unity.</span><span class="sxs-lookup"><span data-stu-id="91132-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="91132-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="91132-106">.NET Standard</span></span>

<span data-ttu-id="91132-107">L'uso di .NET Standard è il modo migliore per aggiungere il supporto multipiattaforma a una libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="91132-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="91132-108">[.NET Standard](../net-standard.md) è una specifica delle API .NET disponibili in tutte le implementazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="91132-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="91132-109">Scegliendo come destinazione .NET Standard è possibile creare librerie vincolate all'uso delle API di una determinata versione di .NET Standard, che possono quindi essere usate da tutte le piattaforme che implementano tale versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="91132-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="91132-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="91132-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="91132-111">La scelta di .NET Standard come destinazione e la corretta compilazione del progetto non garantiscono che la libreria verrà eseguita correttamente in tutte le piattaforme:</span><span class="sxs-lookup"><span data-stu-id="91132-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="91132-112">Le API specifiche della piattaforma avranno esito negativo nelle altre piattaforme.</span><span class="sxs-lookup"><span data-stu-id="91132-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="91132-113">Ad esempio, l'esecuzione di <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> avverrà correttamente in Windows e genererà un'eccezione <xref:System.PlatformNotSupportedException> in qualsiasi altro sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="91132-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="91132-114">Le API possono avere comportamenti diversi.</span><span class="sxs-lookup"><span data-stu-id="91132-114">APIs can behave differently.</span></span> <span data-ttu-id="91132-115">Ad esempio, le API reflection hanno caratteristiche di prestazioni diverse quando un'applicazione usa la compilazione Ahead Of Time in iOS o nella piattaforma UWP.</span><span class="sxs-lookup"><span data-stu-id="91132-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="91132-116">Il team di .NET [offre un analizzatore Roslyn](../analyzers/api-analyzer.md) che consente di individuare i possibili problemi.</span><span class="sxs-lookup"><span data-stu-id="91132-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="91132-117">**✔️ INIZIARE** includendo una destinazione `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="91132-117">**✔️ DO** start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="91132-118">La maggior parte delle librerie per utilizzo generico non necessita di API al di fuori di .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="91132-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="91132-119">.NET standard 2.0 è supportato da tutte le piattaforme moderne ed è il modo consigliato per supportare più piattaforme con una sola destinazione.</span><span class="sxs-lookup"><span data-stu-id="91132-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="91132-120">**❌ evitare** di includere una destinazione di `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="91132-120">**❌ AVOID** including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="91132-121">.NET standard 1.x è distribuito come set granulare di pacchetti NuGet, che crea un grafo delle dipendenze dei pacchetti di grandi dimensioni e obbliga gli sviluppatori a scaricare numerosi pacchetti durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="91132-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="91132-122">Le moderne piattaforme .NET, tra cui .NET Framework 4.6.1, la piattaforma UWP e Xamarin, supportano tutte .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="91132-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="91132-123">Scegliere come destinazione .NET Standard 1.x solo se è necessaria una piattaforma di destinazione meno recente.</span><span class="sxs-lookup"><span data-stu-id="91132-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="91132-124">**✔️ INCLUDERE** una destinazione `netstandard2.0` se è necessaria una destinazione `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="91132-124">**✔️ DO** include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="91132-125">Tutte le piattaforme che supportano .NET Standard 2.0 useranno la destinazione `netstandard2.0` con il vantaggio di avere un grafo dei pacchetti più piccolo, mentre le piattaforme precedenti continueranno a funzionare ed eseguiranno il fallback alla destinazione `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="91132-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="91132-126">**❌** non includere una destinazione .NET standard se la libreria si basa su un modello di app specifico della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="91132-126">**❌ DO NOT** include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="91132-127">Una libreria di toolkit di controlli della piattaforma UWP, ad esempio, dipende da un modello di app che è disponibile solo nella piattaforma UWP.</span><span class="sxs-lookup"><span data-stu-id="91132-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="91132-128">Le API specifiche del modello di app non saranno disponibili in .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="91132-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="91132-129">Multitargeting</span><span class="sxs-lookup"><span data-stu-id="91132-129">Multi-targeting</span></span>

<span data-ttu-id="91132-130">In alcuni casi è necessario accedere alle API specifiche del framework dalle librerie.</span><span class="sxs-lookup"><span data-stu-id="91132-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="91132-131">Il modo migliore per chiamare le API specifiche del framework consiste nell'usare il multitargeting, che compila il progetto per numerosi [framework di destinazione .NET](../frameworks.md) invece che per uno solo.</span><span class="sxs-lookup"><span data-stu-id="91132-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="91132-132">Per evitare ai consumer di dover eseguire la compilazione per i singoli framework, è consigliabile cercare di avere un output .NET Standard e uno o più output specifici del framework.</span><span class="sxs-lookup"><span data-stu-id="91132-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="91132-133">Con il multitargeting, tutti gli assembly vengono inseriti all'interno di un singolo pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91132-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="91132-134">I consumer possono quindi fare riferimento allo stesso pacchetto NuGet e scegliere l'implementazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="91132-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="91132-135">La libreria .NET Standard serve come libreria di fallback usata in tutti i casi ad eccezione di quelli in cui il pacchetto NuGet offre un'implementazione specifica del framework.</span><span class="sxs-lookup"><span data-stu-id="91132-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="91132-136">Il multitargeting consente di usare la compilazione condizionale nel codice e chiamare API specifiche del framework.</span><span class="sxs-lookup"><span data-stu-id="91132-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="91132-137">![Pacchetto NuGet con più assembly](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "Pacchetto NuGet con più assembly")</span><span class="sxs-lookup"><span data-stu-id="91132-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="91132-138">**✔️ Valutare** la scelta delle implementazioni .NET come destinazione in aggiunta a .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="91132-138">**✔️ CONSIDER** targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="91132-139">La scelta delle implementazioni .NET come destinazione consente di chiamare API specifiche della piattaforma al di fuori di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="91132-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="91132-140">Quando si esegue questa operazione, non eliminare il supporto per .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="91132-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="91132-141">Eseguire invece la generazione dall'implementazione e offrire API per le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="91132-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="91132-142">In questo modo, la libreria può essere usata ovunque e supporta l'abilitazione delle funzionalità in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91132-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

<span data-ttu-id="91132-143">**❌ evitare** il multitargeting, nonché la destinazione .NET standard, se il codice sorgente è lo stesso per tutte le destinazioni.</span><span class="sxs-lookup"><span data-stu-id="91132-143">**❌ AVOID** multi-targeting as well as targeting .NET Standard, if your source code is the same for all targets.</span></span>

> <span data-ttu-id="91132-144">L'assembly .NET Standard verrà usato automaticamente da NuGet.</span><span class="sxs-lookup"><span data-stu-id="91132-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="91132-145">La scelta come destinazione di singole implementazioni .NET comporta un aumento delle dimensioni di `*.nupkg` senza offrire alcun vantaggio.</span><span class="sxs-lookup"><span data-stu-id="91132-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="91132-146">**✔️ VALUTARE** l'aggiunta di una destinazione per `net461` quando si offre una destinazione `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="91132-146">**✔️ CONSIDER** adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span>

> <span data-ttu-id="91132-147">L'uso di .NET Standard 2.0 da .NET Framework presenta alcuni problemi che sono stati risolti in .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="91132-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="91132-148">È possibile migliorare l'esperienza per gli sviluppatori che usano ancora .NET Framework 4.6.1-4.7.1 offrendo loro un file binario compilato per .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="91132-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="91132-149">**✔️ DA FARE** Distribuire la libreria usando un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91132-149">**✔️ DO** distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="91132-150">NuGet selezionerà la destinazione migliore per lo sviluppatore evitandogli di dover scegliere l'implementazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="91132-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="91132-151">**✔️ USARE** la proprietà `TargetFrameworks` di un file di progetto quando si usa il multitargeting.</span><span class="sxs-lookup"><span data-stu-id="91132-151">**✔️ DO** use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="91132-152">**✔️ VALUTARE** l'uso di [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) con il multitargeting per la piattaforma UWP e Xamarin in quanto semplifica notevolmente il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="91132-152">**✔️ CONSIDER** using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="91132-153">Destinazioni precedenti</span><span class="sxs-lookup"><span data-stu-id="91132-153">Older targets</span></span>

<span data-ttu-id="91132-154">.NET consente di scegliere come destinazione versioni di .NET Framework per le quali non è più disponibile il supporto e piattaforme non più comunemente usate.</span><span class="sxs-lookup"><span data-stu-id="91132-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="91132-155">In questo modo, la libreria funzionerà con il maggior numero di destinazioni possibili, tuttavia sarà necessario lavoro aggiuntivo per trovare una soluzione alternativa per le API mancanti.</span><span class="sxs-lookup"><span data-stu-id="91132-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="91132-156">Considerando la copertura e le limitazioni, non vale più la pena scegliere come destinazione determinati framework.</span><span class="sxs-lookup"><span data-stu-id="91132-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="91132-157">**❌** non includere una destinazione libreria di classi portabile (PCL).</span><span class="sxs-lookup"><span data-stu-id="91132-157">**❌ DO NOT** include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="91132-158">Ad esempio `portable-net45+win8+wpa81+wp8`.</span><span class="sxs-lookup"><span data-stu-id="91132-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="91132-159">.NET standard è il modo moderno per supportare le librerie .NET multipiattaforma e sostituisce le librerie di classi portabili.</span><span class="sxs-lookup"><span data-stu-id="91132-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="91132-160">**❌** non includono destinazioni per le piattaforme .NET che non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="91132-160">**❌ DO NOT** include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="91132-161">Ad esempio, `SL4`, `WP`.</span><span class="sxs-lookup"><span data-stu-id="91132-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="91132-162">[Precedente](get-started.md)
>[Successivo](strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="91132-162">[Previous](get-started.md)
[Next](strong-naming.md)</span></span>
