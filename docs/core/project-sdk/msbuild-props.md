---
title: Proprietà di MSBuild per Microsoft. NET. SDK
description: Riferimento per le proprietà e gli elementi di MSBuild riconosciuti dal .NET Core SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: cda56b3e23592a341d9fe672fc1f1530adcdab49
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206102"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="42c5b-103">Informazioni di riferimento su MSBuild per progetti .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="42c5b-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="42c5b-104">Questa pagina è un riferimento per le proprietà e gli elementi di MSBuild che è possibile usare per configurare i progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42c5b-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="42c5b-105">Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="42c5b-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="42c5b-106">Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="42c5b-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="42c5b-107">Proprietà del Framework</span><span class="sxs-lookup"><span data-stu-id="42c5b-107">Framework properties</span></span>

- [<span data-ttu-id="42c5b-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="42c5b-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="42c5b-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="42c5b-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="42c5b-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="42c5b-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="42c5b-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="42c5b-111">TargetFramework</span></span>

<span data-ttu-id="42c5b-112">La `TargetFramework` proprietà specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="42c5b-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="42c5b-113">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="42c5b-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="42c5b-114">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="42c5b-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="42c5b-115">TargetFrameworks</span></span>

<span data-ttu-id="42c5b-116">Usare la `TargetFrameworks` proprietà quando si vuole che l'app sia destinata a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="42c5b-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="42c5b-117">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="42c5b-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="42c5b-118">Questa proprietà viene ignorata se `TargetFramework` viene specificato (singolare).</span><span class="sxs-lookup"><span data-stu-id="42c5b-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="42c5b-119">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="42c5b-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="42c5b-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="42c5b-121">Questa proprietà si applica solo ai progetti che usano `netstandard1.x` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="42c5b-122">Non si applica ai progetti che usano `netstandard2.x` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="42c5b-123">Utilizzare la `NetStandardImplicitPackageVersion` proprietà quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) .</span><span class="sxs-lookup"><span data-stu-id="42c5b-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="42c5b-124">Il file di progetto nell'esempio seguente è destinato a `netstandard1.3` , ma usa la versione 1.6.0 di `NETStandard.Library` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="42c5b-125">Proprietà del pacchetto</span><span class="sxs-lookup"><span data-stu-id="42c5b-125">Package properties</span></span>

<span data-ttu-id="42c5b-126">È possibile specificare proprietà quali `PackageId` ,, `PackageVersion` `PackageIcon` , `Title` e `Description` per descrivere il pacchetto che viene creato dal progetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="42c5b-127">Per informazioni su queste e altre proprietà, vedere [destinazione Pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="42c5b-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="42c5b-128">Pubblicare proprietà ed elementi</span><span class="sxs-lookup"><span data-stu-id="42c5b-128">Publish properties and items</span></span>

- [<span data-ttu-id="42c5b-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="42c5b-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="42c5b-130">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="42c5b-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="42c5b-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="42c5b-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="42c5b-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="42c5b-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="42c5b-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="42c5b-133">RuntimeIdentifier</span></span>

<span data-ttu-id="42c5b-134">La `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="42c5b-135">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="42c5b-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="42c5b-136">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="42c5b-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="42c5b-137">La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="42c5b-138">Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime.</span><span class="sxs-lookup"><span data-stu-id="42c5b-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="42c5b-139">`RuntimeIdentifiers`viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="42c5b-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="42c5b-140">`RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un singolo runtime.</span><span class="sxs-lookup"><span data-stu-id="42c5b-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="42c5b-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="42c5b-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="42c5b-142">L' `TrimmerRootAssembly` elemento consente di escludere un assembly dal [*taglio*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="42c5b-143">Il trimming è il processo di rimozione delle parti inutilizzate del runtime da un'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="42c5b-144">In alcuni casi, il trimming potrebbe rimuovere erroneamente i riferimenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="42c5b-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="42c5b-145">Il codice XML seguente esclude l' `System.Security` assembly dalla rimozione.</span><span class="sxs-lookup"><span data-stu-id="42c5b-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="42c5b-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="42c5b-146">UseAppHost</span></span>

<span data-ttu-id="42c5b-147">La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 del .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="42c5b-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="42c5b-148">Controlla se viene creato un file eseguibile nativo per una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="42c5b-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="42c5b-149">Per le distribuzioni autosufficienti è necessario un eseguibile nativo.</span><span class="sxs-lookup"><span data-stu-id="42c5b-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="42c5b-150">In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework.</span><span class="sxs-lookup"><span data-stu-id="42c5b-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="42c5b-151">Impostare la `UseAppHost` proprietà su `false` per disabilitare la generazione del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="42c5b-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="42c5b-152">Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="42c5b-153">Proprietà di compilazione</span><span class="sxs-lookup"><span data-stu-id="42c5b-153">Compile properties</span></span>

- [<span data-ttu-id="42c5b-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="42c5b-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="42c5b-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="42c5b-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="42c5b-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="42c5b-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="42c5b-157">La `EmbeddedResourceUseDependentUponConvention` proprietà definisce se i nomi dei file manifesto delle risorse vengono generati da informazioni sul tipo nei file di origine che sono collocati con file di risorse.</span><span class="sxs-lookup"><span data-stu-id="42c5b-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="42c5b-158">Se, ad esempio, *Form1. resx* si trova nella stessa cartella di *Form1.cs*e `EmbeddedResourceUseDependentUponConvention` è impostato su `true` , il file con *estensione resources* generato prende il nome dal primo tipo definito in *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="42c5b-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="42c5b-159">Se, ad esempio, `MyNamespace.Form1` è il primo tipo definito in *Form1.cs*, il nome del file generato è *MyNamespace. Form1. resources*.</span><span class="sxs-lookup"><span data-stu-id="42c5b-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="42c5b-160">Se `LogicalName` `ManifestResourceName` `DependentUpon` per un elemento sono specificati i metadati, o `EmbeddedResource` , il nome del file manifesto generato per quel file di risorse è invece basato su tali metadati.</span><span class="sxs-lookup"><span data-stu-id="42c5b-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="42c5b-161">Per impostazione predefinita, in un nuovo progetto .NET Core questa proprietà è impostata su `true` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="42c5b-162">Se è impostato su `false` e `LogicalName` `ManifestResourceName` `DependentUpon` per l'elemento nel file di progetto non sono specificati metadati, o, `EmbeddedResource` il nome del file manifesto della risorsa è basato sullo spazio dei nomi radice per il progetto e sul percorso file relativo del file con *estensione resx* .</span><span class="sxs-lookup"><span data-stu-id="42c5b-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="42c5b-163">Per ulteriori informazioni, vedere [come vengono denominati i file manifesto delle risorse](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="42c5b-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="42c5b-164">LangVersion</span></span>

<span data-ttu-id="42c5b-165">La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="42c5b-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="42c5b-166">Se ad esempio si desidera accedere alle funzionalità di anteprima C#, impostare `LangVersion` su `preview` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="42c5b-167">Per ulteriori informazioni, vedere [controllo delle versioni del linguaggio C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="42c5b-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="42c5b-168">Proprietà di configurazione in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="42c5b-168">Run-time configuration properties</span></span>

<span data-ttu-id="42c5b-169">È possibile configurare alcuni comportamenti in fase di esecuzione specificando le proprietà MSBuild nel file di progetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="42c5b-169">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="42c5b-170">Per informazioni su altri modi di configurare il comportamento in fase di esecuzione, vedere [impostazioni di configurazione di runtime di .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-170">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="42c5b-171">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="42c5b-171">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="42c5b-172">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="42c5b-172">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="42c5b-173">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="42c5b-173">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="42c5b-174">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="42c5b-174">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="42c5b-175">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="42c5b-175">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="42c5b-176">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="42c5b-176">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="42c5b-177">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="42c5b-177">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="42c5b-178">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="42c5b-178">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="42c5b-179">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="42c5b-179">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="42c5b-180">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="42c5b-180">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="42c5b-181">La `ConcurrentGarbageCollection` Proprietà configura se la [Garbage Collection di sfondo (simultanea)](../../standard/garbage-collection/background-gc.md) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="42c5b-181">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="42c5b-182">Impostare il valore su `false` per disabilitare lo sfondo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="42c5b-182">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="42c5b-183">Per ulteriori informazioni, vedere [System. GC. Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span><span class="sxs-lookup"><span data-stu-id="42c5b-183">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="42c5b-184">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="42c5b-184">InvariantGlobalization</span></span>

<span data-ttu-id="42c5b-185">La `InvariantGlobalization` Proprietà configura se l'app viene eseguita in modalità di *globalizzazione invariante* , il che significa che non ha accesso a dati specifici delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="42c5b-185">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="42c5b-186">Impostare il valore su `true` per l'esecuzione in modalità invariante di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="42c5b-186">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="42c5b-187">Per altre informazioni, vedere [modalità invariante](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="42c5b-187">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="42c5b-188">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="42c5b-188">RetainVMGarbageCollection</span></span>

<span data-ttu-id="42c5b-189">La `RetainVMGarbageCollection` Proprietà configura il Garbage Collector per inserire i segmenti di memoria eliminati in un elenco di standby per un uso futuro o per rilasciarli.</span><span class="sxs-lookup"><span data-stu-id="42c5b-189">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="42c5b-190">L'impostazione del valore su `true` indica al Garbage Collector di inserire i segmenti in un elenco di standby.</span><span class="sxs-lookup"><span data-stu-id="42c5b-190">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="42c5b-191">Per ulteriori informazioni, vedere [System. GC. RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span><span class="sxs-lookup"><span data-stu-id="42c5b-191">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="42c5b-192">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="42c5b-192">ServerGarbageCollection</span></span>

<span data-ttu-id="42c5b-193">La `ServerGarbageCollection` proprietà consente di configurare se l'applicazione utilizza la [workstation Garbage Collection o Garbage Collection server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="42c5b-193">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="42c5b-194">Impostare il valore su `true` per utilizzare server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="42c5b-194">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="42c5b-195">Per ulteriori informazioni, vedere [System. GC. Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span><span class="sxs-lookup"><span data-stu-id="42c5b-195">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="42c5b-196">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="42c5b-196">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="42c5b-197">La `ThreadPoolMaxThreads` Proprietà configura il numero massimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="42c5b-197">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="42c5b-198">Per altre informazioni, vedere [numero massimo di thread](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="42c5b-198">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="42c5b-199">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="42c5b-199">ThreadPoolMinThreads</span></span>

<span data-ttu-id="42c5b-200">La `ThreadPoolMinThreads` Proprietà configura il numero minimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="42c5b-200">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="42c5b-201">Per ulteriori informazioni, vedere [thread minimi](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="42c5b-201">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="42c5b-202">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="42c5b-202">TieredCompilation</span></span>

<span data-ttu-id="42c5b-203">La `TieredCompilation` Proprietà configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="42c5b-203">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="42c5b-204">Impostare il valore su `false` per disabilitare la compilazione a livelli.</span><span class="sxs-lookup"><span data-stu-id="42c5b-204">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="42c5b-205">Per altre informazioni, vedere [compilazione a livelli](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="42c5b-205">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="42c5b-206">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="42c5b-206">TieredCompilationQuickJit</span></span>

<span data-ttu-id="42c5b-207">La `TieredCompilationQuickJit` Proprietà configura se il compilatore JIT utilizza JIT rapido.</span><span class="sxs-lookup"><span data-stu-id="42c5b-207">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="42c5b-208">Impostare il valore su `false` per disabilitare Quick JIT.</span><span class="sxs-lookup"><span data-stu-id="42c5b-208">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="42c5b-209">Per altre informazioni, vedere [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="42c5b-209">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="42c5b-210">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="42c5b-210">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="42c5b-211">La `TieredCompilationQuickJitForLoops` Proprietà configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="42c5b-211">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="42c5b-212">Impostare il valore su `true` per abilitare Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="42c5b-212">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="42c5b-213">Per altre informazioni, vedere [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="42c5b-213">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="42c5b-214">Proprietà e elementi di riferimento</span><span class="sxs-lookup"><span data-stu-id="42c5b-214">Reference properties and items</span></span>

- [<span data-ttu-id="42c5b-215">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="42c5b-215">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="42c5b-216">PackageReference</span><span class="sxs-lookup"><span data-stu-id="42c5b-216">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="42c5b-217">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="42c5b-217">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="42c5b-218">Riferimento</span><span class="sxs-lookup"><span data-stu-id="42c5b-218">Reference</span></span>](#reference)
- [<span data-ttu-id="42c5b-219">Ripristino delle proprietà</span><span class="sxs-lookup"><span data-stu-id="42c5b-219">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="42c5b-220">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="42c5b-220">AssetTargetFallback</span></span>

<span data-ttu-id="42c5b-221">La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del Framework compatibili per i riferimenti al progetto e i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="42c5b-221">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="42c5b-222">Se ad esempio si specifica una dipendenza del pacchetto usando `PackageReference` ma il pacchetto non contiene risorse compatibili con i progetti `TargetFramework` , la `AssetTargetFallback` Proprietà entra in gioco.</span><span class="sxs-lookup"><span data-stu-id="42c5b-222">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="42c5b-223">La compatibilità del pacchetto a cui si fa riferimento viene riverificata utilizzando ogni Framework di destinazione specificato in `AssetTargetFallback` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-223">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="42c5b-224">È possibile impostare la `AssetTargetFallback` proprietà su una o più [versioni di Framework di destinazione](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="42c5b-224">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="42c5b-225">PackageReference</span><span class="sxs-lookup"><span data-stu-id="42c5b-225">PackageReference</span></span>

<span data-ttu-id="42c5b-226">L' `PackageReference` elemento definisce un riferimento a un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="42c5b-226">The `PackageReference` item defines a reference to a NuGet package.</span></span> <span data-ttu-id="42c5b-227">Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="42c5b-227">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="42c5b-228">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-228">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="42c5b-229">L' `Version` attributo specifica la versione o l'intervallo di versioni.</span><span class="sxs-lookup"><span data-stu-id="42c5b-229">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="42c5b-230">Per informazioni su come specificare una versione minima, una versione massima, un intervallo o una corrispondenza esatta, vedere [intervalli di versioni](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="42c5b-230">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="42c5b-231">È anche possibile aggiungere i metadati seguenti a un riferimento al progetto: `IncludeAssets` , `ExcludeAssets` e `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-231">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="42c5b-232">Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="42c5b-232">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="42c5b-233">Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="42c5b-233">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="42c5b-234">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="42c5b-234">ProjectReference</span></span>

<span data-ttu-id="42c5b-235">L' `ProjectReference` elemento definisce un riferimento a un altro progetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-235">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="42c5b-236">Il progetto a cui si fa riferimento viene aggiunto come dipendenza del pacchetto NuGet, ovvero viene considerato come un `PackageReference` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-236">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="42c5b-237">L' `Include` attributo specifica il percorso del progetto.</span><span class="sxs-lookup"><span data-stu-id="42c5b-237">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="42c5b-238">È anche possibile aggiungere i metadati seguenti a un riferimento al progetto: `IncludeAssets` , `ExcludeAssets` e `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-238">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="42c5b-239">Il frammento di file di progetto nell'esempio seguente fa riferimento a un progetto denominato `Project2` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-239">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="42c5b-240">Riferimento</span><span class="sxs-lookup"><span data-stu-id="42c5b-240">Reference</span></span>

<span data-ttu-id="42c5b-241">L' `Reference` elemento definisce un riferimento a un file di assembly.</span><span class="sxs-lookup"><span data-stu-id="42c5b-241">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="42c5b-242">L' `Include` attributo specifica il nome del file e i `HintPath` metadati specificano il percorso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="42c5b-242">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="42c5b-243">Ripristino delle proprietà</span><span class="sxs-lookup"><span data-stu-id="42c5b-243">Restore properties</span></span>

<span data-ttu-id="42c5b-244">Il ripristino di un pacchetto a cui viene fatto riferimento consente di installare tutte le dipendenze dirette e tutte le dipendenze di tali dipendenze.</span><span class="sxs-lookup"><span data-stu-id="42c5b-244">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="42c5b-245">È possibile personalizzare il ripristino dei pacchetti specificando proprietà quali `RestorePackagesPath` e `RestoreIgnoreFailedSources` .</span><span class="sxs-lookup"><span data-stu-id="42c5b-245">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="42c5b-246">Per altre informazioni su queste e altre proprietà, vedere [destinazione di ripristino](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="42c5b-246">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="42c5b-247">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42c5b-247">See also</span></span>

- [<span data-ttu-id="42c5b-248">Riferimento allo schema MSBuild</span><span class="sxs-lookup"><span data-stu-id="42c5b-248">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="42c5b-249">Proprietà MSBuild comuni</span><span class="sxs-lookup"><span data-stu-id="42c5b-249">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="42c5b-250">Proprietà di MSBuild per il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="42c5b-250">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="42c5b-251">Proprietà di MSBuild per il ripristino di NuGet</span><span class="sxs-lookup"><span data-stu-id="42c5b-251">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="42c5b-252">Personalizzare una compilazione</span><span class="sxs-lookup"><span data-stu-id="42c5b-252">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
