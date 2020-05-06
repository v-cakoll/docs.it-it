---
title: Proprietà di MSBuild per Microsoft. NET. SDK
description: Riferimento per le proprietà MSBuild riconosciute dal .NET Core SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 800ff59310d8437d7f770bf20a5bdf37714f8515
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795573"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="f351a-103">Proprietà MSBuild per progetti .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f351a-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="f351a-104">Questa pagina descrive le proprietà di MSBuild per la configurazione di progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f351a-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span> <span data-ttu-id="f351a-105">È possibile specificare i *metadati* per ogni proprietà come elementi figlio della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f351a-105">You can specify *metadata* for each property as child elements of the property.</span></span>

> [!NOTE]
> <span data-ttu-id="f351a-106">Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f351a-106">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="f351a-107">Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="f351a-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="f351a-108">Proprietà del Framework</span><span class="sxs-lookup"><span data-stu-id="f351a-108">Framework properties</span></span>

- [<span data-ttu-id="f351a-109">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="f351a-109">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="f351a-110">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="f351a-110">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="f351a-111">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="f351a-111">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="f351a-112">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="f351a-112">TargetFramework</span></span>

<span data-ttu-id="f351a-113">La `TargetFramework` proprietà specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="f351a-113">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="f351a-114">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="f351a-114">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="f351a-115">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f351a-115">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="f351a-116">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="f351a-116">TargetFrameworks</span></span>

<span data-ttu-id="f351a-117">Usare la `TargetFrameworks` proprietà quando si vuole che l'app sia destinata a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="f351a-117">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="f351a-118">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="f351a-118">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="f351a-119">Questa proprietà viene ignorata `TargetFramework` se viene specificato (singolare).</span><span class="sxs-lookup"><span data-stu-id="f351a-119">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="f351a-120">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f351a-120">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="f351a-121">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="f351a-121">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="f351a-122">Questa proprietà si applica solo ai progetti `netstandard1.x`che usano.</span><span class="sxs-lookup"><span data-stu-id="f351a-122">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="f351a-123">Non si applica ai progetti che usano `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="f351a-123">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="f351a-124">Utilizzare la `NetStandardImplicitPackageVersion` proprietà quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) .</span><span class="sxs-lookup"><span data-stu-id="f351a-124">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="f351a-125">Il file di progetto nell'esempio seguente è `netstandard1.3` destinato a, ma usa la `NETStandard.Library`versione 1.6.0 di.</span><span class="sxs-lookup"><span data-stu-id="f351a-125">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="f351a-126">Proprietà del pacchetto</span><span class="sxs-lookup"><span data-stu-id="f351a-126">Package properties</span></span>

<span data-ttu-id="f351a-127">È possibile specificare `PackageId`proprietà quali, `PackageVersion`, `PackageIcon`, `Title`e `Description` per descrivere il pacchetto che viene creato dal progetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-127">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="f351a-128">Per informazioni su queste e altre proprietà, vedere [destinazione Pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="f351a-128">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties"></a><span data-ttu-id="f351a-129">Pubblica proprietà</span><span class="sxs-lookup"><span data-stu-id="f351a-129">Publish properties</span></span>

- [<span data-ttu-id="f351a-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="f351a-130">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="f351a-131">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="f351a-131">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="f351a-132">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="f351a-132">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="f351a-133">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="f351a-133">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="f351a-134">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="f351a-134">RuntimeIdentifier</span></span>

<span data-ttu-id="f351a-135">La `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-135">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="f351a-136">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="f351a-136">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="f351a-137">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="f351a-137">RuntimeIdentifiers</span></span>

<span data-ttu-id="f351a-138">La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-138">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="f351a-139">Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime.</span><span class="sxs-lookup"><span data-stu-id="f351a-139">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="f351a-140">`RuntimeIdentifiers`viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="f351a-140">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="f351a-141">`RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un singolo runtime.</span><span class="sxs-lookup"><span data-stu-id="f351a-141">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="f351a-142">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="f351a-142">TrimmerRootAssembly</span></span>

<span data-ttu-id="f351a-143">L' `TrimmerRootAssembly` elemento consente di escludere un assembly dal [*taglio*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="f351a-143">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="f351a-144">Il trimming è il processo di rimozione delle parti inutilizzate del runtime da un'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-144">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="f351a-145">In alcuni casi, il trimming potrebbe rimuovere erroneamente i riferimenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="f351a-145">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="f351a-146">Il codice XML seguente esclude l' `System.Security` assembly dalla rimozione.</span><span class="sxs-lookup"><span data-stu-id="f351a-146">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="f351a-147">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="f351a-147">UseAppHost</span></span>

<span data-ttu-id="f351a-148">La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 del .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="f351a-148">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="f351a-149">Controlla se viene creato un file eseguibile nativo per una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f351a-149">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="f351a-150">Per le distribuzioni autosufficienti è necessario un eseguibile nativo.</span><span class="sxs-lookup"><span data-stu-id="f351a-150">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="f351a-151">In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework.</span><span class="sxs-lookup"><span data-stu-id="f351a-151">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="f351a-152">Impostare la `UseAppHost` proprietà su `false` per disabilitare la generazione del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f351a-152">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="f351a-153">Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f351a-153">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="f351a-154">Proprietà di compilazione</span><span class="sxs-lookup"><span data-stu-id="f351a-154">Compile properties</span></span>

- [<span data-ttu-id="f351a-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="f351a-155">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="f351a-156">LangVersion</span><span class="sxs-lookup"><span data-stu-id="f351a-156">LangVersion</span></span>

<span data-ttu-id="f351a-157">La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="f351a-157">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="f351a-158">Se ad esempio si desidera accedere alle funzionalità di anteprima C#, impostare `LangVersion` su `preview`.</span><span class="sxs-lookup"><span data-stu-id="f351a-158">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="f351a-159">Per ulteriori informazioni, vedere [controllo delle versioni del linguaggio C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="f351a-159">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="f351a-160">Proprietà di configurazione in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f351a-160">Run-time configuration properties</span></span>

<span data-ttu-id="f351a-161">È possibile configurare alcuni comportamenti in fase di esecuzione specificando le proprietà MSBuild nel file di progetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="f351a-161">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="f351a-162">Per informazioni su altri modi di configurare il comportamento in fase di esecuzione, vedere [impostazioni di configurazione di runtime di .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="f351a-162">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="f351a-163">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="f351a-163">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="f351a-164">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="f351a-164">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="f351a-165">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="f351a-165">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="f351a-166">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="f351a-166">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="f351a-167">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="f351a-167">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="f351a-168">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="f351a-168">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="f351a-169">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="f351a-169">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="f351a-170">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="f351a-170">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="f351a-171">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="f351a-171">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="f351a-172">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="f351a-172">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="f351a-173">La `ConcurrentGarbageCollection` proprietà configura se la [Garbage Collection di sfondo (simultanea)](../../standard/garbage-collection/background-gc.md) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="f351a-173">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="f351a-174">Impostare il valore su `false` per disabilitare lo sfondo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f351a-174">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="f351a-175">Per ulteriori informazioni, vedere [System. GC. Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span><span class="sxs-lookup"><span data-stu-id="f351a-175">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="f351a-176">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="f351a-176">InvariantGlobalization</span></span>

<span data-ttu-id="f351a-177">La `InvariantGlobalization` proprietà configura se l'app viene eseguita in modalità di *globalizzazione invariante* , il che significa che non ha accesso a dati specifici delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f351a-177">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="f351a-178">Impostare il valore su `true` per l'esecuzione in modalità invariante di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="f351a-178">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="f351a-179">Per altre informazioni, vedere [modalità invariante](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="f351a-179">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="f351a-180">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="f351a-180">RetainVMGarbageCollection</span></span>

<span data-ttu-id="f351a-181">La `RetainVMGarbageCollection` proprietà configura il Garbage Collector per inserire i segmenti di memoria eliminati in un elenco di standby per un uso futuro o per rilasciarli.</span><span class="sxs-lookup"><span data-stu-id="f351a-181">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="f351a-182">L'impostazione del valore `true` su indica al Garbage Collector di inserire i segmenti in un elenco di standby.</span><span class="sxs-lookup"><span data-stu-id="f351a-182">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="f351a-183">Per ulteriori informazioni, vedere [System. GC. RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span><span class="sxs-lookup"><span data-stu-id="f351a-183">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="f351a-184">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="f351a-184">ServerGarbageCollection</span></span>

<span data-ttu-id="f351a-185">La `ServerGarbageCollection` proprietà consente di configurare se l'applicazione utilizza la [workstation Garbage Collection o Garbage Collection server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="f351a-185">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="f351a-186">Impostare il valore su `true` per utilizzare server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f351a-186">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="f351a-187">Per ulteriori informazioni, vedere [System. GC. Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span><span class="sxs-lookup"><span data-stu-id="f351a-187">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="f351a-188">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="f351a-188">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="f351a-189">La `ThreadPoolMaxThreads` proprietà configura il numero massimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f351a-189">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="f351a-190">Per altre informazioni, vedere [numero massimo di thread](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="f351a-190">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="f351a-191">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="f351a-191">ThreadPoolMinThreads</span></span>

<span data-ttu-id="f351a-192">La `ThreadPoolMinThreads` proprietà configura il numero minimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f351a-192">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="f351a-193">Per ulteriori informazioni, vedere [thread minimi](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="f351a-193">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="f351a-194">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="f351a-194">TieredCompilation</span></span>

<span data-ttu-id="f351a-195">La `TieredCompilation` proprietà configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="f351a-195">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="f351a-196">Impostare il valore su `false` per disabilitare la compilazione a livelli.</span><span class="sxs-lookup"><span data-stu-id="f351a-196">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="f351a-197">Per altre informazioni, vedere [compilazione a livelli](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="f351a-197">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="f351a-198">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="f351a-198">TieredCompilationQuickJit</span></span>

<span data-ttu-id="f351a-199">La `TieredCompilationQuickJit` proprietà configura se il compilatore JIT utilizza JIT rapido.</span><span class="sxs-lookup"><span data-stu-id="f351a-199">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="f351a-200">Impostare il valore su `false` per disabilitare Quick JIT.</span><span class="sxs-lookup"><span data-stu-id="f351a-200">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="f351a-201">Per altre informazioni, vedere [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="f351a-201">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="f351a-202">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="f351a-202">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="f351a-203">La `TieredCompilationQuickJitForLoops` proprietà configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="f351a-203">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="f351a-204">Impostare il valore su `true` per abilitare Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="f351a-204">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="f351a-205">Per altre informazioni, vedere [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="f351a-205">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties"></a><span data-ttu-id="f351a-206">Proprietà riferimento</span><span class="sxs-lookup"><span data-stu-id="f351a-206">Reference properties</span></span>

- [<span data-ttu-id="f351a-207">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="f351a-207">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="f351a-208">PackageReference</span><span class="sxs-lookup"><span data-stu-id="f351a-208">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="f351a-209">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="f351a-209">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="f351a-210">Riferimento</span><span class="sxs-lookup"><span data-stu-id="f351a-210">Reference</span></span>](#reference)
- [<span data-ttu-id="f351a-211">Ripristino delle proprietà</span><span class="sxs-lookup"><span data-stu-id="f351a-211">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="f351a-212">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="f351a-212">AssetTargetFallback</span></span>

<span data-ttu-id="f351a-213">La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del Framework compatibili per i riferimenti al progetto e i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="f351a-213">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="f351a-214">Se ad esempio si specifica una dipendenza del pacchetto usando `PackageReference` ma il pacchetto non contiene risorse compatibili con i progetti `TargetFramework`, la `AssetTargetFallback` proprietà entra in gioco.</span><span class="sxs-lookup"><span data-stu-id="f351a-214">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="f351a-215">La compatibilità del pacchetto a cui si fa riferimento viene riverificata utilizzando ogni Framework di destinazione specificato `AssetTargetFallback`in.</span><span class="sxs-lookup"><span data-stu-id="f351a-215">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="f351a-216">È possibile impostare la `AssetTargetFallback` proprietà su una o più [versioni di Framework di destinazione](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="f351a-216">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="f351a-217">PackageReference</span><span class="sxs-lookup"><span data-stu-id="f351a-217">PackageReference</span></span>

<span data-ttu-id="f351a-218">`PackageReference` Definisce un riferimento a un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="f351a-218">The `PackageReference` defines a reference to a NuGet package.</span></span> <span data-ttu-id="f351a-219">Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="f351a-219">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="f351a-220">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-220">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="f351a-221">L' `Version` attributo specifica la versione o l'intervallo di versioni.</span><span class="sxs-lookup"><span data-stu-id="f351a-221">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="f351a-222">Per informazioni su come specificare una versione minima, una versione massima, un intervallo o una corrispondenza esatta, vedere [intervalli di versioni](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="f351a-222">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="f351a-223">È anche possibile aggiungere i metadati seguenti a un riferimento al progetto `IncludeAssets`: `ExcludeAssets`, e `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="f351a-223">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="f351a-224">Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="f351a-224">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="f351a-225">Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="f351a-225">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="f351a-226">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="f351a-226">ProjectReference</span></span>

<span data-ttu-id="f351a-227">L' `ProjectReference` elemento definisce un riferimento a un altro progetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-227">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="f351a-228">Il progetto a cui si fa riferimento viene aggiunto come dipendenza del pacchetto NuGet, ovvero viene considerato come un `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="f351a-228">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="f351a-229">L' `Include` attributo specifica il percorso del progetto.</span><span class="sxs-lookup"><span data-stu-id="f351a-229">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="f351a-230">È anche possibile aggiungere i metadati seguenti a un riferimento al progetto `IncludeAssets`: `ExcludeAssets`, e `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="f351a-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="f351a-231">Il frammento di file di progetto nell'esempio seguente fa riferimento `Project2`a un progetto denominato.</span><span class="sxs-lookup"><span data-stu-id="f351a-231">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="f351a-232">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="f351a-232">Reference</span></span>

<span data-ttu-id="f351a-233">L' `Reference` elemento definisce un riferimento a un file di assembly.</span><span class="sxs-lookup"><span data-stu-id="f351a-233">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="f351a-234">L' `Include` attributo specifica il nome del file e l' `HintPath` elemento figlio specifica il percorso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f351a-234">The `Include` attribute specifies the name of the file, and the `HintPath` child element specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="f351a-235">Ripristino delle proprietà</span><span class="sxs-lookup"><span data-stu-id="f351a-235">Restore properties</span></span>

<span data-ttu-id="f351a-236">Il ripristino di un pacchetto a cui viene fatto riferimento consente di installare tutte le dipendenze dirette e tutte le dipendenze di tali dipendenze.</span><span class="sxs-lookup"><span data-stu-id="f351a-236">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="f351a-237">È possibile personalizzare il `RestorePackagesPath` ripristino dei pacchetti specificando proprietà quali `RestoreIgnoreFailedSources`e.</span><span class="sxs-lookup"><span data-stu-id="f351a-237">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="f351a-238">Per altre informazioni su queste e altre proprietà, vedere [destinazione di ripristino](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="f351a-238">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="f351a-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f351a-239">See also</span></span>

- [<span data-ttu-id="f351a-240">Riferimento allo schema MSBuild</span><span class="sxs-lookup"><span data-stu-id="f351a-240">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="f351a-241">Proprietà MSBuild comuni</span><span class="sxs-lookup"><span data-stu-id="f351a-241">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="f351a-242">Proprietà di MSBuild per il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="f351a-242">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="f351a-243">Proprietà di MSBuild per il ripristino di NuGet</span><span class="sxs-lookup"><span data-stu-id="f351a-243">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="f351a-244">Personalizzare una compilazione</span><span class="sxs-lookup"><span data-stu-id="f351a-244">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
