---
title: Comando dotnet build
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 04/24/2019
ms.openlocfilehash: 6e577defb9f5c7795ee40efa18da30daee1b52c0
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168066"
---
# <a name="dotnet-build"></a>dotnet build

**Questo articolo si applica a: ✓** .NET Core 1.x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nome

`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

```console
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--nologo] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a>DESCRIZIONE

Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari. I file binari includono il codice del progetto in Intermediate Language (IL) con estensione *dll* e i file di simboli usati per il debug con estensione *pdb*. Viene generato un file JSON di dipendenze ( *.deps.json*) con l'elenco delle dipendenze dell'applicazione. Viene generato un file *.runtimeconfig.json* che specifica il runtime condiviso e la relativa versione per l'applicazione.

Se il progetto ha dipendenze di terze parti, ad esempio librerie di NuGet, queste dipendenze vengono risolte dalla cache NuGet e non sono disponibili con l'output compilato del progetto. Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione. Questo comportamento si differenzia da quello di .NET Framework in cui la compilazione di un progetto eseguibile (un'applicazione) genera un output che è possibile eseguire in qualsiasi computer in cui è installato .NET Framework. Per ottenere un'esperienza simile in .NET Core, usare il comando [dotnet publish](dotnet-publish.md). Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione. Il file viene creato quando [`dotnet restore`](dotnet-restore.md) viene eseguito. Senza il file di asset sul posto, gli strumenti non possono risolvere gli assembly di riferimento, generando così errori. Con .NET Core 1.x SDK, era necessario eseguire in modo esplicito `dotnet restore` prima di eseguire `dotnet build`. A partire da .NET Core 2.0 SDK, `dotnet restore` viene eseguito in modo implicito quando viene eseguito `dotnet build`. Se si desidera disabilitare ripristino implicito quando si esegue il comando di compilazione, è possibile passare l’opzione `--no-restore`.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno. L'esempio seguente descrive un progetto che produce codice eseguibile:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Per generare una libreria, omettere la proprietà `<OutputType>`. La differenza principale nell'output di compilazione è che la DLL di linguaggio intermedio per una libreria non contiene punti di ingresso e non può essere eseguita.

### <a name="msbuild"></a>MSBuild

Poiché `dotnet build` usa MSBuild per compilare il progetto, sono supportate le compilazioni parallele e incrementali. Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).

In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `-p` per l'impostazione delle proprietà o `-l` per la definizione di un logger. Per altre informazioni su queste opzioni, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). In alternativa è anche possibile usare il comando [dotnet msbuild](dotnet-msbuild.md).

L'esecuzione di `dotnet build` equivale a `dotnet msbuild -restore -target:Build`.

## <a name="arguments"></a>Argomenti

`PROJECT | SOLUTION`

File di progetto o di soluzione da compilare. Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.

## <a name="options"></a>Opzioni

* **`-c|--configuration {Debug|Release}`**

  Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

* **`-f|--framework <FRAMEWORK>`**

  Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico. Il framework deve essere definito nel [file di progetto](csproj.md).

* **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*. Disponibile a partire da .NET Core 2.0 SDK.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

* **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.

* **`--no-incremental`**

  Contrassegna la compilazione come non sicura per la compilazione incrementale. Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.

* **`--no-logo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

* **`--no-restore`**

  Non esegue un ripristino implicito durante la compilazione. Disponibile a partire da .NET Core 2.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory in cui inserire i file binari compilati. È necessario definire anche `--framework` quando si specifica questa opzione. Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Specifica il runtime di destinazione. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

* **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio di MSBuild. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`.

* **`--version-suffix <VERSION_SUFFIX>`**

  Imposta il valore della proprietà `$(VersionSuffix)` da usare durante la compilazione del progetto. Funziona solo se la proprietà `$(Version)` non è impostata. La proprietà `$(Version)` viene quindi impostata su `$(VersionPrefix)` combinata con `$(VersionSuffix)`, separati da un trattino.

## <a name="examples"></a>Esempi

* Compilare un progetto e le relative dipendenze:

  ```console
  dotnet build
  ```

* Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

  ```console
  dotnet build --configuration Release
  ```

* Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 18.04):

  ```console
  dotnet build --runtime ubuntu.18.04-x64
  ```

* Compilare il progetto e usare l'origine del pacchetto NuGet specificato durante l'operazione di ripristino (.NET Core 2.0 SDK e versioni successive):

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* Compilare il progetto e impostare la versione 1.2.3.4 come parametro di compilazione usando l'[opzione MSBuild](#msbuild) `-p`:

  ```console
  dotnet build -p:Version=1.2.3.4
  ```
