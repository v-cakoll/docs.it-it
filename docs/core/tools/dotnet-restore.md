---
title: Comando dotnet restore - Interfaccia della riga di comando di .NET Core
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
keywords: dotnet-restore, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 50e8d5c335386c41e36a490263a4f4ebd2bd39ba
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="dotnet-restore"></a>dotnet restore

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a>Descrizione

Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto. Per impostazione predefinita, il ripristino delle dipendenze e degli strumenti viene eseguito in parallelo.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti. I feed vengono forniti in genere tramite il file di configurazione *NuGet.config*. Durante l'installazione degli strumenti dell'interfaccia della riga di comando, viene fornito un file di configurazione predefinito. È possibile specificare più feed creando un file *NuGet.config* nella directory del progetto. È inoltre possibile specificare feed aggiuntivi per ogni chiamata a un prompt dei comandi.

Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino usando l'argomento `--packages`. Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi (ad esempio, */home/user1* in Linux or *C:\Users\user1* in Windows).

Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.

Il funzionamento del comando `dotnet restore` può essere modificato da alcune impostazioni del file *NuGet.Config*, se è presente. Se ad esempio si imposta `globalPackagesFolder` in *NuGet.Config* i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata. Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`. Per altre informazioni, vedere [NuGet.Config reference](/nuget/schema/nuget-config-file) (Informazioni di riferimento su NuGet.Config).

## <a name="implicit-dotnet-restore"></a>`dotnet restore` implicito

A partire da .NET Core 2.0, `dotnet restore` viene eseguito in modo implicito se necessario quando si usano i comandi seguenti:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

Nella maggior parte dei casi non è più necessario usare il comando `dotnet restore` in modo esplicito. 

In alcuni casi è poco pratico eseguire `dotnet restore` in modo implicito. È ad esempio necessario che alcuni sistemi automatizzati, come i sistemi di compilazione, chiamino `dotnet restore` in modo esplicito per controllare quando si verifica il ripristino in modo che possano controllare l'utilizzo della rete. Per impedire l'esecuzione implicita di `dotnet restore`, è possibile usare l'opzione `--no-restore` con uno di questi comandi per disabilitare il ripristino implicito.

## <a name="arguments"></a>Argomenti

`ROOT`

Percorso facoltativo del file di progetto da ripristinare.

## <a name="options"></a>Opzioni

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--configfile <FILE>`

File di configurazione NuGet (*NuGet.config*) da usare per l'operazione di ripristino.

`--disable-parallel`

Disabilita il ripristino di più progetti in parallelo.

`--force`

Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. Ciò equivale a eliminare il file *project.assets.json*.

`-h|--help`

Stampa una breve guida per il comando.

`--ignore-failed-sources`

Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.

`--no-cache`

Specifica di non memorizzare nella cache pacchetti e richieste HTTP.

`--no-dependencies`

Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.

`--packages <PACKAGES_DIRECTORY>`

Specifica la directory per i pacchetti ripristinati.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Specifica un runtime per il ripristino dei pacchetti. Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Specificare più origini selezionando questa opzione più volte.

`-s|--source <SOURCE>`

Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino. Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*. È possibile specificare più origini, selezionando questa opzione più volte.

`--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--configfile <FILE>`

File di configurazione NuGet (*NuGet.config*) da usare per l'operazione di ripristino.

`--disable-parallel`

Disabilita il ripristino di più progetti in parallelo.

`-h|--help`

Stampa una breve guida per il comando.

`--ignore-failed-sources`

Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.

`--no-cache`

Specifica di non memorizzare nella cache pacchetti e richieste HTTP.

`--no-dependencies`

Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.

`--packages <PACKAGES_DIRECTORY>`

Specifica la directory per i pacchetti ripristinati.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Specifica un runtime per il ripristino dei pacchetti. Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Specificare più origini selezionando questa opzione più volte.

`-s|--source <SOURCE>`

Specifica un'origine dei pacchetti NuGet da usare durante l'operazione di ripristino. Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*. È possibile specificare più origini, selezionando questa opzione più volte.

`--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

## <a name="examples"></a>Esempi

Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:

`dotnet restore`

Ripristinare le dipendenze e gli strumenti per il progetto `app1` che si trova nel percorso specificato:

`dotnet restore ~/projects/app1/app1.csproj`

Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando il percorso di file specificato come origine:

`dotnet restore -s c:\packages\mypackages`

Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando i due percorsi di file specificati come origini:

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente e mostrare solo un output minimo:

`dotnet restore --verbosity minimal`
