---
title: Organizzare i progetti per .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
author: conniey
ms.date: 12/07/2018
ms.openlocfilehash: d71cc3102846c08f4e35831921b8cc4ca82f9e1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75777339"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="56e8d-103">Organizzare il progetto per il supporto sia di .NET Framework che di .NET Core</span><span class="sxs-lookup"><span data-stu-id="56e8d-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="56e8d-104">È possibile creare una soluzione che viene compilata sia per .NET Framework che per .NET Core side-by-side.</span><span class="sxs-lookup"><span data-stu-id="56e8d-104">You can create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="56e8d-105">In questo articolo vengono illustrate diverse opzioni di organizzazione del progetto che consentono di raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="56e8d-105">This article covers several project-organization options to help you achieve this goal.</span></span> <span data-ttu-id="56e8d-106">Ecco alcuni scenari tipici da considerare quando si decide come configurare il layout del progetto con .NET Core.Here are some typical scenarios to consider when you're deciding how to set up your project layout with .NET Core.</span><span class="sxs-lookup"><span data-stu-id="56e8d-106">Here are some typical scenarios to consider when you're deciding how to set up your project layout with .NET Core.</span></span> <span data-ttu-id="56e8d-107">È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="56e8d-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

- [<span data-ttu-id="56e8d-108">**Combinare progetti esistenti e progetti .NET Core in singoli progetti**</span><span class="sxs-lookup"><span data-stu-id="56e8d-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="56e8d-109">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="56e8d-109">*What this is good for:*</span></span>
  - <span data-ttu-id="56e8d-110">Semplifica il processo di compilazione compilando un singolo progetto anziché più progetti destinati a una piattaforma o una versione di .NET Framework diversa.</span><span class="sxs-lookup"><span data-stu-id="56e8d-110">Simplifies your build process by compiling a single project rather than multiple projects that each target a different .NET Framework version or platform.</span></span>
  - <span data-ttu-id="56e8d-111">Semplifica la gestione dei file di origine per i progetti con più target perché è necessario gestire un singolo file di progetto.</span><span class="sxs-lookup"><span data-stu-id="56e8d-111">Simplifies source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="56e8d-112">Quando si aggiungono o rimuovono file di origine, le alternative richiedono la sincronizzazione manuale con gli altri progetti.</span><span class="sxs-lookup"><span data-stu-id="56e8d-112">When adding or removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  - <span data-ttu-id="56e8d-113">Genera facilmente un pacchetto NuGet per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="56e8d-113">Easily generate a NuGet package for consumption.</span></span>
  - <span data-ttu-id="56e8d-114">Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.</span><span class="sxs-lookup"><span data-stu-id="56e8d-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="56e8d-115">*Scenari non supportati:Unsupported scenarios:*</span><span class="sxs-lookup"><span data-stu-id="56e8d-115">*Unsupported scenarios:*</span></span>
  - <span data-ttu-id="56e8d-116">Richiede agli sviluppatori di utilizzare Visual Studio 2017 o versione successiva per aprire i progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="56e8d-116">Requires developers to use Visual Studio 2017 or a later version to open existing projects.</span></span> <span data-ttu-id="56e8d-117">Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="56e8d-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

- <a name="support-vs"></a><span data-ttu-id="56e8d-118">[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="56e8d-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="56e8d-119">*Vantaggi:*</span><span class="sxs-lookup"><span data-stu-id="56e8d-119">*What this is good for:*</span></span>
  - <span data-ttu-id="56e8d-120">Supporta lo sviluppo di progetti esistenti per sviluppatori e collaboratori che potrebbero non disporre di Visual Studio 2017 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="56e8d-120">Supports development on existing projects for developers and contributors who may not have Visual Studio 2017 or a later version.</span></span>
  - <span data-ttu-id="56e8d-121">Diminuisce la possibilità di creare nuovi bug nei progetti esistenti perché non è necessaria alcuna varianza del codice in tali progetti.</span><span class="sxs-lookup"><span data-stu-id="56e8d-121">Decreases the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="56e8d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="56e8d-122">Example</span></span>

<span data-ttu-id="56e8d-123">Si consideri il repository seguente:</span><span class="sxs-lookup"><span data-stu-id="56e8d-123">Consider the repository below:</span></span>

![Progetto esistente](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="56e8d-125">**Codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="56e8d-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="56e8d-126">Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="56e8d-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="56e8d-127">Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni</span><span class="sxs-lookup"><span data-stu-id="56e8d-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="56e8d-128">Riorganizzare il repository in modo che tutti i file \* \*con estensione csproj\* esistenti vengano rimossi e venga creato un singolo \* \*\* file con estensione csproj destinato a più framework.</span><span class="sxs-lookup"><span data-stu-id="56e8d-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="56e8d-129">Questa è una grande opzione, perché un singolo progetto è in grado di compilare per framework diversi.</span><span class="sxs-lookup"><span data-stu-id="56e8d-129">This is a great option, because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="56e8d-130">Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="56e8d-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![Creare un file con estensione csproj con più framework come destinazione](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="56e8d-132">**Codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="56e8d-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="56e8d-133">Modifiche da notare:</span><span class="sxs-lookup"><span data-stu-id="56e8d-133">Changes to note are:</span></span>

- <span data-ttu-id="56e8d-134">Sostituzione di *packages.config* e *\*.csproj* con un nuovo [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span><span class="sxs-lookup"><span data-stu-id="56e8d-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="56e8d-135">I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.</span><span class="sxs-lookup"><span data-stu-id="56e8d-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="56e8d-136">Mantenere i progetti esistenti e creare un progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="56e8d-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="56e8d-137">Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.</span><span class="sxs-lookup"><span data-stu-id="56e8d-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![Progetto .NET Core con un progetto esistente in un'altra cartella](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="56e8d-139">**Codice sorgente**</span><span class="sxs-lookup"><span data-stu-id="56e8d-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="56e8d-140">I progetti esistenti e .NET Core vengono mantenuti in cartelle separate.</span><span class="sxs-lookup"><span data-stu-id="56e8d-140">The .NET Core and existing projects are kept in separate folders.</span></span> <span data-ttu-id="56e8d-141">Mantenere i progetti in cartelle separate evita di forzare l'utente ad avere Visual Studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="56e8d-141">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017 or later versions.</span></span> <span data-ttu-id="56e8d-142">È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.</span><span class="sxs-lookup"><span data-stu-id="56e8d-142">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="56e8d-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56e8d-143">See also</span></span>

- [<span data-ttu-id="56e8d-144">Documentazione sul porting di .NET Core</span><span class="sxs-lookup"><span data-stu-id="56e8d-144">.NET Core porting documentation</span></span>](index.md)
