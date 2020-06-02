---
title: Comando dotnet migrate
description: Il comando dotnet migrate consente di eseguire la migrazione di un progetto e di tutte le relative dipendenze.
ms.date: 02/14/2020
ms.openlocfilehash: 2e7f9ae5a1d11c54280d914b04df761f0d5aff99
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284092"
---
# <a name="dotnet-migrate"></a>dotnet migrate

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK

## <a name="name"></a>Nome

`dotnet migrate`: esegue la migrazione di un progetto .NET Core Preview 2 a un progetto di tipo .NET Core SDK.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json <REPORT_FILE>]
    [-r|--report-file <REPORT_FILE>] [-s|--skip-project-references [Debug|Release]]
    [--skip-backup] [-t|--template-file <TEMPLATE_FILE>] [-v|--sdk-package-version]
    [-x|--xproj-file]

dotnet migrate -h|--help
```

## <a name="description"></a>Descrizione

Questo comando è deprecato. Il `dotnet migrate` comando non è più disponibile a partire da .NET Core 3,0 SDK. È possibile eseguire la migrazione di un progetto .NET Core di anteprima 2 a un progetto .NET Core 1. x, che non è supportato.

Per impostazione predefinita, il comando esegue la migrazione del progetto radice e dei riferimenti del progetto presenti nel progetto radice. Questo comportamento viene disabilitato usando l' `--skip-project-references` opzione in fase di esecuzione.

È possibile eseguire la migrazione in uno degli asset seguenti:

* Un singolo progetto, specificando il file *project.json* di cui eseguire la migrazione.
* Tutte le directory specificate nel file *global.json*, passando un percorso del file *global.json*.
* Un file *solution.sln*, dove vengono migrati i progetti a cui viene fatto riferimento nella soluzione.
* Tutte le sottodirectory della directory specificata, in modo ricorsivo.

Il comando `dotnet migrate` mantiene il file *project.json* di cui è stata eseguita la migrazione all'interno di una directory `backup`, che verrà creata se non esiste già. Questo comportamento viene sottoposto a override tramite l'opzione `--skip-backup`.

Per impostazione predefinita, l'operazione di migrazione restituisce lo stato del processo di migrazione all'output standard (STDOUT). Se si usa l'opzione `--report-file <REPORT_FILE>`, l'output viene salvato nel file specificato.

Il comando `dotnet migrate` supporta solo progetti basati su *project.json* Preview 2 validi. Questo significa che non è possibile usare questo comando per eseguire la migrazione di progetti basati su DNX o *project.json* Preview 1 direttamente a progetti MSBuild/csproj. È prima necessario eseguire manualmente la migrazione del progetto a un progetto basato su *project.json* Preview 2 e quindi usare il comando `dotnet migrate` per eseguire la migrazione del progetto.

## <a name="arguments"></a>Argomenti

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

Percorso a uno degli elementi seguenti:

* File *project.json* di cui eseguire la migrazione.
* File *global.json*: viene eseguita la migrazione delle cartelle specificate in *global.json*.
* File *solution.sln*: viene eseguita la migrazione dei progetti a cui viene fatto riferimento nella soluzione.
* Directory di cui eseguire la migrazione: vengono cercati in modo ricorsivo i file *project.json* di cui eseguire la migrazione all'interno della directory specificata.

Se non è specificata alcuna opzione, verrà impostata automaticamente la directory corrente.

## <a name="options"></a>Opzioni

`--format-report-file-json <REPORT_FILE>`

File di report di migrazione dell'output come JSON anziché messaggi utente.

`-h|--help`

Stampa una breve guida per il comando.

`-r|--report-file <REPORT_FILE>`

Report di migrazione dell'output a un file oltre che alla console.

`-s|--skip-project-references [Debug|Release]`

Ignora la migrazione dei riferimenti del progetto. Per impostazione predefinita, i riferimenti al progetto vengono migrati in modo ricorsivo.

`--skip-backup`

Dopo l'esito positivo della migrazione, ignorare lo spostamento di *project.json*, *global.json* e *\*.xproj* in una directory `backup`.

`-t|--template-file <TEMPLATE_FILE>`

File csproj modello da usare per la migrazione. Per impostazione predefinita, viene usato lo stesso modello di quello eliminato da `dotnet new console`.

`-v|--sdk-package-version <VERSION>`

Versione del pacchetto SDK a cui viene fatto riferimento nell'app di cui è stata eseguita la migrazione. Il valore predefinito è la versione dell'SDK in `dotnet new`.

`-x|--xproj-file <FILE>`

Percorso del file xproj da usare. Obbligatorio quando è presente più di un progetto xproj nella directory di un progetto.

## <a name="examples"></a>Esempi

Eseguire la migrazione di un progetto nella directory corrente e in tutte le relative dipendenze da progetto a progetto:

`dotnet migrate`

Eseguire la migrazione di tutti i progetti inclusi nel file *global.json*:

`dotnet migrate path/to/global.json`

Eseguire solo la migrazione del progetto corrente e non delle dipendenze da progetto a progetto. Usare una versione specifica dell'SDK:

`dotnet migrate -s -v 1.0.0-preview4`
