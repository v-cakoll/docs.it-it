---
title: Gestione delle dipendenze negli strumenti di .NET Core
description: Viene illustrato come gestire le dipendenze con gli strumenti di .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965620"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="3e53b-103">Gestire le dipendenze con .NET Core SDK 1,0</span><span class="sxs-lookup"><span data-stu-id="3e53b-103">Manage dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="3e53b-104">Con il passaggio dei progetti .NET Core da project.json a csproj e MSBuild, è stato eseguito un investimento significativo che ha comportato l'unificazione del file di progetto e degli asset che consentono il monitoraggio delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="3e53b-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="3e53b-105">Per i progetti .NET Core, questa operazione è simile a quella di Project. JSON.</span><span class="sxs-lookup"><span data-stu-id="3e53b-105">For .NET Core projects, this is similar to what project.json did.</span></span> <span data-ttu-id="3e53b-106">Non esiste alcun file JSON o XML separato che tiene traccia delle dipendenze NuGet.</span><span class="sxs-lookup"><span data-stu-id="3e53b-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="3e53b-107">Con questa modifica, è stato anche introdotto un altro tipo di *riferimento* nella sintassi csproj denominato `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="3e53b-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span>

<span data-ttu-id="3e53b-108">Questo documento descrive il nuovo tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3e53b-108">This document describes the new reference type.</span></span> <span data-ttu-id="3e53b-109">Illustra anche come aggiungere al progetto una dipendenza del pacchetto usando questo nuovo tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3e53b-109">It also shows how to add a package dependency using this new reference type to your project.</span></span>

## <a name="the-new-packagereference-element"></a><span data-ttu-id="3e53b-110">Nuovo elemento \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="3e53b-110">The new \<PackageReference> element</span></span>

<span data-ttu-id="3e53b-111">L'elemento `<PackageReference>` ha la struttura di base seguente:</span><span class="sxs-lookup"><span data-stu-id="3e53b-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="3e53b-112">Se si ha familiarità con MSBuild, il nuovo elemento risulterà analogo agli altri tipi di riferimento già esistenti.</span><span class="sxs-lookup"><span data-stu-id="3e53b-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="3e53b-113">La chiave è l'istruzione `Include`, che specifica l'ID del pacchetto che si desidera aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="3e53b-113">The key is the `Include` statement, which specifies the package ID that you wish to add to the project.</span></span> <span data-ttu-id="3e53b-114">L'elemento figlio `<Version>` specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="3e53b-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="3e53b-115">Le versioni vengono specificate in base alle [regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="3e53b-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="3e53b-116">Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="3e53b-116">If you're not familiar with the project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="3e53b-117">Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3e53b-117">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="3e53b-118">La dipendenza sarà valida solo se la compilazione è in corso per la destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3e53b-118">The dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="3e53b-119">Il `$(TargetFramework)` nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="3e53b-119">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="3e53b-120">Per le applicazioni .NET Core più comuni, non occorre eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="3e53b-120">For most common .NET Core applications, you will not need to do this.</span></span>

## <a name="add-a-dependency-to-the-project"></a><span data-ttu-id="3e53b-121">Aggiungere una dipendenza al progetto</span><span class="sxs-lookup"><span data-stu-id="3e53b-121">Add a dependency to the project</span></span>

<span data-ttu-id="3e53b-122">L'aggiunta di una dipendenza al progetto è un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="3e53b-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="3e53b-123">Di seguito è riportato un esempio che illustra come aggiungere Json.NET versione `9.0.1` al progetto.</span><span class="sxs-lookup"><span data-stu-id="3e53b-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="3e53b-124">Naturalmente, è applicabile a qualsiasi altra dipendenza NuGet.</span><span class="sxs-lookup"><span data-stu-id="3e53b-124">Of course, it is applicable to any other NuGet dependency.</span></span>

<span data-ttu-id="3e53b-125">Il file di progetto contiene due o più nodi `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="3e53b-125">Your project file has two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="3e53b-126">In uno dei nodi sono già presenti elementi `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="3e53b-126">One of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="3e53b-127">È possibile aggiungere la nuova dipendenza a questo nodo o crearne una nuova. il risultato sarà lo stesso.</span><span class="sxs-lookup"><span data-stu-id="3e53b-127">You can add your new dependency to this node or create a new one; the result will be the same.</span></span>

<span data-ttu-id="3e53b-128">Nell'esempio seguente viene usato il modello predefinito eliminato da `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="3e53b-128">The following example uses the default template that's dropped by `dotnet new console`.</span></span> <span data-ttu-id="3e53b-129">Si tratta di una semplice applicazione console.</span><span class="sxs-lookup"><span data-stu-id="3e53b-129">This is a simple console application.</span></span> <span data-ttu-id="3e53b-130">Quando si apre il progetto, è possibile trovare la `<ItemGroup>` con `<PackageReference>` già esistente.</span><span class="sxs-lookup"><span data-stu-id="3e53b-130">When you open up the project, you'll find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="3e53b-131">Aggiungere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e53b-131">Add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="3e53b-132">Al termine, salvare il progetto ed eseguire il comando `dotnet restore` per installare la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="3e53b-132">After this, save the project and run the `dotnet restore` command to install the dependency.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="3e53b-133">Il progetto completo è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3e53b-133">The full project looks like this:</span></span>

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

## <a name="remove-a-dependency-from-the-project"></a><span data-ttu-id="3e53b-134">Rimuovere una dipendenza dal progetto</span><span class="sxs-lookup"><span data-stu-id="3e53b-134">Remove a dependency from the project</span></span>

<span data-ttu-id="3e53b-135">La rimozione di una dipendenza dal file di progetto comporta la semplice rimozione di `<PackageReference>` dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="3e53b-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
