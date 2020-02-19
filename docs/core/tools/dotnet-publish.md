---
title: Comando dotnet publish
description: Il comando dotnet publish consente di pubblicare il progetto .NET Core in una directory.
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451292"
---
# <a name="dotnet-publish"></a>dotnet publish

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet publish`: inserisce l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema host.

## <a name="synopsis"></a>Riepilogo

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Descrizione

`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory. L'output include gli asset seguenti:

- Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.
- File *.deps.json* che contiene tutte le dipendenze del progetto.
- File *.runtimeconfig.json* che specifica il runtime condiviso previsto dall'applicazione e altre opzioni di configurazione per il runtime, ad esempio il tipo di Garbage Collection.
- Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.

L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione. È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione. A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno. Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md). Per la struttura di directory di un'applicazione pubblicata, vedere [Directory structure](/aspnet/core/hosting/directory-structure) (Struttura di directory).

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argomenti

`PROJECT`

Progetto da pubblicare. Si tratta del percorso e del nome di un file di progetto [C#](csproj.md), F# o Visual Basic oppure del percorso di una directory contenente un file di progetto C#, F# o Visual Basic. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.

## <a name="options"></a>Opzioni

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato. È necessario specificare il framework di destinazione nel file di progetto.

`--force`

Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

`-h|--help`

Stampa una breve guida per il comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app. Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md). Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto. Questa opzione è disponibile a partire da .NET Core 2.0 SDK.

`--no-build`

Non compila il progetto prima della pubblicazione. Imposta anche in modo implicito il flag `--no-restore`.

`--no-dependencies`

Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.

`--no-restore`

Non esegue un ripristino implicito quando si esegue il comando.

`-o|--output <OUTPUT_DIRECTORY>`

Specifica il percorso della directory di output. Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.
Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.

`--self-contained`

Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione. Se viene specificato un identificatore di runtime, il valore predefinito è `true`. Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Pubblica l'applicazione per un determinato runtime. Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#publish-self-contained). Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#publish-runtime-dependent).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato. È necessario specificare il framework di destinazione nel file di progetto.

`--force`

Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

`-h|--help`

Stampa una breve guida per il comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app. Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md). Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto. Questa opzione è disponibile a partire da .NET Core 2.0 SDK.

`--no-dependencies`

Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.

`--no-restore`

Non esegue un ripristino implicito quando si esegue il comando.

`-o|--output <OUTPUT_DIRECTORY>`

Specifica il percorso della directory di output. Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.
Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.

`--self-contained`

Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione. Se viene specificato un identificatore di runtime, il valore predefinito è `true`. Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Pubblica l'applicazione per un determinato runtime. Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#publish-self-contained). Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#publish-runtime-dependent).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`.

`-f|--framework <FRAMEWORK>`

Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato. È necessario specificare il framework di destinazione nel file di progetto.

`-h|--help`

Stampa una breve guida per il comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app. Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md). Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto. Questa opzione è disponibile a partire da .NET Core 2.0 SDK.

`-o|--output <OUTPUT_DIRECTORY>`

Specifica il percorso della directory di output. Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.
Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Pubblica l'applicazione per un determinato runtime. Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#publish-self-contained). Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#publish-runtime-dependent).

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.

---

## <a name="examples"></a>Esempi

Pubblicare il progetto nella directory corrente:

`dotnet publish`

Pubblicare l'applicazione usando il file di progetto specificato:

`dotnet publish ~/projects/app1/app1.csproj`

Pubblicare il progetto nella directory corrente usando il framework `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`

Pubblicare l'applicazione corrente usando il framework `netcoreapp1.1` e il runtime per `OS X 10.10`. Questo identificatore di runtime deve essere elencato nel file di progetto.

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), soltanto il progetto radice durante l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):

`dotnet publish --no-dependencies`

## <a name="see-also"></a>Vedere anche

- [Framework di destinazione](../../standard/frameworks.md)
- [Catalogo RID (Runtime IDentifier)](../rid-catalog.md)
