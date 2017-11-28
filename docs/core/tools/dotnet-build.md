---
title: Comando dotnet build - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: b2b625729b5db22bc7b69194f20963857004e3e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-build"></a>dotnet-build

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nome

`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a>Descrizione

Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari. I file binari includono il codice del progetto in Intermediate Language (IL) con estensione *dll* e i file di simboli usati per il debug con estensione *pdb*. Viene generato un file JSON di dipendenze (*\*.deps.json*) con l'elenco delle dipendenze dell'applicazione. Viene generato un file *\*.runtimeconfig.json* che specifica il runtime condiviso e la relativa versione per l'applicazione.

Se il progetto ha dipendenze di terze parti, ad esempio librerie di NuGet, queste dipendenze vengono risolte dalla cache NuGet e non sono disponibili con l'output compilato del progetto. Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione. Questo comportamento si differenzia da quello di .NET Framework in cui la compilazione di un progetto eseguibile (un'applicazione) genera un output che è possibile eseguire in qualsiasi computer in cui è installato .NET Framework. Per ottenere un'esperienza simile in .NET Core, usare il comando [dotnet publish](dotnet-publish.md). Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione. Il file viene creato quando [`dotnet restore`](dotnet-restore.md) viene eseguito. Senza il file di asset sul posto, gli strumenti non sono in grado di risolvere gli assembly di riferimento, generando così errori. Con .NET Core è 1. x SDK, è necessario eseguire esplicitamente il `dotnet restore` prima di eseguire `dotnet build`. A partire da .NET Core 2.0 SDK `dotnet restore` viene eseguito implicitamente quando si esegue `dotnet build`. Se si desidera disabilitare ripristino implicito quando si esegue il comando di compilazione, è possibile passare l’opzione `--no-restore`.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

`dotnet build` usa MSBuild per compilare il progetto e quindi supporta le compilazioni parallele e incrementali. Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).

In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `/p` per l'impostazione delle proprietà o `/l` per la definizione di un logger. Altre informazioni su queste opzioni sono disponibili in [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). 

La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno. L'esempio seguente descrive un progetto che produce codice eseguibile:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Per generare una libreria, omettere la proprietà `<OutputType>`. La differenza principale nell'output di compilazione è che la DLL di linguaggio intermedio per una libreria non contiene punti di ingresso e non può essere eseguita. 

## <a name="arguments"></a>Argomenti

`PROJECT`

File di progetto da compilare. Se non viene specificato un file di progetto, MSBuild cerca nella directory di lavoro corrente un file con estensione che termina con *proj* e usa tale file.

## <a name="options"></a>Opzioni

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico. Il framework deve essere definito nel [file di progetto](csproj.md).

`--force`

 Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. Ciò equivale a eliminare il file *project.assets.json*.

`-h|--help`

Stampa una breve guida per il comando.

`--no-dependencies`

Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato per la compilazione.

`--no-incremental`

Contrassegna la compilazione come non sicura per la compilazione incrementale. Disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.

`--no-restore`

Non esegue un ripristino implicito durante la compilazione.

`-o|--output <OUTPUT_DIRECTORY>`

Directory in cui inserire i file binari compilati. È necessario definire anche `--framework` quando si specifica questa opzione.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Specifica il runtime di destinazione. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definisce il suffisso di versione per un asterisco (`*`) nel campo del file di progetto relativo alla versione. Il formato rispetta le linee guida della versione NuGet.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico. Il framework deve essere definito nel [file di progetto](csproj.md).

`-h|--help`

Stampa una breve guida per il comando.

`--no-dependencies`

Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato per la compilazione.

`--no-incremental`

Contrassegna la compilazione come non sicura per la compilazione incrementale. Disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.

`-o|--output <OUTPUT_DIRECTORY>`

Directory in cui inserire i file binari compilati. È necessario definire anche `--framework` quando si specifica questa opzione.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Specifica il runtime di destinazione. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definisce il suffisso di versione per un asterisco (`*`) nel campo del file di progetto relativo alla versione. Il formato rispetta le linee guida della versione NuGet.

---

## <a name="examples"></a>Esempi

Compilare un progetto e le relative dipendenze:

`dotnet build`

Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

`dotnet build --configuration Release`

Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`