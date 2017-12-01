---
title: Immagini Docker .NET ufficiale
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Immagini Docker .NET ufficiale
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a>Immagini Docker .NET ufficiale

Le immagini Docker .NET ufficiale sono immagini Docker creati e ottimizzati da Microsoft. Sono disponibili pubblicamente in repository Microsoft su [Hub Docker](https://hub.docker.com/u/microsoft/). Ogni archivio può contenere più immagini, a seconda delle versioni di .NET e il sistema operativo e le versioni (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core e così via).

La visione Microsoft per i repository .NET è repository granulare e sono specifici, in un repository rappresenta uno scenario specifico o un carico di lavoro. Ad esempio, il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagini devono essere utilizzate quando usando ASP.NET Core in Docker, poiché tali immagini ASP.NET Core offrono ulteriori ottimizzazioni contenitori in questo caso è possibile avviare più velocemente.

D'altra parte, le immagini di .NET Core (microsoft/dotnet) sono progettate per le applicazioni di console basate su .NET Core. Ad esempio, i processi batch, i processi Web di Azure e altri scenari di console devono utilizzare .NET Core. Tali immagini non includono lo stack ASP.NET Core, risultante in un'immagine contenitore più piccolo.

La maggior parte dei repository di immagini forniscono tag completo che consentono di selezionare non solo una versione di framework specifico, ma anche per scegliere un sistema operativo (versione di Windows o Linux distro).

Per ulteriori informazioni sulle immagini Docker .NET ufficiale fornito da Microsoft, vedere il [riepilogo immagini Docker .NET](https://aka.ms/dotnetdockerimages).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Ottimizzazioni di immagine .NET core e Docker per lo sviluppo e produzione

Quando si compila immagini Docker per gli sviluppatori, Microsoft è incentrata su scenari principali seguenti:

-   Le immagini utilizzate per *sviluppare* e creazione di applicazioni .NET Core.

-   Le immagini utilizzate per *eseguire* app .NET Core.

Perché più immagini? Durante lo sviluppo, compilazione e l'esecuzione di applicazioni nei contenitori, è in genere in base alla priorità. Fornendo immagini differenti per queste attività distinte, Microsoft consente di ottimizzare i processi di sviluppo, compilazione e distribuzione di applicazioni separati.

### <a name="during-development-and-build"></a>Durante lo sviluppo e compilazione

Durante lo sviluppo, aspetto importante è la velocità con cui è possibile scorrere le modifiche e la possibilità di eseguire il debug delle modifiche. Le dimensioni dell'immagine non sono importante quanto la possibilità di apportare modifiche al codice e visualizzare rapidamente le modifiche. Alcuni strumenti e i "contenitori agente di compilazione" Usa lo sviluppo immagine ASP.NET di base (microsoft/aspnetcore-compilazione) durante lo sviluppo e processo di compilazione. Quando si compila in un contenitore Docker, gli aspetti importanti sono gli elementi necessari per compilare l'app. Ciò include il compilatore e Gulp ed eventuali altre dipendenze di .NET, più dipendenze, lo sviluppo web quali npm, Bower.

Perché questo tipo di immagine di compilazione è importante? Non si distribuirla questa immagine nell'ambiente di produzione. Si tratta invece di un'immagine da utilizzare per compilare il contenuto che si inserisce in un'immagine di produzione. Questa immagine potrebbe essere utilizzata in un ambiente di integrazione continua (CI) o di un ambiente di compilazione. Ad esempio, anziché l'installazione manuale di tutte le dipendenze dell'applicazione direttamente su un agente di compilazione host (ad esempio VM), l'agente di compilazione creerebbe un'istanza di un'immagine di compilazione .NET Core con tutte le dipendenze necessarie per compilare l'applicazione. Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker. Questo semplifica l'ambiente CI e rende molto più prevedibili.

### <a name="in-production"></a>Nell'ambiente di produzione

È importante nell'ambiente di produzione è la velocità con cui è possibile distribuire e avviare i contenitori basati su un'immagine .NET Core di produzione. Pertanto, in base l'immagine solo runtime [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) è ridotto in modo che è possibile spostare rapidamente in rete dal Registro di sistema Docker per gli host Docker. Il contenuto è pronto per l'esecuzione, consentendo l'ora più veloce dall'avvio del contenitore per l'elaborazione dei risultati. Nel modello di Docker, non è necessario per la compilazione da C\# il codice, come quando si esegue la compilazione dotnet o dotnet pubblicare quando utilizza il contenitore della build.

In questa immagine ottimizzata vengono inseriti solo i file binari e altri contenuti necessari per eseguire l'applicazione. Ad esempio, di pubblicare il contenuto creato da dotnet contiene solo i file binari compilati .NET, immagini, js e file CSS. Nel corso del tempo, si noterà immagini che contengono pacchetti preJit.

Anche se sono presenti più versioni di .NET Core e ASP.NET Core immagini, condividono uno o più livelli, tra cui il livello di base. Pertanto, la quantità di spazio su disco necessario per archiviare un'immagine è di piccole dimensioni è costituito solo il delta tra l'immagine personalizzata e l'immagine di base. Il risultato è che è più veloce effettuare il pull dell'immagine dal Registro di sistema.

Quando si Esplora il repository di immagini .NET hub Docker, sono disponibili più versioni di immagine classificati o contrassegnato con tag. Questi tag utili per decidere quale utilizzare, a seconda della versione che è necessario, ad esempio quelli riportati nella tabella seguente:

-   Microsoft /**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   Microsoft /**aspnetcore-compilazione: 2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[Precedente] (net-contenitore-os-targets.md) [Avanti] (... /Architect-microservice-Container-Applications/index.MD)
