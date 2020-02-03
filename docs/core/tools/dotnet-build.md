---
title: Comando dotnet build
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 10/14/2019
ms.openlocfilehash: ec37d82c9e22a59acf7617f80a7491c0bcab89c9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734309"
---
# <a name="dotnet-build"></a>dotnet build

**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force]
    [--interactive] [--no-dependencies] [--no-incremental] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari. I file binari includono il codice del progetto nei file Intermediate Language (IL) con estensione *. dll* .  A seconda del tipo di progetto e delle impostazioni, è possibile includere altri file, ad esempio:

- Eseguibile che può essere usato per eseguire l'applicazione, se il tipo di progetto è un file eseguibile destinato a .NET Core 3,0 o versione successiva.
- File di simboli usati per il debug con estensione *PDB* .
- Un file con *estensione Deps. JSON* , che elenca le dipendenze dell'applicazione o della libreria.
- Un file *. runtimeconfig. JSON* che specifica il runtime condiviso e la relativa versione per un'applicazione.
- Altre librerie da cui dipende il progetto (tramite i riferimenti al progetto o i riferimenti ai pacchetti NuGet).

Per i progetti eseguibili destinati a versioni precedenti a .NET Core 3,0, le dipendenze della libreria da NuGet non vengono in genere copiate nella cartella di output.  Vengono risolti dalla cartella pacchetti globali NuGet in fase di esecuzione. Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione. Per creare una versione dell'applicazione che può essere distribuita, è necessario pubblicarla, ad esempio con il comando [DotNet Publish](dotnet-publish.md) . Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

Per i progetti eseguibili destinati a .NET Core 3,0 e versioni successive, le dipendenze della libreria vengono copiate nella cartella di output. Ciò significa che se non sono presenti altre logiche specifiche per la pubblicazione, ad esempio i progetti web, l'output di compilazione deve essere distribuibile.

Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione. Il file viene creato quando [`dotnet restore`](dotnet-restore.md) viene eseguito. Senza il file di asset sul posto, gli strumenti non possono risolvere gli assembly di riferimento, generando così errori. Con .NET Core 1. x SDK, era necessario eseguire in modo esplicito `dotnet restore` prima di eseguire `dotnet build`. A partire da .NET Core 2.0 SDK, `dotnet restore` viene eseguito in modo implicito quando viene eseguito `dotnet build`. Se si desidera disabilitare ripristino implicito quando si esegue il comando di compilazione, è possibile passare l’opzione `--no-restore`.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno. L'esempio seguente descrive un progetto che produce codice eseguibile:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Per produrre una libreria, omettere la proprietà `<OutputType>` o modificarne il valore in `Library`. La DLL il per una libreria non contiene punti di ingresso e non può essere eseguita.

### <a name="msbuild"></a>MSBuild

Poiché `dotnet build` usa MSBuild per compilare il progetto, sono supportate le compilazioni parallele e incrementali. Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).

In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `-p` per l'impostazione delle proprietà o `-l` per la definizione di un logger. Per altre informazioni su queste opzioni, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). In alternativa è anche possibile usare il comando [dotnet msbuild](dotnet-msbuild.md).

L'esecuzione di `dotnet build` equivale all'esecuzione di `dotnet msbuild -restore`; Tuttavia, il livello di dettaglio predefinito dell'output è diverso.

## <a name="arguments"></a>Argomenti

`PROJECT | SOLUTION`

File di progetto o di soluzione da compilare. Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.

## <a name="options"></a>Opzioni

- **`-c|--configuration {Debug|Release}`**

  Definisce la configurazione di compilazione. Il valore predefinito per la maggior parte dei progetti è `Debug`, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.

- **`-f|--framework <FRAMEWORK>`**

  Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico. Il framework deve essere definito nel [file di progetto](csproj.md).

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*. Disponibile a partire da .NET Core 2.0 SDK.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.

- **`--no-incremental`**

  Contrassegna la compilazione come non sicura per la compilazione incrementale. Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.

- **`--no-restore`**

  Non esegue un ripristino implicito durante la compilazione. Disponibile a partire da .NET Core 2.0 SDK.

- **`--nologo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory in cui inserire i file binari compilati. Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.  Per i progetti con più framework di destinazione (tramite la proprietà `TargetFrameworks`), è anche necessario definire `--framework` quando si specifica questa opzione.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Specifica il runtime di destinazione. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio di MSBuild. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Imposta il valore della proprietà `$(VersionSuffix)` da usare durante la compilazione del progetto. Funziona solo se la proprietà `$(Version)` non è impostata. La proprietà `$(Version)` viene quindi impostata su `$(VersionPrefix)` combinata con `$(VersionSuffix)`, separati da un trattino.

## <a name="examples"></a>Esempi

- Compilare un progetto e le relative dipendenze:

  ```dotnetcli
  dotnet build
  ```

- Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

  ```dotnetcli
  dotnet build --configuration Release
  ```

- Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 18.04):

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- Compilare il progetto e usare l'origine del pacchetto NuGet specificato durante l'operazione di ripristino (.NET Core 2.0 SDK e versioni successive):

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- Compilare il progetto e impostare Version 1.2.3.4 come parametro di compilazione usando l' [opzione `-p` MSBuild](#msbuild):

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
