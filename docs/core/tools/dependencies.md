---
title: Gestire le dipendenze in .NET Core
description: Viene illustrato come gestire le dipendenze di progetto per un'applicazione .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: b77acc7d4f03a45784f753d3daaa9810f110a6ac
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205945"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="d3380-103">Gestire le dipendenze nelle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="d3380-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="d3380-104">Questo articolo illustra come aggiungere e rimuovere dipendenze modificando il file di progetto o usando l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d3380-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="d3380-105">\<Elemento> PackageReference</span><span class="sxs-lookup"><span data-stu-id="d3380-105">The \<PackageReference> element</span></span>

<span data-ttu-id="d3380-106">L' `<PackageReference>` elemento del file di progetto ha la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="d3380-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="d3380-107">L' `Include` attributo specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="d3380-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="d3380-108">L' `Version` attributo specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="d3380-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="d3380-109">Le versioni vengono specificate in base [alle regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="d3380-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="d3380-110">Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="d3380-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="d3380-111">Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d3380-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="d3380-112">La dipendenza nell'esempio precedente sarà valida solo se la compilazione è in corso per la destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="d3380-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="d3380-113">`$(TargetFramework)`Nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="d3380-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="d3380-114">Per la maggior parte delle applicazioni .NET Core comuni, non è necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="d3380-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="d3380-115">Aggiungere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="d3380-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="d3380-116">Per aggiungere una dipendenza, aggiungere un `<PackageReference>` elemento all'interno di un `<ItemGroup>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d3380-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="d3380-117">È possibile aggiungere a un esistente `<ItemGroup>` o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="d3380-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="d3380-118">Nell'esempio seguente viene usato il progetto di applicazione console predefinito creato da `dotnet new console` :</span><span class="sxs-lookup"><span data-stu-id="d3380-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="d3380-119">Aggiungere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d3380-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="d3380-120">Per aggiungere una dipendenza, eseguire il [dotnet add package](dotnet-add-package.md) comando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d3380-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="d3380-121">Rimuovere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="d3380-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="d3380-122">Per rimuovere una dipendenza, rimuovere il relativo `<PackageReference>` elemento dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="d3380-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="d3380-123">Rimuovere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d3380-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="d3380-124">Per rimuovere una dipendenza, eseguire il [dotnet remove package](dotnet-remove-package.md) comando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d3380-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="d3380-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3380-125">See also</span></span>

* [<span data-ttu-id="d3380-126">Riferimenti ai pacchetti nei file di progetto</span><span class="sxs-lookup"><span data-stu-id="d3380-126">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties-and-items)
* <span data-ttu-id="d3380-127">[dotnet list packagecomando](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="d3380-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
