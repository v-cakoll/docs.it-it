---
title: Architettura degli strumenti della riga di comando di .NET Core
description: Informazioni sui livelli degli strumenti di .NET Core e sulle modifiche apportate nelle versioni più recenti.
author: blackdwarf
ms.date: 03/06/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 909e3ba088a3eabededf008fa07a51ac7d677fa2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a>Panoramica generale delle modifiche agli strumenti di .NET Core

Questo documento descrive le modifiche associate al passaggio da *project.json* a MSBuild e al sistema di progetti *csproj* con informazioni sulle modifiche ai livelli degli strumenti .NET Core e all'implementazione dei comandi dell'interfaccia della riga di comando. Queste modifiche sono state introdotte con il rilascio di .NET Core SDK 1.0 e Visual Studio 2017 il 7 marzo 2017 (vedere l'[annuncio](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)), ma sono state implementate inizialmente con il rilascio di .NET Core SDK Preview 3.

## <a name="moving-away-from-projectjson"></a>Abbandono di project.json
Il cambiamento più significativo negli strumenti di .NET Core è il [passaggio da project.json a csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) come sistema di progetto. Le versioni più recenti degli strumenti da riga di comando non supportano i file *project.json*. Questo significa che non può essere usata per creare, eseguire o pubblicare applicazioni e librerie basate su project.json. Per usare questa versione degli strumenti, è necessario eseguire la migrazione dei progetti esistenti o avviarne di nuovi. 

Come parte di questo passaggio, il motore di compilazione personalizzato sviluppato per i progetti project.json è stato sostituito da un motore di compilazione maturo e dotato di funzionalità complete denominato [MSBuild](https://github.com/Microsoft/msbuild). MSBuild è un motore noto nella community .NET: è stato infatti una tecnologia fondamentale fin dalla prima versione della piattaforma. Naturalmente, poiché è necessario per la compilazione di applicazioni .NET Core, MSBuild è stato portato in .NET Core e può essere usato su qualsiasi piattaforma in cui viene eseguito .NET Core. Una delle promesse principali di .NET Core è la realizzazione di uno stack di sviluppo multipiattaforma, e Microsoft ha mantenuto tale promessa.

> [!NOTE]
> Se non si ha familiarità con MSBuild e per altre informazioni su MSBuild, leggere l'articolo [MSBuild Concepts](/visualstudio/msbuild/msbuild-concepts) (Concetti relativi a MSBuild). 

## <a name="the-tooling-layers"></a>Livelli degli strumenti
Con l'abbandono del sistema di progetto esistente e dei commutatori del motore di compilazione, la domanda da porsi è la seguente: uno qualsiasi di questi cambiamenti modificherà i livelli complessivi dell'ecosistema degli strumenti .NET Core? Esistono nuovi elementi e componenti?

Nella figura seguente viene fornito un breve riepilogo dei livelli dell'anteprima 2:

![Architettura di alto livello degli strumenti dell'anteprima 2](media/cli-msbuild-architecture/p2-arch.png)

L'organizzazione su più livelli degli strumenti è piuttosto semplice. Al livello più basso, come base, si trovano gli strumenti della riga di comando di .NET Core. Tutti gli altri strumenti di livello più alto, ad esempio Visual Studio o Visual Studio Code, dipendono e si basano sull'interfaccia della riga di comando per la compilazione dei progetti, il ripristino delle dipendenze e così via. Ad esempio, questo significa che, se Visual Studio voleva eseguire un'operazione di ripristino, doveva chiamare il comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) nell'interfaccia della riga di comando. 

Con il passaggio al nuovo sistema di progetto, il diagramma precedente risulta modificato nel modo illustrato di seguito: 

![Architettura di alto livello di .NET Core SDK 1.0.0](media/cli-msbuild-architecture/p3-arch.png)

La differenza principale è che l'interfaccia della riga di comando non è più il livello di base. Tale ruolo viene ora svolto dal "componente SDK condiviso". Questo componente SDK condiviso è un set di destinazioni e attività associate responsabili della compilazione e della pubblicazione del codice, della creazione di pacchetti NuGet e così via. L'SDK stesso è open source ed è disponibile in GitHub nel [repository SDK](https://github.com/dotnet/sdk). 

> [!NOTE]
> "Destinazione" è un termine di MSBuild che indica un'operazione denominata che può essere richiamata da MSBuild. La destinazione è in genere associata a una o più attività che eseguono la logica dell'operazione. MSBuild supporta diverse destinazioni predefinite, ad esempio `Copy` o `Execute`. Consente inoltre agli utenti di scrivere le proprie attività usando codice gestito e definire destinazioni per eseguire tali attività. Per altre informazioni, vedere [Attività di MSBuild](/visualstudio/msbuild/msbuild-tasks). 

Tutti i set di strumenti, inclusa l'interfaccia della riga di comando, utilizzano ora il componente SDK condiviso e le relative destinazioni. Ad esempio, la prossima versione di Visual Studio non chiamerà il comando `dotnet restore` ([vedere la nota](#dotnet-restore-note)) per ripristinare le dipendenze per i progetti .NET Core, ma userà direttamente la destinazione "Restore". Poiché si tratta di destinazioni MSBuild, è anche possibile usare direttamente MSBuild per eseguirle mediante il comando [dotnet-msbuild](dotnet-msbuild.md). 

### <a name="cli-commands"></a>Comandi dell'interfaccia della riga di comando
Con l'introduzione del componente SDK condiviso, la maggior parte dei comandi dell'interfaccia della riga di comando esistenti sono stati reimplementati come attività e destinazioni MSBuild. Cosa significa questo per i comandi dell'interfaccia della riga di comando e per l'utilizzo del set di strumenti? 

La modalità di utilizzo dell'interfaccia della riga di comando non viene modificata. Nell'interfaccia della riga di comando sono infatti ancora disponibili i comandi base presenti nell'anteprima 2:

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

Questi comandi consentono di eseguire le stesse operazioni di prima, ad esempio creare un progetto, compilarlo, pubblicarlo, crearne un pacchetto e così via. La maggior parte delle opzioni non è stata modificata. Per acquisire familiarità con le modifiche, vedere le schermate della Guida dei comandi (usando `dotnet <command> --help`) o la documentazione in questo sito. 

Dal punto di vista dell'esecuzione, i comandi dell'interfaccia della riga di comando accetteranno i parametri e invieranno una chiamata diretta a MSBuild. Quest'ultimo imposterà le proprietà necessarie ed eseguirà la destinazione desiderata. Per comprendere meglio quanto esposto sopra, prendere in considerazione il comando seguente: 

   `dotnet publish -o pub -c Release`
    
Questo comando pubblica un'applicazione in una cartella `pub` usando la configurazione "Release". A livello interno, il comando viene tradotto nella chiamata a MSBuild seguente: 

   `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

La principale eccezione a questa regola sono i comandi `new` e `run`, che non sono stati implementati come destinazioni MSBuild.

<a name="dotnet-restore-note"></a> [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]