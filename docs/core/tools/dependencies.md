---
title: Gestire le dipendenze in .NET CoreManage dependencies in .NET Core
description: Viene illustrato come gestire le dipendenze di progetto per un'applicazione .NET Core.Explains how to manage project dependencies for a .NET Core application.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399147"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="6912b-103">Gestire le dipendenze nelle applicazioni .NET CoreManage dependencies in .NET Core applications</span><span class="sxs-lookup"><span data-stu-id="6912b-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="6912b-104">In questo articolo viene illustrato come aggiungere e rimuovere dipendenze modificando il file di progetto o utilizzando l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6912b-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="6912b-105">Elemento \<del> PackageReferenceThe PackageReference> element</span><span class="sxs-lookup"><span data-stu-id="6912b-105">The \<PackageReference> element</span></span>

<span data-ttu-id="6912b-106">L'elemento del file di progetto ha la struttura seguente:The `<PackageReference>` project file element has the following structure:</span><span class="sxs-lookup"><span data-stu-id="6912b-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="6912b-107">L'attributo `Include` specifica l'ID del pacchetto da aggiungere al progetto.</span><span class="sxs-lookup"><span data-stu-id="6912b-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="6912b-108">L'attributo `Version` specifica la versione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="6912b-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="6912b-109">Le versioni vengono specificate in base alle regole della [versione NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="6912b-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="6912b-110">Se non si ha familiarità con la sintassi del file di progetto, vedere la documentazione di riferimento del [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6912b-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="6912b-111">Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="6912b-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="6912b-112">La dipendenza nell'esempio precedente sarà valida solo se la compilazione viene eseguito per quella destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="6912b-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="6912b-113">La `$(TargetFramework)` condizione nella condizione è una proprietà MSBuild che viene impostata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="6912b-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="6912b-114">Per le applicazioni .NET Core più comuni, non è necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="6912b-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="6912b-115">Aggiungere una dipendenza modificando il file di progettoAdd a dependency by editing the project file</span><span class="sxs-lookup"><span data-stu-id="6912b-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="6912b-116">Per aggiungere una dipendenza, `<PackageReference>` aggiungere `<ItemGroup>` un elemento all'interno di un elemento.</span><span class="sxs-lookup"><span data-stu-id="6912b-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="6912b-117">È possibile aggiungere `<ItemGroup>` a un esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="6912b-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="6912b-118">Nell'esempio seguente viene utilizzato il progetto `dotnet new console`di applicazione console predefinito creato da :</span><span class="sxs-lookup"><span data-stu-id="6912b-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="6912b-119">Aggiungere una dipendenza utilizzando l'interfaccia della riga di comandoAdd a dependency by using the CLI</span><span class="sxs-lookup"><span data-stu-id="6912b-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="6912b-120">Per aggiungere una dipendenza, [dotnet add package](dotnet-add-package.md) eseguire il comando, come illustrato nell'esempio seguente:To add a dependency, run the command, as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="6912b-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="6912b-121">Rimuovere una dipendenza modificando il file di progetto</span><span class="sxs-lookup"><span data-stu-id="6912b-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="6912b-122">Per rimuovere una dipendenza, `<PackageReference>` rimuovere il relativo elemento dal file di progetto.</span><span class="sxs-lookup"><span data-stu-id="6912b-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="6912b-123">Rimuovere una dipendenza utilizzando l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="6912b-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="6912b-124">Per rimuovere una dipendenza, [dotnet remove package](dotnet-remove-package.md) eseguire il comando, come illustrato nell'esempio seguente:To remove a dependency, run the command, as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="6912b-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="6912b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6912b-125">See also</span></span>

* [<span data-ttu-id="6912b-126">Pacchetti NuGet nei file di progettoNuGet packages in project files</span><span class="sxs-lookup"><span data-stu-id="6912b-126">NuGet packages in project files</span></span>](../project-sdk/msbuild-props.md#nuget-packages)
* <span data-ttu-id="6912b-127">[dotnet list packageComando](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="6912b-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
