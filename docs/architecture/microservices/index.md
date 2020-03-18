---
title: Microservizi .NET. Architettura per le applicazioni .NET incluse in contenitori
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | I microservizi sono servizi modulari e distribuibili in modo indipendente. I contenitori Docker (per Linux e Windows) semplificano le attività di distribuzione e test riunendo un servizio e le relative dipendenze in una singola unità che viene quindi eseguita in un ambiente isolato.
ms.date: 01/30/2020
ms.openlocfilehash: 1337fe56e78e03a85627737bd52a089fd946b842
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77543534"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a>Microservizi .NET: architettura per le applicazioni .NET incluse in contenitori

![Copertina](./media/cover-small.png)

**EDITION v3.1** - Aggiornato per ASP.NET Core 3.1

Questa guida offre un'introduzione allo sviluppo di applicazioni basate su microservizi e alla relativa gestione tramite i contenitori. Vengono descritti gli approcci alla progettazione e all'implementazione dell'architettura mediante i contenitori di .NET Core e Docker.

Per rendere più semplice iniziare, la guida illustra un'applicazione di riferimento basata su microservizi e inclusa in un contenitore che è possibile esplorare. L'applicazione di riferimento è disponibile nel repository GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

## <a name="action-links"></a>Collegamenti all'azione

- Questo e-book è disponibile anche in formato PDF (solo versione inglese) [Scarica](https://aka.ms/microservicesebook)

- Clonare o eseguire il fork dell'applicazione di riferimento [eShopOnContainers su GitHub](https://github.com/dotnet-architecture/eShopOnContainers)

- Guardare il [video introduttivo su Channel 9](https://aka.ms/microservices-video)

- Ottenere immediatamente informazioni sull'[architettura di microservizi](https://aka.ms/MicroservicesArchitecture)

## <a name="introduction"></a>Introduzione

Sempre più spesso nelle aziende vengono usati i contenitori per realizzare risparmi sui costi, risolvere i problemi di distribuzione e migliorare DevOps e operazioni di produzione. Microsoft ha introdotto innovazioni dei contenitori per Windows e Linux tramite la creazione di prodotti come il servizio Azure Kubernetes e Azure Service Fabric, oltre che attraverso la collaborazione con aziende leader del settore come Docker, Mesosphere e Kubernetes. Questi prodotti offrono soluzioni per i contenitori che consentono alle aziende di creare e distribuire le applicazioni con la velocità e la scalabilità del cloud, indipendentemente dalla piattaforma o dagli strumenti scelti.

Docker sta diventando lo standard di fatto nel settore dei contenitori, supportato dai più significativi fornitori negli ecosistemi Windows e Linux (Microsoft è uno dei principali fornitori di cloud che supportano Docker.) In futuro, Docker sarà probabilmente onnipresente in qualsiasi data center nel cloud o in locale.

Inoltre, l'architettura dei [microservizi](https://martinfowler.com/articles/microservices.html) sta emergendo come un importante approccio alle applicazioni distribuite di importanza strategica. In un'architettura basata su microservizi, l'applicazione si basa su una raccolta di servizi che possono essere sviluppati, testati, distribuiti e sottoposti a controllo della versione in modo indipendente.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida offre un'introduzione allo sviluppo di applicazioni basate su microservizi e alla relativa gestione tramite i contenitori. Vengono descritti gli approcci alla progettazione e all'implementazione dell'architettura mediante i contenitori di .NET Core e Docker. Per rendere più semplice iniziare a usare i contenitori e i microservizi, la guida illustra un'applicazione di riferimento basata su microservizi e inclusa in un contenitore che è possibile esplorare. L'applicazione di esempio è disponibile nel repository GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

Questa guida fornisce indicazioni di base per lo sviluppo e l'architettura principalmente a livello di ambiente di sviluppo, con particolare attenzione per due tecnologie: Docker e .NET Core. La guida dovrebbe essere letta al momento di valutare la progettazione dell'applicazione, senza considerare l'infrastruttura (cloud o locale) dell'ambiente di produzione. Sarà possibile prendere le decisioni relative all'infrastruttura in un secondo momento, durante la creazione delle applicazioni di produzione. Pertanto, questa guida è pensata per essere indipendente dall'infrastruttura e maggiormente incentrata sull'ambiente di sviluppo.

Dopo aver consultato questa guida, il passaggio successivo sarà acquisire informazioni sui microservizi disponibili per la produzione in Microsoft Azure.

## <a name="version"></a>Versione

Questa guida è stata rivista per coprire la versione **.NET Core 3.1** insieme a molti aggiornamenti aggiuntivi correlati alla stessa "onda" di tecnologie (vale a dire, Azure e tecnologie di terze parti aggiuntive) che colazzano in tempo con la versione 3.1 di .NET Core. Ecco perché la versione del libro è stata aggiornata anche alla versione **3.1**.

## <a name="what-this-guide-does-not-cover"></a>Argomenti non trattati dalla guida

Questa guida non tratta gli argomenti relativi a ciclo di vita delle applicazioni, DevOps, pipeline CI/CD o lavoro in team. La guida complementare [Ciclo di vita delle applicazioni Docker incluse in contenitori con la piattaforma e gli strumenti Microsoft](https://aka.ms/dockerlifecycleebook) è dedicata a tali argomenti. La presente guida inoltre non contiene i dettagli relativi all'implementazione nell'infrastruttura Azure, ad esempio le informazioni sugli specifici agenti di orchestrazione.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft** (e-book scaricabile)  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a>Destinatari della guida

Questa guida è stata scritta per gli sviluppatori e gli architetti di soluzioni che non hanno familiarità con lo sviluppo di applicazioni basate su Docker e l'architettura basata su microservizi. La guida è destinata ai professionisti che vogliono sapere come progettare e implementare applicazioni di prova con le tecnologie di sviluppo Microsoft (con particolare attenzione per .NET Core) e i contenitori Docker.

Questa guida è inoltre utile per i responsabili decisionali tecnici, ad esempio gli Enterprise Architect, che hanno bisogno di una panoramica dell'architettura e della tecnologia prima di decidere quale approccio scegliere per le applicazioni distribuite nuove e moderne.

### <a name="how-to-use-this-guide"></a>Come usare questa guida

Nella prima parte della guida vengono presentati i contenitori Docker, viene illustrato come scegliere tra .NET Core e .NET Framework come framework di sviluppo e viene fornita una panoramica dei microservizi. Questo contenuto è destinato ai progettisti e ai responsabili decisionali tecnici che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione del codice.

La seconda parte della guida inizia con la sezione [Processo di sviluppo per le applicazioni basate su Docker](./docker-application-development-process/index.md). Si concentra sullo sviluppo e sui modelli dei microservizi per l'implementazione di applicazioni tramite .NET Core e Docker. Questa sezione sarà di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sul codice e sui dettagli relativi a modelli e implementazione.

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a>Applicazione di riferimento correlata basata su microservizi e contenitori: eShopOnContainers

L'applicazione eShopOnContainers è un'applicazione open-source di riferimento per .NET Core e i microservizi, progettata per la distribuzione mediante i contenitori Docker. L'applicazione è costituita da più sottosistemi, inclusi diversi front-end con interfaccia utente per negozi online (un'app Web MVC, un'applicazione Web a pagina singola e un'app per dispositivi mobili nativa). Include inoltre i microservizi e i contenitori back-end per tutte le operazioni lato server necessarie.

Lo scopo dell'applicazione consiste nel presentare i modelli di architettura. **NON È UN MODELLO DA USARE IN PRODUZIONE** per avviare applicazioni reali. Di fatto, l'applicazione è in uno stato beta permanente, perché viene usata anche per testare le nuove tecnologie potenzialmente interessanti quando diventano disponibili.

## <a name="send-us-your-feedback"></a>Inviateci i vostri commenti!

Questa guida è stata scritta per aiutare il lettore a comprendere l'architettura delle applicazioni incluse in contenitori e dei microservizi in .NET. La guida e l'applicazione di riferimento correlata sono in evoluzione, pertanto qualsiasi commento è molto apprezzato. Se hai commenti su come migliorare questa guida, <https://aka.ms/ebookfeedback>invia un feedback all'indirizzo .

## <a name="credits"></a>Credits

Coautori:

> **Cesar de la Torre**, Senior PM, team del prodotto .NET, Microsoft Corp.
>
> **Bill Wagner**, Senior Content Developer, C+E, Microsoft Corp.
>
> **Mike Rousos**, Principal Software Engineer, team DevDiv CAT, Microsoft

Editor:

> **Mike Pope**
>
> **Steve Hoag**

Collaboratori e revisori:

> **Jeffrey Richter**, Partner Software Eng, team di Azure, Microsoft
>
> **Jimmy Bogard**, Chief Architect di Headspring
>
> **Udi Dahan**, fondatore e CEO di Particular Software
>
> **Jimmy Nilsson**, cofondatore e CEO di Factor10
>
> **Glenn Condron**, Senior Program Manager, team di ASP.NET
>
> **Mark Fussell**, Principal PM Lead, team di Azure Service Fabric, Microsoft
>
> **Diego Vega**, PM Lead, team di Entity Framework, Microsoft
>
> **Barry Dorrans**, Senior Security Program Manager
>
> **Rowan Miller**, Senior Program Manager, Microsoft
>
> **Ankit Asthana**, Principal PM Manager, team di .NET, Microsoft
>
> **Scott Hunter**, Partner Director PM, team di .NET, Microsoft
>
> **Nish Anil**, Senior Program Manager, team di .NET, Microsoft
>
> **Dylan Reisenberger**, Architect and Dev Lead di Polly
>
> **Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)
>
> **Ian Cooper**, Coding Architect di Brighter
>
> **Unai Zorrilla**, Architect and Dev Lead di Plain Concepts
>
> **Eduard Tomas**, Dev Lead di Plain Concepts
>
> **Ramon Tomas**, sviluppatore di Plain Concepts
>
> **David Sanz**, sviluppatore di Plain Concepts
>
> **Javier Valero**, Chief Operating Officer di Grupo Solutio
>
> **Pierre Millet**, Senior Consultant, Microsoft
>
> **Michael Friis**, Product Manager, Docker Inc
>
> **Charles Lowell**, Software Engineer, team VS CAT, Microsoft
>
> **Miguel Veloso**, Software Development Engineer presso Plain Concepts

## <a name="copyright"></a>Copyright

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2020 da Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

 Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi. Nessuna associazione reale o connessione è intenzionale o può essere desunta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Il logo Docker whale è un marchio registrato di Docker, Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

>[!div class="step-by-step"]
>[Avanti](container-docker-introduction/index.md)
