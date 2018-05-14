---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.openlocfilehash: c56ed032ccef6c6fd19a13214b04b384ffff28d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-command"></a>Comando dotnet

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet`: driver generale per l'esecuzione dei comandi della riga di comando.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
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

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

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

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

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
[dotnet add reference](dotnet-add-reference.md) | Aggiungere un riferimento al progetto.
[dotnet list reference](dotnet-list-reference.md) | Elencare i riferimenti al progetto.
[dotnet remove reference](dotnet-remove-reference.md) | Rimuovere un riferimento al progetto.

### <a name="nuget-packages"></a>Pacchetti NuGet

Comando | Funzione
--- | ---
[dotnet add package](dotnet-add-package.md) | Aggiungere un pacchetto NuGet.
[dotnet remove package](dotnet-remove-package.md) | Rimuovere un pacchetto NuGet.

### <a name="nuget-commands"></a>Comandi NuGet

Comando | Funzione
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Rimuove dall'elenco o elimina un pacchetto dal server.
[dotnet nuget locals](dotnet-nuget-locals.md) | Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.
[dotnet nuget push](dotnet-nuget-push.md) | Effettua il push di un pacchetto nel server e lo pubblica.

## <a name="examples"></a>Esempi

Inizializzare un'applicazione console .NET Core di esempio che può essere compilata ed eseguita:

`dotnet new console`

Ripristinare le dipendenze per una determinata applicazione:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Compilare un progetto e le relative dipendenze in una determinata directory:

`dotnet build`

Eseguire un'app dipendente dal framework denominata `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Variabili di ambiente

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

`DOTNET_MULTILEVEL_LOOKUP`

Specifica se il runtime .NET Core, il framework condiviso o SDK vengono risolti dal percorso globale. Se non sono impostati, il valore predefinito è `true`. Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`). Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`DOTNET_PACKAGES`

Cache dei pacchetti principali. Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.

`DOTNET_SERVICING`

Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft. Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`). Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.

---
