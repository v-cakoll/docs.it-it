---
title: Comando dotnet run - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 82c6e44e52aa6af7044edf72fd6e57b7614a70f3
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696312"
---
# <a name="dotnet-run"></a>dotnet run

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```
---

## <a name="description"></a>Descrizione

Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando. Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando. Il comando dipende dal comando [`dotnet build`](dotnet-build.md) per compilare il codice. I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.

I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`. Se ad esempio si ha un'applicazione `netcoreapp1.0` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp1.0`. I file vengono sovrascritti in base alle esigenze. I file temporanei vengono inseriti nella directory `obj`.

Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.

Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione. Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando. Ad esempio, per eseguire `myapp.dll`, usare:

```console
dotnet myapp.dll
```

Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).

Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet. È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache. In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a>Opzioni

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--`

Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione. Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato. Il framework deve essere specificato nel file di progetto.

`--force`

Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

`-h|--help`

Stampa una breve guida per il comando.

`--launch-profile <NAME>`

Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione. I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`. Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).

`--no-build`

Non compila il progetto prima dell'esecuzione. Imposta anche in modo implicito il flag `--no-restore`.

`--no-dependencies`

Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.

`--no-launch-profile`

Non tenta di usare *launchSettings.json* per configurare l'applicazione.

`--no-restore`

Non esegue un ripristino implicito quando si esegue il comando.

`-p|--project <PATH>`

Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.

`--runtime <RUNTIME_IDENTIFIER>`

Specifica il runtime di destinazione per cui ripristinare i pacchetti. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--`

Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione. Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato. Il framework deve essere specificato nel file di progetto.

`--force`

Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

`-h|--help`

Stampa una breve guida per il comando.

`--launch-profile <NAME>`

Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione. I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`. Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).

`--no-build`

Non compila il progetto prima dell'esecuzione. Imposta anche in modo implicito il flag `--no-restore`.

`--no-dependencies`

Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.

`--no-launch-profile`

Non tenta di usare *launchSettings.json* per configurare l'applicazione.

`--no-restore`

Non esegue un ripristino implicito quando si esegue il comando.

`-p|--project <PATH>`

Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.

`--runtime <RUNTIME_IDENTIFIER>`

Specifica il runtime di destinazione per cui ripristinare i pacchetti. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--`

Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione. Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato. Il framework deve essere specificato nel file di progetto.

`-h|--help`

Stampa una breve guida per il comando.

`-p|--project <PATH/PROJECT.csproj>`

Specifica il percorso e il nome del file di progetto. Vedere la nota. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.

> [!NOTE]
> Usare il percorso e il nome del file di progetto con l'opzione `-p|--project`. Una regressione nell'interfaccia della riga di comando impedisce di specificare un percorso di cartella con .NET Core SDK 1.x. Per altre informazioni su questo problema, vedere [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, non è possibile avviare un progetto (dotnet/cli #5992)).

---

## <a name="examples"></a>Esempi

Eseguire il progetto nella directory corrente:

`dotnet run`

Eseguire il progetto specificato:

`dotnet run --project /projects/proj1/proj1.csproj`

Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usato l'argomento `--`:

`dotnet run --configuration Release -- --help`

Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente visualizzando solo il risultato minimo, quindi eseguire il progetto: (.NET Core SDK 2.0 e versioni successive):

`dotnet run --verbosity m`