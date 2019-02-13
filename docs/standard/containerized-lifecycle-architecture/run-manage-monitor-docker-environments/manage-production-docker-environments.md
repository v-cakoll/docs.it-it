---
title: Gestire gli ambienti di produzione Docker
description: Conoscere i punti chiave per la gestione di un ambiente di produzione basate su contenitori.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 54e2b999f744600d3b6853442bb9ccca004f4e76
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219490"
---
# <a name="manage-production-docker-environments"></a>Gestire gli ambienti di produzione Docker

Gestione del cluster e l'orchestrazione è il processo di controllo di un gruppo di host. Ciò può implicare l'aggiunta e rimozione di host da un cluster, recupero di informazioni sullo stato corrente dell'host e contenitori e l'avvio e arresto dei processi. Orchestrazione e gestione del cluster sono strettamente legate alla pianificazione perché l'utilità di pianificazione deve avere accesso a ogni host del cluster per poter pianificare servizi. Per questo motivo, lo stesso strumento viene spesso utilizzato per entrambi gli scopi.

## <a name="container-service-and-management-tools"></a>Strumenti di gestione e del servizio contenitore

Servizio contenitore consente la distribuzione rapida di soluzioni di clustering e orchestrazione di contenitori open source più diffuso. Usa le immagini Docker per garantire che i contenitori di applicazioni siano completamente portabili. Tramite il servizio contenitore, è possibile distribuire DC/OS (con tecnologia Apache Mesos e Mesosphere) e un cluster Docker Swarm con modelli Azure Resource Manager o il portale di Azure per garantire che è possibile ridimensionare tali applicazioni a migliaia, persino decine di migliaia, di contenitori.

Cluster vengono distribuiti tramite set di scalabilità di macchine virtuali di Azure e i cluster di sfruttano i vantaggi delle offerte di rete e archiviazione di Azure. Per accedere a servizio contenitore, è necessaria una sottoscrizione di Azure. Con il servizio contenitore, è possibile sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

Tabella 6-1 sono elencati i comuni strumenti di gestione correlati alla loro gli agenti di orchestrazione, le utilità di pianificazione e la piattaforma di clustering.

Tabella 6-1: Strumenti di gestione di docker


| Strumenti di gestione      | Descrizione           | Agenti di orchestrazione correlate |
|-----------------------|-----------------------|-----------------------|
| Servizio contenitore di\(gestione dell'interfaccia utente nel portale di Azure) | [Servizio contenitore](https://azure.microsoft.com/services/container-service/) offre una semplice ottenere avviato consente [distribuire un cluster di contenitori in Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) basata su agenti di orchestrazione più diffusi, ad esempio Mesosphere DC/OS, Kubernetes e Docker Swarm. <br /><br /> Servizio contenitore di ottimizza la configurazione di queste piattaforme. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti di orchestrazione e il servizio contenitore gestisce tutto il resto. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker Universal Control Plane\(in locale o cloud) | [Docker Universal Control Plane](https://docs.docker.com/v1.11/ucp/overview/) è la soluzione di gestione di livello aziendale del cluster da Docker. Consente di gestire l'intero cluster da un'unica posizione. <br /><br /> Docker Universal Control Plane è incluso come parte del prodotto commerciale denominato Docker Datacenter, che include Docker Swarm, Docker Universal Control Plane e registro attendibile Docker. <br /><br /> Docker Datacenter può essere installato in locale o il provisioning di un cloud pubblico come Azure. | Docker Swarm\(supportato dal servizio contenitore di) |
| Cloud docker\(noto anche come Tutum; cloud SaaS) | [Cloud docker](https://docs.docker.com/docker-cloud/) è un servizio di gestione ospitato (SaaS) che offre funzionalità di orchestrazione e un registro Docker build e di prova per le immagini dell'applicazione nel contenitore Docker, gli strumenti che consentono di configurare e gestire l'infrastruttura di host, e le funzionalità di distribuzione che consentono di automatizzare la distribuzione di immagini per l'infrastruttura concreto. È possibile connettere l'account Cloud Docker SaaS per l'infrastruttura nel servizio contenitore di esecuzione di un cluster Docker Swarm. | Docker Swarm\(supportato dal servizio contenitore di) |
| Mesosphere Marathon\(in locale o cloud) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) è una piattaforma di orchestrazione e utilità di pianificazione contenitore livello di produzione per Mesosphere DC/OS e Apache Mesos. <br /><br /> Funziona con Mesos (DC/OS è basato su Apache Mesos) al controllo con esecuzione prolungata dei servizi e fornisce una [interfaccia utente web per la gestione dei processo e il contenitore](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Fornisce uno strumento di gestione dell'interfaccia utente web | Mesosphere DC/OS\(basato su Apache Mesos, supportato dal servizio contenitore di) |
| Google Kubernetes | [Kubernetes](https://kubernetes.io/docs/user-guide/ui/#dashboard-access) si estende all'orchestrazione, la pianificazione e infrastruttura del cluster. È una piattaforma open source per l'automazione della distribuzione, ridimensionamento e la gestione dei contenitori di applicazioni in cluster di host, che fornisce infrastruttura incentrata sui contenitori. | Google Kubernetes\(supportato dal servizio contenitore di) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Un'altra scelta per la gestione e distribuzione di cluster è Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) è una piattaforma di microservizi Microsoft che include l'orchestrazione dei contenitori, nonché per gli sviluppatori di programmazione i modelli per creare applicazioni di microservizi altamente scalabili. Service Fabric supporta Docker nelle versioni di anteprima Linux corrente, ad esempio la [anteprima di Service Fabric in Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)e per i contenitori Windows [nella prossima versione](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Di seguito sono gli strumenti di gestione di Service Fabric:

-   [Portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) operazioni correlate al cluster (creazione/aggiornamento/eliminazione) un cluster o configurare l'infrastruttura (macchine virtuali, servizio di bilanciamento del carico, rete e così via)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) è uno strumento dell'interfaccia utente web specializzato che fornisce informazioni dettagliate e alcune operazioni nel cluster di Service Fabric dal punto di vista della nodi/macchine virtuali e dal punto di vista dell'applicazione e i servizi.

>[!div class="step-by-step"]
>[Precedente](run-microservices-based-applications-in-production.md)
>[Successivo](monitor-containerized-application-services.md)