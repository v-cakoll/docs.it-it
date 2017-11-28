---
title: Gestione delle dipendenze negli strumenti di .NET Core
description: Viene illustrato come gestire le dipendenze con gli strumenti di .NET Core.
keywords: "interfaccia della riga di comando, estendibilità, comandi personalizzati, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
ms.openlocfilehash: 21f42bbf4693c78a5be271b7769ef4489ed6d476
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="967be-104">Gestione delle dipendenze con .NET Core SDK 1.0</span><span class="sxs-lookup"><span data-stu-id="967be-104">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="967be-105">Con il passaggio dei progetti .NET Core da project.json a csproj e MSBuild, è stato eseguito un investimento significativo che ha comportato l'unificazione del file di progetto e degli asset che consentono il monitoraggio delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="967be-105">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="967be-106">Per i progetti .NET Core si tratta di un comportamento simile a quello di project.json.</span><span class="sxs-lookup"><span data-stu-id="967be-106">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="967be-107">Non esiste alcun file JSON o XML separato che tiene traccia delle dipendenze NuGet.</span><span class="sxs-lookup"><span data-stu-id="967be-107">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="967be-108">Con questa modifica, è stato anche introdotto un altro tipo di *riferimento* nella sintassi csproj denominato `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="967be-108">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="967be-109">Questo documento descrive il nuovo tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="967be-109">This document describes the new reference type.</span></span> <span data-ttu-id="967be-110">Illustra anche come aggiungere al progetto una dipendenza del pacchetto usando questo nuovo tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="967be-110">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="967be-111">Nuovo elemento \<PackageReference></span><span class="sxs-lookup"><span data-stu-id="967be-111">The new \<PackageReference> element</span></span>
<span data-ttu-id="967be-112">L'elemento `<PackageReference>` ha la struttura di base seguente:</span><span class="sxs-lookup"><span data-stu-id="967be-112">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="967be-113">Se si ha familiarità con MSBuild, il nuovo elemento risulterà analogo agli altri tipi di riferimento già esistenti.</span><span class="sxs-lookup"><span data-stu-id="967be-113">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="967be-114">La chiave è l'istruzione `Include` che specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="967be-114">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="967be-115">L'elemento figlio `<Version>` specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="967be-115">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="967be-116">Le versioni vengono specificate in base alle [regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="967be-116">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="967be-117">Se non si ha familiarità con la sintassi `csproj`, vedere la [documentazione di riferimento del progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="967be-117">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="967be-118">Per aggiungere una dipendenza disponibile solo in una destinazione specifica, usare le condizioni come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="967be-118">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

<span data-ttu-id="967be-119">Quanto descritto sopra indica che la dipendenza sarà valida solo se la compilazione avviene per una specifica destinazione.</span><span class="sxs-lookup"><span data-stu-id="967be-119">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="967be-120">`$(TargetFramework)` nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="967be-120">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="967be-121">Per le applicazioni .NET Core più comuni, non occorre eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="967be-121">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="967be-122">Aggiunta di una dipendenza al progetto</span><span class="sxs-lookup"><span data-stu-id="967be-122">Adding a dependency to your project</span></span>
<span data-ttu-id="967be-123">L'aggiunta di una dipendenza al progetto è un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="967be-123">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="967be-124">Di seguito è riportato un esempio che illustra come aggiungere Json.NET versione `9.0.1` al progetto.</span><span class="sxs-lookup"><span data-stu-id="967be-124">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="967be-125">Naturalmente, è applicabile a qualsiasi altra dipendenza NuGet.</span><span class="sxs-lookup"><span data-stu-id="967be-125">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="967be-126">Quando si apre il file di progetto, verranno visualizzati due o più nodi `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="967be-126">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="967be-127">Si noterà che uno dei nodi dispone già degli elementi `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="967be-127">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="967be-128">È possibile aggiungere la nuova dipendenza a questo nodo o crearne una nuova. La scelta tra queste due opzioni è responsabilità dell'utente, il risultato sarà identico.</span><span class="sxs-lookup"><span data-stu-id="967be-128">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="967be-129">In questo esempio verrà usato il modello predefinito eliminato da `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="967be-129">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="967be-130">Si tratta di una semplice applicazione console.</span><span class="sxs-lookup"><span data-stu-id="967be-130">This is a simple console application.</span></span> <span data-ttu-id="967be-131">Quando si apre il progetto, è possibile visualizzare `<ItemGroup>` con `<PackageReference>` già presente.</span><span class="sxs-lookup"><span data-stu-id="967be-131">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="967be-132">Vengono quindi aggiunti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="967be-132">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
<span data-ttu-id="967be-133">Successivamente, salvare il progetto ed eseguire il comando `dotnet restore` per installare la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="967be-133">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="967be-134">Il progetto completo è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="967be-134">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="967be-135">Rimozione di una dipendenza dal progetto</span><span class="sxs-lookup"><span data-stu-id="967be-135">Removing a dependency from the project</span></span>
<span data-ttu-id="967be-136">La rimozione di una dipendenza dal file di progetto comporta la semplice rimozione di `<PackageReference>` dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="967be-136">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
