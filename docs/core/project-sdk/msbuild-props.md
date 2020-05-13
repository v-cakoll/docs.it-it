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
# <a name="msbuild-reference-for-net-core-sdk-projects"></a>Informazioni di riferimento su MSBuild per progetti .NET Core SDK

Questa pagina è un riferimento per le proprietà e gli elementi di MSBuild che è possibile usare per configurare i progetti .NET Core.

> [!NOTE]
> Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK. Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Proprietà del Framework

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

La `TargetFramework` proprietà specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages). Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Usare la `TargetFrameworks` proprietà quando si vuole che l'app sia destinata a più piattaforme. Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).

> [!NOTE]
> Questa proprietà viene ignorata se `TargetFramework` viene specificato (singolare).

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Questa proprietà si applica solo ai progetti che usano `netstandard1.x` . Non si applica ai progetti che usano `netstandard2.x` .

Utilizzare la `NetStandardImplicitPackageVersion` proprietà quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) . Il file di progetto nell'esempio seguente è destinato a `netstandard1.3` , ma usa la versione 1.6.0 di `NETStandard.Library` .

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a>Proprietà del pacchetto

È possibile specificare proprietà quali `PackageId` ,, `PackageVersion` `PackageIcon` , `Title` e `Description` per descrivere il pacchetto che viene creato dal progetto. Per informazioni su queste e altre proprietà, vedere [destinazione Pack](/nuget/reference/msbuild-targets#pack-target).

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a>Pubblicare proprietà ed elementi

- [RuntimeIdentifier](#runtimeidentifier)
- [Identificatori di runtime](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

La `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto. Il RID consente di pubblicare una distribuzione autonoma.

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a>Identificatori di runtime

La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto. Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime. `RuntimeIdentifiers`viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.

> [!TIP]
> `RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un singolo runtime.

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a>TrimmerRootAssembly

L' `TrimmerRootAssembly` elemento consente di escludere un assembly dal [*taglio*](../deploying/trim-self-contained.md). Il trimming è il processo di rimozione delle parti inutilizzate del runtime da un'applicazione in pacchetto. In alcuni casi, il trimming potrebbe rimuovere erroneamente i riferimenti richiesti.

Il codice XML seguente esclude l' `System.Security` assembly dalla rimozione.

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a>UseAppHost

La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 del .NET Core SDK. Controlla se viene creato un file eseguibile nativo per una distribuzione. Per le distribuzioni autosufficienti è necessario un eseguibile nativo.

In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework. Impostare la `UseAppHost` proprietà su `false` per disabilitare la generazione del file eseguibile.

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).

## <a name="compile-properties"></a>Proprietà di compilazione

- [EmbeddedResourceUseDependentUponConvention](#embeddedresourceusedependentuponconvention)
- [LangVersion](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a>EmbeddedResourceUseDependentUponConvention

La `EmbeddedResourceUseDependentUponConvention` proprietà definisce se i nomi dei file manifesto delle risorse vengono generati da informazioni sul tipo nei file di origine che sono collocati con file di risorse. Se, ad esempio, *Form1. resx* si trova nella stessa cartella di *Form1.cs*e `EmbeddedResourceUseDependentUponConvention` è impostato su `true` , il file con *estensione resources* generato prende il nome dal primo tipo definito in *Form1.cs*. Se, ad esempio, `MyNamespace.Form1` è il primo tipo definito in *Form1.cs*, il nome del file generato è *MyNamespace. Form1. resources*.

> [!NOTE]
> Se `LogicalName` `ManifestResourceName` `DependentUpon` per un elemento sono specificati i metadati, o `EmbeddedResource` , il nome del file manifesto generato per quel file di risorse è invece basato su tali metadati.

Per impostazione predefinita, in un nuovo progetto .NET Core questa proprietà è impostata su `true` . Se è impostato su `false` e `LogicalName` `ManifestResourceName` `DependentUpon` per l'elemento nel file di progetto non sono specificati metadati, o, `EmbeddedResource` il nome del file manifesto della risorsa è basato sullo spazio dei nomi radice per il progetto e sul percorso file relativo del file con *estensione resx* . Per ulteriori informazioni, vedere [come vengono denominati i file manifesto delle risorse](../resources/manifest-file-names.md).

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a>LangVersion

La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione. Se ad esempio si desidera accedere alle funzionalità di anteprima C#, impostare `LangVersion` su `preview` .

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
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

La `ConcurrentGarbageCollection` Proprietà configura se la [Garbage Collection di sfondo (simultanea)](../../standard/garbage-collection/background-gc.md) è abilitata. Impostare il valore su `false` per disabilitare lo sfondo Garbage Collection. Per ulteriori informazioni, vedere [System. GC. Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a>InvariantGlobalization

La `InvariantGlobalization` Proprietà configura se l'app viene eseguita in modalità di *globalizzazione invariante* , il che significa che non ha accesso a dati specifici delle impostazioni cultura. Impostare il valore su `true` per l'esecuzione in modalità invariante di globalizzazione. Per altre informazioni, vedere [modalità invariante](../run-time-config/globalization.md#invariant-mode).

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a>RetainVMGarbageCollection

La `RetainVMGarbageCollection` Proprietà configura il Garbage Collector per inserire i segmenti di memoria eliminati in un elenco di standby per un uso futuro o per rilasciarli. L'impostazione del valore su `true` indica al Garbage Collector di inserire i segmenti in un elenco di standby. Per ulteriori informazioni, vedere [System. GC. RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a>ServerGarbageCollection

La `ServerGarbageCollection` proprietà consente di configurare se l'applicazione utilizza la [workstation Garbage Collection o Garbage Collection server](../../standard/garbage-collection/workstation-server-gc.md). Impostare il valore su `true` per utilizzare server Garbage Collection. Per ulteriori informazioni, vedere [System. GC. Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a>ThreadPoolMaxThreads

La `ThreadPoolMaxThreads` Proprietà configura il numero massimo di thread per il pool di thread di lavoro. Per altre informazioni, vedere [numero massimo di thread](../run-time-config/threading.md#maximum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a>ThreadPoolMinThreads

La `ThreadPoolMinThreads` Proprietà configura il numero minimo di thread per il pool di thread di lavoro. Per ulteriori informazioni, vedere [thread minimi](../run-time-config/threading.md#minimum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a>TieredCompilation

La `TieredCompilation` Proprietà configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation). Impostare il valore su `false` per disabilitare la compilazione a livelli. Per altre informazioni, vedere [compilazione a livelli](../run-time-config/compilation.md#tiered-compilation).

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a>TieredCompilationQuickJit

La `TieredCompilationQuickJit` Proprietà configura se il compilatore JIT utilizza JIT rapido. Impostare il valore su `false` per disabilitare Quick JIT. Per altre informazioni, vedere [Quick JIT](../run-time-config/compilation.md#quick-jit).

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a>TieredCompilationQuickJitForLoops

La `TieredCompilationQuickJitForLoops` Proprietà configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli. Impostare il valore su `true` per abilitare Quick JIT sui metodi che contengono cicli. Per altre informazioni, vedere [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a>Proprietà e elementi di riferimento

- [AssetTargetFallback](#assettargetfallback)
- [PackageReference](#packagereference)
- [ProjectReference](#projectreference)
- [Riferimento](#reference)
- [Ripristino delle proprietà](#restore-properties)

### <a name="assettargetfallback"></a>AssetTargetFallback

La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del Framework compatibili per i riferimenti al progetto e i pacchetti NuGet. Se ad esempio si specifica una dipendenza del pacchetto usando `PackageReference` ma il pacchetto non contiene risorse compatibili con i progetti `TargetFramework` , la `AssetTargetFallback` Proprietà entra in gioco. La compatibilità del pacchetto a cui si fa riferimento viene riverificata utilizzando ogni Framework di destinazione specificato in `AssetTargetFallback` .

È possibile impostare la `AssetTargetFallback` proprietà su una o più [versioni di Framework di destinazione](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a>PackageReference

L' `PackageReference` elemento definisce un riferimento a un pacchetto NuGet. Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages).

L'attributo `Include` specifica l'ID del pacchetto. L' `Version` attributo specifica la versione o l'intervallo di versioni. Per informazioni su come specificare una versione minima, una versione massima, un intervallo o una corrispondenza esatta, vedere [intervalli di versioni](/nuget/concepts/package-versioning#version-ranges). È anche possibile aggiungere i metadati seguenti a un riferimento al progetto: `IncludeAssets` , `ExcludeAssets` e `PrivateAssets` .

Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).

### <a name="projectreference"></a>ProjectReference

L' `ProjectReference` elemento definisce un riferimento a un altro progetto. Il progetto a cui si fa riferimento viene aggiunto come dipendenza del pacchetto NuGet, ovvero viene considerato come un `PackageReference` .

L' `Include` attributo specifica il percorso del progetto. È anche possibile aggiungere i metadati seguenti a un riferimento al progetto: `IncludeAssets` , `ExcludeAssets` e `PrivateAssets` .

Il frammento di file di progetto nell'esempio seguente fa riferimento a un progetto denominato `Project2` .

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a>Riferimento

L' `Reference` elemento definisce un riferimento a un file di assembly.

L' `Include` attributo specifica il nome del file e i `HintPath` metadati specificano il percorso dell'assembly.

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a>Ripristino delle proprietà

Il ripristino di un pacchetto a cui viene fatto riferimento consente di installare tutte le dipendenze dirette e tutte le dipendenze di tali dipendenze. È possibile personalizzare il ripristino dei pacchetti specificando proprietà quali `RestorePackagesPath` e `RestoreIgnoreFailedSources` . Per altre informazioni su queste e altre proprietà, vedere [destinazione di ripristino](/nuget/reference/msbuild-targets#restore-target).

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a>Vedere anche

- [Riferimento allo schema MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties)
- [Proprietà di MSBuild per il pacchetto NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Proprietà di MSBuild per il ripristino di NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Personalizzare una compilazione](/visualstudio/msbuild/customize-your-build)
