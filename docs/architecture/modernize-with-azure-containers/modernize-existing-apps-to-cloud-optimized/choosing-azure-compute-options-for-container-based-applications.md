---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitori
ms.date: 02/18/2020
ms.openlocfilehash: 52e7cf1c5dd3a5850564bdb33ac7a4ac4904f432
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503869"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore

Come si è notato dopo aver letto le sezioni precedenti, Azure è un cloud aperto che offre più opzioni. È tuttavia possibile usare la soluzione più adatta alle proprie esigenze, ma anche le domande sul prodotto/tecnologia da usare per le applicazioni in contenitori.

Come raccomandazione *per impostazione predefinita* , di seguito sono riportati i criteri principali consigliati in questa guida:

- **Singola app monolitica:** Scegliere app Azure servizio
- **App a più livelli:** Scegliere gli agenti di orchestrazione, ad esempio Azure Kubernetes Service (AKS) o il servizio app, se si dispone di un singolo o di pochi servizi back-end
- **Microservizi:** Scegliere AKS o app Web di Azure per contenitori
- **Funzioni senza server & gestori eventi:** Scegliere funzioni di Azure
- **Batch su larga scala:** Scegliere Azure Batch

Questa raccomandazione, tuttavia, deve essere eseguita con un pizzico di Salt, in quanto la selezione del prodotto dipende dalle esigenze e dalle caratteristiche specifiche dell'applicazione. Non tutte le applicazioni sono le stesse anche quando inizialmente potrebbero sembrare tipi simili.

Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso. Tuttavia, come punto di partenza, è opportuno disporre di indicazioni iniziali da cui è possibile iniziare a valutare e testare in base a una determinata priorità.

Nella tabella seguente è possibile visualizzare una suddivisione dei diversi tipi di app e i relativi scenari di hosting di Azure possibili e consigliati.

| Architettura dell'applicazione | VM-macchine virtuali di Azure | ACI-istanze di contenitore di Azure | Servizio app Azure (contenitori w-w/o) | AKS-Servizi Kubernetes di Azure | Funzioni di Azure | Azure Batch |
|:------------------------:|:--:|:--:|:--:|:--:|:--:|:--:|
| **App Web (monolitica)**         | ![Possibili con le macchine virtuali](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Consigliato con il servizio app](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Possibile con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | |
| **App a più livelli (servizi)**        | ![Possibili con le macchine virtuali](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Consigliato con il servizio app](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Possibile con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con Azure fuctions](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | |
| **Nativo del cloud (microservizi)**  | | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | ![Consigliato con AKS](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Contenitori&nbsp;Linux)| ![Consigliato con funzioni di Azure](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Basato&#x2011;su eventi) | |
| **Batch/processi (attività in background)** | ![Possibili con le macchine virtuali](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con il servizio app](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Possibile con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Consigliato con funzioni di Azure](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Attività in background&nbsp;) | ![Consigliato con Azure Batch](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Larga&#x2011;scala) |

**Legenda**

![Icona consigliata](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) Consigliabile
![Icona possibile](media/choosing-azure-compute-options-for-container-based-applications/possible.png) Possibile

> [!div class="step-by-step"]
> [Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
