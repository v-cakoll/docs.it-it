---
title: Architettura degli strumenti della riga di comando di .NET Core
description: Informazioni sui livelli degli strumenti di .NET Core e sulle modifiche apportate nelle versioni più recenti.
ms.date: 03/06/2017
ms.openlocfilehash: 0064e7354f073be618bcf6a79962ab495927fadd
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980210"
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a>Panoramica generale delle modifiche agli strumenti di .NET Core

Questo documento descrive le modifiche associate al passaggio da *project.json* a MSBuild e al sistema di progetti *csproj* con informazioni sulle modifiche ai livelli degli strumenti .NET Core e all'implementazione dei comandi dell'interfaccia della riga di comando. Queste modifiche sono state introdotte con il rilascio di .NET Core SDK 1.0 e Visual Studio 2017 il 7 marzo 2017 (vedere l'[annuncio](https://devblogs.microsoft.com/dotnet/announcing-net-core-tools-1-0/)), ma sono state implementate inizialmente con il rilascio di .NET Core SDK Preview 3.

## <a name="moving-away-from-projectjson"></a>Abbandono di project.json

Il cambiamento più significativo negli strumenti di .NET Core è il [passaggio da project.json a csproj](https://devblogs.microsoft.com/dotnet/changes-to-project-json/) come sistema di progetto. Le versioni più recenti degli strumenti da riga di comando non supportano i file *project.json*. Ciò significa che non può essere usato per compilare, eseguire o pubblicare applicazioni e librerie basate su Project. JSON. Per usare questa versione degli strumenti, eseguire la migrazione dei progetti esistenti o avviarne di nuovi.

Come parte di questo passaggio, il motore di compilazione personalizzato sviluppato per i progetti project.json è stato sostituito da un motore di compilazione maturo e dotato di funzionalità complete denominato [MSBuild](https://github.com/Microsoft/msbuild). MSBuild è un motore noto nella community di .NET. Si tratta di una tecnologia fondamentale rispetto alla prima versione della piattaforma. Poiché è necessario compilare applicazioni .NET Core, MSBuild è stato trasferito a .NET Core e può essere usato su qualsiasi piattaforma su cui è in esecuzione .NET Core. Una delle promesse principali di .NET Core è la realizzazione di uno stack di sviluppo multipiattaforma, e Microsoft ha mantenuto tale promessa.

> [!TIP]
> Se non si ha familiarità con MSBuild e si desidera ottenere altre informazioni, è possibile iniziare leggendo i [concetti relativi a MSBuild](/visualstudio/msbuild/msbuild-concepts) .

## <a name="the-tooling-layers"></a>Livelli degli strumenti

Con l'abbandono del sistema di progetto esistente e dei commutatori del motore di compilazione, la domanda da porsi è la seguente: uno qualsiasi di questi cambiamenti modificherà i livelli complessivi dell'ecosistema degli strumenti .NET Core? Esistono nuovi elementi e componenti?

Nella figura seguente viene fornito un breve riepilogo dei livelli dell'anteprima 2:

![Architettura di alto livello degli strumenti dell'anteprima 2](media/cli-msbuild-architecture/p2-arch.png)

L'organizzazione su più livelli degli strumenti è piuttosto semplice. Nella parte inferiore, la base è la interfaccia della riga di comando di .NET Core. Tutti gli altri strumenti di livello più alto, ad esempio Visual Studio o Visual Studio Code, dipendono e si basano sull'interfaccia della riga di comando per compilare progetti, ripristinare le dipendenze e così via. Ad esempio, se Visual Studio voleva eseguire un'operazione di ripristino, eseguirebbe la chiamata nel comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) nell'interfaccia della riga di comando.

Con il passaggio al nuovo sistema di progetto, il diagramma precedente risulta modificato nel modo illustrato di seguito:

![Architettura di alto livello di .NET Core SDK 1.0.0](media/cli-msbuild-architecture/p3-arch.png)

La differenza principale è che l'interfaccia della riga di comando non è più il livello di base. Tale ruolo viene ora svolto dal "componente SDK condiviso". Questo componente SDK condiviso è un set di destinazioni e attività associate responsabili della compilazione del codice, della pubblicazione, della compressione dei pacchetti NuGet e così via. Il .NET Core SDK è open source ed è disponibile in GitHub nel [repository SDK](https://github.com/dotnet/sdk).

> [!NOTE]
> Una "destinazione" è un termine di MSBuild che indica un'operazione denominata che MSBuild può richiamare. La destinazione è in genere associata a una o più attività che eseguono la logica dell'operazione. MSBuild supporta diverse destinazioni predefinite, ad esempio `Copy` o `Execute`. Consente inoltre agli utenti di scrivere le proprie attività usando codice gestito e definire destinazioni per eseguire tali attività. Per altre informazioni, vedere [Attività di MSBuild](/visualstudio/msbuild/msbuild-tasks).

Tutti i set di strumenti, inclusa l'interfaccia della riga di comando, utilizzano ora il componente SDK condiviso e le relative destinazioni. Ad esempio, Visual Studio 2019 non chiama il comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) per ripristinare le dipendenze per i progetti .NET Core. Viene invece utilizzata direttamente la destinazione "Restore". Poiché si tratta di destinazioni MSBuild, è anche possibile usare direttamente MSBuild per eseguirle mediante il comando [dotnet-msbuild](dotnet-msbuild.md).

### <a name="cli-commands"></a>Comandi dell'interfaccia della riga di comando

Con l'introduzione del componente SDK condiviso, la maggior parte dei comandi dell'interfaccia della riga di comando esistenti sono stati reimplementati come attività e destinazioni MSBuild. Cosa significa questo per i comandi dell'interfaccia della riga di comando e per l'utilizzo del set di strumenti?

Dal punto di vista dell'utilizzo, non cambia il modo in cui si usa l'interfaccia della riga di comando. L'interfaccia della riga di comando contiene ancora i comandi di base esistenti nella versione di .NET Core 1,0 Preview 2:

- `new`
- `restore`
- `run`
- `build`
- `publish`
- `test`
- `pack`

Questi comandi eseguono ancora le operazioni che si prevede di eseguire (nuovo progetto, compilazione, pubblicazione, compressione e così via). È possibile consultare la schermata della guida del comando (usando `dotnet <command> --help`) o la documentazione di questo sito per acquisire familiarità con il proprio comportamento.

Dal punto di vista dell'esecuzione, i comandi dell'interfaccia della riga di comando accettano i parametri e creano una chiamata a MSBuild "Raw" che imposta le proprietà necessarie ed esegue la destinazione desiderata. Per comprendere meglio quanto esposto sopra, prendere in considerazione il comando seguente:

   ```dotnetcli
   dotnet publish -o pub -c Release
   ```

Questo comando pubblica un'applicazione in una cartella `pub` usando la configurazione "release". A livello interno, il comando viene tradotto nella chiamata a MSBuild seguente:

   ```dotnetcli
   dotnet msbuild -t:Publish -p:OutputPath=pub -p:Configuration=Release
   ```

Le eccezioni rilevanti a questa regola sono i comandi `new` e `run`. Non sono state implementate come destinazioni MSBuild.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
