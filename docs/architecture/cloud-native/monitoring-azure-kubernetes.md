---
title: Monitoraggio nei servizi Azure Kubernetes
description: Monitoraggio nei servizi Azure Kubernetes
ms.date: 02/05/2020
ms.openlocfilehash: 5c46b9e8599f70d430ad26cf1364343454d30a16
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450063"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Monitoraggio nei servizi Azure Kubernetes

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La registrazione incorporata in Kubernetes è primitiva. Tuttavia, esistono alcune opzioni eccezionali per ottenere i log da Kubernetes e in una posizione in cui possono essere analizzati correttamente. Se è necessario monitorare i cluster AKS, la configurazione di Elastic stack per Kubernetes è un'ottima soluzione.

## <a name="azure-monitor-for-containers"></a>Monitoraggio di Azure per contenitori

Il [monitoraggio di Azure per i contenitori](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) supporta l'utilizzo di log non solo Kubernetes, ma anche da altri motori di orchestrazione, ad esempio DC/OS, Docker Swarm e Red Hat OpenShift.

![l'utilizzo di log da vari contenitori](./media/containers-diagram.png)
**figura 7-10**. Utilizzo di log da vari contenitori

[Prometeo](https://prometheus.io/) è una diffusa soluzione di monitoraggio delle metriche open source. Fa parte della base di calcolo nativa del cloud. In genere, l'uso di Prometeo richiede la gestione di un server Prometeo con il proprio archivio. Tuttavia, [monitoraggio di Azure per i contenitori fornisce l'integrazione diretta con gli endpoint della metrica Prometheus](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-prometheus-integration), quindi non è necessario un server separato.

Le informazioni relative a log e metriche vengono raccolte non solo dai contenitori in esecuzione nel cluster, ma anche dal cluster che ospita autonomamente. Consente di correlare le informazioni di log dai due, rendendo molto più semplice rilevare un errore.

L'installazione degli agenti di raccolta log è diversa nei cluster [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) e [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . In entrambi i casi, tuttavia, la raccolta di log viene implementata come Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), vale a dire che l'agente di raccolta log viene eseguito come contenitore in ogni nodo.

Indipendentemente dall'agente di orchestrazione o dal sistema operativo che esegue il daemon di monitoraggio di Azure, le informazioni di log vengono trasmesse agli stessi strumenti di monitoraggio di Azure con cui gli utenti hanno familiarità. Ciò garantisce un'esperienza parallela in ambienti che combinano origini di log diverse, ad esempio un ambiente ibrido per Kubernetes/funzioni di Azure.

![un dashboard di esempio che mostra le informazioni di registrazione e metrica da diversi contenitori in esecuzione.](./media/containers-dashboard.png)
**figura 7-11**. Un dashboard di esempio che mostra le informazioni di registrazione e metrica da diversi contenitori in esecuzione.

## <a name="logfinalize"></a>Log. Finalize ()

La registrazione è uno dei componenti più trascurati e ancora più importanti della distribuzione di applicazioni su larga scala. Con l'aumentare delle dimensioni e della complessità delle applicazioni, è quindi difficile eseguirne il debug. Avere log di qualità superiore disponibili rende il debug molto più semplice e lo sposta dall'area di autenticazione "quasi impossibile" a "un'esperienza piacevole".

>[!div class="step-by-step"]
>[Precedente](logging-with-elastic-stack.md)
>[Successivo](azure-monitor.md)
