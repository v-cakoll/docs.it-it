---
title: Architettura degli strumenti della riga di comando di .NET Core
description: Informazioni sui livelli degli strumenti di .NET Core e sulle modifiche apportate nelle versioni più recenti.
ms.date: 03/06/2017
ms.openlocfilehash: e1a9fe59225c17d54f6e7213d2b3c3fa70ee58e0
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102879"
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a>Panoramica generale delle modifiche agli strumenti di .NET Core

Questo documento descrive le modifiche associate al passaggio da *project.json* a MSBuild e al sistema di progetti *csproj* con informazioni sulle modifiche ai livelli degli strumenti .NET Core e all'implementazione dei comandi dell'interfaccia della riga di comando. Queste modifiche sono state introdotte con il rilascio di .NET Core SDK 1.0 e Visual Studio 2017 il 7 marzo 2017 (vedere l'[annuncio](https://devblogs.microsoft.com/dotnet/announcing-net-core-tools-1-0/)), ma sono state implementate inizialmente con il rilascio di .NET Core SDK Preview 3.

## <a name="moving-away-from-projectjson"></a>Abbandono di project.json

Il cambiamento più significativo negli strumenti di .NET Core è il [passaggio da project.json a csproj](https://devblogs.microsoft.com/dotnet/changes-to-project-json/) come sistema di progetto. Le versioni più recenti degli strumenti da riga di comando non supportano i file *project.json*. Ciò significa che non può essere utilizzato per compilare, eseguire o pubblicare applicazioni e librerie basate su project.json. Per utilizzare questa versione degli strumenti, eseguire la migrazione dei progetti esistenti o crearne di nuovi.

Come parte di questo passaggio, il motore di compilazione personalizzato sviluppato per i progetti project.json è stato sostituito da un motore di compilazione maturo e dotato di funzionalità complete denominato [MSBuild](https://github.com/Microsoft/msbuild). MSBuild è un motore noto nella community di .NET. È stata una tecnologia chiave fin dalla prima versione della piattaforma. Poiché è necessario compilare applicazioni .NET Core, MSBuild è stato portato in .NET Core e può essere utilizzato su qualsiasi piattaforma in cui viene eseguito .NET Core. Una delle promesse principali di .NET Core è la realizzazione di uno stack di sviluppo multipiattaforma, e Microsoft ha mantenuto tale promessa.

> [!TIP]
> Se non si ha familiarità con MSBuild e si desidera ottenere ulteriori informazioni, è possibile iniziare leggendo l'articolo sui concetti di [MSBuild.If](/visualstudio/msbuild/msbuild-concepts) you are new to MSBuild and would to learn more about it, you can start by reading the MSBuild concepts article.

## <a name="the-tooling-layers"></a>Livelli degli strumenti

Con il cambiamento nel motore di compilazione e l'allontanarsi dal sistema di progetto esistente, alcune domande naturalmente seguono. Una di queste modifiche modifica la "stratificazione" complessiva dell'ecosistema degli strumenti di .NET Core? Esistono nuovi elementi e componenti?

Nella figura seguente viene fornito un breve riepilogo dei livelli dell'anteprima 2:

![Architettura di alto livello degli strumenti dell'anteprima 2](media/cli-msbuild-architecture/p2-arch.png)

La stratificazione degli strumenti in Anteprima 2 è semplice. Nella parte inferiore, la base è l'interfaccia della riga di comando di .NET Core. Tutti gli altri strumenti di livello superiore, ad esempio Visual Studio o Visual Studio Code, dipendono e si basano sull'interfaccia della riga di comando per compilare progetti, ripristinare le dipendenze e così via. Ad esempio, se Visual Studio desidera eseguire un'operazione `dotnet restore` di ripristino, chiamerebbe il comando nell'interfaccia della riga di comando.

Con il passaggio al nuovo sistema di progetto, il diagramma precedente risulta modificato nel modo illustrato di seguito:

![Architettura di alto livello di .NET Core SDK 1.0.0](media/cli-msbuild-architecture/p3-arch.png)

La differenza principale è che l'interfaccia della riga di comando non è più il livello di base. Tale ruolo viene ora svolto dal "componente SDK condiviso". Questo componente SDK condiviso è un set di destinazioni e attività associate responsabili della compilazione del codice, della pubblicazione, della creazione di pacchetti NuGet e così via. .NET Core SDK è open source ed è disponibile in GitHub nel [repository SDK.](https://github.com/dotnet/sdk)

> [!NOTE]
> Una "destinazione" è un termine MSBuild che indica un'operazione denominata che MSBuild può richiamare. La destinazione è in genere associata a una o più attività che eseguono la logica dell'operazione. MSBuild supporta diverse destinazioni predefinite, ad esempio `Copy` o `Execute`. Consente inoltre agli utenti di scrivere le proprie attività usando codice gestito e definire destinazioni per eseguire tali attività. Per altre informazioni, vedere [Attività di MSBuild](/visualstudio/msbuild/msbuild-tasks).

Tutti i set di strumenti, inclusa l'interfaccia della riga di comando, utilizzano ora il componente SDK condiviso e le relative destinazioni. Ad esempio, Visual Studio 2019 non `dotnet restore` chiama il comando per ripristinare le dipendenze per i progetti .NET Core.For example, Visual Studio 2019 doesn't call into the command to restore dependencies for .NET Core projects. Al contrario, utilizza direttamente la destinazione "Ripristina". Poiché si tratta di destinazioni MSBuild, è anche possibile usare direttamente MSBuild per eseguirle mediante il comando [dotnet-msbuild](dotnet-msbuild.md).

### <a name="cli-commands"></a>Comandi dell'interfaccia della riga di comando

Il componente SDK condiviso significa che la maggior parte dei comandi DELL-interfaccia della riga di comando esistenti sono stati reimplementati come attività e destinazioni MSBuild. Cosa significa questo per i comandi dell'interfaccia della riga di comando e per l'utilizzo del set di strumenti?

Dal punto di vista dell'utilizzo, non cambia il modo in cui si usa l'interfaccia della riga di comando. L'interfaccia della riga di comando contiene ancora i comandi di base esistenti nella versione di .NET Core 1.0 Preview 2:The CLI still has the core commands that existed in the .NET Core 1.0 Preview 2 release:

- `new`
- `restore`
- `run`
- `build`
- `publish`
- `test`
- `pack`

Questi comandi fanno ancora quello che ti aspetti che facciano (nuovo un progetto, compilarlo, pubblicarlo, imballare e così via). È possibile consultare la schermata `dotnet <command> --help`di aiuto del comando (utilizzando ) o la documentazione su questo sito per acquisire familiarità con il loro comportamento.

Dal punto di vista dell'esecuzione, i comandi dell'interfaccia della riga di comando accettano i parametri e creano una chiamata a MSBuild "non elaborato" che imposta le proprietà necessarie ed esegue la destinazione desiderata. Per comprendere meglio quanto esposto sopra, prendere in considerazione il comando seguente:

   ```dotnetcli
   dotnet publish -o pub -c Release
   ```

Questo comando pubblica un'applicazione `pub` in una cartella utilizzando la configurazione "Release". A livello interno, il comando viene tradotto nella chiamata a MSBuild seguente:

   ```dotnetcli
   dotnet msbuild -t:Publish -p:OutputPath=pub -p:Configuration=Release
   ```

Eccezioni degne di `new` nota a questa regola sono i comandi e `run` . Non sono stati implementati come destinazioni MSBuild.

### <a name="implicit-restore"></a>Ripristino implicito

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
