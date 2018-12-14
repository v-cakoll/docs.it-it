---
title: Organizzare i progetti per .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.custom: seodec18
ms.openlocfilehash: cfb3670bda887792389c7cee3f65397e649304d5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146927"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="d3af1-103">Organizzare il progetto per il supporto sia di .NET Framework che di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d3af1-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="d3af1-104">Informazioni su come creare una soluzione che viene compilata sia per .NET Framework che per .NET Core side-by-side.</span><span class="sxs-lookup"><span data-stu-id="d3af1-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="d3af1-105">Vedere le diverse opzioni per organizzare i progetti e poter raggiungere tale obiettivo.</span><span class="sxs-lookup"><span data-stu-id="d3af1-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="d3af1-106">Ecco alcuni scenari tipici da considerare quando si decide quale modalità di configurazione del layout di progetto usare con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d3af1-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="d3af1-107">È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d3af1-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="d3af1-108">[**Combinare progetti esistenti e progetti .NET Core in singoli progetti**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="d3af1-108">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="d3af1-109">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="d3af1-109">*What this is good for:*</span></span>
  * <span data-ttu-id="d3af1-110">Semplificazione del processo di compilazione mediante la compilazione di un singolo progetto piuttosto che di progetti multipli, ciascuno destinato a una versione o a una piattaforma differente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3af1-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="d3af1-111">Semplificazione della gestione di file di origine per progetti con più destinazioni perché è necessario gestire un unico file di progetto.</span><span class="sxs-lookup"><span data-stu-id="d3af1-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="d3af1-112">Quando si aggiungono o rimuovono i file di origine, le alternative richiedono una sincronizzazione manuale di questi file con altri progetti.</span><span class="sxs-lookup"><span data-stu-id="d3af1-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="d3af1-113">Generazione semplificata di un pacchetto NuGet per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d3af1-113">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="d3af1-114">Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d3af1-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="d3af1-115">*Scenari non supportati:*</span><span class="sxs-lookup"><span data-stu-id="d3af1-115">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="d3af1-116">Gli sviluppatori devono usare Visual Studio 2017 per aprire i progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="d3af1-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="d3af1-117">Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="d3af1-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="d3af1-118">[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="d3af1-118">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="d3af1-119">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="d3af1-119">*What this is good for:*</span></span>
  * <span data-ttu-id="d3af1-120">Supporto per lo sviluppo di progetti esistenti, senza necessità di aggiornamento per sviluppatori/collaboratori che non dispongono di Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d3af1-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="d3af1-121">Riduzione della possibilità di creazione di nuovi bug nei progetti esistenti in quanto non è necessaria alcuna varianza del codice nei progetti.</span><span class="sxs-lookup"><span data-stu-id="d3af1-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="d3af1-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3af1-122">Example</span></span>

<span data-ttu-id="d3af1-123">Si consideri il repository seguente:</span><span class="sxs-lookup"><span data-stu-id="d3af1-123">Consider the repository below:</span></span>

<span data-ttu-id="d3af1-124">![Progetto esistente][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="d3af1-124">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="d3af1-125">[**Codice sorgente**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="d3af1-125">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="d3af1-126">Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="d3af1-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="d3af1-127">Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni</span><span class="sxs-lookup"><span data-stu-id="d3af1-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="d3af1-128">Riorganizzare il repository in modo che venga rimosso qualsiasi file *\*csproj* esistente e venga creato un singolo file *\*csproj* destinato a più framework.</span><span class="sxs-lookup"><span data-stu-id="d3af1-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="d3af1-129">Questa è un'ottima opzione perché consente di compilare un singolo progetto per diversi framework.</span><span class="sxs-lookup"><span data-stu-id="d3af1-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="d3af1-130">Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d3af1-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="d3af1-131">![Creare un file csproj con più framework come destinazione][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="d3af1-131">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="d3af1-132">[**Codice sorgente**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="d3af1-132">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="d3af1-133">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="d3af1-133">Changes to note are:</span></span>

* <span data-ttu-id="d3af1-134">Sostituzione di *packages.config* e *\*csproj* con un nuovo [.NET Core *\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="d3af1-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="d3af1-135">I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="d3af1-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="d3af1-136">Mantenere i progetti esistenti e creare un progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="d3af1-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="d3af1-137">Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.</span><span class="sxs-lookup"><span data-stu-id="d3af1-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="d3af1-138">![Progetto .NET Core con un progetto esistente in un'altra cartella][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="d3af1-138">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="d3af1-139">[**Codice sorgente**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="d3af1-139">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="d3af1-140">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="d3af1-140">Changes to note are:</span></span>

* <span data-ttu-id="d3af1-141">I progetti esistenti e .NET Core vengono mantenuti in cartelle separate.</span><span class="sxs-lookup"><span data-stu-id="d3af1-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  * <span data-ttu-id="d3af1-142">La gestione dei progetti in cartelle separate evita l'obbligo di avere Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d3af1-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="d3af1-143">È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.</span><span class="sxs-lookup"><span data-stu-id="d3af1-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3af1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3af1-144">See Also</span></span>

* <span data-ttu-id="d3af1-145">Per altre indicazioni relative alla migrazione a .NET Core, vedere la [documentazione relativa alla portabilità di .NET Core][porting-doc].</span><span class="sxs-lookup"><span data-stu-id="d3af1-145">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Progetto esistente"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Creare un file con estensione csproj con più framework come destinazione"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Progetto .NET Core con una libreria di classi portabile esistente in un'altra cartella"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
