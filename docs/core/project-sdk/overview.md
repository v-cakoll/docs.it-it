---
title: Panoramica dell'SDK del progetto .NET Core
titleSuffix: ''
description: Informazioni sugli SDK per progetti .NET Core.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: 9db62ab7774e3dd71412fa346d78ae0c62a2f81f
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803041"
---
# <a name="net-core-project-sdks"></a>SDK per progetti .NET Core

I progetti .NET Core sono associati a un Software Development Kit (SDK). Ogni *SDK di progetto* è un set di [destinazioni](/visualstudio/msbuild/msbuild-targets) MSBuild e [attività](/visualstudio/msbuild/msbuild-tasks) associate responsabili della compilazione, della compressione e della pubblicazione di codice. Un progetto che fa riferimento a un SDK di progetto viene talvolta definito *progetto di tipo SDK*.

## <a name="available-sdks"></a>SDK disponibili

Per .NET Core sono disponibili gli SDK seguenti:

| ID | Descrizione | Repository|
| - | - | - |
| `Microsoft.NET.Sdk` | .NET Core SDK | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | [SDK Web](/aspnet/core/razor-pages/web-sdk) di .NET Core | <https://github.com/aspnet/websdk> |
| `Microsoft.NET.Sdk.Razor` | .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk) |
| `Microsoft.NET.Sdk.Worker` | SDK del servizio Worker di .NET Core |
| `Microsoft.NET.Sdk.WindowsDesktop` | .NET Core WinForms e WPF SDK |

Il .NET Core SDK è l'SDK di base per .NET Core. Gli altri SDK fanno riferimento al .NET Core SDK e i progetti associati agli altri SDK hanno tutte le proprietà di .NET Core SDK disponibili. Il Web SDK, ad esempio, dipende dal .NET Core SDK e Razor SDK.

È anche possibile creare un proprio SDK che può essere distribuito tramite NuGet.

## <a name="project-files"></a>File di progetto

I progetti .NET Core sono basati sul formato [MSBuild](/visualstudio/msbuild/msbuild) . I file di progetto, che hanno estensioni come *. csproj* per i progetti C# e *. fsproj* per i progetti F #, sono in formato XML. L'elemento radice di un file di progetto MSBuild è l'elemento [Project](/visualstudio/msbuild/project-element-msbuild) . L' `Project` elemento dispone di un `Sdk` attributo facoltativo che specifica quale SDK (e versione) utilizzare. Per usare gli strumenti di .NET Core e compilare il codice, impostare l' `Sdk` attributo su uno degli ID nella tabella [SDK disponibili](#available-sdks) .

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

Per specificare un SDK che deriva da NuGet, includere la versione alla fine del nome o specificare il nome e la versione nella *global.jssu* file.

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
> In un computer Windows, i file *SDK. props* e *SDK. targets* si trovano nella cartella *%ProgramFiles%\dotnet\sdk \\ [Version] \Sdks\Microsoft.NET.Sdk\Sdk*

### <a name="preprocess-the-project-file"></a>Pre-elaborare il file di progetto

È possibile visualizzare il progetto completamente espanso poiché MSBuild lo rileva dopo che l'SDK e le relative destinazioni sono inclusi tramite il `dotnet msbuild -preprocess` comando. L'opzione di [pre-elaborazione](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del [`dotnet msbuild`](../tools/dotnet-msbuild.md) comando Mostra i file che vengono importati, le relative origini e i relativi contributi alla compilazione senza compilare effettivamente il progetto.

Se il progetto dispone di più framework di destinazione, concentrare i risultati del comando su un solo Framework specificandone il risultato come proprietà di MSBuild. Ad esempio:

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a>La compilazione predefinita include

L'impostazione predefinita include ed esclude gli elementi di compilazione, le risorse incorporate e `None` gli elementi sono definiti nell'SDK. A differenza dei progetti non SDK .NET Framework, non è necessario specificare questi elementi nel file di progetto, perché i valori predefiniti coprono i casi d'uso più comuni. In questo modo, il file di progetto risulta più piccolo e più semplice da comprendere e modificare manualmente, se necessario.

La tabella seguente Mostra gli elementi e i [glob](https://en.wikipedia.org/wiki/Glob_(programming)) che vengono inclusi ed esclusi nella .NET Core SDK:

| Elemento           | GLOB Include                              | GLOB Exclude                                                  | GLOB Remove              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compilazione           | \*\*/\*.cs (o altre estensioni del linguaggio) | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc  | N/D                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                      |
| nessuno              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> `./bin` `./obj` Per impostazione predefinita, le cartelle e, che sono rappresentate dalle `$(BaseOutputPath)` `$(BaseIntermediateOutputPath)` proprietà e MSBuild, sono escluse dai glob. Le esclusioni sono rappresentate dalla proprietà `$(DefaultItemExcludes)` .

#### <a name="build-errors"></a>Errori di compilazione

Se si definisce in modo esplicito uno di questi elementi nel file di progetto, è probabile che si ottenga un errore di compilazione "NETSDK1022" simile al seguente:

  > Sono stati inclusi elementi ' Compile ' duplicati. .NET SDK include gli elementi di compilazione dalla directory del progetto per impostazione predefinita. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se li si vuole includere esplicitamente nel file di progetto)

  > Sono stati inclusi elementi ' EmbeddedResource ' duplicati. Per impostazione predefinita, .NET SDK include gli elementi "EmbeddedResource" della directory del progetto. È possibile rimuovere questi elementi dal file di progetto o impostare la proprietà' EnableDefaultEmbeddedResourceItems ' su' false ' se si desidera includerli in modo esplicito nel file di progetto.

Per risolvere gli errori, eseguire una delle operazioni seguenti:

- Rimuovere gli `Compile` elementi, `EmbeddedResource` o espliciti `None` che corrispondono a quelli impliciti elencati nella tabella precedente.

- Impostare la `EnableDefaultItems` proprietà su `false` per disabilitare tutte le inclusioni di file implicite:

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  Se si vuole specificare i file da pubblicare con l'app, è comunque possibile usare i meccanismi di MSBuild noti, ad esempio l' `Content` elemento.

- Disabilitare selettivamente solo `Compile` `EmbeddedResource` i glob, o impostando `None` la `EnableDefaultCompileItems` proprietà, `EnableDefaultEmbeddedResourceItems` o `EnableDefaultNoneItems` su `false` :

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  Se si disabilitano solo i `Compile` glob, Esplora soluzioni in Visual Studio Visualizza ancora \* gli elementi. cs come parte del progetto, inclusi come `None` elementi. Per disabilitare il glob implicito `None` , `EnableDefaultNoneItems` impostare `false` anche su.

## <a name="customize-the-build"></a>Personalizzare la compilazione

Esistono diversi modi per [personalizzare una compilazione](/visualstudio/msbuild/customize-your-build). Potrebbe essere necessario eseguire l'override di una proprietà passandola come argomento a un comando [MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) o [DotNet](../tools/index.md) . È anche possibile aggiungere la proprietà al file di progetto o a un file *Directory. Build. props* . Per un elenco di proprietà utili per i progetti .NET Core, vedere informazioni di [riferimento su MSBuild per progetti .NET Core SDK](msbuild-props.md).

### <a name="custom-targets"></a>Destinazioni personalizzate

I progetti .NET Core possono comprimere le proprietà e le destinazioni di MSBuild personalizzate per l'uso da parte di progetti che utilizzano il pacchetto. Utilizzare questo tipo di estendibilità quando si desidera:

- Estendere il processo di compilazione.
- Accedere agli elementi del processo di compilazione, ad esempio i file generati.
- Esaminare la configurazione in cui viene richiamata la compilazione.

Per aggiungere destinazioni o proprietà di compilazione personalizzate, inserire i file nel formato `<package_id>.targets` o `<package_id>.props` (ad esempio, `Contoso.Utility.UsefulStuff.targets` ) nella cartella di *compilazione* del progetto.

Il codice XML seguente è un frammento di codice di un file con estensione *csproj* che indica al [`dotnet pack`](../tools/dotnet-pack.md) comando cosa eseguire il pacchetto. L' `<ItemGroup Label="dotnet pack instructions">` elemento inserisce i file di destinazione nella cartella di *compilazione* all'interno del pacchetto. L' `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` elemento inserisce gli assembly e i file *JSON* nella cartella di *compilazione* .

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

Per utilizzare una destinazione personalizzata nel progetto, aggiungere un `PackageReference` elemento che punti al pacchetto e alla relativa versione. Diversamente dagli strumenti, il pacchetto di destinazioni personalizzato è incluso nella chiusura delle dipendenze del progetto che lo utilizza.

È possibile configurare la modalità di utilizzo della destinazione personalizzata. Poiché si tratta di una destinazione MSBuild, può dipendere da una destinazione specificata, essere eseguita dopo un'altra destinazione oppure essere richiamata manualmente tramite il `dotnet msbuild -t:<target-name>` comando. Tuttavia, per offrire un'esperienza utente migliore, è possibile combinare gli strumenti per progetto e le destinazioni personalizzate. In questo scenario, lo strumento per progetto accetta qualsiasi parametro necessario e lo traduce nella [`dotnet msbuild`](../tools/dotnet-msbuild.md) chiamata necessaria che esegue la destinazione. È possibile visualizzare un esempio di questo tipo di sinergia nel repository degli [esempi di MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) nel progetto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="see-also"></a>Vedere anche

- [Installare .NET Core](../install/index.yml)
- [Come usare gli SDK di progetto MSBuild](/visualstudio/msbuild/how-to-use-project-sdk)
- [Creare pacchetti di destinazioni e oggetti personalizzati MSBuild con NuGet](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
