---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitoriChoosing Azure compute platforms for container-based applications
ms.date: 02/18/2020
ms.openlocfilehash: 52e7cf1c5dd3a5850564bdb33ac7a4ac4904f432
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503869"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore

Come si è notato dopo aver letto le sezioni precedenti, Azure è un cloud aperto che offre più opzioni. È possibile utilizzare la soluzione migliore per le proprie esigenze, tuttavia, vengono anche affrontate domande su quale prodotto/tecnologia è necessario utilizzare per le applicazioni containerizzate.

Come raccomandazione predefinita, di seguito sono riportati i criteri principali consigliati in questa guida:As a *by-default* recommendation, the following is the main criteria recommended in this guidance:

- **Singola app monolitica:** Scegliere il servizio app di AzureChoose Azure App Service
- **App a n livelli:** Scegliere gli agenti di orchestrazione, ad esempio il servizio Azure Kubernetes (AKS) o il servizio app, se si dispone di un servizio back-end singolo o alcuni
- **Microservizi:** Scegliere AKS o App Web di Azure per i contenitoriChoose AKS or Azure Web Apps for Containers
- **Funzioni senza server & gestori eventi:Serverless functions & event handlers:** Scegliere Funzioni di AzureChoose Azure Functions
- **Batch su larga scala:** Scegliere Batch di AzureChoose Azure Batch

Tuttavia, questa raccomandazione deve essere presa con un pizzico di sale, in quanto la selezione del prodotto dipenderà dalle esigenze e dalle caratteristiche dell'applicazione specifica. Non tutte le applicazioni sono uguali anche quando inizialmente potrebbero sembrare tipi simili.

Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso. Ma, come punto di partenza, è bene avere una guida iniziale da cui è possibile iniziare a valutare e testare in base a una determinata priorità.

Nella tabella seguente è possibile visualizzare una suddivisione dei diversi tipi di app e gli scenari di hosting di Azure possibili e consigliati.

| Architettura dell'applicazione | Macchine virtuali - Macchine virtuali di Azure | ACI - Azure Container Instances | Servizio app di Azure (contenitori w-w/o)Azure App Service (w-w/o containers) | AKS - Servizi di Azure Kubernetes | Funzioni di Azure | Azure Batch |
|:------------------------:|:--:|:--:|:--:|:--:|:--:|:--:|
| **App Web (Monolitic)**         | ![Possibile con le macchine virtualiPossible with VMs](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Consigliato con il servizio app](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Possibile con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | |
| **App a più livelli (Servizi)**        | ![Possibile con le macchine virtualiPossible with VMs](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Consigliato con il servizio app](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Possibile con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con Le fuzioni di AzurePossible with Azure Fuctions](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | |
| **Cloud-Native (Microservizi)**  | | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | ![Consigliato con AKS](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (contenitori Linux)&nbsp;| ![Consigliato con funzioni di AzureRecommended with Azure Functions](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (&#x2011;guidata dall'evento) | |
| **Batch/Processi (attività in background)** | ![Possibile con le macchine virtualiPossible with VMs](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con il servizio app](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Consigliato con funzioni di AzureRecommended with Azure Functions](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Attività&nbsp;in background) | ![Consigliato con Azure BatchRecommended with Azure Batch](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Scala&#x2011;grande) |

**Leggenda**

![Icona Consigliata](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) Consigliato .
![Icona possibile](media/choosing-azure-compute-options-for-container-based-applications/possible.png) Possibile

> [!div class="step-by-step"]
> [Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [precedente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
