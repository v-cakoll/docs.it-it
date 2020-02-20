---
title: Comando dotnet run
description: Il comando dotnet run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
ms.date: 02/19/2020
ms.openlocfilehash: 415d7079db6a3da80c4fcf2074307ea760e84982
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503603"
---
# <a name="dotnet-run"></a>dotnet run

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] 
    [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] 
    [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando. Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando. Il comando dipende dal comando [`dotnet build`](dotnet-build.md) per compilare il codice. I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.

I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`. Se ad esempio si ha un'applicazione `netcoreapp2.1` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp2.1`. I file vengono sovrascritti in base alle esigenze. I file temporanei vengono inseriti nella directory `obj`.

Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.

Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione. Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando. Ad esempio, per eseguire `myapp.dll`, usare:

```dotnetcli
dotnet myapp.dll
```

Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).

Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet. È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache. In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a>Opzioni

- **`--`**

  Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione. Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito per la maggior parte dei progetti è `Debug`, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.

- **`-f|--framework <FRAMEWORK>`**

  Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato. Il framework deve essere specificato nel file di progetto.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 3.0 SDK.

- **`--launch-profile <NAME>`**

  Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione. I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`. Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).

- **`--no-build`**

  Non compila il progetto prima dell'esecuzione. Imposta anche in modo implicito il flag `--no-restore`.

- **`--no-dependencies`**

  Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.

- **`--no-launch-profile`**

  Non tenta di usare *launchSettings.json* per configurare l'applicazione.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`-p|--project <PATH>`**

  Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Specifica il runtime di destinazione per cui ripristinare i pacchetti. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). `-r` opzione short disponibile a partire da .NET Core 3,0 SDK.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `m`. Disponibile a partire da .NET Core 2,1 SDK. 

## <a name="examples"></a>Esempi

- Eseguire il progetto nella directory corrente:

  ```dotnetcli
  dotnet run
  ```

- Eseguire il progetto specificato:

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usata l'opzione `--` vuota:

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente visualizzando solo il risultato minimo, quindi eseguire il progetto: (.NET Core SDK 2.0 e versioni successive):

  ```dotnetcli
  dotnet run --verbosity m
  ```
