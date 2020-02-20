---
title: Proprietà di MSBuild per Microsoft. NET. SDK
description: Riferimento per le proprietà MSBuild riconosciute dal .NET Core SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 00d9152d864ac0727a511f4c3c15abba82aab904
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503816"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="abe0f-103">Proprietà MSBuild per progetti .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="abe0f-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="abe0f-104">Questa pagina descrive le proprietà di MSBuild per la configurazione di progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="abe0f-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="abe0f-105">Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="abe0f-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="abe0f-106">Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="abe0f-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="abe0f-107">Proprietà del Framework</span><span class="sxs-lookup"><span data-stu-id="abe0f-107">Framework properties</span></span>

- [<span data-ttu-id="abe0f-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="abe0f-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="abe0f-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="abe0f-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="abe0f-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="abe0f-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="abe0f-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="abe0f-111">TargetFramework</span></span>

<span data-ttu-id="abe0f-112">La proprietà `TargetFramework` specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="abe0f-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="abe0f-113">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="abe0f-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="abe0f-114">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="abe0f-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="abe0f-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="abe0f-115">TargetFrameworks</span></span>

<span data-ttu-id="abe0f-116">Usare la proprietà `TargetFrameworks` quando si vuole che l'app sia destinata a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="abe0f-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="abe0f-117">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="abe0f-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="abe0f-118">Questa proprietà viene ignorata se viene specificato `TargetFramework` (Singular).</span><span class="sxs-lookup"><span data-stu-id="abe0f-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="abe0f-119">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="abe0f-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="abe0f-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="abe0f-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="abe0f-121">Questa proprietà si applica solo ai progetti che usano `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="abe0f-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="abe0f-122">Non si applica ai progetti che usano `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="abe0f-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="abe0f-123">Utilizzare la proprietà `NetStandardImplicitPackageVersion` quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) .</span><span class="sxs-lookup"><span data-stu-id="abe0f-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="abe0f-124">Il file di progetto nell'esempio seguente ha come destinazione `netstandard1.3` ma usa la versione 1.6.0 di `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="abe0f-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="abe0f-125">Pubblica proprietà</span><span class="sxs-lookup"><span data-stu-id="abe0f-125">Publish properties</span></span>

- [<span data-ttu-id="abe0f-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="abe0f-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="abe0f-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="abe0f-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="abe0f-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="abe0f-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="abe0f-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="abe0f-129">RuntimeIdentifier</span></span>

<span data-ttu-id="abe0f-130">Il `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="abe0f-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="abe0f-131">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="abe0f-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="abe0f-132">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="abe0f-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="abe0f-133">La proprietà `RuntimeIdentifiers` consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="abe0f-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="abe0f-134">Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime.</span><span class="sxs-lookup"><span data-stu-id="abe0f-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="abe0f-135">`RuntimeIdentifiers` viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="abe0f-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="abe0f-136">`RuntimeIdentifier` (Singular) può fornire build più veloci quando è necessario un solo Runtime.</span><span class="sxs-lookup"><span data-stu-id="abe0f-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="abe0f-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="abe0f-137">UseAppHost</span></span>

<span data-ttu-id="abe0f-138">La proprietà `UseAppHost` è stata introdotta nella versione 2.1.400 del .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="abe0f-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="abe0f-139">Controlla se viene creato un file eseguibile nativo per una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="abe0f-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="abe0f-140">Per le distribuzioni autosufficienti è necessario un eseguibile nativo.</span><span class="sxs-lookup"><span data-stu-id="abe0f-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="abe0f-141">In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework.</span><span class="sxs-lookup"><span data-stu-id="abe0f-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="abe0f-142">Impostare la proprietà `UseAppHost` su `false` per disabilitare la generazione del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="abe0f-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="abe0f-143">Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="abe0f-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="abe0f-144">Proprietà di compilazione</span><span class="sxs-lookup"><span data-stu-id="abe0f-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="abe0f-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="abe0f-145">LangVersion</span></span>

<span data-ttu-id="abe0f-146">Il `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="abe0f-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="abe0f-147">Se ad esempio si desidera accedere alle C# funzionalità di anteprima, impostare `LangVersion` su `preview`.</span><span class="sxs-lookup"><span data-stu-id="abe0f-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="abe0f-148">Per ulteriori informazioni, vedere [ C# controllo delle versioni dei linguaggi](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="abe0f-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="abe0f-149">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="abe0f-149">NuGet packages</span></span>

- [<span data-ttu-id="abe0f-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="abe0f-150">PackageReference</span></span>](#packagereference)

### <a name="packagereference"></a><span data-ttu-id="abe0f-151">PackageReference</span><span class="sxs-lookup"><span data-stu-id="abe0f-151">PackageReference</span></span>

<span data-ttu-id="abe0f-152">Il `PackageReference` elemento consente di specificare una dipendenza NuGet.</span><span class="sxs-lookup"><span data-stu-id="abe0f-152">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="abe0f-153">Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="abe0f-153">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="abe0f-154">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="abe0f-154">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="abe0f-155">Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="abe0f-155">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="abe0f-156">Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="abe0f-156">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="pack-and-restore-targets"></a><span data-ttu-id="abe0f-157">Destinazioni di Pack e ripristino</span><span class="sxs-lookup"><span data-stu-id="abe0f-157">Pack and restore targets</span></span>

<span data-ttu-id="abe0f-158">MSBuild 15,1 ha introdotto `pack` e `restore` destinazioni per la creazione e il ripristino di pacchetti NuGet come parte di una compilazione.</span><span class="sxs-lookup"><span data-stu-id="abe0f-158">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="abe0f-159">Per informazioni sulle proprietà MSBuild per queste destinazioni, tra cui `PackageTargetFallback`, vedere [Pack e Restore di NuGet come destinazioni MSBuild](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="abe0f-159">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="abe0f-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abe0f-160">See also</span></span>

- [<span data-ttu-id="abe0f-161">Riferimento allo schema MSBuild</span><span class="sxs-lookup"><span data-stu-id="abe0f-161">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="abe0f-162">Proprietà MSBuild comuni</span><span class="sxs-lookup"><span data-stu-id="abe0f-162">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="abe0f-163">Proprietà di MSBuild per il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="abe0f-163">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="abe0f-164">Proprietà di MSBuild per il ripristino di NuGet</span><span class="sxs-lookup"><span data-stu-id="abe0f-164">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="abe0f-165">Personalizzare una compilazione</span><span class="sxs-lookup"><span data-stu-id="abe0f-165">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
