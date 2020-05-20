---
title: ''
description: ''
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: ''
ms.openlocfilehash: 667b2d4d68edd82a4d18c370e45ea18f4d4b379a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702848"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="cd731-101">Gestire le dipendenze nelle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="cd731-101">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="cd731-102">Questo articolo illustra come aggiungere e rimuovere dipendenze modificando il file di progetto o usando l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cd731-102">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="cd731-103">\<Elemento> PackageReference</span><span class="sxs-lookup"><span data-stu-id="cd731-103">The \<PackageReference> element</span></span>

<span data-ttu-id="cd731-104">L' `<PackageReference>` elemento del file di progetto ha la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="cd731-104">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="cd731-105">L' `Include` attributo specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="cd731-105">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="cd731-106">L' `Version` attributo specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="cd731-106">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="cd731-107">Le versioni vengono specificate in base [alle regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="cd731-107">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="cd731-108">Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="cd731-108">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="cd731-109">Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cd731-109">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="cd731-110">La dipendenza nell'esempio precedente sarà valida solo se la compilazione è in corso per la destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="cd731-110">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="cd731-111">`$(TargetFramework)`Nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="cd731-111">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="cd731-112">Per la maggior parte delle applicazioni .NET Core comuni, non è necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="cd731-112">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="cd731-113">Aggiungere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="cd731-113">Add a dependency by editing the project file</span></span>

<span data-ttu-id="cd731-114">Per aggiungere una dipendenza, aggiungere un `<PackageReference>` elemento all'interno di un `<ItemGroup>` elemento.</span><span class="sxs-lookup"><span data-stu-id="cd731-114">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="cd731-115">È possibile aggiungere a un esistente `<ItemGroup>` o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="cd731-115">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="cd731-116">Nell'esempio seguente viene usato il progetto di applicazione console predefinito creato da `dotnet new console` :</span><span class="sxs-lookup"><span data-stu-id="cd731-116">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="cd731-117">Aggiungere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="cd731-117">Add a dependency by using the CLI</span></span>

<span data-ttu-id="cd731-118">Per aggiungere una dipendenza, eseguire il [dotnet add package](dotnet-add-package.md) comando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cd731-118">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="cd731-119">Rimuovere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="cd731-119">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="cd731-120">Per rimuovere una dipendenza, rimuovere il relativo `<PackageReference>` elemento dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cd731-120">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="cd731-121">Rimuovere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="cd731-121">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="cd731-122">Per rimuovere una dipendenza, eseguire il [dotnet remove package](dotnet-remove-package.md) comando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cd731-122">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="cd731-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd731-123">See also</span></span>

* [<span data-ttu-id="cd731-124">Riferimenti ai pacchetti nei file di progetto</span><span class="sxs-lookup"><span data-stu-id="cd731-124">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties-and-items)
* <span data-ttu-id="cd731-125">[dotnet list packagecomando](dotnet-list-package.md)</span><span class="sxs-lookup"><span data-stu-id="cd731-125">[dotnet list package command](dotnet-list-package.md)</span></span>
