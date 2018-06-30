---
title: Gestire gli ambienti di produzione Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 169ffa7ba61fa5dff09229410adb534f8e34a35c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104585"
---
# <a name="manage-production-docker-environments"></a>Gestire gli ambienti di produzione Docker

Gestione del cluster e l'orchestrazione è il processo di controllo di un gruppo di host. Ciò può implicare l'aggiunta e rimozione di host da un cluster, recupero di informazioni sullo stato corrente dell'host e i contenitori, avvio e arresto dei processi. Orchestrazione e la gestione di cluster sono strettamente legati alla pianificazione poiché l'utilità di pianificazione deve avere accesso a ogni host del cluster per poter pianificare servizi. Per questo motivo, lo stesso strumento viene spesso utilizzato per entrambi gli scopi.

## <a name="container-service-and-management-tools"></a>Strumenti di gestione e del servizio contenitore

Il servizio contenitore fornisce una rapida distribuzione di soluzioni di clustering e orchestrazione contenitore open source più diffusi. Usa le immagini Docker per assicurarsi che i contenitori di applicazioni siano completamente portabili. Tramite il servizio contenitore, è possibile distribuire controller di dominio/OS (con tecnologia Mesosphere e Apache Mesos) e Docker Swarm cluster con i modelli di gestione risorse di Azure o il portale di Azure per garantire che è possibile scalare le applicazioni per migliaia, ovvero anche decine di migliaia, ovvero di contenitori.

Distribuire tali cluster utilizzando il set di scalabilità macchina virtuale di Azure e i cluster possono sfruttare le offerte di rete e archiviazione di Azure. Per accedere a servizio di contenitore, è necessaria una sottoscrizione Azure. Con il servizio di contenitore, è possibile sfruttare le funzionalità aziendale di Azure pur mantenendo la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

Nella tabella 6-1 sono elencati i comuni strumenti di gestione correlati alla loro orchestrators, utilità di pianificazione e della piattaforma di clustering.

Strumenti di gestione di Docker tabella 6-1:


| Strumenti di gestione      | Descrizione           | Orchestrators correlati |
|-----------------------|-----------------------|-----------------------|
| Il servizio contenitore\(gestione dell'interfaccia utente nel portale di Azure) | [Il servizio contenitore](https://azure.microsoft.com/en-us/services/container-service/) fornisce una semplice ottenere avviato modo per [distribuire un cluster di contenitore in Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) base orchestrators diffusi come controller di dominio Mesosphere/OS, Kubernetes e Docker Swarm. <br /><br /> Il servizio contenitore consente di ottimizzare la configurazione di tali piattaforme. È sufficiente selezionare le dimensioni, il numero di host e la scelta degli strumenti di orchestrator e il servizio contenitore gestisce tutto il resto. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Piano di controllo universale docker\(in locale o cloud) | [Piano di controllo universale docker](https://docs.docker.com/v1.11/ucp/overview/) è la soluzione di gestione aziendale del cluster da Docker. Consente di gestire l'intero cluster da un'unica posizione. <br /><br /> Piano di controllo universale docker è incluso come parte del prodotto commerciale denominato Data Center di Docker offrendo tramite Docker Swarm, Docker Universal piano di controllo e registro attendibile Docker. <br /><br /> Data Center di docker possono essere installati in locale o il provisioning da un cloud pubblico come Azure. | Docker Swarm\(supportate dal servizio di contenitore) |
| Docker Cloud\(noto anche come Tutum; cloud SaaS) | [Cloud docker](https://docs.docker.com/docker-cloud/) è un servizio di gestione ospitato (SaaS) che offre funzionalità di orchestrazione e un registro di sistema di Docker build e di prova per le immagini dell'applicazione Dockerized, strumenti che consentono di configurare e gestire l'infrastruttura host, e le funzionalità di distribuzione che consentono di automatizzare la distribuzione delle immagini per l'infrastruttura concreta. È possibile connettere l'account Cloud Docker SaaS per l'infrastruttura nel servizio di contenitore in esecuzione un cluster di Docker Swarm. | Docker Swarm\(supportate dal servizio di contenitore) |
| Marathon mesosphere\(in locale o cloud) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) è una piattaforma di orchestrazione e utilità di pianificazione di contenitore anno scolastico di produzione per del Mesosphere controller di dominio/OS e Apache Mesos. <br /><br /> Funziona con Mesos (controller di dominio/OS è basato su Apache Mesos) al controllo del codice con esecuzione prolungata dei servizi e fornisce un [interfaccia utente web per processo e gestione dei contenitori](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Fornisce uno strumento di gestione dell'interfaccia utente web | Controller di dominio/OS mesosphere\(basato su Apache Mesos; supportato dal servizio di contenitore) |
| Google Kubernetes | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access) si estende a orchestrazione, pianificazione e l'infrastruttura di cluster. È una piattaforma open source per l'automazione della distribuzione, ridimensionamento e delle operazioni di contenitori di applicazioni per i cluster di host, che offre un'infrastruttura incentrata sul contenitore. | Google Kubernetes\(supportate dal servizio di contenitore) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Azure Service Fabric è un'altra scelta per la gestione e distribuzione di cluster. [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/) è una piattaforma di microservizi Microsoft che include l'orchestrazione di contenitore, nonché per sviluppatori di programmazione i modelli per compilare applicazioni estremamente scalabili microservizi. Service Fabric supporta Docker nelle versioni di anteprima Linux corrente, come le [anteprima di Service Fabric in Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)e per i contenitori di Windows [nella prossima versione](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Di seguito sono strumenti di gestione di Service Fabric:

-   [Portale di Azure per Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) operazioni correlate ai cluster (creazione/aggiornamento/eliminazione) un cluster o configurare l'infrastruttura (le macchine virtuali, servizio di bilanciamento del carico di rete, e così via.)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) è uno strumento dell'interfaccia utente web specializzato che fornisce informazioni dettagliate e alcune operazioni sul cluster di Service Fabric dal punto di vista del nodi/macchine virtuali e dal punto di vista dell'applicazione e i servizi.


>[!div class="step-by-step"]
[Precedente](run-microservices-based-applications-in-production.md)
[Successivo](monitor-containerized-application-services.md)
