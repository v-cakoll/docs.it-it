---
title: Organizzare i progetti per .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 789f50ffb61b80f590a24bc45693df895b3424f7
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801934"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="42f94-103">Organizzare il progetto per il supporto sia di .NET Framework che di .NET Core</span><span class="sxs-lookup"><span data-stu-id="42f94-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="42f94-104">Informazioni su come creare una soluzione che viene compilata sia per .NET Framework che per .NET Core side-by-side.</span><span class="sxs-lookup"><span data-stu-id="42f94-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="42f94-105">Vedere le diverse opzioni per organizzare i progetti e poter raggiungere tale obiettivo.</span><span class="sxs-lookup"><span data-stu-id="42f94-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="42f94-106">Ecco alcuni scenari tipici da considerare quando si decide quale modalità di configurazione del layout di progetto usare con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42f94-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="42f94-107">È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="42f94-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

- [<span data-ttu-id="42f94-108">**Combinare progetti esistenti e progetti .NET Core in singoli progetti**</span><span class="sxs-lookup"><span data-stu-id="42f94-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="42f94-109">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="42f94-109">*What this is good for:*</span></span>
  - <span data-ttu-id="42f94-110">Semplificazione del processo di compilazione mediante la compilazione di un singolo progetto piuttosto che di progetti multipli, ciascuno destinato a una versione o a una piattaforma differente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="42f94-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  - <span data-ttu-id="42f94-111">Semplificazione della gestione di file di origine per progetti con più destinazioni perché è necessario gestire un unico file di progetto.</span><span class="sxs-lookup"><span data-stu-id="42f94-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="42f94-112">Quando si aggiungono o rimuovono i file di origine, le alternative richiedono una sincronizzazione manuale di questi file con altri progetti.</span><span class="sxs-lookup"><span data-stu-id="42f94-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  - <span data-ttu-id="42f94-113">Generazione semplificata di un pacchetto NuGet per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="42f94-113">Easily generating a NuGet package for consumption.</span></span>
  - <span data-ttu-id="42f94-114">Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.</span><span class="sxs-lookup"><span data-stu-id="42f94-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="42f94-115">*Scenari non supportati:*</span><span class="sxs-lookup"><span data-stu-id="42f94-115">*Unsupported scenarios:*</span></span>
  - <span data-ttu-id="42f94-116">Richiede agli sviluppatori di usare Visual Studio 2017 o una versione successiva per aprire i progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="42f94-116">Requires developers to use Visual Studio 2017 or a later version to open existing projects.</span></span> <span data-ttu-id="42f94-117">Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="42f94-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

- <a name="support-vs"></a><span data-ttu-id="42f94-118">[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="42f94-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="42f94-119">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="42f94-119">*What this is good for:*</span></span>
  - <span data-ttu-id="42f94-120">Supporto dello sviluppo sui progetti esistenti per sviluppatori e collaboratori che non possono avere Visual Studio 2017 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="42f94-120">Supporting development on existing projects for developers and contributors who may not have Visual Studio 2017 or a later version.</span></span>
  - <span data-ttu-id="42f94-121">Riduzione della possibilità di creazione di nuovi bug nei progetti esistenti in quanto non è necessaria alcuna varianza del codice nei progetti.</span><span class="sxs-lookup"><span data-stu-id="42f94-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="42f94-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="42f94-122">Example</span></span>

<span data-ttu-id="42f94-123">Si consideri il repository seguente:</span><span class="sxs-lookup"><span data-stu-id="42f94-123">Consider the repository below:</span></span>

![Progetto esistente](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="42f94-125">**Codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="42f94-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="42f94-126">Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="42f94-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="42f94-127">Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni</span><span class="sxs-lookup"><span data-stu-id="42f94-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="42f94-128">Riorganizzare il repository in modo che venga rimosso qualsiasi file *\*csproj* esistente e venga creato un singolo file *\*csproj* destinato a più framework.</span><span class="sxs-lookup"><span data-stu-id="42f94-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="42f94-129">Questa è un'ottima opzione perché consente di compilare un singolo progetto per diversi framework.</span><span class="sxs-lookup"><span data-stu-id="42f94-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="42f94-130">Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42f94-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![Creare un file csproj con più framework di destinazione](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="42f94-132">**Codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="42f94-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="42f94-133">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="42f94-133">Changes to note are:</span></span>

- <span data-ttu-id="42f94-134">Sostituzione di *packages.config* e *\*.csproj* con un nuovo [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span><span class="sxs-lookup"><span data-stu-id="42f94-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="42f94-135">I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="42f94-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="42f94-136">Mantenere i progetti esistenti e creare un progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="42f94-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="42f94-137">Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.</span><span class="sxs-lookup"><span data-stu-id="42f94-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![Progetto .NET Core con un progetto esistente in un'altra cartella](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="42f94-139">**Codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="42f94-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="42f94-140">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="42f94-140">Changes to note are:</span></span>

- <span data-ttu-id="42f94-141">I progetti esistenti e .NET Core vengono mantenuti in cartelle separate.</span><span class="sxs-lookup"><span data-stu-id="42f94-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  - <span data-ttu-id="42f94-142">La conservazione di progetti in cartelle separate evita di dover disporre di Visual Studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="42f94-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017 or later versions.</span></span> <span data-ttu-id="42f94-143">È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.</span><span class="sxs-lookup"><span data-stu-id="42f94-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="42f94-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f94-144">See also</span></span>

- [<span data-ttu-id="42f94-145">Documentazione sulla portabilità di .NET Core</span><span class="sxs-lookup"><span data-stu-id="42f94-145">.NET Core porting documentation</span></span>](index.md)
