---
title: Comando dotnet
description: Informazioni sul comando DotNet (il driver generico per la interfaccia della riga di comando di .NET Core) e il relativo utilizzo.
ms.date: 06/04/2018
ms.openlocfilehash: 7674529980623caa2291987bdeba52f50ce2fc2c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920544"
---
# <a name="dotnet-command"></a>Comando dotnet

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet`: uno strumento per la gestione dei file binari e del codice sorgente di .NET.

## <a name="synopsis"></a>Riepilogo

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a>Descrizione

`dotnet` è uno strumento per la gestione dei file binari e del codice sorgente di .NET. Espone i comandi che eseguono attività specifiche, come ad esempio [`dotnet build`](dotnet-build.md) e [`dotnet run`](dotnet-run.md). Ogni comando definisce i propri argomenti. Digitare `--help` dopo ogni comando per accedere a una breve documentazione della Guida.

`dotnet` può essere usato per eseguire le applicazioni specificando una DLL dell'applicazione, come ad esempio `dotnet myapp.dll`. Per informazioni sulle opzioni di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

## <a name="options"></a>Options

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--additional-deps <PATH>`

Percorso di un file *.deps.json* aggiuntivo.

`--additionalprobingpath <PATH>`

Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

`--depsfile`

Percorso di un file *deps.json*.

Un file *Deps. JSON* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti di assembly. Per altre informazioni su questo file, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.

`-d|--diagnostics`

Abilita l'output di diagnostica.

`--fx-version <VERSION>`

Versione del runtime di .NET Core da usare per eseguire l'applicazione.

`-h|--help`

Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`. `dotnet --help` consente di visualizzare un elenco dei comandi disponibili.

`--info`

Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.

`--list-runtimes`

Visualizza i runtime di .NET Core installati.

`--list-sdks`

Visualizza i .NET Core SDK installati.

`--roll-forward-on-no-candidate-fx <N>`

Definisce il comportamento quando il framework condiviso richiesto non è disponibile. `N` può essere:

- `0` - Disabilitare anche il roll forward per la versione secondaria.
- `1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale. Comportamento predefinito.
- `2` - Eseguire il roll forward per le versioni principali e secondarie.

 Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

`--runtimeconfig`

Percorso di un file *runtimeconfig.json*.

Un file *runtimeconfig. JSON* è un file di configurazione contenente le impostazioni della fase di esecuzione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.

`--version`

Stampa la versione di .NET Core SDK in uso.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--additional-deps <PATH>`

Percorso di un file *.deps.json* aggiuntivo.

`--additionalprobingpath <PATH>`

Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

`--depsfile`

Percorso di un file *deps.json*.

Un file *deps.json* contiene un elenco di dipendenze, le dipendenze di compilazione e le informazioni sulla versione usate per risolvere i conflitti di assembly. Per altri dettagli su questo file, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.

`-d|--diagnostics`

Abilita l'output di diagnostica.

`--fx-version <VERSION>`

Versione del runtime di .NET Core da usare per eseguire l'applicazione.

`-h|--help`

Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`. `dotnet --help` consente di visualizzare un elenco dei comandi disponibili.

`--info`

Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.

`--roll-forward-on-no-candidate-fx`

 Se impostato su `0`, disabilita il roll forward della versione secondaria. Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

`--runtimeconfig`

Percorso di un file *runtimeconfig.json*.

Un file *runtimeconfig. JSON* è un file di configurazione contenente le impostazioni della fase di esecuzione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.

`--version`

Stampa la versione di .NET Core SDK in uso.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

`--depsfile`

Percorso di un file *deps.json*.

Un file *deps.json* contiene un elenco di dipendenze, le dipendenze di compilazione e le informazioni sulla versione usate per risolvere i conflitti di assembly. Per altri dettagli su questo file, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.

`-d|--diagnostics`

Abilita l'output di diagnostica.

`--fx-version <VERSION>`

Versione del runtime di .NET Core da usare per eseguire l'applicazione.

`-h|--help`

Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`. `dotnet --help` consente di visualizzare un elenco dei comandi disponibili.

`--info`

Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.

`--runtimeconfig`

Percorso di un file *runtimeconfig.json*.

Un file *runtimeconfig. JSON* è un file di configurazione contenente le impostazioni della fase di esecuzione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.

`--version`

Stampa la versione di .NET Core SDK in uso.

---

## <a name="dotnet-commands"></a>Comandi dotnet

### <a name="general"></a>Generale

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

| Comando                                       | Funzione                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | Compila un'applicazione .NET Core.                                     |
| [dotnet build-server](dotnet-build-server.md) | Interagisce con i server avviati da una compilazione.                          |
| [dotnet clean](dotnet-clean.md)               | Pulisce gli output di compilazione.                                                |
| [dotnet help](dotnet-help.md)                 | Visualizza documentazione online dettagliata per il comando.           |
| [dotnet migrate](dotnet-migrate.md)           | Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.  |
| [dotnet msbuild](dotnet-msbuild.md)           | Consente di accedere alla riga di comando di MSBuild.                        |
| [dotnet new](dotnet-new.md)                   | Inizializza un progetto C# o F# per un modello specificato.                |
| [dotnet pack](dotnet-pack.md)                 | Crea un pacchetto NuGet del codice.                               |
| [dotnet publish](dotnet-publish.md)           | Pubblica un'applicazione .NET dipendente dal framework o autonoma. |
| [dotnet restore](dotnet-restore.md)           | Ripristina le dipendenze per una determinata applicazione.                  |
| [dotnet run](dotnet-run.md)                   | Esegue l'applicazione dall'origine.                                   |
| [dotnet sln](dotnet-sln.md)                   | Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.       |
| [dotnet store](dotnet-store.md)               | Archivia gli assembly nell'archivio pacchetti di runtime.                     |
| [dotnet test](dotnet-test.md)                 | Esegue test usando un Test Runner.                                     |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

| Comando                             | Funzione                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Compila un'applicazione .NET Core.                                     |
| [dotnet clean](dotnet-clean.md)     | Pulisce gli output di compilazione.                                              |
| [dotnet help](dotnet-help.md)       | Visualizza documentazione online dettagliata per il comando.           |
| [dotnet migrate](dotnet-migrate.md) | Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.  |
| [dotnet msbuild](dotnet-msbuild.md) | Consente di accedere alla riga di comando di MSBuild.                        |
| [dotnet new](dotnet-new.md)         | Inizializza un progetto C# o F# per un modello specificato.                |
| [dotnet pack](dotnet-pack.md)       | Crea un pacchetto NuGet del codice.                               |
| [dotnet publish](dotnet-publish.md) | Pubblica un'applicazione .NET dipendente dal framework o autonoma. |
| [dotnet restore](dotnet-restore.md) | Ripristina le dipendenze per una determinata applicazione.                  |
| [dotnet run](dotnet-run.md)         | Esegue l'applicazione dall'origine.                                   |
| [dotnet sln](dotnet-sln.md)         | Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.       |
| [dotnet store](dotnet-store.md)     | Archivia gli assembly nell'archivio pacchetti di runtime.                     |
| [dotnet test](dotnet-test.md)       | Esegue test usando un Test Runner.                                     |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

| Comando                             | Funzione                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Compila un'applicazione .NET Core.                                     |
| [dotnet clean](dotnet-clean.md)     | Pulisce gli output di compilazione.                                              |
| [dotnet migrate](dotnet-migrate.md) | Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.  |
| [dotnet msbuild](dotnet-msbuild.md) | Consente di accedere alla riga di comando di MSBuild.                        |
| [dotnet new](dotnet-new.md)         | Inizializza un progetto C# o F# per un modello specificato.                |
| [dotnet pack](dotnet-pack.md)       | Crea un pacchetto NuGet del codice.                               |
| [dotnet publish](dotnet-publish.md) | Pubblica un'applicazione .NET dipendente dal framework o autonoma. |
| [dotnet restore](dotnet-restore.md) | Ripristina le dipendenze per una determinata applicazione.                  |
| [dotnet run](dotnet-run.md)         | Esegue l'applicazione dall'origine.                                   |
| [dotnet sln](dotnet-sln.md)         | Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.       |
| [dotnet test](dotnet-test.md)       | Esegue test usando un Test Runner.                                     |

---

### <a name="project-references"></a>Riferimenti al progetto

Comando | Funzione
--- | ---
[dotnet add reference](dotnet-add-reference.md) | Aggiunge un riferimento al progetto.
[dotnet list reference](dotnet-list-reference.md) | Elenca i riferimenti al progetto.
[dotnet remove reference](dotnet-remove-reference.md) | Rimuove un riferimento dal progetto.

### <a name="nuget-packages"></a>Pacchetti NuGet

Comando | Funzione
--- | ---
[dotnet add package](dotnet-add-package.md) | Aggiunge un pacchetto NuGet.
[dotnet remove package](dotnet-remove-package.md) | Rimuove un pacchetto NuGet.

### <a name="nuget-commands"></a>Comandi NuGet

Comando | Funzione
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Rimuove dall'elenco o elimina un pacchetto dal server.
[dotnet nuget locals](dotnet-nuget-locals.md) | Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
[dotnet nuget push](dotnet-nuget-push.md) | Effettua il push di un pacchetto nel server e lo pubblica.

### <a name="global-tools-commands"></a>Comandi degli strumenti globali

Gli [strumenti globali .NET Core](global-tools.md) sono disponibili a partire da .NET Core SDK 2.1.300:

Comando | Funzione
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Installa uno strumento globale nel computer.
[dotnet tool list](dotnet-tool-list.md) | Elenca tutti gli strumenti globali attualmente installati nella directory predefinita nel computer o nel percorso specificato.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Disinstalla uno strumento globale dal computer.
[dotnet tool update](dotnet-tool-update.md) | Aggiorna uno strumento globale nel computer.

### <a name="additional-tools"></a>Altri strumenti

A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK. Tali strumenti sono elencati nella tabella seguente:

| Strumento                                              | Funzione                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea e gestisce i certificati di sviluppo.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Strumenti da riga di comando di Entity Framework Core.                    |
| sql-cache                                         | Strumenti da riga di comando della cache di SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Gestisce i segreti dell'utente di sviluppo.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Avvia un watcher per file che esegue un comando quando si modificano i file. |

Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.

## <a name="examples"></a>Esempi

Creare una nuova applicazione console .NET Core:

`dotnet new console`

Ripristinare le dipendenze per una determinata applicazione:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Compilare un progetto e le relative dipendenze in una determinata directory:

`dotnet build`

Eseguire una DLL dell'applicazione, ad esempio `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Variabili di ambiente

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`DOTNET_PACKAGES`

La cartella dei pacchetti globali. Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

`DOTNET_MULTILEVEL_LOOKUP`

Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale. Se non sono impostati, il valore predefinito è `true`. Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`). Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

Se impostato su `0`, disabilita il roll forward della versione secondaria. Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

`DOTNET_MULTILEVEL_LOOKUP`

Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale. Se non sono impostati, il valore predefinito è `true`. Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`). Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

---

## <a name="see-also"></a>Vedere anche

- [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)
- [Impostazioni di configurazione della fase di esecuzione di .NET Core](../run-time-config/index.md)
