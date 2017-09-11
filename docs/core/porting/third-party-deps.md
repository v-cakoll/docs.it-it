---
title: "Portabilità in .NET Core - Analisi delle dipendenze di terze parti"
description: "Portabilità in .NET Core - Analisi delle dipendenze di terze parti"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a074978f2817abafa7b8a9fefe7c67c9c52195b3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a><span data-ttu-id="6793c-104">Portabilità in .NET Core - Analisi delle dipendenze di terze parti</span><span class="sxs-lookup"><span data-stu-id="6793c-104">Porting to .NET Core - Analyzing your Third-Party Party Dependencies</span></span>

<span data-ttu-id="6793c-105">Il primo passaggio nel processo di trasferimento consiste nel comprendere le dipendenze di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6793c-105">The first step in the porting process is to understand your third party dependencies.</span></span>  <span data-ttu-id="6793c-106">È necessario capire se alcune di esse non vengono ancora eseguite su .NET Core e sviluppare un piano di emergenza adeguato.</span><span class="sxs-lookup"><span data-stu-id="6793c-106">You need to figure out which of them, if any, don't yet run on .NET Core, and develop a contingency plan for those which don't run on .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6793c-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6793c-107">Prerequisites</span></span>

<span data-ttu-id="6793c-108">Questo articolo presuppone che si usino Windows e Visual Studio e che si disponga di codice attualmente in esecuzione su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6793c-108">This article will assume you are using Windows and Visual Studio, and that you have code which runs on the .NET Framework today.</span></span>

## <a name="analyzing-nuget-packages"></a><span data-ttu-id="6793c-109">Analisi dei pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="6793c-109">Analyzing NuGet Packages</span></span>

<span data-ttu-id="6793c-110">L'analisi dei pacchetti NuGet per la portabilità è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="6793c-110">Analyzing NuGet packages for portability is very easy.</span></span>  <span data-ttu-id="6793c-111">Poiché un pacchetto NuGet è un set di cartelle che contengono gli assembly specifici della piattaforma, è sufficiente verificare se è presente una cartella che contiene un assembly .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6793c-111">Because a NuGet package is itself a set of folders which contain platform-specific assemblies, all you have to do is check to see if there is a folder which contains a .NET Core assembly.</span></span>

<span data-ttu-id="6793c-112">L'esplorazione delle cartelle del pacchetto NuGet è più semplice con lo strumento [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="6793c-112">Inspecting NuGet Package folders is easiest with the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span>  <span data-ttu-id="6793c-113">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="6793c-113">Here's how to do it.</span></span>

1. <span data-ttu-id="6793c-114">Scaricare e aprire NuGet Package Explorer.</span><span class="sxs-lookup"><span data-stu-id="6793c-114">Download and open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="6793c-115">Fare clic su "Open package from online feed" (Apri il pacchetto dal feed online).</span><span class="sxs-lookup"><span data-stu-id="6793c-115">Click "Open package from online feed".</span></span>
3. <span data-ttu-id="6793c-116">Cercare il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6793c-116">Search for the name of the package.</span></span>
4. <span data-ttu-id="6793c-117">Espandere la cartella "lib" sul lato destro e osservare i nomi delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="6793c-117">Expand the "lib" folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="6793c-118">È inoltre possibile visualizzare gli elementi supportati da un pacchetto in [nuget.org](https://www.nuget.org/) nella sezione **Dependencies** (Dipendenze) della pagina del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6793c-118">You can also see what a package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the page for that package.</span></span>

<span data-ttu-id="6793c-119">In entrambi i casi, è necessario cercare una cartella o una voce in [nuget.org](https://www.nuget.org/) con uno qualsiasi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6793c-119">In either case, you'll need to look for a folder or entry on [nuget.org](https://www.nuget.org/) with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="6793c-120">Si tratta dei Target Framework Moniker (TFM) che corrispondono alle versioni di [.NET Standard](../../standard/net-standard.md) e dei profili tradizionali della libreria di classi portabile compatibili con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6793c-120">These are the Target Framework Monikers (TFM) which map to versions of the [.NET Standard](../../standard/net-standard.md) and traditional Portable Class Library (PCL) profiles which are compatible with .NET Core.</span></span>  <span data-ttu-id="6793c-121">Si noti che `netcoreapp1.0`, anche se compatibile, è adatto alle applicazioni non alle librerie.</span><span class="sxs-lookup"><span data-stu-id="6793c-121">Note that `netcoreapp1.0`, while compatible, is for applications and not libraries.</span></span>  <span data-ttu-id="6793c-122">Anche se non vi sono problemi con l'uso di una libreria basata su `netcoreapp1.0`, è possibile che tale libreria non sia prevista per un utilizzo *diverso* da quello per le applicazioni `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="6793c-122">Although there's nothing wrong with using a library which is `netcoreapp1.0`-based, that library may not be intended for anything *other* than consumption by other `netcoreapp1.0` applications.</span></span>

<span data-ttu-id="6793c-123">Sono disponibili anche alcuni TFM legacy usati nelle versioni provvisorie di .NET Core che possono essere compatibili:</span><span class="sxs-lookup"><span data-stu-id="6793c-123">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="6793c-124">**Anche se questi funzioneranno con il codice, non esiste alcuna garanzia di compatibilità**.</span><span class="sxs-lookup"><span data-stu-id="6793c-124">**While these will likely work with your code, there is no guarantee of compatibility**.</span></span>  <span data-ttu-id="6793c-125">I pacchetti con questi TFM sono stati creati con le versioni provvisorie dei pacchetti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6793c-125">Packages with these TFMs were built with pre-release .NET Core packages.</span></span>  <span data-ttu-id="6793c-126">Prendere nota di quando (o se) pacchetti come questo sono aggiornati per essere basati su `netstandard`.</span><span class="sxs-lookup"><span data-stu-id="6793c-126">Take note of when (or if) packages like this are updated to be `netstandard`-based.</span></span>

> [!NOTE]
> <span data-ttu-id="6793c-127">Per usare un pacchetto che ha come destinazione una libreria di classi portabile tradizionale o una versione provvisoria di .NET Core, è necessario usare la direttiva `imports` nel file `project.json`.</span><span class="sxs-lookup"><span data-stu-id="6793c-127">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `imports` directive in your `project.json` file.</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="6793c-128">Operazioni da eseguire quando una dipendenza del pacchetto NuGet non viene eseguita in .NET Core</span><span class="sxs-lookup"><span data-stu-id="6793c-128">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="6793c-129">Se la dipendenza da un pacchetto NuGet non viene eseguita in .NET Core, è possibile effettuare alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="6793c-129">There are a few things you can do if a NuGet package you depend on won't run on .NET Core.</span></span>

1. <span data-ttu-id="6793c-130">Se il progetto è open source e ospitato in una posizione come GitHub, è possibile coinvolgere direttamente gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="6793c-130">If the project is open source and hosted somewhere like GitHub, you can engage the developer(s) directly.</span></span>
2. <span data-ttu-id="6793c-131">È possibile contattare l'autore direttamente su [nuget.org](https://www.nuget.org/) cercando il pacchetto e facendo clic su "Contact Owners" (Contatta i proprietari) sul lato sinistro della pagina del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6793c-131">You can contact the author directly on [nuget.org](https://www.nuget.org/) by searching for the package and clicking "Contact Owners" on the left hand side of the package's page.</span></span>
3. <span data-ttu-id="6793c-132">È possibile cercare un altro pacchetto che viene eseguito in .NET Core e che esegue la stessa attività del pacchetto in uso.</span><span class="sxs-lookup"><span data-stu-id="6793c-132">You can look for another package that runs on .NET Core which accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="6793c-133">È possibile tentare di scrivere autonomamente il codice eseguito dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6793c-133">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="6793c-134">È inoltre possibile eliminare la dipendenza del pacchetto modificando la funzionalità dell'app, almeno fino a quando una versione compatibile del pacchetto non diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="6793c-134">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="6793c-135">Si ricordi che i gestori di progetti open source e gli autori di pacchetti NuGet sono spesso volontari che contribuiscono perché interessati a un determinato dominio, lo fanno gratuitamente e spesso si occupano di altro.</span><span class="sxs-lookup"><span data-stu-id="6793c-135">Please remember that open source project maintainers and NuGet package publishers are often volunteers who contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="6793c-136">Se si riesce a mettersi in comunicazione, è consigliabile iniziare con un'affermazione positiva sulla libreria prima di chiedere supporto per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6793c-136">If you do reach out, you might start with a positive statement about the library before asking about .NET Core support.</span></span>

<span data-ttu-id="6793c-137">Se non si riesce a risolvere il problema con nessuna delle indicazioni precedenti, è possibile che si debba eseguire il trasferimento in .NET Core in un altro momento.</span><span class="sxs-lookup"><span data-stu-id="6793c-137">If you're unable to resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="6793c-138">Per il team di .NET è molto importante sapere quali librerie risultano più importanti, al fine di migliorare il supporto di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6793c-138">The .NET Team would like to know which libraries are the most important to support next with .NET Core.</span></span> <span data-ttu-id="6793c-139">È possibile anche inviare un messaggio di posta elettronica sulle librerie preferite all'indirizzo dotnet@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6793c-139">You can also send us mail at dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a><span data-ttu-id="6793c-140">Analisi delle dipendenze non appartenenti ai pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="6793c-140">Analyzing Dependencies which aren't NuGet Packages</span></span>

<span data-ttu-id="6793c-141">È possibile disporre di dipendenze non appartenenti a un pacchetto NuGet, ad esempio una DLL nel file system.</span><span class="sxs-lookup"><span data-stu-id="6793c-141">You may have a dependency that isn't a NuGet package, such as a DLL in the filesystem.</span></span>  <span data-ttu-id="6793c-142">L'unico modo per determinare la portabilità di tale dipendenza è l'esecuzione dello [strumento ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="6793c-142">The only way to determine the portability of that dependency is to run the [ApiPort tool](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6793c-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6793c-143">Next steps</span></span>

<span data-ttu-id="6793c-144">Se si esegue il trasferimento di una libreria, consultare [Porting your Libraries](libraries.md) (Portabilità delle librerie).</span><span class="sxs-lookup"><span data-stu-id="6793c-144">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>

