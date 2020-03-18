---
title: Panoramica dell'SDK del progetto .NET Core
description: Informazioni sugli SDK del progetto .NET Core.Learn about the .NET Core project SDKs.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: 32e14993326c6f17d6470249fe5a545180348631
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399175"
---
# <a name="net-core-project-sdks"></a>SDK del progetto .NET Core

I progetti .NET Core sono associati a un Software Development Kit (SDK). Ogni SDK del progetto è un set di [destinazioni](/visualstudio/msbuild/msbuild-targets) MSBuild e [attività](/visualstudio/msbuild/msbuild-tasks) associate responsabili della compilazione, dell'imballaggio e della pubblicazione del codice.

## <a name="available-sdks"></a>SDK disponibili

Per .NET Core sono disponibili i seguenti SDK:

| ID | Descrizione | Repo|
| - | - | - |
| `Microsoft.NET.Sdk` | The .NET Core SDK | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | Web [SDK](/aspnet/core/razor-pages/web-sdk) di .NET Core | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | SDK di .NET Core [Razor](/aspnet/core/razor-pages/sdk) |
| `Microsoft.NET.Sdk.Worker` | L'SDK del servizio di lavoro .NET Core |
| `Microsoft.NET.Sdk.WindowsDesktop` | WinForms e WPF SDK di .NET Core |

.NET Core SDK è l'SDK di base per .NET Core. Gli altri SDK fanno riferimento a .NET Core SDK e i progetti associati agli altri SDK dispongono di tutte le proprietà di .NET Core SDK. Il Web SDK, ad esempio, dipende sia da .NET Core SDK che da Razor SDK.

È anche possibile creare il proprio SDK che può essere distribuito tramite NuGet.You can also author your own SDK that can be distributed via NuGet.

## <a name="project-files"></a>File di progetto

I progetti .NET Core sono basati sul formato [MSBuild.](/visualstudio/msbuild/msbuild) I file di progetto, che dispongono di estensioni come *.csproj* per i progetti in C, e *.fsproj* per i progetti F , sono in formato XML. L'elemento radice di un file di progetto MSBuild è l'elemento [Project.](/visualstudio/msbuild/project-element-msbuild) L'elemento `Project` dispone `Sdk` di un attributo facoltativo che specifica l'SDK (e la versione) da utilizzare. Per usare gli strumenti .NET Core e `Sdk` compilare il codice, impostare l'attributo su uno degli ID nella tabella [SDK disponibili.](#available-sdks)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

Per specificare un SDK proveniente da NuGet, includere la versione alla fine del nome oppure specificare il nome e la versione nel file *global.json.*

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

Un altro modo per specificare l'SDK è con l'elemento [Sdk](/visualstudio/msbuild/sdk-element-msbuild) di primo livello:

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

Il riferimento a un SDK in uno di questi modi semplifica notevolmente i file di progetto per .NET Core.Referening an SDK in one of these ways greatly simplifies project files for .NET Core. Durante la valutazione del progetto, MSBuild `Sdk.props` aggiunge importazioni implicite `Sdk.targets` per all'inizio del file di progetto e nella parte inferiore.

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
> In un computer Windows, i file *Sdk.props* e *Sdk.targets* sono disponibili nella cartella *%ProgramFiles%\\*

### <a name="preprocess-the-project-file"></a>Pre-elaborare il file di progetto

È possibile visualizzare il progetto completamente espanso come MSBuild vede dopo `dotnet msbuild -preprocess` l'SDK e le relative destinazioni sono inclusi utilizzando il comando. L'opzione [`dotnet msbuild`](../tools/dotnet-msbuild.md) di [pre-elaborazione](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando mostra quali file vengono importati, le relative origini e i relativi contributi alla compilazione senza compilare effettivamente il progetto.

Se il progetto dispone di più framework di destinazione, spostare i risultati del comando su un solo framework specificandolo come proprietà MSBuild. Ad esempio:

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a>La compilazione predefinita include

L'impostazione predefinita include ed esclude per gli elementi di compilazione e le risorse incorporate sono definite nell'SDK. A differenza dei progetti .NET Framework non SDK, non è necessario specificare questi elementi nel file di progetto, perché i valori predefiniti riguardano i casi d'uso più comuni. Questo porta a file di progetto più piccoli che sono più facili da capire e modificare a mano, se necessario.

Nella tabella seguente vengono illustrati l'elemento e i [glob](https://en.wikipedia.org/wiki/Glob_(programming)) inclusi ed esclusi in .NET Core SDK:

| Elemento           | GLOB Include                              | GLOB Exclude                                                  | GLOB Remove              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compilazione           | \*\*/\*.cs (o altre estensioni del linguaggio) | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc  | N/D                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                      |
| nessuno              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> Le `./bin` `./obj` cartelle e, rappresentate `$(BaseOutputPath)` `$(BaseIntermediateOutputPath)` dalle proprietà e MSBuild, sono escluse dai glob per impostazione predefinita. Gli esclusi sono `$(DefaultItemExcludes)`rappresentati dalla proprietà .

Se si definiscono in modo esplicito questi elementi nel file di progetto, è probabile che venga visualizzato il seguente errore:

**Sono stati inclusi elementi Compile duplicati. .NET SDK include gli elementi Compile dalla directory del progetto per impostazione predefinita. È possibile rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se si desidera includerli in modo esplicito nel file di progetto.**

Per risolvere l'errore, `Compile` rimuovere gli elementi espliciti che corrispondono a `EnableDefaultCompileItems` quelli `false`impliciti elencati nella tabella precedente oppure impostare la proprietà su , che disabilita l'inclusione implicita:

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

Se si desidera specificare, ad esempio, alcuni file da pubblicare con l'app, è comunque `Content` possibile usare i meccanismi MSBuild noti per tale file, ad esempio l'elemento.

`EnableDefaultCompileItems`disabilita solo `Compile` globs ma non influisce su altri glob, come il glob implicito `None` che si applica anche agli \*elementi .cs. Per questo, Esplora soluzioni \*in Visual Studio mostra gli elementi `None` con estensione cs come parte del progetto, inclusi come elementi. Per disabilitare `None` il glob `false`implicito, impostare su `EnableDefaultNoneItems` :

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

Per disabilitare *tutti i* glob impliciti, impostare la `EnableDefaultItems` proprietà su `false`:

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a>Personalizzare la build

Esistono vari modi per [personalizzare una compilazione](/visualstudio/msbuild/customize-your-build). È possibile eseguire l'override di una proprietà passandola come argomento a un comando [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) o [dotnet.](../tools/index.md) È inoltre possibile aggiungere la proprietà al file di progetto o a un file *Directory.Build.props.* Per un elenco di proprietà utili per i progetti .NET Core, vedere Proprietà MSBuild per i [progetti .NET Core SDK](msbuild-props.md).

### <a name="custom-targets"></a>Destinazioni personalizzate

I progetti .NET Core possono creare pacchetti di destinazioni e proprietà MSBuild personalizzate per l'utilizzo da parte di progetti che utilizzano il pacchetto. Utilizzare questo tipo di estendibilità quando si desidera:

- Estendere il processo di compilazione.
- Accedere agli elementi del processo di compilazione, ad esempio i file generati.
- Esaminare la configurazione in cui viene richiamata la compilazione.

È possibile aggiungere proprietà o destinazioni `<package_id>.targets` di `<package_id>.props` compilazione `Contoso.Utility.UsefulStuff.targets`personalizzate inserendo i file nel formato o (ad esempio) nella cartella di *compilazione* del progetto.

Il codice XML seguente è un frammento di [`dotnet pack`](../tools/dotnet-pack.md) codice da un file con estensione *csproj* che indica al comando cosa creare un pacchetto. L'elemento `<ItemGroup Label="dotnet pack instructions">` inserisce i file di destinazione nella cartella di *compilazione* all'interno del pacchetto. L'elemento `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` inserisce gli assembly e i file *json* nella cartella di *compilazione.*

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...
  
</Project>
```

Per usare una destinazione personalizzata `PackageReference` nel progetto, aggiungere un elemento che punta al pacchetto e alla relativa versione. A differenza degli strumenti, il pacchetto di destinazioni personalizzate è incluso nella chiusura delle dipendenze del progetto consumer.

È possibile configurare la modalità di utilizzo della destinazione personalizzata. Poiché si tratta di una destinazione MSBuild, può dipendere da una determinata destinazione, eseguirla dopo un'altra destinazione o essere richiamata manualmente tramite il `dotnet msbuild -t:<target-name>` comando. Tuttavia, per offrire un'esperienza utente migliore, è possibile combinare strumenti per progetto e destinazioni personalizzate. In questo scenario, lo strumento per progetto accetta i parametri necessari [`dotnet msbuild`](../tools/dotnet-msbuild.md) e lo converte nella chiamata richiesta che esegue la destinazione. È possibile visualizzare un esempio di questo tipo di sinergia nel repository degli [esempi di MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) nel progetto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="see-also"></a>Vedere anche

- [Installare .NET Core](../install/index.md)
- [Come utilizzare gli SDK del progetto MSBuildHow to use MSBuild project SDK](/visualstudio/msbuild/how-to-use-project-sdk)
- [Creare il pacchetto di destinazioni e oggetti di scena MSBuild personalizzati con NuGetPackage custom MSBuild targets and props with NuGet](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
