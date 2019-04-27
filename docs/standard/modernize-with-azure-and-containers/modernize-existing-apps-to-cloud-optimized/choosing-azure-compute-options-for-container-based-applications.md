---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Scegliere le piattaforme di calcolo di Azure per le applicazioni basate su contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: f251aecfeaf2421a5cecf218577369963bc736fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61811761"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore

Come è stato certamente notato dopo la lettura delle sezioni precedenti, Azure è un cloud aperta che offre più opzioni. È possibile usare la soluzione ottimale per le proprie esigenze, tuttavia, lo segnala anche domande su quale prodotto/tecnologia deve usare per le applicazioni in contenitori.

Come un *per impostazione predefinita* raccomandazione, di seguito è riportato il criterio principale consigliato in questa guida:

- **Singola app monolitica, occorre:** Scegliere servizio App di Azure
- **App a più livelli:** Scegliere gli agenti di orchestrazione, ad esempio servizio App, Service Fabric (SF) o Azure Kubernetes Service (AKS) se si dispone di uno o alcuni servizi di back-end
- **Microservizi di Linux:** Scegliere servizio contenitore di AZURE/Kubernetes
- **Microservizi di Windows:** Scegliere Service Fabric
- **Le funzioni senza server e i gestori eventi:** Scegliere le funzioni di Azure
- **Batch su vasta scala:** Scegli Azure Batch

Tuttavia, questa raccomandazione attenzione con un con avvicinamento delle dita di salt, come selezione del prodotto varia in base alle esigenze e le caratteristiche dell'applicazione specifico. Non tutte le applicazioni sono gli stessi, anche se inizialmente risultino tipi simili.

Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso. Ma, come punto di partenza, è buona norma disporre le indicazioni iniziali da dove iniziare la valutazione e test di base di determinate priorità.

Nella figura che segue, è possibile analizzare più globale durante la tabella decisioni dettagliati.

![](./media/image8.5.png)

Si noti come il sottostante del sistema operativo (Windows Visual Studio. Linux) può anche rappresentare un fattore di decisione perché alcuni agenti di orchestrazione sono più maturo in contenitori Linux e altre sui contenitori di Windows. Ad esempio, i contenitori Linux sono molto maturi in Kubernetes (servizio contenitore di AZURE in Azure) ma meno maturo in Service Fabric. D'altra parte, i contenitori Windows sono più "maturo" Service Fabric (rilasciato a maggio 2017) e meno maturo in AKS.

Tuttavia, tali differenze nel livello di maturità del sistema operativo verranno dissolvenza in entrata in futuro e più piattaforme abbiano confrontabili maturità del sistema operativo e la decisione si troveranno altre preferenze basata su funzionalità specifiche dell'applicazione potrebbe essere necessario o base ecosistema di ciascuna piattaforma motivi.

> [!div class="step-by-step"]
> [Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
