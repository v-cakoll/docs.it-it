---
title: Gestire le dipendenze in .NET Core
description: Viene illustrato come gestire le dipendenze di progetto per un'applicazione .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157245"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="f422e-103">Gestire le dipendenze nelle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="f422e-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="f422e-104">Questo articolo illustra come aggiungere e rimuovere dipendenze modificando il file di progetto o usando l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f422e-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="f422e-105">Elemento > \<PackageReference</span><span class="sxs-lookup"><span data-stu-id="f422e-105">The \<PackageReference> element</span></span>

<span data-ttu-id="f422e-106">L'elemento del file di progetto `<PackageReference>` ha la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="f422e-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="f422e-107">L'attributo `Include` specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="f422e-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="f422e-108">L'attributo `Version` specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="f422e-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="f422e-109">Le versioni vengono specificate in base [alle regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="f422e-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="f422e-110">Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="f422e-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="f422e-111">Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f422e-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="f422e-112">La dipendenza nell'esempio precedente sarà valida solo se la compilazione è in corso per la destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="f422e-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="f422e-113">Il `$(TargetFramework)` nella condizione è una proprietà di MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="f422e-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="f422e-114">Per la maggior parte delle applicazioni .NET Core comuni, non è necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f422e-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="f422e-115">Aggiungere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="f422e-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="f422e-116">Per aggiungere una dipendenza, aggiungere un elemento `<PackageReference>` all'interno di un elemento `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="f422e-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="f422e-117">È possibile aggiungere un `<ItemGroup>` esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="f422e-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="f422e-118">Nell'esempio seguente viene usato il progetto di applicazione console predefinito creato da `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="f422e-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="f422e-119">Aggiungere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="f422e-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="f422e-120">Per aggiungere una dipendenza, eseguire il comando [dotnet add package](dotnet-add-package.md) , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f422e-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="f422e-121">Rimuovere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="f422e-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="f422e-122">Per rimuovere una dipendenza, rimuovere il relativo `<PackageReference>` elemento dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f422e-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="f422e-123">Rimuovere una dipendenza usando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="f422e-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="f422e-124">Per rimuovere una dipendenza, eseguire il comando [dotnet remove package](dotnet-remove-package.md) , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f422e-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="f422e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f422e-125">See also</span></span>

* [<span data-ttu-id="f422e-126">Pacchetti NuGet nei file di progetto</span><span class="sxs-lookup"><span data-stu-id="f422e-126">NuGet packages in project files</span></span>](../project-sdk/msbuild-props.md#nuget-packages)
* <span data-ttu-id="f422e-127">[comando dotnet list package](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="f422e-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
