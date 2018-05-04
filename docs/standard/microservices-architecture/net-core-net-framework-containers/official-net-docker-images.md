---
title: Immagini Docker .NET ufficiali
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Immagini Docker .NET ufficiali
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: adbe63a2d2f93819b5b29c6dd8d8089cd35ad2f3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="official-net-docker-images"></a>Immagini Docker .NET ufficiali

Le immagini Docker .NET ufficiali sono immagini Docker create e ottimizzate da Microsoft. Sono disponibili pubblicamente nei repository Microsoft nell'[hub Docker](https://hub.docker.com/u/microsoft/). Ogni repository può contenere più immagini, a seconda delle versioni di .NET e a seconda del sistema operativo e delle relative versioni, ad esempio Linux Debian, Linux Spline, Windows Nano Server, Windows Server Core e così via.

Lo scopo di Microsoft per i repository .NET è quello di avere repository granulari e mirati, dove ogni repository rappresenta uno specifico scenario o carico di lavoro. Ad esempio, le immagini [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) devono essere usate quando si usa ASP.NET Core in Docker, perché le immagini ASP.NET Core forniscono ottimizzazioni aggiuntive per avviare più velocemente i contenitori.

D'altra parte, le immagini .NET Core (microsoft/dotnet) sono destinate alle app console basate su .NET Core. I processi batch, Processi Web di Azure e altri scenari console devono usare le immagini .NET Core. Queste immagini non includono lo stack di ASP.NET Core e quindi l'immagine del contenitore risulta più piccola.

La maggior parte dei repository di immagini fornisce contrassegni completi che consentono di selezionare sia una versione specifica del framework che un sistema operativo (distribuzione di Linux o versione di Windows).

Per altre informazioni sulle immagini Docker .NET Core ufficiali fornite da Microsoft, vedere il [riepilogo delle immagini Docker .NET](https://aka.ms/dotnetdockerimages).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>Ottimizzazioni delle immagini .NET Core e Docker per lo sviluppo e la produzione

Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione sugli scenari principali seguenti:

-   Immagini usate per *sviluppare* e compilare app .NET Core.

-   Immagini usate per *eseguire* app .NET Core.

Perché sono disponibili più immagini? Durante lo sviluppo, la compilazione e l'esecuzione di applicazioni in contenitori, è necessario tenere conto di diverse priorità. Fornendo immagini diverse per queste attività separate, Microsoft consente di ottimizzare i processi per lo sviluppo, la compilazione e la distribuzione di app.

### <a name="during-development-and-build"></a>Durante lo sviluppo e la compilazione

Durante lo sviluppo, ciò che conta è la velocità di iterazione delle modifiche e la possibilità di eseguire il debug delle modifiche. Le dimensioni dell'immagine non sono importanti quanto la possibilità di apportare modifiche al codice e visualizzare rapidamente tali modifiche. Alcuni strumenti e i "contenitori dell'agente di compilazione" usano l'immagine ASP.NET Core (microsoft/aspnetcore-build) di sviluppo durante il processo di sviluppo e compilazione. Durante la compilazione all'interno di un contenitore Docker, gli aspetti importanti sono gli elementi necessari per compilare l'app. In particolare il compilatore e le eventuali altre dipendenze di .NET e le dipendenze dello sviluppo Web come npm, Gulp e Bower.

Perché questo tipo di immagine di compilazione è importante? Questa immagine non viene distribuita nell'ambiente di produzione. È piuttosto un'immagine usata per compilare il contenuto inserito in un'immagine di produzione. Questa immagine verrà usata nell'ambiente di integrazione continua o nell'ambiente di compilazione. Ad esempio, anziché installare manualmente tutte le dipendenze dell'applicazione direttamente in un host agente di compilazione, come una macchina virtuale, l'agente di compilazione creerà un'istanza dell'immagine di compilazione .NET Core con tutte le dipendenze necessarie per compilare l'applicazione. Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker. Questo semplifica l'ambiente di integrazione continua e lo rende molto più prevedibile.

### <a name="in-production"></a>In produzione

Ciò che conta nella produzione è quanto velocemente è possibile distribuire e avviare i contenitori basati su un'immagine .NET Core di produzione. Di conseguenza, l'immagine solo runtime basata su [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) è di piccole dimensioni in modo che possa attraversare velocemente la rete dal registro Docker agli host Docker. Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'avvio del contenitore e l'elaborazione dei risultati. Nel modello Docker, non è necessario eseguire la compilazione dal codice C\#, come quando si eseguono i comandi dotnet build o dotnet publish con il contenitore di compilazione.

In questa immagine ottimizzata si inseriscono solo i binari e altro contenuto necessari per eseguire l'applicazione. Ad esempio, il contenuto creato dal comando dotnet publish contiene solo i file JS e CSS, le immagini e i file binari .NET compilati. Nel corso del tempo si vedranno immagini contenenti pacchetti pre-JIT.

Anche se sono presenti più versioni delle immagini .NET Core e ASP.NET Core, tutte queste versioni condividono uno o più livelli, incluso il livello di base. La quantità di spazio su disco necessaria per archiviare un'immagine è quindi ridotta ed è formata solo dal valore differenziale tra l'immagine personalizzata e l'immagine di base. Ne consegue quindi che il pull dell'immagine dal registro è veloce.

Durante l'esplorazione dei repository di immagini .NET nell'hub Docker, si troveranno più versioni delle immagini classificate o contrassegnate con tag. Questi tag consentono di decidere l'immagine da usare a seconda della versione necessaria, come quelle nella tabella seguente:

-   microsoft/**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   microsoft/**aspnetcore-build:2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[Indietro] (net-container-os-targets.md) [Avanti] (../architect-microservice-container-applications/index.md)
