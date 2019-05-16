---
title: Gestire gli ambienti di produzione Docker
description: Conoscere i punti chiave per la gestione di un ambiente di produzione basate su contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: 7d10f670745f8bac1084b8c33c5acde67bac6229
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641069"
---
# <a name="manage-production-docker-environments"></a>Gestire gli ambienti di produzione Docker

Gestione del cluster e l'orchestrazione è il processo di controllo di un gruppo di host. Ciò può implicare l'aggiunta e rimozione di host da un cluster, recupero di informazioni sullo stato corrente dell'host e contenitori e l'avvio e arresto dei processi. Orchestrazione e gestione del cluster sono strettamente legate alla pianificazione perché l'utilità di pianificazione deve avere accesso a ogni host del cluster per poter pianificare servizi. Per questo motivo, lo stesso strumento viene spesso utilizzato per entrambi gli scopi.

## <a name="container-service-and-management-tools"></a>Strumenti di gestione e del servizio contenitore

Servizio contenitore consente la distribuzione rapida di soluzioni di clustering e orchestrazione di contenitori open source più diffuso. Usa le immagini Docker per garantire che i contenitori di applicazioni siano completamente portabili. Tramite il servizio contenitore, è possibile distribuire DC/OS (con tecnologia Apache Mesos e Mesosphere) e un cluster Docker Swarm con modelli Azure Resource Manager o il portale di Azure per garantire che è possibile ridimensionare tali applicazioni a migliaia, persino decine di migliaia, di contenitori.

Cluster vengono distribuiti tramite set di scalabilità di macchine virtuali di Azure e i cluster di sfruttano i vantaggi delle offerte di rete e archiviazione di Azure. Per accedere a servizio contenitore, è necessaria una sottoscrizione di Azure. Con il servizio contenitore, è possibile sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

Tabella 6-1 sono elencati i comuni strumenti di gestione correlati alla loro gli agenti di orchestrazione, le utilità di pianificazione e la piattaforma di clustering.

**Tabella 6-1**. Strumenti di gestione di docker

| Strumenti di gestione | Descrizione | Agenti di orchestrazione correlate |
|------------------|-------------|-----------------------|
| [Monitoraggio di Azure per contenitori](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Strumento di gestione dedicato Azure in Kubernetes | Azure Kubernetes Services (AKS) |
| [Interfaccia utente Web Kubernetes (dashboard)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Strumento di gestione di Kubernetes, è possibile monitorare e gestire un cluster Kubernetes locale | Servizio Azure Kubernetes<br/>Kubernetes locale |
| [Portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Versioni desktop e online per la gestione dei cluster di Service Fabric, in Azure, in locale, lo sviluppo locale e altri cloud | Azure Service Fabric |
| [Contenitore Monitoring (monitoraggio di Azure)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | Y gestione generale contenitore soluzione di monitoraggio. Consente di gestire il cluster Kubernetes tramite [monitoraggio di Azure per contenitori](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Servizio Azure Kubernetes<br/>Mesosphere DC/OS e ad altri utenti. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Un'altra scelta per la gestione e distribuzione di cluster è Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) è una piattaforma di microservizi Microsoft che include l'orchestrazione dei contenitori, nonché per gli sviluppatori di programmazione i modelli per creare applicazioni di microservizi altamente scalabile. Service Fabric supporta Docker in contenitori Linux e Windows e possono essere eseguiti in server Windows e Linux.

Di seguito sono gli strumenti di gestione di Service Fabric:

- [Portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) operazioni correlate al cluster (creazione/aggiornamento/eliminazione) un cluster o configurare l'infrastruttura (macchine virtuali, servizio di bilanciamento del carico, rete e così via)

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) è un'oggetto specifico dell'interfaccia utente e strumento multi-piattaforma desktop che fornisce informazioni dettagliate e alcune operazioni sui cluster di Service Fabric, dal punto di vista della nodi/macchine virtuali e dal punto di vista dell'applicazione e i servizi web.

>[!div class="step-by-step"]
>[Precedente](run-microservices-based-applications-in-production.md)
>[Successivo](monitor-containerized-application-services.md)
