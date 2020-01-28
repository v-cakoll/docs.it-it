---
title: Comando dotnet pack
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
ms.date: 08/08/2019
ms.openlocfilehash: 057d1029e5c933912c43c178b6db8a8498f2ed57
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734114"
---
# <a name="dotnet-pack"></a>dotnet pack

**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet pack`: comprime il codice in un pacchetto NuGet.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo] [-o|--output] [--runtime] [-s|--serviceable]
    [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet. Il risultato di questo comando è un pacchetto NuGet, ovvero un file con *estensione nupkg* .

Se si desidera generare un pacchetto che contiene i simboli di debug, sono disponibili due opzioni:

- `--include-symbols`: crea il pacchetto di simboli.
- `--include-source`: crea il pacchetto di simboli con una cartella `src` all'interno di che contiene i file di origine.

Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto. I riferimenti da progetto a progetto non sono inseriti all'interno del progetto. Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.

Per impostazione predefinita, `dotnet pack` compila prima il progetto. Se si vuole evitare questo comportamento, passare l'opzione `--no-build`. Questa opzione è in genere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration) in cui si sa che il codice è stato compilato in precedenza.

È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione. Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild). La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild -p per due diversi scenari.

Per impostazione predefinita, non è possibile creare un pacchetto dei progetti Web. Per eseguire l'override del comportamento predefinito, aggiungere la proprietà seguente al file con estensione *csproj*:

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argomenti

`PROJECT | SOLUTION`

  Progetto o soluzione da comprimere. Si tratta di un percorso di un [file csproj](csproj.md), di un file di soluzione o di una directory. Se non specificato, il comando Cerca nella directory corrente un file di progetto o di soluzione.

## <a name="options"></a>Options

- **`-c|--configuration {Debug|Release}`**

  Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*. Opzione disponibile a partire da .NET Core 2.0 SDK.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--include-source`**

  Include i pacchetti NuGet dei simboli di debug oltre ai pacchetti NuGet normali nella directory di output. I file di origine sono inclusi nella cartella `src` all'interno del pacchetto di simboli.

- **`--include-symbols`**

  Include i pacchetti NuGet dei simboli di debug oltre ai pacchetti NuGet normali nella directory di output.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-build`**

  Non compila il progetto prima della compressione. Imposta anche in modo implicito il flag `--no-restore`.

- **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice. Opzione disponibile a partire da .NET Core 2.0 SDK.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando. Opzione disponibile a partire da .NET Core 2.0 SDK.

- **`--nologo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Inserisce i pacchetti compilati nella directory specificata.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Specifica il runtime di destinazione per cui ripristinare i pacchetti. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Opzione disponibile a partire da .NET Core 2.0 SDK.

- **`-s|--serviceable`**

  Imposta il flag utilizzabile dai servizi nel pacchetto. Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).

- **`--version-suffix <VERSION_SUFFIX>`**

  Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

## <a name="examples"></a>Esempi

- Comprimere il progetto nella directory corrente:

  ```dotnetcli
  dotnet pack
  ```

- Comprimere il progetto `app1`:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- Comprimere il progetto per un [framework di destinazione](../../standard/frameworks.md) specifico:

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- Comprimere il progetto e usare un runtime specifico (Windows 10) per l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- Comprimere il progetto usando un [file con estensione nuspec](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
