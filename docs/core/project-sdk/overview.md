---
title: Panoramica dell'SDK del progetto .NET Core
description: Informazioni sugli SDK per progetti .NET Core.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: c41b25bf7933e7b1f6cb50da5e52dc0b312f5c74
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626249"
---
# <a name="net-core-project-sdks"></a>SDK per progetti .NET Core

I progetti .NET Core sono associati a un Software Development Kit (SDK). Ogni SDK di progetto è un set di [destinazioni](/visualstudio/msbuild/msbuild-targets) MSBuild e [attività](/visualstudio/msbuild/msbuild-tasks) associate responsabili della compilazione, della compressione e della pubblicazione di codice.

## <a name="available-sdks"></a>SDK disponibili

Per .NET Core sono disponibili gli SDK seguenti:

| ID | Descrizione | Repo|
| - | - | - |
| `Microsoft.NET.Sdk` | .NET Core SDK | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | [SDK Web](/aspnet/core/razor-pages/web-sdk) di .NET Core | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk) |
| `Microsoft.NET.Sdk.Worker` | SDK del servizio Worker di .NET Core |
| `Microsoft.NET.Sdk.WindowsDesktop` | .NET Core WinForms e WPF SDK |

Il .NET Core SDK è l'SDK di base per .NET Core. Gli altri SDK fanno riferimento al .NET Core SDK e i progetti associati agli altri SDK hanno tutte le proprietà di .NET Core SDK disponibili. Il Web SDK, ad esempio, dipende dal .NET Core SDK e Razor SDK.

È anche possibile creare un proprio SDK che può essere distribuito tramite NuGet.

## <a name="project-files"></a>File di progetto

I progetti .NET Core sono basati sul formato [MSBuild](/visualstudio/msbuild/msbuild) . I file di progetto, che hanno estensioni come *. csproj* per C# i progetti e F# *. fsproj* per i progetti, sono in formato XML. L'elemento radice di un file di progetto MSBuild è l'elemento [Project](/visualstudio/msbuild/project-element-msbuild) . L'elemento `Project` dispone di un attributo `Sdk` facoltativo che specifica quale SDK (e versione) utilizzare. Per usare gli strumenti di .NET Core e compilare il codice, impostare l'attributo `Sdk` su uno degli ID nella tabella [SDK disponibili](#available-sdks) .

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

Per specificare un SDK che deriva da NuGet, includere la versione alla fine del nome o specificare il nome e la versione nel file *Global. JSON* .

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

Un altro modo per specificare l'SDK è con l'elemento dell' [SDK](/visualstudio/msbuild/sdk-element-msbuild) di primo livello:

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

Il riferimento a un SDK in uno di questi modi semplifica notevolmente i file di progetto per .NET Core. Durante la valutazione del progetto, MSBuild aggiunge le importazioni implicite per `Sdk.props` all'inizio del file di progetto e `Sdk.targets` nella parte inferiore.

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> In un computer Windows, i file *SDK. props* e *SDK. targets* si trovano nella cartella *%ProgramFiles%\dotnet\sdk\\[Version] \Sdks\Microsoft.NET.Sdk\Sdk*

### <a name="preprocess-the-project-file"></a>Pre-elaborare il file di progetto

È possibile visualizzare il progetto completamente espanso poiché MSBuild lo rileva dopo che l'SDK e le relative destinazioni sono inclusi usando il comando `dotnet msbuild -preprocess`. L'opzione di [pre-elaborazione](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](../tools/dotnet-msbuild.md) Mostra i file che vengono importati, le relative origini e i relativi contributi alla compilazione senza compilare effettivamente il progetto.

Se il progetto dispone di più framework di destinazione, concentrare i risultati del comando su un solo Framework specificandone il risultato come proprietà di MSBuild. Ad esempio,

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a>La compilazione predefinita include

Le impostazioni predefinite include ed Escludi per gli elementi di compilazione e le risorse incorporate sono definite nell'SDK. A differenza dei progetti non SDK .NET Framework, non è necessario specificare questi elementi nel file di progetto, perché i valori predefiniti coprono i casi d'uso più comuni. In questo modo, i file di progetto più piccoli risultano più facili da comprendere e modificati manualmente, se necessario.

La tabella seguente mostra l'elemento e i [glob](https://en.wikipedia.org/wiki/Glob_(programming)) che vengono inclusi ed esclusi nella .NET Core SDK:

| Elemento           | GLOB Include                              | GLOB Exclude                                                  | GLOB Remove              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs (o altre estensioni del linguaggio) | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc  | N/D                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                      |
| None              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> Per impostazione predefinita, le cartelle `./bin` e `./obj`, rappresentate dalle proprietà `$(BaseOutputPath)` e `$(BaseIntermediateOutputPath)` MSBuild, sono escluse dai glob. Le esclusioni sono rappresentate dalla proprietà `$(DefaultItemExcludes)`.

Se si definiscono in modo esplicito questi elementi nel file di progetto, è probabile che si ottenga l'errore seguente:

**Sono stati inclusi elementi di compilazione duplicati. .NET SDK include gli elementi di compilazione dalla directory del progetto per impostazione predefinita. È possibile rimuovere questi elementi dal file di progetto o impostare la proprietà' EnableDefaultCompileItems ' su' false ' se si desidera includerli in modo esplicito nel file di progetto.**

Per risolvere l'errore, rimuovere gli elementi `Compile` espliciti che corrispondono a quelli impliciti elencati nella tabella precedente oppure impostare la proprietà `EnableDefaultCompileItems` su `false`, che disabilita l'inclusione implicita:

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

Se si vuole specificare, ad esempio, alcuni file da pubblicare con l'app, è comunque possibile usare i meccanismi MSBuild noti per tale elemento, ad esempio l'elemento `Content`.

`EnableDefaultCompileItems` Disabilita solo i glob `Compile` ma non influisce su altri glob, ad esempio il glob `None` implicito che si applica anche agli elementi \*. cs. Per questo motivo, Esplora soluzioni in Visual Studio Visualizza gli elementi \*. cs come parte del progetto, inclusi come elementi di `None`. Per disabilitare il glob implicito `None`, impostare `EnableDefaultNoneItems` su `false`:

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

Per disabilitare *tutti* i glob impliciti, impostare la proprietà `EnableDefaultItems` su `false`:

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a>Personalizzare la compilazione

Esistono diversi modi per [personalizzare una compilazione](/visualstudio/msbuild/customize-your-build). Potrebbe essere necessario eseguire l'override di una proprietà passandola come argomento a un comando [MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) o [DotNet](../tools/index.md) . È anche possibile aggiungere la proprietà al file di progetto o a un file *Directory. Build. props* . Per un elenco di proprietà utili per i progetti .NET Core, vedere [Proprietà MSBuild per progetti .NET Core SDK](msbuild-props.md).

## <a name="see-also"></a>Vedere anche

- [Installare .NET Core](../install/index.md)
- [Come usare gli SDK di progetto MSBuild](/visualstudio/msbuild/how-to-use-project-sdk)
