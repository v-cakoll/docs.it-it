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
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>Proprietà MSBuild per progetti .NET Core SDK

In questa pagina vengono descritte le proprietà MSBuild per la configurazione di progetti .NET Core.This page describes MSBuild properties for configuring .NET Core projects.

> [!NOTE]
> Questa pagina è un work in progress e non elenca tutte le proprietà MSBuild utili per .NET Core SDK. Per un elenco delle proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Proprietà del framework

- [Quadro di destinazione](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>Quadro di destinazione

La `TargetFramework` proprietà specifica la versione del framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto.](../packages.md#metapackages) Per un elenco dei moniker del framework di destinazione validi, vedere Framework di destinazione [nei progetti in stile SDK.](../../standard/frameworks.md#supported-target-framework-versions)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Per ulteriori informazioni, consultate Framework di destinazione nei progetti in [stile SDK.](../../standard/frameworks.md)

### <a name="targetframeworks"></a>TargetFrameworks

Usa `TargetFrameworks` la proprietà quando vuoi che l'app sia destinata a più piattaforme. Per un elenco dei moniker del framework di destinazione validi, vedere Framework di destinazione [nei progetti in stile SDK.](../../standard/frameworks.md#supported-target-framework-versions)

> [!NOTE]
> Questa proprietà viene `TargetFramework` ignorata se viene specificato (singolare).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

Per ulteriori informazioni, consultate Framework di destinazione nei progetti in [stile SDK.](../../standard/frameworks.md)

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Questa proprietà si applica `netstandard1.x`solo ai progetti che utilizzano . Non si applica ai `netstandard2.x`progetti che utilizzano .

Utilizzare `NetStandardImplicitPackageVersion` la proprietà quando si desidera specificare una versione del framework inferiore alla versione del [metapacchetto.](../packages.md#metapackages) Il file di progetto `netstandard1.3` nell'esempio seguente è destinato `NETStandard.Library`ma utilizza la versione 1.6.0 di .

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
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

La `RuntimeIdentifier` proprietà consente di specificare un singolo identificatore di [runtime (RID)](../rid-catalog.md) per il progetto. Il RID consente di pubblicare una distribuzione autonoma.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>Identificatori di runtime

La `RuntimeIdentifiers` proprietà consente di specificare un elenco delimitato da punti e virgola di identificatori di [runtime (RIDE)](../rid-catalog.md) per il progetto. Utilizzare questa proprietà se è necessario pubblicare per più runtime. `RuntimeIdentifiers`viene utilizzato in fase di ripristino per garantire che le risorse corrette siano presenti nel grafico.

> [!TIP]
> `RuntimeIdentifier`(singolare) può fornire compilazioni più veloci quando è necessario un solo runtime.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

La `UseAppHost` proprietà è stata introdotta nella versione 2.1.400 di .NET Core SDK. Controlla se viene creato o meno un eseguibile nativo per una distribuzione. Per le distribuzioni autonome è necessario un eseguibile nativo.

In .NET Core 3.0 e versioni successive, un eseguibile dipendente dal framework viene creato per impostazione predefinita. Impostare `UseAppHost` la `false` proprietà su per disabilitare la generazione dell'eseguibile.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

Per ulteriori informazioni sulla distribuzione, vedere Distribuzione di [applicazioni .NET Core](../deploying/index.md).

## <a name="compile-properties"></a>Compile (proprietà)

### <a name="langversion"></a>LinguaVersione

La `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione. Se, ad esempio, si desidera accedere `LangVersion` alle `preview`funzionalità di anteprima di C, impostare su .

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

Per ulteriori informazioni, vedere [Controllo delle versioni del linguaggio C.](../../csharp/language-reference/configure-language-version.md#override-a-default)

## <a name="nuget-packages"></a>Pacchetti NuGet

- [PackageReference](#packagereference)
- [AssetTargetFallback](#assettargetfallback)

### <a name="packagereference"></a>PackageReference

L'elemento consente di specificare una dipendenza NuGet.The `PackageReference` item lets you specify a NuGet dependency. Ad esempio, è possibile fare riferimento a un singolo pacchetto anziché a un [metapacchetto](../packages.md#metapackages). L'attributo `Include` specifica l'ID del pacchetto. Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System.Runtime.The](https://www.nuget.org/packages/System.Runtime/) project file snippet in the following example references the System.Runtime package.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

Per ulteriori informazioni, consultate [Riferimenti ai pacchetti nei file](/nuget/consume-packages/package-references-in-project-files)di progetto.

### <a name="assettargetfallback"></a>AssetTargetFallback

La `AssetTargetFallback` proprietà consente di specificare versioni aggiuntive del framework compatibili per i progetti a cui il progetto fa riferimento e i pacchetti NuGet che utilizzano il progetto. Ad esempio, se si specifica `PackageReference` una dipendenza del pacchetto utilizzando ma tale pacchetto non `TargetFramework`contiene `AssetTargetFallback` asset compatibili con i progetti, la proprietà entra in gioco. La compatibilità del pacchetto a cui si fa riferimento `AssetTargetFallback`viene ricontrollata utilizzando ogni framework di destinazione specificato in .

È possibile `AssetTargetFallback` impostare la proprietà su una o più versioni del framework di [destinazione.](../../standard/frameworks.md#supported-target-framework-versions)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a>Imballare e ripristinare gli obiettivi

MSBuild 15.1 `pack` `restore` introdotto e destinazioni per la creazione e il ripristino di pacchetti NuGet come parte di una compilazione. Per informazioni sulle proprietà MSBuild per `PackageTargetFallback`queste destinazioni, tra cui , vedere [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sullo schema MSBuildMSBuild schema reference](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Proprietà MSBuild comuniCommon MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties)
- [Proprietà MSBuild per NuGet Pack](/nuget/reference/msbuild-targets#pack-target)
- [Proprietà MSBuild per il ripristino di NuGetMSBuild properties for NuGet restore](/nuget/reference/msbuild-targets#restore-properties)
- [Personalizzare una compilazione](/visualstudio/msbuild/customize-your-build)
