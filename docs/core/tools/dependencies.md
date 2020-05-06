---
title: Gestire le dipendenze in .NET Core
description: Viene illustrato come gestire le dipendenze di progetto per un'applicazione .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 3e1d807ea69e66e31b277a92cd6a1dc0e76531b5
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795547"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="6f8b7-103">Gestire le dipendenze nelle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="6f8b7-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="6f8b7-104">Questo articolo illustra come aggiungere e rimuovere dipendenze modificando il file di progetto o usando l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="6f8b7-105">Elemento \<> PackageReference</span><span class="sxs-lookup"><span data-stu-id="6f8b7-105">The \<PackageReference> element</span></span>

<span data-ttu-id="6f8b7-106">L' `<PackageReference>` elemento del file di progetto ha la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="6f8b7-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="6f8b7-107">L' `Include` attributo specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="6f8b7-108">L' `Version` attributo specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="6f8b7-109">Le versioni vengono specificate in base [alle regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="6f8b7-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="6f8b7-110">Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="6f8b7-111">Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6f8b7-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="6f8b7-112">La dipendenza nell'esempio precedente sarà valida solo se la compilazione è in corso per la destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="6f8b7-113">`$(TargetFramework)` Nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="6f8b7-114">Per la maggior parte delle applicazioni .NET Core comuni, non è necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="6f8b7-115">Aggiungere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="6f8b7-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="6f8b7-116">Per aggiungere una dipendenza, aggiungere un `<PackageReference>` elemento all'interno `<ItemGroup>` di un elemento.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="6f8b7-117">È possibile aggiungere a un esistente `<ItemGroup>` o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="6f8b7-118">Nell'esempio seguente viene usato il progetto di applicazione console predefinito creato da `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="6f8b7-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="6f8b7-119">Aggiungere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="6f8b7-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="6f8b7-120">Per aggiungere una dipendenza, eseguire il [dotnet add package](dotnet-add-package.md) comando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6f8b7-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="6f8b7-121">Rimuovere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="6f8b7-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="6f8b7-122">Per rimuovere una dipendenza, rimuovere il `<PackageReference>` relativo elemento dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="6f8b7-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="6f8b7-123">Rimuovere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="6f8b7-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="6f8b7-124">Per rimuovere una dipendenza, eseguire il [dotnet remove package](dotnet-remove-package.md) comando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6f8b7-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="6f8b7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f8b7-125">See also</span></span>

* [<span data-ttu-id="6f8b7-126">Riferimenti ai pacchetti nei file di progetto</span><span class="sxs-lookup"><span data-stu-id="6f8b7-126">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties)
* <span data-ttu-id="6f8b7-127">[dotnet list packagecomando](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="6f8b7-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
