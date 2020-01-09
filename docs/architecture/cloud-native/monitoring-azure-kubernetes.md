---
title: Monitoraggio nei servizi Azure Kubernetes
description: Monitoraggio nei servizi Azure Kubernetes
ms.date: 09/23/2019
ms.openlocfilehash: fc9d84fd738ff1c40d25860680e14313c9323517
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711649"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Monitoraggio nei servizi Azure Kubernetes

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La registrazione incorporata in Kubernetes è primitiva. Tuttavia, esistono alcune opzioni eccezionali per ottenere i log da Kubernetes e in una posizione in cui possono essere analizzati correttamente. Se è necessario monitorare i cluster AKS, la configurazione di Elastic stack per Kubernetes è un'ottima soluzione.

## <a name="elastic-stack"></a>Elastic stack

Elastic stack è un'opzione potente per la raccolta di informazioni da un cluster Kubernetes. Kubernetes supporta l'invio di log a un endpoint elasticsearch e, nella [maggior parte dei casi](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), è sufficiente impostare le variabili di ambiente, come illustrato nella figura 7-5:

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**Figura 7-5** -variabili di configurazione per Kubernetes

Verrà installato elasticsearch nel cluster e la destinazione invierà tutti i log del cluster.

![un esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes](./media/kibana-dashboard.png)
**figura 7-6**. Esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes

## <a name="azure-container-monitoring"></a>Monitoraggio del contenitore di Azure

Il monitoraggio dei contenitori di Azure supporta l'utilizzo di log solo da Kubernetes, ma anche da altri motori di orchestrazione come DC/OS, Docker Swarm e Red Hat OpenShift.

![l'utilizzo di log da vari contenitori](./media/containers-diagram.png)
**figura 7-7**.  Utilizzo di log da vari contenitori

Le informazioni relative a log e metriche vengono raccolte non solo dai contenitori in esecuzione nel cluster, ma anche dal cluster che ospita autonomamente. Consente di correlare le informazioni di log dai due, rendendo molto più semplice rilevare un errore.

L'installazione degli agenti di raccolta log è diversa nei cluster [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) e [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . In entrambi i casi, tuttavia, la raccolta di log viene implementata come Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), vale a dire che l'agente di raccolta log viene eseguito come contenitore in ogni nodo.

Indipendentemente dall'agente di orchestrazione o dal sistema operativo che esegue il daemon di monitoraggio di Azure, le informazioni di log vengono trasmesse agli stessi strumenti di monitoraggio di Azure con cui gli utenti hanno familiarità. Ciò garantisce un'esperienza parallela in ambienti che combinano origini di log diverse, ad esempio un ambiente ibrido per Kubernetes/funzioni di Azure.

![un dashboard di esempio che mostra le informazioni di registrazione e metrica da diversi contenitori in esecuzione.](./media/containers-dashboard.png)
**figura 7-8**. Un dashboard di esempio che mostra le informazioni di registrazione e metrica da diversi contenitori in esecuzione.

## <a name="logfinalize"></a>Log. Finalize ()

La registrazione è uno dei componenti più trascurati e ancora più importanti della distribuzione di applicazioni su larga scala. Con l'aumentare delle dimensioni e della complessità delle applicazioni, è quindi difficile eseguirne il debug. Avere log di qualità superiore disponibili rende il debug molto più semplice e lo sposta dall'area di autenticazione "quasi impossibile" a "un'esperienza piacevole".

>[!div class="step-by-step"]
>[Precedente](logging-with-elastic-stack.md)
>[Successivo](azure-monitor.md)
