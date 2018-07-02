---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805659"
---
# <a name="dotnet-command"></a>Comando dotnet

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet`: driver generale per l'esecuzione dei comandi della riga di comando.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a>Descrizione

`dotnet` è un driver generico per la toolchain dell'interfaccia della riga di comando. Se richiamato come comando autonomo, visualizza brevi istruzioni di utilizzo.

Ogni funzionalità specifica viene implementata come un comando. Per usare la funzionalità, il comando viene specificato dopo `dotnet`, ad esempio [`dotnet build`](dotnet-build.md). Tutti gli argomenti che seguono il comando sono gli argomenti del comando.

`dotnet` viene usato come comando autonomo solo per eseguire [app dipendenti dal framework](../deploying/index.md). Per eseguire l'applicazione, ad esempio `dotnet myapp.dll`, specificare una DLL di applicazione dopo il verbo `dotnet`.

## <a name="options"></a>Opzioni

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--additional-deps <PATH>`

Percorso del file *deps.json* aggiuntivo.

`--additionalprobingpath <PATH>`

Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

`-d|--diagnostics`

Abilita l'output di diagnostica.

`--fx-version <VERSION>`

Versione del runtime .NET Core installato da usare per eseguire l'applicazione.

`-h|--help`

Stampa una breve guida per il comando. Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.

`--info`

Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.

`--list-runtimes`

Visualizza i runtime di .NET Core installati.

`--list-sdks`

Visualizza i .NET Core SDK installati.

`--roll-forward-on-no-candidate-fx`

 Non esegue il roll forward su framework condiviso candidato.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.

`--version`

Stampa la versione di .NET Core SDK in uso.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--additional-deps <PATH>`

Percorso del file *deps.json* aggiuntivo.

`--additionalprobingpath <PATH>`

Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

`-d|--diagnostics`

Abilita l'output di diagnostica.

`--fx-version <VERSION>`

Versione del runtime .NET Core installato da usare per eseguire l'applicazione.

`-h|--help`

Stampa una breve guida per il comando. Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.

`--info`

Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.

`--roll-forward-on-no-candidate-fx`

 Non esegue il roll forward su framework condiviso candidato.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.

`--version`

Stampa la versione di .NET Core SDK in uso.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.

`-d|--diagnostics`

Abilita l'output di diagnostica.

`--fx-version <VERSION>`

Versione del runtime .NET Core installato da usare per eseguire l'applicazione.

`-h|--help`

Stampa una breve guida per il comando. Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.

`--info`

Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.

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

A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK. Questi strumenti comprendono:

| Strumento                                              | Funzione                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea e gestisce i certificati di sviluppo.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Strumenti da riga di comando di Entity Framework Core.                    |
| sql-cache                                         | Strumenti da riga di comando della cache di SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Gestisce i segreti dell'utente di sviluppo.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Avvia un watcher per file che esegue un comando quando si modificano i file. |

Per altre informazioni sui diversi strumenti, eseguire `dotnet <tool-name> --help`.

## <a name="examples"></a>Esempi

Creare una nuova applicazione console .NET Core:

`dotnet new console`

Ripristinare le dipendenze per una determinata applicazione:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Compilare un progetto e le relative dipendenze in una determinata directory:

`dotnet build`

Eseguire un'app dipendente dal framework denominata `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Variabili di ambiente

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

`DOTNET_MULTILEVEL_LOOKUP`

Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale. Se non sono impostati, il valore predefinito è `true`. Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`). Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

Disabilita il roll forward della versione secondaria. Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

`DOTNET_MULTILEVEL_LOOKUP`

Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale. Se non sono impostati, il valore predefinito è `true`. Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`). Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

---
