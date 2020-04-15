---
title: Comando dotnet
description: Informazioni sul comando dotnet (il driver generico per l'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
ms.date: 02/13/2020
ms.openlocfilehash: 9446808d7f23d762c7a3c8a58252664fc5dade5b
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389603"
---
# <a name="dotnet-command"></a>Comando dotnet

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet`- Il driver generico per l'interfaccia della riga di comando di .NET Core.- The generic driver for the .NET Core CLI.

## <a name="synopsis"></a>Riepilogo

Per ottenere informazioni sui comandi disponibili e sull'ambiente:

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

Per eseguire un comando (richiede l'installazione SDK):

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

Per eseguire un'applicazione:

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

`--roll-forward`è disponibile a partire da .NET Core 3.x. Utilizzare `--roll-forward-on-no-candidate-fx` per .NET Core 2.x.

## <a name="description"></a>Descrizione

Il `dotnet` comando ha due funzioni:

- Fornisce comandi per l'utilizzo di progetti .NET Core.It provides commands for working with .NET Core projects.

  Ad esempio, [`dotnet build`](dotnet-build.md) compila un progetto. Ogni comando definisce le proprie opzioni e argomenti. Tutti i `--help` comandi supportano l'opzione per stampare una breve documentazione su come utilizzare il comando.

- Esegue applicazioni .NET Core.It runs .NET Core applications.

  Specificare il percorso `.dll` di un file dell'applicazione per eseguire l'applicazione.  Eseguire l'applicazione significa trovare ed eseguire il punto di ingresso, `Main` che nel caso delle applicazioni console è il metodo. Ad esempio, `dotnet myapp.dll` `myapp` esegue l'applicazione. Per informazioni sulle opzioni di distribuzione, [vedere Distribuzione di applicazioni .NET Core.See .NET Core application deployment](../deploying/index.md) to learn about deployment options.

## <a name="options"></a>Opzioni

Sono disponibili diverse `dotnet` opzioni per se stesso, per l'esecuzione di un comando e per l'esecuzione di un'applicazione.

### <a name="options-for-dotnet-by-itself"></a>Opzioni per dotnet da solo

Le seguenti opzioni `dotnet` sono per sé. Ad esempio: `dotnet --info`. Stampano informazioni sull'ambiente.

- **`--info`**

  Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.

- **`--version`**

  Stampa la versione di .NET Core SDK in uso.

- **`--list-runtimes`**

  Stampa un elenco dei runtime .NET Core installati. Una versione x86 dell'SDK elenca solo i runtime x86 e una versione x64 del SDK elenca solo i runtime x64.

- **`--list-sdks`**

  Stampa un elenco degli SDK di .NET Core installati.

- **`-h|--help`**

  Stampa un elenco dei comandi disponibili.

### <a name="sdk-options-for-running-a-command"></a>Opzioni SDK per l'esecuzione di un comando

Le seguenti opzioni `dotnet` sono per con un comando. Ad esempio: `dotnet build --help`.

- **`-d|--diagnostics`**

  Abilita l'output di diagnostica.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in ogni comando. Vedere la pagina dei comandi specifica per determinare se questa opzione è disponibile.

- **`-h|--help`**

  Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.

- **`command options`**

  Ogni comando definisce le opzioni specifiche di tale comando. Vedere la pagina dei comandi specifici per un elenco delle opzioni disponibili.

### <a name="runtime-options"></a>Opzioni di runtime

Quando `dotnet` si esegue un'applicazione, sono disponibili le opzioni seguenti. Ad esempio: `dotnet myapp.dll --fx-version 3.1.1`.

- **`--additionalprobingpath <PATH>`**

  Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

- **`--additional-deps <PATH>`**

  Percorso di un file *.deps.json* aggiuntivo. Un file *deps.json* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti tra assembly. Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.

- **`--fx-version <VERSION>`**

  Versione del runtime di .NET Core da usare per eseguire l'applicazione.

- **`--runtimeconfig`**

  Percorso di un file *runtimeconfig.json*. Un file *runtimeconfig.json* è un file di configurazione che contiene le impostazioni di runtime. Per ulteriori informazioni, vedere Impostazioni di configurazione di [runtime di .NET Core](../run-time-config/index.md#runtimeconfigjson).

- **`--roll-forward-on-no-candidate-fx <N>`****Disponibile in .NET Core 2.x SDK.**

  Definisce il comportamento quando il framework condiviso richiesto non è disponibile. `N` può essere:

  - `0` - Disabilitare anche il roll forward per la versione secondaria.
  - `1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale. Questo è il comportamento predefinito.
  - `2` - Eseguire il roll forward per le versioni principali e secondarie.

   Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

- **`--roll-forward <SETTING>`****Disponibile a partire da .NET Core SDK 3.0.**

  Controlla il modo in cui il rollforward viene applicato all'app. Può `SETTING` essere uno dei seguenti valori. Se non `Minor` specificato, è l'impostazione predefinita.

  - `LatestPatch`- Roll forward alla versione patch più alta. Disabilita il roll forward della versione secondaria.
  - `Minor`- Roll forward alla versione secondaria più bassa superiore, se richiesta versione secondaria è mancante. Se la versione secondaria richiesta è presente, viene usato il criterio LatestPatch.
  - `Major`- Roll forward alla versione principale superiore più bassa e versione secondaria più bassa, se manca la versione principale richiesta. Se la versione principale richiesta è presente, viene usato il criterio Minor.
  - `LatestMinor`- Passa alla versione secondaria più alta, anche se è presente la versione secondaria richiesta. È destinata a scenari di hosting dei componenti.
  - `LatestMajor`- Passa alla versione principale e secondaria più alta, anche se è presente la versione principale richiesta. È destinata a scenari di hosting dei componenti.
  - `Disable`- Non andare avanti. Esegue solo un'associazione alla versione specificata. Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti. Questo valore è consigliato solo a scopo di test.

Ad eccezione `Disable`di , tutte le impostazioni utilizzeranno la versione di patch più alta disponibile.

Il comportamento di rollforward può essere configurato anche in una proprietà del file di progetto, in una proprietà del file di configurazione di runtime e in una variabile di ambiente. Per ulteriori informazioni, vedere [Rollforward di runtime di versione principale](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).

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

### <a name="global-tool-path-and-local-tools-commands"></a>Comandi globali, del percorso degli strumenti e degli strumenti locali

Gli strumenti sono applicazioni console installate da pacchetti NuGet e richiamate dal prompt dei comandi. È possibile scrivere strumenti da soli o installare strumenti scritti da terze parti. Gli strumenti sono noti anche come strumenti globali, strumenti per il percorso degli strumenti e strumenti locali. Per ulteriori informazioni, vedere [Panoramica degli strumenti .NET Core](global-tools.md). Gli strumenti globali e per corsi degli strumenti sono disponibili a partire da .NET Core SDK 2.1. Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.

Comando | Funzione
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Installa uno strumento sul computer.
[dotnet tool list](dotnet-tool-list.md) | Elenca tutti gli strumenti globali, del percorso degli strumenti o locali attualmente installati nel computer.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Disinstalla uno strumento dal computer.
[dotnet tool update](dotnet-tool-update.md) | Aggiorna uno strumento installato nel computer.

### <a name="additional-tools"></a>Strumenti aggiuntivi

A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK. Tali strumenti sono elencati nella tabella seguente:

| Strumento                                              | Funzione                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea e gestisce i certificati di sviluppo.                |
| [Ef](/ef/core/miscellaneous/cli/dotnet)           | Strumenti da riga di comando di Entity Framework Core.                    |
| sql-cache                                         | Strumenti da riga di comando della cache di SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Gestisce i segreti dell'utente di sviluppo.                            |
| [orologio](/aspnet/core/tutorials/dotnet-watch)      | Avvia un watcher per file che esegue un comando quando si modificano i file. |

Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.

## <a name="examples"></a>Esempi

Creare una nuova applicazione console .NET Core:Create a new .NET Core console application:

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

  Specifica il percorso dei runtime .NET Core, se non sono installati nel percorso predefinito. Il percorso predefinito `C:\Program Files\dotnet`in Windows è . Il percorso predefinito su Linux `/usr/share/dotnet`e macOS è . Questa variabile di ambiente viene usata solo quando si eseguono app tramite file eseguibili generati (apphosts). `DOTNET_ROOT(x86)`viene utilizzato invece quando si esegue un eseguibile a 32 bit su un sistema operativo a 64 bit.

- `DOTNET_PACKAGES`

  La cartella dei pacchetti globali. Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.

- `DOTNET_SERVICING`

  Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

- `DOTNET_NOLOGO`

  Specifica se i messaggi di benvenuto e di telemetria di .NET Core vengono visualizzati alla prima esecuzione. Impostare `true` su per disattivare `true` `1`l'audio di questi messaggi (valori `yes` o accettati) o su `false` consentito (valori `false`, `0`o `no` accettati ). Se non è impostato, il valore predefinito è `false` e i messaggi verranno visualizzati alla prima esecuzione. Si noti che questo flag `DOTNET_CLI_TELEMETRY_OPTOUT` non ha alcun effetto sui dati di telemetria (vedere per la disattivazione dell'invio di dati di telemetria).

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

- `DOTNET_MULTILEVEL_LOOKUP`

  Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale. Se non è impostato, il `true`valore predefinito è 1 (logico ). Impostare su `false`0 (logico ) per non risolvere dal percorso globale e sono state isolate installazioni .NET Core. Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

- `DOTNET_ROLL_FORWARD`**Disponibile a partire da .NET Core 3.x SDK.**

  Determina il comportamento di rollforward. Per altre informazioni, `--roll-forward` vedere l'opzione più indietro in questo articolo.

- `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`**Disponibile in .NET Core 2.x SDK.**

  Se impostato su `0`, disabilita il roll forward della versione secondaria. Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

- `DOTNET_CLI_UI_LANGUAGE`

  Imposta la lingua dell'interfaccia utente dell'interfaccia della riga di comando utilizzando un valore delle impostazioni locali, `en-us`ad esempio . The supported values are the same as for Visual Studio. Per ulteriori informazioni, vedere la sezione sulla modifica della lingua del programma di installazione nella [documentazione relativa all'installazione](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)di Visual Studio. Si applicano le regole di gestione delle risorse .NET, pertanto non è necessario selezionare una corrispondenza&mdash;esatta, è anche possibile selezionare i discendenti nell'albero. `CultureInfo` Ad esempio, se si `fr-CA`imposta su , l'interfaccia della riga di comando troverà e utilizzerà le `fr` traduzioni. Se si imposta su una lingua non supportata, l'interfaccia della riga di comando esegue il fallback all'inglese.

- `DOTNET_DISABLE_GUI_ERRORS`

  Per gli eseguibili generati abilitati per GUI - disabilita la finestra popup della finestra di dialogo, che normalmente mostra per alcune classi di errori. Scrive `stderr` e esce solo in questi casi.
  
- `DOTNET_ADDITIONAL_DEPS`

  Equivalente all'opzione `--additional-deps`CLI .

- `DOTNET_RUNTIME_ID`

  Esegue l'override del RID rilevato.

- `DOTNET_SHARED_STORE`

  Posizione dell'"archivio condiviso" in cui viene eseguito il fallback della risoluzione dell'assembly in alcuni casi.

- `DOTNET_STARTUP_HOOKS`

  Elenco di assembly da cui caricare ed eseguire gli hook di avvio.

- `COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`

  Controlla la traccia diagnostica dai `dotnet.exe`componenti `hostfxr`di `hostpolicy`hosting, ad esempio , e .

## <a name="see-also"></a>Vedere anche

- [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)
- [Impostazioni di configurazione di runtime di .NET Core](../run-time-config/index.md)
