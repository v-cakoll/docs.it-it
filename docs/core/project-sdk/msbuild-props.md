---
title: Proprietà di MSBuild per Microsoft. NET. SDK
description: Riferimento per le proprietà MSBuild riconosciute dal .NET Core SDK.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 105b7d67ea24515ea88481cb4a4fe42d2a03cfd0
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506789"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="4b71f-103">Proprietà MSBuild per progetti .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="4b71f-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="4b71f-104">Questa pagina descrive le proprietà di MSBuild per la configurazione di progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b71f-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="4b71f-105">Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="4b71f-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="4b71f-106">Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="4b71f-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="4b71f-107">Proprietà del Framework</span><span class="sxs-lookup"><span data-stu-id="4b71f-107">Framework properties</span></span>

- [<span data-ttu-id="4b71f-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="4b71f-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="4b71f-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="4b71f-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="4b71f-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="4b71f-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="4b71f-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="4b71f-111">TargetFramework</span></span>

<span data-ttu-id="4b71f-112">La `TargetFramework` proprietà specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="4b71f-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="4b71f-113">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="4b71f-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4b71f-114">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="4b71f-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="4b71f-115">TargetFrameworks</span></span>

<span data-ttu-id="4b71f-116">Usare la `TargetFrameworks` proprietà quando si vuole che l'app sia destinata a più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="4b71f-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="4b71f-117">Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="4b71f-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="4b71f-118">Questa proprietà viene ignorata `TargetFramework` se viene specificato (singolare).</span><span class="sxs-lookup"><span data-stu-id="4b71f-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4b71f-119">Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="4b71f-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="4b71f-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="4b71f-121">Questa proprietà si applica solo ai progetti `netstandard1.x`che usano.</span><span class="sxs-lookup"><span data-stu-id="4b71f-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="4b71f-122">Non si applica ai progetti che usano `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="4b71f-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="4b71f-123">Utilizzare la `NetStandardImplicitPackageVersion` proprietà quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) .</span><span class="sxs-lookup"><span data-stu-id="4b71f-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="4b71f-124">Il file di progetto nell'esempio seguente è `netstandard1.3` destinato a, ma usa la `NETStandard.Library`versione 1.6.0 di.</span><span class="sxs-lookup"><span data-stu-id="4b71f-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="4b71f-125">Pubblica proprietà</span><span class="sxs-lookup"><span data-stu-id="4b71f-125">Publish properties</span></span>

- [<span data-ttu-id="4b71f-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="4b71f-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="4b71f-127">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="4b71f-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="4b71f-128">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="4b71f-128">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="4b71f-129">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="4b71f-129">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="4b71f-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="4b71f-130">RuntimeIdentifier</span></span>

<span data-ttu-id="4b71f-131">La `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4b71f-131">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="4b71f-132">Il RID consente di pubblicare una distribuzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="4b71f-132">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="4b71f-133">Identificatori di runtime</span><span class="sxs-lookup"><span data-stu-id="4b71f-133">RuntimeIdentifiers</span></span>

<span data-ttu-id="4b71f-134">La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4b71f-134">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="4b71f-135">Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime.</span><span class="sxs-lookup"><span data-stu-id="4b71f-135">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="4b71f-136">`RuntimeIdentifiers`viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.</span><span class="sxs-lookup"><span data-stu-id="4b71f-136">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="4b71f-137">`RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un singolo runtime.</span><span class="sxs-lookup"><span data-stu-id="4b71f-137">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="4b71f-138">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="4b71f-138">TrimmerRootAssembly</span></span>

<span data-ttu-id="4b71f-139">L' `TrimmerRootAssembly` elemento consente di escludere un assembly dal [*taglio*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-139">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="4b71f-140">Il trimming è il processo di rimozione delle parti inutilizzate del runtime da un'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4b71f-140">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="4b71f-141">In alcuni casi, il trimming potrebbe rimuovere erroneamente i riferimenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="4b71f-141">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="4b71f-142">Il codice XML seguente esclude l' `System.Security` assembly dalla rimozione.</span><span class="sxs-lookup"><span data-stu-id="4b71f-142">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="4b71f-143">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="4b71f-143">UseAppHost</span></span>

<span data-ttu-id="4b71f-144">La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 del .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="4b71f-144">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="4b71f-145">Controlla se viene creato un file eseguibile nativo per una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4b71f-145">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="4b71f-146">Per le distribuzioni autosufficienti è necessario un eseguibile nativo.</span><span class="sxs-lookup"><span data-stu-id="4b71f-146">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="4b71f-147">In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework.</span><span class="sxs-lookup"><span data-stu-id="4b71f-147">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="4b71f-148">Impostare la `UseAppHost` proprietà su `false` per disabilitare la generazione del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4b71f-148">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4b71f-149">Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-149">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="4b71f-150">Proprietà di compilazione</span><span class="sxs-lookup"><span data-stu-id="4b71f-150">Compile properties</span></span>

- [<span data-ttu-id="4b71f-151">LangVersion</span><span class="sxs-lookup"><span data-stu-id="4b71f-151">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="4b71f-152">LangVersion</span><span class="sxs-lookup"><span data-stu-id="4b71f-152">LangVersion</span></span>

<span data-ttu-id="4b71f-153">La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4b71f-153">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="4b71f-154">Se ad esempio si desidera accedere alle funzionalità di anteprima C#, impostare `LangVersion` su `preview`.</span><span class="sxs-lookup"><span data-stu-id="4b71f-154">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4b71f-155">Per ulteriori informazioni, vedere [controllo delle versioni del linguaggio C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="4b71f-155">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="4b71f-156">Proprietà di configurazione in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="4b71f-156">Run-time configuration properties</span></span>

<span data-ttu-id="4b71f-157">È possibile configurare alcuni comportamenti in fase di esecuzione specificando le proprietà MSBuild nel file di progetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="4b71f-157">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="4b71f-158">Per informazioni su altri modi di configurare il comportamento in fase di esecuzione, vedere [impostazioni di configurazione di runtime di .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-158">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="4b71f-159">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="4b71f-159">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="4b71f-160">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="4b71f-160">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="4b71f-161">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="4b71f-161">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="4b71f-162">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="4b71f-162">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="4b71f-163">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="4b71f-163">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="4b71f-164">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="4b71f-164">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="4b71f-165">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="4b71f-165">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="4b71f-166">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="4b71f-166">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="4b71f-167">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="4b71f-167">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="4b71f-168">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="4b71f-168">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="4b71f-169">La `ConcurrentGarbageCollection` proprietà configura se la [Garbage Collection di sfondo (simultanea)](../../standard/garbage-collection/background-gc.md) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4b71f-169">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="4b71f-170">Impostare il valore su `false` per disabilitare lo sfondo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4b71f-170">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="4b71f-171">Per ulteriori informazioni, vedere [System. GC. Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span><span class="sxs-lookup"><span data-stu-id="4b71f-171">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="invariantglobalization"></a><span data-ttu-id="4b71f-172">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="4b71f-172">InvariantGlobalization</span></span>

<span data-ttu-id="4b71f-173">La `InvariantGlobalization` proprietà configura se l'app viene eseguita in modalità di *globalizzazione invariante* , il che significa che non ha accesso a dati specifici delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="4b71f-173">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="4b71f-174">Impostare il valore su `true` per l'esecuzione in modalità invariante di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="4b71f-174">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="4b71f-175">Per altre informazioni, vedere [modalità invariante](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="4b71f-175">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>
</Project>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="4b71f-176">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="4b71f-176">RetainVMGarbageCollection</span></span>

<span data-ttu-id="4b71f-177">La `RetainVMGarbageCollection` proprietà configura il Garbage Collector per inserire i segmenti di memoria eliminati in un elenco di standby per un uso futuro o per rilasciarli.</span><span class="sxs-lookup"><span data-stu-id="4b71f-177">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="4b71f-178">L'impostazione del valore `true` su indica al Garbage Collector di inserire i segmenti in un elenco di standby.</span><span class="sxs-lookup"><span data-stu-id="4b71f-178">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="4b71f-179">Per ulteriori informazioni, vedere [System. GC. RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span><span class="sxs-lookup"><span data-stu-id="4b71f-179">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="4b71f-180">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="4b71f-180">ServerGarbageCollection</span></span>

<span data-ttu-id="4b71f-181">La `ServerGarbageCollection` proprietà consente di configurare se l'applicazione utilizza la [workstation Garbage Collection o Garbage Collection server](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-181">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="4b71f-182">Impostare il valore su `true` per utilizzare server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4b71f-182">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="4b71f-183">Per ulteriori informazioni, vedere [System. GC. Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span><span class="sxs-lookup"><span data-stu-id="4b71f-183">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="4b71f-184">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="4b71f-184">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="4b71f-185">La `ThreadPoolMaxThreads` proprietà configura il numero massimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4b71f-185">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="4b71f-186">Per altre informazioni, vedere [numero massimo di thread](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="4b71f-186">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>
</Project>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="4b71f-187">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="4b71f-187">ThreadPoolMinThreads</span></span>

<span data-ttu-id="4b71f-188">La `ThreadPoolMinThreads` proprietà configura il numero minimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4b71f-188">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="4b71f-189">Per ulteriori informazioni, vedere [thread minimi](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="4b71f-189">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilation"></a><span data-ttu-id="4b71f-190">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="4b71f-190">TieredCompilation</span></span>

<span data-ttu-id="4b71f-191">La `TieredCompilation` proprietà configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="4b71f-191">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="4b71f-192">Impostare il valore su `false` per disabilitare la compilazione a livelli.</span><span class="sxs-lookup"><span data-stu-id="4b71f-192">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="4b71f-193">Per altre informazioni, vedere [compilazione a livelli](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="4b71f-193">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="4b71f-194">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="4b71f-194">TieredCompilationQuickJit</span></span>

<span data-ttu-id="4b71f-195">La `TieredCompilationQuickJit` proprietà configura se il compilatore JIT utilizza JIT rapido.</span><span class="sxs-lookup"><span data-stu-id="4b71f-195">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="4b71f-196">Impostare il valore su `false` per disabilitare Quick JIT.</span><span class="sxs-lookup"><span data-stu-id="4b71f-196">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="4b71f-197">Per altre informazioni, vedere [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="4b71f-197">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="4b71f-198">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="4b71f-198">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="4b71f-199">La `TieredCompilationQuickJitForLoops` proprietà configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="4b71f-199">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="4b71f-200">Impostare il valore su `true` per abilitare Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="4b71f-200">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="4b71f-201">Per altre informazioni, vedere [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="4b71f-201">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>
</Project>
```

## <a name="nuget-packages"></a><span data-ttu-id="4b71f-202">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="4b71f-202">NuGet packages</span></span>

- [<span data-ttu-id="4b71f-203">PackageReference</span><span class="sxs-lookup"><span data-stu-id="4b71f-203">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="4b71f-204">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="4b71f-204">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="4b71f-205">PackageReference</span><span class="sxs-lookup"><span data-stu-id="4b71f-205">PackageReference</span></span>

<span data-ttu-id="4b71f-206">L' `PackageReference` elemento consente di specificare una dipendenza NuGet.</span><span class="sxs-lookup"><span data-stu-id="4b71f-206">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="4b71f-207">Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="4b71f-207">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="4b71f-208">L'attributo `Include` specifica l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4b71f-208">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="4b71f-209">Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="4b71f-209">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="4b71f-210">Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="4b71f-210">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="4b71f-211">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="4b71f-211">AssetTargetFallback</span></span>

<span data-ttu-id="4b71f-212">La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del Framework compatibili per i progetti a cui fa riferimento il progetto e i pacchetti NuGet utilizzati dal progetto.</span><span class="sxs-lookup"><span data-stu-id="4b71f-212">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="4b71f-213">Se ad esempio si specifica una dipendenza del pacchetto usando `PackageReference` ma il pacchetto non contiene risorse compatibili con i progetti `TargetFramework`, la `AssetTargetFallback` proprietà entra in gioco.</span><span class="sxs-lookup"><span data-stu-id="4b71f-213">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="4b71f-214">La compatibilità del pacchetto a cui si fa riferimento viene riverificata utilizzando ogni Framework di destinazione specificato `AssetTargetFallback`in.</span><span class="sxs-lookup"><span data-stu-id="4b71f-214">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="4b71f-215">È possibile impostare la `AssetTargetFallback` proprietà su una o più [versioni di Framework di destinazione](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="4b71f-215">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="4b71f-216">Destinazioni di Pack e ripristino</span><span class="sxs-lookup"><span data-stu-id="4b71f-216">Pack and restore targets</span></span>

<span data-ttu-id="4b71f-217">MSBuild 15,1 introduce `pack` e `restore` destinazioni per la creazione e il ripristino di pacchetti NuGet come parte di una compilazione.</span><span class="sxs-lookup"><span data-stu-id="4b71f-217">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="4b71f-218">Per informazioni sulle proprietà MSBuild per queste destinazioni, incluso `PackageTargetFallback`, vedere [Pack e Restore di NuGet come destinazioni MSBuild](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="4b71f-218">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b71f-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b71f-219">See also</span></span>

- [<span data-ttu-id="4b71f-220">Riferimento allo schema MSBuild</span><span class="sxs-lookup"><span data-stu-id="4b71f-220">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="4b71f-221">Proprietà MSBuild comuni</span><span class="sxs-lookup"><span data-stu-id="4b71f-221">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="4b71f-222">Proprietà di MSBuild per il pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="4b71f-222">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="4b71f-223">Proprietà di MSBuild per il ripristino di NuGet</span><span class="sxs-lookup"><span data-stu-id="4b71f-223">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="4b71f-224">Personalizzare una compilazione</span><span class="sxs-lookup"><span data-stu-id="4b71f-224">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
