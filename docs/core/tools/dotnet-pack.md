---
title: Comando dotnet pack
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
ms.date: 04/28/2020
ms.openlocfilehash: 26a8581f55a8dc9e61aa52e62ed94c73eefd3e03
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595754"
---
# <a name="dotnet-pack"></a>dotnet pack

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet pack`: comprime il codice in un pacchetto NuGet.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a>Descrizione

Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet. Il risultato di questo comando è un pacchetto NuGet, ovvero un file con *estensione nupkg* .

Se si desidera generare un pacchetto che contiene i simboli di debug, sono disponibili due opzioni:

- `--include-symbols`-Crea il pacchetto di simboli.
- `--include-source`-Crea il pacchetto di simboli con una `src` cartella all'interno di che contiene i file di origine.

Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto. I riferimenti da progetto a progetto non sono inseriti all'interno del progetto. Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.

Per impostazione predefinita, `dotnet pack` compila prima il progetto. Se si vuole evitare questo comportamento, passare l'opzione `--no-build`. Questa opzione è in genere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration) in cui si sa che il codice è stato compilato in precedenza.

> [!NOTE]
> In alcuni casi, non è possibile eseguire la compilazione implicita. Questo problema può verificarsi `GeneratePackageOnBuild` quando è impostato, per evitare una dipendenza ciclica tra le destinazioni di compilazione e di Pack. La compilazione può anche avere esito negativo se è presente un file bloccato o un altro problema.

È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione. Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild). La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild -p per due diversi scenari.

Per impostazione predefinita, non è possibile creare un pacchetto dei progetti Web. Per eseguire l'override del comportamento predefinito, aggiungere la proprietà seguente al file con estensione *csproj*:

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a>Ripristino implicito

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argomenti

`PROJECT | SOLUTION`

  Progetto o soluzione da comprimere. Si tratta di un percorso di un [file csproj](csproj.md), di un file di soluzione o di una directory. Se non specificato, il comando Cerca nella directory corrente un file di progetto o di soluzione.

## <a name="options"></a>Opzioni

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito per la maggior `Debug`parte dei progetti è, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--include-source`**

  Include i pacchetti NuGet dei simboli di debug oltre ai pacchetti NuGet normali nella directory di output. I file di origine sono inclusi nella `src` cartella all'interno del pacchetto di simboli.

- **`--include-symbols`**

  Include i pacchetti NuGet dei simboli di debug oltre ai pacchetti NuGet normali nella directory di output.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-build`**

  Non compila il progetto prima della compressione. Imposta anche in modo implicito il flag `--no-restore`.

- **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`--nologo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Inserisce i pacchetti compilati nella directory specificata.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Specifica il runtime di destinazione per cui ripristinare i pacchetti. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

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

- Comprimere il progetto e usare un runtime specifico (Windows 10) per l'operazione di ripristino:

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- Comprimere il progetto usando un file con *estensione NuSpec* :

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  Per informazioni sull'utilizzo `NuspecFile`di, `NuspecBasePath`e `NuspecProperties`, vedere le risorse seguenti:
  
  - [Creazione di un pacchetto con un file .nuspec](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [Punti di estensione avanzati per la creazione di pacchetti personalizzati](https://docs.microsoft.com/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [Proprietà globali](https://docs.microsoft.com/visualstudio/msbuild/msbuild-properties?view=vs-2019#global-properties)
