---
title: Comando dotnet
description: Informazioni sul comando DotNet (il driver generico per la interfaccia della riga di comando di .NET Core) e il relativo utilizzo.
ms.date: 02/13/2020
ms.openlocfilehash: 88e92b3ff5e8f68b980015a817434dd2d67df93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378834"
---
# <a name="dotnet-command"></a>Comando dotnet

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet`-Il driver generico per la interfaccia della riga di comando di .NET Core.

## <a name="synopsis"></a>Riepilogo

Per ottenere informazioni sui comandi disponibili e sull'ambiente:

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

Per eseguire un comando (richiede l'installazione dell'SDK):

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

Per eseguire un'applicazione:

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

`--roll-forward`è disponibile a partire da .NET Core 3. x. Usare `--roll-forward-on-no-candidate-fx` per .NET Core 2. x.

## <a name="description"></a>Description

Il `dotnet` comando ha due funzioni:

- Fornisce i comandi per l'uso dei progetti .NET Core.

  Ad esempio, [`dotnet build`](dotnet-build.md) Compila un progetto. Ogni comando definisce le proprie opzioni e gli argomenti. Tutti i comandi supportano l' `--help` opzione per stampare brevemente la documentazione su come usare il comando.

- Esegue le applicazioni .NET Core.

  Specificare il percorso di un `.dll` file di applicazione per eseguire l'applicazione.  Per eseguire l'applicazione significa trovare ed eseguire il punto di ingresso, che nel caso delle app console è il `Main` metodo. Ad esempio, `dotnet myapp.dll` esegue l' `myapp` applicazione. Per informazioni sulle opzioni di distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md) .

## <a name="options"></a>Opzioni

Diverse opzioni sono disponibili per `dotnet` sé, per l'esecuzione di un comando e per l'esecuzione di un'applicazione.

### <a name="options-for-dotnet-by-itself"></a>Opzioni per DotNet autonomamente

Le opzioni seguenti sono destinate a `dotnet` se stesso. Ad esempio, `dotnet --info` Stampano le informazioni sull'ambiente.

- **`--info`**

  Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.

- **`--version`**

  Stampa la versione di .NET Core SDK in uso.

- **`--list-runtimes`**

  Stampa un elenco di runtime di .NET Core installati. Una versione x86 dell'SDK elenca solo i Runtime x86 e una versione x64 dell'SDK elenca solo i runtime x64.

- **`--list-sdks`**

  Stampa un elenco degli SDK di .NET Core installati.

- **`-h|--help`**

  Stampa un elenco di comandi disponibili.

### <a name="sdk-options-for-running-a-command"></a>Opzioni SDK per l'esecuzione di un comando

Le opzioni seguenti sono per `dotnet` con un comando. Ad esempio, `dotnet build --help`

- **`-d|--diagnostics`**

  Abilita l'output di diagnostica.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in ogni comando. Vedere la pagina di comando specifica per determinare se questa opzione è disponibile.

- **`-h|--help`**

  Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.

- **`command options`**

  Ogni comando definisce opzioni specifiche del comando. Per un elenco delle opzioni disponibili, vedere la pagina di comando specifica.

### <a name="runtime-options"></a>Opzioni di runtime

Quando `dotnet` viene eseguita un'applicazione, sono disponibili le opzioni seguenti. Ad esempio, `dotnet myapp.dll --roll-forward Major`

- **`--additionalprobingpath <PATH>`**

  Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

- **`--additional-deps <PATH>`**

  Percorso di un file *.deps.json* aggiuntivo. Un file *Deps. JSON* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti di assembly. Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.

- **`--depsfile <PATH_TO_DEPSFILE>`**

  Percorso del file *Deps. JSON* . Un file *Deps. JSON* è un file di configurazione che contiene informazioni sulle dipendenze necessarie per l'esecuzione dell'applicazione. Questo file viene generato dal .NET Core SDK.

- **`--runtimeconfig`**

  Percorso di un file *runtimeconfig.json*. Un file *runtimeconfig. JSON* è un file di configurazione che contiene le impostazioni della fase di esecuzione. Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).

- **`--roll-forward <SETTING>`****Disponibile a partire da .NET Core SDK 3,0.**

  Controlla il modo in cui viene applicato il rollforward all'app. `SETTING`Può essere uno dei valori seguenti. Se non è specificato, `Minor` è il valore predefinito.

  - `LatestPatch`-Eseguire il rollforward alla versione più recente della patch. Disabilita il roll forward della versione secondaria.
  - `Minor`-Eseguire il rollforward alla versione secondaria più bassa, se manca la versione secondaria richiesta. Se la versione secondaria richiesta è presente, viene usato il criterio LatestPatch.
  - `Major`: Eseguire il rollforward alla versione principale più bassa e la versione secondaria più bassa, se la versione principale richiesta è mancante. Se la versione principale richiesta è presente, viene usato il criterio Minor.
  - `LatestMinor`-Rollforward alla versione secondaria più elevata, anche se è presente una versione secondaria richiesta. È destinata a scenari di hosting dei componenti.
  - `LatestMajor`-Eseguire il rollforward alla versione principale più elevata e alla versione secondaria più elevata, anche se è presente la versione principale richiesta. È destinata a scenari di hosting dei componenti.
  - `Disable`-Non eseguire il rollforward. Esegue solo un'associazione alla versione specificata. Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti. Questo valore è consigliato solo a scopo di test.

  Ad eccezione di `Disable` , tutte le impostazioni utilizzeranno la versione patch più recente disponibile.

  Il comportamento di rollforward può essere configurato anche in una proprietà file di progetto, in una proprietà del file di configurazione in fase di esecuzione e in una variabile di ambiente. Per ulteriori informazioni, vedere il [rollforward del runtime della versione principale](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).

- **`--roll-forward-on-no-candidate-fx <N>`****Disponibile in .NET Core 2. x SDK.**

  Definisce il comportamento quando il framework condiviso richiesto non è disponibile. `N` può essere:

  - `0` - Disabilitare anche il roll forward per la versione secondaria.
  - `1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale. Questo è il comportamento predefinito.
  - `2` - Eseguire il roll forward per le versioni principali e secondarie.

  Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

  A partire da .NET Core 3,0, questa opzione è sostituita da `--roll-forward` ed è invece necessario usare questa opzione.

- **`--fx-version <VERSION>`**

  Versione del runtime di .NET Core da usare per eseguire l'applicazione.

  Questa opzione esegue l'override della versione del primo riferimento al Framework nel file dell'applicazione `.runtimeconfig.json` . Ciò significa che funziona solo come previsto se è presente solo un riferimento al Framework. Se l'applicazione dispone di più di un riferimento a Framework, l'utilizzo di questa opzione può causare errori.

## <a name="dotnet-commands"></a>Comandi dotnet

### <a name="general"></a>Generale

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
[dotnet nuget push](dotnet-nuget-push.md) | Effettua il push di un pacchetto nel server e lo pubblica.
[dotnet nuget locals](dotnet-nuget-locals.md) | Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
[dotnet nuget add source](dotnet-nuget-add-source.md) | Aggiunge un'origine NuGet.
[dotnet nuget disable source](dotnet-nuget-disable-source.md) | Disabilita un'origine NuGet.
[dotnet nuget enable source](dotnet-nuget-enable-source.md) | Abilita un'origine NuGet.
[dotnet nuget list source](dotnet-nuget-list-source.md) | Elenca tutte le origini NuGet configurate.
[dotnet nuget remove source](dotnet-nuget-remove-source.md) | Rimuove un'origine NuGet.
[dotnet nuget update source](dotnet-nuget-update-source.md) | Aggiorna un'origine NuGet.

### <a name="global-tool-path-and-local-tools-commands"></a>Comandi Global, Tool-Path e local Tools

Gli strumenti sono applicazioni console installate da pacchetti NuGet e vengono richiamate dal prompt dei comandi. È possibile scrivere strumenti manualmente oppure installare gli strumenti scritti da terze parti. Gli strumenti sono noti anche come strumenti globali, strumenti per percorsi di strumenti e strumenti locali. Per altre informazioni, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md). Gli strumenti per percorsi globali e strumenti sono disponibili a partire da .NET Core SDK 2,1. Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.

Comando | Funzione
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Installa uno strumento nel computer.
[dotnet tool list](dotnet-tool-list.md) | Elenca tutti gli strumenti globali, di percorso degli strumenti o locali attualmente installati nel computer.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Disinstalla uno strumento dal computer.
[dotnet tool update](dotnet-tool-update.md) | Aggiorna uno strumento installato nel computer.

### <a name="additional-tools"></a>Strumenti aggiuntivi

A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK. Tali strumenti sono elencati nella tabella seguente:

| Strumento                                              | Funzione                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea e gestisce i certificati di sviluppo.                |
| [EF](/ef/core/miscellaneous/cli/dotnet)           | Strumenti da riga di comando di Entity Framework Core.                    |
| sql-cache                                         | Strumenti da riga di comando della cache di SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Gestisce i segreti dell'utente di sviluppo.                            |
| [guardare](/aspnet/core/tutorials/dotnet-watch)      | Avvia un watcher per file che esegue un comando quando si modificano i file. |

Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.

## <a name="examples"></a>Esempi

Creare una nuova applicazione console .NET Core:

```dotnetcli
dotnet new console
```

Compilare un progetto e le relative dipendenze in una determinata directory:

```dotnetcli
dotnet build
```

Eseguire un'applicazione:

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a>Variabili di ambiente

- `DOTNET_ROOT`, `DOTNET_ROOT(x86)`

  Specifica il percorso dei runtime di .NET Core, se non sono installati nel percorso predefinito. Il percorso predefinito in Windows è `C:\Program Files\dotnet` . Il percorso predefinito in Linux e macOS è `/usr/share/dotnet` . Questa variabile di ambiente viene utilizzata solo quando si eseguono app tramite file eseguibili generati (apphosts). `DOTNET_ROOT(x86)`viene invece usato quando si esegue un eseguibile a 32 bit in un sistema operativo a 64 bit.

- `DOTNET_PACKAGES`

  La cartella dei pacchetti globali. Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.

- `DOTNET_SERVICING`

  Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

- `DOTNET_NOLOGO`

  Specifica se i messaggi di benvenuto e di telemetria di .NET Core vengono visualizzati alla prima esecuzione. Impostare su `true` per disattivare questi messaggi (valori `true` , `1` o `yes` accettati) o impostare su `false` Consenti (valori `false` , `0` o `no` accettati). Se non è impostato, il valore predefinito è `false` e i messaggi verranno visualizzati alla prima esecuzione. Questo flag non ha alcun effetto sui dati di telemetria (vedere per rifiutare esplicitamente `DOTNET_CLI_TELEMETRY_OPTOUT` l'invio di dati di telemetria).

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

- `DOTNET_MULTILEVEL_LOOKUP`

  Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale. Se non impostato, il valore predefinito è 1 (logico `true` ). Impostare su 0 (Logical `false` ) per non risolversi dal percorso globale e avere installazioni .NET Core isolate. Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

- `DOTNET_ROLL_FORWARD`**Disponibile a partire da .NET Core 3. x.**

  Determina il comportamento di rollforward. Per ulteriori informazioni, vedere l' `--roll-forward` opzione riportata in precedenza in questo articolo.

- `DOTNET_ROLL_FORWARD_TO_PRERELEASE`**Disponibile a partire da .NET Core 3. x.**

  Se impostato su `1` (abilitato), consente di eseguire il rollforward di una versione non definitiva da una versione di rilascio. Per impostazione predefinita ( `0` -disabilitato), quando viene richiesta una versione di rilascio del runtime di .NET Core, il rollforward prende in considerazione solo le versioni di rilascio installate.

  Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).

- `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`**Disponibile in .NET Core 2. x.**

  Se impostato su `0`, disabilita il roll forward della versione secondaria. Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

  Questa impostazione viene sostituita in .NET Core 3,0 da `DOTNET_ROLL_FORWARD` . In alternativa, è consigliabile usare le nuove impostazioni.

- `DOTNET_CLI_UI_LANGUAGE`

  Imposta la lingua dell'interfaccia utente CLI usando un valore delle impostazioni locali, ad esempio `en-us` . I valori supportati sono identici a quelli di Visual Studio. Per ulteriori informazioni, vedere la sezione relativa alla modifica della lingua del programma di installazione nella [documentazione sull'installazione di Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019). Si applicano le regole di .NET Resource Manager, pertanto non è necessario scegliere una corrispondenza esatta &mdash; . è anche possibile selezionare i discendenti nell' `CultureInfo` albero. Se, ad esempio, si imposta su `fr-CA` , l'interfaccia della riga di comando troverà e utilizzerà le `fr` traduzioni. Se lo si imposta su una lingua non supportata, l'interfaccia della riga di comando esegue il fallback all'inglese.

- `DOTNET_DISABLE_GUI_ERRORS`

  Per gli eseguibili generati da GUI, Disabilita il popup della finestra di dialogo, che in genere viene visualizzato per determinate classi di errori. In questi casi, scrive solo in `stderr` e chiude.
  
- `DOTNET_ADDITIONAL_DEPS`

  Equivale all'opzione CLI `--additional-deps` .

- `DOTNET_RUNTIME_ID`

  Esegue l'override del RID rilevato.

- `DOTNET_SHARED_STORE`

  Percorso dell'archivio condiviso in cui viene eseguito il fallback della risoluzione degli assembly in alcuni casi.

- `DOTNET_STARTUP_HOOKS`

  Elenco di assembly da cui caricare ed eseguire hook di avvio.

- `DOTNET_BUNDLE_EXTRACT_BASE_DIR`**Disponibile a partire da .NET Core 3. x.**

  Specifica una directory in cui viene estratta un'applicazione a file singolo prima che venga eseguita.

  Per ulteriori informazioni, vedere [file eseguibili con singolo file](../whats-new/dotnet-core-3-0.md#single-file-executables).

- `COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`

  Controlla la traccia di diagnostica dai componenti di hosting, ad esempio `dotnet.exe` , `hostfxr` e `hostpolicy` .

  * `COREHOST_TRACE=[0/1]`-la traccia predefinita è `0` disabilitata. Se impostato su `1` , la traccia di diagnostica è abilitata.
  * `COREHOST_TRACEFILE=<file path>`-ha effetto solo se la traccia è abilitata tramite `COREHOST_TRACE=1` . Se impostato, le informazioni di traccia vengono scritte nel file specificato, in caso contrario le informazioni di traccia vengono scritte in `stderr` . **Disponibile a partire da .NET Core 3. x.**
  * `COREHOST_TRACE_VERBOSITY=[1/2/3/4]`-il valore predefinito è `4` . L'impostazione viene utilizzata solo quando la traccia è abilitata tramite `COREHOST_TRACE=1` . **Disponibile a partire da .NET Core 3. x.**
    * `4`-tutte le informazioni di traccia vengono scritte
    * `3`-vengono scritti solo messaggi informativi, di avviso e di errore
    * `2`-vengono scritti solo i messaggi di avviso e di errore
    * `1`-vengono scritti solo i messaggi di errore

  Il modo più comune per ottenere informazioni dettagliate sulla traccia dell'avvio dell'applicazione consiste nell'impostare `COREHOST_TRACE=1` e `COREHOST_TRACEFILE=host_trace.txt` quindi eseguire l'applicazione. Verrà creato un nuovo file `host_trace.txt` nella directory corrente con le informazioni dettagliate.

## <a name="see-also"></a>Vedere anche

- [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)
- [Impostazioni di configurazione della fase di esecuzione di .NET Core](../run-time-config/index.md)
