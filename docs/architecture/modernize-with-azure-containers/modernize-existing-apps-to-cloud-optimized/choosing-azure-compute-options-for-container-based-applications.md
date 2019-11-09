---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitori
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "73737014"
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

Nella figura 1 è possibile visualizzare una suddivisione dei diversi tipi di app e i relativi scenari di hosting di Azure ideali.

![Tabella di cui gli scenari di hosting di Azure sono migliori per le diverse app.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> [Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
