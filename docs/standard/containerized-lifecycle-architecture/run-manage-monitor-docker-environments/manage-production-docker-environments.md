---
title: Gestire gli ambienti di produzione Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c962543004c88b0a6413cc22d8bdddf954af66f8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="manage-production-docker-environments"></a>Gestire gli ambienti di produzione Docker

Gestione del cluster e l'orchestrazione è il processo di controllo di un gruppo di host. Ciò può implicare l'aggiunta e rimozione di host da un cluster, recupero di informazioni sullo stato corrente dell'host e i contenitori, avvio e arresto dei processi. Orchestrazione e la gestione di cluster sono strettamente legati alla pianificazione poiché l'utilità di pianificazione deve avere accesso a ogni host del cluster per poter pianificare servizi. Per questo motivo, lo stesso strumento viene spesso utilizzato per entrambi gli scopi.

## <a name="container-service-and-management-tools"></a>Strumenti di gestione e del servizio contenitore

Servizio contenitore fornisce una rapida distribuzione di soluzioni di clustering e orchestrazione contenitore open source più diffusi. Usa le immagini Docker per assicurarsi che i contenitori di applicazioni siano completamente portabili. Tramite il servizio di contenitore, è possibile distribuire controller di dominio o del sistema operativo (con tecnologia Mesosphere e Apache Mesos) e Docker Swarm cluster con modelli di gestione risorse di Azure o il portale di Azure per garantire che è possibile scalare le applicazioni a migliaia, anche decine di migliaia, di contenitori.

Distribuire tali cluster utilizzando i set di scalabilità di macchine virtuali di Azure e i cluster di sfruttano i vantaggi delle offerte di rete e archiviazione Azure. Per accedere a servizio di contenitore, è necessaria una sottoscrizione di Azure. Con il servizio di contenitore, è possibile sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

Nella tabella 6-1 sono elencati i comuni strumenti di gestione correlati alla loro orchestrators, l'utilità di pianificazione e piattaforma clustering.

Nella tabella 6-1: strumenti di gestione di Docker


| Strumenti di gestione      | Descrizione           | Orchestrators correlati |
|-----------------------|-----------------------|-----------------------|
| Il servizio contenitore\(gestione dell'interfaccia utente nel portale di Azure) | [Il servizio contenitore](https://azure.microsoft.com/en-us/services/container-service/) offre una semplice ottenere avviato modo per [distribuire un cluster di contenitore in Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) in base a più diffusi orchestrators come controller di dominio/OS Mesosphere, Kubernetes e Docker Swarm. <br /><br /> Il servizio contenitore consente di ottimizzare la configurazione di tali piattaforme. È sufficiente selezionare le dimensioni, il numero di host e la scelta degli strumenti di orchestrator e il servizio contenitore gestisce tutto il resto. | Controller di dominio mesosphere/OS <br /><br /> Kubernetes <br /><br /> Sciame docker |
| Piano di controllo universale docker\(locale o cloud) | [Piano di controllo universale docker](https://docs.docker.com/v1.11/ucp/overview/) è la soluzione di gestione aziendale del cluster da Docker. Consente di gestire l'intero cluster da un'unica posizione. <br /><br /> Piano di controllo universale docker è incluso come parte del prodotto commerciale denominato Data Center di Docker offrendo Docker Swarm, Docker Universal piano di controllo e registro attendibile Docker. <br /><br /> Data Center di docker può essere installato in locale o il provisioning da un cloud pubblico come Azure. | Docker Swarm\(supportate dal servizio di contenitore) |
| Cloud docker\(noto anche come Tutum; cloud SaaS) | [Cloud docker](https://docs.docker.com/docker-cloud/) è un servizio di gestione ospitato (SaaS) che offre funzionalità di orchestrazione e un registro di sistema di Docker build e di prova per le immagini dell'applicazione Dockerized, strumenti che consentono di configurare e gestire l'infrastruttura host e le funzionalità di distribuzione per automatizzare la distribuzione delle immagini per l'infrastruttura concreta. È possibile connettere l'account Cloud Docker SaaS per l'infrastruttura nel servizio di contenitore in esecuzione di un cluster di Docker Swarm. | Docker Swarm\(supportate dal servizio di contenitore) |
| Maratona mesosphere\(locale o cloud) | [Maratona](https://mesosphere.github.io/marathon/docs/marathon-ui.html) è una piattaforma di orchestrazione e utilità di pianificazione di contenitore in grado di produzione per del Mesosphere controller di dominio/OS e Apache Mesos. <br /><br /> Funziona con Mesos (controller di dominio o sistema operativo è basato su Apache Mesos) al controllo con esecuzione prolungata dei servizi e fornisce un [interfaccia utente web per processo e gestione dei contenitori](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Fornisce uno strumento di gestione dell'interfaccia utente web | Controller di dominio/OS mesosphere\(basato su Apache Mesos; supportato dal servizio di contenitore) |
| Kubernetes di Google | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access) si estende su orchestrazione, pianificazione e l'infrastruttura di cluster. È una piattaforma open source per l'automazione della distribuzione, ridimensionamento e delle operazioni di contenitori di applicazioni per i cluster di host, offre un'infrastruttura incentrato sul contenitore. | Google Kubernetes\(supportate dal servizio di contenitore) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Un'altra scelta per la gestione e distribuzione di cluster è Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/) è una piattaforma di microservizi Microsoft che include l'orchestrazione di contenitore, nonché per sviluppatori di modelli per creare applicazioni estremamente scalabili microservizi programmazione. Service Fabric supporta Docker nelle versioni di anteprima Linux corrente, come il [anteprima Service Fabric in Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)e per i contenitori di Windows [nella prossima versione](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Di seguito sono strumenti di gestione di Service Fabric:

-   [Portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) le operazioni di relative al cluster (creazione/aggiornamento/eliminazione) un cluster o configurare l'infrastruttura (VM, servizio di bilanciamento del carico di rete, e così via).

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) è uno strumento dell'interfaccia utente web specializzato che fornisce informazioni dettagliate e alcune operazioni sul cluster di Service Fabric dal punto di vista nodi/macchine virtuali e dal punto di vista dell'applicazione e i servizi.


>[!div class="step-by-step"]
[Precedente] [Avanti] (monitoraggio-contenitore-applicazione-services.md) (run-microservices-based-applications-in-production.md)
