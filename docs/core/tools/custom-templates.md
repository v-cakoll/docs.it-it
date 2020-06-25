---
title: Modelli personalizzati per dotnet new
description: Informazioni sui modelli personalizzati per qualsiasi tipo di file o progetto .NET.
author: adegeo
ms.date: 05/20/2020
ms.openlocfilehash: cabe220917e7ff688a2c2d2df56d9bc7f8afdf56
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324508"
---
# <a name="custom-templates-for-dotnet-new"></a>Modelli personalizzati per dotnet new

[.NET Core SDK](https://dotnet.microsoft.com/download) viene distribuito con molti modelli già installati e pronti per l'uso. Il [ `dotnet new` comando](dotnet-new.md) non è solo la modalità di utilizzo di un modello, ma anche come installare e disinstallare i modelli. A partire da .NET Core 2.0, è possibile creare modelli personalizzati per qualsiasi tipo di progetto, ad esempio un'app, un servizio, uno strumento o una libreria di classi. È possibile anche creare un modello che restituisce uno o più file indipendenti, ad esempio un file di configurazione.

È possibile installare modelli personalizzati da un pacchetto NuGet in qualsiasi feed NuGet, facendo riferimento direttamente a un file NuGet *. nupkg* oppure specificando una file System Directory che contiene il modello. Il motore del modello offre funzionalità che consentono di sostituire i valori, includere ed escludere file ed eseguire operazioni di elaborazione personalizzate quando si usa il modello.

Il motore del modello è open source e il repository del codice online si trova in [dotnet/templating](https://github.com/dotnet/templating/) su GitHub. Più modelli, inclusi i modelli di terze parti, sono disponibili in [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Modelli disponibili per dotnet new) su GitHub. Per altre informazioni sulla creazione e l'uso di modelli personalizzati, vedere [Come creare modelli personalizzati per dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) e la [wiki del repository GitHub dotnet/templating](https://github.com/dotnet/templating/wiki).

> [!NOTE]
> Gli esempi di modelli sono disponibili nel repository GitHub [DotNet/DotNet-template-Samples](https://github.com/dotnet/dotnet-template-samples) . Tuttavia, sebbene questi esempi siano una risorsa efficace per apprendere il funzionamento dei modelli, il repository viene archiviato e non viene più mantenuto. Gli esempi potrebbero non essere aggiornati e non funzionano più.

Per seguire una procedura dettagliata e creare un modello, vedere l'esercitazione [Creare un modello personalizzato per dotnet new](../tutorials/cli-templates-create-item-template.md).

### <a name="net-default-templates"></a>Modelli predefiniti .NET

Quando si installa [.NET Core SDK](https://dotnet.microsoft.com/download), si riceve circa una decina di modelli predefiniti per la creazione di progetti e file, tra cui app console, librerie di classi, progetti unit test, app ASP.NET Core (inclusi i progetti [Angular](https://angular.io/) e [React](https://facebook.github.io/react/)) e file di configurazione. Per elencare i modelli predefiniti, eseguire il comando `dotnet new` con l'opzione `-l|--list`:

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a>Configurazione

Un modello è costituito dai componenti seguenti:

- File e cartelle di origine.
- Un file di configurazione (*template.json*).

### <a name="source-files-and-folders"></a>File e cartelle di origine

I file e le cartelle di origine includono tutti i file e le cartelle che devono essere usati dal motore del modello quando viene eseguito il comando `dotnet new <TEMPLATE>`. Il motore del modello è progettato per usare *progetti eseguibili* come codice sorgente per creare i progetti. Ciò comporta diversi vantaggi:

- Il motore del modello non richiede di inserire speciali token nel codice sorgente del progetto.
- I file di codice non sono file speciali o modificati in alcun modo per essere usati con il motore del modello. Gli strumenti usati in genere quando si usano progetti funzionano quindi anche con il contenuto del modello.
- Compilare, eseguire ed effettuare il debug dei progetti di modello, proprio come per qualsiasi altro progetto.
- È possibile creare rapidamente un modello da un progetto esistente aggiungendo semplicemente un file di configurazione *./.template.config/template.json* al progetto.

I file e le cartelle archiviati nel modello non sono limitati ai tipi di progetto .NET formali. I file e le cartelle di origine possono essere costituiti da qualsiasi contenuto che si vuole creare quando viene usato il modello, anche se il motore del modello genera un solo file di output.

I file generati dal modello possono essere modificati in base alla logica e alle impostazioni specificate nel file di configurazione *template.json*. L'utente può eseguire l'override di queste impostazioni passando opzioni al comando `dotnet new <TEMPLATE>`. Un esempio comune di logica personalizzata consiste nel fornire un nome per una classe o una variabile nel file di codice che viene distribuito da un modello.

### <a name="templatejson"></a>template.json

Il file *template.json* si trova in una cartella *.template.config* nella directory radice del modello. Il file fornisce informazioni di configurazione al motore del modello. Per la configurazione minima sono necessari i membri visualizzati nella tabella seguente, sufficiente per creare un modello funzionale.

| Membro            | Type          | Description |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | Lo schema JSON per il file *template.json*. Gli editor che supportano gli schemi JSON abilitano le funzionalità di modifica JSON quando viene specificato lo schema. Ad esempio, [Visual Studio Code](https://code.visualstudio.com/) richiede questo membro per abilitare IntelliSense. Usare un valore di `http://json.schemastore.org/template`. |
| `author`          | string        | L'autore del modello. |
| `classifications` | array(string) | Zero o più caratteristiche del modello che un utente può usare per individuare il modello durante la ricerca. Le classificazioni vengono visualizzate anche nella colonna *Tags* quando viene visualizzata in un elenco di modelli generati usando il comando `dotnet new -l|--list`. |
| `identity`        | string        | Un nome univoco per questo modello. |
| `name`            | string        | Il nome per il modello che verrà visualizzato agli utenti. |
| `shortName`       | string        | Un nome breve predefinito per la selezione del modello che si applica agli ambienti in cui il nome del modello viene specificato dall'utente e non selezionato tramite un'interfaccia utente grafica. Ad esempio, il nome breve è utile quando si usano i modelli da un prompt dei comandi con i comandi dell'interfaccia della riga di comando. |

Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template). Per altre informazioni sul file *template.json*, vedere il [wiki sulla creazione di modelli dotnet](https://github.com/dotnet/templating/wiki).

#### <a name="example"></a>Esempio

Qui è ad esempio riportata la cartella di un modello che contiene due file di contenuto: *console.cs* e *readme.txt*. Si noti che è presente la cartella obbligatoria denominata *.template.config* che contiene il file *template.json*.

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

Il file *template.json* ha un aspetto simile al seguente:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

La cartella *mytemplate* è un pacchetto di modelli installabile. Dopo aver installato il pacchetto, è possibile usare `shortName` con il comando `dotnet new`. `dotnet new adatumconsole`, ad esempio, genera come output i file `console.cs` e `readme.txt` nella cartella corrente.

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Compressione di un modello in un pacchetto NuGet (file nupkg)

Un modello personalizzato viene compresso in un pacchetto con il comando [dotnet pack](dotnet-pack.md) e un file con estensione *csproj*. In alternativa, è possibile usare [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) con il comando [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) e un file con estensione *nuspec*. Tuttavia, NuGet richiede l'.NET Framework in Windows e [mono](https://www.mono-project.com/) in Linux e MacOS.

Il file con estensione *csproj* è leggermente diverso da un file *csproj* di un progetto di codice tradizionale. Si notino le impostazioni seguenti:

01. È inclusa l'impostazione `<PackageType>` con il valore `Template`.
01. È inclusa l'impostazione `<PackageVersion>` con un [numero di versione NuGet](/nuget/reference/package-versioning) valido.
01. È inclusa l'impostazione `<PackageId>` con un identificatore univoco. Questo identificatore è utile per disinstallare il pacchetto di modelli e viene usato dai feed NuGet per registrare tale pacchetto.
01. Le impostazioni dei metadati generici devono essere definite: `<Title>`, `<Authors>`, `<Description>` e `<PackageTags>`.
01. L'impostazione `<TargetFramework>` deve essere definita, anche se non viene usato il file binario generato dal processo del modello. Nell'esempio seguente è definito il valore `netstandard2.0`.

Per un pacchetto di modelli, nel formato NuGet con estensione *nupkg*, è necessario che tutti i modelli siano archiviati nella cartella *content* all'interno del pacchetto. Vi sono altre impostazioni da aggiungere a un file con estensione *csproj* per assicurarsi che il file *nupkg* generato possa essere installato come pacchetto di modelli:

01. L'impostazione `<IncludeContentInPack>` ha valore `true` in modo da includere qualsiasi file definito come **content** del progetto nel pacchetto NuGet.
01. L'impostazione `<IncludeBuildOutput>` ha valore `false` in modo da escludere tutti i file binari generati dal compilatore in base al pacchetto NuGet.
01. L'impostazione `<ContentTargetFolders>` ha valore `content`. Ciò consente di assicurarsi che i file impostati come **content** vengano archiviati nella cartella *content* del pacchetto NuGet. Questa cartella del pacchetto NuGet viene analizzata dal sistema di modelli dotnet.

Un modo semplice per escludere tutti i file del codice dalla compilazione in base al progetto di modello è quello di usare l'elemento `<Compile Remove="**\*" />` nel file di progetto, all'interno di un elemento `<ItemGroup>`.

Un modo semplice per definire la struttura del pacchetto di modelli è quello di inserire tutti i modelli in singole cartelle e quindi ogni cartella di modello all'interno di una cartella *templates* che si trova nella stessa directory del file con estensione *csproj*. In questo modo, è possibile usare un singolo elemento di progetto per includere tutti i file e le cartelle in *templates* come **content**. All'interno di un elemento `<ItemGroup>` creare un elemento `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`.

Di seguito è riportato un esempio di file con estensione *csproj* in cui sono rispettate tutte le linee guida indicate sopra. Comprime la sottocartella *templates* nella cartella *content* del pacchetto ed esclude qualsiasi file di codice compilato.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

L'esempio seguente illustra la struttura di file e cartelle necessaria per usare un file con estensione *csproj* per creare un pacchetto di modelli. Il file *MyDotnetTemplates.csproj* e la cartella *templates* si trovano entrambi nella radice di una directory denominata *project_folder*. La cartella *templates* contiene due modelli, *mytemplate1* e *mytemplate2*. Ogni modello ha file di contenuto e una cartella *.template.config* con un file di configurazione *template.json*.

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a>Installazione di un modello

Per installare un pacchetto, usare il comando [dotnet new -i|--install](dotnet-new.md).

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Per installare un modello da un pacchetto NuGet archiviato in nuget.org

Usare l'identificatore del pacchetto NuGet per installare un pacchetto di modelli.

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>Per installare un modello da un file nupkg locale

Specificare il percorso di un file di pacchetto NuGet con estensione *nupkg*.

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>Per installare un modello da una directory del file system

I modelli possono essere installati da una cartella di modello, come *mytemplate1* nell'esempio precedente. Specificare il percorso della cartella *.template.config*. Il percorso della directory del modello non deve essere assoluto. Un percorso assoluto è tuttavia necessario per disinstallare un modello installato da una cartella.

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a>Ottenere un elenco dei modelli installati

Il comando uninstall, senza altri parametri, elenca tutti i modelli installati.

```dotnetcli
dotnet new -u
```

Il comando restituisce un output simile al seguente:

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

Il primo livello degli elementi dopo `Currently installed items:` è costituito dagli identificatori usati nella disinstallazione di un modello. Nell'esempio precedente sono elencati `Microsoft.DotNet.Common.ItemTemplates` e `Microsoft.DotNet.Common.ProjectTemplates.3.0`. Se il modello è stato installato usando un percorso del file system, questo identificatore corrisponde al percorso della cartella *.template.config*.

## <a name="uninstalling-a-template"></a>Disinstallazione di un modello

Per disinstallare un pacchetto, usare il comando [dotnet new -u|--uninstall](dotnet-new.md).

Se il pacchetto è stato installato tramite un feed NuGet o direttamente da un file con estensione *nupkg*, specificare l'identificatore.

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

Se il pacchetto è stato installato specificando un percorso per la cartella *.template.config*, usare tale percorso **assoluto** per disinstallare il pacchetto. È possibile visualizzare il percorso assoluto del modello nell'output generato dal comando `dotnet new -u`. Per altre informazioni, vedere la sezione precedente [Ottenere un elenco dei modelli installati](#get-a-list-of-installed-templates).

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Creare un progetto usando un modello personalizzato

Dopo l'installazione di un modello, usare il modello eseguendo il comando `dotnet new <TEMPLATE>` come si farebbe con qualsiasi altro modello pre-installato. È possibile anche specificare [options](dotnet-new.md#options) per il comando `dotnet new`, includendo le opzioni specifiche del modello configurate nelle impostazioni del modello. Specificare il nome breve del modello direttamente nel comando:

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>Vedi anche

- [Creare un modello personalizzato per dotnet new (esercitazione)](../tutorials/cli-templates-create-item-template.md)
- [Wiki del repository GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)
- [Repository GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [Come creare modelli personalizzati per dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- Lo schema [*template.JSON* nell'archivio di schemi JSON](http://json.schemastore.org/template)
