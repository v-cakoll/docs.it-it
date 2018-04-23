---
title: Organizzare il progetto per il supporto di .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
keywords: .NET, .NET Core, .NET Framework, layout di progetto, più framework
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
ms.workload:
- dotnetcore
ms.openlocfilehash: 2392c6e477138e21dc98055fe7ecca84789f07af
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a><span data-ttu-id="de8a7-104">Organizzare il progetto per il supporto di .NET Framework e .NET Core</span><span class="sxs-lookup"><span data-stu-id="de8a7-104">Organizing your project to support .NET Framework and .NET Core</span></span>

<span data-ttu-id="de8a7-105">Questo articolo offre indicazioni per i responsabili di progetto che intendono compilare la propria soluzione affiancando .NET Framework e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="de8a7-105">This article helps project owners who want to compile their solution against .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="de8a7-106">Offre diverse opzioni per organizzare i progetti in modo da consentire agli sviluppatori di raggiungere tale obiettivo.</span><span class="sxs-lookup"><span data-stu-id="de8a7-106">It provides several options to organize projects to help developers achieve this goal.</span></span> <span data-ttu-id="de8a7-107">L'elenco seguente visualizza alcuni scenari tipici da considerare per la scelta della modalità di configurazione del layout di progetto da usare con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="de8a7-107">The following list provides some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="de8a7-108">È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="de8a7-108">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="de8a7-109">[**Combinare progetti esistenti e progetti .NET Core in singoli progetti**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="de8a7-109">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="de8a7-110">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="de8a7-110">*What this is good for:*</span></span>
  * <span data-ttu-id="de8a7-111">Semplificazione del processo di compilazione mediante la compilazione di un singolo progetto piuttosto che di progetti multipli, ciascuno destinato a una versione o a una piattaforma differente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de8a7-111">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="de8a7-112">Semplificazione della gestione di file di origine per progetti con più destinazioni perché è necessario gestire un unico file di progetto.</span><span class="sxs-lookup"><span data-stu-id="de8a7-112">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="de8a7-113">Quando si aggiungono o rimuovono i file di origine, le alternative richiedono una sincronizzazione manuale di questi file con altri progetti.</span><span class="sxs-lookup"><span data-stu-id="de8a7-113">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="de8a7-114">Generazione semplificata di un pacchetto NuGet per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="de8a7-114">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="de8a7-115">Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.</span><span class="sxs-lookup"><span data-stu-id="de8a7-115">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="de8a7-116">*Scenari non supportati:*</span><span class="sxs-lookup"><span data-stu-id="de8a7-116">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="de8a7-117">Gli sviluppatori devono usare Visual Studio 2017 per aprire i progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="de8a7-117">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="de8a7-118">Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="de8a7-118">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="de8a7-119">[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="de8a7-119">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="de8a7-120">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="de8a7-120">*What this is good for:*</span></span>
  * <span data-ttu-id="de8a7-121">Supporto per lo sviluppo di progetti esistenti, senza necessità di aggiornamento per sviluppatori/collaboratori che non dispongono di Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="de8a7-121">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="de8a7-122">Riduzione della possibilità di creazione di nuovi bug nei progetti esistenti in quanto non è necessaria alcuna varianza del codice nei progetti.</span><span class="sxs-lookup"><span data-stu-id="de8a7-122">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="de8a7-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="de8a7-123">Example</span></span>

<span data-ttu-id="de8a7-124">Si consideri il repository seguente:</span><span class="sxs-lookup"><span data-stu-id="de8a7-124">Consider the repository below:</span></span>

<span data-ttu-id="de8a7-125">![Progetto esistente][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="de8a7-125">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="de8a7-126">[**Codice sorgente**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="de8a7-126">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="de8a7-127">Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="de8a7-127">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="de8a7-128">Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni</span><span class="sxs-lookup"><span data-stu-id="de8a7-128">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="de8a7-129">Riorganizzare il repository in modo che venga rimosso qualsiasi file *\*csproj* esistente e venga creato un singolo file *\*csproj* destinato a più framework.</span><span class="sxs-lookup"><span data-stu-id="de8a7-129">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="de8a7-130">Questa è un'ottima opzione perché consente di compilare un singolo progetto per diversi framework.</span><span class="sxs-lookup"><span data-stu-id="de8a7-130">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="de8a7-131">Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de8a7-131">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="de8a7-132">![Creare un file csproj con più framework come destinazione][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="de8a7-132">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="de8a7-133">[**Codice sorgente**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="de8a7-133">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="de8a7-134">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="de8a7-134">Changes to note are:</span></span>
* <span data-ttu-id="de8a7-135">Sostituzione di *packages.config* e *\*csproj* con un nuovo [.NET Core *\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="de8a7-135">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="de8a7-136">I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="de8a7-136">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="de8a7-137">Mantenere i progetti esistenti e creare un progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="de8a7-137">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="de8a7-138">Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.</span><span class="sxs-lookup"><span data-stu-id="de8a7-138">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="de8a7-139">![Progetto .NET Core con un progetto esistente in un'altra cartella][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="de8a7-139">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="de8a7-140">[**Codice sorgente**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="de8a7-140">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="de8a7-141">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="de8a7-141">Changes to note are:</span></span>
* <span data-ttu-id="de8a7-142">I progetti esistenti e .NET Core vengono mantenuti in cartelle separate.</span><span class="sxs-lookup"><span data-stu-id="de8a7-142">The .NET Core and existing projects are kept in separate folders.</span></span>
    * <span data-ttu-id="de8a7-143">La gestione dei progetti in cartelle separate evita l'obbligo di avere Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="de8a7-143">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="de8a7-144">È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.</span><span class="sxs-lookup"><span data-stu-id="de8a7-144">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="de8a7-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de8a7-145">See Also</span></span>

<span data-ttu-id="de8a7-146">Per altre indicazioni relative alla migrazione a .NET Core, vedere la [documentazione relativa alla portabilità di .NET Core][porting-doc].</span><span class="sxs-lookup"><span data-stu-id="de8a7-146">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Progetto esistente"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Creare un file csproj con più framework come destinazione"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Progetto .NET Core con una libreria di classi portabile esistente in un'altra cartella"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
