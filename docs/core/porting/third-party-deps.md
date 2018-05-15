---
title: Portabilità in .NET Core - Analisi delle dipendenze di terze parti
description: Informazioni su come analizzare le dipendenze di terze parti per trasferire il progetto da .NET Framework a .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 02/15/2018
ms.openlocfilehash: a5affd8f1c493a87b2a4f7cd4096d168d404626a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="analyze-your-third-party-dependencies"></a><span data-ttu-id="cae01-103">Analisi delle dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="cae01-103">Analyze your third-party dependencies</span></span>

<span data-ttu-id="cae01-104">Per trasferire codice a .NET Core o .NET Standard, la prima fase del processo è la definizione delle dipendenze di terze parti.</span><span class="sxs-lookup"><span data-stu-id="cae01-104">If you're looking to port your code to .NET Core or .NET Standard, the first step in the porting process is to understand your third-party dependencies.</span></span> <span data-ttu-id="cae01-105">Le dipendenze di terze parti sono [pacchetti NuGet](#analyze-referenced-nuget-packages-on-your-project) o [DLL](#analyze-dependencies-that-arent-nuget-packages) a cui si fa riferimento nel progetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-105">Third-party dependencies are either [NuGet packages](#analyze-referenced-nuget-packages-on-your-project) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you're referencing in your project.</span></span> <span data-ttu-id="cae01-106">È necessario valutare le singole dipendenze e definire un piano di emergenza per le dipendenze non compatibili con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-106">Evaluate each dependency and develop a contingency plan for the dependencies that aren't compatible with .NET Core.</span></span> <span data-ttu-id="cae01-107">Questo articolo illustra come determinare se la dipendenza è compatibile con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-107">This article shows you how to determine if the dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-project"></a><span data-ttu-id="cae01-108">Analizzare i pacchetti NuGet cui si fa riferimento nel progetto</span><span class="sxs-lookup"><span data-stu-id="cae01-108">Analyze referenced NuGet packages in your project</span></span>

<span data-ttu-id="cae01-109">Se il progetto contiene riferimenti a pacchetti NuGet, è necessario verificare se i pacchetti sono compatibili con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-109">If you're referencing NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="cae01-110">È possibile ottenere questo risultato in due modi:</span><span class="sxs-lookup"><span data-stu-id="cae01-110">There are two ways to accomplish that:</span></span>

* <span data-ttu-id="cae01-111">[Tramite l'app NuGet Package Explorer](#analyze-nuget-packages-using-nuget-package-explorer) (il metodo più affidabile).</span><span class="sxs-lookup"><span data-stu-id="cae01-111">[Using the NuGet Package Explorer app](#analyze-nuget-packages-using-nuget-package-explorer) (the most reliable method).</span></span>
* <span data-ttu-id="cae01-112">[Tramite il sito nuget.org](#analyze-nuget-packages-using-nugetorg).</span><span class="sxs-lookup"><span data-stu-id="cae01-112">[Using the nuget.org site](#analyze-nuget-packages-using-nugetorg).</span></span>

<span data-ttu-id="cae01-113">Dopo l'analisi dei pacchetti, se questi non sono compatibili con .NET Core e supportano solo .NET Framework, sarà possibile verificare se la [modalità di compatibilità .NET Framework](#net-framework-compatibility-mode) risulta utile per il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="cae01-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="cae01-114">Analizzare i pacchetti NuGet usando NuGet Package Explorer</span><span class="sxs-lookup"><span data-stu-id="cae01-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="cae01-115">Un pacchetto NuGet è un set di cartelle contenenti assembly specifici per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="cae01-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="cae01-116">Pertanto è necessario verificare se nel pacchetto è presente una cartella che contiene un assembly compatibile.</span><span class="sxs-lookup"><span data-stu-id="cae01-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="cae01-117">Il metodo più semplice per esaminare le cartelle del pacchetto NuGet è lo strumento [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="cae01-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="cae01-118">Dopo aver installato lo strumento seguire questa procedura per visualizzare i nomi delle cartelle:</span><span class="sxs-lookup"><span data-stu-id="cae01-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="cae01-119">Aprire NuGet Package Explorer.</span><span class="sxs-lookup"><span data-stu-id="cae01-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="cae01-120">Fare clic su **Open package from online feed** (Apri il pacchetto dal feed online).</span><span class="sxs-lookup"><span data-stu-id="cae01-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="cae01-121">Cercare il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="cae01-122">Selezionare il nome del pacchetto nei risultati della ricerca e fare clic su **open** (Apri).</span><span class="sxs-lookup"><span data-stu-id="cae01-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="cae01-123">Espandere la cartella *lib* sul lato destro per visualizzare i nomi delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="cae01-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="cae01-124">Cercare una cartella con uno dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cae01-124">Look for a folder with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="cae01-125">Questi valori sono i [Target Framework Moniker (TFM)](../../standard/frameworks.md) che corrispondono a versioni dei profili [.NET Standard](../../standard/net-standard.md), .NET Core e dei tradizionali profili della libreria di classi portabile (PCL) compatibili con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cae01-126">Quando si esaminano i TFM supportati da un pacchetto, si noti che `netcoreapp*` è compatibile, ma è destinato solo ai progetti .NET Core e non ai progetti .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="cae01-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="cae01-127">Una libreria che supporta solo `netcoreapp*` ma non `netstandard*` può essere usata solo da altre applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

<span data-ttu-id="cae01-128">Sono disponibili anche alcuni TFM legacy usati nelle versioni provvisorie di .NET Core che possono essere compatibili:</span><span class="sxs-lookup"><span data-stu-id="cae01-128">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="cae01-129">È possibile che questi TFM funzionino con il codice, ma la loro compatibilità non è garantita.</span><span class="sxs-lookup"><span data-stu-id="cae01-129">While these TFMs likely work with your code, there is no guarantee of compatibility.</span></span> <span data-ttu-id="cae01-130">I pacchetti con questi TFM sono stati creati con le versioni provvisorie dei pacchetti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-130">Packages with these TFMs were built with pre-release .NET Core packages.</span></span> <span data-ttu-id="cae01-131">Rilevare se o in che data i pacchetti che usano questi TFM vengono aggiornati in modo che siano basati su .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="cae01-131">Take note of when (or if) packages using these TFMs are updated to be .NET Standard-based.</span></span>

> [!NOTE]
> <span data-ttu-id="cae01-132">Per usare un pacchetto che ha come destinazione una libreria di classi portabile tradizionale o una versione provvisoria di .NET Core, è necessario usare l'elemento MSBuild `PackageTargetFallback` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-132">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `PackageTargetFallback` MSBuild element in your project file.</span></span>
> <span data-ttu-id="cae01-133">Per altre informazioni su questo elemento MSBuild, vedere [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).</span><span class="sxs-lookup"><span data-stu-id="cae01-133">For more information about this MSBuild element, see [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="cae01-134">Analizzare i pacchetti NuGet usando nuget.org</span><span class="sxs-lookup"><span data-stu-id="cae01-134">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="cae01-135">In alternativa è possibile visualizzare i TFM supportati da ogni pacchetto in [nuget.org](https://www.nuget.org/) nella sezione **Dependencies** (Dipendenze) della pagina del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-135">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="cae01-136">La verifica della compatibilità risulta più semplice nel sito, ma le informazioni presenti in **Dependencies** (Dipendenze) non sono disponibili per tutti i pacchetti nel sito.</span><span class="sxs-lookup"><span data-stu-id="cae01-136">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="cae01-137">Modalità di compatibilità di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cae01-137">.NET Framework compatibility mode</span></span>

<span data-ttu-id="cae01-138">Il risultato dell'analisi dei pacchetti NuGet può essere che i pacchetti supportano solo .NET Framework, come la maggior parte dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="cae01-138">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="cae01-139">A partire da .NET Standard 2.0 è stata introdotta la modalità di compatibilità di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cae01-139">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="cae01-140">Questa modalità consente a progetti .NET Standard e .NET Core di gestire riferimenti a librerie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cae01-140">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="cae01-141">I riferimenti alle librerie .NET Framework non funzionano per tutti i progetti, ad esempio se la libreria usa API Windows Presentation Foundation (WPF), ma sono in grado di risolvere molti scenari di portabilità.</span><span class="sxs-lookup"><span data-stu-id="cae01-141">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="cae01-142">Quando nel progetto si fa riferimento a pacchetti NuGet che supportano .NET Framework, ad esempio [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), viene visualizzato un avviso di fallback del pacchetto ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cae01-142">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="cae01-143">Questo avviso viene visualizzato quando si aggiunge il pacchetto e ogni volta che si esegue la compilazione, per garantire che il pacchetto venga testato con il progetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-143">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="cae01-144">Se il progetto funziona come previsto, è possibile eliminare l'avviso modificando le proprietà del pacchetto in Visual Studio o modificando manualmente il file di progetto nell'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="cae01-144">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="cae01-145">Per eliminare l'avviso modificando il file di progetto, trovare la voce `PackageReference` del pacchetto per il quale si vuole eliminare l'avviso e aggiungere l'attributo `NoWarn`.</span><span class="sxs-lookup"><span data-stu-id="cae01-145">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="cae01-146">L'attributo `NoWarn` accetta un elenco delimitato da virgole di tutti gli ID avviso.</span><span class="sxs-lookup"><span data-stu-id="cae01-146">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="cae01-147">L'esempio seguente illustra come eliminare l'avviso `NU1701` per il pacchetto `Huitian.PowerCollections` modificando manualmente il file di progetto:</span><span class="sxs-lookup"><span data-stu-id="cae01-147">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="cae01-148">Per altre informazioni sull'eliminazione degli avvisi del compilatore in Visual Studio, vedere [Non visualizzare avvisi per i pacchetti NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span><span class="sxs-lookup"><span data-stu-id="cae01-148">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="cae01-149">Operazioni da eseguire quando una dipendenza del pacchetto NuGet non viene eseguita in .NET Core</span><span class="sxs-lookup"><span data-stu-id="cae01-149">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="cae01-150">Se un pacchetto NuGet importante non può essere eseguito in .NET Core, è possibile provare varie soluzioni:</span><span class="sxs-lookup"><span data-stu-id="cae01-150">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="cae01-151">Se il progetto è open source e ospitato in una posizione come GitHub, è possibile coinvolgere direttamente gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="cae01-151">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="cae01-152">È possibile contattare direttamente l'autore in [nuget.org](https://www.nuget.org/). Cercare il pacchetto e fare clic su **Contact Owners** (Contatta proprietari) sul lato sinistro della pagina del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-152">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="cae01-153">È possibile cercare un altro pacchetto che supporta .NET Core ed esegue la stessa attività del pacchetto in uso.</span><span class="sxs-lookup"><span data-stu-id="cae01-153">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="cae01-154">È possibile tentare di scrivere autonomamente il codice eseguito dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cae01-154">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="cae01-155">È inoltre possibile eliminare la dipendenza del pacchetto modificando la funzionalità dell'app, almeno fino a quando una versione compatibile del pacchetto non diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="cae01-155">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="cae01-156">Tenere presente che spesso i gestori di progetti open source e gli autori di pacchetti NuGet sono volontari.</span><span class="sxs-lookup"><span data-stu-id="cae01-156">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="cae01-157">Questi utenti offrono il loro contributo a titolo gratuito perché sono interessati a un determinato argomento e in molti casi svolgono un'altra attività.</span><span class="sxs-lookup"><span data-stu-id="cae01-157">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="cae01-158">Tenere presente questo aspetto quando si richiede loro supporto per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-158">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="cae01-159">Se non si riesce a risolvere il problema con nessuna delle indicazioni precedenti, potrebbe essere necessario rimandare il trasferimento a .NET Core a una data successiva.</span><span class="sxs-lookup"><span data-stu-id="cae01-159">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="cae01-160">Il team .NET è interessato a sapere quali sono le librerie più importanti da supportare in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-160">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="cae01-161">È possibile inviare un messaggio di posta elettronica indicando le librerie preferite all'indirizzo dotnet@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cae01-161">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="cae01-162">Analizzare le dipendenze che non sono pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="cae01-162">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="cae01-163">Nel file system può essere presente una dipendenza diversa da un pacchetto NuGet, ad esempio una DLL.</span><span class="sxs-lookup"><span data-stu-id="cae01-163">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="cae01-164">L'unico metodo per determinare la portabilità di tale dipendenza è l'esecuzione dello strumento [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport).</span><span class="sxs-lookup"><span data-stu-id="cae01-164">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="cae01-165">Lo strumento può analizzare gli assembly che supportano .NET Framework e identificare le API non trasferibili ad altre piattaforme .NET come .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cae01-165">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="cae01-166">È possibile eseguire lo strumento come applicazione console o come [estensione di Visual Studio](../../standard/analyzers/portability-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="cae01-166">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cae01-167">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cae01-167">Next steps</span></span>

<span data-ttu-id="cae01-168">Se si esegue il trasferimento di una libreria, consultare [Porting your Libraries](libraries.md) (Portabilità delle librerie).</span><span class="sxs-lookup"><span data-stu-id="cae01-168">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
