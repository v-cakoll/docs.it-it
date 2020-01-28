---
title: Gestione delle dipendenze negli strumenti di .NET Core
description: Viene illustrato come gestire le dipendenze con gli strumenti di .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: e14fa42534d807e2a0fcce1dabe747c18c5166b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733381"
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="33d4e-103">Gestione delle dipendenze con .NET Core SDK 1.0</span><span class="sxs-lookup"><span data-stu-id="33d4e-103">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="33d4e-104">Con il passaggio dei progetti .NET Core da project.json a csproj e MSBuild, è stato eseguito un investimento significativo che ha comportato l'unificazione del file di progetto e degli asset che consentono il monitoraggio delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="33d4e-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="33d4e-105">Per i progetti .NET Core si tratta di un comportamento simile a quello di project.json.</span><span class="sxs-lookup"><span data-stu-id="33d4e-105">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="33d4e-106">Non esiste alcun file JSON o XML separato che tiene traccia delle dipendenze NuGet.</span><span class="sxs-lookup"><span data-stu-id="33d4e-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="33d4e-107">Con questa modifica, è stato anche introdotto un altro tipo di *riferimento* nella sintassi csproj denominato `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="33d4e-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="33d4e-108">Questo documento descrive il nuovo tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="33d4e-108">This document describes the new reference type.</span></span> <span data-ttu-id="33d4e-109">Illustra anche come aggiungere al progetto una dipendenza del pacchetto usando questo nuovo tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="33d4e-109">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="33d4e-110">Nuovo elemento \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="33d4e-110">The new \<PackageReference> element</span></span>
<span data-ttu-id="33d4e-111">L'elemento `<PackageReference>` ha la struttura di base seguente:</span><span class="sxs-lookup"><span data-stu-id="33d4e-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="33d4e-112">Se si ha familiarità con MSBuild, il nuovo elemento risulterà analogo agli altri tipi di riferimento già esistenti.</span><span class="sxs-lookup"><span data-stu-id="33d4e-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="33d4e-113">La chiave è l'istruzione `Include` che specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="33d4e-113">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="33d4e-114">L'elemento figlio `<Version>` specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="33d4e-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="33d4e-115">Le versioni vengono specificate in base alle [regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="33d4e-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="33d4e-116">Se non si ha familiarità con la sintassi `csproj`, vedere la [documentazione di riferimento del progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="33d4e-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="33d4e-117">Per aggiungere una dipendenza disponibile solo in una destinazione specifica, usare le condizioni come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="33d4e-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="33d4e-118">Quanto descritto sopra indica che la dipendenza sarà valida solo se la compilazione avviene per una specifica destinazione.</span><span class="sxs-lookup"><span data-stu-id="33d4e-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="33d4e-119">Il `$(TargetFramework)` nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="33d4e-119">The `$(TargetFramework)` in the condition is an MSBuild property that is being set in the project.</span></span> <span data-ttu-id="33d4e-120">Per le applicazioni .NET Core più comuni, non occorre eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="33d4e-120">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="33d4e-121">Aggiunta di una dipendenza al progetto</span><span class="sxs-lookup"><span data-stu-id="33d4e-121">Adding a dependency to your project</span></span>
<span data-ttu-id="33d4e-122">L'aggiunta di una dipendenza al progetto è un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="33d4e-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="33d4e-123">Di seguito è riportato un esempio che illustra come aggiungere Json.NET versione `9.0.1` al progetto.</span><span class="sxs-lookup"><span data-stu-id="33d4e-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="33d4e-124">Naturalmente, è applicabile a qualsiasi altra dipendenza NuGet.</span><span class="sxs-lookup"><span data-stu-id="33d4e-124">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="33d4e-125">Quando si apre il file di progetto, verranno visualizzati due o più nodi `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="33d4e-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="33d4e-126">Si noterà che uno dei nodi dispone già degli elementi `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="33d4e-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="33d4e-127">È possibile aggiungere la nuova dipendenza a questo nodo o crearne una nuova. La scelta tra queste due opzioni è responsabilità dell'utente, il risultato sarà identico.</span><span class="sxs-lookup"><span data-stu-id="33d4e-127">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="33d4e-128">In questo esempio verrà usato il modello predefinito eliminato da `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="33d4e-128">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="33d4e-129">Si tratta di una semplice applicazione console.</span><span class="sxs-lookup"><span data-stu-id="33d4e-129">This is a simple console application.</span></span> <span data-ttu-id="33d4e-130">Quando si apre il progetto, è possibile visualizzare `<ItemGroup>` con `<PackageReference>` già presente.</span><span class="sxs-lookup"><span data-stu-id="33d4e-130">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="33d4e-131">Vengono quindi aggiunti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="33d4e-131">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="33d4e-132">Successivamente, salvare il progetto ed eseguire il comando `dotnet restore` per installare la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="33d4e-132">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="33d4e-133">Il progetto completo è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="33d4e-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="33d4e-134">Rimozione di una dipendenza dal progetto</span><span class="sxs-lookup"><span data-stu-id="33d4e-134">Removing a dependency from the project</span></span>
<span data-ttu-id="33d4e-135">La rimozione di una dipendenza dal file di progetto comporta la semplice rimozione di `<PackageReference>` dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="33d4e-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
