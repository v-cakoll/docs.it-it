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
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="0bde7-103">Monitoraggio nei servizi Azure Kubernetes</span><span class="sxs-lookup"><span data-stu-id="0bde7-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0bde7-104">La registrazione incorporata in Kubernetes è primitiva.</span><span class="sxs-lookup"><span data-stu-id="0bde7-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="0bde7-105">Tuttavia, esistono alcune opzioni eccezionali per ottenere i log da Kubernetes e in una posizione in cui possono essere analizzati correttamente.</span><span class="sxs-lookup"><span data-stu-id="0bde7-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="0bde7-106">Se è necessario monitorare i cluster AKS, la configurazione di Elastic stack per Kubernetes è un'ottima soluzione.</span><span class="sxs-lookup"><span data-stu-id="0bde7-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="0bde7-107">Elastic stack</span><span class="sxs-lookup"><span data-stu-id="0bde7-107">Elastic Stack</span></span>

<span data-ttu-id="0bde7-108">Elastic stack è un'opzione potente per la raccolta di informazioni da un cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="0bde7-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="0bde7-109">Kubernetes supporta l'invio di log a un endpoint elasticsearch e, nella [maggior parte dei casi](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), è sufficiente impostare le variabili di ambiente, come illustrato nella figura 7-5:</span><span class="sxs-lookup"><span data-stu-id="0bde7-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="0bde7-110">**Figura 7-5** -variabili di configurazione per Kubernetes</span><span class="sxs-lookup"><span data-stu-id="0bde7-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="0bde7-111">Verrà installato elasticsearch nel cluster e la destinazione invierà tutti i log del cluster.</span><span class="sxs-lookup"><span data-stu-id="0bde7-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="0bde7-112">![un esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes](./media/kibana-dashboard.png)
**figura 7-6**.</span><span class="sxs-lookup"><span data-stu-id="0bde7-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="0bde7-113">Esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes</span><span class="sxs-lookup"><span data-stu-id="0bde7-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="0bde7-114">Monitoraggio del contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="0bde7-114">Azure Container Monitoring</span></span>

<span data-ttu-id="0bde7-115">Il monitoraggio dei contenitori di Azure supporta l'utilizzo di log solo da Kubernetes, ma anche da altri motori di orchestrazione come DC/OS, Docker Swarm e Red Hat OpenShift.</span><span class="sxs-lookup"><span data-stu-id="0bde7-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="0bde7-116">![l'utilizzo di log da vari contenitori](./media/containers-diagram.png)
**figura 7-7**.</span><span class="sxs-lookup"><span data-stu-id="0bde7-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="0bde7-117">Utilizzo di log da vari contenitori</span><span class="sxs-lookup"><span data-stu-id="0bde7-117">Consuming logs from various containers</span></span>

<span data-ttu-id="0bde7-118">Le informazioni relative a log e metriche vengono raccolte non solo dai contenitori in esecuzione nel cluster, ma anche dal cluster che ospita autonomamente.</span><span class="sxs-lookup"><span data-stu-id="0bde7-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="0bde7-119">Consente di correlare le informazioni di log dai due, rendendo molto più semplice rilevare un errore.</span><span class="sxs-lookup"><span data-stu-id="0bde7-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="0bde7-120">L'installazione degli agenti di raccolta log è diversa nei cluster [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) e [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) .</span><span class="sxs-lookup"><span data-stu-id="0bde7-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="0bde7-121">In entrambi i casi, tuttavia, la raccolta di log viene implementata come Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), vale a dire che l'agente di raccolta log viene eseguito come contenitore in ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="0bde7-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="0bde7-122">Indipendentemente dall'agente di orchestrazione o dal sistema operativo che esegue il daemon di monitoraggio di Azure, le informazioni di log vengono trasmesse agli stessi strumenti di monitoraggio di Azure con cui gli utenti hanno familiarità.</span><span class="sxs-lookup"><span data-stu-id="0bde7-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="0bde7-123">Ciò garantisce un'esperienza parallela in ambienti che combinano origini di log diverse, ad esempio un ambiente ibrido per Kubernetes/funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="0bde7-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="0bde7-124">![un dashboard di esempio che mostra le informazioni di registrazione e metrica da diversi contenitori in esecuzione.](./media/containers-dashboard.png)
**figura 7-8**.</span><span class="sxs-lookup"><span data-stu-id="0bde7-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="0bde7-125">Un dashboard di esempio che mostra le informazioni di registrazione e metrica da diversi contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0bde7-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="0bde7-126">Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="0bde7-126">Log.Finalize()</span></span>

<span data-ttu-id="0bde7-127">La registrazione è uno dei componenti più trascurati e ancora più importanti della distribuzione di applicazioni su larga scala.</span><span class="sxs-lookup"><span data-stu-id="0bde7-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="0bde7-128">Con l'aumentare delle dimensioni e della complessità delle applicazioni, è quindi difficile eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="0bde7-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="0bde7-129">Avere log di qualità superiore disponibili rende il debug molto più semplice e lo sposta dall'area di autenticazione "quasi impossibile" a "un'esperienza piacevole".</span><span class="sxs-lookup"><span data-stu-id="0bde7-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0bde7-130">[Precedente](logging-with-elastic-stack.md)
>[Successivo](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="0bde7-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
