---
title: Gestire gli ambienti di produzione Docker
description: Informazioni sui punti chiave per la gestione di un ambiente di produzione basato su contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: 26e7a3319afe593d75e2384d023c901a389245dc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834510"
---
# <a name="manage-production-docker-environments"></a>Gestire gli ambienti di produzione Docker

La gestione e l'orchestrazione del cluster è il processo di controllo di un gruppo di host. Ciò può includere l'aggiunta e la rimozione di host da un cluster, il recupero di informazioni sullo stato corrente di host e contenitori e l'avvio e l'arresto di processi. La gestione e l'orchestrazione del cluster sono attività strettamente correlate alla pianificazione perché l'utilità di pianificazione deve avere accesso a ogni host del cluster per poter pianificare i servizi. Per questo motivo, viene spesso usato lo stesso strumento per entrambi gli scopi.

## <a name="container-service-and-management-tools"></a>Servizio contenitore e strumenti di gestione

Il servizio contenitore consente la distribuzione rapida delle soluzioni open source di clustering e orchestrazione dei contenitori più diffuse. Usa le immagini Docker per assicurare la portabilità completa dei contenitori delle applicazioni. Tramite il servizio contenitore, è possibile distribuire DC/OS (supportato da Mesosphere e Apache Mesos) e i cluster Docker Swarm con i modelli di Azure Resource Manager o il portale di Azure per assicurare la scalabilità di queste applicazioni a migliaia, o persino a decine di migliaia, di contenitori.

I cluster vengono distribuiti tramite set di scalabilità di macchine virtuali di Azure e sfruttano i vantaggi delle offerte di rete e di archiviazione di Azure. Per accedere al servizio contenitore è necessaria una sottoscrizione di Azure. Con il servizio contenitore è possibile sfruttare i vantaggi delle funzionalità di livello aziendale di Azure, mantenendo al tempo stesso la portabilità delle applicazioni, anche ai livelli di orchestrazione.

La tabella 6-1 elenca strumenti di gestione comuni con gli agenti di orchestrazione, le utilità di pianificazione e la piattaforma di clustering correlati.

**Tabella 6-1**. Strumenti di gestione Docker

| Strumenti di gestione | Descrizione | Agenti di orchestrazione correlati |
|------------------|-------------|-----------------------|
| [Azure Monitor for Containers](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Strumento di gestione Kubernetes dedicato di Azure | Servizio Azure Kubernetes (AKS) |
| [Interfaccia utente Web di Kubernetes (dashboard)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Strumento di gestione Kubernetes che consente di monitorare e gestire un cluster Kubernetes locale | Servizio Azure Kubernetes<br/>Kubernetes locale |
| [Portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Versione desktop e online per la gestione di cluster Service Fabric in Azure, in locale, in ambienti di sviluppo locali e in altri cloud | Azure Service Fabric |
| [Monitoraggio contenitori (Monitoraggio di Azure)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | Soluzione di monitoraggio e gestione contenitori generica. Consente di gestire cluster Kubernetes tramite [Monitoraggio di Azure per contenitori](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Servizio Azure Kubernetes<br/>Mesosphere DC/OS e altri. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Un'altra opzione per la distribuzione e la gestione di cluster è Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) è una piattaforma di microservizi Microsoft che include l'orchestrazione dei contenitori e modelli di programmazione per sviluppatori per compilare applicazioni di microservizi a scalabilità elevata. Service Fabric supporta Docker in contenitori Linux e Windows e può essere eseguito in server Windows e Linux.

Di seguito sono riportati gli strumenti di gestione di Service Fabric:The following are Service Fabric management tools:

- Il [portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) per le operazioni correlate ai cluster, ad esempio creazione/aggiornamento/eliminazione di un cluster oppure la configurazione dell'infrastruttura (macchine virtuali, bilanciamento del carico, rete e così via).

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) è uno strumento multipiattaforma specializzato disponibile in versione interfaccia utente Web e desktop che offre informazioni dettagliate e alcune operazioni nel cluster Service Fabric, dal punto di vista dei nodi e delle macchine virtuali e da quello dell'applicazione e dei servizi.

>[!div class="step-by-step"]
>[Successivo](run-microservices-based-applications-in-production.md)
>[precedente](monitor-containerized-application-services.md)
