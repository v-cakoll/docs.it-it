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
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>Proprietà MSBuild per progetti .NET Core SDK

Questa pagina descrive le proprietà di MSBuild per la configurazione di progetti .NET Core.

> [!NOTE]
> Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK. Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Proprietà del Framework

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

La `TargetFramework` proprietà specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages). Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Usare la `TargetFrameworks` proprietà quando si vuole che l'app sia destinata a più piattaforme. Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).

> [!NOTE]
> Questa proprietà viene ignorata `TargetFramework` se viene specificato (singolare).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Questa proprietà si applica solo ai progetti `netstandard1.x`che usano. Non si applica ai progetti che usano `netstandard2.x`.

Utilizzare la `NetStandardImplicitPackageVersion` proprietà quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) . Il file di progetto nell'esempio seguente è `netstandard1.3` destinato a, ma usa la `NETStandard.Library`versione 1.6.0 di.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a>Pubblica proprietà

- [RuntimeIdentifier](#runtimeidentifier)
- [Identificatori di runtime](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

La `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto. Il RID consente di pubblicare una distribuzione autonoma.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>Identificatori di runtime

La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto. Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime. `RuntimeIdentifiers`viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.

> [!TIP]
> `RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un singolo runtime.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="trimmerrootassembly"></a>TrimmerRootAssembly

L' `TrimmerRootAssembly` elemento consente di escludere un assembly dal [*taglio*](../deploying/trim-self-contained.md). Il trimming è il processo di rimozione delle parti inutilizzate del runtime da un'applicazione in pacchetto. In alcuni casi, il trimming potrebbe rimuovere erroneamente i riferimenti richiesti.

Il codice XML seguente esclude l' `System.Security` assembly dalla rimozione.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 del .NET Core SDK. Controlla se viene creato un file eseguibile nativo per una distribuzione. Per le distribuzioni autosufficienti è necessario un eseguibile nativo.

In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework. Impostare la `UseAppHost` proprietà su `false` per disabilitare la generazione del file eseguibile.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).

## <a name="compile-properties"></a>Proprietà di compilazione

- [LangVersion](#langversion)

### <a name="langversion"></a>LangVersion

La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione. Se ad esempio si desidera accedere alle funzionalità di anteprima C#, impostare `LangVersion` su `preview`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

Per ulteriori informazioni, vedere [controllo delle versioni del linguaggio C#](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="run-time-configuration-properties"></a>Proprietà di configurazione in fase di esecuzione

È possibile configurare alcuni comportamenti in fase di esecuzione specificando le proprietà MSBuild nel file di progetto dell'app. Per informazioni su altri modi di configurare il comportamento in fase di esecuzione, vedere [impostazioni di configurazione di runtime di .NET Core](../run-time-config/index.md).

- [ConcurrentGarbageCollection](#concurrentgarbagecollection)
- [InvariantGlobalization](#invariantglobalization)
- [RetainVMGarbageCollection](#retainvmgarbagecollection)
- [ServerGarbageCollection](#servergarbagecollection)
- [ThreadPoolMaxThreads](#threadpoolmaxthreads)
- [ThreadPoolMinThreads](#threadpoolminthreads)
- [TieredCompilation](#tieredcompilation)
- [TieredCompilationQuickJit](#tieredcompilationquickjit)
- [TieredCompilationQuickJitForLoops](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a>ConcurrentGarbageCollection

La `ConcurrentGarbageCollection` proprietà configura se la [Garbage Collection di sfondo (simultanea)](../../standard/garbage-collection/background-gc.md) è abilitata. Impostare il valore su `false` per disabilitare lo sfondo Garbage Collection. Per ulteriori informazioni, vedere [System. GC. Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="invariantglobalization"></a>InvariantGlobalization

La `InvariantGlobalization` proprietà configura se l'app viene eseguita in modalità di *globalizzazione invariante* , il che significa che non ha accesso a dati specifici delle impostazioni cultura. Impostare il valore su `true` per l'esecuzione in modalità invariante di globalizzazione. Per altre informazioni, vedere [modalità invariante](../run-time-config/globalization.md#invariant-mode).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>
</Project>
```

### <a name="retainvmgarbagecollection"></a>RetainVMGarbageCollection

La `RetainVMGarbageCollection` proprietà configura il Garbage Collector per inserire i segmenti di memoria eliminati in un elenco di standby per un uso futuro o per rilasciarli. L'impostazione del valore `true` su indica al Garbage Collector di inserire i segmenti in un elenco di standby. Per ulteriori informazioni, vedere [System. GC. RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="servergarbagecollection"></a>ServerGarbageCollection

La `ServerGarbageCollection` proprietà consente di configurare se l'applicazione utilizza la [workstation Garbage Collection o Garbage Collection server](../../standard/garbage-collection/workstation-server-gc.md). Impostare il valore su `true` per utilizzare server Garbage Collection. Per ulteriori informazioni, vedere [System. GC. Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="threadpoolmaxthreads"></a>ThreadPoolMaxThreads

La `ThreadPoolMaxThreads` proprietà configura il numero massimo di thread per il pool di thread di lavoro. Per altre informazioni, vedere [numero massimo di thread](../run-time-config/threading.md#maximum-threads).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>
</Project>
```

### <a name="threadpoolminthreads"></a>ThreadPoolMinThreads

La `ThreadPoolMinThreads` proprietà configura il numero minimo di thread per il pool di thread di lavoro. Per ulteriori informazioni, vedere [thread minimi](../run-time-config/threading.md#minimum-threads).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilation"></a>TieredCompilation

La `TieredCompilation` proprietà configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation). Impostare il valore su `false` per disabilitare la compilazione a livelli. Per altre informazioni, vedere [compilazione a livelli](../run-time-config/compilation.md#tiered-compilation).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilationquickjit"></a>TieredCompilationQuickJit

La `TieredCompilationQuickJit` proprietà configura se il compilatore JIT utilizza JIT rapido. Impostare il valore su `false` per disabilitare Quick JIT. Per altre informazioni, vedere [Quick JIT](../run-time-config/compilation.md#quick-jit).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilationquickjitforloops"></a>TieredCompilationQuickJitForLoops

La `TieredCompilationQuickJitForLoops` proprietà configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli. Impostare il valore su `true` per abilitare Quick JIT sui metodi che contengono cicli. Per altre informazioni, vedere [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>
</Project>
```

## <a name="nuget-packages"></a>Pacchetti NuGet

- [PackageReference](#packagereference)
- [AssetTargetFallback](#assettargetfallback)

### <a name="packagereference"></a>PackageReference

L' `PackageReference` elemento consente di specificare una dipendenza NuGet. Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages). L'attributo `Include` specifica l'ID del pacchetto. Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).

### <a name="assettargetfallback"></a>AssetTargetFallback

La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del Framework compatibili per i progetti a cui fa riferimento il progetto e i pacchetti NuGet utilizzati dal progetto. Se ad esempio si specifica una dipendenza del pacchetto usando `PackageReference` ma il pacchetto non contiene risorse compatibili con i progetti `TargetFramework`, la `AssetTargetFallback` proprietà entra in gioco. La compatibilità del pacchetto a cui si fa riferimento viene riverificata utilizzando ogni Framework di destinazione specificato `AssetTargetFallback`in.

È possibile impostare la `AssetTargetFallback` proprietà su una o più [versioni di Framework di destinazione](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a>Destinazioni di Pack e ripristino

MSBuild 15,1 introduce `pack` e `restore` destinazioni per la creazione e il ripristino di pacchetti NuGet come parte di una compilazione. Per informazioni sulle proprietà MSBuild per queste destinazioni, incluso `PackageTargetFallback`, vedere [Pack e Restore di NuGet come destinazioni MSBuild](/nuget/reference/msbuild-targets).

## <a name="see-also"></a>Vedere anche

- [Riferimento allo schema MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties)
- [Proprietà di MSBuild per il pacchetto NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Proprietà di MSBuild per il ripristino di NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Personalizzare una compilazione](/visualstudio/msbuild/customize-your-build)
