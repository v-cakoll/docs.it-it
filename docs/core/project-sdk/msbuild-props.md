---
title: Proprietà MSBuild per Microsoft.NET.Sdk
description: Riferimento per le proprietà MSBuild riconosciute da .NET Core SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399182"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="b9634-103">Proprietà MSBuild per progetti .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="b9634-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="b9634-104">In questa pagina vengono descritte le proprietà MSBuild per la configurazione di progetti .NET Core.This page describes MSBuild properties for configuring .NET Core projects.</span><span class="sxs-lookup"><span data-stu-id="b9634-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="b9634-105">Questa pagina è un work in progress e non elenca tutte le proprietà MSBuild utili per .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b9634-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="b9634-106">Per un elenco delle proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="b9634-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="b9634-107">Proprietà del framework</span><span class="sxs-lookup"><span data-stu-id="b9634-107">Framework properties</span></span>

- [<span data-ttu-id="b9634-108">Quadro di destinazione</span><span class="sxs-lookup"><span data-stu-id="b9634-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="b9634-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="b9634-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="b9634-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="b9634-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="b9634-111">Quadro di destinazione</span><span class="sxs-lookup"><span data-stu-id="b9634-111">TargetFramework</span></span>

<span data-ttu-id="b9634-112">La `TargetFramework` proprietà specifica la versione del framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto.](../packages.md#metapackages)</span><span class="sxs-lookup"><span data-stu-id="b9634-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="b9634-113">Per un elenco dei moniker del framework di destinazione validi, vedere Framework di destinazione [nei progetti in stile SDK.](../../standard/frameworks.md#supported-target-framework-versions)</span><span class="sxs-lookup"><span data-stu-id="b9634-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="b9634-114">Per ulteriori informazioni, consultate Framework di destinazione nei progetti in [stile SDK.](../../standard/frameworks.md)</span><span class="sxs-lookup"><span data-stu-id="b9634-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="b9634-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="b9634-115">TargetFrameworks</span></span>

<span data-ttu-id="b9634-116">Usa `TargetFrameworks` la proprietà quando vuoi che l'app sia destinata a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="b9634-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="b9634-117">Per un elenco dei moniker del framework di destinazione validi, vedere Framework di destinazione [nei progetti in stile SDK.](../../standard/frameworks.md#supported-target-framework-versions)</span><span class="sxs-lookup"><span data-stu-id="b9634-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="b9634-118">Questa proprietà viene `TargetFramework` ignorata se viene specificato (singolare).</span><span class="sxs-lookup"><span data-stu-id="b9634-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="b9634-119">Per ulteriori informazioni, consultate Framework di destinazione nei progetti in [stile SDK.](../../standard/frameworks.md)</span><span class="sxs-lookup"><span data-stu-id="b9634-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="b9634-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="b9634-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="b9634-121">Questa proprietà si applica `netstandard1.x`solo ai progetti che utilizzano .</span><span class="sxs-lookup"><span data-stu-id="b9634-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="b9634-122">Non si applica ai `netstandard2.x`progetti che utilizzano .</span><span class="sxs-lookup"><span data-stu-id="b9634-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="b9634-123">Utilizzare `NetStandardImplicitPackageVersion` la proprietà quando si desidera specificare una versione del framework inferiore alla versione del [metapacchetto.](../packages.md#metapackages)</span><span class="sxs-lookup"><span data-stu-id="b9634-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="b9634-124">Il file di progetto `netstandard1.3` nell'esempio seguente è destinato `NETStandard.Library`ma utilizza la versione 1.6.0 di .</span><span class="sxs-lookup"><span data-stu-id="b9634-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="b9634-125">Pubblica proprietà</span><span class="sxs-lookup"><span data-stu-id="b9634-125">Publish properties</span></span>

- [<span data-ttu-id="b9634-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="b9634-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="b9634-127">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="b9634-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="b9634-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="b9634-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="b9634-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="b9634-129">RuntimeIdentifier</span></span>

<span data-ttu-id="b9634-130">La `RuntimeIdentifier` proprietà consente di specificare un singolo identificatore di [runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b9634-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b9634-131">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="b9634-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="b9634-132">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="b9634-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="b9634-133">La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di identificatori di [runtime (RIDE)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b9634-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b9634-134">Utilizzare questa proprietà se è necessario pubblicare per più runtime.</span><span class="sxs-lookup"><span data-stu-id="b9634-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="b9634-135">`RuntimeIdentifiers`viene utilizzato in fase di ripristino per garantire che le risorse corrette siano presenti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="b9634-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="b9634-136">`RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un solo runtime.</span><span class="sxs-lookup"><span data-stu-id="b9634-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="b9634-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="b9634-137">UseAppHost</span></span>

<span data-ttu-id="b9634-138">La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b9634-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="b9634-139">Controlla se viene creato o meno un eseguibile nativo per una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b9634-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="b9634-140">Per le distribuzioni autonome è necessario un eseguibile nativo.</span><span class="sxs-lookup"><span data-stu-id="b9634-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="b9634-141">In .NET Core 3.0 e versioni successive, un eseguibile dipendente dal framework viene creato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9634-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="b9634-142">Impostare `UseAppHost` la `false` proprietà su per disabilitare la generazione dell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="b9634-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="b9634-143">Per ulteriori informazioni sulla distribuzione, vedere Distribuzione di [applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="b9634-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="b9634-144">Compile (proprietà)</span><span class="sxs-lookup"><span data-stu-id="b9634-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="b9634-145">LinguaVersione</span><span class="sxs-lookup"><span data-stu-id="b9634-145">LangVersion</span></span>

<span data-ttu-id="b9634-146">La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="b9634-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="b9634-147">Se, ad esempio, si desidera accedere `LangVersion` alle `preview`funzionalità di anteprima di C, impostare su .</span><span class="sxs-lookup"><span data-stu-id="b9634-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="b9634-148">Per ulteriori informazioni, vedere [Controllo delle versioni del linguaggio C.](../../csharp/language-reference/configure-language-version.md#override-a-default)</span><span class="sxs-lookup"><span data-stu-id="b9634-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="b9634-149">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="b9634-149">NuGet packages</span></span>

- [<span data-ttu-id="b9634-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="b9634-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="b9634-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="b9634-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="b9634-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="b9634-152">PackageReference</span></span>

<span data-ttu-id="b9634-153">L'elemento consente di specificare una dipendenza NuGet.The `PackageReference` item lets you specify a NuGet dependency.</span><span class="sxs-lookup"><span data-stu-id="b9634-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="b9634-154">Ad esempio, è possibile fare riferimento a un singolo pacchetto anziché a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="b9634-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="b9634-155">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b9634-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="b9634-156">Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System.Runtime.The](https://www.nuget.org/packages/System.Runtime/) project file snippet in the following example references the System.Runtime package.</span><span class="sxs-lookup"><span data-stu-id="b9634-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="b9634-157">Per ulteriori informazioni, consultate [Riferimenti ai pacchetti nei file](/nuget/consume-packages/package-references-in-project-files)di progetto.</span><span class="sxs-lookup"><span data-stu-id="b9634-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="b9634-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="b9634-158">AssetTargetFallback</span></span>

<span data-ttu-id="b9634-159">La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del framework compatibili per i progetti a cui il progetto fa riferimento e i pacchetti NuGet che utilizzano il progetto.</span><span class="sxs-lookup"><span data-stu-id="b9634-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="b9634-160">Ad esempio, se si specifica `PackageReference` una dipendenza del pacchetto utilizzando ma tale pacchetto non `TargetFramework`contiene `AssetTargetFallback` asset compatibili con i progetti, la proprietà entra in gioco.</span><span class="sxs-lookup"><span data-stu-id="b9634-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="b9634-161">La compatibilità del pacchetto a cui si fa riferimento `AssetTargetFallback`viene ricontrollata utilizzando ogni framework di destinazione specificato in .</span><span class="sxs-lookup"><span data-stu-id="b9634-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="b9634-162">È possibile `AssetTargetFallback` impostare la proprietà su una o più versioni del framework di [destinazione.](../../standard/frameworks.md#supported-target-framework-versions)</span><span class="sxs-lookup"><span data-stu-id="b9634-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="b9634-163">Imballare e ripristinare gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="b9634-163">Pack and restore targets</span></span>

<span data-ttu-id="b9634-164">MSBuild 15.1 `pack` `restore` introdotto e destinazioni per la creazione e il ripristino di pacchetti NuGet come parte di una compilazione.</span><span class="sxs-lookup"><span data-stu-id="b9634-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="b9634-165">Per informazioni sulle proprietà MSBuild per `PackageTargetFallback`queste destinazioni, tra cui , vedere [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="b9634-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9634-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9634-166">See also</span></span>

- [<span data-ttu-id="b9634-167">Informazioni di riferimento sullo schema MSBuildMSBuild schema reference</span><span class="sxs-lookup"><span data-stu-id="b9634-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="b9634-168">Proprietà MSBuild comuniCommon MSBuild properties</span><span class="sxs-lookup"><span data-stu-id="b9634-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="b9634-169">Proprietà MSBuild per NuGet Pack</span><span class="sxs-lookup"><span data-stu-id="b9634-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="b9634-170">Proprietà MSBuild per il ripristino di NuGetMSBuild properties for NuGet restore</span><span class="sxs-lookup"><span data-stu-id="b9634-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="b9634-171">Personalizzare una compilazione</span><span class="sxs-lookup"><span data-stu-id="b9634-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
