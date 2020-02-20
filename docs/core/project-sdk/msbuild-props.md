---
title: Proprietà di MSBuild per Microsoft. NET. SDK
description: Riferimento per le proprietà MSBuild riconosciute dal .NET Core SDK.
ms.date: 02/02/2020
ms.topic: reference
ms.openlocfilehash: f5dc2079bc313b8dd9fa5556cd941521a597ae38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453811"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>Proprietà MSBuild per progetti .NET Core SDK

Questa pagina descrive le proprietà di MSBuild per la configurazione di progetti .NET Core.

> [!NOTE]
> Questa pagina è un lavoro in corso e non elenca tutte le proprietà di MSBuild utili per la .NET Core SDK. Per un elenco di proprietà MSBuild comuni, vedere [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Proprietà del Framework

- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)
- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Questa proprietà si applica solo ai progetti che usano `netstandard1.x`. Non si applica ai progetti che usano `netstandard2` e versioni successive.

Utilizzare la proprietà `NetStandardImplicitPackageVersion` quando si desidera specificare una versione del Framework inferiore alla versione del [metapacchetto](../packages.md#metapackages) . Il file di progetto nell'esempio seguente ha come destinazione `netstandard1.3` ma usa la versione 1.6.0 di `NETStandard.Library`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

### <a name="targetframework"></a>TargetFramework

La proprietà `TargetFramework` specifica la versione del Framework di destinazione per l'app, che fa riferimento in modo implicito a un [metapacchetto](../packages.md#metapackages). Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Usare la proprietà `TargetFrameworks` quando si vuole che l'app sia destinata a più piattaforme. Per un elenco dei moniker di Framework di destinazione validi, vedere [Framework di destinazione nei progetti di tipo SDK](../../standard/frameworks.md#supported-target-framework-versions).

> [!NOTE]
> Questa proprietà viene ignorata se viene specificato `TargetFramework` (Singular).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

Per altre informazioni, vedere [Framework di destinazione nei progetti in stile SDK](../../standard/frameworks.md).

## <a name="publish-properties"></a>Pubblica proprietà

- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

Il `RuntimeIdentifier` proprietà consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto. Il RID consente di pubblicare una distribuzione autonoma.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>Identificatori di runtime

La proprietà `RuntimeIdentifiers` consente di specificare un elenco delimitato da punti e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto. Usare questa proprietà se è necessario eseguire la pubblicazione per più Runtime. `RuntimeIdentifiers` viene usato in fase di ripristino per assicurarsi che le risorse corrette siano presenti nel grafico.

> [!TIP]
> `RuntimeIdentifier` (Singular) può fornire build più veloci quando è necessario un solo Runtime.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

La proprietà `UseAppHost` è stata introdotta nella versione 2.1.400 del .NET Core SDK. Controlla se viene creato un file eseguibile nativo per una distribuzione. Per le distribuzioni autosufficienti è necessario un eseguibile nativo.

In .NET Core 3,0 e versioni successive, per impostazione predefinita viene creato un file eseguibile dipendente dal Framework. Impostare la proprietà `UseAppHost` su `false` per disabilitare la generazione del file eseguibile.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

Per altre informazioni sulla distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).

## <a name="compile-properties"></a>Proprietà di compilazione

### <a name="langversion"></a>LangVersion

Il `LangVersion` proprietà consente di specificare una versione specifica del linguaggio di programmazione. Se ad esempio si desidera accedere alle C# funzionalità di anteprima, impostare `LangVersion` su `preview`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

Per ulteriori informazioni, vedere [ C# controllo delle versioni dei linguaggi](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="nuget-packages"></a>Pacchetti NuGet

- [PackageReference](#packagereference)

### <a name="packagereference"></a>PackageReference

Il `PackageReference` elemento consente di specificare una dipendenza NuGet. Ad esempio, è possibile fare riferimento a un singolo pacchetto invece che a un [metapacchetto](../packages.md#metapackages). L'attributo `Include` specifica l'ID del pacchetto. Il frammento di file di progetto nell'esempio seguente fa riferimento al pacchetto [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

Per altre informazioni, vedere [riferimenti ai pacchetti nei file di progetto](/nuget/consume-packages/package-references-in-project-files).

### <a name="pack-and-restore-targets"></a>Destinazioni di Pack e ripristino

MSBuild 15,1 ha introdotto `pack` e `restore` destinazioni per la creazione e il ripristino di pacchetti NuGet come parte di una compilazione. Per informazioni sulle proprietà MSBuild per queste destinazioni, tra cui `PackageTargetFallback`, vedere [Pack e Restore di NuGet come destinazioni MSBuild](/nuget/reference/msbuild-targets).

## <a name="see-also"></a>Vedere anche

- [Riferimento allo schema MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Proprietà MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties)
- [Proprietà di MSBuild per il pacchetto NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Proprietà di MSBuild per il ripristino di NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Personalizzare una compilazione](/visualstudio/msbuild/customize-your-build)
