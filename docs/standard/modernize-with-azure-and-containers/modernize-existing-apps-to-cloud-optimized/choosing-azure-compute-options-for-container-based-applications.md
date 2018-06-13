---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate sul contenitore
description: Modernizzare le applicazioni .NET esistenti con i contenitori di Windows e Cloud di Azure | Scelta delle piattaforme di calcolo di Azure per le applicazioni basate sul contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958011"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Scelta delle piattaforme di calcolo di Azure per le applicazioni basate sul contenitore

Come si notare dopo la lettura delle sezioni precedenti, Azure è un cloud aperto che offre più opzioni. È possibile usare la scelta migliore per le proprie esigenze, tuttavia, anche superfici domande sul prodotto o tecnologia deve usare per le applicazioni nei contenitori.

Come un *per impostazione predefinita* , quanto segue si consiglia di principali criteri consigliati in questa guida:

  - **Singola app monolitico:** scegliere servizio App di Azure
  - **App a più livelli:** scegliere orchestrators quali Azure Kubernetes servizio (AKS), Service Fabric (SF) o il servizio App se si dispone di un singolo o alcuni servizi back-end
  - **Linux microservizi:** scegliere AKS/Kubernetes
  - **Windows microservizi:** scegliere Service Fabric
  - **Funzioni senza server & gestori di eventi:** scegliere le funzioni di Azure
  - **Batch su vasta scala:** scegliere Azure Batch

Tuttavia, questa indicazione è opportuno tenere con un zoom indietro del salt, come selezione del prodotto varia in base alle esigenze e le caratteristiche dell'applicazione specifica. Non tutte le applicazioni sono gli stessi anche quando inizialmente sembrano tipi simili.

Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso. Ma, come un punto di partenza, è opportuno usare le istruzioni iniziali da dove è possibile avviare la valutazione e il test in base a determinati la priorità.

Nella figura che segue, è possibile analizzare più globale durante la tabella decisioni dettagliate.

![](./media/image8.5.png)

Si noti il modo in cui sottostante del sistema operativo (Windows Visual Studio. Linux) può anche rappresentare un fattore di decisione come alcuni orchestrators sono più maturo sui contenitori di Linux e altri in contenitori di Windows. Ad esempio, i contenitori di Linux sono molto maturi in Kubernetes (AKS in Azure), ma meno avanzata nell'infrastruttura del servizio. D'altro canto, i contenitori di Windows sono più maturo in Service Fabric (rilasciato nel maggio 2017) e meno avanzata in AKS.

Tuttavia, queste differenze in scadenza del sistema operativo gradualmente in futuro e più piattaforme avrà confrontabili maturità del sistema operativo e la decisione si troveranno altre preferenze in base alle funzionalità specifiche dell'applicazione potrebbe essere necessario o in base a ecosistema di ciascuna piattaforma motivi.


>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
