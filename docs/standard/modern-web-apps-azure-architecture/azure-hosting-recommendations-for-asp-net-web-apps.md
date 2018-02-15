---
title: Hosting di indicazioni per le applicazioni web ASP.NET di base di Azure
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | Indicazioni per le applicazioni web ASP.NET di hosting di Azure
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 868f1b7ce452be9e29b921888f90d128e074ba13
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Hosting di indicazioni per le applicazioni Web ASP.NET di base di Azure

> "Leader line-of-business everywhere sono ignorando i reparti IT per ottenere applicazioni dal cloud (noto anche come SaaS) e come se fossero una rivista sottoscrizione a pagamento per tali. E quando il servizio non è più necessario, è possibile annullare la sottoscrizione con nessun apparecchiature lasciata inutilizzata nell'angolo".  
> _\- Daryl Plummer, analista Gartner_

## <a name="summary"></a>Riepilogo

Qualsiasi esigenze e architettura dell'applicazione, Azure può supportare. Le esigenze di hosting possono essere semplice come un sito web statico a un'applicazione estremamente sofisticata costituito da decine di servizi. Per le applicazioni ASP.NET Core monolitico web e servizi di supporto, esistono molte configurazioni note consigliati. Le indicazioni riportate di seguito vengono raggruppate in base al tipo di risorsa per essere ospitati, completo se applicazioni, i singoli processi o i dati.

## <a name="web-applications"></a>Applicazioni Web

Applicazioni Web possono essere ospitate con:

-   App del servizio Web App

-   Contenitori

-   Azure Service Fabric

-   Macchine virtuali (VM)

Di questi, App Web del servizio App sono l'approccio consigliato per la maggior parte degli scenari. Per le architetture microservizio, prendere in considerazione un approccio basato sul contenitore o dall'infrastruttura del servizio. Se è necessario un maggiore controllo sui computer che esegue l'applicazione, prendere in considerazione le macchine virtuali di Azure.

### <a name="app-service-web-apps"></a>App del servizio Web App

Servizio App Web App offre una piattaforma completamente gestita ottimizzata per l'hosting di applicazioni web. È un platform-as-a-service(PaaS) offerta che consentendo di che concentrarsi sulla logica di business, mentre Azure si occupa dell'infrastruttura necessari per eseguire e ridimensionare l'app. Alcune funzionalità principali di servizio App dell'App Web:

-   Ottimizzazione di DevOps (integrazione continua e il recapito, più ambienti, A / B eseguire test, il supporto di script)

-   Su scala globale e la disponibilità elevata

-   Connessioni a SaaS piattaforme e i dati locali

-   Sicurezza e conformità

-   integrazione con Visual Studio

Servizio App di Azure è la scelta migliore per la maggior parte delle applicazioni web. Gestione e distribuzione sono integrati nella piattaforma scalabile rapidamente siti per gestire carichi di traffico elevata e la gestione di traffico e di bilanciamento del carico incorporati garantire un'elevata disponibilità. È possibile spostare i siti esistenti al servizio App di Azure con facilità uno strumento di migrazione online, utilizzare un'applicazione open source dalla raccolta di applicazioni Web o creare un nuovo sito usando gli strumenti di propria scelta e framework. La funzionalità processi Web è facile aggiungere processo in background di elaborazione per l'app web di servizio App.

### <a name="containers-and-azure-container-service"></a>Contenitori e il servizio contenitore di Azure

Il servizio contenitore di Azure, è più semplice per poter creare, configurare e gestire un cluster di macchine virtuali che sono preconfigurati per l'esecuzione di applicazioni nei contenitori. Usa una configurazione ottimizzata di strumenti di pianificazione e l'orchestrazione open source più diffusi. In questo modo è possibile usare le competenze esistenti o disegnare su un corpo di grandi dimensioni e in continua crescito di esperienza della community, distribuire e gestire applicazioni basate sul contenitore in Microsoft Azure.

Il servizio contenitore di Azure, è più semplice per poter creare, configurare e gestire un cluster di macchine virtuali che sono preconfigurati per l'esecuzione di applicazioni nei contenitori. Usa una configurazione ottimizzata di strumenti di pianificazione e l'orchestrazione open source più diffusi. In questo modo è possibile usare le competenze esistenti o disegnare su un corpo di grandi dimensioni e in continua crescito di esperienza della community, distribuire e gestire applicazioni basate sul contenitore in Microsoft Azure.

Uno degli obiettivi di servizio di contenitore di Azure consiste nel fornire un ambiente di hosting del contenitore utilizzando strumenti open source e tecnologie che sono attualmente più diffusi tra i clienti Microsoft. A tal fine, il servizio contenitore di Azure espone gli endpoint API standard per la scelta orchestrator (controller di dominio o del sistema operativo, Docker Swarm o Kubernetes). Tramite questi endpoint, è possibile utilizzare qualsiasi software che è in grado di comunicare con gli endpoint. Ad esempio, nel caso l'endpoint Docker Swarm, è possibile utilizzare l'interfaccia della riga di comando di Docker (CLI). Per i controller di dominio o del sistema operativo, è possibile scegliere DCOS CLI. Per Kubernetes, è possibile scegliere kubectl. Figura 11-1 viene illustrato come utilizzare questi endpoint per gestire i cluster del contenitore.

![](./media/image11-1.png)

**Figura 11-1.** Gestione di Azure il servizio contenitore con Docker, Kubernetes o controller di dominio o del sistema operativo, gli endpoint.

### <a name="azure-service-fabric"></a>Azure Service Fabric

Se si crea una nuova app o riscrivere un'app esistente per l'utilizzo di un'architettura microservizio, Service Fabric è una scelta ottimale. Le app, che vengono eseguite in un pool condiviso di computer, è possono avviare piccole e aumento delle dimensioni in larga scala con centinaia o migliaia di computer in base alle esigenze. Servizi con stato semplificano in modo coerente e affidabile archiviare lo stato dell'app e Service Fabric gestisce automaticamente il partizionamento del servizio, scalabilità e disponibilità per l'utente. Service Fabric supporta inoltre WebAPI aprire interfaccia Web per .NET (OWIN) e ASP.NET Core. Rispetto al servizio App, Service Fabric fornisce più controllo sulla o accesso diretto a, l'infrastruttura sottostante. È possibile remoto nel server o configurare le attività di avvio server.

### <a name="azure-virtual-machines"></a>Macchine virtuali di Azure

Se si dispone di un'applicazione esistente che richiede modifiche sostanziali per l'esecuzione nel servizio App o dall'infrastruttura di servizio, è possibile scegliere le macchine virtuali per semplificare la migrazione al cloud. Tuttavia, correttamente la configurazione, la protezione e gestione di macchine virtuali richiede molto tempo e competenze IT rispetto al servizio App di Azure e Service Fabric. Se si prevede di macchine virtuali di Azure, assicurarsi di prendere in considerazione l'impegno di manutenzione richiesto per applicare la patch, aggiornare e gestire l'ambiente di VM. Macchine virtuali di Azure è Infrastructure-as-a-Service (IaaS), mentre l'infrastruttura dei servizi e servizio App sono Platform-as-a-Service (Paas).

#### <a name="feature-comparison"></a>Confronto delle funzionalità

| Funzionalità di servizio App | Service Fabric | Macchina virtuale |
|---------|----------|----------|
| Distribuzione quasi immediata | x | x | |
| Scalabilità verticale in computer più grandi senza ridistribuzione | x | x | |
| Le istanze condividono contenuto e configurazione. non è necessario ridistribuire o riconfigurare in caso di ridimensionamento | x | x | |
| Più ambienti di distribuzione (produzione e gestione temporanea) | x | x | |
| Gestione automatica degli aggiornamenti del sistema operativo | x | | |
| Trasparente il passaggio tra le piattaforme a 32/64 bit | x | | |
| Distribuzione del codice con Git, FTP | x | | x |
| Distribuzione del codice con WebDeploy | x | | x |
| Distribuzione del codice con TFS | x | X | x |
| Sito web host o il livello di servizio web dell'architettura a più livelli | x | X | x |
| Accesso ai servizi di Azure come Database di SQL Service Bus, archiviazione, | x | X | x |
| Installare qualsiasi MSI personalizzato | | x | x |

## <a name="logical-processes"></a>Criteri logici

Singoli processi logici che possono essere separati dal resto dell'applicazione possono essere distribuiti in modo indipendente per le funzioni di Azure in modo "senza server". Funzioni di Azure consente di scrivere il codice necessario per un problema specifico, senza doversi preoccupare di applicazione o dell'infrastruttura per l'esecuzione. È possibile scegliere tra un'ampia gamma di linguaggi di programmazione, tra cui C\#, F\#, Node.js, Python e PHP, consentendo di scegliere il linguaggio più produttivo per l'attività in questione. Come la maggior parte delle soluzioni basate su cloud, si paga solo per la quantità di tempo l'uso e può essere considerato attendibile funzioni di Azure per la scalabilità verticale in base alle esigenze.

## <a name="data"></a>Dati

Azure offre un'ampia gamma di opzioni di archiviazione di dati, in modo che l'applicazione può utilizzare il provider di dati appropriato per i dati in questione.

Per i dati transazionali e relazionali, database SQL di Azure sono la scelta migliore. Per prestazioni elevate prevalentemente di sola lettura dei dati, una cache Redis supportata da un Database di SQL Azure è una buona soluzione.

Non strutturati i dati JSON possono essere archiviati in diversi modi per DocumentDB, dalle colonne di Database SQL a BLOB o tabelle in archiviazione di Azure. Di questi, DocumentDB offre le migliori funzionalità di query e l'opzione consigliata per un numero elevato di documenti JSON in base che devono supportare l'esecuzione di query.

Dati temporanei comando - o basato su eventi utilizzati per orchestrare il comportamento dell'applicazione è possono utilizzare il Bus di servizio di Azure o le code di archiviazione Azure. Bus di archiviazione di Azure offre una maggiore flessibilità ed è il servizio consigliato per la messaggistica non semplice all'interno e tra applicazioni.

## <a name="architecture-recommendations"></a>Raccomandazioni relative all'architettura

Requisiti dell'applicazione dovrebbero indicare la relativa architettura. Sono disponibili molti servizi di Azure diversi, la scelta che giusta è una decisione importante. Microsoft offre una raccolta di architetture di riferimento per identificare le architetture tipico ottimizzate per scenari comuni. È possibile associare un'architettura di riferimento che esegue il mapping più appropriato alle esigenze dell'applicazione oppure in offre almeno un punto di partenza.

Figura 11-2 è illustrata un'architettura di riferimento di esempio. Questo diagramma illustra un approccio di architettura consigliata per un sito Web del sistema di gestione dei contenuti Sitecore ottimizzato per marketing.

![](./media/image11-2.png)

**Figura 11-2.** Architettura di riferimento del sito Web marketing Sitecore.

**Riferimenti: indicazioni di Hosting di Azure**

-   Soluzione Azure Architectures\
    <https://azure.microsoft.com/solutions/architecture/>

-   Guide\ per sviluppatori Azure
    <https://azure.microsoft.com/campaigns/developer-guide/>

-   Che cos'è Azure App Service? \
    <https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is>

-   Servizio App di Azure, le macchine virtuali, Service Fabric e Comparison\ di servizi Cloud
    <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

>[!div class="step-by-step"]
[Precedente] (sviluppo-processo-per-azure.md)
